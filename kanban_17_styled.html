<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Канбан-доска броней (17 столов)</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: sans-serif; background: #eef2f5; padding: 20px; line-height: 1.4; }
    h2 { margin-bottom: 16px; color: #333; }
    .controls { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }
    .controls input, .controls select, .controls button {
      padding: 6px 10px;
      border: 1px solid #bbb;
      border-radius: 4px;
      background: #fff;
    }
    .controls button { 
      background: #4078c0; 
      color: #fff; 
      border-color: #305a8c; 
      cursor: pointer; 
    }
    .controls button:hover { background: #305a8c; }
    .clear-btn { background: #c0392b; border-color: #922b21; }
    .clear-btn:hover { background: #922b21; }
    .board {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }
    .cell {
      background: #fff;
      border: 1px solid #dde2e8;
      border-radius: 6px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }
    .cell-header {
      background: #4078c0;
      color: #fff;
      text-align: center;
      padding: 8px;
      font-weight: bold;
      font-size: 14px;
    }
    .cell-body {
      flex: 1;
      padding: 8px;
      overflow-y: auto;
    }
    .cell-footer {
      background: #f5f7fa;
      color: #555;
      text-align: center;
      padding: 6px;
      font-size: 13px;
      border-top: 1px solid #dde2e8;
    }
    .card {
      background: #ffeeba;
      border-left: 6px solid #d39e00;
      border-radius: 4px;
      padding: 8px;
      margin-bottom: 8px;
      box-shadow: 0 1px 2px rgba(0,0,0,0.1);
      cursor: move;
      transition: transform .1s;
      font-size: 13px;
    }
    .card:hover { transform: translateY(-2px); }
    .green {
      background: #d4edda !important;
      border-left-color: #28a745 !important;
    }
    .status-btn, .delete-btn {
      margin-top: 6px;
      background: transparent;
      border: none;
      color: #555;
      cursor: pointer;
      font-size: 12px;
      padding: 2px 4px;
    }
    .delete-btn { color: #c0392b; }
  </style>
</head>
<body>

<h2>Канбан-доска броней (17 столов)</h2>

<div class="controls">
  <input id="name" placeholder="Имя">
  <input id="phone" placeholder="Телефон">
  <select id="table"><option disabled selected>Стол</option></select>
  <input id="time" type="time">
  <input id="guests" type="number" placeholder="Гостей">
  <select id="source">
    <option disabled selected>Источник</option>
    <option value="Звонок">Звонок</option>
    <option value="Лично">Лично</option>
    <option value="Онлайн">Онлайн</option>
  </select>
  <label><input id="hookah" type="checkbox"> Кальян</label>
  <label><input id="vr" type="checkbox"> VR</label>
  <button onclick="addCard()">Добавить</button>
  <button class="clear-btn" onclick="clearAll()">Очистить все</button>
</div>

<div class="board" id="board"></div>

<script>
  // Сгенерировать список столов и селект
  const tableSelect = document.getElementById('table');
  const board = document.getElementById('board');
  for (let i = 1; i <= 17; i++) {
    // опция в селекте
    const opt = document.createElement('option');
    opt.value = i; opt.textContent = i;
    tableSelect.appendChild(opt);

    // определить вместимость
    let cap;
    if (i <= 8) cap = '4–6 чел.';
    else if ([9,12,16].includes(i)) cap = '4 чел.';
    else if ([13,14].includes(i)) cap = '2 чел.';
    else if ([10,11,15].includes(i)) cap = '8 чел.';
    else cap = 'VIP 12+ чел.';

    // создать ячейку стола
    const cell = document.createElement('div');
    cell.className = 'cell';
    cell.id = 'table-' + i;
    cell.ondragover = ev => ev.preventDefault();
    cell.ondrop = ev => drop(ev);
    cell.innerHTML = `
      <div class="cell-header">Стол ${i}</div>
      <div class="cell-body"></div>
      <div class="cell-footer">${cap}</div>
    `;
    board.appendChild(cell);
  }

  let cardId = 0;
  function drag(ev) {
    ev.dataTransfer.setData('text', ev.target.id);
  }
  function drop(ev) {
    ev.preventDefault();
    const id = ev.dataTransfer.getData('text');
    const target = ev.currentTarget.querySelector('.cell-body');
    target.appendChild(document.getElementById(id));
    saveState();
  }

  function addCard() {
    const name   = document.getElementById('name').value.trim();
    const phone  = document.getElementById('phone').value.trim();
    const table  = document.getElementById('table').value;
    const time   = document.getElementById('time').value;
    const guests = document.getElementById('guests').value;
    const source = document.getElementById('source').value;
    const hookah = document.getElementById('hookah').checked ? 'Кальян' : '';
    const vr     = document.getElementById('vr').checked     ? 'VR'     : '';
    if (!name || !phone || !table || !time || !guests || !source) return;

    const card = document.createElement('div');
    card.className = 'card red';
    card.id = 'card-' + cardId++;
    card.draggable = true;
    card.ondragstart = drag;
    card.innerHTML = `
      <strong>${name}</strong><br>
      ${time} · ${guests} чел.<br>
      тел. ${phone}<br>
      src: ${source}${hookah?'<br>🍹':''}${vr?'<br>🎮':''}<br>
      <button class="status-btn" onclick="toggleStatus('${card.id}')">Статус</button>
      <button class="delete-btn" onclick="deleteCard('${card.id}')">Удалить</button>
    `;
    document.querySelector('#table-' + table + ' .cell-body').appendChild(card);
    saveState();
  }

  function toggleStatus(id) {
    const c = document.getElementById(id);
    c.classList.toggle('green');
    saveState();
  }

  function deleteCard(id) {
    const card = document.getElementById(id);
    if (card) card.remove();
    let data = JSON.parse(localStorage.getItem('kanban17') || '[]');
    data = data.filter(item => item.id !== id);
    localStorage.setItem('kanban17', JSON.stringify(data));
  }

  function clearAll() {
    document.querySelectorAll('.card').forEach(c => c.remove());
    localStorage.removeItem('kanban17');
  }

  function saveState() {
    const data = [];
    document.querySelectorAll('.cell').forEach(cell => {
      const t = cell.id.split('-')[1];
      cell.querySelectorAll('.card').forEach(c => {
        data.push({ id: c.id, table: t, cls: c.className, html: c.innerHTML });
      });
    });
    localStorage.setItem('kanban17', JSON.stringify(data));
  }

  function loadState() {
    const data = JSON.parse(localStorage.getItem('kanban17') || '[]');
    data.forEach(item => {
      const cell = document.querySelector('#table-' + item.table + ' .cell-body');
      if (!cell) return;
      const c = document.createElement('div');
      c.id = item.id;
      c.className = item.cls;
      c.draggable = true;
      c.ondragstart = drag;
      c.innerHTML = item.html;
      cell.appendChild(c);
    });
  }

  window.onload = loadState;
</script>

</body>
</html>

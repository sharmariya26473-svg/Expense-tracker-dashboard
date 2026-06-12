let expenses = [];

function addExpense() {
  let name = document.getElementById("expName").value;
  let amount = parseFloat(document.getElementById("expAmount").value);
  let category = document.getElementById("expCategory").value;

  // Basic validation
  if (!name || !amount) {
    alert("Please fill all fields!");
    return;
  }

  // Create expense object
  let expense = { name, amount, category };
  expenses.push(expense);

  // Refresh display
  displayExpenses();
  updateTotal();

  // Clear inputs
  document.getElementById("expName").value = "";
  document.getElementById("expAmount").value = "";
}

function displayExpenses() {
  let list = document.getElementById("expenseList");
  list.innerHTML = "";

  expenses.forEach((exp, index) => {
    list.innerHTML += `
      <li>
        <span>${exp.name} (${exp.category})</span>
        <span>₹${exp.amount}</span>
        <span class="delete" onclick="deleteExpense(${index})">🗑️</span>
      </li>
    `;
  });
}

function updateTotal() {
  let total = expenses.reduce((sum, exp) => sum + exp.amount, 0);
  document.getElementById("total").textContent = total.toFixed(2);
}

function deleteExpense(index) {
  expenses.splice(index, 1);
  displayExpenses();
  updateTotal();
}

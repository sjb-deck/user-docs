# Reverting Transactions

!!! warning
    Reverting transactions is **not possible** without admin privileges.

!!! danger
    Reverting an item order will result in the transaction being marked as "Reverted" and will not be displayed in the transaction log. **Users cannot undo the revert action**.

The Revert Transactions feature allows users to revert transactions in the system. 

## Reverting Item Orders

!!! note
    Some item order transactions linking to kits cannot be reverted. To revert them, the user must first revert the kit transaction.

1. Click on the "View Transactions" button in the sidebar navigation.
2. Click on the "Orders" tab.
3. Search for the transaction you want to revert.
4. Click on the "Revert" button.
5. A confirmation message will appear, click on "Confirm" to revert the transaction.

## Reverting Loans

``` mermaid
graph LR
  A[Start] -->|Loan Submitted| B[Loan Active]
    B -->|Loan Returned Full| C[Loan Inactive]
    B -->|Loan Returned Partial| C[Loan Inactive]
    C -->|Revert Loan| B
    B -->|Revert Loan| A
```

The process of reverting loans is similar to reverting item orders. However, reverting a loan will only bring it back to its previous state. ie. If the loan has been returned, reverting the loan will bring it back to an active state.

## Reverting Kits

The process of reverting kits is similar to reverting item orders. However, there are some limitations to reverting kits.

* We can only revert the latest transaction of a kit. ie. If a kit has multiple transactions, we can only revert the latest transaction.
* If the kit transaction is linked to an item order transaction, the item order transaction cannot be reverted only the kit transaction can be reverted, which will also revert the item order transaction.
## Learn about delegatecall attacks - where one contract can change data in another | Learn Web3 DAO

.delegatecall() is a method in Solidity used to call a function in a target contract from an original contract. However, unlike other methods, when the function is executed in the target contract using

.delegatecall(), the context is passed from the original contract i.e. the code executes in the target contract, but variables get modified in the original contract.

Through this tutorial, we will learn why its important to correctly understand how .delegatecall() works or else it can have some severe consequences.

```shell
Compiled 4 Solidity files successfully

  delegatecall Attack
Helper Contract's Address: 0x5FbDB2315678afecb367f032d93F642f64180aa3
Good Contract's Address: 0xe7f1725E7734CE288F8367e1Bb143E90bb3F0512
Attack Contract's Address 0x9fE46736679d2D9a65F0992F2272dE9f3c7fa6e0
    ✔ Should change the owner of the Good contract (1116ms)

  Lock
    Deployment
      ✔ Should set the right unlockTime (47ms)
      ✔ Should set the right owner
      ✔ Should receive and store the funds to lock
      ✔ Should fail if the unlockTime is not in the future
    Withdrawals
      Validations
        ✔ Should revert with the right error if called too soon
        ✔ Should revert with the right error if called from another account
        ✔ Shouldn't fail if the unlockTime has arrived and the owner calls it
      Events
        ✔ Should emit an event on withdrawals
      Transfers
        ✔ Should transfer the funds to the owner


  10 passing (1s)
```

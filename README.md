# Sports Token

This Solidity contract defines a basic implementation of a token contract named "Sports Token" (symbol: SPORT).

## Description

The contract includes functionalities to manage a token:
1. Token Details: Public variables store details about the token such as its name (Sports Token), abbreviation (SPORT), and total supply (totalSupply).
2. Token Balances: Uses a mapping (balances) to find the track of token balances for each address.
3. Mint Function: Increase the total supply and adds tokens to the balance of a specified address (addr).
4. Burn Function: Decreases the total supply and removes tokens from the balance of a specified address (addr). It includes a check to ensure that the address has sufficient tokens to burn (balances[addr] >= amount).

## Requirements

1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
2. Your contract will have a mapping of addresses to balances (address => uint)
3. You will have a mint function that takes two parameters: an address and a value. 
   The function then increases the total supply by that number and increases the balance 
   of the “sender” address by that amount
4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
   It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.
5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal  to the amount that is supposed to be burned.

## Getting Started

### Executing program

To interact with this contract:
1. Use Remix, an online Solidity IDE. Visit the [Remix website](https://remix.ethereum.org/).
2. Create a new file named SportsToken.sol and paste the following code:

   solidity
   // SPDX-License-Identifier: MIT
   pragma solidity 0.8.25;

   contract SportsToken {

       string public constant name = "Sports Token";
       string public constant symbol = "SPORT";
       uint public totalSupply = 0;

       // Mapping for token balances
       mapping(address => uint) public balances;

       // Mint function 
       function mint(address addr, uint amount) public {
           totalSupply += amount;
           balances[addr] += amount;
       }

       // Burn function 
       function burn(address addr, uint amount) public {
           require(balances[addr] >= amount, "Insufficient balance to burn");
           totalSupply -= amount;
           balances[addr] -= amount;
       }
   }
   

3. Navigate to the "Solidity Compiler" tab in Remix, and click "Compile SportsToken.sol".
4. Deploy the contract using the "Deploy & Run Transactions" tab. Select the SportsToken contract, specify parameters (if any), and click "Deploy".
5. It will show the updated transactions.

## LEARNER

SHUBHAM

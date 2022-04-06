## Getting Started

`cargo install spl-token-cli`

## Creating the SPL token

Instead of `devnet` you can also use mainnet

`spl-token create-token --url devnet`

You will get a result similer to this

```
Creating token <TOKEN-ADDRESS>

Signature: <TOKEN-SIFNATURE>
```

## Minting

A wallet can have multiple account and each account can have multiple token. To create an account to hold our token, we need to use:

`spl-token create-account <TOKEN-ADDRESS> --url devnet`

You will get a result like this

```
Creating account <ACCOUNT-ADDRESS>

Signature: <SIGNATURE>
```

## Check the balance

`spl-token balance <TOKEN_ADDRESS> --url <NETWORK>`

Initially it will log 0

To mint new token:
`spl-token mint <TOKEN_ADDRESS> <AMOUNT> --url <NETWORK>`

Resulting LOG

```
Minting 1000 tokens
  Token: <TOKEN-ADDRESS>
  Recipient: <ACCONT-ADDRESS>

Signature: <SIGNATURE>
```

Check the balance and you will get the result.

**Note:** Only you have the previllage to mint tokens

## Circulating the supply of tokens

Check the number of tokens available in the total network:

`spl-token supply CJ1nMXhZEN6Q28CAjVxHHEsTbVnnmJhexpG2d1Xx4riL --url devnet`

### LIMIT TOKEN

You can limit the total supply of tokens on the solana blockchain also:

1. Mint the total supply
2. Disable minting facilities by:
   `spl-token authorize <TOKEN_ADDRESS> mint --disable --url <NETWORK>`

You can check if it is disabled or not by trying to mint new tokens

### BURN TOKEN

You can burn token by: `spl-token burn <ACCOUNT_ADDRESS> <AMOUNT_TO_BURN> --url devnet`

You can check your balance to make sure the tokens have burnt

## Send tokens to phantom wallet

`spl-token transfer <TOKEN_ADDRESS> <AMOUNT> <ADDRESS_OF_FRIEND> --url <NETWORK> --fund-recipient`

#Tryton Shell

## Installation
`pip install tryton_shell`

## Usage

`tryton_shell -d <database> -c <path to tryton_config>`

default config is `/etc/trytond.conf`

or

After setting environment variable `DB_NAME`, `TRYTOND_DATABASE_URI`

`tryton_shell`

should do the job and if you prefer using `IPython's Shell` then

`tryton_shell -i` or `tryton_shell --ipython`


### Inside `tryton_shell`

* `B(readonly=True)` Begin new transaction.
* `E(commit=True)` End transaction.
* `change_password(username, new_password)` change user's password.

#### Example

```python
B(False)
Party = Pool().get('party.party')
party = Party()
party.name = 'John Lock'
party.save()
E(True)
```

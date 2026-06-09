# StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdFromUser(Windows::Internal::StateRepository::IUser *,StateRepository::Database &,__int64 *,bool *)

- ea: `0x18000dc60`
- end: `0x18000e13b`
- name: `?TryGet_UserIdFromUser@User@DataAccessLayer@WinRT@StateRepository@@SAJPEAUIUser@4Internal@Windows@@AEAVDatabase@4@PEA_JPEA_N@Z`
- size: `1243`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IUser *, struct StateRepository::Database *, __int64 *, bool *)`
- caller_count: `295`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1800041c0`
- `0x180004650`
- `0x180009ba0`
- `0x18000a230`
- `0x18000bb70`
- `0x18000f090`
- `0x18001d710`
- `0x18001ea80`
- `0x18002d220`
- `0x18003e940`
- `0x180040e40`
- `0x18005feb0`
- `0x180063c50`
- `0x18007a260`
- `0x18007ce20`
- `0x180080910`
- `0x180082280`
- `0x180082c10`
- `0x180084540`
- `0x180084ce0`
- `0x1800853e0`
- `0x1800894e0`
- `0x18008b960`
- `0x18008c450`
- `0x18008dc70`
- `0x18008f080`
- `0x18008f810`
- `0x1800918a0`
- `0x180091d80`
- `0x180092d60`
- `0x180096930`
- `0x180098080`
- `0x1800984b0`
- `0x18009a9b0`
- `0x18009cbf0`
- `0x1800a40c0`
- `0x1800a4710`
- `0x1800a4cf0`
- `0x1800a5380`
- `0x1800a5680`
- `0x1800a5960`
- `0x1800a7410`
- `0x1800a7760`
- `0x1800b62f0`
- `0x1800b6fc0`
- `0x1800b8430`
- `0x1800c1380`
- `0x1800c2670`
- `0x1800c31f0`
- `0x1800c48e0`

## callees

- `0x180007a40`
- `0x18000a100`
- `0x18000dc60`
- `0x18000e694`
- `0x180010d28`
- `0x1800131f8`
- `0x180017a58`
- `0x180018bbc`
- `0x180019794`
- `0x18001a548`
- `0x18001a9e0`
- `0x18018fb50`
- `0x18020b074`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e05d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e05d`
- `StateRepository.Core!sqlite3_db_handle` at `0x18000e030`
- `StateRepository.Core!sqlite3_db_handle` at `0x18000e030`
- `StateRepository.Core!sqlite3_column_int64` at `0x18000dfae`
- `StateRepository.Core!sqlite3_column_int64` at `0x18000dfae`
- `StateRepository.Core!sqlite3_errcode` at `0x18000e000`
- `StateRepository.Core!sqlite3_errcode` at `0x18000e000`

## string_xrefs

- `0x18000ddeb`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18000de05`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000df2e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000df61`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000df88`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000e0dc`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x18000dd23`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000df77`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000e112`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000ddcf`: `SELECT _UserID FROM User WHERE UserSid=?;`
- `0x18000dce6`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`
- `0x18000de39`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`
- `0x18000e08a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`

## pseudocode

```c

```

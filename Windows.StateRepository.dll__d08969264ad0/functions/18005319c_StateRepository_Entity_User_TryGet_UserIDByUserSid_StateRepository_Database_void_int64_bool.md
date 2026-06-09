# StateRepository::Entity::User::TryGet_UserIDByUserSid(StateRepository::Database &,void *,__int64 *,bool &)

- ea: `0x18005319c`
- end: `0x180053568`
- name: `?TryGet_UserIDByUserSid@User@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEA_JAEA_N@Z`
- size: `972`
- prototype: `__int64 __fastcall(struct sqlite3 **, void *, __int64 *, bool *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180053140`
- `0x1800be9ec`

## callees

- `0x180007a40`
- `0x18000a100`
- `0x180010d28`
- `0x1800131f8`
- `0x180017a58`
- `0x180018bbc`
- `0x180019794`
- `0x18001a548`
- `0x18001a9e0`
- `0x18005319c`
- `0x18018fb50`
- `0x18020b074`
- `0x18027e010`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x180053487`
- `StateRepository.Core!sqlite3_db_handle` at `0x180053487`
- `StateRepository.Core!sqlite3_column_int64` at `0x180053402`
- `StateRepository.Core!sqlite3_column_int64` at `0x180053402`
- `StateRepository.Core!sqlite3_errcode` at `0x180053457`
- `StateRepository.Core!sqlite3_errcode` at `0x180053457`

## string_xrefs

- `0x180053217`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180053234`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180053309`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180053319`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18005336c`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x1800534f0`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x1800532f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180053526`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18005353e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1800531ec`: `SELECT _UserID FROM User WHERE UserSid=?;`
- `0x18005326e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`
- `0x1800533a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`
- `0x1800534b5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`

## pseudocode

```c

```

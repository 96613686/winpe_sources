# StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)

- ea: `0x1800131f8`
- end: `0x180013723`
- name: `?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z`
- size: `1323`
- prototype: `__int64 __fastcall(struct sqlite3 *, char *, __int64, struct sqlite3_stmt **)`
- caller_count: `29`
- callee_count: `17`
- tags: ``

## callers

- `0x180005c60`
- `0x18000629c`
- `0x1800065fc`
- `0x180006950`
- `0x180006ca8`
- `0x180006fec`
- `0x180007384`
- `0x1800076c0`
- `0x18000bb70`
- `0x18000dc60`
- `0x18000e144`
- `0x180010260`
- `0x180010a48`
- `0x180011bfc`
- `0x180012e84`
- `0x1800140f4`
- `0x1800189bc`
- `0x180018de8`
- `0x180019324`
- `0x180019d90`
- `0x18001a070`
- `0x18001a450`
- `0x18001a730`
- `0x180030c58`
- `0x18005319c`
- `0x1800590fc`
- `0x180062ee0`
- `0x1800640b0`
- `0x1800adc4c`

## callees

- `0x1800131f8`
- `0x180017a58`
- `0x180018400`
- `0x180063268`
- `0x18006aff0`
- `0x1800a3060`
- `0x1800a3384`
- `0x1800a4ff8`
- `0x1800b187c`
- `0x1800bd500`
- `0x1800c0040`
- `0x18018f650`
- `0x180190234`
- `0x180207eac`
- `0x180262e18`
- `0x180263be0`
- `0x180275c14`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800132dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800132dc`
- `StateRepository.Core!sqlite3_log` at `0x1800132a4`
- `StateRepository.Core!sqlite3_log` at `0x1800134c6`
- `StateRepository.Core!sqlite3_log` at `0x180013579`
- `StateRepository.Core!sqlite3_log` at `0x1800136b5`
- `StateRepository.Core!sqlite3_log` at `0x1800136f4`
- `StateRepository.Core!sqlite3_log` at `0x1800132a4`
- `StateRepository.Core!sqlite3_log` at `0x1800134c6`
- `StateRepository.Core!sqlite3_log` at `0x180013579`
- `StateRepository.Core!sqlite3_log` at `0x1800136b5`
- `StateRepository.Core!sqlite3_log` at `0x1800136f4`
- `StateRepository.Core!sqlite3_errmsg` at `0x1800133a5`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001364c`
- `StateRepository.Core!sqlite3_errmsg` at `0x1800133a5`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001364c`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x180013526`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x180013526`
- `StateRepository.Core!sqlite3_prepare_v2` at `0x1800132f8`
- `StateRepository.Core!sqlite3_prepare_v2` at `0x1800132f8`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001326c`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001326c`

## string_xrefs

- `0x180013251`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180013391`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c

```

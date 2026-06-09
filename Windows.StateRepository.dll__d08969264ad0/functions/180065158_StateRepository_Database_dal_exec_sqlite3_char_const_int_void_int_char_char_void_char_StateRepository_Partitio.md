# StateRepository::Database::dal_exec(sqlite3 *,char const *,int (*)(void *,int,char * *,char * *),void *,char * *,StateRepository::Partition,long (*)(void *),void *)

- ea: `0x180065158`
- end: `0x180065cc8`
- name: `?dal_exec@Database@StateRepository@@SAJPEAUsqlite3@@PEBDP6AHPEAXHPEAPEAD3@Z23W4Partition@2@P6AJ2@Z2@Z`
- size: `2928`
- prototype: `__int64 __fastcall(struct sqlite3 *, struct sqlite3 *, __int64, __int64, __int64, unsigned int, void (__fastcall *)(__int64), __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1800650e4`

## callees

- `0x180017a58`
- `0x180018400`
- `0x180063268`
- `0x180065158`
- `0x18006aff0`
- `0x180097d64`
- `0x1800a3060`
- `0x1800a3384`
- `0x1800a4ff8`
- `0x1800b187c`
- `0x1800bd500`
- `0x1800c0040`
- `0x18018f650`
- `0x180190234`
- `0x180207eac`
- `0x180208508`
- `0x18020a448`
- `0x180262e18`
- `0x180263264`
- `0x180263be0`
- `0x180275c14`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800653f9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800653f9`
- `StateRepository.Core!sqlite3_log` at `0x1800653a0`
- `StateRepository.Core!sqlite3_log` at `0x18006579d`
- `StateRepository.Core!sqlite3_log` at `0x180065a6c`
- `StateRepository.Core!sqlite3_log` at `0x180065c7f`
- `StateRepository.Core!sqlite3_log` at `0x1800653a0`
- `StateRepository.Core!sqlite3_log` at `0x18006579d`
- `StateRepository.Core!sqlite3_log` at `0x180065a6c`
- `StateRepository.Core!sqlite3_log` at `0x180065c7f`
- `StateRepository.Core!sqlite3_exec` at `0x18006543f`
- `StateRepository.Core!sqlite3_exec` at `0x18006543f`
- `StateRepository.Core!sqlite3_free` at `0x180065410`
- `StateRepository.Core!sqlite3_free` at `0x180065c96`
- `StateRepository.Core!sqlite3_free` at `0x180065410`
- `StateRepository.Core!sqlite3_free` at `0x180065c96`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800651f6`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800651f6`

## string_xrefs

- `0x1800651db`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800654fb`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c

```

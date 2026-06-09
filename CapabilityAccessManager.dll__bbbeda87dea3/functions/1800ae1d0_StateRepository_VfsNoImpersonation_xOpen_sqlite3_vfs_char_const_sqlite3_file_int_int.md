# StateRepository::VfsNoImpersonation::xOpen(sqlite3_vfs *,char const *,sqlite3_file *,int,int *)

- ea: `0x1800ae1d0`
- end: `0x1800ae380`
- name: `?xOpen@VfsNoImpersonation@StateRepository@@CAHPEAUsqlite3_vfs@@PEBDPEAUsqlite3_file@@HPEAH@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct sqlite3_vfs *, const char *, struct sqlite3_file *, int, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180021074`
- `0x1800a0b58`
- `0x1800a2298`
- `0x1800adda0`
- `0x1800ae1d0`
- `0x1800c7010`

## import_xrefs

- `winsqlite3!sqlite3_malloc` at `0x1800ae2a2`
- `winsqlite3!sqlite3_malloc` at `0x1800ae2a2`
- `winsqlite3!sqlite3_log` at `0x1800ae2cc`
- `winsqlite3!sqlite3_log` at `0x1800ae2cc`

## string_xrefs

- `0x1800ae36b`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800ae23a`: `onecore\base\appmodel\staterepository\dataaccesslayer\vfsnoimpersonation.cpp`
- `0x1800ae27a`: `onecore\base\appmodel\staterepository\dataaccesslayer\vfsnoimpersonation.cpp`
- `0x1800ae2c3`: `[vfs:xOpen] #%u sqlite3_malloc() failed`

## pseudocode

```c

```

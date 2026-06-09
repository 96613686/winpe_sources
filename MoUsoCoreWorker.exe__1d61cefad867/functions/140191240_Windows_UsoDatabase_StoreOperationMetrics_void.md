# Windows::UsoDatabase::StoreOperationMetrics(void)

- ea: `0x140191240`
- end: `0x14019178c`
- name: `?StoreOperationMetrics@UsoDatabase@Windows@@UEAAXXZ`
- size: `1356`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this)`
- caller_count: `7`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140190cfc`
- `0x14019d2c0`
- `0x14019d660`
- `0x14019daa0`
- `0x14019dfe0`
- `0x14019e720`
- `0x14019ebb0`

## callees

- `0x14002b6ec`
- `0x1400413a8`
- `0x140044b18`
- `0x140045184`
- `0x140045404`
- `0x14018d1a4`
- `0x140191240`
- `0x140192ad8`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401913b0`
- `winsqlite3!sqlite3_bind_text16` at `0x1401915be`
- `winsqlite3!sqlite3_bind_text16` at `0x1401913b0`
- `winsqlite3!sqlite3_bind_text16` at `0x1401915be`
- `winsqlite3!sqlite3_bind_int` at `0x14019141a`
- `winsqlite3!sqlite3_bind_int` at `0x140191624`
- `winsqlite3!sqlite3_bind_int` at `0x14019141a`
- `winsqlite3!sqlite3_bind_int` at `0x140191624`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140191360`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019156d`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140191360`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019156d`
- `winsqlite3!sqlite3_finalize` at `0x140191495`
- `winsqlite3!sqlite3_finalize` at `0x14019169b`
- `winsqlite3!sqlite3_finalize` at `0x140191495`
- `winsqlite3!sqlite3_finalize` at `0x14019169b`

## string_xrefs

- `0x140191356`: `INSERT INTO VARIABLES (KEY, VALUE, TYPE) VALUES (?, ?, ?) ON CONFLICT(KEY) DO UPDATE SET VALUE = VALUE + excluded.VALUE;`
- `0x140191563`: `INSERT INTO VARIABLES (KEY, VALUE, TYPE) VALUES (?, ?, ?) ON CONFLICT(KEY) DO UPDATE SET VALUE = VALUE + excluded.VALUE;`

## pseudocode

```c

```

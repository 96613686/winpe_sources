# Windows::UsoDatabase::AddCompletedUpdate(SystemInterface::CompletedUpdateStorage const &)

- ea: `0x140195730`
- end: `0x140195cc9`
- name: `?AddCompletedUpdate@UsoDatabase@Windows@@UEAAXAEBUCompletedUpdateStorage@SystemInterface@@@Z`
- size: `1433`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::CompletedUpdateStorage *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14018eaa4`

## callees

- `0x14002cd1c`
- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x140195730`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401957ce`
- `winsqlite3!sqlite3_bind_text16` at `0x14019580d`
- `winsqlite3!sqlite3_bind_text16` at `0x140195891`
- `winsqlite3!sqlite3_bind_text16` at `0x1401958d9`
- `winsqlite3!sqlite3_bind_text16` at `0x140195918`
- `winsqlite3!sqlite3_bind_text16` at `0x14019595a`
- `winsqlite3!sqlite3_bind_text16` at `0x140195a04`
- `winsqlite3!sqlite3_bind_text16` at `0x140195b42`
- `winsqlite3!sqlite3_bind_text16` at `0x1401957ce`
- `winsqlite3!sqlite3_bind_text16` at `0x14019580d`
- `winsqlite3!sqlite3_bind_text16` at `0x140195891`
- `winsqlite3!sqlite3_bind_text16` at `0x1401958d9`
- `winsqlite3!sqlite3_bind_text16` at `0x140195918`
- `winsqlite3!sqlite3_bind_text16` at `0x14019595a`
- `winsqlite3!sqlite3_bind_text16` at `0x140195a04`
- `winsqlite3!sqlite3_bind_text16` at `0x140195b42`
- `winsqlite3!sqlite3_bind_int` at `0x140195a35`
- `winsqlite3!sqlite3_bind_int` at `0x140195a6f`
- `winsqlite3!sqlite3_bind_int` at `0x140195acb`
- `winsqlite3!sqlite3_bind_int` at `0x140195a35`
- `winsqlite3!sqlite3_bind_int` at `0x140195a6f`
- `winsqlite3!sqlite3_bind_int` at `0x140195acb`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019578a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019578a`
- `winsqlite3!sqlite3_finalize` at `0x140195b7a`
- `winsqlite3!sqlite3_finalize` at `0x140195b7a`
- `winsqlite3!sqlite3_bind_null` at `0x140195a91`
- `winsqlite3!sqlite3_bind_null` at `0x140195aed`
- `winsqlite3!sqlite3_bind_null` at `0x140195a91`
- `winsqlite3!sqlite3_bind_null` at `0x140195aed`

## string_xrefs

- `0x140195780`: `INSERT OR REPLACE INTO COMPLETEDUPDATES (PROVIDERID, UPDATEID, TIME, TITLE, DESCRIPTION, MOREINFOURL, HISTORYCATEGORY, UNINSTALL, WASREBOOTREQUIRED, FOROS, METADATA) VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)`

## pseudocode

```c

```

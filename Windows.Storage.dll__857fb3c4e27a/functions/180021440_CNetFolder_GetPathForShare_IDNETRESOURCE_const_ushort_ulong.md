# CNetFolder::_GetPathForShare(IDNETRESOURCE const *,ushort *,ulong)

- ea: `0x180021440`
- end: `0x18002168a`
- name: `?_GetPathForShare@CNetFolder@@AEAAJPEBUIDNETRESOURCE@@PEAGK@Z`
- size: `586`
- prototype: `__int64 __fastcall(CNetFolder *__hidden this, const struct IDNETRESOURCE *, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18001ff10`
- `0x180020e6c`
- `0x180132a30`
- `0x180132bd0`
- `0x180134458`

## callees

- `0x180020cc4`
- `0x180021440`
- `0x180021690`
- `0x1800a3080`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18063e943`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18063e943`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18063ea4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18063ea4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021651`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180021651`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18063ea15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18063ea15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021476`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021577`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021577`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021661`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180021661`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180021500`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180021500`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180021509`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002161b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180021509`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002161b`
- `SHCORE!__imp_ualstrcpynW` at `0x18002160d`
- `SHCORE!__imp_ualstrcpynW` at `0x18002160d`
- `MPR!WNetUseConnectionW` at `0x18063e9ed`
- `MPR!WNetUseConnectionW` at `0x18063e9ed`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800214d0`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800214d0`

## pseudocode

```c

```

# RdVhd::Uvhd::CDirectoryHelper::CopyFileOrFolder(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180013da0`
- end: `0x1800141e0`
- name: `?CopyFileOrFolder@CDirectoryHelper@Uvhd@RdVhd@@UEBAJPEBG00K@Z`
- size: `1088`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180013da0`
- `0x18004ea60`

## callees

- `0x180004db0`
- `0x180013da0`
- `0x1800141e8`
- `0x1800197c0`
- `0x180019b38`
- `0x180043eec`
- `0x180048b28`
- `0x18004cfd0`
- `0x18004d588`
- `0x18004d648`
- `0x18004d784`
- `0x18004e6a0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013eb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013eb3`

## string_xrefs

- `0x180013f44`: `SetFileAttributes(%s, %d) has FAILED in CreateDirectoryForUser`
- `0x180014039`: `CopyFileOrFolder(%s, %s) has FAILED`
- `0x180014160`: `CopyFile(%s, %s) has FAILED`

## pseudocode

```c

```

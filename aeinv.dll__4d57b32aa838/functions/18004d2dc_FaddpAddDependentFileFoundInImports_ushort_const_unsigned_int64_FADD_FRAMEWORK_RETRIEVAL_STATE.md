# FaddpAddDependentFileFoundInImports(ushort const *,unsigned __int64,_FADD_FRAMEWORK_RETRIEVAL_STATE *)

- ea: `0x18004d2dc`
- end: `0x18004d78b`
- name: `?FaddpAddDependentFileFoundInImports@@YAJPEBG_KPEAU_FADD_FRAMEWORK_RETRIEVAL_STATE@@@Z`
- size: `1199`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, struct _FADD_FRAMEWORK_RETRIEVAL_STATE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18004cd24`

## callees

- `0x180006cc0`
- `0x1800197d4`
- `0x18001b0b8`
- `0x18001b5bc`
- `0x18001b830`
- `0x180021ebc`
- `0x18004ba9c`
- `0x18004d2dc`
- `0x180059920`
- `0x18005a8bc`
- `0x18006b234`
- `0x18006bc4c`
- `0x18011855c`
- `0x1801188c8`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004d4fd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004d4fd`
- `KERNEL32!HeapReAlloc` at `0x18004d685`
- `KERNEL32!HeapReAlloc` at `0x18004d685`
- `KERNEL32!HeapAlloc` at `0x18004d665`
- `KERNEL32!HeapAlloc` at `0x18004d665`

## string_xrefs

- `0x18004d550`: `AslFileMappingCreate failed [%x]`
- `0x18004d451`: `FaddpDirectoryPathFromFullPath failed [%x].`
- `0x18004d4d7`: `FaddpPathCombine failed to combind directory/module name [%x].`
- `0x18004d47a`: `StringCchCopyW failed [%x]`

## pseudocode

```c

```

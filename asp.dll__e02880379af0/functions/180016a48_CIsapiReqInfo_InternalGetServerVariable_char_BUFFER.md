# CIsapiReqInfo::InternalGetServerVariable(char *,BUFFER *)

- ea: `0x180016a48`
- end: `0x180016aab`
- name: `?InternalGetServerVariable@CIsapiReqInfo@@AEAAHPEADPEAVBUFFER@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(CIsapiReqInfo *__hidden this, char *, struct BUFFER *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180008470`
- `0x18000a6d0`
- `0x18000a9d0`
- `0x18000ca50`
- `0x180013370`
- `0x180016988`
- `0x1800169c0`
- `0x180017fc0`
- `0x18001e7a0`
- `0x1800491d8`
- `0x180049238`
- `0x180049290`

## callees

- `0x180016a48`
- `0x180064010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002d651`
- `KERNEL32!SetLastError` at `0x18002d651`
- `KERNEL32!GetLastError` at `0x18002d62c`
- `KERNEL32!GetLastError` at `0x18002d62c`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180016a5d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180016a5d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002d642`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002d642`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016a75`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002d66c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016a75`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002d66c`

## pseudocode

```c

```

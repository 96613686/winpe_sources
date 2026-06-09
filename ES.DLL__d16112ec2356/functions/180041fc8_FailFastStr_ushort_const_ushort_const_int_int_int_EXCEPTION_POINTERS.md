# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x180041fc8`
- end: `0x180042073`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `171`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int, struct _EXCEPTION_POINTERS *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025d08`
- `0x180026450`
- `0x180040c9c`

## callees

- `0x1800419a4`
- `0x180041fc8`
- `0x18004239c`
- `0x18004269c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004203b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004203b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180042049`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180042049`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180041ff2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180041ff2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180042023`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180042023`

## string_xrefs

- `0x180042005`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c

```

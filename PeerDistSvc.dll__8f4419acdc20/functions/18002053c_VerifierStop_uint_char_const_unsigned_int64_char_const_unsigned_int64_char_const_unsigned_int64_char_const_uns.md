# VerifierStop(uint,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *,unsigned __int64,char const *)

- ea: `0x18002053c`
- end: `0x1800205f0`
- name: `?VerifierStop@@YAXIPEBD_K0101010@Z`
- size: `180`
- prototype: `void __fastcall(unsigned int, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64, const char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018b38`

## callees

- `0x18002053c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020550`
- `ntdll!DbgPrint` at `0x1800205de`
- `ntdll!DbgPrint` at `0x1800205de`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800205e4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800205e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020564`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020564`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18002055e`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18002055e`

## string_xrefs

- `0x180020575`: `owning thread`

## pseudocode

```c

```

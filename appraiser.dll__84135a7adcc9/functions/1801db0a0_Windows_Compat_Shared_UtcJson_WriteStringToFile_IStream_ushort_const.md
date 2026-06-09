# Windows::Compat::Shared::UtcJson::WriteStringToFile(IStream *,ushort const *)

- ea: `0x1801db0a0`
- end: `0x1801db248`
- name: `?WriteStringToFile@UtcJson@Shared@Compat@Windows@@CAJPEAUIStream@@PEBG@Z`
- size: `424`
- prototype: `__int64 __fastcall(struct IStream *, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801da510`

## callees

- `0x1801db028`
- `0x1801db0a0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1801db0e0`
- `KERNEL32!WideCharToMultiByte` at `0x1801db1a9`
- `KERNEL32!WideCharToMultiByte` at `0x1801db0e0`
- `KERNEL32!WideCharToMultiByte` at `0x1801db1a9`
- `KERNEL32!GetProcessHeap` at `0x1801db15a`
- `KERNEL32!GetProcessHeap` at `0x1801db227`
- `KERNEL32!GetProcessHeap` at `0x1801db15a`
- `KERNEL32!GetProcessHeap` at `0x1801db227`
- `KERNEL32!HeapAlloc` at `0x1801db168`
- `KERNEL32!HeapAlloc` at `0x1801db168`
- `KERNEL32!GetLastError` at `0x1801db0ec`
- `KERNEL32!GetLastError` at `0x1801db11b`
- `KERNEL32!GetLastError` at `0x1801db1b3`
- `KERNEL32!GetLastError` at `0x1801db1de`
- `KERNEL32!GetLastError` at `0x1801db0ec`
- `KERNEL32!GetLastError` at `0x1801db11b`
- `KERNEL32!GetLastError` at `0x1801db1b3`
- `KERNEL32!GetLastError` at `0x1801db1de`
- `KERNEL32!HeapFree` at `0x1801db235`
- `KERNEL32!HeapFree` at `0x1801db235`

## string_xrefs

- `0x1801db13d`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801db200`: `onecore\base\appcompat\shared\unmanaged\utclogger\lib\utcjson.cpp`
- `0x1801db125`: `Windows::Compat::Shared::UtcJson::WriteStringToFile`
- `0x1801db1e8`: `Windows::Compat::Shared::UtcJson::WriteStringToFile`

## pseudocode

```c

```

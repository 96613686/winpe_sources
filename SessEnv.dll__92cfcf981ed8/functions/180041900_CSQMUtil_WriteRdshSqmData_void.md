# CSQMUtil::WriteRdshSqmData(void)

- ea: `0x180041900`
- end: `0x180041afe`
- name: `?WriteRdshSqmData@CSQMUtil@@SAJXZ`
- size: `510`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180019d10`
- `0x180040980`

## callees

- `0x180003f30`
- `0x180021db8`
- `0x180040e44`
- `0x180041900`

## import_xrefs

- `ntdll!WinSqmStartSession` at `0x18004196f`
- `ntdll!WinSqmStartSession` at `0x18004196f`
- `ntdll!WinSqmIsOptedIn` at `0x180041915`
- `ntdll!WinSqmIsOptedIn` at `0x180041915`
- `ntdll!WinSqmSetDWORD` at `0x1800419b2`
- `ntdll!WinSqmSetDWORD` at `0x1800419c7`
- `ntdll!WinSqmSetDWORD` at `0x1800419b2`
- `ntdll!WinSqmSetDWORD` at `0x1800419c7`
- `ntdll!WinSqmEndSession` at `0x180041a68`
- `ntdll!WinSqmEndSession` at `0x180041a68`
- `ntdll!WinSqmAddToStream` at `0x1800419ff`
- `ntdll!WinSqmAddToStream` at `0x180041a3e`
- `ntdll!WinSqmAddToStream` at `0x180041aab`
- `ntdll!WinSqmAddToStream` at `0x1800419ff`
- `ntdll!WinSqmAddToStream` at `0x180041a3e`
- `ntdll!WinSqmAddToStream` at `0x180041aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004197e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004197e`

## string_xrefs

- `0x18004194a`: `CSQMUtil::WriteRdshSqmData`
- `0x180041ade`: `CSQMUtil::WriteRdshSqmData`

## pseudocode

```c

```

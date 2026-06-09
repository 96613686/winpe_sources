# TelemetryController::NetworkLanAvailable(bool &)

- ea: `0x1801aafa8`
- end: `0x1801ab240`
- name: `?NetworkLanAvailable@TelemetryController@@SAJAEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005623c`
- `0x1801aae7c`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x1801aafa8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801ab045`
- `KERNEL32!LoadLibraryExW` at `0x1801ab045`
- `KERNEL32!FreeLibrary` at `0x1801ab207`
- `KERNEL32!FreeLibrary` at `0x1801ab207`
- `KERNEL32!GetProcAddress` at `0x1801ab05d`
- `KERNEL32!GetProcAddress` at `0x1801ab070`
- `KERNEL32!GetProcAddress` at `0x1801ab083`
- `KERNEL32!GetProcAddress` at `0x1801ab05d`
- `KERNEL32!GetProcAddress` at `0x1801ab070`
- `KERNEL32!GetProcAddress` at `0x1801ab083`
- `WS2_32!getaddrinfo` at `0x1801ab146`
- `WS2_32!getaddrinfo` at `0x1801ab146`
- `WS2_32!freeaddrinfo` at `0x1801ab1e2`
- `WS2_32!freeaddrinfo` at `0x1801ab1e2`
- `WS2_32!__imp_gethostname` at `0x1801ab0df`
- `WS2_32!__imp_gethostname` at `0x1801ab0df`
- `WS2_32!__imp_WSAGetLastError` at `0x1801ab0e9`
- `WS2_32!__imp_WSAGetLastError` at `0x1801ab0e9`
- `WS2_32!__imp_WSAStartup` at `0x1801ab0b8`
- `WS2_32!__imp_WSAStartup` at `0x1801ab0b8`
- `WS2_32!__imp_WSACleanup` at `0x1801ab20d`
- `WS2_32!__imp_WSACleanup` at `0x1801ab20d`

## string_xrefs

- `0x1801ab022`: `ws2_32.dll`

## pseudocode

```c

```

# Windows::Internal::CapabilityAccess::Private::IsEraOrSraXboxApp(ulong)

- ea: `0x180043f14`
- end: `0x180043fdf`
- name: `?IsEraOrSraXboxApp@Private@CapabilityAccess@Internal@Windows@@YA_NK@Z`
- size: `203`
- prototype: `bool __fastcall(DWORD dwProcessId, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18006fa20`

## callees

- `0x18002392c`
- `0x18003f4a0`
- `0x180043f14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180043f24`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180043f24`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForProcess` at `0x180043f5c`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForProcess` at `0x180043f8d`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForProcess` at `0x180043f5c`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForProcess` at `0x180043f8d`

## pseudocode

```c

```

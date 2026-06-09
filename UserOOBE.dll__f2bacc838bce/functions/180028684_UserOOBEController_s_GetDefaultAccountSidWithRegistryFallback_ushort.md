# UserOOBEController::s_GetDefaultAccountSidWithRegistryFallback(ushort * *)

- ea: `0x180028684`
- end: `0x180028797`
- name: `?s_GetDefaultAccountSidWithRegistryFallback@UserOOBEController@@CAJPEAPEAG@Z`
- size: `275`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800238b0`

## callees

- `0x1800054ac`
- `0x180005768`
- `0x180007134`
- `0x18000a5c8`
- `0x18000a5e8`
- `0x18000d5a0`
- `0x18000e580`
- `0x180022afc`
- `0x18002849c`
- `0x180028684`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002870d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002870d`

## string_xrefs

- `0x1800286d1`: `DefaultAccountSID`
- `0x18002874f`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c

```

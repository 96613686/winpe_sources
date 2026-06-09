# RegistryPath::InitializeCurrentUserPath(ulong,ushort const *)

- ea: `0x18008194c`
- end: `0x180081a0d`
- name: `?InitializeCurrentUserPath@RegistryPath@@QEAAJKPEBG@Z`
- size: `193`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007dfa4`

## callees

- `0x180079840`
- `0x18007d1b8`
- `0x18008168c`
- `0x18008194c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800819fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800819fa`

## string_xrefs

- `0x18008197e`: `RegistryPath::InitializeCurrentUserPath`
- `0x1800819dd`: `RegistryPath::InitializeCurrentUserPath`
- `0x1800819d6`: `RegistryPath::Initialize`
- `0x18008198b`: `%s: RegOpenCurrentUserKey(%lu) failed with win32 error code: 0x%08x.`

## pseudocode

```c

```

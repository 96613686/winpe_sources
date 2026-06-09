# PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)

- ea: `0x1800952f0`
- end: `0x18009557a`
- name: `?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z`
- size: `650`
- prototype: `static int(const struct Common::COMMON_STRING *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009524c`

## callees

- `0x1800285a4`
- `0x180028770`
- `0x180028afc`
- `0x18004aac0`
- `0x18004d4c8`
- `0x180071f50`
- `0x1800952f0`
- `0x1800992a0`
- `0x18009d729`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800953c1`
- `ntdll!RtlFreeUnicodeString` at `0x18009540a`
- `ntdll!RtlFreeUnicodeString` at `0x180095526`
- `ntdll!RtlFreeUnicodeString` at `0x180095544`
- `ntdll!RtlFreeUnicodeString` at `0x1800953c1`
- `ntdll!RtlFreeUnicodeString` at `0x18009540a`
- `ntdll!RtlFreeUnicodeString` at `0x180095526`
- `ntdll!RtlFreeUnicodeString` at `0x180095544`
- `ntdll!RtlInitUnicodeString` at `0x180095345`
- `ntdll!RtlInitUnicodeString` at `0x180095345`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180095504`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180095504`
- `ntdll!RtlDowncaseUnicodeString` at `0x18009535c`
- `ntdll!RtlDowncaseUnicodeString` at `0x18009535c`

## string_xrefs

- `0x1800953a0`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x1800953ef`: `onecore\base\appmodel\package\packagesid.cpp`

## pseudocode

```c

```

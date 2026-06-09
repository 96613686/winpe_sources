# PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)

- ea: `0x18017472c`
- end: `0x1801749b6`
- name: `?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z`
- size: `650`
- prototype: `static int(const struct Common::COMMON_STRING *, void **)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a12bc`
- `0x180116f8c`
- `0x18017e74c`

## callees

- `0x180012fc8`
- `0x18001bf68`
- `0x18003ba3c`
- `0x1800415ec`
- `0x180043aec`
- `0x1800aed10`
- `0x1800ba45d`
- `0x1800eb94c`
- `0x18017472c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1801747fd`
- `ntdll!RtlFreeUnicodeString` at `0x180174846`
- `ntdll!RtlFreeUnicodeString` at `0x180174962`
- `ntdll!RtlFreeUnicodeString` at `0x180174980`
- `ntdll!RtlFreeUnicodeString` at `0x1801747fd`
- `ntdll!RtlFreeUnicodeString` at `0x180174846`
- `ntdll!RtlFreeUnicodeString` at `0x180174962`
- `ntdll!RtlFreeUnicodeString` at `0x180174980`
- `ntdll!RtlInitUnicodeString` at `0x180174781`
- `ntdll!RtlInitUnicodeString` at `0x180174781`
- `ntdll!RtlDowncaseUnicodeString` at `0x180174798`
- `ntdll!RtlDowncaseUnicodeString` at `0x180174798`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180174940`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180174940`

## string_xrefs

- `0x1801747dc`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x18017482b`: `onecore\base\appmodel\package\packagesid.cpp`

## pseudocode

```c

```

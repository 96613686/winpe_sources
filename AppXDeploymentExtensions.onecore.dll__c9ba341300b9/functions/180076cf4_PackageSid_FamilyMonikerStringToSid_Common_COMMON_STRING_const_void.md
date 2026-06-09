# PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)

- ea: `0x180076cf4`
- end: `0x180076f75`
- name: `?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z`
- size: `641`
- prototype: `static int(const struct Common::COMMON_STRING *, void **)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800dee30`
- `0x180128f7c`
- `0x1801621d4`
- `0x1801e79c4`
- `0x1801f10f0`

## callees

- `0x180012030`
- `0x180012188`
- `0x180076cf4`
- `0x180076f7c`
- `0x1800a219c`
- `0x1800a5970`
- `0x1800cdd78`
- `0x1800f0260`
- `0x1800fc211`
- `0x180211010`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180076f12`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180076f12`
- `ntdll!RtlFreeUnicodeString` at `0x180076db2`
- `ntdll!RtlFreeUnicodeString` at `0x180076e57`
- `ntdll!RtlFreeUnicodeString` at `0x180076f2e`
- `ntdll!RtlFreeUnicodeString` at `0x180076f46`
- `ntdll!RtlFreeUnicodeString` at `0x180076db2`
- `ntdll!RtlFreeUnicodeString` at `0x180076e57`
- `ntdll!RtlFreeUnicodeString` at `0x180076f2e`
- `ntdll!RtlFreeUnicodeString` at `0x180076f46`
- `ntdll!RtlInitUnicodeString` at `0x180076d49`
- `ntdll!RtlInitUnicodeString` at `0x180076d49`
- `ntdll!RtlDowncaseUnicodeString` at `0x180076d5a`
- `ntdll!RtlDowncaseUnicodeString` at `0x180076d5a`

## string_xrefs

- `0x180076df9`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x180076d91`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x180076e3c`: `onecore\base\appmodel\package\packagesid.cpp`

## pseudocode

```c

```

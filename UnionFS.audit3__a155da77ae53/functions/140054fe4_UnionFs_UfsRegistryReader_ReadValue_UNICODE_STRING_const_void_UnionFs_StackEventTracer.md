# UnionFs::UfsRegistryReader::ReadValue(_UNICODE_STRING const &,void *,UnionFs::StackEventTracer &)

- ea: `0x140054fe4`
- end: `0x140055166`
- name: `?ReadValue@UfsRegistryReader@UnionFs@@AEAAJAEBU_UNICODE_STRING@@PEAXAEAVStackEventTracer@2@@Z`
- size: `386`
- prototype: `int(UnionFs::UfsRegistryReader *__hidden this, const struct _UNICODE_STRING *, void *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003e000`
- `0x14005516c`

## callees

- `0x14001014c`
- `0x140054d2c`
- `0x140054fe4`
- `0x140056bd0`
- `0x140056c44`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140055027`
- `ntoskrnl!ZwQueryValueKey` at `0x140055105`
- `ntoskrnl!ZwQueryValueKey` at `0x140055027`
- `ntoskrnl!ZwQueryValueKey` at `0x140055105`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400550bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400550bb`

## string_xrefs

- `0x14005508c`: `UnionFs::UfsRegistryReader::ReadValue`
- `0x140055128`: `UnionFs::UfsRegistryReader::ReadValue`

## pseudocode

```c

```

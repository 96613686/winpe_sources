# UnionFs::UfsRegistryReader::ReadValue(_UNICODE_STRING const &,void *,UnionFs::StackEventTracer &)

- ea: `0x140054e60`
- end: `0x140054fe2`
- name: `?ReadValue@UfsRegistryReader@UnionFs@@AEAAJAEBU_UNICODE_STRING@@PEAXAEAVStackEventTracer@2@@Z`
- size: `386`
- prototype: `int(UnionFs::UfsRegistryReader *__hidden this, const struct _UNICODE_STRING *, void *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003dee0`
- `0x140054fe8`

## callees

- `0x14001012c`
- `0x140054ba8`
- `0x140054e60`
- `0x140056a50`
- `0x140056ac4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140054ea3`
- `ntoskrnl!ZwQueryValueKey` at `0x140054f81`
- `ntoskrnl!ZwQueryValueKey` at `0x140054ea3`
- `ntoskrnl!ZwQueryValueKey` at `0x140054f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054f37`

## string_xrefs

- `0x140054f08`: `UnionFs::UfsRegistryReader::ReadValue`
- `0x140054fa4`: `UnionFs::UfsRegistryReader::ReadValue`

## pseudocode

```c

```

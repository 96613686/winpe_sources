# RegistryPropertyBag::EncryptedDwordProperty::Read(HKEY__ *)

- ea: `0x1800be304`
- end: `0x1800be52b`
- name: `?Read@EncryptedDwordProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `551`
- prototype: `int(RegistryPropertyBag::EncryptedDwordProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800bd7b0`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x1800bd1b4`
- `0x1800bd1dc`
- `0x1800be304`
- `0x1800bf260`

## import_xrefs

- `ntdll!NtQueryKey` at `0x1800be47f`
- `ntdll!NtQueryKey` at `0x1800be47f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be39d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be423`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be39d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be4d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be4d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800be3dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800be3dc`

## pseudocode

```c

```

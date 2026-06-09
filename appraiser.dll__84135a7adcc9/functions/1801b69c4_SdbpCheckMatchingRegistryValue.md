# SdbpCheckMatchingRegistryValue

- ea: `0x1801b69c4`
- end: `0x1801b6d4c`
- name: `SdbpCheckMatchingRegistryValue`
- size: `904`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1801b67dc`
- `0x1801b781c`

## callees

- `0x1800091bc`
- `0x18001a2f4`
- `0x18001b860`
- `0x18001bd08`
- `0x1801b69c4`
- `0x1802174e4`
- `0x1802174f0`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x1801b6a6e`
- `ntdll!ZwQueryValueKey` at `0x1801b6af0`
- `ntdll!ZwQueryValueKey` at `0x1801b6a6e`
- `ntdll!ZwQueryValueKey` at `0x1801b6af0`
- `ntdll!RtlFreeHeap` at `0x1801b6c58`
- `ntdll!RtlFreeHeap` at `0x1801b6c75`
- `ntdll!RtlFreeHeap` at `0x1801b6c92`
- `ntdll!RtlFreeHeap` at `0x1801b6c58`
- `ntdll!RtlFreeHeap` at `0x1801b6c75`
- `ntdll!RtlFreeHeap` at `0x1801b6c92`
- `ntdll!RtlAllocateHeap` at `0x1801b6aa4`
- `ntdll!RtlAllocateHeap` at `0x1801b6baa`
- `ntdll!RtlAllocateHeap` at `0x1801b6cef`
- `ntdll!RtlAllocateHeap` at `0x1801b6aa4`
- `ntdll!RtlAllocateHeap` at `0x1801b6baa`
- `ntdll!RtlAllocateHeap` at `0x1801b6cef`
- `ntdll!RtlInitUnicodeString` at `0x1801b6a4a`
- `ntdll!RtlInitUnicodeString` at `0x1801b6a4a`

## string_xrefs

- `0x1801b6abf`: `SdbpCheckMatchingRegistryValue`
- `0x1801b6b0d`: `SdbpCheckMatchingRegistryValue`
- `0x1801b6afd`: `Failed to read value`
- `0x1801b6b72`: `Unknown registry value data type`
- `0x1801b6a12`: `dbRegistryDefaultName`

## pseudocode

```c

```

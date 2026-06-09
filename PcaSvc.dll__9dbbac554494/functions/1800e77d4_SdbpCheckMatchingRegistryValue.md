# SdbpCheckMatchingRegistryValue

- ea: `0x1800e77d4`
- end: `0x1800e7b54`
- name: `SdbpCheckMatchingRegistryValue`
- size: `896`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e75ec`
- `0x1800e85bc`

## callees

- `0x18000f6c4`
- `0x180012920`
- `0x180012de0`
- `0x180019c84`
- `0x180056262`
- `0x18007aa17`
- `0x1800e77d4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800e782e`
- `msvcrt!_wcsicmp` at `0x1800e782e`
- `ntdll!ZwQueryValueKey` at `0x1800e787f`
- `ntdll!ZwQueryValueKey` at `0x1800e7901`
- `ntdll!ZwQueryValueKey` at `0x1800e787f`
- `ntdll!ZwQueryValueKey` at `0x1800e7901`
- `ntdll!RtlInitUnicodeString` at `0x1800e785b`
- `ntdll!RtlInitUnicodeString` at `0x1800e785b`
- `ntdll!RtlAllocateHeap` at `0x1800e78b5`
- `ntdll!RtlAllocateHeap` at `0x1800e79bb`
- `ntdll!RtlAllocateHeap` at `0x1800e7af7`
- `ntdll!RtlAllocateHeap` at `0x1800e78b5`
- `ntdll!RtlAllocateHeap` at `0x1800e79bb`
- `ntdll!RtlAllocateHeap` at `0x1800e7af7`

## string_xrefs

- `0x1800e790e`: `Failed to read value`
- `0x1800e7983`: `Unknown registry value data type`
- `0x1800e7822`: `dbRegistryDefaultName`
- `0x1800e78d0`: `SdbpCheckMatchingRegistryValue`
- `0x1800e791e`: `SdbpCheckMatchingRegistryValue`

## pseudocode

```c

```

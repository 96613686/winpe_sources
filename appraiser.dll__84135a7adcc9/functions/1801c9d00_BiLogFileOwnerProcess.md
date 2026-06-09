# BiLogFileOwnerProcess

- ea: `0x1801c9d00`
- end: `0x1801ca04d`
- name: `BiLogFileOwnerProcess`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1801c56ec`

## callees

- `0x1801c9d00`
- `0x1801ca330`

## import_xrefs

- `ntdll!ZwQueryInformationFile` at `0x1801c9e36`
- `ntdll!ZwQueryInformationFile` at `0x1801c9e36`
- `ntdll!ZwOpenFile` at `0x1801c9dbc`
- `ntdll!ZwOpenFile` at `0x1801c9dbc`
- `ntdll!ZwClose` at `0x1801c9f72`
- `ntdll!ZwClose` at `0x1801c9fe7`
- `ntdll!ZwClose` at `0x1801ca030`
- `ntdll!ZwClose` at `0x1801c9f72`
- `ntdll!ZwClose` at `0x1801c9fe7`
- `ntdll!ZwClose` at `0x1801ca030`
- `ntdll!RtlFreeHeap` at `0x1801c9f8e`
- `ntdll!RtlFreeHeap` at `0x1801ca004`
- `ntdll!RtlFreeHeap` at `0x1801ca021`
- `ntdll!RtlFreeHeap` at `0x1801c9f8e`
- `ntdll!RtlFreeHeap` at `0x1801ca004`
- `ntdll!RtlFreeHeap` at `0x1801ca021`
- `ntdll!RtlAllocateHeap` at `0x1801c9dfb`
- `ntdll!RtlAllocateHeap` at `0x1801c9f15`
- `ntdll!RtlAllocateHeap` at `0x1801c9dfb`
- `ntdll!RtlAllocateHeap` at `0x1801c9f15`
- `ntdll!ZwQueryInformationProcess` at `0x1801c9ee3`
- `ntdll!ZwQueryInformationProcess` at `0x1801c9f40`
- `ntdll!ZwQueryInformationProcess` at `0x1801c9ee3`
- `ntdll!ZwQueryInformationProcess` at `0x1801c9f40`
- `ntdll!ZwOpenProcess` at `0x1801c9eba`
- `ntdll!ZwOpenProcess` at `0x1801c9eba`

## string_xrefs

- `0x1801c9dc9`: `Failed to open file attributes. Status: %x`
- `0x1801c9d6e`: `Attempting to determine owner of file %ws.`
- `0x1801c9fca`: `Failed to open process. Status: %x`

## pseudocode

```c

```

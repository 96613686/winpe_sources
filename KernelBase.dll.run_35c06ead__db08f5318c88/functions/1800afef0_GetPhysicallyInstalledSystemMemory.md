# GetPhysicallyInstalledSystemMemory

- ea: `0x1800afef0`
- end: `0x1800b0318`
- name: `GetPhysicallyInstalledSystemMemory`
- size: `1064`
- prototype: `BOOL __stdcall(PULONGLONG TotalMemoryInKilobytes)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x1800afef0`
- `0x1800b0320`
- `0x1800b0540`
- `0x1800b0674`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800aff98`
- `ntdll!RtlSetLastWin32Error` at `0x1800b0255`
- `ntdll!RtlSetLastWin32Error` at `0x1800aff98`
- `ntdll!RtlSetLastWin32Error` at `0x1800b0255`
- `ntdll!RtlFreeHeap` at `0x1800b0021`
- `ntdll!RtlFreeHeap` at `0x1800b011b`
- `ntdll!RtlFreeHeap` at `0x1800b0138`
- `ntdll!RtlFreeHeap` at `0x1800b0021`
- `ntdll!RtlFreeHeap` at `0x1800b011b`
- `ntdll!RtlFreeHeap` at `0x1800b0138`
- `ntdll!RtlAllocateHeap` at `0x1800b0079`
- `ntdll!RtlAllocateHeap` at `0x1800b0173`
- `ntdll!RtlAllocateHeap` at `0x1800b0216`
- `ntdll!RtlAllocateHeap` at `0x1800b0079`
- `ntdll!RtlAllocateHeap` at `0x1800b0173`
- `ntdll!RtlAllocateHeap` at `0x1800b0216`

## pseudocode

```c

```

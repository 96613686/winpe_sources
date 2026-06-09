# SeHookManagerAddCallback

- ea: `0x180038ee4`
- end: `0x180039168`
- name: `SeHookManagerAddCallback`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800533f0`

## callees

- `0x18000f114`
- `0x180024a80`
- `0x180038ee4`
- `0x180059175`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180039151`
- `ntdll!RtlLeaveCriticalSection` at `0x180039151`
- `ntdll!RtlEnterCriticalSection` at `0x180038f0d`
- `ntdll!RtlEnterCriticalSection` at `0x180038f0d`
- `ntdll!RtlReAllocateHeap` at `0x1800390a1`
- `ntdll!RtlReAllocateHeap` at `0x1800390a1`
- `ntdll!RtlAllocateHeap` at `0x18003907d`
- `ntdll!RtlAllocateHeap` at `0x18003907d`

## string_xrefs

- `0x180038f18`: `Attempt to hook a NULL callback is illegal`

## pseudocode

```c

```

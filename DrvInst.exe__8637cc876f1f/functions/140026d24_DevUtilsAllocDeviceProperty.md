# DevUtilsAllocDeviceProperty

- ea: `0x140026d24`
- end: `0x140026e51`
- name: `DevUtilsAllocDeviceProperty`
- size: `301`
- prototype: `__int64 __usercall@<rax>(DEVINST dnDevInst@<ecx>, DEVPROPKEY *PropertyKey@<rdx>, DEVPROPTYPE *PropertyType@<r8>, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400149e0`
- `0x140018b38`
- `0x140019cf4`
- `0x14001f0cc`
- `0x1400272a0`
- `0x140029a3c`
- `0x140029db8`
- `0x14002b434`

## callees

- `0x140026d24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140026dd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140026dd9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026dc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026dc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140026e08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026e2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140026e2d`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140026d9b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140026d9b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x140026d8a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x140026d8a`

## pseudocode

```c

```

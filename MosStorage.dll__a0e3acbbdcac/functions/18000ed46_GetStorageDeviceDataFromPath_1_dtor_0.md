# _GetStorageDeviceDataFromPath_::_1_::dtor$0

- ea: `0x18000ed46`
- end: `0x18000ed52`
- name: `_GetStorageDeviceDataFromPath_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006cd0`

## pseudocode

```c
void __fastcall GetStorageDeviceDataFromPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>((char **)(a2 + 48));
}

```

## disassembly

```asm
0x18000ed46  lea     rcx, [rdx+30h]
0x18000ed4d  jmp     ??1?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAA@XZ; std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(void)
```

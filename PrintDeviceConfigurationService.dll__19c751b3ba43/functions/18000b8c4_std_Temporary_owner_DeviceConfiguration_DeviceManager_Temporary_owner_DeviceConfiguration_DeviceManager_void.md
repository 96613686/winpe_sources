# std::_Temporary_owner<DeviceConfiguration::DeviceManager>::~_Temporary_owner<DeviceConfiguration::DeviceManager>(void)

- ea: `0x18000b8c4`
- end: `0x18000b8da`
- name: `??1?$_Temporary_owner@VDeviceManager@DeviceConfiguration@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(DeviceConfiguration::DeviceManager **, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bac8`
- `0x180016943`

## callees

- `0x18000b8c4`
- `0x18000b9e8`

## pseudocode

```c
void *__fastcall std::_Temporary_owner<DeviceConfiguration::DeviceManager>::~_Temporary_owner<DeviceConfiguration::DeviceManager>(
        DeviceConfiguration::DeviceManager **a1,
        unsigned int a2)
{
  DeviceConfiguration::DeviceManager *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return DeviceConfiguration::DeviceManager::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18000b8c4  sub     rsp, 28h
0x18000b8c8  mov     rcx, [rcx]; this
0x18000b8cb  test    rcx, rcx
0x18000b8ce  jz      short loc_18000B8D5
0x18000b8d0  call    ??_GDeviceManager@DeviceConfiguration@@QEAAPEAXI@Z; DeviceConfiguration::DeviceManager::`scalar deleting destructor'(uint)
0x18000b8d5  add     rsp, 28h
0x18000b8d9  retn
```

# std::_Temporary_owner<DeviceConfiguration::WNFListener>::~_Temporary_owner<DeviceConfiguration::WNFListener>(void)

- ea: `0x18000b8e0`
- end: `0x18000b8f6`
- name: `??1?$_Temporary_owner@VWNFListener@DeviceConfiguration@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(DeviceConfiguration::WNFListener **, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bac8`
- `0x180016967`

## callees

- `0x18000b8e0`
- `0x18000ba14`

## pseudocode

```c
void *__fastcall std::_Temporary_owner<DeviceConfiguration::WNFListener>::~_Temporary_owner<DeviceConfiguration::WNFListener>(
        DeviceConfiguration::WNFListener **a1,
        unsigned int a2)
{
  DeviceConfiguration::WNFListener *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return DeviceConfiguration::WNFListener::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18000b8e0  sub     rsp, 28h
0x18000b8e4  mov     rcx, [rcx]; this
0x18000b8e7  test    rcx, rcx
0x18000b8ea  jz      short loc_18000B8F1
0x18000b8ec  call    ??_GWNFListener@DeviceConfiguration@@QEAAPEAXI@Z; DeviceConfiguration::WNFListener::`scalar deleting destructor'(uint)
0x18000b8f1  add     rsp, 28h
0x18000b8f5  retn
```

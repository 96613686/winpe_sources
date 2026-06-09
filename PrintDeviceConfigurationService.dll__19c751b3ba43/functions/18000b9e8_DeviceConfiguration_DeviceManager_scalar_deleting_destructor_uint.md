# DeviceConfiguration::DeviceManager::`scalar deleting destructor'(uint)

- ea: `0x18000b9e8`
- end: `0x18000ba0c`
- name: `??_GDeviceManager@DeviceConfiguration@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void **__fastcall(void **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000b8c4`
- `0x18000c2a0`

## callees

- `0x180002490`
- `0x18000b908`

## pseudocode

```c
void **__fastcall DeviceConfiguration::DeviceManager::`scalar deleting destructor'(void **this)
{
  std::unique_ptr<DeviceConfiguration::DeviceInstaller>::~unique_ptr<DeviceConfiguration::DeviceInstaller>(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b9e8  push    rbx
0x18000b9ea  sub     rsp, 20h
0x18000b9ee  mov     rbx, rcx
0x18000b9f1  call    ??1?$unique_ptr@VDeviceInstaller@DeviceConfiguration@@U?$default_delete@VDeviceInstaller@DeviceConfiguration@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeviceConfiguration::DeviceInstaller>::~unique_ptr<DeviceConfiguration::DeviceInstaller>(void)
0x18000b9f6  mov     edx, 18h; unsigned __int64
0x18000b9fb  mov     rcx, rbx; void *
0x18000b9fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba03  mov     rax, rbx
0x18000ba06  add     rsp, 20h
0x18000ba0a  pop     rbx
0x18000ba0b  retn
```

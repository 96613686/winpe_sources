# DeviceConfiguration::WNFListener::`scalar deleting destructor'(uint)

- ea: `0x18000ba14`
- end: `0x18000ba38`
- name: `??_GWNFListener@DeviceConfiguration@@QEAAPEAXI@Z`
- size: `36`
- prototype: `DeviceConfiguration::WNFListener *__fastcall(DeviceConfiguration::WNFListener *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000b8e0`
- `0x18000c2c0`

## callees

- `0x180002490`
- `0x18000b968`

## pseudocode

```c
DeviceConfiguration::WNFListener *__fastcall DeviceConfiguration::WNFListener::`scalar deleting destructor'(
        DeviceConfiguration::WNFListener *this)
{
  DeviceConfiguration::WNFListener::~WNFListener(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ba14  push    rbx
0x18000ba16  sub     rsp, 20h
0x18000ba1a  mov     rbx, rcx
0x18000ba1d  call    ??1WNFListener@DeviceConfiguration@@QEAA@XZ; DeviceConfiguration::WNFListener::~WNFListener(void)
0x18000ba22  mov     edx, 60h ; '`'; unsigned __int64
0x18000ba27  mov     rcx, rbx; void *
0x18000ba2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba2f  mov     rax, rbx
0x18000ba32  add     rsp, 20h
0x18000ba36  pop     rbx
0x18000ba37  retn
```

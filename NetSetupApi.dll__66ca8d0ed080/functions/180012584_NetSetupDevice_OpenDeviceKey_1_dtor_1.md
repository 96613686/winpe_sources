# _NetSetupDevice::OpenDeviceKey_::_1_::dtor$1

- ea: `0x180012584`
- end: `0x180012590`
- name: `_NetSetupDevice::OpenDeviceKey_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180005308`

## pseudocode

```c
void __fastcall NetSetupDevice::OpenDeviceKey_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  RegistryKey::~RegistryKey((HKEY *)(a2 + 64));
}

```

## disassembly

```asm
0x180012584  lea     rcx, [rdx+40h]; this
0x18001258b  jmp     ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
```

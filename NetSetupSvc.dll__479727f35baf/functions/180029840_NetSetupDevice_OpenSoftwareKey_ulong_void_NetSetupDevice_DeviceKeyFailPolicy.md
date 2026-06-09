# NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)

- ea: `0x180029840`
- end: `0x180029857`
- name: `?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z`
- size: `23`
- prototype: `RegistryKey *__fastcall(NetSetupDevice *, RegistryKey *, REGSAM, char *)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18001aad4`
- `0x18001ac78`
- `0x18001e828`
- `0x18001eb14`
- `0x18001f2e4`
- `0x18001f984`
- `0x18001fe58`
- `0x180020384`
- `0x180021650`
- `0x1800223a4`
- `0x180023718`

## callees

- `0x1800296fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RegistryKey *__fastcall NetSetupDevice::OpenSoftwareKey(NetSetupDevice *a1, RegistryKey *a2, REGSAM a3, char *a4)
{
  NetSetupDevice::OpenDeviceKey(a1, a2, a3, a4);
  return a2;
}

```

## disassembly

```asm
0x180029840  push    rbx
0x180029842  sub     rsp, 50h
0x180029846  mov     rbx, rdx
0x180029849  call    ?OpenDeviceKey@NetSetupDevice@@AEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@KK@Z; NetSetupDevice::OpenDeviceKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy,ulong,ulong)
0x18002984e  mov     rax, rbx
0x180029851  add     rsp, 50h
0x180029855  pop     rbx
0x180029856  retn
```

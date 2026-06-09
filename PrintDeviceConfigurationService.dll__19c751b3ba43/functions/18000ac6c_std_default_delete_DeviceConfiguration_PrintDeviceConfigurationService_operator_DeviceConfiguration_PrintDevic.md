# std::default_delete<DeviceConfiguration::PrintDeviceConfigurationService>::operator()(DeviceConfiguration::PrintDeviceConfigurationService *)

- ea: `0x18000ac6c`
- end: `0x18000ac94`
- name: `??R?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@QEBAXPEAVPrintDeviceConfigurationService@DeviceConfiguration@@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, DeviceConfiguration::PrintDeviceConfigurationService *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000aab0`
- `0x18000b080`

## callees

- `0x180002490`
- `0x18000ab48`
- `0x18000ac6c`

## pseudocode

```c
void __fastcall std::default_delete<DeviceConfiguration::PrintDeviceConfigurationService>::operator()(
        __int64 a1,
        DeviceConfiguration::PrintDeviceConfigurationService *a2)
{
  if ( a2 )
  {
    DeviceConfiguration::PrintDeviceConfigurationService::~PrintDeviceConfigurationService(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000ac6c  test    rdx, rdx
0x18000ac6f  jz      short locret_18000AC93
0x18000ac71  push    rbx
0x18000ac72  sub     rsp, 20h
0x18000ac76  mov     rcx, rdx; this
0x18000ac79  mov     rbx, rdx
0x18000ac7c  call    ??1PrintDeviceConfigurationService@DeviceConfiguration@@QEAA@XZ; DeviceConfiguration::PrintDeviceConfigurationService::~PrintDeviceConfigurationService(void)
0x18000ac81  mov     edx, 0A8h; unsigned __int64
0x18000ac86  mov     rcx, rbx; void *
0x18000ac89  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac8e  add     rsp, 20h
0x18000ac92  pop     rbx
0x18000ac93  retn
```

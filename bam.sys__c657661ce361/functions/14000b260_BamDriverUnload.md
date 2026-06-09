# BamDriverUnload

- ea: `0x14000b260`
- end: `0x14000b2e9`
- name: `BamDriverUnload`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x140001814`
- `0x14000b260`
- `0x14000b4d4`
- `0x14000c83c`
- `0x14000d00c`
- `0x14000f0c0`

## import_xrefs

- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000b2c9`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14000b2c9`
- `ntoskrnl!ExUnregisterExtension` at `0x14000b270`
- `ntoskrnl!ExUnregisterExtension` at `0x14000b270`
- `ntoskrnl!IoDeleteDevice` at `0x14000b283`
- `ntoskrnl!IoDeleteDevice` at `0x14000b283`

## pseudocode

```c
NTSTATUS BamDriverUnload()
{
  NTSTATUS result; // eax

  if ( BampKernelExtensionRegistration )
    ExUnregisterExtension();
  IoDeleteDevice(BamDeviceObject);
  BamDeviceObject = 0;
  BampThrottlingShutdownModule();
  BamUserSettingsShutdown();
  BamDriverObject = 0;
  TlgUnregisterAggregateProvider();
  result = Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline();
  if ( result && PoPowerSettingCallbackHandle )
    result = PoUnregisterPowerSettingCallback(PoPowerSettingCallbackHandle);
  if ( WilInitialized )
    return wil_UninitializeFeatureStaging();
  return result;
}

```

## disassembly

```asm
0x14000b260  sub     rsp, 28h
0x14000b264  mov     rcx, cs:BampKernelExtensionRegistration
0x14000b26b  test    rcx, rcx
0x14000b26e  jz      short loc_14000B27C
0x14000b270  call    cs:__imp_ExUnregisterExtension
0x14000b277  nop     dword ptr [rax+rax+00h]
0x14000b27c  mov     rcx, cs:BamDeviceObject; DeviceObject
0x14000b283  call    cs:__imp_IoDeleteDevice
0x14000b28a  nop     dword ptr [rax+rax+00h]
0x14000b28f  mov     cs:BamDeviceObject, 0
0x14000b29a  call    BampThrottlingShutdownModule
0x14000b29f  call    BamUserSettingsShutdown
0x14000b2a4  mov     cs:BamDriverObject, 0
0x14000b2af  call    TlgUnregisterAggregateProvider
0x14000b2b4  call    Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline
0x14000b2b9  test    eax, eax
0x14000b2bb  jz      short loc_14000B2D5
0x14000b2bd  mov     rcx, cs:PoPowerSettingCallbackHandle; Handle
0x14000b2c4  test    rcx, rcx
0x14000b2c7  jz      short loc_14000B2D5
0x14000b2c9  call    cs:__imp_PoUnregisterPowerSettingCallback
0x14000b2d0  nop     dword ptr [rax+rax+00h]
0x14000b2d5  cmp     cs:WilInitialized, 0
0x14000b2dc  jz      short loc_14000B2E3
0x14000b2de  call    wil_UninitializeFeatureStaging
0x14000b2e3  add     rsp, 28h
0x14000b2e7  retn
```

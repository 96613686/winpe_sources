# Common::AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>::~AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>(void)

- ea: `0x140008358`
- end: `0x140008360`
- name: `??1?$AutoPtr@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@$1??$AutoPtrDeallocate@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Common@@YAXPEAV1234@@Z@Common@@QEAA@XZ`
- size: `8`
- prototype: `void *__fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper **)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000ed7c`

## callees

- `0x140007e9c`

## pseudocode

```c
void *__fastcall Common::AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&void Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>::~AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&void Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper **a1)
{
  return Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(*a1);
}

```

## disassembly

```asm
0x140008358  mov     rcx, [rcx]
0x14000835b  jmp     ??$AutoPtrDeallocate@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Common@@YAXPEAVCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Z; Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)
```

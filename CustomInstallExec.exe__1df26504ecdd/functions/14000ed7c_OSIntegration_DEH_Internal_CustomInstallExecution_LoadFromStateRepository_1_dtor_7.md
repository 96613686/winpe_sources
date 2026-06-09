# _OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$7

- ea: `0x14000ed7c`
- end: `0x14000ed88`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$7`
- size: `12`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008358`

## pseudocode

```c
void *__fastcall OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor_7(
        __int64 a1,
        __int64 a2)
{
  return Common::AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&void Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>::~AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&void Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>((OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper **)(a2 + 168));
}

```

## disassembly

```asm
0x14000ed7c  lea     rcx, [rdx+0A8h]
0x14000ed83  jmp     ??1?$AutoPtr@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@$1??$AutoPtrDeallocate@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Common@@YAXPEAV1234@@Z@Common@@QEAA@XZ; Common::AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>::~AutoPtr<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,&Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)>(void)
```

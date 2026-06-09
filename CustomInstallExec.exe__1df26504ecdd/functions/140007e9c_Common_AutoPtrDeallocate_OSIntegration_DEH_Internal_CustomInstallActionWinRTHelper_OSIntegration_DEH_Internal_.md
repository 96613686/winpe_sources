# Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)

- ea: `0x140007e9c`
- end: `0x140007eb4`
- name: `??$AutoPtrDeallocate@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Common@@YAXPEAVCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Z`
- size: `24`
- prototype: `void *__fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008358`
- `0x140009cd8`

## callees

- `0x140007e9c`
- `0x1400086ac`

## pseudocode

```c
void *__fastcall Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *a1)
{
  void *result; // rax

  if ( a1 )
    return OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::`scalar deleting destructor'(a1, 1u);
  return result;
}

```

## disassembly

```asm
0x140007e9c  sub     rsp, 28h
0x140007ea0  test    rcx, rcx
0x140007ea3  jz      short loc_140007EAF
0x140007ea5  mov     edx, 1; unsigned int
0x140007eaa  call    ??_GCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAPEAXI@Z; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::`scalar deleting destructor'(uint)
0x140007eaf  add     rsp, 28h
0x140007eb3  retn
```

# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`scalar deleting destructor'(uint)

- ea: `0x1800043a0`
- end: `0x1800043cb`
- name: `??_G?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001644`
- `0x1800043a0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800043a0  push    rbx
0x1800043a2  sub     rsp, 20h
0x1800043a6  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable'
0x1800043ad  mov     rbx, rcx
0x1800043b0  mov     [rcx], rax
0x1800043b3  test    dl, 1
0x1800043b6  jz      short loc_1800043C2
0x1800043b8  mov     edx, 20h ; ' '; unsigned __int64
0x1800043bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800043c2  mov     rax, rbx
0x1800043c5  add     rsp, 20h
0x1800043c9  pop     rbx
0x1800043ca  retn
```

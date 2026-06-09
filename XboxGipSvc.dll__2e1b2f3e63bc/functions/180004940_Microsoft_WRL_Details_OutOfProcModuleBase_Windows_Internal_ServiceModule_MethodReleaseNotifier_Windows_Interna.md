# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`scalar deleting destructor'(uint)

- ea: `0x180004940`
- end: `0x18000496b`
- name: `??_G?$MethodReleaseNotifier@V?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001b6c`
- `0x180004940`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x20);
  return a1;
}

```

## disassembly

```asm
0x180004940  push    rbx
0x180004942  sub     rsp, 20h
0x180004946  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable'
0x18000494d  mov     rbx, rcx
0x180004950  mov     [rcx], rax
0x180004953  test    dl, 1
0x180004956  jz      short loc_180004962
0x180004958  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000495d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004962  mov     rax, rbx
0x180004965  add     rsp, 20h
0x180004969  pop     rbx
0x18000496a  retn
```

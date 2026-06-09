# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___

- ea: `0x180011960`
- end: `0x180011991`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011960`
- `0x180012010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___()
{
  __int64 result; // rax

  if ( byte_18001A5A0 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_)(
               &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_,
               0);
    byte_18001A5A0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011960  sub     rsp, 28h
0x180011964  cmp     cs:byte_18001A5A0, 0
0x18001196b  jz      short loc_18001198C
0x18001196d  mov     rax, cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180011974  lea     rcx, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x18001197b  xor     edx, edx
0x18001197d  mov     rax, [rax]
0x180011980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011985  mov     cs:byte_18001A5A0, 0
0x18001198c  add     rsp, 28h
0x180011990  retn
```

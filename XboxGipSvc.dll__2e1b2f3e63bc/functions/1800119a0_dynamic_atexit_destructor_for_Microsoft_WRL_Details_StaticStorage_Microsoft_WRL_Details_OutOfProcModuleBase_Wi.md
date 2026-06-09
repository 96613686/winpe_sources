# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___

- ea: `0x1800119a0`
- end: `0x1800119d1`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800119a0`
- `0x180012010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___()
{
  __int64 result; // rax

  if ( byte_18001A5D0 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_)(
               &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_,
               0);
    byte_18001A5D0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800119a0  sub     rsp, 28h
0x1800119a4  cmp     cs:byte_18001A5D0, 0
0x1800119ab  jz      short loc_1800119CC
0x1800119ad  mov     rax, cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x1800119b4  lea     rcx, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x1800119bb  xor     edx, edx
0x1800119bd  mov     rax, [rax]
0x1800119c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c5  mov     cs:byte_18001A5D0, 0
0x1800119cc  add     rsp, 28h
0x1800119d0  retn
```

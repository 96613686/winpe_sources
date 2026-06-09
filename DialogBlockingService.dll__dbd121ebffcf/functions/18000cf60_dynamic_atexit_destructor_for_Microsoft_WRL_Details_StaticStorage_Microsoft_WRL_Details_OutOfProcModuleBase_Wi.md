# _dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___

- ea: `0x18000cf60`
- end: `0x18000cf91`
- name: `_dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___`
- size: `49`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cf60`
- `0x18000e010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___()
{
  __int64 result; // rax

  if ( byte_1800144D0 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_)(
               &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_,
               0);
    byte_1800144D0 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000cf60  sub     rsp, 28h
0x18000cf64  cmp     cs:byte_1800144D0, 0
0x18000cf6b  jz      short loc_18000CF8C
0x18000cf6d  mov     rax, cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x18000cf74  lea     rcx, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x18000cf7b  xor     edx, edx
0x18000cf7d  mov     rax, [rax]
0x18000cf80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf85  mov     cs:byte_1800144D0, 0
0x18000cf8c  add     rsp, 28h
0x18000cf90  retn
```

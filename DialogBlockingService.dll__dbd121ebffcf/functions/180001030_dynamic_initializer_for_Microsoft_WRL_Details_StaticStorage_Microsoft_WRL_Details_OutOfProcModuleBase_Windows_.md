# _dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___

- ea: `0x180001030`
- end: `0x18000103c`
- name: `_dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001a20`

## pseudocode

```c
int dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::SvcHostModule_::MethodReleaseNotifier_Windows::Internal::Service_DialogBlockingService_1_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::SvcHostModule_::instance___);
}

```

## disassembly

```asm
0x180001030  lea     rcx, _dynamic_atexit_destructor_for__Microsoft__WRL__Details__StaticStorage_Microsoft__WRL__Details__OutOfProcModuleBase_Windows__Internal__SvcHostModule___MethodReleaseNotifier_Windows__Internal__Service_DialogBlockingService_1_Windows__Internal__ServiceModuleBase__SecurityPolicyEveryoneLocal_2_Windows__Internal__DefaultServerDescriptor____3_Windows__Internal__SvcHostModule___instance___
0x180001037  jmp     atexit
```

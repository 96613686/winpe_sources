# _dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___

- ea: `0x180001070`
- end: `0x18000107c`
- name: `_dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001b4c`

## pseudocode

```c
int dynamic_initializer_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Microsoft::WRL::Details::StaticStorage_Microsoft::WRL::Details::OutOfProcModuleBase_Windows::Internal::ServiceModule_::MethodReleaseNotifier_Windows::Internal::Service_GipMgmtSvc_2_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor____3_Windows::Internal::ServiceModule_::instance___);
}

```

## disassembly

```asm
0x180001070  lea     rcx, _dynamic_atexit_destructor_for__Microsoft__WRL__Details__StaticStorage_Microsoft__WRL__Details__OutOfProcModuleBase_Windows__Internal__ServiceModule___MethodReleaseNotifier_Windows__Internal__Service_GipMgmtSvc_2_Windows__Internal__ServiceModuleBase__SecurityPolicyEveryoneLocal_2_Windows__Internal__DefaultServerDescriptor____3_Windows__Internal__ServiceModule___instance___
0x180001077  jmp     atexit
```

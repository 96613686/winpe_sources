# _Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$1

- ea: `0x1800116df`
- end: `0x1800116eb`
- name: `_Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800023f0`

## pseudocode

```c
void __fastcall Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>((__int64 *)(a2 + 144));
}

```

## disassembly

```asm
0x1800116df  lea     rcx, [rdx+90h]; void *
0x1800116e6  jmp     ??1?$ComPtr@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>(void)
```

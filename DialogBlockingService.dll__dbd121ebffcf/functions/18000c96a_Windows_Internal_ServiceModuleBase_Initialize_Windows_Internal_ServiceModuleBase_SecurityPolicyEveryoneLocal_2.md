# _Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$1

- ea: `0x18000c96a`
- end: `0x18000c976`
- name: `_Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003c3c`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>((_QWORD *)(a2 + 112));
}

```

## disassembly

```asm
0x18000c96a  lea     rcx, [rdx+70h]
0x18000c971  jmp     ??1?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(void)
```

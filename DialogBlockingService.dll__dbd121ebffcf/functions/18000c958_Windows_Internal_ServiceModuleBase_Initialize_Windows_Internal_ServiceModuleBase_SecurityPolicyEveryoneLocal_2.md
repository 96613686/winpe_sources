# _Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$0

- ea: `0x18000c958`
- end: `0x18000c964`
- name: `_Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003e90`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return wil::details::lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>::~lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>(a2 + 64);
}

```

## disassembly

```asm
0x18000c958  lea     rcx, [rdx+40h]
0x18000c95f  jmp     ??1?$lambda_call@V_lambda_0844bed45d04fee2db371e67ed993d11_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>::~lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>(void)
```

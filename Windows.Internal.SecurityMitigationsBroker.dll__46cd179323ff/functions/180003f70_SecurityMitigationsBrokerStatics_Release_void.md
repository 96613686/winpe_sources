# SecurityMitigationsBrokerStatics::Release(void)

- ea: `0x180003f70`
- end: `0x180003f75`
- name: `?Release@SecurityMitigationsBrokerStatics@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(SecurityMitigationsBrokerStatics *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x180003ec0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SecurityMitigationsBrokerStatics::Release(__int64 this, __int64 a2)
{
  return Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
           this,
           a2);
}

```

## disassembly

```asm
0x180003f70  jmp     ?Release@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
```

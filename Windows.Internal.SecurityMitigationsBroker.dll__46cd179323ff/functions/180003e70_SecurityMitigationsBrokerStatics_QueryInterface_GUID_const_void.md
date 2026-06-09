# SecurityMitigationsBrokerStatics::QueryInterface(_GUID const &,void * *)

- ea: `0x180003e70`
- end: `0x180003e75`
- name: `?QueryInterface@SecurityMitigationsBrokerStatics@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(SecurityMitigationsBrokerStatics *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003e80`

## callees

- `0x180003d80`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SecurityMitigationsBrokerStatics::QueryInterface(__int64 this, _DWORD *a2, _QWORD *a3)
{
  return Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x180003e70  jmp     ?QueryInterface@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)
```

# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::QueryInterface(_GUID const &,void * *)

- ea: `0x1800041d0`
- end: `0x1800041d5`
- name: `?QueryInterface@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800041e0`

## callees

- `0x180004010`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::QueryInterface(
        __int64 this,
        _DWORD *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800041d0  jmp     ?QueryInterface@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)
```

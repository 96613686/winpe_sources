# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::QueryInterface(_GUID const &,void * *)

- ea: `0x1800041a0`
- end: `0x1800041a5`
- name: `?QueryInterface@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800041b0`
- `0x1800041c0`

## callees

- `0x180003f50`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::QueryInterface(
        __int64 this,
        _DWORD *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800041a0  jmp     ?QueryInterface@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)
```

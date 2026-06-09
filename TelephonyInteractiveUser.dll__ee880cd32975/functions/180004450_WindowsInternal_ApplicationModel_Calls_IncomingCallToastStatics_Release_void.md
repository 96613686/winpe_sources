# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Release(void)

- ea: `0x180004450`
- end: `0x180004455`
- name: `?Release@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004460`
- `0x180004470`

## callees

- `0x1800042d0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::Release(
        __int64 this,
        __int64 a2)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
           this,
           a2);
}

```

## disassembly

```asm
0x180004450  jmp     ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
```

# [thunk]:Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef`adjustor{16}' (void)

- ea: `0x180003590`
- end: `0x180003599`
- name: `?AddRef@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003520`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(
        __int64 a1)
{
  return WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::AddRef((WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *)(a1 - 16));
}

```

## disassembly

```asm
0x180003590  sub     rcx, 10h; this
0x180003594  jmp     ?AddRef@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAKXZ; WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::AddRef(void)
```

# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIids(ulong *,_GUID * *)

- ea: `0x180003c10`
- end: `0x180003c15`
- name: `?GetIids@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `5`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003c20`

## callees

- `0x180003b00`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::GetIids(
        __int64 this,
        _DWORD *a2,
        GUID **a3)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x180003c10  jmp     ?GetIids@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)
```

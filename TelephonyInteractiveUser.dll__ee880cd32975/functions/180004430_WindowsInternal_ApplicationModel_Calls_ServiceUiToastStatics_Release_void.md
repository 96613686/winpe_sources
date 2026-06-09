# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::Release(void)

- ea: `0x180004430`
- end: `0x180004435`
- name: `?Release@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004440`

## callees

- `0x180004220`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::Release(__int64 this, __int64 a2)
{
  return Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
           this,
           a2);
}

```

## disassembly

```asm
0x180004430  jmp     ?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
```

# Windows::UI::Input::InjectionBrokerImpl::QueryInterface(_GUID const &,void * *)

- ea: `0x180007080`
- end: `0x180007085`
- name: `?QueryInterface@InjectionBrokerImpl@Input@UI@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(__int64 this, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007090`
- `0x1800070a0`

## callees

- `0x180006f10`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::QueryInterface(__int64 this, _DWORD *a2, _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::QueryInterface(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x180007080  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectionBroker@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
```

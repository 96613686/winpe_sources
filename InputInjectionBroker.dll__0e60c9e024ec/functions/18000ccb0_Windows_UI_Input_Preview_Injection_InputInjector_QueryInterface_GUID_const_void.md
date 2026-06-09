# Windows::UI::Input::Preview::Injection::InputInjector::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ccb0`
- end: `0x18000ccb5`
- name: `?QueryInterface@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(__int64 this, _DWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ccc0`
- `0x18000ccd0`
- `0x18000cce0`
- `0x18000ccf0`
- `0x18000cd00`

## callees

- `0x18000cb90`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::QueryInterface(
        __int64 this,
        _DWORD *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::QueryInterface(
           this,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000ccb0  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector2@56789@UIInputInjector3@56789@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
```

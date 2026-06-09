# Windows::UI::Input::Preview::Injection::InputInjector::Release(void)

- ea: `0x18000de60`
- end: `0x18000de65`
- name: `?Release@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAKXZ`
- size: `5`
- prototype: `__int64 __fastcall(volatile signed __int64 *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000de70`
- `0x18000de80`
- `0x18000de90`
- `0x18000dea0`
- `0x18000deb0`

## callees

- `0x18000dd70`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::Release(volatile signed __int64 *this)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::Release(this);
}

```

## disassembly

```asm
0x18000de60  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector2@56789@UIInputInjector3@56789@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::Release(void)
```

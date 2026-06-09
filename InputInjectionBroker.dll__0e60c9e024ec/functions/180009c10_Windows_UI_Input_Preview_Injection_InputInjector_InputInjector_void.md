# Windows::UI::Input::Preview::Injection::InputInjector::~InputInjector(void)

- ea: `0x180009c10`
- end: `0x180009ce3`
- name: `??1InputInjector@Injection@Preview@Input@UI@Windows@@MEAA@XZ`
- size: `211`
- prototype: `void __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009ea0`

## callees

- `0x18000986c`
- `0x180009c10`
- `0x18000e2bc`
- `0x18000e340`
- `0x18000e3d0`
- `0x18000e460`
- `0x180010858`
- `0x180010920`
- `0x180010c80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ccb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ccb`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180009c6a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180009c6a`
- `XboxgipSynthetic!SyntheticController_RemoveController` at `0x180009cbe`
- `XboxgipSynthetic!SyntheticController_RemoveController` at `0x180009cbe`

## pseudocode

```c
void __fastcall Windows::UI::Input::Preview::Injection::InputInjector::~InputInjector(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  struct Windows::UI::Input::Preview::Injection::KeyboardTelemetry *v2; // rdx
  struct Windows::UI::Input::Preview::Injection::MouseTelemetry *v3; // rdx
  struct Windows::UI::Input::Preview::Injection::ShortcutTelemetry *v4; // rdx

  *(_QWORD *)this = &Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjector'};
  *((_QWORD *)this + 1) = &Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjector2'};
  *((_QWORD *)this + 3) = &Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>'};
  *((_QWORD *)this + 5) = &Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( *((_QWORD *)this + 21) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  Windows::UI::Input::Preview::Injection::InputInjector::UninitializeTouchInjection(this);
  Windows::UI::Input::Preview::Injection::InputInjector::UninitializePenInjection(this);
  Windows::UI::Input::Preview::Injection::InputInjector::UninitializeGamepadInjection((Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 16));
  Windows::UI::Input::Preview::Injection::InputInjector::UninitializeButtonInjection(this);
  Windows::UI::Input::Preview::Injection::WriteKeyboardTelemetry(
    (Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 304),
    v2);
  Windows::UI::Input::Preview::Injection::WriteMouseTelemetry(
    (Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 328),
    v3);
  Windows::UI::Input::Preview::Injection::WriteShortcutTelemetry(
    (Windows::UI::Input::Preview::Injection::InputInjector *)((char *)this + 364),
    v4);
  if ( *((_QWORD *)this + 13) )
    SyntheticController_RemoveController();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180009c10  mov     [rsp+arg_0], rbx
0x180009c15  push    rdi
0x180009c16  sub     rsp, 20h
0x180009c1a  lea     rax, ??_7InputInjector@Injection@Preview@Input@UI@Windows@@6BIInputInjector@12345@@; const Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjector'}
0x180009c21  mov     rbx, rcx
0x180009c24  mov     [rcx], rax
0x180009c27  lea     rax, ??_7InputInjector@Injection@Preview@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInputInjector2@Injection@Preview@Input@UI@Windows@@UIInputInjector3@6789Windows@@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>'}
0x180009c2e  mov     [rcx+8], rax
0x180009c32  lea     rax, ??_7InputInjector@Injection@Preview@Input@UI@Windows@@6BIInputInjector2@12345@@; const Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Windows::UI::Input::Preview::Injection::IInputInjector2'}
0x180009c39  mov     [rcx+10h], rax
0x180009c3d  lea     rax, ??_7InputInjector@Injection@Preview@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInputInjector3@Injection@Preview@Input@UI@Windows@@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>'}
0x180009c44  mov     [rcx+18h], rax
0x180009c48  lea     rax, ??_7InputInjector@Injection@Preview@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>'}
0x180009c4f  mov     [rcx+20h], rax
0x180009c53  lea     rax, ??_7InputInjector@Injection@Preview@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::Preview::Injection::InputInjector::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180009c5a  mov     [rcx+28h], rax
0x180009c5e  mov     rcx, [rcx+0A8h]
0x180009c65  test    rcx, rcx
0x180009c68  jz      short loc_180009C70
0x180009c6a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180009c70  mov     rcx, rbx; this
0x180009c73  call    ?UninitializeTouchInjection@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::UninitializeTouchInjection(void)
0x180009c78  mov     rcx, rbx; this
0x180009c7b  call    ?UninitializePenInjection@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::UninitializePenInjection(void)
0x180009c80  lea     rcx, [rbx+10h]; this
0x180009c84  call    ?UninitializeGamepadInjection@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::UninitializeGamepadInjection(void)
0x180009c89  mov     rcx, rbx; this
0x180009c8c  call    ?UninitializeButtonInjection@InputInjector@Injection@Preview@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::UninitializeButtonInjection(void)
0x180009c91  lea     rcx, [rbx+130h]; this
0x180009c98  call    ?WriteKeyboardTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUKeyboardTelemetry@12345@@Z; Windows::UI::Input::Preview::Injection::WriteKeyboardTelemetry(Windows::UI::Input::Preview::Injection::KeyboardTelemetry &)
0x180009c9d  lea     rcx, [rbx+148h]; this
0x180009ca4  call    ?WriteMouseTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUMouseTelemetry@12345@@Z; Windows::UI::Input::Preview::Injection::WriteMouseTelemetry(Windows::UI::Input::Preview::Injection::MouseTelemetry &)
0x180009ca9  lea     rcx, [rbx+16Ch]; this
0x180009cb0  call    ?WriteShortcutTelemetry@Injection@Preview@Input@UI@Windows@@YAXAEAUShortcutTelemetry@12345@@Z; Windows::UI::Input::Preview::Injection::WriteShortcutTelemetry(Windows::UI::Input::Preview::Injection::ShortcutTelemetry &)
0x180009cb5  mov     rcx, [rbx+68h]
0x180009cb9  test    rcx, rcx
0x180009cbc  jz      short loc_180009CC4
0x180009cbe  call    cs:__imp_SyntheticController_RemoveController
0x180009cc4  lea     rcx, [rbx+80h]; lpCriticalSection
0x180009ccb  call    cs:__imp_DeleteCriticalSection
0x180009cd1  mov     rcx, rbx
0x180009cd4  mov     rbx, [rsp+28h+arg_0]
0x180009cd9  add     rsp, 20h
0x180009cdd  pop     rdi
0x180009cde  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector2@56789@UIInputInjector3@56789@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>(void)
```

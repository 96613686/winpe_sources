# Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::~CWindowsTipPresenter(void)

- ea: `0x180330c90`
- end: `0x180330ef4`
- name: `??1CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@UEAA@XZ`
- size: `612`
- prototype: `void(Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ac600`

## callees

- `0x180009dfc`
- `0x18002fe34`
- `0x180037b9c`
- `0x1800f522c`
- `0x1800fd4d8`
- `0x1802215cc`
- `0x180330c90`
- `0x180330f84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330d92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330dec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330ea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330ed1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330d92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330dec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330ea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180330ed1`

## pseudocode

```c
void __fastcall Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::~CWindowsTipPresenter(
        Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *this)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'};
  *((_QWORD *)this + 2) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  *((_QWORD *)this + 3) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'};
  *((_QWORD *)this + 4) = &Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  v2 = Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::CleanupNotification(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x316,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
      (const char *)(unsigned int)v2,
      v3);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 504);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 472);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 464);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 456);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 440);
  Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours::~CreativeVisualDataForGuidedTours((Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *)((char *)this + 320));
  Windows::Internal::UI::WindowsTip::CreativeMetadata::~CreativeMetadata((Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *)((char *)this + 296));
  Windows::Internal::UI::WindowsTip::CWindowsTipNotification::~CWindowsTipNotification((Windows::Internal::UI::WindowsTip::CWindowsTipPresenter *)((char *)this + 240));
  WindowsDeleteString(*((HSTRING *)this + 23));
  *((_QWORD *)this + 23) = 0;
  WindowsDeleteString(*((HSTRING *)this + 22));
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(*((HSTRING *)this + 21));
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 144);
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 11) = -1073741823;
}

```

## disassembly

```asm
0x180330c90  mov     [rsp+arg_0], rbx
0x180330c95  push    rdi; int
0x180330c96  sub     rsp, 20h
0x180330c9a  mov     rbx, rcx
0x180330c9d  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'
0x180330ca4  mov     [rcx], rax
0x180330ca7  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6BIUIAutomationStructureChangedEventHandler@@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'}
0x180330cae  mov     [rcx+8], rax
0x180330cb2  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@56@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@56@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x180330cb9  mov     [rcx+10h], rax
0x180330cbd  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@Foundation@4@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'}
0x180330cc4  mov     [rcx+18h], rax
0x180330cc8  lea     rax, ??_7CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x180330ccf  mov     [rcx+20h], rax
0x180330cd3  call    ?CleanupNotification@CWindowsTipPresenter@WindowsTip@UI@Internal@Windows@@AEAAJXZ; Windows::Internal::UI::WindowsTip::CWindowsTipPresenter::CleanupNotification(void)
0x180330cd8  xor     edi, edi
0x180330cda  test    eax, eax
0x180330cdc  jns     short loc_180330CF7
0x180330cde  mov     rcx, [rsp+28h]; this
0x180330ce3  mov     r9d, eax; char *
0x180330ce6  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180330ced  mov     edx, 316h; void *
0x180330cf2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180330cf7  lea     rcx, [rbx+1F8h]
0x180330cfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180330d03  lea     rcx, [rbx+1D8h]
0x180330d0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180330d0f  lea     rcx, [rbx+1D0h]
0x180330d16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180330d1b  lea     rcx, [rbx+1C8h]
0x180330d22  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180330d27  lea     rcx, [rbx+1B8h]
0x180330d2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180330d33  lea     rcx, [rbx+140h]; this
0x180330d3a  call    ??1CreativeVisualDataForGuidedTours@WindowsTip@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours::~CreativeVisualDataForGuidedTours(void)
0x180330d3f  lea     rcx, [rbx+128h]; this
0x180330d46  call    ??1CreativeMetadata@WindowsTip@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::WindowsTip::CreativeMetadata::~CreativeMetadata(void)
0x180330d4b  lea     rcx, [rbx+0F0h]; this
0x180330d52  call    ??1CWindowsTipNotification@WindowsTip@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::WindowsTip::CWindowsTipNotification::~CWindowsTipNotification(void)
0x180330d57  mov     rcx, [rbx+0B8h]; string
0x180330d5e  call    cs:__imp_WindowsDeleteString
0x180330d65  nop     dword ptr [rax+rax+00h]
0x180330d6a  mov     [rbx+0B8h], rdi
0x180330d71  mov     rcx, [rbx+0B0h]; string
0x180330d78  call    cs:__imp_WindowsDeleteString
0x180330d7f  nop     dword ptr [rax+rax+00h]
0x180330d84  mov     [rbx+0B0h], rdi
0x180330d8b  mov     rcx, [rbx+0A8h]; string
0x180330d92  call    cs:__imp_WindowsDeleteString
0x180330d99  nop     dword ptr [rax+rax+00h]
0x180330d9e  mov     [rbx+0A8h], rdi
0x180330da5  mov     rcx, [rbx+0A0h]; string
0x180330dac  call    cs:__imp_WindowsDeleteString
0x180330db3  nop     dword ptr [rax+rax+00h]
0x180330db8  mov     [rbx+0A0h], rdi
0x180330dbf  mov     rcx, [rbx+98h]; string
0x180330dc6  call    cs:__imp_WindowsDeleteString
0x180330dcd  nop     dword ptr [rax+rax+00h]
0x180330dd2  mov     [rbx+98h], rdi
0x180330dd9  lea     rcx, [rbx+90h]
0x180330de0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180330de5  mov     rcx, [rbx+88h]; string
0x180330dec  call    cs:__imp_WindowsDeleteString
0x180330df3  nop     dword ptr [rax+rax+00h]
0x180330df8  mov     [rbx+88h], rdi
0x180330dff  mov     rcx, [rbx+80h]; string
0x180330e06  call    cs:__imp_WindowsDeleteString
0x180330e0d  nop     dword ptr [rax+rax+00h]
0x180330e12  mov     [rbx+80h], rdi
0x180330e19  mov     rcx, [rbx+78h]; string
0x180330e1d  call    cs:__imp_WindowsDeleteString
0x180330e24  nop     dword ptr [rax+rax+00h]
0x180330e29  mov     [rbx+78h], rdi
0x180330e2d  mov     rcx, [rbx+70h]; string
0x180330e31  call    cs:__imp_WindowsDeleteString
0x180330e38  nop     dword ptr [rax+rax+00h]
0x180330e3d  mov     [rbx+70h], rdi
0x180330e41  mov     rcx, [rbx+68h]; string
0x180330e45  call    cs:__imp_WindowsDeleteString
0x180330e4c  nop     dword ptr [rax+rax+00h]
0x180330e51  mov     [rbx+68h], rdi
0x180330e55  mov     rcx, [rbx+60h]; string
0x180330e59  call    cs:__imp_WindowsDeleteString
0x180330e60  nop     dword ptr [rax+rax+00h]
0x180330e65  mov     [rbx+60h], rdi
0x180330e69  mov     rcx, [rbx+58h]; string
0x180330e6d  call    cs:__imp_WindowsDeleteString
0x180330e74  nop     dword ptr [rax+rax+00h]
0x180330e79  mov     [rbx+58h], rdi
0x180330e7d  mov     rcx, [rbx+50h]; string
0x180330e81  call    cs:__imp_WindowsDeleteString
0x180330e88  nop     dword ptr [rax+rax+00h]
0x180330e8d  mov     [rbx+50h], rdi
0x180330e91  mov     rcx, [rbx+48h]; string
0x180330e95  call    cs:__imp_WindowsDeleteString
0x180330e9c  nop     dword ptr [rax+rax+00h]
0x180330ea1  mov     [rbx+48h], rdi
0x180330ea5  mov     rcx, [rbx+40h]; string
0x180330ea9  call    cs:__imp_WindowsDeleteString
0x180330eb0  nop     dword ptr [rax+rax+00h]
0x180330eb5  mov     [rbx+40h], rdi
0x180330eb9  mov     rcx, [rbx+38h]; string
0x180330ebd  call    cs:__imp_WindowsDeleteString
0x180330ec4  nop     dword ptr [rax+rax+00h]
0x180330ec9  mov     [rbx+38h], rdi
0x180330ecd  mov     rcx, [rbx+30h]; string
0x180330ed1  call    cs:__imp_WindowsDeleteString
0x180330ed8  nop     dword ptr [rax+rax+00h]
0x180330edd  mov     [rbx+30h], rdi
0x180330ee1  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180330ee8  mov     rbx, [rsp+28h+arg_0]
0x180330eed  add     rsp, 20h
0x180330ef1  pop     rdi
0x180330ef2  retn
```

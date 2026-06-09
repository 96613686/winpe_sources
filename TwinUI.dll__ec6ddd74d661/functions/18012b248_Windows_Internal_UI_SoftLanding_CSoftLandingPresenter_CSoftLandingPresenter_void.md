# Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::~CSoftLandingPresenter(void)

- ea: `0x18012b248`
- end: `0x18012b3ef`
- name: `??1CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@UEAA@XZ`
- size: `423`
- prototype: `void(Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18033d3c0`

## callees

- `0x180009dfc`
- `0x18002fe34`
- `0x180037b9c`
- `0x18012b248`
- `0x18012b3f8`
- `0x18012b56c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b325`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b33d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b36d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b39d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b3b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b3cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b325`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b33d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b36d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b39d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b3b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012b3cd`

## pseudocode

```c
void __fastcall Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::~CSoftLandingPresenter(
        Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *this)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'};
  *((_QWORD *)this + 2) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  *((_QWORD *)this + 3) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'};
  *((_QWORD *)this + 4) = &Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'};
  v2 = Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::_CleanupNotification(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingpresenter.cpp",
      (const char *)(unsigned int)v2,
      v3);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 376);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 344);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 336);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 328);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 312);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 272);
  Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification((Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *)((char *)this + 208));
  Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification((Windows::Internal::UI::SoftLanding::CSoftLandingPresenter *)((char *)this + 152));
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
0x18012b248  push    rbx; int
0x18012b24a  sub     rsp, 20h
0x18012b24e  mov     rbx, rcx
0x18012b251  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'
0x18012b258  mov     [rcx], rax
0x18012b25b  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6BIUIAutomationStructureChangedEventHandler@@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `IUIAutomationStructureChangedEventHandler'}
0x18012b262  mov     [rcx+8], rax
0x18012b266  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@56@U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@56@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,IInspectable *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x18012b26d  mov     [rcx+10h], rax
0x18012b271  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastDismissedEventArgs@234@@Foundation@4@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>'}
0x18012b278  mov     [rcx+18h], rax
0x18012b27c  lea     rax, ??_7CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>>'}
0x18012b283  mov     [rcx+20h], rax
0x18012b287  call    ?_CleanupNotification@CSoftLandingPresenter@SoftLanding@UI@Internal@Windows@@AEAAJXZ; Windows::Internal::UI::SoftLanding::CSoftLandingPresenter::_CleanupNotification(void)
0x18012b28c  test    eax, eax
0x18012b28e  jns     short loc_18012B2A9
0x18012b290  mov     rcx, [rsp+28h]; this
0x18012b295  mov     r9d, eax; char *
0x18012b298  lea     r8, aShellTwinuiSof_3; "shell\\twinui\\softlanding\\lib\\softla"...
0x18012b29f  mov     edx, 1D3h; void *
0x18012b2a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18012b2a9  lea     rcx, [rbx+178h]
0x18012b2b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18012b2b5  lea     rcx, [rbx+158h]
0x18012b2bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012b2c1  lea     rcx, [rbx+150h]
0x18012b2c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012b2cd  lea     rcx, [rbx+148h]
0x18012b2d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012b2d9  lea     rcx, [rbx+138h]
0x18012b2e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012b2e5  lea     rcx, [rbx+110h]
0x18012b2ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012b2f1  lea     rcx, [rbx+0D0h]; this
0x18012b2f8  call    ??1CSoftLandingNotification@SoftLanding@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification(void)
0x18012b2fd  lea     rcx, [rbx+98h]; this
0x18012b304  call    ??1CSoftLandingNotification@SoftLanding@UI@Internal@Windows@@QEAA@XZ; Windows::Internal::UI::SoftLanding::CSoftLandingNotification::~CSoftLandingNotification(void)
0x18012b309  mov     rcx, [rbx+70h]; string
0x18012b30d  call    cs:__imp_WindowsDeleteString
0x18012b314  nop     dword ptr [rax+rax+00h]
0x18012b319  mov     qword ptr [rbx+70h], 0
0x18012b321  mov     rcx, [rbx+68h]; string
0x18012b325  call    cs:__imp_WindowsDeleteString
0x18012b32c  nop     dword ptr [rax+rax+00h]
0x18012b331  mov     qword ptr [rbx+68h], 0
0x18012b339  mov     rcx, [rbx+60h]; string
0x18012b33d  call    cs:__imp_WindowsDeleteString
0x18012b344  nop     dword ptr [rax+rax+00h]
0x18012b349  mov     qword ptr [rbx+60h], 0
0x18012b351  mov     rcx, [rbx+58h]; string
0x18012b355  call    cs:__imp_WindowsDeleteString
0x18012b35c  nop     dword ptr [rax+rax+00h]
0x18012b361  mov     qword ptr [rbx+58h], 0
0x18012b369  mov     rcx, [rbx+50h]; string
0x18012b36d  call    cs:__imp_WindowsDeleteString
0x18012b374  nop     dword ptr [rax+rax+00h]
0x18012b379  mov     qword ptr [rbx+50h], 0
0x18012b381  mov     rcx, [rbx+48h]; string
0x18012b385  call    cs:__imp_WindowsDeleteString
0x18012b38c  nop     dword ptr [rax+rax+00h]
0x18012b391  mov     qword ptr [rbx+48h], 0
0x18012b399  mov     rcx, [rbx+40h]; string
0x18012b39d  call    cs:__imp_WindowsDeleteString
0x18012b3a4  nop     dword ptr [rax+rax+00h]
0x18012b3a9  mov     qword ptr [rbx+40h], 0
0x18012b3b1  mov     rcx, [rbx+38h]; string
0x18012b3b5  call    cs:__imp_WindowsDeleteString
0x18012b3bc  nop     dword ptr [rax+rax+00h]
0x18012b3c1  mov     qword ptr [rbx+38h], 0
0x18012b3c9  mov     rcx, [rbx+30h]; string
0x18012b3cd  call    cs:__imp_WindowsDeleteString
0x18012b3d4  nop     dword ptr [rax+rax+00h]
0x18012b3d9  mov     qword ptr [rbx+30h], 0
0x18012b3e1  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18012b3e8  add     rsp, 20h
0x18012b3ec  pop     rbx
0x18012b3ed  retn
```

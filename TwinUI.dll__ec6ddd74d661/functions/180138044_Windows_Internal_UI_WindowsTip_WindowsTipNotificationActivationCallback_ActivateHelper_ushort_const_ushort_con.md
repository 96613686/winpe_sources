# Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::ActivateHelper(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180138044`
- end: `0x1801382b5`
- name: `?ActivateHelper@WindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@AEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `625`
- prototype: `int(Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180138010`

## callees

- `0x180031d80`
- `0x1800378dc`
- `0x1800fdcec`
- `0x18010ac4c`
- `0x180138044`
- `0x180142e10`
- `0x18018261c`
- `0x1802282c4`
- `0x18031c680`
- `0x18031cdd8`
- `0x18031cfc8`
- `0x18031d11c`
- `0x18031d658`
- `0x18031d818`
- `0x18032c954`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801380dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801380f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013827d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801380dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801380f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138267`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013827d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013818f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013818f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18013807f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18013807f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::ActivateHelper(
        Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *v7; // rcx
  int ContentIdAndPath; // eax
  int v9; // ebx
  Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *v10; // rcx
  int CreativeId; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  HSTRING v17; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+40h] [rbp-C0h]
  HSTRING v20; // [rsp+48h] [rbp-B8h] BYREF
  char v21; // [rsp+50h] [rbp-B0h]
  Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback *v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[384]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  if ( StrCmpIW(a2, L"Windows.SystemToast.WindowsTip") || !a3 || !*a3 )
    return 2147942487LL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl'::`2'::impl) )
  {
    Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::ProcessActivationAsync(a3);
    return 0;
  }
  else
  {
    v19 = 0;
    v21 = 0;
    WindowsDeleteString(0);
    v20 = 0;
    WindowsDeleteString(0);
    string = 0;
    ContentIdAndPath = Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetContentIdAndPath(
                         v7,
                         a3,
                         &string,
                         &v20);
    v9 = ContentIdAndPath;
    if ( ContentIdAndPath >= 0 )
    {
      WindowsDeleteString(0);
      v17 = 0;
      CreativeId = Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetCreativeId(
                     v10,
                     string,
                     &v17);
      v9 = CreativeId;
      if ( CreativeId >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v17, 0);
        wil::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v23);
        *(_QWORD *)v23 = &SoftLandingTelemetry::NotificationInvoke::`vftable';
        SoftLandingTelemetry::NotificationInvoke::StartActivity(
          (SoftLandingTelemetry::NotificationInvoke *)v23,
          StringRawBuffer,
          1);
        v22 = this;
        Microsoft::WRL::ComPtr<CExtensionListContextMenu>::InternalAddRef(&v22);
        v13 = _lambda_6852bcebcf55780741477f5ab9ed6c4e_::_lambda_6852bcebcf55780741477f5ab9ed6c4e_(
                (unsigned int)v24,
                (unsigned int)&string,
                (unsigned int)&v20,
                (unsigned int)&v22,
                (__int64)v23);
        v9 = Windows::Internal::ComTaskPool::QueueTask<_lambda_6852bcebcf55780741477f5ab9ed6c4e_>(v14, v13);
        _lambda_6852bcebcf55780741477f5ab9ed6c4e_::~_lambda_6852bcebcf55780741477f5ab9ed6c4e_((_lambda_6852bcebcf55780741477f5ab9ed6c4e_ *)v24);
        if ( v9 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7D,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstipnotificationactivationcallback.cpp",
            (const char *)(unsigned int)v9,
            v16);
        if ( this )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehaviorFactory>::Release(this);
        SoftLandingTelemetry::NotificationInvoke::~NotificationInvoke((SoftLandingTelemetry::NotificationInvoke *)v23);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstipnotificationactivationcallback.cpp",
          (const char *)(unsigned int)CreativeId,
          v15);
      }
      WindowsDeleteString(v17);
      v17 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstipnotificationactivationcallback.cpp",
        (const char *)(unsigned int)ContentIdAndPath,
        v15);
    }
    WindowsDeleteString(v20);
    v20 = 0;
    WindowsDeleteString(string);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180138044  mov     [rsp-8+arg_18], rbx
0x180138049  push    rbp
0x18013804a  push    rsi
0x18013804b  push    rdi
0x18013804c  lea     rbp, [rsp-240h]
0x180138054  sub     rsp, 340h
0x18013805b  mov     rax, cs:__security_cookie
0x180138062  xor     rax, rsp
0x180138065  mov     [rbp+250h+var_20], rax
0x18013806c  mov     rbx, r8
0x18013806f  mov     rax, rdx
0x180138072  mov     rdi, rcx
0x180138075  lea     rdx, ?c_windowsTipAppIdentity@Shared@CreativeFramework@@3QBGB; "Windows.SystemToast.WindowsTip"
0x18013807c  mov     rcx, rax; psz1
0x18013807f  call    cs:__imp_StrCmpIW
0x180138086  nop     dword ptr [rax+rax+00h]
0x18013808b  xor     esi, esi
0x18013808d  test    eax, eax
0x18013808f  jnz     loc_18013828D
0x180138095  test    rbx, rbx
0x180138098  jz      loc_18013828D
0x18013809e  cmp     [rbx], si
0x1801380a1  jz      loc_18013828D
0x1801380a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SoftLandingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2> `wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl(void)'::`2'::impl
0x1801380ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(void)
0x1801380b3  test    al, al
0x1801380b5  jz      short loc_1801380C6
0x1801380b7  mov     rcx, rbx
0x1801380ba  call    ?ProcessActivationAsync@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUfire_and_forget@winrt@@PEBG@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::ProcessActivationAsync(ushort const *)
0x1801380bf  xor     eax, eax
0x1801380c1  jmp     loc_180138292
0x1801380c6  mov     [rsp+350h+string], rsi
0x1801380cb  mov     [rsp+350h+var_310], sil
0x1801380d0  mov     [rsp+350h+var_308], rsi
0x1801380d5  mov     [rsp+350h+var_300], sil
0x1801380da  xor     ecx, ecx; string
0x1801380dc  call    cs:__imp_WindowsDeleteString
0x1801380e3  nop     dword ptr [rax+rax+00h]
0x1801380e8  mov     [rsp+350h+var_308], rsi
0x1801380ed  mov     rcx, [rsp+350h+string]; string
0x1801380f2  call    cs:__imp_WindowsDeleteString
0x1801380f9  nop     dword ptr [rax+rax+00h]
0x1801380fe  mov     [rsp+350h+string], rsi
0x180138103  lea     r9, [rsp+350h+var_308]; HSTRING *
0x180138108  lea     r8, [rsp+350h+string]; HSTRING *
0x18013810d  mov     rdx, rbx; unsigned __int16 *
0x180138110  call    ?GetContentIdAndPath@WindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@AEAAJPEBGPEAPEAUHSTRING__@@1@Z; Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetContentIdAndPath(ushort const *,HSTRING__ * *,HSTRING__ * *)
0x180138115  mov     ebx, eax
0x180138117  test    eax, eax
0x180138119  jns     short loc_18013813B
0x18013811b  mov     rcx, [rbp+258h]; this
0x180138122  mov     r9d, eax; char *
0x180138125  lea     r8, aShellTwinuiSof_1; "shell\\twinui\\softlanding\\lib\\window"...
0x18013812c  mov     edx, 6Eh ; 'n'; void *
0x180138131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138136  jmp     loc_180138262
0x18013813b  mov     [rsp+350h+var_320], rsi
0x180138140  xor     ecx, ecx; string
0x180138142  call    cs:__imp_WindowsDeleteString
0x180138149  nop     dword ptr [rax+rax+00h]
0x18013814e  mov     [rsp+350h+var_320], rsi
0x180138153  lea     r8, [rsp+350h+var_320]; HSTRING *
0x180138158  mov     rdx, [rsp+350h+string]; HSTRING
0x18013815d  call    ?GetCreativeId@WindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAPEAU6@@Z; Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback::GetCreativeId(HSTRING__ *,HSTRING__ * *)
0x180138162  mov     ebx, eax
0x180138164  test    eax, eax
0x180138166  jns     short loc_180138188
0x180138168  mov     rcx, [rbp+258h]; this
0x18013816f  mov     r9d, eax; char *
0x180138172  lea     r8, aShellTwinuiSof_1; "shell\\twinui\\softlanding\\lib\\window"...
0x180138179  mov     edx, 71h ; 'q'; void *
0x18013817e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138183  jmp     loc_18013824C
0x180138188  xor     edx, edx; length
0x18013818a  mov     rcx, [rsp+350h+var_320]; string
0x18013818f  call    cs:__imp_WindowsGetStringRawBuffer
0x180138196  nop     dword ptr [rax+rax+00h]
0x18013819b  mov     rbx, rax
0x18013819e  lea     rdx, aNotificationin; "NotificationInvoke"
0x1801381a5  lea     rcx, [rsp+350h+var_2F0]; struct wil::details::IFailureCallback *
0x1801381aa  call    ??0?$ActivityBase@VSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801381af  lea     rax, ??_7NotificationInvoke@SoftLandingTelemetry@@6B@; const SoftLandingTelemetry::NotificationInvoke::`vftable'
0x1801381b6  mov     qword ptr [rsp+350h+var_2F0], rax
0x1801381bb  mov     r8b, 1; bool
0x1801381be  mov     rdx, rbx; unsigned __int16 *
0x1801381c1  lea     rcx, [rsp+350h+var_2F0]; this
0x1801381c6  call    ?StartActivity@NotificationInvoke@SoftLandingTelemetry@@QEAAXPEBG_N@Z; SoftLandingTelemetry::NotificationInvoke::StartActivity(ushort const *,bool)
0x1801381cb  nop
0x1801381cc  mov     [rsp+350h+var_2F8], rdi
0x1801381d1  lea     rcx, [rsp+350h+var_2F8]
0x1801381d6  call    ?InternalAddRef@?$ComPtr@VCExtensionListContextMenu@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CExtensionListContextMenu>::InternalAddRef(void)
0x1801381db  lea     rax, [rsp+350h+var_2F0]
0x1801381e0  mov     qword ptr [rsp+350h+var_330], rax; int
0x1801381e5  lea     r9, [rsp+350h+var_2F8]
0x1801381ea  lea     r8, [rsp+350h+var_308]
0x1801381ef  lea     rdx, [rsp+350h+string]
0x1801381f4  lea     rcx, [rbp+250h+var_1A0]
0x1801381fb  call    ??0_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@QEAA@AEBV?$MoveOnCopy@VHString@Wrappers@WRL@Microsoft@@@Internal@Windows@@0AEBV?$ComPtr@VWindowsTipNotificationActivationCallback@WindowsTip@UI@Internal@Windows@@@WRL@Microsoft@@AEBVNotificationInvoke@SoftLandingTelemetry@@@Z; _lambda_6852bcebcf55780741477f5ab9ed6c4e_::_lambda_6852bcebcf55780741477f5ab9ed6c4e_(Windows::Internal::MoveOnCopy<Microsoft::WRL::Wrappers::HString> const &,Windows::Internal::MoveOnCopy<Microsoft::WRL::Wrappers::HString> const &,Microsoft::WRL::ComPtr<Windows::Internal::UI::WindowsTip::WindowsTipNotificationActivationCallback> const &,SoftLandingTelemetry::NotificationInvoke const &)
0x180138200  mov     rdx, rax
0x180138203  call    ??$QueueTask@V_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_6852bcebcf55780741477f5ab9ed6c4e_>(Windows::Internal::TaskApartment,_lambda_6852bcebcf55780741477f5ab9ed6c4e_ &&)
0x180138208  mov     ebx, eax
0x18013820a  lea     rcx, [rbp+250h+var_1A0]; this
0x180138211  call    ??1_lambda_6852bcebcf55780741477f5ab9ed6c4e_@@QEAA@XZ; _lambda_6852bcebcf55780741477f5ab9ed6c4e_::~_lambda_6852bcebcf55780741477f5ab9ed6c4e_(void)
0x180138216  test    ebx, ebx
0x180138218  jns     short loc_180138235
0x18013821a  mov     rcx, [rbp+258h]; this
0x180138221  mov     r9d, ebx; char *
0x180138224  lea     r8, aShellTwinuiSof_1; "shell\\twinui\\softlanding\\lib\\window"...
0x18013822b  mov     edx, 7Dh ; '}'; void *
0x180138230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138235  test    rdi, rdi
0x180138238  jz      short loc_180138242
0x18013823a  mov     rcx, rdi
0x18013823d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDuiBehaviorFactory@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehaviorFactory>::Release(void)
0x180138242  lea     rcx, [rsp+350h+var_2F0]; this
0x180138247  call    ??1NotificationInvoke@SoftLandingTelemetry@@QEAA@XZ; SoftLandingTelemetry::NotificationInvoke::~NotificationInvoke(void)
0x18013824c  mov     rcx, [rsp+350h+var_320]; string
0x180138251  call    cs:__imp_WindowsDeleteString
0x180138258  nop     dword ptr [rax+rax+00h]
0x18013825d  mov     [rsp+350h+var_320], rsi
0x180138262  mov     rcx, [rsp+350h+var_308]; string
0x180138267  call    cs:__imp_WindowsDeleteString
0x18013826e  nop     dword ptr [rax+rax+00h]
0x180138273  mov     [rsp+350h+var_308], rsi
0x180138278  mov     rcx, [rsp+350h+string]; string
0x18013827d  call    cs:__imp_WindowsDeleteString
0x180138284  nop     dword ptr [rax+rax+00h]
0x180138289  mov     eax, ebx
0x18013828b  jmp     short loc_180138292
0x18013828d  mov     eax, 80070057h
0x180138292  mov     rcx, [rbp+250h+var_20]
0x180138299  xor     rcx, rsp; StackCookie
0x18013829c  call    __security_check_cookie
0x1801382a1  mov     rbx, [rsp+350h+arg_18]
0x1801382a9  add     rsp, 340h
0x1801382b0  pop     rdi
0x1801382b1  pop     rsi
0x1801382b2  pop     rbp
0x1801382b3  retn
```

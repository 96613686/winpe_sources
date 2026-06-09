# NLInternal::CToastNotifierCallback::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x140012980`
- end: `0x140012caa`
- name: `?Activate@CToastNotifierCallback@NLInternal@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `810`
- prototype: `__int64 __fastcall(NLInternal::CToastNotifierCallback *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002d30`
- `0x140004dbc`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x140012724`
- `0x1400128b8`
- `0x14001296c`
- `0x140012980`
- `0x140012dfc`
- `0x140013588`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012a69`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012a69`

## string_xrefs

- `0x140012a3e`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NLInternal::CToastNotifierCallback::Activate(
        NLInternal::CToastNotifierCallback *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  int v4; // r8d
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rdi
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, __int64 *); // rbx
  int v19; // eax
  int v21; // [rsp+20h] [rbp-51h] BYREF
  __int64 v22; // [rsp+28h] [rbp-49h] BYREF
  __int64 v23; // [rsp+30h] [rbp-41h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-39h] BYREF
  __int64 v25; // [rsp+40h] [rbp-31h] BYREF
  __int64 v26; // [rsp+48h] [rbp-29h] BYREF
  const unsigned __int16 *v27; // [rsp+50h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-19h] BYREF
  __int64 v29; // [rsp+70h] [rbp-1h]
  _BYTE v30[16]; // [rsp+78h] [rbp+7h] BYREF
  __int64 v31; // [rsp+88h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v27 = a3;
  std::wstring::wstring(v30, a3);
  if ( std::wstring::rfind(v30) && v31 )
  {
    LODWORD(v22) = 0;
    if ( (*(int (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)g_cpOrchestratorPolicy + 32LL))(
           g_cpOrchestratorPolicy,
           L"ToastDismissCount",
           &v22) < 0 )
    {
      v4 = 0;
    }
    else
    {
      v4 = v22;
      if ( (unsigned int)v22 >= 2 )
      {
        LOBYTE(v21) = 0;
        SpeechPlatform::Settings::Set<SpeechPlatform::Settings::OnlineSpeechLogging::LoggingAllowed>(&v21);
LABEL_27:
        v7 = 0;
        goto LABEL_28;
      }
    }
    (*(void (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(*(_QWORD *)g_cpOrchestratorPolicy + 48LL))(
      g_cpOrchestratorPolicy,
      L"ToastDismissCount",
      (unsigned int)(v4 + 1));
    goto LABEL_27;
  }
  v25 = 0;
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v5 = v29;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v25);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v22 = 0;
    v8 = v25;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 48LL);
    if ( v31 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
      v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v27);
      v10 = v9(v8, *(_QWORD *)(v12 + 24), &v22);
      v7 = v10;
      if ( v10 < 0 )
      {
        v11 = 57;
        goto LABEL_13;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
      v29 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"ms-settings:privacy-speech",
        0x1Bu,
        0x1Au);
      v10 = v9(v8, v29, &v22);
      v7 = v10;
      if ( v10 < 0 )
      {
        v11 = 51;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\toastnotifier.cpp",
          (const char *)(unsigned int)v10,
          v21);
LABEL_24:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
        goto LABEL_25;
      }
    }
    v24 = 0;
    v29 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Launcher",
      0x18u,
      0x17u);
    v13 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(v29, &v24);
    v7 = v13;
    if ( v13 >= 0 )
    {
      v23 = 0;
      v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
      v15 = **v24;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
      v16 = v15(v14, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v23);
      v7 = v16;
      if ( v16 >= 0 )
      {
        v26 = 0;
        v17 = v23;
        v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v23 + 64LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
        v19 = v18(v17, v22, &v26);
        v7 = v19;
        if ( v19 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
          goto LABEL_27;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\toastnotifier.cpp",
          (const char *)(unsigned int)v19,
          v21);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\toastnotifier.cpp",
          (const char *)(unsigned int)v16,
          v21);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\toastnotifier.cpp",
        (const char *)(unsigned int)v13,
        v21);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\toastnotifier.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v21);
LABEL_25:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
LABEL_28:
  std::wstring::~wstring(v30);
  return v7;
}

```

## disassembly

```asm
0x140012980  push    rbp
0x140012982  push    rbx
0x140012983  push    rsi
0x140012984  push    rdi
0x140012985  lea     rbp, [rsp-37h]
0x14001298a  sub     rsp, 0A8h
0x140012991  mov     rax, cs:__security_cookie
0x140012998  xor     rax, rsp
0x14001299b  mov     [rbp+4Fh+var_28], rax
0x14001299f  mov     [rbp+4Fh+var_70], r8
0x1400129a3  mov     rdx, r8
0x1400129a6  lea     rcx, [rbp+4Fh+var_48]
0x1400129aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400129af  nop
0x1400129b0  lea     rcx, [rbp+4Fh+var_48]
0x1400129b4  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::rfind(ushort const * const,unsigned __int64)
0x1400129b9  xor     esi, esi
0x1400129bb  test    rax, rax
0x1400129be  jz      short loc_140012A2C
0x1400129c0  cmp     [rbp+4Fh+var_38], rsi
0x1400129c4  jz      short loc_140012A2C
0x1400129c6  mov     dword ptr [rbp+4Fh+var_98], esi
0x1400129c9  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x1400129d0  mov     rax, [rcx]
0x1400129d3  lea     r8, [rbp+4Fh+var_98]
0x1400129d7  lea     rdx, aToastdismissco; "ToastDismissCount"
0x1400129de  mov     rax, [rax+20h]
0x1400129e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129e7  test    eax, eax
0x1400129e9  js      short loc_140012A07
0x1400129eb  mov     r8d, dword ptr [rbp+4Fh+var_98]
0x1400129ef  cmp     r8d, 2
0x1400129f3  jb      short loc_140012A0A
0x1400129f5  mov     byte ptr [rbp+4Fh+var_A0], sil
0x1400129f9  lea     rcx, [rbp+4Fh+var_A0]
0x1400129fd  call    ??$Set@ULoggingAllowed@OnlineSpeechLogging@Settings@SpeechPlatform@@@Settings@SpeechPlatform@@YAJAEB_N@Z; SpeechPlatform::Settings::Set<SpeechPlatform::Settings::OnlineSpeechLogging::LoggingAllowed>(bool const &)
0x140012a02  jmp     loc_140012C85
0x140012a07  mov     r8d, esi
0x140012a0a  mov     rcx, cs:?g_cpOrchestratorPolicy@@3V?$CComPtr@UISpAudioOrchestratorPolicy@@@ATL@@A; ATL::CComPtr<ISpAudioOrchestratorPolicy> g_cpOrchestratorPolicy
0x140012a11  mov     rax, [rcx]
0x140012a14  inc     r8d
0x140012a17  lea     rdx, aToastdismissco; "ToastDismissCount"
0x140012a1e  mov     rax, [rax+30h]
0x140012a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a27  jmp     loc_140012C85
0x140012a2c  mov     [rbp+4Fh+var_80], rsi
0x140012a30  mov     [rbp+4Fh+var_50], rsi
0x140012a34  mov     r9d, 16h; unsigned int
0x140012a3a  lea     r8d, [r9+1]; unsigned int
0x140012a3e  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x140012a45  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x140012a49  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140012a4e  mov     rbx, [rbp+4Fh+var_50]
0x140012a52  lea     rcx, [rbp+4Fh+var_80]
0x140012a56  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012a5b  lea     r8, [rbp+4Fh+var_80]
0x140012a5f  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x140012a66  mov     rcx, rbx
0x140012a69  call    cs:__imp_RoGetActivationFactory
0x140012a6f  mov     ebx, eax
0x140012a71  test    eax, eax
0x140012a73  jns     short loc_140012A92
0x140012a75  mov     rcx, [rbp+57h]; this
0x140012a79  mov     r9d, eax; char *
0x140012a7c  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140012a83  mov     edx, 2Ch ; ','; void *
0x140012a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012a8d  jmp     loc_140012C49
0x140012a92  mov     [rbp+4Fh+var_98], rsi
0x140012a96  mov     rdi, [rbp+4Fh+var_80]
0x140012a9a  lea     rcx, [rbp+4Fh+var_98]
0x140012a9e  mov     rax, [rdi]
0x140012aa1  mov     rbx, [rax+30h]
0x140012aa5  cmp     [rbp+4Fh+var_38], rsi
0x140012aa9  jnz     short loc_140012B05
0x140012aab  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012ab0  mov     [rbp+4Fh+var_50], rsi
0x140012ab4  mov     r9d, 1Ah; unsigned int
0x140012aba  lea     r8d, [r9+1]; unsigned int
0x140012abe  lea     rdx, sourceString; "ms-settings:privacy-speech"
0x140012ac5  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x140012ac9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140012ace  nop
0x140012acf  lea     r8, [rbp+4Fh+var_98]
0x140012ad3  mov     rdx, [rbp+4Fh+var_50]
0x140012ad7  mov     rcx, rdi
0x140012ada  mov     rax, rbx
0x140012add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ae2  mov     ebx, eax
0x140012ae4  test    eax, eax
0x140012ae6  jns     short loc_140012B38
0x140012ae8  mov     edx, 33h ; '3'; void *
0x140012aed  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140012af4  mov     r9d, eax; char *
0x140012af7  mov     rcx, [rbp+57h]; this
0x140012afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012b00  jmp     loc_140012C3F
0x140012b05  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012b0a  lea     rdx, [rbp+4Fh+var_70]
0x140012b0e  lea     rcx, [rbp+4Fh+hstringHeader]
0x140012b12  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140012b17  nop
0x140012b18  lea     r8, [rbp+4Fh+var_98]
0x140012b1c  mov     rdx, [rax+18h]
0x140012b20  mov     rcx, rdi
0x140012b23  mov     rax, rbx
0x140012b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b2b  mov     ebx, eax
0x140012b2d  test    eax, eax
0x140012b2f  jns     short loc_140012B38
0x140012b31  mov     edx, 39h ; '9'
0x140012b36  jmp     short loc_140012AED
0x140012b38  mov     [rbp+4Fh+var_88], rsi
0x140012b3c  mov     [rbp+4Fh+var_50], rsi
0x140012b40  mov     r9d, 17h; unsigned int
0x140012b46  lea     r8d, [r9+1]; unsigned int
0x140012b4a  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x140012b51  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x140012b55  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140012b5a  lea     rdx, [rbp+4Fh+var_88]
0x140012b5e  mov     rcx, [rbp+4Fh+var_50]
0x140012b62  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x140012b67  mov     ebx, eax
0x140012b69  test    eax, eax
0x140012b6b  jns     short loc_140012B8A
0x140012b6d  mov     rcx, [rbp+57h]; this
0x140012b71  mov     r9d, eax; char *
0x140012b74  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140012b7b  mov     edx, 3Eh ; '>'; void *
0x140012b80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012b85  jmp     loc_140012C35
0x140012b8a  mov     [rbp+4Fh+var_90], rsi
0x140012b8e  mov     rbx, [rbp+4Fh+var_88]
0x140012b92  mov     rax, [rbx]
0x140012b95  mov     rdi, [rax]
0x140012b98  lea     rcx, [rbp+4Fh+var_90]
0x140012b9c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012ba1  lea     r8, [rbp+4Fh+var_90]
0x140012ba5  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x140012bac  mov     rcx, rbx
0x140012baf  mov     rax, rdi
0x140012bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bb7  mov     ebx, eax
0x140012bb9  test    eax, eax
0x140012bbb  jns     short loc_140012BD7
0x140012bbd  mov     rcx, [rbp+57h]; this
0x140012bc1  mov     r9d, eax; char *
0x140012bc4  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140012bcb  mov     edx, 41h ; 'A'; void *
0x140012bd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012bd5  jmp     short loc_140012C2B
0x140012bd7  mov     [rbp+4Fh+var_78], rsi
0x140012bdb  mov     rdi, [rbp+4Fh+var_90]
0x140012bdf  mov     rax, [rdi]
0x140012be2  mov     rbx, [rax+40h]
0x140012be6  lea     rcx, [rbp+4Fh+var_78]
0x140012bea  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012bef  lea     r8, [rbp+4Fh+var_78]
0x140012bf3  mov     rdx, [rbp+4Fh+var_98]
0x140012bf7  mov     rcx, rdi
0x140012bfa  mov     rax, rbx
0x140012bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c02  mov     ebx, eax
0x140012c04  test    eax, eax
0x140012c06  jns     short loc_140012C54
0x140012c08  mov     rcx, [rbp+57h]; this
0x140012c0c  mov     r9d, eax; char *
0x140012c0f  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140012c16  mov     edx, 46h ; 'F'; void *
0x140012c1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012c20  nop
0x140012c21  lea     rcx, [rbp+4Fh+var_78]
0x140012c25  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c2a  nop
0x140012c2b  lea     rcx, [rbp+4Fh+var_90]
0x140012c2f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c34  nop
0x140012c35  lea     rcx, [rbp+4Fh+var_88]
0x140012c39  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c3e  nop
0x140012c3f  lea     rcx, [rbp+4Fh+var_98]
0x140012c43  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c48  nop
0x140012c49  lea     rcx, [rbp+4Fh+var_80]
0x140012c4d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c52  jmp     short loc_140012C87
0x140012c54  lea     rcx, [rbp+4Fh+var_78]
0x140012c58  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c5d  nop
0x140012c5e  lea     rcx, [rbp+4Fh+var_90]
0x140012c62  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c67  nop
0x140012c68  lea     rcx, [rbp+4Fh+var_88]
0x140012c6c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c71  nop
0x140012c72  lea     rcx, [rbp+4Fh+var_98]
0x140012c76  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c7b  nop
0x140012c7c  lea     rcx, [rbp+4Fh+var_80]
0x140012c80  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140012c85  mov     ebx, esi
0x140012c87  lea     rcx, [rbp+4Fh+var_48]
0x140012c8b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012c90  mov     eax, ebx
0x140012c92  mov     rcx, [rbp+4Fh+var_28]
0x140012c96  xor     rcx, rsp; StackCookie
0x140012c99  call    __security_check_cookie
0x140012c9e  add     rsp, 0A8h
0x140012ca5  pop     rdi
0x140012ca6  pop     rsi
0x140012ca7  pop     rbx
0x140012ca8  pop     rbp
0x140012ca9  retn
```

# SystemSettings::Speech::CTextToSpeechPreviewButton::Invoke(HWND__ *)

- ea: `0x1800ccea0`
- end: `0x1800cd2a8`
- name: `?Invoke@CTextToSpeechPreviewButton@Speech@SystemSettings@@MEAAJPEAUHWND__@@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(SystemSettings::Speech::CTextToSpeechPreviewButton *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18002012c`
- `0x1800212b0`
- `0x1800773c4`
- `0x180081a64`
- `0x180086844`
- `0x1800869cc`
- `0x1800cafe0`
- `0x1800cb894`
- `0x1800ccea0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd12a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd17e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd25d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd12a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd17e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd25d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd140`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::Speech::CTextToSpeechPreviewButton::Invoke(
        SystemSettings::Speech::CTextToSpeechPreviewButton *this,
        HWND a2)
{
  __int64 *v3; // rsi
  int v4; // ebx
  __int64 v5; // rdx
  char *v6; // r15
  int v7; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rdi
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  HSTRING *StringRawBuffer; // rbx
  PCWSTR v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING, char *); // rbx
  __int64 v24; // [rsp+20h] [rbp-39h] BYREF
  __int64 v25; // [rsp+28h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-29h] BYREF
  __int64 v27; // [rsp+48h] [rbp-11h]
  HSTRING v28; // [rsp+50h] [rbp-9h] BYREF
  __int64 v29; // [rsp+58h] [rbp-1h] BYREF
  HSTRING v30; // [rsp+60h] [rbp+7h] BYREF
  __int64 v31; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+70h] [rbp+17h] BYREF
  __int64 v33; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v3 = (__int64 *)((char *)this + 216);
  if ( *((_QWORD *)this + 27)
    || (v27 = 0,
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.UI.Xaml.Controls.MediaElement",
          0x26u,
          0x25u),
        v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IMediaElement>>(
               v27,
               v3),
        v4 >= 0) )
  {
    v6 = (char *)this + 224;
    v27 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Media.SpeechSynthesis.SpeechSynthesizer",
      0x30u,
      0x2Fu);
    v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::ISpeechSynthesizer>>(
           v27,
           (char *)this + 224);
    if ( v4 < 0 )
    {
      v5 = 619;
      goto LABEL_4;
    }
    string = 0;
    v30 = 0;
    v33 = 0;
    v27 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Media.SpeechSynthesis.SpeechSynthesizer",
      0x30u,
      0x2Fu);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IInstalledVoicesStatic>>(
           v27,
           &v33);
    v4 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x273,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
        (const char *)(unsigned int)v7,
        v24);
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
LABEL_34:
      WindowsDeleteString(v30);
      v30 = 0;
      WindowsDeleteString(string);
      return (unsigned int)v4;
    }
    v29 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 56LL))(v33, &v29);
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147024894 )
    {
      v8 = (unsigned int)v4;
      v9 = 630;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
        (const char *)v8,
        v24);
LABEL_22:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      goto LABEL_23;
    }
    v10 = v29;
    if ( !v29 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v4 = 0;
      goto LABEL_23;
    }
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v12 = v11(v10, &string);
    v4 = v12;
    if ( v12 < 0 )
    {
      v8 = (unsigned int)v12;
      v9 = 635;
      goto LABEL_12;
    }
    v31 = 0;
    v13 = Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>::As<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>(
            &v29,
            &v31);
    v4 = v13;
    if ( v13 < 0 )
    {
      v14 = 637;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
        (const char *)(unsigned int)v13,
        v24);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      goto LABEL_22;
    }
    v15 = v31;
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 48LL);
    WindowsDeleteString(v30);
    v30 = 0;
    v13 = v16(v15, &v30);
    v4 = v13;
    if ( v13 < 0 )
    {
      v14 = 638;
      goto LABEL_21;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v28 = 0;
    StringRawBuffer = (HSTRING *)WindowsGetStringRawBuffer(string, 0);
    WindowsDeleteString(v28);
    v28 = 0;
    v18 = WindowsGetStringRawBuffer(v30, 0);
    v19 = SystemSettings::DataModel::FormatMessageArgAllocHString(v18, (const unsigned __int16 *)&v28, StringRawBuffer);
    v4 = v19;
    if ( v19 >= 0 )
    {
      v21 = *(_QWORD *)v6;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING, char *))(**(_QWORD **)v6 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 232);
      v19 = v22(v21, v28, (char *)this + 232);
      v4 = v19;
      if ( v19 >= 0 )
      {
        v24 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v3);
        v24 = *v3;
        v25 = v24;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v25);
        v4 = StartOperationAndThen<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *>,Windows::Foundation::IAsyncOperation<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *>,_lambda_d3c9d3dbdfa34488e04590d5409c603b_>(
               *((_QWORD *)this + 29),
               &v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        if ( v4 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
          WindowsDeleteString(v28);
          v4 = 0;
          goto LABEL_33;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29A,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
          (const char *)(unsigned int)v4,
          v24);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
LABEL_27:
        WindowsDeleteString(v28);
LABEL_33:
        v28 = 0;
        goto LABEL_34;
      }
      v20 = 649;
    }
    else
    {
      v20 = 645;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
      (const char *)(unsigned int)v19,
      v24);
    goto LABEL_27;
  }
  v5 = 613;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\speech.cpp",
    (const char *)(unsigned int)v4,
    v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ccea0  mov     [rsp-8+arg_8], rbx
0x1800ccea5  mov     [rsp-8+arg_10], rsi
0x1800cceaa  push    rbp
0x1800cceab  push    rdi
0x1800cceac  push    r12
0x1800cceae  push    r14
0x1800cceb0  push    r15
0x1800cceb2  lea     rbp, [rsp-37h]
0x1800cceb7  sub     rsp, 90h
0x1800ccebe  mov     rax, cs:__security_cookie
0x1800ccec5  xor     rax, rsp
0x1800ccec8  mov     [rbp+57h+var_30], rax
0x1800ccecc  mov     r14, rcx
0x1800ccecf  lea     rsi, [rcx+0D8h]
0x1800cced6  xor     r12d, r12d
0x1800cced9  cmp     [rsi], r12
0x1800ccedc  jnz     short loc_1800CCF2B
0x1800ccede  mov     [rbp+57h+var_68], r12
0x1800ccee2  lea     r9d, [r12+25h]; unsigned int
0x1800ccee7  lea     r8d, [r12+26h]; unsigned int
0x1800cceec  lea     rdx, ?RuntimeClass_Windows_UI_Xaml_Controls_MediaElement@@3QBGB; "Windows.UI.Xaml.Controls.MediaElement"
0x1800ccef3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ccef7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ccefc  mov     rdx, rsi
0x1800cceff  mov     rcx, [rbp+57h+var_68]
0x1800ccf03  call    ??$ActivateInstance@V?$ComPtr@UIMediaElement@Controls@Xaml@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIMediaElement@Controls@Xaml@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IMediaElement>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IMediaElement>>)
0x1800ccf08  mov     ebx, eax
0x1800ccf0a  test    eax, eax
0x1800ccf0c  jns     short loc_1800CCF2B
0x1800ccf0e  mov     edx, 265h; void *
0x1800ccf13  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800ccf1a  mov     r9d, ebx; char *
0x1800ccf1d  mov     rcx, [rbp+5Fh]; this
0x1800ccf21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccf26  jmp     loc_1800CD27D
0x1800ccf2b  lea     r15, [r14+0E0h]
0x1800ccf32  mov     [rbp+57h+var_68], r12
0x1800ccf36  mov     edi, 2Fh ; '/'
0x1800ccf3b  mov     r9d, edi; unsigned int
0x1800ccf3e  lea     r8d, [rdi+1]; unsigned int
0x1800ccf42  lea     rdx, ?RuntimeClass_Windows_Media_SpeechSynthesis_SpeechSynthesizer@@3QBGB; "Windows.Media.SpeechSynthesis.SpeechSyn"...
0x1800ccf49  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ccf4d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ccf52  mov     rdx, r15
0x1800ccf55  mov     rcx, [rbp+57h+var_68]
0x1800ccf59  call    ??$ActivateInstance@V?$ComPtr@UISpeechSynthesizer@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISpeechSynthesizer@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::ISpeechSynthesizer>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::ISpeechSynthesizer>>)
0x1800ccf5e  mov     ebx, eax
0x1800ccf60  test    eax, eax
0x1800ccf62  jns     short loc_1800CCF6B
0x1800ccf64  mov     edx, 26Bh
0x1800ccf69  jmp     short loc_1800CCF13
0x1800ccf6b  mov     [rbp+57h+string], r12
0x1800ccf6f  mov     [rbp+57h+var_50], r12
0x1800ccf73  mov     [rbp+57h+var_38], r12
0x1800ccf77  mov     [rbp+57h+var_68], r12
0x1800ccf7b  mov     r9d, edi; unsigned int
0x1800ccf7e  mov     r8d, 30h ; '0'; unsigned int
0x1800ccf84  lea     rdx, ?RuntimeClass_Windows_Media_SpeechSynthesis_SpeechSynthesizer@@3QBGB; "Windows.Media.SpeechSynthesis.SpeechSyn"...
0x1800ccf8b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ccf8f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ccf94  lea     rdx, [rbp+57h+var_38]
0x1800ccf98  mov     rcx, [rbp+57h+var_68]
0x1800ccf9c  call    ??$GetActivationFactory@V?$ComPtr@UIInstalledVoicesStatic@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInstalledVoicesStatic@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IInstalledVoicesStatic>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IInstalledVoicesStatic>>)
0x1800ccfa1  mov     ebx, eax
0x1800ccfa3  test    eax, eax
0x1800ccfa5  jns     short loc_1800CCFC4
0x1800ccfa7  mov     rcx, [rbp+5Fh]; this
0x1800ccfab  mov     r9d, eax; char *
0x1800ccfae  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800ccfb5  mov     edx, 273h; void *
0x1800ccfba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccfbf  jmp     loc_1800CD0E2
0x1800ccfc4  mov     [rbp+57h+var_58], r12
0x1800ccfc8  mov     rcx, [rbp+57h+var_38]
0x1800ccfcc  mov     rax, [rcx]
0x1800ccfcf  lea     rdx, [rbp+57h+var_58]
0x1800ccfd3  mov     rax, [rax+38h]
0x1800ccfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccfdc  mov     ebx, eax
0x1800ccfde  mov     eax, 80000000h
0x1800ccfe3  lea     ecx, [rbx+rax]
0x1800ccfe6  test    eax, ecx
0x1800ccfe8  jnz     short loc_1800CD00F
0x1800ccfea  cmp     ebx, 80070002h
0x1800ccff0  jz      short loc_1800CD00F
0x1800ccff2  mov     r9d, ebx; char *
0x1800ccff5  mov     edx, 276h; void *
0x1800ccffa  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cd001  mov     rcx, [rbp+5Fh]; this
0x1800cd005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd00a  jmp     loc_1800CD0D8
0x1800cd00f  mov     rbx, [rbp+57h+var_58]
0x1800cd013  test    rbx, rbx
0x1800cd016  jnz     short loc_1800CD029
0x1800cd018  lea     rcx, [rbp+57h+var_58]
0x1800cd01c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd021  mov     ebx, r12d
0x1800cd024  jmp     loc_1800CD0E2
0x1800cd029  mov     rax, [rbx]
0x1800cd02c  mov     rdi, [rax+30h]
0x1800cd030  mov     rcx, [rbp+57h+string]; string
0x1800cd034  call    cs:__imp_WindowsDeleteString
0x1800cd03b  nop     dword ptr [rax+rax+00h]
0x1800cd040  mov     [rbp+57h+string], r12
0x1800cd044  lea     rdx, [rbp+57h+string]
0x1800cd048  mov     rcx, rbx
0x1800cd04b  mov     rax, rdi
0x1800cd04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd053  mov     ebx, eax
0x1800cd055  test    eax, eax
0x1800cd057  jns     short loc_1800CD063
0x1800cd059  mov     r9d, eax
0x1800cd05c  mov     edx, 27Bh
0x1800cd061  jmp     short loc_1800CCFFA
0x1800cd063  mov     [rbp+57h+var_48], r12
0x1800cd067  lea     rdx, [rbp+57h+var_48]
0x1800cd06b  lea     rcx, [rbp+57h+var_58]
0x1800cd06f  call    ??$As@UIVoiceInformationAllProperties@Internal@SpeechSynthesis@Media@Windows@@@?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVoiceInformationAllProperties@Internal@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>::As<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>>)
0x1800cd074  mov     ebx, eax
0x1800cd076  test    eax, eax
0x1800cd078  jns     short loc_1800CD081
0x1800cd07a  mov     edx, 27Dh
0x1800cd07f  jmp     short loc_1800CD0BA
0x1800cd081  mov     rdi, [rbp+57h+var_48]
0x1800cd085  mov     rax, [rdi]
0x1800cd088  mov     rbx, [rax+30h]
0x1800cd08c  mov     rcx, [rbp+57h+var_50]; string
0x1800cd090  call    cs:__imp_WindowsDeleteString
0x1800cd097  nop     dword ptr [rax+rax+00h]
0x1800cd09c  mov     [rbp+57h+var_50], r12
0x1800cd0a0  lea     rdx, [rbp+57h+var_50]
0x1800cd0a4  mov     rcx, rdi
0x1800cd0a7  mov     rax, rbx
0x1800cd0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd0af  mov     ebx, eax
0x1800cd0b1  test    eax, eax
0x1800cd0b3  jns     short loc_1800CD0F0
0x1800cd0b5  mov     edx, 27Eh; void *
0x1800cd0ba  mov     r9d, eax; char *
0x1800cd0bd  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cd0c4  mov     rcx, [rbp+5Fh]; this
0x1800cd0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd0cd  nop
0x1800cd0ce  lea     rcx, [rbp+57h+var_48]
0x1800cd0d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd0d7  nop
0x1800cd0d8  lea     rcx, [rbp+57h+var_58]
0x1800cd0dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd0e1  nop
0x1800cd0e2  lea     rcx, [rbp+57h+var_38]
0x1800cd0e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd0eb  jmp     loc_1800CD259
0x1800cd0f0  lea     rcx, [rbp+57h+var_48]
0x1800cd0f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd0f9  nop
0x1800cd0fa  lea     rcx, [rbp+57h+var_58]
0x1800cd0fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd103  nop
0x1800cd104  lea     rcx, [rbp+57h+var_38]
0x1800cd108  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd10d  mov     [rbp+57h+var_60], r12
0x1800cd111  xor     edx, edx; length
0x1800cd113  mov     rcx, [rbp+57h+string]; string
0x1800cd117  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd11e  nop     dword ptr [rax+rax+00h]
0x1800cd123  mov     rbx, rax
0x1800cd126  mov     rcx, [rbp+57h+var_60]; string
0x1800cd12a  call    cs:__imp_WindowsDeleteString
0x1800cd131  nop     dword ptr [rax+rax+00h]
0x1800cd136  mov     [rbp+57h+var_60], r12
0x1800cd13a  xor     edx, edx; length
0x1800cd13c  mov     rcx, [rbp+57h+var_50]; string
0x1800cd140  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd147  nop     dword ptr [rax+rax+00h]
0x1800cd14c  mov     r8, rbx; HSTRING *
0x1800cd14f  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800cd153  mov     rcx, rax; lpSource
0x1800cd156  call    ?FormatMessageArgAllocHString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@ZZ; SystemSettings::DataModel::FormatMessageArgAllocHString(ushort const *,HSTRING__ * *,...)
0x1800cd15b  mov     ebx, eax
0x1800cd15d  test    eax, eax
0x1800cd15f  jns     short loc_1800CD18F
0x1800cd161  mov     edx, 285h; void *
0x1800cd166  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cd16d  mov     r9d, eax; char *
0x1800cd170  mov     rcx, [rbp+5Fh]; this
0x1800cd174  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd179  nop
0x1800cd17a  mov     rcx, [rbp+57h+var_60]; string
0x1800cd17e  call    cs:__imp_WindowsDeleteString
0x1800cd185  nop     dword ptr [rax+rax+00h]
0x1800cd18a  jmp     loc_1800CD255
0x1800cd18f  mov     rdi, [r15]
0x1800cd192  mov     rax, [rdi]
0x1800cd195  mov     rbx, [rax+30h]
0x1800cd199  lea     rcx, [r14+0E8h]
0x1800cd1a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd1a5  lea     r8, [r14+0E8h]
0x1800cd1ac  mov     rdx, [rbp+57h+var_60]
0x1800cd1b0  mov     rcx, rdi
0x1800cd1b3  mov     rax, rbx
0x1800cd1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd1bb  mov     ebx, eax
0x1800cd1bd  test    eax, eax
0x1800cd1bf  jns     short loc_1800CD1C8
0x1800cd1c1  mov     edx, 289h
0x1800cd1c6  jmp     short loc_1800CD166
0x1800cd1c8  mov     [rbp+57h+var_90], r12
0x1800cd1cc  lea     rcx, [rbp+57h+var_90]
0x1800cd1d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd1d5  mov     rcx, rsi
0x1800cd1d8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800cd1dd  mov     rax, [rsi]
0x1800cd1e0  mov     [rbp+57h+var_90], rax
0x1800cd1e4  mov     [rbp+57h+var_88], rax
0x1800cd1e8  lea     rcx, [rbp+57h+var_88]
0x1800cd1ec  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800cd1f1  nop
0x1800cd1f2  lea     rdx, [rbp+57h+var_88]
0x1800cd1f6  mov     rcx, [r14+0E8h]
0x1800cd1fd  call    ??$StartOperationAndThen@U?$IAsyncOperationCompletedHandler@PEAVSpeechSynthesisStream@SpeechSynthesis@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSpeechSynthesisStream@SpeechSynthesis@Media@Windows@@@23@V_lambda_d3c9d3dbdfa34488e04590d5409c603b_@@@@YAJPEAU?$IAsyncOperation@PEAVSpeechSynthesisStream@SpeechSynthesis@Media@Windows@@@Foundation@Windows@@$$QEAV_lambda_d3c9d3dbdfa34488e04590d5409c603b_@@@Z; StartOperationAndThen<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *>,Windows::Foundation::IAsyncOperation<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *>,_lambda_d3c9d3dbdfa34488e04590d5409c603b_>(Windows::Foundation::IAsyncOperation<Windows::Media::SpeechSynthesis::SpeechSynthesisStream *> *,_lambda_d3c9d3dbdfa34488e04590d5409c603b_ &&)
0x1800cd202  mov     ebx, eax
0x1800cd204  lea     rcx, [rbp+57h+var_88]
0x1800cd208  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd20d  test    ebx, ebx
0x1800cd20f  jns     short loc_1800CD238
0x1800cd211  mov     rcx, [rbp+5Fh]; this
0x1800cd215  mov     r9d, ebx; char *
0x1800cd218  lea     r8, aShellSystemset_51; "shell\\systemsettingsthreshold\\handler"...
0x1800cd21f  mov     edx, 29Ah; void *
0x1800cd224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd229  nop
0x1800cd22a  lea     rcx, [rbp+57h+var_90]
0x1800cd22e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd233  jmp     loc_1800CD17A
0x1800cd238  lea     rcx, [rbp+57h+var_90]
0x1800cd23c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cd241  nop
0x1800cd242  mov     rcx, [rbp+57h+var_60]; string
0x1800cd246  call    cs:__imp_WindowsDeleteString
0x1800cd24d  nop     dword ptr [rax+rax+00h]
0x1800cd252  mov     ebx, r12d
0x1800cd255  mov     [rbp+57h+var_60], r12
0x1800cd259  mov     rcx, [rbp+57h+var_50]; string
0x1800cd25d  call    cs:__imp_WindowsDeleteString
0x1800cd264  nop     dword ptr [rax+rax+00h]
0x1800cd269  mov     [rbp+57h+var_50], r12
0x1800cd26d  mov     rcx, [rbp+57h+string]; string
0x1800cd271  call    cs:__imp_WindowsDeleteString
0x1800cd278  nop     dword ptr [rax+rax+00h]
0x1800cd27d  mov     eax, ebx
0x1800cd27f  mov     rcx, [rbp+57h+var_30]
0x1800cd283  xor     rcx, rsp; StackCookie
0x1800cd286  call    __security_check_cookie
0x1800cd28b  lea     r11, [rsp+0B0h+var_20]
0x1800cd293  mov     rbx, [r11+38h]
0x1800cd297  mov     rsi, [r11+40h]
0x1800cd29b  mov     rsp, r11
0x1800cd29e  pop     r15
0x1800cd2a0  pop     r14
0x1800cd2a2  pop     r12
0x1800cd2a4  pop     rdi
0x1800cd2a5  pop     rbp
0x1800cd2a6  retn
```

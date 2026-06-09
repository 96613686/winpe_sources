# CloudExperienceHostAPI::Speech::SpeechRecognitionKnownCommands::GetKnownListConstraint(ushort const *,uint,Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint * *)

- ea: `0x180011188`
- end: `0x180011634`
- name: `?GetKnownListConstraint@SpeechRecognitionKnownCommands@Speech@CloudExperienceHostAPI@@AEAAJPEBGIPEAPEAUISpeechRecognitionConstraint@SpeechRecognition@Media@Windows@@@Z`
- size: `1196`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::Speech::SpeechRecognitionKnownCommands *__hidden this, const unsigned __int16 *, unsigned int, struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint **)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180095ab0`
- `0x180095b30`
- `0x180095b50`
- `0x180095b90`

## callees

- `0x180003a70`
- `0x180005174`
- `0x18000fb00`
- `0x18000fb58`
- `0x180010810`
- `0x180010c8c`
- `0x180011188`
- `0x180011d60`
- `0x1800128a4`
- `0x180013c14`
- `0x18001a540`
- `0x18001b004`
- `0x180022790`
- `0x1800924b4`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800113d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18001143a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800113d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18001143a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001127c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800115ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001127c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800115ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800112d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800112d5`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18001131f`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18001131f`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800112f4`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800112f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011202`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011482`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011202`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011482`

## string_xrefs

- `0x18001153e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall CloudExperienceHostAPI::Speech::SpeechRecognitionKnownCommands::GetKnownListConstraint(
        const wchar_t **this,
        const unsigned __int16 *a2,
        int a3,
        struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint **a4)
{
  int ActivationFactory; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, HSTRING *); // rbx
  int v12; // eax
  const WCHAR *StringRawBuffer; // rax
  const char *v14; // r9
  unsigned __int16 v15; // bx
  const char *v16; // r9
  int v17; // eax
  HINSTANCE v18; // rdx
  CloudExperienceHostAPI::Speech::SpeechRecognitionKnownCommands *v19; // rcx
  int v20; // eax
  wchar_t *v21; // rax
  char v22; // r8
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, PVOID); // rdi
  HSTRING_HEADER *v25; // rax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, _QWORD); // rdi
  _QWORD *v30; // rax
  int v31; // eax
  int v32; // eax
  char v33; // r8
  struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *v34; // rdi
  __int64 (__fastcall *v35)(struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *, PVOID); // rbx
  HSTRING_HEADER *v36; // rax
  int v37; // eax
  struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *v38; // rax
  int v40; // [rsp+20h] [rbp-188h]
  int v41; // [rsp+20h] [rbp-188h]
  struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *v42; // [rsp+30h] [rbp-178h] BYREF
  HSTRING string; // [rsp+38h] [rbp-170h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint **); // [rsp+40h] [rbp-168h] BYREF
  wchar_t *String; // [rsp+48h] [rbp-160h] BYREF
  __int64 v46; // [rsp+50h] [rbp-158h] BYREF
  __int64 v47; // [rsp+58h] [rbp-150h] BYREF
  wchar_t *v48; // [rsp+60h] [rbp-148h] BYREF
  __int64 v49; // [rsp+68h] [rbp-140h] BYREF
  __int64 *v50; // [rsp+70h] [rbp-138h] BYREF
  wchar_t *Context; // [rsp+78h] [rbp-130h] BYREF
  const WCHAR *v52; // [rsp+80h] [rbp-128h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-120h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-108h]
  WCHAR LocaleName[88]; // [rsp+B0h] [rbp-F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v52 = a2;
  *a4 = 0;
  v50 = 0;
  v54 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.ApplicationLanguages",
    0x2Bu,
    0x2Au);
  ActivationFactory = RoGetActivationFactory(v54, &GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed, &v50);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x365,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v40);
  v47 = 0;
  v8 = *v50;
  v47 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 64))(v50, &v47);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x367,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v9,
      v40);
  string = 0;
  v10 = v47;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v47 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v12 = v11(v10, 0, &string);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v12,
      v40);
  memset_0(LocaleName, 0, 0xAAu);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !ResolveLocaleName(StringRawBuffer, LocaleName, 85) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      v14);
  v15 = LocaleNameToLCID(LocaleName, 0x8000000u);
  if ( !v15 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36F,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      v16);
  v46 = 0;
  v17 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
          (__int64)retaddr,
          &v46);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x372,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v17,
      v40);
  String = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &String,
    0);
  v20 = CloudExperienceHostAPI::Speech::SpeechRecognitionKnownCommands::LoadLocalizedString(v19, v18, a3, v15, &String);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x377,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v20,
      v41);
  Context = 0;
  v21 = wcstok(String, this[10], &Context);
  v23 = v46;
  while ( 1 )
  {
    v48 = v21;
    if ( !v21 )
      break;
    v24 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v23 + 104LL);
    v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v48, v22);
    v26 = v24(v23, v25[1].Reserved.Reserved1);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37C,
        (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
        (const char *)(unsigned int)v26,
        v41);
    v21 = wcstok(0, this[10], &Context);
  }
  v49 = 0;
  v54 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Media.SpeechRecognition.SpeechRecognitionListConstraint",
    0x40u,
    0x3Fu);
  v27 = RoGetActivationFactory(v54, &GUID_40f3cdc7_562a_426a_9f3b_3b4e282be1d5, &v49);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v27,
      v41);
  v44 = 0;
  v28 = v49;
  v29 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v49 + 48LL);
  v44 = 0;
  v30 = (_QWORD *)wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>,wil::err_exception_policy>::query<Windows::Foundation::Collections::IIterable<HSTRING__ *>>(
                    &v46,
                    &v48);
  v31 = v29(v28, *v30, &v44);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v31,
      v41);
  wil::com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>::~com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>(&v48);
  v42 = 0;
  v32 = (**v44)(v44, &GUID_79ac1628_4d68_43c4_8911_40dc4101b55b, &v42);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v32,
      v41);
  v34 = v42;
  v35 = *(__int64 (__fastcall **)(struct Windows::Media::SpeechRecognition::ISpeechRecognitionConstraint *, PVOID))(*(_QWORD *)v42 + 72LL);
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v52, v33);
  v37 = v35(v34, v36[1].Reserved.Reserved1);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\speech.cpp",
      (const char *)(unsigned int)v37,
      v41);
  v38 = v42;
  v42 = 0;
  *a4 = v38;
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v42);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v44);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v49);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v46);
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v47);
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(&v50);
  return 0;
}

```

## disassembly

```asm
0x180011188  push    rbx
0x18001118a  push    rsi
0x18001118b  push    rdi
0x18001118c  push    r12
0x18001118e  push    r14
0x180011190  push    r15
0x180011192  sub     rsp, 178h
0x180011199  mov     rax, cs:__security_cookie
0x1800111a0  xor     rax, rsp
0x1800111a3  mov     [rsp+1A8h+var_48], rax
0x1800111ab  mov     r15, r9
0x1800111ae  mov     r14d, r8d
0x1800111b1  mov     rsi, rcx
0x1800111b4  mov     [rsp+1A8h+var_128], rdx
0x1800111bc  xor     r12d, r12d
0x1800111bf  mov     [r9], r12
0x1800111c2  mov     [rsp+1A8h+var_138], r12
0x1800111c7  mov     [rsp+1A8h+var_108], r12
0x1800111cf  lea     r9d, [r12+2Ah]; unsigned int
0x1800111d4  lea     r8d, [r12+2Bh]; unsigned int
0x1800111d9  lea     rdx, ?RuntimeClass_Windows_Globalization_ApplicationLanguages@@3QBGB; "Windows.Globalization.ApplicationLangua"...
0x1800111e0  lea     rcx, [rsp+1A8h+hstringHeader]; hstringHeader
0x1800111e8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800111ed  nop
0x1800111ee  lea     r8, [rsp+1A8h+var_138]
0x1800111f3  lea     rdx, _GUID_75b40847_0a4c_4a92_9565_fd63c95f7aed
0x1800111fa  mov     rcx, [rsp+1A8h+var_108]
0x180011202  call    cs:__imp_RoGetActivationFactory
0x180011208  mov     rcx, [rsp+1A8h]; this
0x180011210  test    eax, eax
0x180011212  jns     short loc_180011229
0x180011214  mov     r9d, eax; char *
0x180011217  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001121e  mov     edx, 365h; void *
0x180011223  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011229  mov     [rsp+1A8h+var_150], r12
0x18001122e  mov     rcx, [rsp+1A8h+var_138]
0x180011233  mov     rax, [rcx]
0x180011236  mov     [rsp+1A8h+var_150], r12
0x18001123b  lea     rdx, [rsp+1A8h+var_150]
0x180011240  mov     rax, [rax+40h]
0x180011244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011249  mov     rcx, [rsp+1A8h]; this
0x180011251  test    eax, eax
0x180011253  jns     short loc_180011269
0x180011255  mov     r9d, eax; char *
0x180011258  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001125f  mov     edx, 367h; void *
0x180011264  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011269  mov     [rsp+1A8h+string], r12
0x18001126e  mov     rdi, [rsp+1A8h+var_150]
0x180011273  mov     rax, [rdi]
0x180011276  mov     rbx, [rax+30h]
0x18001127a  xor     ecx, ecx; string
0x18001127c  call    cs:__imp_WindowsDeleteString
0x180011282  mov     [rsp+1A8h+string], r12
0x180011287  lea     r8, [rsp+1A8h+string]
0x18001128c  xor     edx, edx
0x18001128e  mov     rcx, rdi
0x180011291  mov     rax, rbx
0x180011294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011299  mov     rcx, [rsp+1A8h]; this
0x1800112a1  test    eax, eax
0x1800112a3  jns     short loc_1800112B9
0x1800112a5  mov     r9d, eax; char *
0x1800112a8  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800112af  mov     edx, 369h; void *
0x1800112b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800112b9  xor     edx, edx; Val
0x1800112bb  mov     r8d, 0AAh; Size
0x1800112c1  lea     rcx, [rsp+1A8h+LocaleName]; void *
0x1800112c9  call    memset_0
0x1800112ce  xor     edx, edx; length
0x1800112d0  mov     rcx, [rsp+1A8h+string]; string
0x1800112d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800112db  mov     rbx, [rsp+1A8h]
0x1800112e3  mov     r8d, 55h ; 'U'; cchLocaleName
0x1800112e9  lea     rdx, [rsp+1A8h+LocaleName]; lpLocaleName
0x1800112f1  mov     rcx, rax; lpNameToResolve
0x1800112f4  call    cs:__imp_ResolveLocaleName
0x1800112fa  test    eax, eax
0x1800112fc  jnz     short loc_180011312
0x1800112fe  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011305  mov     edx, 36Dh; void *
0x18001130a  mov     rcx, rbx; this
0x18001130d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180011312  mov     edx, 8000000h; dwFlags
0x180011317  lea     rcx, [rsp+1A8h+LocaleName]; lpName
0x18001131f  call    cs:__imp_LocaleNameToLCID
0x180011325  mov     ebx, eax
0x180011327  mov     rcx, [rsp+1A8h]; this
0x18001132f  cmp     r12w, ax
0x180011333  jnz     short loc_180011347
0x180011335  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001133c  mov     edx, 36Fh; void *
0x180011341  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180011347  mov     [rsp+1A8h+var_158], r12
0x18001134c  lea     rdx, [rsp+1A8h+var_158]
0x180011351  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x180011356  mov     rcx, [rsp+1A8h]; this
0x18001135e  test    eax, eax
0x180011360  jns     short loc_180011376
0x180011362  mov     r9d, eax; char *
0x180011365  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001136c  mov     edx, 372h; void *
0x180011371  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011376  mov     [rsp+1A8h+String], r12
0x18001137b  xor     edx, edx
0x18001137d  lea     rcx, [rsp+1A8h+String]
0x180011382  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180011387  lea     rax, [rsp+1A8h+String]
0x18001138c  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x180011391  movzx   r9d, bx; unsigned __int16
0x180011395  mov     r8d, r14d; int
0x180011398  call    ?LoadLocalizedString@SpeechRecognitionKnownCommands@Speech@CloudExperienceHostAPI@@AEAAJPEAUHINSTANCE__@@HGPEAPEAG@Z; CloudExperienceHostAPI::Speech::SpeechRecognitionKnownCommands::LoadLocalizedString(HINSTANCE__ *,int,ushort,ushort * *)
0x18001139d  mov     rcx, [rsp+1A8h]; this
0x1800113a5  test    eax, eax
0x1800113a7  jns     short loc_1800113BD
0x1800113a9  mov     r9d, eax; char *
0x1800113ac  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800113b3  mov     edx, 377h; void *
0x1800113b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800113bd  mov     [rsp+1A8h+Context], r12
0x1800113c2  lea     r8, [rsp+1A8h+Context]; Context
0x1800113c7  mov     rdx, [rsi+50h]; Delimiter
0x1800113cb  mov     rcx, [rsp+1A8h+String]; String
0x1800113d0  call    cs:__imp_wcstok
0x1800113d6  mov     rbx, [rsp+1A8h+var_158]
0x1800113db  mov     [rsp+1A8h+var_148], rax
0x1800113e0  test    rax, rax
0x1800113e3  jz      short loc_180011442
0x1800113e5  mov     rax, [rbx]
0x1800113e8  mov     rdi, [rax+68h]
0x1800113ec  lea     rdx, [rsp+1A8h+var_148]
0x1800113f1  lea     rcx, [rsp+1A8h+hstringHeader]
0x1800113f9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800113fe  nop
0x1800113ff  mov     rdx, [rax+18h]
0x180011403  mov     rcx, rbx
0x180011406  mov     rax, rdi
0x180011409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001140e  mov     rcx, [rsp+1A8h]; this
0x180011416  test    eax, eax
0x180011418  jns     short loc_18001142F
0x18001141a  mov     r9d, eax; char *
0x18001141d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011424  mov     edx, 37Ch; void *
0x180011429  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001142f  lea     r8, [rsp+1A8h+Context]; Context
0x180011434  mov     rdx, [rsi+50h]; Delimiter
0x180011438  xor     ecx, ecx; String
0x18001143a  call    cs:__imp_wcstok
0x180011440  jmp     short loc_1800113DB
0x180011442  mov     [rsp+1A8h+var_140], r12
0x180011447  mov     [rsp+1A8h+var_108], r12
0x18001144f  mov     r9d, 3Fh ; '?'; unsigned int
0x180011455  lea     r8d, [r9+1]; unsigned int
0x180011459  lea     rdx, ?RuntimeClass_Windows_Media_SpeechRecognition_SpeechRecognitionListConstraint@@3QBGB; "Windows.Media.SpeechRecognition.SpeechR"...
0x180011460  lea     rcx, [rsp+1A8h+hstringHeader]; hstringHeader
0x180011468  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001146d  nop
0x18001146e  lea     r8, [rsp+1A8h+var_140]
0x180011473  lea     rdx, _GUID_40f3cdc7_562a_426a_9f3b_3b4e282be1d5
0x18001147a  mov     rcx, [rsp+1A8h+var_108]
0x180011482  call    cs:__imp_RoGetActivationFactory
0x180011488  mov     rcx, [rsp+1A8h]; this
0x180011490  test    eax, eax
0x180011492  jns     short loc_1800114A9
0x180011494  mov     r9d, eax; char *
0x180011497  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x18001149e  mov     edx, 381h; void *
0x1800114a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800114a9  mov     [rsp+1A8h+var_168], r12
0x1800114ae  mov     rbx, [rsp+1A8h+var_140]
0x1800114b3  mov     rax, [rbx]
0x1800114b6  mov     rdi, [rax+30h]
0x1800114ba  mov     [rsp+1A8h+var_168], r12
0x1800114bf  lea     rdx, [rsp+1A8h+var_148]
0x1800114c4  lea     rcx, [rsp+1A8h+var_158]
0x1800114c9  call    ??$query@U?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@?$com_ptr_t@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>,wil::err_exception_policy>::query<Windows::Foundation::Collections::IIterable<HSTRING__ *>>(void)
0x1800114ce  nop
0x1800114cf  lea     r8, [rsp+1A8h+var_168]
0x1800114d4  mov     rdx, [rax]
0x1800114d7  mov     rcx, rbx
0x1800114da  mov     rax, rdi
0x1800114dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114e2  mov     rcx, [rsp+1A8h]; this
0x1800114ea  test    eax, eax
0x1800114ec  jns     short loc_180011503
0x1800114ee  mov     r9d, eax; char *
0x1800114f1  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x1800114f8  mov     edx, 383h; void *
0x1800114fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011503  lea     rcx, [rsp+1A8h+var_148]
0x180011508  call    ??1?$com_ptr_t@UIStoreContext3@Store@Services@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>::~com_ptr_t<Windows::Services::Store::IStoreContext3,wil::err_returncode_policy>(void)
0x18001150d  nop
0x18001150e  mov     [rsp+1A8h+var_178], r12
0x180011513  mov     rcx, [rsp+1A8h+var_168]
0x180011518  mov     rax, [rcx]
0x18001151b  lea     r8, [rsp+1A8h+var_178]
0x180011520  lea     rdx, _GUID_79ac1628_4d68_43c4_8911_40dc4101b55b
0x180011527  mov     rax, [rax]
0x18001152a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001152f  mov     rcx, [rsp+1A8h]; this
0x180011537  test    eax, eax
0x180011539  jns     short loc_18001154F
0x18001153b  mov     r9d, eax; char *
0x18001153e  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011545  mov     edx, 1CBEh; void *
0x18001154a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001154f  mov     rdi, [rsp+1A8h+var_178]
0x180011554  mov     rax, [rdi]
0x180011557  mov     rbx, [rax+48h]
0x18001155b  lea     rdx, [rsp+1A8h+var_128]
0x180011563  lea     rcx, [rsp+1A8h+hstringHeader]
0x18001156b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180011570  nop
0x180011571  mov     rdx, [rax+18h]
0x180011575  mov     rcx, rdi
0x180011578  mov     rax, rbx
0x18001157b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011580  mov     rcx, [rsp+1A8h]; this
0x180011588  test    eax, eax
0x18001158a  jns     short loc_1800115A1
0x18001158c  mov     r9d, eax; char *
0x18001158f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudexperiencehost"...
0x180011596  mov     edx, 386h; void *
0x18001159b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800115a1  mov     rax, [rsp+1A8h+var_178]
0x1800115a6  mov     [rsp+1A8h+var_178], r12
0x1800115ab  mov     [r15], rax
0x1800115ae  lea     rcx, [rsp+1A8h+var_178]
0x1800115b3  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800115b8  nop
0x1800115b9  lea     rcx, [rsp+1A8h+var_168]
0x1800115be  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800115c3  nop
0x1800115c4  lea     rcx, [rsp+1A8h+var_140]
0x1800115c9  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800115ce  nop
0x1800115cf  lea     rcx, [rsp+1A8h+String]
0x1800115d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800115d9  nop
0x1800115da  lea     rcx, [rsp+1A8h+var_158]
0x1800115df  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800115e4  nop
0x1800115e5  mov     rcx, [rsp+1A8h+string]; string
0x1800115ea  call    cs:__imp_WindowsDeleteString
0x1800115f0  mov     [rsp+1A8h+string], r12
0x1800115f5  lea     rcx, [rsp+1A8h+var_150]
0x1800115fa  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x1800115ff  nop
0x180011600  lea     rcx, [rsp+1A8h+var_138]
0x180011605  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVLaunchUriResult@System@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::System::LaunchUriResult *>,wil::err_exception_policy>(void)
0x18001160a  xor     eax, eax
0x18001160c  jmp     short loc_180011612
0x18001160e  mov     eax, dword ptr [rsp+1A8h+var_178]
0x180011612  mov     rcx, [rsp+1A8h+var_48]
0x18001161a  xor     rcx, rsp; StackCookie
0x18001161d  call    __security_check_cookie
0x180011622  add     rsp, 178h
0x180011629  pop     r15
0x18001162b  pop     r14
0x18001162d  pop     r12
0x18001162f  pop     rdi
0x180011630  pop     rsi
0x180011631  pop     rbx
0x180011632  retn
```

# Cortana::ConstraintIndex::CSGSuggestion::CSGSuggester::_GetEntitiesAsJson(Platform::String *,Platform::String *,int,bool)

- ea: `0x18003e52c`
- end: `0x18003e90b`
- name: `?_GetEntitiesAsJson@CSGSuggester@CSGSuggestion@ConstraintIndex@Cortana@@AE$AAAPE$AAVString@Platform@@PE$AAV56@0H_N@Z`
- size: `991`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b7a0`

## callees

- `0x1800049e0`
- `0x180005250`
- `0x180005e44`
- `0x18000617a`
- `0x18000619e`
- `0x18000c840`
- `0x18000cdb0`
- `0x18001c0dc`
- `0x180039724`
- `0x18003a0dc`
- `0x18003a4a0`
- `0x18003a5f4`
- `0x18003a92c`
- `0x18003a9b4`
- `0x18003bbb0`
- `0x18003c648`
- `0x18003d550`
- `0x18003d830`
- `0x18003e52c`
- `0x18003fe64`
- `0x18003ff00`
- `0x18003ff8c`
- `0x180040b20`
- `0x180071e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7c4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003e729`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003e76a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003e729`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003e76a`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003e876`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003e8c7`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003e876`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003e8c7`
- `wincorlib!??0Exception@Platform@@QE$AAA@HPE$AAVString@1@@Z` at `0x18003e8a0`
- `wincorlib!??0Exception@Platform@@QE$AAA@HPE$AAVString@1@@Z` at `0x18003e8ec`
- `wincorlib!??0Exception@Platform@@QE$AAA@HPE$AAVString@1@@Z` at `0x18003e8a0`
- `wincorlib!??0Exception@Platform@@QE$AAA@HPE$AAVString@1@@Z` at `0x18003e8ec`

## string_xrefs

- `0x18003e6e4`: `shellcommon\shell\cortana\constraintindex\src\CSGSuggest\CSGSuggester.cpp`
- `0x18003e59b`: `CSGSuggester_GetEntitiesAsJson`
- `0x18003e6d2`: `Constraint Index is not ready`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Cortana::ConstraintIndex::CSGSuggestion::CSGSuggester::_GetEntitiesAsJson(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  HSTRING v7; // r15
  HSTRING v8; // r12
  PCWSTR StringRawBuffer_0; // rax
  PCWSTR v10; // rax
  char v11; // si
  const CHAR *v12; // rbx
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  __int64 EntitySuggestions; // rax
  HSTRING v17; // rsi
  int v18; // eax
  int v19; // edi
  WCHAR *lpWideCharStr; // r14
  __int64 v21; // rcx
  unsigned int v22; // edi
  HSTRING v23; // rbx
  signed int v24; // eax
  signed int LastError; // eax
  __int64 v26; // rbx
  void *v28; // rbx
  __int64 FastPassSystemStringFromLiteral; // rax
  __int64 v30; // r8
  void *Exception; // rbx
  __int64 v32; // r8
  const char *cchWideChar; // [rsp+28h] [rbp-E8h]
  _QWORD v34[2]; // [rsp+90h] [rbp-80h] BYREF
  __int64 NativeErrorMessage; // [rsp+A0h] [rbp-70h] BYREF
  _BYTE v36[24]; // [rsp+A8h] [rbp-68h] BYREF
  HSTRING v37; // [rsp+C0h] [rbp-50h]
  HSTRING v38; // [rsp+C8h] [rbp-48h]
  __int64 v39; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-38h] BYREF
  _BYTE v41[32]; // [rsp+E0h] [rbp-30h] BYREF
  _BYTE v42[32]; // [rsp+100h] [rbp-10h] BYREF
  _BYTE v43[128]; // [rsp+120h] [rbp+10h] BYREF
  _QWORD v44[42]; // [rsp+1A0h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+228h]

  v7 = (HSTRING)__abi_winrt_ptrto_string_ctor(a2);
  v37 = v7;
  v8 = (HSTRING)__abi_winrt_ptrto_string_ctor(a3);
  v38 = v8;
  memset_0(v44, 0, sizeof(v44));
  wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v44);
  v44[0] = &Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::`vftable';
  Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::StartActivity(
    (__int64)v44,
    v7,
    v8,
    a4);
  memset_0(v43, 0, 0x78u);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v43);
  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v7, 0);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(
    v43,
    v42,
    StringRawBuffer_0);
  v10 = WindowsGetStringRawBuffer_0(v8, 0);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(
    v43,
    v41,
    v10);
  v11 = 0;
  LOBYTE(v34[0]) = 0;
  v34[1] = 0;
  v12 = 0;
  v40 = 0;
  if ( *(_QWORD *)(a1 + 32) )
  {
    std::_String_val<std::_Simple_types<char>>::_Myptr(v41);
    v13 = std::_String_val<std::_Simple_types<char>>::_Myptr(v42);
    EntitySuggestions = GetEntitySuggestions(
                          *(_QWORD *)(a1 + 32),
                          v13,
                          v14,
                          (unsigned int)&word_1801017B2,
                          (__int64)"*",
                          1,
                          1,
                          0,
                          1,
                          1,
                          v15,
                          0,
                          1,
                          a4,
                          10,
                          a4,
                          (__int64)v34);
    v12 = (const CHAR *)EntitySuggestions;
    v40 = EntitySuggestions;
    v11 = v34[0];
  }
  else
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x86,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\CSGSuggest\\CSGSuggester.cpp",
      (const char *)0x80004005LL,
      (int)"Constraint Index is not ready",
      cchWideChar);
    EntitySuggestions = 0;
  }
  if ( v11 )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x80u);
    v39 = (__int64)Exception;
    NativeErrorMessage = Cortana::ConstraintIndex::CSGSuggestion::GetNativeErrorMessage(v34);
    v39 = Platform::Exception::Exception(Exception, 2147500037LL, NativeErrorMessage);
    wil::details::ReportFailure_CustomException<Platform::Exception __gc *>(retaddr, 137, v32, v39);
  }
  v17 = 0;
  NativeErrorMessage = 0;
  if ( EntitySuggestions )
  {
    v18 = MultiByteToWideChar(0xFDE9u, 0, v12, -1, 0, 0);
    v19 = v18;
    if ( v18 <= 0 )
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      lpWideCharStr = (WCHAR *)operator new[](saturated_mul(v18, 2u));
      v39 = (__int64)lpWideCharStr;
      if ( MultiByteToWideChar(0xFDE9u, 0, v12, -1, lpWideCharStr, v19) <= 0 )
      {
        v24 = GetLastError();
        v22 = v24;
        if ( v24 > 0 )
          v22 = (unsigned __int16)v24 | 0x80070000;
      }
      else
      {
        v22 = 0;
        v34[0] = 0;
        v23 = (HSTRING)Platform::String::String(v21, lpWideCharStr);
        v34[0] = v23;
        __abi_winrt_ptrto_string_assign(&NativeErrorMessage, v23);
        WindowsDeleteString_0(v23);
        v17 = (HSTRING)NativeErrorMessage;
      }
      std::unique_ptr<char const [0]>::~unique_ptr<char const [0]>(&v39);
    }
    if ( v22 )
    {
      v28 = Platform::Details::Heap::AllocateException(0x68u, 0x80u);
      v34[0] = v28;
      FastPassSystemStringFromLiteral = __abi_winrt_CreateFastPassSystemStringFromLiteral(
                                          L"Error while converting from utf8 to utf16",
                                          41,
                                          v36);
      v34[0] = Platform::Exception::Exception(v28, v22, FastPassSystemStringFromLiteral);
      wil::details::ReportFailure_CustomException<Platform::Exception __gc *>(retaddr, 166, v30, v34[0]);
    }
  }
  Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::Stop(
    (__int64)v44,
    v17);
  v26 = __abi_winrt_ptrto_string_ctor(v17);
  WindowsDeleteString_0(v17);
  std::unique_ptr<char const [0]>::~unique_ptr<char const [0]>(&v40);
  std::string::_Tidy_deallocate(v41);
  std::string::_Tidy_deallocate(v42);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v43);
  Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::~CSGSuggester_GetEntitiesAsJson((Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson *)v44);
  WindowsDeleteString_0(v7);
  WindowsDeleteString_0(v8);
  return v26;
}

```

## disassembly

```asm
0x18003e52c  push    rbp
0x18003e52e  push    rbx
0x18003e52f  push    rsi
0x18003e530  push    rdi
0x18003e531  push    r12
0x18003e533  push    r14
0x18003e535  push    r15
0x18003e537  lea     rbp, [rsp-1F0h]
0x18003e53f  sub     rsp, 300h
0x18003e546  mov     rax, cs:__security_cookie
0x18003e54d  xor     rax, rsp
0x18003e550  mov     [rbp+220h+var_40], rax
0x18003e557  mov     r14d, r9d
0x18003e55a  mov     rbx, r8
0x18003e55d  mov     rdi, rcx
0x18003e560  mov     [rbp+220h+var_270], rdx
0x18003e564  mov     [rbp+220h+var_268], rbx
0x18003e568  mov     rcx, rdx
0x18003e56b  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18003e570  mov     r15, rax
0x18003e573  mov     [rbp+220h+var_270], rax
0x18003e577  mov     rcx, rbx
0x18003e57a  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18003e57f  mov     r12, rax
0x18003e582  mov     [rbp+220h+var_268], rax
0x18003e586  xor     edx, edx; Val
0x18003e588  mov     r8d, 150h; Size
0x18003e58e  lea     rcx, [rbp+220h+var_190]; void *
0x18003e595  call    memset_0
0x18003e59a  nop
0x18003e59b  lea     rdx, aCsgsuggesterGe; "CSGSuggester_GetEntitiesAsJson"
0x18003e5a2  lea     rcx, [rbp+220h+var_190]; struct wil::details::IFailureCallback *
0x18003e5a9  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$0A@$0A@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003e5ae  lea     rax, ??_7CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@6B@; const Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::`vftable'
0x18003e5b5  mov     [rbp+220h+var_190], rax
0x18003e5bc  mov     r9d, r14d
0x18003e5bf  mov     r8, r12
0x18003e5c2  mov     rdx, r15
0x18003e5c5  lea     rcx, [rbp+220h+var_190]
0x18003e5cc  call    ?StartActivity@CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@QEAAXPE$AAVString@Platform@@0H@Z; Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::StartActivity(Platform::String *,Platform::String *,int)
0x18003e5d1  nop
0x18003e5d2  xor     edx, edx; Val
0x18003e5d4  lea     r8d, [rdx+78h]; Size
0x18003e5d8  lea     rcx, [rbp+220h+var_210]; void *
0x18003e5dc  call    memset_0
0x18003e5e1  lea     rcx, [rbp+220h+var_210]
0x18003e5e5  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(void)
0x18003e5ea  nop
0x18003e5eb  xor     edx, edx; length
0x18003e5ed  mov     rcx, r15; string
0x18003e5f0  call    WindowsGetStringRawBuffer_0
0x18003e5f5  mov     r8, rax
0x18003e5f8  lea     rdx, [rbp+220h+var_230]
0x18003e5fc  lea     rcx, [rbp+220h+var_210]
0x18003e600  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEB_W@Z; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(wchar_t const *)
0x18003e605  nop
0x18003e606  xor     edx, edx; length
0x18003e608  mov     rcx, r12; string
0x18003e60b  call    WindowsGetStringRawBuffer_0
0x18003e610  mov     r8, rax
0x18003e613  lea     rdx, [rbp+220h+var_250]
0x18003e617  lea     rcx, [rbp+220h+var_210]
0x18003e61b  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEB_W@Z; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(wchar_t const *)
0x18003e620  nop
0x18003e621  xor     sil, sil
0x18003e624  mov     byte ptr [rbp+220h+var_2A0], sil
0x18003e628  mov     [rbp+220h+var_298], 0
0x18003e630  xor     ebx, ebx
0x18003e632  mov     [rbp+220h+var_258], rbx
0x18003e636  cmp     [rdi+20h], rbx
0x18003e63a  jz      loc_18003E6CB
0x18003e640  movzx   r9d, [rbp+220h+arg_20]
0x18003e648  lea     rcx, [rbp+220h+var_250]
0x18003e64c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003e651  mov     r8, rax
0x18003e654  lea     rcx, [rbp+220h+var_230]
0x18003e658  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003e65d  mov     rdx, rax
0x18003e660  lea     rax, [rbp+220h+var_2A0]
0x18003e664  mov     [rsp+330h+var_2B0], rax
0x18003e66c  mov     [rsp+330h+var_2B8], r14d
0x18003e671  mov     [rsp+330h+var_2C0], 0Ah
0x18003e679  mov     [rsp+330h+var_2C8], r14d
0x18003e67e  lea     eax, [rbx+1]
0x18003e681  mov     [rsp+330h+var_2D0], eax
0x18003e685  mov     [rsp+330h+var_2D8], ebx
0x18003e689  mov     [rsp+330h+var_2E0], r9d
0x18003e68e  mov     [rsp+330h+var_2E8], eax
0x18003e692  mov     [rsp+330h+var_2F0], eax
0x18003e696  mov     [rsp+330h+var_2F8], ebx
0x18003e69a  mov     [rsp+330h+var_300], eax
0x18003e69e  mov     dword ptr [rsp+330h+cchWideChar], eax
0x18003e6a2  lea     rax, asc_1801017B4; "*"
0x18003e6a9  mov     [rsp+330h+lpWideCharStr], rax
0x18003e6ae  lea     r9, word_1801017B2
0x18003e6b5  mov     rcx, [rdi+20h]
0x18003e6b9  call    GetEntitySuggestions
0x18003e6be  mov     rbx, rax
0x18003e6c1  mov     [rbp+220h+var_258], rax
0x18003e6c5  mov     sil, byte ptr [rbp+220h+var_2A0]
0x18003e6c9  jmp     short loc_18003E6F7
0x18003e6cb  mov     rcx, [rbp+228h]; this
0x18003e6d2  lea     rax, aConstraintInde_0; "Constraint Index is not ready"
0x18003e6d9  mov     [rsp+330h+lpWideCharStr], rax; int
0x18003e6de  mov     r9d, 80004005h; char *
0x18003e6e4  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\cortana\\constraint"...
0x18003e6eb  mov     edx, 86h; void *
0x18003e6f0  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e6f5  xor     eax, eax
0x18003e6f7  test    sil, sil
0x18003e6fa  jnz     loc_18003E8BF
0x18003e700  xor     esi, esi
0x18003e702  mov     [rbp+220h+var_290], rsi
0x18003e706  test    rax, rax
0x18003e709  jz      loc_18003E7E1
0x18003e70f  mov     dword ptr [rsp+330h+cchWideChar], esi; cchWideChar
0x18003e713  mov     [rsp+330h+lpWideCharStr], rsi; lpWideCharStr
0x18003e718  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003e71c  mov     r9d, r14d; cbMultiByte
0x18003e71f  mov     r8, rbx; lpMultiByteStr
0x18003e722  xor     edx, edx; dwFlags
0x18003e724  mov     ecx, 0FDE9h; CodePage
0x18003e729  call    cs:__imp_MultiByteToWideChar
0x18003e72f  movsxd  rdi, eax
0x18003e732  test    eax, eax
0x18003e734  jle     loc_18003E7C4
0x18003e73a  lea     eax, [rsi+2]
0x18003e73d  mul     rdi
0x18003e740  cmovb   rax, r14
0x18003e744  mov     rcx, rax; unsigned __int64
0x18003e747  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003e74c  mov     r14, rax
0x18003e74f  mov     [rbp+220h+var_260], rax
0x18003e753  mov     dword ptr [rsp+330h+cchWideChar], edi; cchWideChar
0x18003e757  mov     [rsp+330h+lpWideCharStr], rax; lpWideCharStr
0x18003e75c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003e760  mov     r8, rbx; lpMultiByteStr
0x18003e763  xor     edx, edx; dwFlags
0x18003e765  mov     ecx, 0FDE9h; CodePage
0x18003e76a  call    cs:__imp_MultiByteToWideChar
0x18003e770  test    eax, eax
0x18003e772  jle     short loc_18003E7A4
0x18003e774  xor     edi, edi
0x18003e776  mov     [rbp+220h+var_2A0], rdi
0x18003e77a  mov     rdx, r14
0x18003e77d  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x18003e782  mov     rbx, rax
0x18003e785  mov     [rbp+220h+var_2A0], rax
0x18003e789  mov     rdx, rax
0x18003e78c  lea     rcx, [rbp+220h+var_290]
0x18003e790  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x18003e795  nop
0x18003e796  mov     rcx, rbx; string
0x18003e799  call    WindowsDeleteString_0
0x18003e79e  mov     rsi, [rbp+220h+var_290]
0x18003e7a2  jmp     short loc_18003E7B9
0x18003e7a4  call    cs:__imp_GetLastError
0x18003e7aa  mov     edi, eax
0x18003e7ac  test    eax, eax
0x18003e7ae  jle     short loc_18003E7B9
0x18003e7b0  movzx   edi, ax
0x18003e7b3  or      edi, 80070000h
0x18003e7b9  lea     rcx, [rbp+220h+var_260]
0x18003e7bd  call    ??1?$unique_ptr@$$BY0A@$$CBDU?$default_delete@$$BY0A@$$CBD@std@@@std@@QEAA@XZ; std::unique_ptr<char const [0]>::~unique_ptr<char const [0]>(void)
0x18003e7c2  jmp     short loc_18003E7D9
0x18003e7c4  call    cs:__imp_GetLastError
0x18003e7ca  mov     edi, eax
0x18003e7cc  test    eax, eax
0x18003e7ce  jle     short loc_18003E7D9
0x18003e7d0  movzx   edi, ax
0x18003e7d3  or      edi, 80070000h
0x18003e7d9  test    edi, edi
0x18003e7db  jnz     loc_18003E86E
0x18003e7e1  mov     rdx, rsi
0x18003e7e4  lea     rcx, [rbp+220h+var_190]
0x18003e7eb  call    ?Stop@CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@QEAAXPE$AAVString@Platform@@@Z; Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::Stop(Platform::String *)
0x18003e7f0  mov     rcx, rsi
0x18003e7f3  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18003e7f8  mov     rbx, rax
0x18003e7fb  mov     rcx, rsi; string
0x18003e7fe  call    WindowsDeleteString_0
0x18003e803  nop
0x18003e804  lea     rcx, [rbp+220h+var_258]
0x18003e808  call    ??1?$unique_ptr@$$BY0A@$$CBDU?$default_delete@$$BY0A@$$CBD@std@@@std@@QEAA@XZ; std::unique_ptr<char const [0]>::~unique_ptr<char const [0]>(void)
0x18003e80d  nop
0x18003e80e  lea     rcx, [rbp+220h+var_250]
0x18003e812  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003e817  nop
0x18003e818  lea     rcx, [rbp+220h+var_230]
0x18003e81c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003e821  nop
0x18003e822  lea     rcx, [rbp+220h+var_210]
0x18003e826  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(void)
0x18003e82b  nop
0x18003e82c  lea     rcx, [rbp+220h+var_190]; this
0x18003e833  call    ??1CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@QEAA@XZ; Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::~CSGSuggester_GetEntitiesAsJson(void)
0x18003e838  nop
0x18003e839  mov     rcx, r15; string
0x18003e83c  call    WindowsDeleteString_0
0x18003e841  nop
0x18003e842  mov     rcx, r12; string
0x18003e845  call    WindowsDeleteString_0
0x18003e84a  mov     rax, rbx
0x18003e84d  mov     rcx, [rbp+220h+var_40]
0x18003e854  xor     rcx, rsp; StackCookie
0x18003e857  call    __security_check_cookie
0x18003e85c  add     rsp, 300h
0x18003e863  pop     r15
0x18003e865  pop     r14
0x18003e867  pop     r12
0x18003e869  pop     rdi
0x18003e86a  pop     rsi
0x18003e86b  pop     rbx
0x18003e86c  pop     rbp
0x18003e86d  retn
0x18003e86e  mov     edx, 80h
0x18003e873  lea     ecx, [rdx-18h]
0x18003e876  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x18003e87c  mov     rbx, rax
0x18003e87f  mov     [rbp+220h+var_2A0], rax
0x18003e883  lea     r8, [rbp+220h+var_288]
0x18003e887  mov     edx, 29h ; ')'
0x18003e88c  lea     rcx, aErrorWhileConv; "Error while converting from utf8 to utf"...
0x18003e893  call    ?__abi_winrt_CreateFastPassSystemStringFromLiteral@@YAPE$AAVString@Platform@@PEB_WIPEAU__Platform_Details_HSTRING_HEADER@@@Z; __abi_winrt_CreateFastPassSystemStringFromLiteral(wchar_t const *,uint,__Platform_Details_HSTRING_HEADER *)
0x18003e898  mov     r8, rax
0x18003e89b  mov     edx, edi
0x18003e89d  mov     rcx, rbx
0x18003e8a0  call    cs:__imp_??0Exception@Platform@@QE$AAA@HPE$AAVString@1@@Z; Platform::Exception::Exception(int,Platform::String *)
0x18003e8a6  mov     [rbp+220h+var_2A0], rax
0x18003e8aa  mov     rcx, [rbp+228h]
0x18003e8b1  mov     r9, rax
0x18003e8b4  mov     edx, 0A6h
0x18003e8b9  call    ??$ReportFailure_CustomException@PE$AAVException@Platform@@@details@wil@@YAXPEAXIPEBDPE$AAVException@Platform@@@Z; wil::details::ReportFailure_CustomException<Platform::Exception *>(void *,uint,char const *,Platform::Exception *)
0x18003e8bf  mov     edx, 80h
0x18003e8c4  lea     ecx, [rdx-18h]
0x18003e8c7  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x18003e8cd  mov     rbx, rax
0x18003e8d0  mov     [rbp+220h+var_260], rax
0x18003e8d4  lea     rcx, [rbp+220h+var_2A0]
0x18003e8d8  call    ?GetNativeErrorMessage@CSGSuggestion@ConstraintIndex@Cortana@@YAPE$AAVString@Platform@@AEBUNativeError@@@Z; Cortana::ConstraintIndex::CSGSuggestion::GetNativeErrorMessage(NativeError const &)
0x18003e8dd  mov     [rbp+220h+var_290], rax
0x18003e8e1  mov     r8, rax
0x18003e8e4  mov     edx, 80004005h
0x18003e8e9  mov     rcx, rbx
0x18003e8ec  call    cs:__imp_??0Exception@Platform@@QE$AAA@HPE$AAVString@1@@Z; Platform::Exception::Exception(int,Platform::String *)
0x18003e8f2  mov     [rbp+220h+var_260], rax
0x18003e8f6  mov     rcx, [rbp+228h]
0x18003e8fd  mov     r9, rax
0x18003e900  mov     edx, 89h
0x18003e905  call    ??$ReportFailure_CustomException@PE$AAVException@Platform@@@details@wil@@YAXPEAXIPEBDPE$AAVException@Platform@@@Z; wil::details::ReportFailure_CustomException<Platform::Exception *>(void *,uint,char const *,Platform::Exception *)
```

# _lambda_c61c46c46e349cd54943a680c14dff16_::operator()

- ea: `0x18003c6ac`
- end: `0x18003ca5b`
- name: `_lambda_c61c46c46e349cd54943a680c14dff16_::operator()`
- size: `943`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b9c8`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18003286c`
- `0x1800335a4`
- `0x180034e30`
- `0x1800352e8`
- `0x18003b8b0`
- `0x18003c6ac`
- `0x18003f218`
- `0x18003f670`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003c7ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003c7ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c953`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c6ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c962`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c9b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ca2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c6ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c962`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c9b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ca2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c899`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c938`

## string_xrefs

- `0x18003c74d`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003c861`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003c9a3`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003c9e3`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall lambda_c61c46c46e349cd54943a680c14dff16_::operator()(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rdi
  int *v5; // rbx
  int *v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v10; // rax
  const WCHAR *v11; // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, _QWORD, char *); // r15
  unsigned int v14; // esi
  unsigned __int64 v15; // rcx
  int *v16; // rbx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64); // rbx
  __int64 v18; // rdx
  const char *v19; // r15
  HSTRING *v20; // rsi
  int v21; // ecx
  HSTRING v22; // rsi
  __int64 (__fastcall *v23)(HSTRING, HSTRING *); // rdi
  int *v24; // rbx
  const WCHAR *v25; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-59h]
  char v28[4]; // [rsp+30h] [rbp-49h] BYREF
  UINT32 length; // [rsp+34h] [rbp-45h] BYREF
  char *v30; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v31; // [rsp+40h] [rbp-39h] BYREF
  __int64 v32; // [rsp+48h] [rbp-31h] BYREF
  UINT32 v33; // [rsp+50h] [rbp-29h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-21h] BYREF
  HSTRING string; // [rsp+60h] [rbp-19h] BYREF
  HSTRING *v36; // [rsp+68h] [rbp-11h] BYREF
  int v37; // [rsp+70h] [rbp-9h]
  const char *v38; // [rsp+78h] [rbp-1h] BYREF
  HSTRING v39; // [rsp+80h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = *(int **)a1;
  *v5 = v4(a2, &string);
  v6 = *(int **)a1;
  v7 = **(_DWORD **)a1;
  if ( v7 < 0 )
  {
    v8 = 506;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    goto LABEL_31;
  }
  LODWORD(v30) = 0;
  *v6 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)a2 + 56LL))(a2, &v30);
  v7 = **(_DWORD **)a1;
  if ( v7 < 0 )
  {
    v8 = 510;
    goto LABEL_5;
  }
  v28[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v10 = AttributeFetcher::ParseNamespace(StringRawBuffer, 0);
  v11 = v10;
  v12 = **(_QWORD **)(a1 + 8);
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, char *))(*(_QWORD *)v12 + 80LL);
  v14 = (unsigned int)v30;
  length = 0;
  v15 = -1;
  do
    ++v15;
  while ( v10[v15] );
  if ( (int)ULongLongToUInt(v15, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(v11, length, &hstringHeader, &v39);
  v16 = *(int **)a1;
  *v16 = v13(v12, v39, v14, v28);
  v7 = **(_DWORD **)a1;
  if ( v7 < 0 )
  {
    v8 = 519;
    goto LABEL_5;
  }
  if ( v28[0] )
  {
LABEL_30:
    v7 = 0;
    goto LABEL_31;
  }
  v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 128LL);
  v34 = v17;
  if ( !v17 )
  {
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    goto LABEL_30;
  }
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v17)[1])(v17);
  v32 = 0;
  **(_DWORD **)a1 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(
                      &v34,
                      (__int64)&v32);
  v7 = **(_DWORD **)a1;
  if ( v7 >= 0 )
  {
    v33 = 0;
    v19 = (const char *)WindowsGetStringRawBuffer(string, &v33);
    v38 = v19;
    wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>((__int64)&v39);
    v20 = &v39;
    v36 = &v39;
    v21 = (v39 != 0) - 1;
    v37 = v21;
    while ( *(_DWORD *)v20[2] >= 0 && v21 != -1 )
    {
      v31 = 0;
      v22 = v20[1];
      v23 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v22 + 64LL);
      WindowsDeleteString(0);
      v31 = 0;
      v24 = *(int **)a1;
      *v24 = v23(v22, &v31);
      v7 = **(_DWORD **)a1;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21E,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v7,
          bIgnoreCase);
        WindowsDeleteString(v31);
        v31 = 0;
        wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(&v39);
        goto LABEL_17;
      }
      length = 0;
      v25 = WindowsGetStringRawBuffer(v31, &length);
      if ( CompareStringOrdinal((LPCWCH)v19, v33, v25, length, 1) == 2 )
      {
        CtacTelemetry::RequiredClientAttrError<unsigned short const * &,int &>(&v38, &v30);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x226,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v30,
          (int)"Required attribute (%ws) failed!",
          v19);
        WindowsDeleteString(v31);
        break;
      }
      WindowsDeleteString(v31);
      wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(&v36);
      v21 = v37;
      v20 = v36;
    }
    wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(&v39);
    v7 = **(_DWORD **)a1;
    if ( v7 < 0 )
    {
      v18 = 554;
      goto LABEL_16;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    goto LABEL_29;
  }
  v18 = 532;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
    (const char *)(unsigned int)v7,
    bIgnoreCase);
LABEL_17:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
LABEL_31:
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003c6ac  mov     [rsp-8+arg_10], rbx
0x18003c6b1  mov     [rsp-8+arg_18], rsi
0x18003c6b6  push    rbp
0x18003c6b7  push    rdi
0x18003c6b8  push    r12
0x18003c6ba  push    r14
0x18003c6bc  push    r15
0x18003c6be  lea     rbp, [rsp-37h]
0x18003c6c3  sub     rsp, 0B0h
0x18003c6ca  mov     rax, cs:__security_cookie
0x18003c6d1  xor     rax, rsp
0x18003c6d4  mov     [rbp+57h+var_30], rax
0x18003c6d8  mov     rsi, rdx
0x18003c6db  mov     r14, rcx
0x18003c6de  xor     r12d, r12d
0x18003c6e1  mov     [rbp+57h+string], r12
0x18003c6e5  mov     rax, [rdx]
0x18003c6e8  mov     rdi, [rax+30h]
0x18003c6ec  xor     ecx, ecx; string
0x18003c6ee  call    cs:__imp_WindowsDeleteString
0x18003c6f4  mov     [rbp+57h+string], r12
0x18003c6f8  mov     rbx, [r14]
0x18003c6fb  lea     rdx, [rbp+57h+string]
0x18003c6ff  mov     rcx, rsi
0x18003c702  mov     rax, rdi
0x18003c705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c70a  mov     [rbx], eax
0x18003c70c  mov     rax, [r14]
0x18003c70f  mov     ebx, [rax]
0x18003c711  test    ebx, ebx
0x18003c713  jns     short loc_18003C71C
0x18003c715  mov     edx, 1FAh
0x18003c71a  jmp     short loc_18003C746
0x18003c71c  mov     dword ptr [rbp+57h+var_98], r12d
0x18003c720  mov     rbx, rax
0x18003c723  mov     rax, [rsi]
0x18003c726  lea     rdx, [rbp+57h+var_98]
0x18003c72a  mov     rcx, rsi
0x18003c72d  mov     rax, [rax+38h]
0x18003c731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c736  mov     [rbx], eax
0x18003c738  mov     rax, [r14]
0x18003c73b  mov     ebx, [rax]
0x18003c73d  test    ebx, ebx
0x18003c73f  jns     short loc_18003C75E
0x18003c741  mov     edx, 1FEh; void *
0x18003c746  mov     rcx, [rbp+5Fh]; this
0x18003c74a  mov     r9d, ebx; char *
0x18003c74d  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003c754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c759  jmp     loc_18003CA27
0x18003c75e  mov     [rbp+57h+var_A0], r12b
0x18003c762  xor     edx, edx; length
0x18003c764  mov     rcx, [rbp+57h+string]; string
0x18003c768  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c76e  xor     edx, edx; unsigned __int16 *
0x18003c770  mov     rcx, rax; unsigned __int16 *
0x18003c773  call    ?ParseNamespace@AttributeFetcher@@CAPEBGPEBGPEAG@Z; AttributeFetcher::ParseNamespace(ushort const *,ushort *)
0x18003c778  mov     rbx, rax
0x18003c77b  mov     rcx, [r14+8]
0x18003c77f  mov     rdi, [rcx]
0x18003c782  mov     rcx, [rdi]
0x18003c785  mov     r15, [rcx+50h]
0x18003c789  mov     esi, dword ptr [rbp+57h+var_98]
0x18003c78c  mov     [rbp+57h+length], r12d
0x18003c790  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003c794  inc     rcx; unsigned __int64
0x18003c797  cmp     [rax+rcx*2], r12w
0x18003c79c  jnz     short loc_18003C794
0x18003c79e  lea     rdx, [rbp+57h+length]; unsigned int *
0x18003c7a2  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003c7a7  test    eax, eax
0x18003c7a9  jns     short loc_18003C7C0
0x18003c7ab  xor     r9d, r9d; lpArguments
0x18003c7ae  xor     r8d, r8d; nNumberOfArguments
0x18003c7b1  lea     edx, [r9+1]; dwExceptionFlags
0x18003c7b5  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003c7ba  call    cs:__imp_RaiseException
0x18003c7c0  lea     r9, [rbp+57h+var_50]; string
0x18003c7c4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003c7c8  mov     edx, [rbp+57h+length]; length
0x18003c7cb  mov     rcx, rbx; sourceString
0x18003c7ce  call    cs:__imp_WindowsCreateStringReference
0x18003c7d4  mov     rbx, [r14]
0x18003c7d7  lea     r9, [rbp+57h+var_A0]
0x18003c7db  mov     r8d, esi
0x18003c7de  mov     rdx, [rbp+57h+var_50]
0x18003c7e2  mov     rcx, rdi
0x18003c7e5  mov     rax, r15
0x18003c7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7ed  mov     [rbx], eax
0x18003c7ef  mov     rax, [r14]
0x18003c7f2  mov     ebx, [rax]
0x18003c7f4  test    ebx, ebx
0x18003c7f6  jns     short loc_18003C802
0x18003c7f8  mov     edx, 207h
0x18003c7fd  jmp     loc_18003C746
0x18003c802  cmp     [rbp+57h+var_A0], r12b
0x18003c806  jnz     loc_18003CA24
0x18003c80c  mov     rax, [r14+10h]
0x18003c810  mov     rbx, [rax+10h]
0x18003c814  mov     rbx, [rbx+80h]
0x18003c81b  mov     [rbp+57h+var_78], rbx
0x18003c81f  test    rbx, rbx
0x18003c822  jz      short loc_18003C834
0x18003c824  mov     rax, [rbx]
0x18003c827  mov     rcx, rbx
0x18003c82a  mov     rax, [rax+8]
0x18003c82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c833  nop
0x18003c834  test    rbx, rbx
0x18003c837  jz      loc_18003CA1B
0x18003c83d  mov     [rbp+57h+var_88], r12
0x18003c841  lea     rdx, [rbp+57h+var_88]
0x18003c845  lea     rcx, [rbp+57h+var_78]
0x18003c849  call    ??$As@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *>>>)
0x18003c84e  mov     rcx, [r14]
0x18003c851  mov     [rcx], eax
0x18003c853  mov     rax, [r14]
0x18003c856  mov     ebx, [rax]
0x18003c858  test    ebx, ebx
0x18003c85a  jns     short loc_18003C88D
0x18003c85c  mov     edx, 214h; void *
0x18003c861  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003c868  mov     r9d, ebx; char *
0x18003c86b  mov     rcx, [rbp+5Fh]; this
0x18003c86f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c874  nop
0x18003c875  lea     rcx, [rbp+57h+var_88]
0x18003c879  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c87e  nop
0x18003c87f  lea     rcx, [rbp+57h+var_78]
0x18003c883  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c888  jmp     loc_18003CA27
0x18003c88d  mov     [rbp+57h+var_80], r12d
0x18003c891  lea     rdx, [rbp+57h+var_80]; length
0x18003c895  mov     rcx, [rbp+57h+string]; string
0x18003c899  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c89f  mov     r15, rax
0x18003c8a2  mov     [rbp+57h+var_58], rax
0x18003c8a6  mov     r8, [r14]
0x18003c8a9  mov     rdx, [rbp+57h+var_88]
0x18003c8ad  lea     rcx, [rbp+57h+var_50]
0x18003c8b1  call    ??$GetRangeNoThrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@YA?AV?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@0@PEAU?$IIterable@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Data::Json::IJsonValue *>(Windows::Foundation::Collections::IIterable<Windows::Data::Json::IJsonValue *> *,long *)
0x18003c8b6  nop
0x18003c8b7  mov     rcx, [rbp+57h+var_50]
0x18003c8bb  neg     rcx
0x18003c8be  sbb     edx, edx
0x18003c8c0  neg     edx
0x18003c8c2  dec     edx
0x18003c8c4  lea     rsi, [rbp+57h+var_50]
0x18003c8c8  mov     [rbp+57h+var_68], rsi
0x18003c8cc  mov     ecx, r12d
0x18003c8cf  cmp     edx, 0FFFFFFFFh
0x18003c8d2  setnz   cl
0x18003c8d5  dec     ecx
0x18003c8d7  mov     [rbp+57h+var_60], ecx
0x18003c8da  mov     rax, [rsi+10h]
0x18003c8de  cmp     [rax], r12d
0x18003c8e1  jl      loc_18003C9C0
0x18003c8e7  cmp     ecx, 0FFFFFFFFh
0x18003c8ea  jz      loc_18003C9C0
0x18003c8f0  mov     [rbp+57h+var_90], r12
0x18003c8f4  mov     rsi, [rsi+8]
0x18003c8f8  mov     rax, [rsi]
0x18003c8fb  mov     rdi, [rax+40h]
0x18003c8ff  xor     ecx, ecx; string
0x18003c901  call    cs:__imp_WindowsDeleteString
0x18003c907  mov     [rbp+57h+var_90], r12
0x18003c90b  mov     rbx, [r14]
0x18003c90e  lea     rdx, [rbp+57h+var_90]
0x18003c912  mov     rcx, rsi
0x18003c915  mov     rax, rdi
0x18003c918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c91d  mov     [rbx], eax
0x18003c91f  mov     rax, [r14]
0x18003c922  mov     ebx, [rax]
0x18003c924  test    ebx, ebx
0x18003c926  js      loc_18003C9DC
0x18003c92c  mov     [rbp+57h+length], r12d
0x18003c930  lea     rdx, [rbp+57h+length]; length
0x18003c934  mov     rcx, [rbp+57h+var_90]; string
0x18003c938  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c93e  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18003c946  mov     r9d, [rbp+57h+length]; cchCount2
0x18003c94a  mov     r8, rax; lpString2
0x18003c94d  mov     edx, [rbp+57h+var_80]; cchCount1
0x18003c950  mov     rcx, r15; lpString1
0x18003c953  call    cs:__imp_CompareStringOrdinal
0x18003c959  cmp     eax, 2
0x18003c95c  jz      short loc_18003C97D
0x18003c95e  mov     rcx, [rbp+57h+var_90]; string
0x18003c962  call    cs:__imp_WindowsDeleteString
0x18003c968  lea     rcx, [rbp+57h+var_68]
0x18003c96c  call    ??Eiterable_iterator_nothrow@?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAAAEAV012@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::iterable_iterator_nothrow::operator++(void)
0x18003c971  mov     ecx, [rbp+57h+var_60]
0x18003c974  mov     rsi, [rbp+57h+var_68]
0x18003c978  jmp     loc_18003C8DA
0x18003c97d  lea     rdx, [rbp+57h+var_98]
0x18003c981  lea     rcx, [rbp+57h+var_58]
0x18003c985  call    ??$RequiredClientAttrError@AEAPEBGAEAH@CtacTelemetry@@SAXAEAPEBGAEAH@Z; CtacTelemetry::RequiredClientAttrError<ushort const * &,int &>(ushort const * &,int &)
0x18003c98a  mov     rcx, [rbp+5Fh]; this
0x18003c98e  mov     [rsp+0D0h+var_A8], r15; char *
0x18003c993  lea     rax, aRequiredAttrib; "Required attribute (%ws) failed!"
0x18003c99a  mov     qword ptr [rsp+0D0h+bIgnoreCase], rax; int
0x18003c99f  mov     r9d, dword ptr [rbp+57h+var_98]; char *
0x18003c9a3  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003c9aa  mov     edx, 226h; void *
0x18003c9af  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c9b4  nop
0x18003c9b5  mov     rcx, [rbp+57h+var_90]; string
0x18003c9b9  call    cs:__imp_WindowsDeleteString
0x18003c9bf  nop
0x18003c9c0  lea     rcx, [rbp+57h+var_50]
0x18003c9c4  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x18003c9c9  mov     rax, [r14]
0x18003c9cc  mov     ebx, [rax]
0x18003c9ce  test    ebx, ebx
0x18003c9d0  jns     short loc_18003CA11
0x18003c9d2  mov     edx, 22Ah
0x18003c9d7  jmp     loc_18003C861
0x18003c9dc  mov     rcx, [rbp+5Fh]; this
0x18003c9e0  mov     r9d, ebx; char *
0x18003c9e3  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003c9ea  mov     edx, 21Eh; void *
0x18003c9ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c9f4  nop
0x18003c9f5  mov     rcx, [rbp+57h+var_90]; string
0x18003c9f9  call    cs:__imp_WindowsDeleteString
0x18003c9ff  mov     [rbp+57h+var_90], r12
0x18003ca03  lea     rcx, [rbp+57h+var_50]
0x18003ca07  call    ??1?$iterable_range_nothrow@PEAUIJsonValue@Json@Data@Windows@@@wil@@QEAA@XZ; wil::iterable_range_nothrow<Windows::Data::Json::IJsonValue *>::~iterable_range_nothrow<Windows::Data::Json::IJsonValue *>(void)
0x18003ca0c  jmp     loc_18003C875
0x18003ca11  lea     rcx, [rbp+57h+var_88]
0x18003ca15  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003ca1a  nop
0x18003ca1b  lea     rcx, [rbp+57h+var_78]
0x18003ca1f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003ca24  mov     ebx, r12d
0x18003ca27  mov     rcx, [rbp+57h+string]; string
0x18003ca2b  call    cs:__imp_WindowsDeleteString
0x18003ca31  mov     eax, ebx
0x18003ca33  mov     rcx, [rbp+57h+var_30]
0x18003ca37  xor     rcx, rsp; StackCookie
0x18003ca3a  call    __security_check_cookie
0x18003ca3f  lea     r11, [rsp+0D0h+var_20]
0x18003ca47  mov     rbx, [r11+40h]
0x18003ca4b  mov     rsi, [r11+48h]
0x18003ca4f  mov     rsp, r11
0x18003ca52  pop     r15
0x18003ca54  pop     r14
0x18003ca56  pop     r12
0x18003ca58  pop     rdi
0x18003ca59  pop     rbp
0x18003ca5a  retn
```

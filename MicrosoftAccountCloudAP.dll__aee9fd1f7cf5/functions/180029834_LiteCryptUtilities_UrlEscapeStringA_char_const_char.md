# LiteCryptUtilities::UrlEscapeStringA(char const *,char * *)

- ea: `0x180029834`
- end: `0x180029be3`
- name: `?UrlEscapeStringA@LiteCryptUtilities@@YAJPEBDPEAPEAD@Z`
- size: `943`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, const char *, char **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180028a10`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000def8`
- `0x18000e08c`
- `0x18001200c`
- `0x180023b5c`
- `0x180023c04`
- `0x180026c8c`
- `0x180029834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b20`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180029a80`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180029b16`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180029a80`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180029b16`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180029915`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800299aa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180029915`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800299aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800299f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029ac5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800299f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029ac5`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180029a37`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x180029a37`

## string_xrefs

- `0x180029a44`: `hr = UrlEscapeW(spInputWideCharBuffer, spEscapedWideCharBuffer, &escapedWideCharBufferLength, URL_ESCAPE_PERCENT|URL_ESCAPE_ASCII_URI_COMPONENT|URL_ESCAPE_AS_UTF8|URL_ESCAPE_SEGMENT_ONLY )`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LiteCryptUtilities::UrlEscapeStringA(LPCCH lpMultiByteStr, char *a2, char **a3)
{
  int v5; // eax
  __int64 cchWideChar; // rdi
  signed int LastError; // eax
  WCHAR *v8; // rsi
  int v9; // r9d
  const char *v10; // rax
  char v11; // r8
  signed int v12; // eax
  WCHAR *v13; // rdi
  HRESULT v14; // eax
  int v15; // eax
  SIZE_T v16; // rsi
  signed int v17; // eax
  CHAR *v18; // rbx
  signed int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rdx
  int v22; // r8d
  const unsigned __int16 *lpWideCharStr; // [rsp+20h] [rbp-89h]
  CHAR *v25; // [rsp+40h] [rbp-69h] BYREF
  __int64 v26; // [rsp+48h] [rbp-61h]
  __int64 v27; // [rsp+50h] [rbp-59h]
  _QWORD v28[3]; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v29[3]; // [rsp+70h] [rbp-39h] BYREF
  int *v30[4]; // [rsp+88h] [rbp-21h] BYREF
  _QWORD v31[11]; // [rsp+A8h] [rbp-1h] BYREF
  int v32; // [rsp+118h] [rbp+6Fh] BYREF
  DWORD pcchEscaped; // [rsp+120h] [rbp+77h] BYREF

  v32 = 0;
  memset(v29, 0, sizeof(v29));
  memset(v28, 0, sizeof(v28));
  v25 = 0;
  v27 = 0;
  v26 = 0;
  pcchEscaped = 2084;
  v31[0] = "LiteCryptUtilities::UrlEscapeStringA";
  v31[1] = &v32;
  v31[2] = 0;
  v31[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::UrlEscapeStringA",
    (const char *)0x8C,
    0,
    lpWideCharStr);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v30, "LiteCryptUtilities::UrlEscapeStringA", &v32, 11, &qword_180041D90);
  if ( !a2 || !lpMultiByteStr || !*lpMultiByteStr )
  {
    v9 = -2147024809;
    v10 = "hr = E_INVALIDARG";
    v11 = -104;
    goto LABEL_34;
  }
  *(_QWORD *)a2 = 0;
  v5 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v32 = LastError;
    if ( LastError < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::UrlEscapeStringA",
        169,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
      goto LABEL_35;
    }
  }
  v8 = (WCHAR *)LocalAlloc(0x40u, 2 * cchWideChar);
  Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)v29);
  v29[0] = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    v10 = "hr = E_OUTOFMEMORY";
    v11 = -81;
LABEL_34:
    v32 = v9;
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::UrlEscapeStringA",
      v11,
      v9,
      v10);
    goto LABEL_35;
  }
  if ( !MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, v8, cchWideChar) )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v32 = v12;
    if ( v12 < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::UrlEscapeStringA",
        185,
        v12,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
      goto LABEL_35;
    }
  }
  v13 = (WCHAR *)LocalAlloc(0x40u, 2LL * pcchEscaped);
  Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)v28);
  v28[0] = v13;
  if ( !v13 )
  {
    v9 = -2147024882;
    v10 = "hr=E_OUTOFMEMORY";
    v11 = -62;
    goto LABEL_34;
  }
  v14 = UrlEscapeW(v8, v13, &pcchEscaped, 0xC3000u);
  v32 = v14;
  if ( v14 < 0 )
  {
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::UrlEscapeStringA",
      207,
      v14,
      "hr = UrlEscapeW(spInputWideCharBuffer, spEscapedWideCharBuffer, &escapedWideCharBufferLength, URL_ESCAPE_PERCENT|U"
      "RL_ESCAPE_ASCII_URI_COMPONENT|URL_ESCAPE_AS_UTF8|URL_ESCAPE_SEGMENT_ONLY )");
    goto LABEL_35;
  }
  v15 = WideCharToMultiByte(0xFDE9u, 0, v13, -1, 0, 0, 0, 0);
  v16 = v15;
  if ( !v15 )
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    v32 = v17;
    if ( v17 < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::UrlEscapeStringA",
        223,
        v17,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
      goto LABEL_35;
    }
  }
  v18 = (CHAR *)LocalAlloc(0x40u, v16);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v25);
  v25 = v18;
  if ( !v18 )
  {
    v9 = -2147024882;
    v10 = "hr = E_OUTOFMEMORY";
    v11 = -27;
    goto LABEL_34;
  }
  if ( WideCharToMultiByte(0xFDE9u, 0, v13, -1, v18, v16, 0, 0) )
    goto LABEL_32;
  v19 = GetLastError();
  if ( v19 > 0 )
    v19 = (unsigned __int16)v19 | 0x80070000;
  v32 = v19;
  if ( v19 >= 0 )
  {
LABEL_32:
    v25 = 0;
    v26 = 0;
    *(_QWORD *)a2 = v18;
  }
  else
  {
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::UrlEscapeStringA",
      241,
      v19,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
LABEL_35:
  v20 = v32;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v30[3], *v30[2], (unsigned __int64)v30[1], v30[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v31, v21, v22);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)&v25);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v28);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v29);
  return v20;
}

```

## disassembly

```asm
0x180029834  mov     [rsp-8+arg_0], rbx
0x180029839  push    rbp
0x18002983a  push    rsi
0x18002983b  push    rdi
0x18002983c  push    r12
0x18002983e  push    r13
0x180029840  push    r14
0x180029842  push    r15
0x180029844  lea     rbp, [rsp-27h]
0x180029849  sub     rsp, 0D0h
0x180029850  mov     r14, rdx
0x180029853  mov     rbx, rcx
0x180029856  xor     r15d, r15d
0x180029859  mov     [rbp+57h+arg_8], r15d
0x18002985d  mov     [rbp+57h+var_90], r15
0x180029861  mov     [rbp+57h+var_80], r15
0x180029865  mov     [rbp+57h+var_88], r15
0x180029869  mov     [rbp+57h+var_A8], r15
0x18002986d  mov     [rbp+57h+var_98], r15
0x180029871  mov     [rbp+57h+var_A0], r15
0x180029875  mov     [rbp+57h+var_C0], r15
0x180029879  mov     [rbp+57h+var_B0], r15
0x18002987d  mov     [rbp+57h+var_B8], r15
0x180029881  mov     [rbp+57h+pcchEscaped], 824h
0x180029888  lea     r12, aLitecryptutili_0; "LiteCryptUtilities::UrlEscapeStringA"
0x18002988f  mov     [rbp+57h+var_58], r12
0x180029893  lea     rax, [rbp+57h+arg_8]
0x180029897  mov     [rbp+57h+var_50], rax
0x18002989b  mov     [rbp+57h+var_48], r15
0x18002989f  mov     [rbp+57h+var_40], r15
0x1800298a3  xor     r9d, r9d; unsigned int
0x1800298a6  mov     r8d, 8Ch; char *
0x1800298ac  mov     rdx, r12; char *
0x1800298af  lea     r13, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800298b6  mov     rcx, r13; this
0x1800298b9  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800298be  nop
0x1800298bf  lea     rax, qword_180041D90
0x1800298c6  mov     [rsp+100h+lpWideCharStr], rax; int *
0x1800298cb  lea     r9d, [r15+0Bh]; unsigned __int64
0x1800298cf  lea     r8, [rbp+57h+arg_8]; int *
0x1800298d3  mov     rdx, r12; char *
0x1800298d6  lea     rcx, [rbp+57h+var_78]; this
0x1800298da  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800298df  test    r14, r14
0x1800298e2  jz      loc_180029B5D
0x1800298e8  test    rbx, rbx
0x1800298eb  jz      loc_180029B5D
0x1800298f1  cmp     [rbx], r15b
0x1800298f4  jz      loc_180029B5D
0x1800298fa  mov     [r14], r15
0x1800298fd  mov     [rsp+100h+cchWideChar], r15d; cchWideChar
0x180029902  mov     [rsp+100h+lpWideCharStr], r15; lpWideCharStr
0x180029907  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002990b  mov     r8, rbx; lpMultiByteStr
0x18002990e  xor     edx, edx; dwFlags
0x180029910  mov     ecx, 0FDE9h; CodePage
0x180029915  call    cs:__imp_MultiByteToWideChar
0x18002991b  movsxd  rdi, eax
0x18002991e  test    eax, eax
0x180029920  jnz     short loc_180029955
0x180029922  call    cs:__imp_GetLastError
0x180029928  test    eax, eax
0x18002992a  jle     short loc_180029934
0x18002992c  movzx   eax, ax
0x18002992f  or      eax, 80070000h
0x180029934  mov     [rbp+57h+arg_8], eax
0x180029937  test    eax, eax
0x180029939  jns     short loc_180029955
0x18002993b  lea     r8, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180029942  mov     [rsp+100h+lpWideCharStr], r8
0x180029947  mov     r9d, eax
0x18002994a  mov     r8d, 0A9h
0x180029950  jmp     loc_180029B79
0x180029955  mov     rdx, rdi
0x180029958  add     rdx, rdx; uBytes
0x18002995b  mov     ecx, 40h ; '@'; uFlags
0x180029960  call    cs:__imp_LocalAlloc
0x180029966  mov     rsi, rax
0x180029969  lea     rcx, [rbp+57h+var_90]
0x18002996d  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180029972  mov     [rbp+57h+var_90], rsi
0x180029976  test    rsi, rsi
0x180029979  jnz     short loc_180029993
0x18002997b  mov     r9d, 8007000Eh
0x180029981  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180029988  mov     r8d, 0AFh
0x18002998e  jmp     loc_180029B70
0x180029993  mov     [rsp+100h+cchWideChar], edi; cchWideChar
0x180029997  mov     [rsp+100h+lpWideCharStr], rsi; lpWideCharStr
0x18002999c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800299a0  mov     r8, rbx; lpMultiByteStr
0x1800299a3  xor     edx, edx; dwFlags
0x1800299a5  mov     ecx, 0FDE9h; CodePage
0x1800299aa  call    cs:__imp_MultiByteToWideChar
0x1800299b0  test    eax, eax
0x1800299b2  jnz     short loc_1800299E7
0x1800299b4  call    cs:__imp_GetLastError
0x1800299ba  test    eax, eax
0x1800299bc  jle     short loc_1800299C6
0x1800299be  movzx   eax, ax
0x1800299c1  or      eax, 80070000h
0x1800299c6  mov     [rbp+57h+arg_8], eax
0x1800299c9  test    eax, eax
0x1800299cb  jns     short loc_1800299E7
0x1800299cd  lea     r8, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800299d4  mov     [rsp+100h+lpWideCharStr], r8
0x1800299d9  mov     r9d, eax
0x1800299dc  mov     r8d, 0B9h
0x1800299e2  jmp     loc_180029B79
0x1800299e7  mov     edx, [rbp+57h+pcchEscaped]
0x1800299ea  add     rdx, rdx; uBytes
0x1800299ed  mov     ebx, 40h ; '@'
0x1800299f2  mov     ecx, ebx; uFlags
0x1800299f4  call    cs:__imp_LocalAlloc
0x1800299fa  mov     rdi, rax
0x1800299fd  lea     rcx, [rbp+57h+var_A8]
0x180029a01  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180029a06  mov     [rbp+57h+var_A8], rdi
0x180029a0a  test    rdi, rdi
0x180029a0d  jnz     short loc_180029A27
0x180029a0f  mov     r9d, 8007000Eh
0x180029a15  lea     rax, aHrEOutofmemory_0; "hr=E_OUTOFMEMORY"
0x180029a1c  mov     r8d, 0C2h
0x180029a22  jmp     loc_180029B70
0x180029a27  mov     r9d, 0C3000h; dwFlags
0x180029a2d  lea     r8, [rbp+57h+pcchEscaped]; pcchEscaped
0x180029a31  mov     rdx, rdi; pszEscaped
0x180029a34  mov     rcx, rsi; pszUrl
0x180029a37  call    cs:__imp_UrlEscapeW
0x180029a3d  mov     [rbp+57h+arg_8], eax
0x180029a40  test    eax, eax
0x180029a42  jns     short loc_180029A5E
0x180029a44  lea     rcx, aHrUrlescapewSp; "hr = UrlEscapeW(spInputWideCharBuffer, "...
0x180029a4b  mov     [rsp+100h+lpWideCharStr], rcx
0x180029a50  mov     r9d, eax
0x180029a53  mov     r8d, 0CFh
0x180029a59  jmp     loc_180029B79
0x180029a5e  mov     [rsp+100h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180029a63  mov     [rsp+100h+lpDefaultChar], r15; lpDefaultChar
0x180029a68  mov     [rsp+100h+cchWideChar], r15d; cbMultiByte
0x180029a6d  mov     [rsp+100h+lpWideCharStr], r15; lpMultiByteStr
0x180029a72  or      r9d, 0FFFFFFFFh; cchWideChar
0x180029a76  mov     r8, rdi; lpWideCharStr
0x180029a79  xor     edx, edx; dwFlags
0x180029a7b  mov     ecx, 0FDE9h; CodePage
0x180029a80  call    cs:__imp_WideCharToMultiByte
0x180029a86  movsxd  rsi, eax
0x180029a89  test    eax, eax
0x180029a8b  jnz     short loc_180029AC0
0x180029a8d  call    cs:__imp_GetLastError
0x180029a93  test    eax, eax
0x180029a95  jle     short loc_180029A9F
0x180029a97  movzx   eax, ax
0x180029a9a  or      eax, 80070000h
0x180029a9f  mov     [rbp+57h+arg_8], eax
0x180029aa2  test    eax, eax
0x180029aa4  jns     short loc_180029AC0
0x180029aa6  lea     r8, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180029aad  mov     [rsp+100h+lpWideCharStr], r8
0x180029ab2  mov     r9d, eax
0x180029ab5  mov     r8d, 0DFh
0x180029abb  jmp     loc_180029B79
0x180029ac0  mov     rdx, rsi; uBytes
0x180029ac3  mov     ecx, ebx; uFlags
0x180029ac5  call    cs:__imp_LocalAlloc
0x180029acb  mov     rbx, rax
0x180029ace  lea     rcx, [rbp+57h+var_C0]
0x180029ad2  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180029ad7  mov     [rbp+57h+var_C0], rbx
0x180029adb  test    rbx, rbx
0x180029ade  jnz     short loc_180029AF5
0x180029ae0  mov     r9d, 8007000Eh
0x180029ae6  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180029aed  mov     r8d, 0E5h
0x180029af3  jmp     short loc_180029B70
0x180029af5  mov     [rsp+100h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180029afa  mov     [rsp+100h+lpDefaultChar], r15; lpDefaultChar
0x180029aff  mov     [rsp+100h+cchWideChar], esi; cbMultiByte
0x180029b03  mov     [rsp+100h+lpWideCharStr], rbx; lpMultiByteStr
0x180029b08  or      r9d, 0FFFFFFFFh; cchWideChar
0x180029b0c  mov     r8, rdi; lpWideCharStr
0x180029b0f  xor     edx, edx; dwFlags
0x180029b11  mov     ecx, 0FDE9h; CodePage
0x180029b16  call    cs:__imp_WideCharToMultiByte
0x180029b1c  test    eax, eax
0x180029b1e  jnz     short loc_180029B50
0x180029b20  call    cs:__imp_GetLastError
0x180029b26  test    eax, eax
0x180029b28  jle     short loc_180029B32
0x180029b2a  movzx   eax, ax
0x180029b2d  or      eax, 80070000h
0x180029b32  mov     [rbp+57h+arg_8], eax
0x180029b35  test    eax, eax
0x180029b37  jns     short loc_180029B50
0x180029b39  lea     r8, aHrHresultFromW_1; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180029b40  mov     [rsp+100h+lpWideCharStr], r8
0x180029b45  mov     r9d, eax
0x180029b48  mov     r8d, 0F1h
0x180029b4e  jmp     short loc_180029B79
0x180029b50  mov     [rbp+57h+var_C0], r15
0x180029b54  mov     [rbp+57h+var_B8], r15
0x180029b58  mov     [r14], rbx
0x180029b5b  jmp     short loc_180029B84
0x180029b5d  mov     r9d, 80070057h; int
0x180029b63  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x180029b6a  mov     r8d, 98h; unsigned int
0x180029b70  mov     [rsp+100h+lpWideCharStr], rax; char *
0x180029b75  mov     [rbp+57h+arg_8], r9d
0x180029b79  mov     rdx, r12; char *
0x180029b7c  mov     rcx, r13; char *
0x180029b7f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180029b84  mov     ebx, [rbp+57h+arg_8]
0x180029b87  mov     r9, [rbp+57h+var_78]; int *
0x180029b8b  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x180029b8f  mov     rdx, [rbp+57h+var_68]
0x180029b93  mov     edx, [rdx]; int
0x180029b95  mov     rcx, [rbp+57h+var_60]; char *
0x180029b99  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180029b9e  nop
0x180029b9f  lea     rcx, [rbp+57h+var_58]
0x180029ba3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180029ba8  nop
0x180029ba9  lea     rcx, [rbp+57h+var_C0]
0x180029bad  call    ??1?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAA@XZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>(void)
0x180029bb2  nop
0x180029bb3  lea     rcx, [rbp+57h+var_A8]
0x180029bb7  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180029bbc  nop
0x180029bbd  lea     rcx, [rbp+57h+var_90]
0x180029bc1  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180029bc6  mov     eax, ebx
0x180029bc8  mov     rbx, [rsp+100h+arg_0]
0x180029bd0  add     rsp, 0D0h
0x180029bd7  pop     r15
0x180029bd9  pop     r14
0x180029bdb  pop     r13
0x180029bdd  pop     r12
0x180029bdf  pop     rdi
0x180029be0  pop     rsi
0x180029be1  pop     rbp
0x180029be2  retn
```

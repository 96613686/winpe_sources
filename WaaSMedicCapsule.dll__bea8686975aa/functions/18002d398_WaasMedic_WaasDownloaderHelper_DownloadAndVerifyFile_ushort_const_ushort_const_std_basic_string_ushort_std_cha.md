# WaasMedic::WaasDownloaderHelper::DownloadAndVerifyFile(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &)

- ea: `0x18002d398`
- end: `0x18002d558`
- name: `?DownloadAndVerifyFile@WaasDownloaderHelper@WaasMedic@@QEAAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016af0`

## callees

- `0x180003bb0`
- `0x180007590`
- `0x180009a34`
- `0x180017a64`
- `0x18002543c`
- `0x18002cb94`
- `0x18002d398`
- `0x18002d560`
- `0x18002da64`
- `0x18002dc1c`
- `0x180030fbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d491`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002d420`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002d420`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18002d3f7`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18002d3f7`

## string_xrefs

- `0x18002d4a9`: `GetTempPath2 Failed, hr=0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::WaasDownloaderHelper::DownloadAndVerifyFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  bool *v10; // r9
  signed int LastError; // eax
  WaasMedic *p_Src; // rcx
  WaasMedic *v13; // rcx
  bool IsTestSigningEnabled; // al
  const unsigned __int16 *v15; // rcx
  unsigned __int16 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int128 Src; // [rsp+28h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+38h] [rbp-C8h]
  WCHAR PathName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR TempFileName[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  *a5 = 0;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  if ( (unsigned int)GetTempPath2W(261, PathName) - 1 > 0x104 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"GetTempPath2 Failed, hr=0x%08x.", v6);
  }
  else
  {
    if ( GetTempFileNameW(PathName, L"euw", 0, TempFileName) )
    {
      std::wstring::append(&Src, TempFileName);
      std::wstring::append(&Src, L".exe");
      goto LABEL_5;
    }
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x171,
           (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
           v5);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    *a5 |= 1u;
    goto LABEL_24;
  }
LABEL_5:
  std::wstring::operator=(&WaasMedic::WaasDownloaderHelper::downloadedPath, &Src);
  v8 = WaasMedic::DownloadFile(v7, (const WCHAR *)&Src);
  if ( v8 >= 0 )
  {
    LOBYTE(v17) = 0;
    p_Src = (WaasMedic *)&Src;
    if ( si128.m128i_i64[1] > 7uLL )
      p_Src = (WaasMedic *)Src;
    v8 = WaasMedic::ValidateDownloadedFileWithHash(p_Src, v9, &v17, v10);
    if ( v8 >= 0 )
    {
      if ( !(_BYTE)v17 )
      {
        *a5 |= 8u;
        v6 = -2147024573;
        goto LABEL_24;
      }
      IsTestSigningEnabled = WaasMedic::IsTestSigningEnabled(v13);
      v15 = (const unsigned __int16 *)&Src;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = (const unsigned __int16 *)Src;
      v8 = WaasMedic::WaasDownloaderHelper::VerifyMicrosoftSignature(v15, IsTestSigningEnabled);
      if ( v8 >= 0 )
      {
        v6 = 0;
        goto LABEL_24;
      }
      *a5 |= 0x10u;
    }
    else
    {
      *a5 |= 4u;
    }
  }
  else
  {
    *a5 |= 2u;
  }
  v6 = v8;
LABEL_24:
  std::wstring::~wstring(&Src);
  return v6;
}

```

## disassembly

```asm
0x18002d398  mov     [rsp-8+arg_0], rbx
0x18002d39d  mov     [rsp-8+arg_8], rdi
0x18002d3a2  push    rbp
0x18002d3a3  lea     rbp, [rsp-380h]
0x18002d3ab  sub     rsp, 480h
0x18002d3b2  mov     rax, cs:__security_cookie
0x18002d3b9  xor     rax, rsp
0x18002d3bc  mov     [rbp+380h+var_10], rax
0x18002d3c3  mov     rdi, [rbp+380h+arg_20]
0x18002d3ca  mov     dword ptr [rdi], 0
0x18002d3d0  xorps   xmm0, xmm0
0x18002d3d3  movups  [rsp+480h+Src], xmm0
0x18002d3d8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002d3e0  movdqu  [rsp+480h+var_448], xmm1
0x18002d3e6  xor     eax, eax
0x18002d3e8  mov     word ptr [rsp+480h+Src], ax
0x18002d3ed  lea     rdx, [rsp+480h+PathName]
0x18002d3f2  mov     ecx, 105h
0x18002d3f7  call    cs:__imp_GetTempPath2W
0x18002d3fd  dec     eax
0x18002d3ff  cmp     eax, 104h
0x18002d404  ja      loc_18002D491
0x18002d40a  lea     r9, [rbp+380h+TempFileName]; lpTempFileName
0x18002d411  xor     r8d, r8d; uUnique
0x18002d414  lea     rdx, PrefixString; "euw"
0x18002d41b  lea     rcx, [rsp+480h+PathName]; lpPathName
0x18002d420  call    cs:__imp_GetTempFileNameW
0x18002d426  test    eax, eax
0x18002d428  jnz     short loc_18002D446
0x18002d42a  mov     rcx, [rbp+388h]; this
0x18002d431  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002d438  mov     edx, 171h; void *
0x18002d43d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d442  mov     ebx, eax
0x18002d444  jmp     short loc_18002D4BA
0x18002d446  lea     rdx, [rbp+380h+TempFileName]; void *
0x18002d44d  lea     rcx, [rsp+480h+Src]; Src
0x18002d452  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002d457  lea     rdx, aExe; ".exe"
0x18002d45e  lea     rcx, [rsp+480h+Src]; Src
0x18002d463  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002d468  lea     rdx, [rsp+480h+Src]
0x18002d46d  lea     rcx, ?downloadedPath@WaasDownloaderHelper@WaasMedic@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring WaasMedic::WaasDownloaderHelper::downloadedPath
0x18002d474  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002d479  lea     rdx, [rsp+480h+Src]
0x18002d47e  call    ?DownloadFile@WaasMedic@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::DownloadFile(ushort const *,std::wstring &)
0x18002d483  test    eax, eax
0x18002d485  jns     short loc_18002D4C3
0x18002d487  or      dword ptr [rdi], 2
0x18002d48a  mov     ebx, eax
0x18002d48c  jmp     loc_18002D528
0x18002d491  call    cs:__imp_GetLastError
0x18002d497  mov     ebx, eax
0x18002d499  test    eax, eax
0x18002d49b  jle     short loc_18002D4A6
0x18002d49d  movzx   ebx, ax
0x18002d4a0  or      ebx, 80070000h
0x18002d4a6  mov     r8d, ebx
0x18002d4a9  lea     rdx, aGettemppath2Fa; "GetTempPath2 Failed, hr=0x%08x."
0x18002d4b0  mov     ecx, 2; unsigned __int8
0x18002d4b5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002d4ba  test    ebx, ebx
0x18002d4bc  jns     short loc_18002D468
0x18002d4be  or      dword ptr [rdi], 1
0x18002d4c1  jmp     short loc_18002D528
0x18002d4c3  mov     byte ptr [rsp+480h+var_460], 0
0x18002d4c8  lea     rcx, [rsp+480h+Src]
0x18002d4cd  cmp     qword ptr [rsp+480h+var_448+8], 7
0x18002d4d3  cmova   rcx, qword ptr [rsp+480h+Src]; this
0x18002d4d9  lea     r8, [rsp+480h+var_460]; unsigned __int16 *
0x18002d4de  call    ?ValidateDownloadedFileWithHash@WaasMedic@@YAJPEBG0PEA_N@Z; WaasMedic::ValidateDownloadedFileWithHash(ushort const *,ushort const *,bool *)
0x18002d4e3  test    eax, eax
0x18002d4e5  jns     short loc_18002D4EC
0x18002d4e7  or      dword ptr [rdi], 4
0x18002d4ea  jmp     short loc_18002D48A
0x18002d4ec  cmp     byte ptr [rsp+480h+var_460], 0
0x18002d4f1  jnz     short loc_18002D4FD
0x18002d4f3  or      dword ptr [rdi], 8
0x18002d4f6  mov     ebx, 80070143h
0x18002d4fb  jmp     short loc_18002D528
0x18002d4fd  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x18002d502  lea     rcx, [rsp+480h+Src]
0x18002d507  cmp     qword ptr [rsp+480h+var_448+8], 7
0x18002d50d  cmova   rcx, qword ptr [rsp+480h+Src]; unsigned __int16 *
0x18002d513  mov     dl, al; bool
0x18002d515  call    ?VerifyMicrosoftSignature@WaasDownloaderHelper@WaasMedic@@CAJPEBG_N@Z; WaasMedic::WaasDownloaderHelper::VerifyMicrosoftSignature(ushort const *,bool)
0x18002d51a  test    eax, eax
0x18002d51c  jns     short loc_18002D526
0x18002d51e  or      dword ptr [rdi], 10h
0x18002d521  jmp     loc_18002D48A
0x18002d526  xor     ebx, ebx
0x18002d528  lea     rcx, [rsp+480h+Src]; void *
0x18002d52d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d532  mov     eax, ebx
0x18002d534  mov     rcx, [rbp+380h+var_10]
0x18002d53b  xor     rcx, rsp; StackCookie
0x18002d53e  call    __security_check_cookie
0x18002d543  lea     r11, [rsp+480h+var_s0]
0x18002d54b  mov     rbx, [r11+10h]
0x18002d54f  mov     rdi, [r11+18h]
0x18002d553  mov     rsp, r11
0x18002d556  pop     rbp
0x18002d557  retn
```

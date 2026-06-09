# DelayLoadFailureHookWithRetryAndTelemetry

- ea: `0x18013c7f0`
- end: `0x18013cb1d`
- name: `DelayLoadFailureHookWithRetryAndTelemetry`
- size: `813`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800091d0`
- `0x18013bf30`
- `0x18013c7f0`
- `0x18013cb20`
- `0x18013d650`
- `0x18013f760`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18013c897`
- `KERNEL32!LoadLibraryExA` at `0x18013c897`
- `KERNEL32!GetModuleHandleW` at `0x18013c8d4`
- `KERNEL32!GetModuleHandleW` at `0x18013c8e6`
- `KERNEL32!GetModuleHandleW` at `0x18013c9fb`
- `KERNEL32!GetModuleHandleW` at `0x18013ca0d`
- `KERNEL32!GetModuleHandleW` at `0x18013c8d4`
- `KERNEL32!GetModuleHandleW` at `0x18013c8e6`
- `KERNEL32!GetModuleHandleW` at `0x18013c9fb`
- `KERNEL32!GetModuleHandleW` at `0x18013ca0d`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013c942`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013ca87`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013c942`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013ca87`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013c98f`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013cadc`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013c98f`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013cadc`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013c9c1`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013cb0e`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013c9c1`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013cb0e`

## string_xrefs

- `0x18013c916`: `DllName`
- `0x18013ca3d`: `DllName`
- `0x18013c8df`: `mso20win32server.dll`
- `0x18013ca06`: `mso20win32server.dll`
- `0x18013c8cd`: `mso20win32client.dll`
- `0x18013c9f4`: `mso20win32client.dll`

## pseudocode

```c
HMODULE __fastcall DelayLoadFailureHookWithRetryAndTelemetry(int a1, struct DelayLoadInfo *a2)
{
  unsigned int v3; // ebx
  HMODULE Library; // r14
  const char **p_szDll; // rdi
  void **v6; // rax
  const char *v7; // r8
  _QWORD *v9; // rax
  const char *v10; // r8
  __int64 v11; // [rsp+30h] [rbp-59h] BYREF
  __int64 v12; // [rsp+38h] [rbp-51h] BYREF
  void **v13; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v14; // [rsp+48h] [rbp-41h]
  __int64 *v15; // [rsp+50h] [rbp-39h]
  void **v16; // [rsp+58h] [rbp-31h] BYREF
  __int64 *v17; // [rsp+60h] [rbp-29h]
  void ***v18; // [rsp+68h] [rbp-21h]
  __int16 v19; // [rsp+70h] [rbp-19h]
  _QWORD Src[3]; // [rsp+78h] [rbp-11h] BYREF
  __int16 v21; // [rsp+90h] [rbp+7h]
  _BYTE v22[32]; // [rsp+98h] [rbp+Fh] BYREF

  if ( a1 != 3 )
    return 0;
  ++g_retryDelayLoadStatistics;
  v3 = 1;
  while ( 1 )
  {
    if ( g_retryDelayLoadTestHook )
      g_retryDelayLoadTestHook(v3, 50);
    if ( _pfnDliNotifyHook2 )
    {
      Library = (HMODULE)_pfnDliNotifyHook2(1u, a2);
      p_szDll = &a2->szDll;
      if ( Library )
        break;
    }
    p_szDll = &a2->szDll;
    if ( !*a2->szDll )
      __fastfail(5u);
    Library = LoadLibraryExA(a2->szDll, 0, 0x1000u);
    if ( Library )
      break;
    v11 = 10LL * v3;
    std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v11);
    if ( ++v3 > 0x32 )
    {
      if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
      {
        v6 = (void **)sub_18013CB20(Src);
        if ( (unsigned __int64)v6[3] > 7 )
          v6 = (void **)*v6;
        v16 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
        v17 = (__int64 *)L"DllName";
        v18 = (void ***)v6;
        v19 = 0;
        if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(50685657, 51, 10) )
        {
          v13 = &Mso::Logging::CompositeStructuredTrace::`vftable';
          v14 = &v11;
          v15 = &v12;
          Mso::Logging::MsoSendStructuredTraceTag(50685657, 51, 10, 0, L"DelayloadRetryError", &v13, &v16, v12);
        }
        std::wstring::~wstring(Src);
      }
      ++dword_180195018;
      v7 = (const char *)&word_180155DCE;
      if ( *p_szDll )
        v7 = *p_szDll;
      strncpy_s(Destination, 0x64u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
  {
    v9 = (_QWORD *)sub_18013CB20(v22);
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    Src[0] = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    Src[1] = L"DllName";
    Src[2] = v9;
    v21 = 0;
    v13 = &Mso::Logging::StructuredErrorCode::`vftable';
    v14 = (__int64 *)L"NumRetries";
    LODWORD(v15) = v3;
    WORD2(v15) = 0;
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(50685656, 51, 50) )
    {
      v16 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v17 = &v11;
      v18 = &v13;
      Mso::Logging::MsoSendStructuredTraceTag(50685656, 51, 50, 0, L"DelayloadRetry", &v16, &v13, Src);
    }
    std::wstring::~wstring(v22);
  }
  ++dword_180195014;
  v10 = (const char *)&word_180155DCE;
  if ( *p_szDll )
    v10 = *p_szDll;
  strncpy_s(byte_18019501C, 0x64u, v10, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x18013c7f0  mov     [rsp-8+arg_0], rbx
0x18013c7f5  mov     [rsp-8+arg_10], rsi
0x18013c7fa  push    rbp
0x18013c7fb  push    rdi
0x18013c7fc  push    r12
0x18013c7fe  push    r14
0x18013c800  push    r15
0x18013c802  lea     rbp, [rsp-37h]
0x18013c807  sub     rsp, 0C0h
0x18013c80e  mov     rax, cs:__security_cookie
0x18013c815  xor     rax, rsp
0x18013c818  mov     [rbp+57h+var_28], rax
0x18013c81c  mov     rsi, rdx
0x18013c81f  cmp     ecx, 3
0x18013c822  jnz     loc_18013C9C7
0x18013c828  inc     cs:?g_retryDelayLoadStatistics@@3URetryDelayLoadStatistics@@A; RetryDelayLoadStatistics g_retryDelayLoadStatistics
0x18013c82e  lea     ebx, [rcx-2]
0x18013c831  xor     r12d, r12d
0x18013c834  mov     rax, cs:?g_retryDelayLoadTestHook@@3P6AXIIPEBD@_EEA
0x18013c83b  test    rax, rax
0x18013c83e  jz      short loc_18013C84F
0x18013c840  xor     r8d, r8d
0x18013c843  lea     edx, [r8+32h]
0x18013c847  mov     ecx, ebx
0x18013c849  call    cs:__guard_dispatch_icall_fptr
0x18013c84f  mov     rax, cs:__pfnDliNotifyHook2
0x18013c856  test    rax, rax
0x18013c859  jz      short loc_18013C879
0x18013c85b  mov     rdx, rsi
0x18013c85e  mov     ecx, 1
0x18013c863  call    cs:__guard_dispatch_icall_fptr
0x18013c869  mov     r14, rax
0x18013c86c  lea     rdi, [rsi+18h]
0x18013c870  test    rax, rax
0x18013c873  jnz     loc_18013C9F1
0x18013c879  lea     rdi, [rsi+18h]
0x18013c87d  mov     rax, [rdi]
0x18013c880  cmp     [rax], r12b
0x18013c883  jnz     short loc_18013C88C
0x18013c885  mov     ecx, 5
0x18013c88a  int     29h; Win8: RtlFailFast(ecx)
0x18013c88c  xor     edx, edx; hFile
0x18013c88e  mov     r8d, 1000h; dwFlags
0x18013c894  mov     rcx, rax; lpLibFileName
0x18013c897  call    cs:__imp_LoadLibraryExA
0x18013c89d  mov     r14, rax
0x18013c8a0  test    rax, rax
0x18013c8a3  jnz     loc_18013C9F1
0x18013c8a9  mov     eax, ebx
0x18013c8ab  lea     rcx, [rax+rax*4]
0x18013c8af  add     rcx, rcx
0x18013c8b2  mov     [rbp+57h+var_B0], rcx
0x18013c8b6  lea     rcx, [rbp+57h+var_B0]
0x18013c8ba  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18013c8bf  inc     ebx
0x18013c8c1  cmp     ebx, 32h ; '2'
0x18013c8c4  jbe     loc_18013C834
0x18013c8ca  mov     rbx, [rdi]
0x18013c8cd  lea     rcx, ModuleName; "mso20win32client.dll"
0x18013c8d4  call    cs:__imp_GetModuleHandleW
0x18013c8da  test    rax, rax
0x18013c8dd  jnz     short loc_18013C8F5
0x18013c8df  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x18013c8e6  call    cs:__imp_GetModuleHandleW
0x18013c8ec  test    rax, rax
0x18013c8ef  jz      loc_18013C99E
0x18013c8f5  mov     rdx, rbx
0x18013c8f8  lea     rcx, [rbp+57h+Src]; Src
0x18013c8fc  call    sub_18013CB20
0x18013c901  cmp     qword ptr [rax+18h], 7
0x18013c906  jbe     short loc_18013C90B
0x18013c908  mov     rax, [rax]
0x18013c90b  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18013c912  mov     [rbp+57h+var_88], rcx
0x18013c916  lea     rcx, aDllname; "DllName"
0x18013c91d  mov     [rbp+57h+var_80], rcx
0x18013c921  mov     [rbp+57h+var_78], rax
0x18013c925  mov     [rbp+57h+var_70], r12w
0x18013c92a  xor     r9d, r9d
0x18013c92d  lea     esi, [r9+0Ah]
0x18013c931  mov     r8d, esi
0x18013c934  lea     ebx, [rsi+29h]
0x18013c937  mov     edx, ebx
0x18013c939  mov     r14d, 30566D9h
0x18013c93f  mov     ecx, r14d
0x18013c942  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18013c948  test    al, al
0x18013c94a  jz      short loc_18013C995
0x18013c94c  lea     rax, [rbp+57h+var_88]
0x18013c950  mov     [rbp+57h+var_B0], rax
0x18013c954  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18013c95b  mov     [rbp+57h+var_A0], rax
0x18013c95f  lea     rax, [rbp+57h+var_B0]
0x18013c963  mov     [rbp+57h+var_98], rax
0x18013c967  lea     rax, [rbp+57h+var_A8]
0x18013c96b  mov     [rbp+57h+var_90], rax
0x18013c96f  xor     r9d, r9d
0x18013c972  lea     rax, [rbp+57h+var_A0]
0x18013c976  mov     [rsp+0E0h+var_B8], rax
0x18013c97b  lea     rax, aDelayloadretry_0; "DelayloadRetryError"
0x18013c982  mov     [rsp+0E0h+var_C0], rax
0x18013c987  mov     r8d, esi
0x18013c98a  mov     edx, ebx
0x18013c98c  mov     ecx, r14d
0x18013c98f  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18013c995  lea     rcx, [rbp+57h+Src]; void *
0x18013c999  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18013c99e  inc     cs:dword_180195018
0x18013c9a4  lea     r8, word_180155DCE
0x18013c9ab  cmp     [rdi], r12
0x18013c9ae  cmovnz  r8, [rdi]; Source
0x18013c9b2  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18013c9b6  lea     edx, [r9+65h]; SizeInBytes
0x18013c9ba  lea     rcx, Destination; Destination
0x18013c9c1  call    cs:__imp_strncpy_s
0x18013c9c7  xor     eax, eax
0x18013c9c9  mov     rcx, [rbp+57h+var_28]
0x18013c9cd  xor     rcx, rsp; StackCookie
0x18013c9d0  call    __security_check_cookie
0x18013c9d5  lea     r11, [rsp+0E0h+var_20]
0x18013c9dd  mov     rbx, [r11+30h]
0x18013c9e1  mov     rsi, [r11+40h]
0x18013c9e5  mov     rsp, r11
0x18013c9e8  pop     r15
0x18013c9ea  pop     r14
0x18013c9ec  pop     r12
0x18013c9ee  pop     rdi
0x18013c9ef  pop     rbp
0x18013c9f0  retn
0x18013c9f1  mov     rsi, [rdi]
0x18013c9f4  lea     rcx, ModuleName; "mso20win32client.dll"
0x18013c9fb  call    cs:__imp_GetModuleHandleW
0x18013ca01  test    rax, rax
0x18013ca04  jnz     short loc_18013CA1C
0x18013ca06  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x18013ca0d  call    cs:__imp_GetModuleHandleW
0x18013ca13  test    rax, rax
0x18013ca16  jz      loc_18013CAEB
0x18013ca1c  mov     rdx, rsi
0x18013ca1f  lea     rcx, [rbp+57h+var_48]; Src
0x18013ca23  call    sub_18013CB20
0x18013ca28  cmp     qword ptr [rax+18h], 7
0x18013ca2d  jbe     short loc_18013CA32
0x18013ca2f  mov     rax, [rax]
0x18013ca32  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18013ca39  mov     [rbp+57h+Src], rcx
0x18013ca3d  lea     rcx, aDllname; "DllName"
0x18013ca44  mov     [rbp+57h+var_60], rcx
0x18013ca48  mov     [rbp+57h+var_58], rax
0x18013ca4c  mov     [rbp+57h+var_50], r12w
0x18013ca51  lea     rax, ??_7StructuredErrorCode@Logging@Mso@@6B@; const Mso::Logging::StructuredErrorCode::`vftable'
0x18013ca58  mov     [rbp+57h+var_A0], rax
0x18013ca5c  lea     rax, aNumretries; "NumRetries"
0x18013ca63  mov     [rbp+57h+var_98], rax
0x18013ca67  mov     dword ptr [rbp+57h+var_90], ebx
0x18013ca6a  mov     word ptr [rbp+57h+var_90+4], r12w
0x18013ca6f  xor     r9d, r9d
0x18013ca72  lea     esi, [r9+32h]
0x18013ca76  mov     r8d, esi
0x18013ca79  lea     ebx, [rsi+1]
0x18013ca7c  mov     edx, ebx
0x18013ca7e  mov     r15d, 30566D8h
0x18013ca84  mov     ecx, r15d
0x18013ca87  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18013ca8d  test    al, al
0x18013ca8f  jz      short loc_18013CAE2
0x18013ca91  lea     rax, [rbp+57h+var_A0]
0x18013ca95  mov     [rbp+57h+var_B0], rax
0x18013ca99  lea     rax, [rbp+57h+Src]
0x18013ca9d  mov     [rbp+57h+var_A8], rax
0x18013caa1  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18013caa8  mov     [rbp+57h+var_88], rax
0x18013caac  lea     rax, [rbp+57h+var_B0]
0x18013cab0  mov     [rbp+57h+var_80], rax
0x18013cab4  lea     rax, [rbp+57h+var_A0]
0x18013cab8  mov     [rbp+57h+var_78], rax
0x18013cabc  xor     r9d, r9d
0x18013cabf  lea     rax, [rbp+57h+var_88]
0x18013cac3  mov     [rsp+0E0h+var_B8], rax
0x18013cac8  lea     rax, aDelayloadretry; "DelayloadRetry"
0x18013cacf  mov     [rsp+0E0h+var_C0], rax
0x18013cad4  mov     r8d, esi
0x18013cad7  mov     edx, ebx
0x18013cad9  mov     ecx, r15d
0x18013cadc  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18013cae2  lea     rcx, [rbp+57h+var_48]; void *
0x18013cae6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18013caeb  inc     cs:dword_180195014
0x18013caf1  lea     r8, word_180155DCE
0x18013caf8  cmp     [rdi], r12
0x18013cafb  cmovnz  r8, [rdi]; Source
0x18013caff  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18013cb03  lea     edx, [r9+65h]; SizeInBytes
0x18013cb07  lea     rcx, byte_18019501C; Destination
0x18013cb0e  call    cs:__imp_strncpy_s
0x18013cb14  mov     rax, r14
0x18013cb17  jmp     loc_18013C9C9
```

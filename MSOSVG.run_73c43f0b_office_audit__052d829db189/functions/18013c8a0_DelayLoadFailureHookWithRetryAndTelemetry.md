# DelayLoadFailureHookWithRetryAndTelemetry

- ea: `0x18013c8a0`
- end: `0x18013cbcd`
- name: `DelayLoadFailureHookWithRetryAndTelemetry`
- size: `813`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800091d0`
- `0x18013bfe0`
- `0x18013c8a0`
- `0x18013cbd0`
- `0x18013d700`
- `0x18013f810`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18013c947`
- `KERNEL32!LoadLibraryExA` at `0x18013c947`
- `KERNEL32!GetModuleHandleW` at `0x18013c984`
- `KERNEL32!GetModuleHandleW` at `0x18013c996`
- `KERNEL32!GetModuleHandleW` at `0x18013caab`
- `KERNEL32!GetModuleHandleW` at `0x18013cabd`
- `KERNEL32!GetModuleHandleW` at `0x18013c984`
- `KERNEL32!GetModuleHandleW` at `0x18013c996`
- `KERNEL32!GetModuleHandleW` at `0x18013caab`
- `KERNEL32!GetModuleHandleW` at `0x18013cabd`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013c9f2`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013cb37`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013c9f2`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18013cb37`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013ca3f`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013cb8c`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013ca3f`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18013cb8c`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013ca71`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013cbbe`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013ca71`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18013cbbe`

## string_xrefs

- `0x18013c9c6`: `DllName`
- `0x18013caed`: `DllName`
- `0x18013c98f`: `mso20win32server.dll`
- `0x18013cab6`: `mso20win32server.dll`
- `0x18013c97d`: `mso20win32client.dll`
- `0x18013caa4`: `mso20win32client.dll`

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
        v6 = (void **)sub_18013CBD0(Src);
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
      v7 = (const char *)&word_180155DB6;
      if ( *p_szDll )
        v7 = *p_szDll;
      strncpy_s(Destination, 0x64u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
  {
    v9 = (_QWORD *)sub_18013CBD0(v22);
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
  v10 = (const char *)&word_180155DB6;
  if ( *p_szDll )
    v10 = *p_szDll;
  strncpy_s(byte_18019501C, 0x64u, v10, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x18013c8a0  mov     [rsp-8+arg_0], rbx
0x18013c8a5  mov     [rsp-8+arg_10], rsi
0x18013c8aa  push    rbp
0x18013c8ab  push    rdi
0x18013c8ac  push    r12
0x18013c8ae  push    r14
0x18013c8b0  push    r15
0x18013c8b2  lea     rbp, [rsp-37h]
0x18013c8b7  sub     rsp, 0C0h
0x18013c8be  mov     rax, cs:__security_cookie
0x18013c8c5  xor     rax, rsp
0x18013c8c8  mov     [rbp+57h+var_28], rax
0x18013c8cc  mov     rsi, rdx
0x18013c8cf  cmp     ecx, 3
0x18013c8d2  jnz     loc_18013CA77
0x18013c8d8  inc     cs:?g_retryDelayLoadStatistics@@3URetryDelayLoadStatistics@@A; RetryDelayLoadStatistics g_retryDelayLoadStatistics
0x18013c8de  lea     ebx, [rcx-2]
0x18013c8e1  xor     r12d, r12d
0x18013c8e4  mov     rax, cs:?g_retryDelayLoadTestHook@@3P6AXIIPEBD@_EEA
0x18013c8eb  test    rax, rax
0x18013c8ee  jz      short loc_18013C8FF
0x18013c8f0  xor     r8d, r8d
0x18013c8f3  lea     edx, [r8+32h]
0x18013c8f7  mov     ecx, ebx
0x18013c8f9  call    cs:__guard_dispatch_icall_fptr
0x18013c8ff  mov     rax, cs:__pfnDliNotifyHook2
0x18013c906  test    rax, rax
0x18013c909  jz      short loc_18013C929
0x18013c90b  mov     rdx, rsi
0x18013c90e  mov     ecx, 1
0x18013c913  call    cs:__guard_dispatch_icall_fptr
0x18013c919  mov     r14, rax
0x18013c91c  lea     rdi, [rsi+18h]
0x18013c920  test    rax, rax
0x18013c923  jnz     loc_18013CAA1
0x18013c929  lea     rdi, [rsi+18h]
0x18013c92d  mov     rax, [rdi]
0x18013c930  cmp     [rax], r12b
0x18013c933  jnz     short loc_18013C93C
0x18013c935  mov     ecx, 5
0x18013c93a  int     29h; Win8: RtlFailFast(ecx)
0x18013c93c  xor     edx, edx; hFile
0x18013c93e  mov     r8d, 1000h; dwFlags
0x18013c944  mov     rcx, rax; lpLibFileName
0x18013c947  call    cs:__imp_LoadLibraryExA
0x18013c94d  mov     r14, rax
0x18013c950  test    rax, rax
0x18013c953  jnz     loc_18013CAA1
0x18013c959  mov     eax, ebx
0x18013c95b  lea     rcx, [rax+rax*4]
0x18013c95f  add     rcx, rcx
0x18013c962  mov     [rbp+57h+var_B0], rcx
0x18013c966  lea     rcx, [rbp+57h+var_B0]
0x18013c96a  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18013c96f  inc     ebx
0x18013c971  cmp     ebx, 32h ; '2'
0x18013c974  jbe     loc_18013C8E4
0x18013c97a  mov     rbx, [rdi]
0x18013c97d  lea     rcx, ModuleName; "mso20win32client.dll"
0x18013c984  call    cs:__imp_GetModuleHandleW
0x18013c98a  test    rax, rax
0x18013c98d  jnz     short loc_18013C9A5
0x18013c98f  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x18013c996  call    cs:__imp_GetModuleHandleW
0x18013c99c  test    rax, rax
0x18013c99f  jz      loc_18013CA4E
0x18013c9a5  mov     rdx, rbx
0x18013c9a8  lea     rcx, [rbp+57h+Src]; Src
0x18013c9ac  call    sub_18013CBD0
0x18013c9b1  cmp     qword ptr [rax+18h], 7
0x18013c9b6  jbe     short loc_18013C9BB
0x18013c9b8  mov     rax, [rax]
0x18013c9bb  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18013c9c2  mov     [rbp+57h+var_88], rcx
0x18013c9c6  lea     rcx, aDllname; "DllName"
0x18013c9cd  mov     [rbp+57h+var_80], rcx
0x18013c9d1  mov     [rbp+57h+var_78], rax
0x18013c9d5  mov     [rbp+57h+var_70], r12w
0x18013c9da  xor     r9d, r9d
0x18013c9dd  lea     esi, [r9+0Ah]
0x18013c9e1  mov     r8d, esi
0x18013c9e4  lea     ebx, [rsi+29h]
0x18013c9e7  mov     edx, ebx
0x18013c9e9  mov     r14d, 30566D9h
0x18013c9ef  mov     ecx, r14d
0x18013c9f2  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18013c9f8  test    al, al
0x18013c9fa  jz      short loc_18013CA45
0x18013c9fc  lea     rax, [rbp+57h+var_88]
0x18013ca00  mov     [rbp+57h+var_B0], rax
0x18013ca04  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18013ca0b  mov     [rbp+57h+var_A0], rax
0x18013ca0f  lea     rax, [rbp+57h+var_B0]
0x18013ca13  mov     [rbp+57h+var_98], rax
0x18013ca17  lea     rax, [rbp+57h+var_A8]
0x18013ca1b  mov     [rbp+57h+var_90], rax
0x18013ca1f  xor     r9d, r9d
0x18013ca22  lea     rax, [rbp+57h+var_A0]
0x18013ca26  mov     [rsp+0E0h+var_B8], rax
0x18013ca2b  lea     rax, aDelayloadretry_0; "DelayloadRetryError"
0x18013ca32  mov     [rsp+0E0h+var_C0], rax
0x18013ca37  mov     r8d, esi
0x18013ca3a  mov     edx, ebx
0x18013ca3c  mov     ecx, r14d
0x18013ca3f  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18013ca45  lea     rcx, [rbp+57h+Src]; void *
0x18013ca49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18013ca4e  inc     cs:dword_180195018
0x18013ca54  lea     r8, word_180155DB6
0x18013ca5b  cmp     [rdi], r12
0x18013ca5e  cmovnz  r8, [rdi]; Source
0x18013ca62  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18013ca66  lea     edx, [r9+65h]; SizeInBytes
0x18013ca6a  lea     rcx, Destination; Destination
0x18013ca71  call    cs:__imp_strncpy_s
0x18013ca77  xor     eax, eax
0x18013ca79  mov     rcx, [rbp+57h+var_28]
0x18013ca7d  xor     rcx, rsp; StackCookie
0x18013ca80  call    __security_check_cookie
0x18013ca85  lea     r11, [rsp+0E0h+var_20]
0x18013ca8d  mov     rbx, [r11+30h]
0x18013ca91  mov     rsi, [r11+40h]
0x18013ca95  mov     rsp, r11
0x18013ca98  pop     r15
0x18013ca9a  pop     r14
0x18013ca9c  pop     r12
0x18013ca9e  pop     rdi
0x18013ca9f  pop     rbp
0x18013caa0  retn
0x18013caa1  mov     rsi, [rdi]
0x18013caa4  lea     rcx, ModuleName; "mso20win32client.dll"
0x18013caab  call    cs:__imp_GetModuleHandleW
0x18013cab1  test    rax, rax
0x18013cab4  jnz     short loc_18013CACC
0x18013cab6  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x18013cabd  call    cs:__imp_GetModuleHandleW
0x18013cac3  test    rax, rax
0x18013cac6  jz      loc_18013CB9B
0x18013cacc  mov     rdx, rsi
0x18013cacf  lea     rcx, [rbp+57h+var_48]; Src
0x18013cad3  call    sub_18013CBD0
0x18013cad8  cmp     qword ptr [rax+18h], 7
0x18013cadd  jbe     short loc_18013CAE2
0x18013cadf  mov     rax, [rax]
0x18013cae2  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18013cae9  mov     [rbp+57h+Src], rcx
0x18013caed  lea     rcx, aDllname; "DllName"
0x18013caf4  mov     [rbp+57h+var_60], rcx
0x18013caf8  mov     [rbp+57h+var_58], rax
0x18013cafc  mov     [rbp+57h+var_50], r12w
0x18013cb01  lea     rax, ??_7StructuredErrorCode@Logging@Mso@@6B@; const Mso::Logging::StructuredErrorCode::`vftable'
0x18013cb08  mov     [rbp+57h+var_A0], rax
0x18013cb0c  lea     rax, aNumretries; "NumRetries"
0x18013cb13  mov     [rbp+57h+var_98], rax
0x18013cb17  mov     dword ptr [rbp+57h+var_90], ebx
0x18013cb1a  mov     word ptr [rbp+57h+var_90+4], r12w
0x18013cb1f  xor     r9d, r9d
0x18013cb22  lea     esi, [r9+32h]
0x18013cb26  mov     r8d, esi
0x18013cb29  lea     ebx, [rsi+1]
0x18013cb2c  mov     edx, ebx
0x18013cb2e  mov     r15d, 30566D8h
0x18013cb34  mov     ecx, r15d
0x18013cb37  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18013cb3d  test    al, al
0x18013cb3f  jz      short loc_18013CB92
0x18013cb41  lea     rax, [rbp+57h+var_A0]
0x18013cb45  mov     [rbp+57h+var_B0], rax
0x18013cb49  lea     rax, [rbp+57h+Src]
0x18013cb4d  mov     [rbp+57h+var_A8], rax
0x18013cb51  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18013cb58  mov     [rbp+57h+var_88], rax
0x18013cb5c  lea     rax, [rbp+57h+var_B0]
0x18013cb60  mov     [rbp+57h+var_80], rax
0x18013cb64  lea     rax, [rbp+57h+var_A0]
0x18013cb68  mov     [rbp+57h+var_78], rax
0x18013cb6c  xor     r9d, r9d
0x18013cb6f  lea     rax, [rbp+57h+var_88]
0x18013cb73  mov     [rsp+0E0h+var_B8], rax
0x18013cb78  lea     rax, aDelayloadretry; "DelayloadRetry"
0x18013cb7f  mov     [rsp+0E0h+var_C0], rax
0x18013cb84  mov     r8d, esi
0x18013cb87  mov     edx, ebx
0x18013cb89  mov     ecx, r15d
0x18013cb8c  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18013cb92  lea     rcx, [rbp+57h+var_48]; void *
0x18013cb96  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18013cb9b  inc     cs:dword_180195014
0x18013cba1  lea     r8, word_180155DB6
0x18013cba8  cmp     [rdi], r12
0x18013cbab  cmovnz  r8, [rdi]; Source
0x18013cbaf  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18013cbb3  lea     edx, [r9+65h]; SizeInBytes
0x18013cbb7  lea     rcx, byte_18019501C; Destination
0x18013cbbe  call    cs:__imp_strncpy_s
0x18013cbc4  mov     rax, r14
0x18013cbc7  jmp     loc_18013CA79
```

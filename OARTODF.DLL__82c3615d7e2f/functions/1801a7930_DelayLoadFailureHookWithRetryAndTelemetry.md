# DelayLoadFailureHookWithRetryAndTelemetry

- ea: `0x1801a7930`
- end: `0x1801a7c5d`
- name: `DelayLoadFailureHookWithRetryAndTelemetry`
- size: `813`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800025a0`
- `0x18000aba4`
- `0x1801a7930`
- `0x1801a7dfc`
- `0x1801a7f0c`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1801a79d7`
- `KERNEL32!LoadLibraryExA` at `0x1801a79d7`
- `KERNEL32!GetModuleHandleW` at `0x1801a7a14`
- `KERNEL32!GetModuleHandleW` at `0x1801a7a26`
- `KERNEL32!GetModuleHandleW` at `0x1801a7b3b`
- `KERNEL32!GetModuleHandleW` at `0x1801a7b4d`
- `KERNEL32!GetModuleHandleW` at `0x1801a7a14`
- `KERNEL32!GetModuleHandleW` at `0x1801a7a26`
- `KERNEL32!GetModuleHandleW` at `0x1801a7b3b`
- `KERNEL32!GetModuleHandleW` at `0x1801a7b4d`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801a7b01`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801a7c4e`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801a7b01`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1801a7c4e`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a7a82`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a7bc7`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a7a82`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a7bc7`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a7acf`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a7c1c`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a7acf`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a7c1c`

## string_xrefs

- `0x1801a7a1f`: `mso20win32server.dll`
- `0x1801a7b46`: `mso20win32server.dll`
- `0x1801a7a56`: `DllName`
- `0x1801a7b7d`: `DllName`
- `0x1801a7a0d`: `mso20win32client.dll`
- `0x1801a7b34`: `mso20win32client.dll`

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
        v6 = (void **)sub_1801A7F0C(Src);
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
      ++dword_180271698;
      v7 = (const char *)&word_18020F34E;
      if ( *p_szDll )
        v7 = *p_szDll;
      strncpy_s(Destination, 0x64u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
  {
    v9 = (_QWORD *)sub_1801A7F0C(v22);
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    Src[0] = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    Src[1] = L"DllName";
    Src[2] = v9;
    v21 = 0;
    v13 = &Mso::Logging::StructuredObject<int,1>::`vftable';
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
  ++dword_180271694;
  v10 = (const char *)&word_18020F34E;
  if ( *p_szDll )
    v10 = *p_szDll;
  strncpy_s(byte_18027169C, 0x64u, v10, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x1801a7930  mov     [rsp-8+arg_0], rbx
0x1801a7935  mov     [rsp-8+arg_10], rsi
0x1801a793a  push    rbp
0x1801a793b  push    rdi
0x1801a793c  push    r12
0x1801a793e  push    r14
0x1801a7940  push    r15
0x1801a7942  lea     rbp, [rsp-37h]
0x1801a7947  sub     rsp, 0C0h
0x1801a794e  mov     rax, cs:__security_cookie
0x1801a7955  xor     rax, rsp
0x1801a7958  mov     [rbp+57h+var_28], rax
0x1801a795c  mov     rsi, rdx
0x1801a795f  cmp     ecx, 3
0x1801a7962  jnz     loc_1801A7B07
0x1801a7968  inc     cs:?g_retryDelayLoadStatistics@@3URetryDelayLoadStatistics@@A; RetryDelayLoadStatistics g_retryDelayLoadStatistics
0x1801a796e  lea     ebx, [rcx-2]
0x1801a7971  xor     r12d, r12d
0x1801a7974  mov     rax, cs:?g_retryDelayLoadTestHook@@3P6AXIIPEBD@_EEA
0x1801a797b  test    rax, rax
0x1801a797e  jz      short loc_1801A798F
0x1801a7980  xor     r8d, r8d
0x1801a7983  lea     edx, [r8+32h]
0x1801a7987  mov     ecx, ebx
0x1801a7989  call    cs:__guard_dispatch_icall_fptr
0x1801a798f  mov     rax, cs:__pfnDliNotifyHook2
0x1801a7996  test    rax, rax
0x1801a7999  jz      short loc_1801A79B9
0x1801a799b  mov     rdx, rsi
0x1801a799e  mov     ecx, 1
0x1801a79a3  call    cs:__guard_dispatch_icall_fptr
0x1801a79a9  mov     r14, rax
0x1801a79ac  lea     rdi, [rsi+18h]
0x1801a79b0  test    rax, rax
0x1801a79b3  jnz     loc_1801A7B31
0x1801a79b9  lea     rdi, [rsi+18h]
0x1801a79bd  mov     rax, [rdi]
0x1801a79c0  cmp     [rax], r12b
0x1801a79c3  jnz     short loc_1801A79CC
0x1801a79c5  mov     ecx, 5
0x1801a79ca  int     29h; Win8: RtlFailFast(ecx)
0x1801a79cc  xor     edx, edx; hFile
0x1801a79ce  mov     r8d, 1000h; dwFlags
0x1801a79d4  mov     rcx, rax; lpLibFileName
0x1801a79d7  call    cs:__imp_LoadLibraryExA
0x1801a79dd  mov     r14, rax
0x1801a79e0  test    rax, rax
0x1801a79e3  jnz     loc_1801A7B31
0x1801a79e9  mov     eax, ebx
0x1801a79eb  lea     rcx, [rax+rax*4]
0x1801a79ef  add     rcx, rcx
0x1801a79f2  mov     [rbp+57h+var_B0], rcx
0x1801a79f6  lea     rcx, [rbp+57h+var_B0]
0x1801a79fa  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801a79ff  inc     ebx
0x1801a7a01  cmp     ebx, 32h ; '2'
0x1801a7a04  jbe     loc_1801A7974
0x1801a7a0a  mov     rbx, [rdi]
0x1801a7a0d  lea     rcx, aMso20win32clie_0; "mso20win32client.dll"
0x1801a7a14  call    cs:__imp_GetModuleHandleW
0x1801a7a1a  test    rax, rax
0x1801a7a1d  jnz     short loc_1801A7A35
0x1801a7a1f  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x1801a7a26  call    cs:__imp_GetModuleHandleW
0x1801a7a2c  test    rax, rax
0x1801a7a2f  jz      loc_1801A7ADE
0x1801a7a35  mov     rdx, rbx
0x1801a7a38  lea     rcx, [rbp+57h+Src]; Src
0x1801a7a3c  call    sub_1801A7F0C
0x1801a7a41  cmp     qword ptr [rax+18h], 7
0x1801a7a46  jbe     short loc_1801A7A4B
0x1801a7a48  mov     rax, [rax]
0x1801a7a4b  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x1801a7a52  mov     [rbp+57h+var_88], rcx
0x1801a7a56  lea     rcx, aDllname; "DllName"
0x1801a7a5d  mov     [rbp+57h+var_80], rcx
0x1801a7a61  mov     [rbp+57h+var_78], rax
0x1801a7a65  mov     [rbp+57h+var_70], r12w
0x1801a7a6a  xor     r9d, r9d
0x1801a7a6d  lea     esi, [r9+0Ah]
0x1801a7a71  mov     r8d, esi
0x1801a7a74  lea     ebx, [rsi+29h]
0x1801a7a77  mov     edx, ebx
0x1801a7a79  mov     r14d, 30566D9h
0x1801a7a7f  mov     ecx, r14d
0x1801a7a82  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x1801a7a88  test    al, al
0x1801a7a8a  jz      short loc_1801A7AD5
0x1801a7a8c  lea     rax, [rbp+57h+var_88]
0x1801a7a90  mov     [rbp+57h+var_B0], rax
0x1801a7a94  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1801a7a9b  mov     [rbp+57h+var_A0], rax
0x1801a7a9f  lea     rax, [rbp+57h+var_B0]
0x1801a7aa3  mov     [rbp+57h+var_98], rax
0x1801a7aa7  lea     rax, [rbp+57h+var_A8]
0x1801a7aab  mov     [rbp+57h+var_90], rax
0x1801a7aaf  xor     r9d, r9d
0x1801a7ab2  lea     rax, [rbp+57h+var_A0]
0x1801a7ab6  mov     [rsp+0E0h+var_B8], rax
0x1801a7abb  lea     rax, aDelayloadretry_0; "DelayloadRetryError"
0x1801a7ac2  mov     [rsp+0E0h+var_C0], rax
0x1801a7ac7  mov     r8d, esi
0x1801a7aca  mov     edx, ebx
0x1801a7acc  mov     ecx, r14d
0x1801a7acf  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x1801a7ad5  lea     rcx, [rbp+57h+Src]
0x1801a7ad9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a7ade  inc     cs:dword_180271698
0x1801a7ae4  lea     r8, word_18020F34E
0x1801a7aeb  cmp     [rdi], r12
0x1801a7aee  cmovnz  r8, [rdi]; Source
0x1801a7af2  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1801a7af6  lea     edx, [r9+65h]; SizeInBytes
0x1801a7afa  lea     rcx, Destination; Destination
0x1801a7b01  call    cs:__imp_strncpy_s
0x1801a7b07  xor     eax, eax
0x1801a7b09  mov     rcx, [rbp+57h+var_28]
0x1801a7b0d  xor     rcx, rsp; StackCookie
0x1801a7b10  call    __security_check_cookie
0x1801a7b15  lea     r11, [rsp+0E0h+var_20]
0x1801a7b1d  mov     rbx, [r11+30h]
0x1801a7b21  mov     rsi, [r11+40h]
0x1801a7b25  mov     rsp, r11
0x1801a7b28  pop     r15
0x1801a7b2a  pop     r14
0x1801a7b2c  pop     r12
0x1801a7b2e  pop     rdi
0x1801a7b2f  pop     rbp
0x1801a7b30  retn
0x1801a7b31  mov     rsi, [rdi]
0x1801a7b34  lea     rcx, aMso20win32clie_0; "mso20win32client.dll"
0x1801a7b3b  call    cs:__imp_GetModuleHandleW
0x1801a7b41  test    rax, rax
0x1801a7b44  jnz     short loc_1801A7B5C
0x1801a7b46  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x1801a7b4d  call    cs:__imp_GetModuleHandleW
0x1801a7b53  test    rax, rax
0x1801a7b56  jz      loc_1801A7C2B
0x1801a7b5c  mov     rdx, rsi
0x1801a7b5f  lea     rcx, [rbp+57h+var_48]; Src
0x1801a7b63  call    sub_1801A7F0C
0x1801a7b68  cmp     qword ptr [rax+18h], 7
0x1801a7b6d  jbe     short loc_1801A7B72
0x1801a7b6f  mov     rax, [rax]
0x1801a7b72  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x1801a7b79  mov     [rbp+57h+Src], rcx
0x1801a7b7d  lea     rcx, aDllname; "DllName"
0x1801a7b84  mov     [rbp+57h+var_60], rcx
0x1801a7b88  mov     [rbp+57h+var_58], rax
0x1801a7b8c  mov     [rbp+57h+var_50], r12w
0x1801a7b91  lea     rax, ??_7?$StructuredObject@H$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<int,1>::`vftable'
0x1801a7b98  mov     [rbp+57h+var_A0], rax
0x1801a7b9c  lea     rax, aNumretries; "NumRetries"
0x1801a7ba3  mov     [rbp+57h+var_98], rax
0x1801a7ba7  mov     dword ptr [rbp+57h+var_90], ebx
0x1801a7baa  mov     word ptr [rbp+57h+var_90+4], r12w
0x1801a7baf  xor     r9d, r9d
0x1801a7bb2  lea     esi, [r9+32h]
0x1801a7bb6  mov     r8d, esi
0x1801a7bb9  lea     ebx, [rsi+1]
0x1801a7bbc  mov     edx, ebx
0x1801a7bbe  mov     r15d, 30566D8h
0x1801a7bc4  mov     ecx, r15d
0x1801a7bc7  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x1801a7bcd  test    al, al
0x1801a7bcf  jz      short loc_1801A7C22
0x1801a7bd1  lea     rax, [rbp+57h+var_A0]
0x1801a7bd5  mov     [rbp+57h+var_B0], rax
0x1801a7bd9  lea     rax, [rbp+57h+Src]
0x1801a7bdd  mov     [rbp+57h+var_A8], rax
0x1801a7be1  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1801a7be8  mov     [rbp+57h+var_88], rax
0x1801a7bec  lea     rax, [rbp+57h+var_B0]
0x1801a7bf0  mov     [rbp+57h+var_80], rax
0x1801a7bf4  lea     rax, [rbp+57h+var_A0]
0x1801a7bf8  mov     [rbp+57h+var_78], rax
0x1801a7bfc  xor     r9d, r9d
0x1801a7bff  lea     rax, [rbp+57h+var_88]
0x1801a7c03  mov     [rsp+0E0h+var_B8], rax
0x1801a7c08  lea     rax, aDelayloadretry; "DelayloadRetry"
0x1801a7c0f  mov     [rsp+0E0h+var_C0], rax
0x1801a7c14  mov     r8d, esi
0x1801a7c17  mov     edx, ebx
0x1801a7c19  mov     ecx, r15d
0x1801a7c1c  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x1801a7c22  lea     rcx, [rbp+57h+var_48]
0x1801a7c26  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a7c2b  inc     cs:dword_180271694
0x1801a7c31  lea     r8, word_18020F34E
0x1801a7c38  cmp     [rdi], r12
0x1801a7c3b  cmovnz  r8, [rdi]; Source
0x1801a7c3f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1801a7c43  lea     edx, [r9+65h]; SizeInBytes
0x1801a7c47  lea     rcx, byte_18027169C; Destination
0x1801a7c4e  call    cs:__imp_strncpy_s
0x1801a7c54  mov     rax, r14
0x1801a7c57  jmp     loc_1801A7B09
```

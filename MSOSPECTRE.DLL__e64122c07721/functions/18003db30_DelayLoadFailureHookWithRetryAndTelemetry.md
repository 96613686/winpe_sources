# DelayLoadFailureHookWithRetryAndTelemetry

- ea: `0x18003db30`
- end: `0x18003deb7`
- name: `DelayLoadFailureHookWithRetryAndTelemetry`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016350`
- `0x18003da60`
- `0x18003db30`
- `0x18003dec0`
- `0x18003df7c`
- `0x18039e5b0`
- `0x1803a0f88`
- `0x1804f99e0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18003dbdc`
- `KERNEL32!LoadLibraryExA` at `0x18003dbdc`
- `KERNEL32!GetModuleHandleW` at `0x18003dc6a`
- `KERNEL32!GetModuleHandleW` at `0x18003dc7c`
- `KERNEL32!GetModuleHandleW` at `0x18003dd96`
- `KERNEL32!GetModuleHandleW` at `0x18003dda8`
- `KERNEL32!GetModuleHandleW` at `0x18003dc6a`
- `KERNEL32!GetModuleHandleW` at `0x18003dc7c`
- `KERNEL32!GetModuleHandleW` at `0x18003dd96`
- `KERNEL32!GetModuleHandleW` at `0x18003dda8`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18003dcd8`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18003de22`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18003dcd8`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18003de22`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18003dd25`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18003de77`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18003dd25`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x18003de77`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18003dd57`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18003dea9`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18003dd57`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18003dea9`

## string_xrefs

- `0x18003dc63`: `mso20win32client.dll`
- `0x18003dd8f`: `mso20win32client.dll`
- `0x18003dcac`: `DllName`
- `0x18003ddd8`: `DllName`
- `0x18003dc75`: `mso20win32server.dll`
- `0x18003dda1`: `mso20win32server.dll`

## pseudocode

```c
HMODULE __fastcall DelayLoadFailureHookWithRetryAndTelemetry(int a1, struct DelayLoadInfo *a2)
{
  unsigned int v3; // edi
  HMODULE Library; // r15
  const char **p_szDll; // rsi
  __int64 v6; // rbx
  DWORD v7; // eax
  void **v8; // rax
  const char *v9; // r8
  _QWORD *v11; // rax
  const char *v12; // r8
  void ***v13; // [rsp+38h] [rbp-69h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-61h] BYREF
  void **v15; // [rsp+50h] [rbp-51h] BYREF
  void ****v16; // [rsp+58h] [rbp-49h]
  _QWORD *v17; // [rsp+60h] [rbp-41h]
  void **v18; // [rsp+68h] [rbp-39h] BYREF
  const wchar_t *v19; // [rsp+70h] [rbp-31h]
  void ***v20; // [rsp+78h] [rbp-29h]
  __int16 v21; // [rsp+80h] [rbp-21h]
  __int64 v22; // [rsp+88h] [rbp-19h] BYREF
  _QWORD Src[3]; // [rsp+90h] [rbp-11h] BYREF
  __int16 v24; // [rsp+A8h] [rbp+7h]
  _BYTE v25[32]; // [rsp+B0h] [rbp+Fh] BYREF

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
    std::chrono::steady_clock::now(&v13);
    v6 = (__int64)v13;
    if ( v3 )
    {
      if ( (__int64)v13 >= 0x7FFFFFFFFFFFFFFFLL - 10000000LL * v3 )
        v6 = 0x7FFFFFFFFFFFFFFFLL;
      else
        v6 = (__int64)&v13[1250000 * v3];
    }
    while ( 1 )
    {
      std::chrono::steady_clock::now(&v22);
      if ( v6 == v22 || v6 < v22 )
        break;
      v14[0] = v6 - v22;
      v7 = std::_Clamped_rel_time_ms_count<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v14);
      Thrd_sleep_for(v7);
    }
    if ( ++v3 > 0x32 )
    {
      if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
      {
        v8 = (void **)sub_18003DF7C(Src);
        if ( (unsigned __int64)v8[3] > 7 )
          v8 = (void **)*v8;
        v18 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
        v19 = L"DllName";
        v20 = (void ***)v8;
        v21 = 0;
        if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(50685657, 51, 10) )
        {
          v13 = &v18;
          v15 = &Mso::Logging::CompositeStructuredTrace::`vftable';
          v16 = &v13;
          v17 = v14;
          Mso::Logging::MsoSendStructuredTraceTag(50685657, 51, 10, 0, L"DelayloadRetryError", &v15);
        }
        std::wstring::_Tidy_deallocate(Src);
      }
      ++dword_1807E0A38;
      v9 = byte_1806ADF48;
      if ( *p_szDll )
        v9 = *p_szDll;
      strncpy_s(Destination, 0x64u, v9, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  if ( GetModuleHandleW(L"mso20win32client.dll") || GetModuleHandleW(L"mso20win32server.dll") )
  {
    v11 = (_QWORD *)sub_18003DF7C(v25);
    if ( v11[3] > 7u )
      v11 = (_QWORD *)*v11;
    Src[0] = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    Src[1] = L"DllName";
    Src[2] = v11;
    v24 = 0;
    v15 = &Mso::Logging::StructuredObject<int,1>::`vftable';
    v16 = (void ****)L"NumRetries";
    LODWORD(v17) = v3;
    WORD2(v17) = 0;
    if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(50685656, 51, 50) )
    {
      v14[0] = &v15;
      v14[1] = Src;
      v18 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v19 = (const wchar_t *)v14;
      v20 = &v15;
      Mso::Logging::MsoSendStructuredTraceTag(50685656, 51, 50, 0, L"DelayloadRetry", &v18);
    }
    std::wstring::_Tidy_deallocate(v25);
  }
  ++dword_1807E0A34;
  v12 = byte_1806ADF48;
  if ( *p_szDll )
    v12 = *p_szDll;
  strncpy_s(byte_1807E0A3C, 0x64u, v12, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x18003db30  mov     rax, rsp
0x18003db33  mov     [rax+8], rbx
0x18003db37  mov     [rax+18h], rsi
0x18003db3b  mov     [rax+20h], rdi
0x18003db3f  push    rbp
0x18003db40  push    r12
0x18003db42  push    r13
0x18003db44  push    r14
0x18003db46  push    r15
0x18003db48  lea     rbp, [rax-5Fh]
0x18003db4c  sub     rsp, 0D0h
0x18003db53  mov     rax, cs:__security_cookie
0x18003db5a  xor     rax, rsp
0x18003db5d  mov     [rbp+57h+var_28], rax
0x18003db61  mov     r14, rdx
0x18003db64  cmp     ecx, 3
0x18003db67  jnz     loc_18003DD5D
0x18003db6d  inc     cs:?g_retryDelayLoadStatistics@@3URetryDelayLoadStatistics@@A; RetryDelayLoadStatistics g_retryDelayLoadStatistics
0x18003db73  lea     edi, [rcx-2]
0x18003db76  xor     r13d, r13d
0x18003db79  mov     rax, cs:?g_retryDelayLoadTestHook@@3P6AXIIPEBD@_EEA
0x18003db80  test    rax, rax
0x18003db83  jz      short loc_18003DB94
0x18003db85  xor     r8d, r8d
0x18003db88  lea     edx, [r8+32h]
0x18003db8c  mov     ecx, edi
0x18003db8e  call    cs:__guard_dispatch_icall_fptr
0x18003db94  mov     rax, cs:__pfnDliNotifyHook2
0x18003db9b  test    rax, rax
0x18003db9e  jz      short loc_18003DBBE
0x18003dba0  mov     rdx, r14
0x18003dba3  mov     ecx, 1
0x18003dba8  call    cs:__guard_dispatch_icall_fptr
0x18003dbae  mov     r15, rax
0x18003dbb1  lea     rsi, [r14+18h]
0x18003dbb5  test    rax, rax
0x18003dbb8  jnz     loc_18003DD8C
0x18003dbbe  lea     rsi, [r14+18h]
0x18003dbc2  mov     rax, [rsi]
0x18003dbc5  cmp     [rax], r13b
0x18003dbc8  jnz     short loc_18003DBD1
0x18003dbca  mov     ecx, 5
0x18003dbcf  int     29h; Win8: RtlFailFast(ecx)
0x18003dbd1  xor     edx, edx; hFile
0x18003dbd3  mov     r8d, 1000h; dwFlags
0x18003dbd9  mov     rcx, rax; lpLibFileName
0x18003dbdc  call    cs:__imp_LoadLibraryExA
0x18003dbe2  mov     r15, rax
0x18003dbe5  test    rax, rax
0x18003dbe8  jnz     loc_18003DD8C
0x18003dbee  lea     rcx, [rbp+57h+var_C0]
0x18003dbf2  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18003dbf7  mov     rbx, [rbp+57h+var_C0]
0x18003dbfb  mov     eax, edi
0x18003dbfd  test    edi, edi
0x18003dbff  jz      short loc_18003DC25
0x18003dc01  imul    rcx, rax, 989680h
0x18003dc08  mov     r15, 7FFFFFFFFFFFFFFFh
0x18003dc12  mov     rax, r15
0x18003dc15  sub     rax, rcx
0x18003dc18  cmp     rbx, rax
0x18003dc1b  jge     short loc_18003DC22
0x18003dc1d  add     rbx, rcx
0x18003dc20  jmp     short loc_18003DC25
0x18003dc22  mov     rbx, r15
0x18003dc25  lea     rcx, [rbp+57h+var_70]
0x18003dc29  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18003dc2e  mov     rax, [rbp+57h+var_70]
0x18003dc32  cmp     rbx, rax
0x18003dc35  jz      short loc_18003DC55
0x18003dc37  jl      short loc_18003DC55
0x18003dc39  mov     rcx, rbx
0x18003dc3c  sub     rcx, rax
0x18003dc3f  mov     [rbp+57h+var_B8], rcx
0x18003dc43  lea     rcx, [rbp+57h+var_B8]
0x18003dc47  call    ??$_Clamped_rel_time_ms_count@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@std@@YA?AU_Clamped_rel_time_ms_count_result@0@AEBV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@0@@Z; std::_Clamped_rel_time_ms_count<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>> const &)
0x18003dc4c  mov     ecx, eax; dwMilliseconds
0x18003dc4e  call    _Thrd_sleep_for
0x18003dc53  jmp     short loc_18003DC25
0x18003dc55  inc     edi
0x18003dc57  cmp     edi, 32h ; '2'
0x18003dc5a  jbe     loc_18003DB79
0x18003dc60  mov     rbx, [rsi]
0x18003dc63  lea     rcx, ModuleName; "mso20win32client.dll"
0x18003dc6a  call    cs:__imp_GetModuleHandleW
0x18003dc70  test    rax, rax
0x18003dc73  jnz     short loc_18003DC8B
0x18003dc75  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x18003dc7c  call    cs:__imp_GetModuleHandleW
0x18003dc82  test    rax, rax
0x18003dc85  jz      loc_18003DD34
0x18003dc8b  mov     rdx, rbx
0x18003dc8e  lea     rcx, [rbp+57h+Src]; Src
0x18003dc92  call    sub_18003DF7C
0x18003dc97  cmp     qword ptr [rax+18h], 7
0x18003dc9c  jbe     short loc_18003DCA1
0x18003dc9e  mov     rax, [rax]
0x18003dca1  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18003dca8  mov     [rbp+57h+var_90], rcx
0x18003dcac  lea     rcx, aDllname; "DllName"
0x18003dcb3  mov     [rbp+57h+var_88], rcx
0x18003dcb7  mov     [rbp+57h+var_80], rax
0x18003dcbb  mov     [rbp+57h+var_78], r13w
0x18003dcc0  xor     r9d, r9d
0x18003dcc3  lea     edi, [r9+0Ah]
0x18003dcc7  mov     r8d, edi
0x18003dcca  lea     ebx, [rdi+29h]
0x18003dccd  mov     edx, ebx
0x18003dccf  mov     r14d, 30566D9h
0x18003dcd5  mov     ecx, r14d
0x18003dcd8  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18003dcde  test    al, al
0x18003dce0  jz      short loc_18003DD2B
0x18003dce2  lea     rax, [rbp+57h+var_90]
0x18003dce6  mov     [rbp+57h+var_C0], rax
0x18003dcea  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18003dcf1  mov     [rbp+57h+var_A8], rax
0x18003dcf5  lea     rax, [rbp+57h+var_C0]
0x18003dcf9  mov     [rbp+57h+var_A0], rax
0x18003dcfd  lea     rax, [rbp+57h+var_B8]
0x18003dd01  mov     [rbp+57h+var_98], rax
0x18003dd05  xor     r9d, r9d
0x18003dd08  lea     rax, [rbp+57h+var_A8]
0x18003dd0c  mov     [rsp+0F0h+var_C8], rax
0x18003dd11  lea     rax, aDelayloadretry_0; "DelayloadRetryError"
0x18003dd18  mov     [rsp+0F0h+var_D0], rax
0x18003dd1d  mov     r8d, edi
0x18003dd20  mov     edx, ebx
0x18003dd22  mov     ecx, r14d
0x18003dd25  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18003dd2b  lea     rcx, [rbp+57h+Src]
0x18003dd2f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dd34  inc     cs:dword_1807E0A38
0x18003dd3a  lea     r8, byte_1806ADF48
0x18003dd41  cmp     [rsi], r13
0x18003dd44  cmovnz  r8, [rsi]; Source
0x18003dd48  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18003dd4c  lea     edx, [r9+65h]; SizeInBytes
0x18003dd50  lea     rcx, Destination; Destination
0x18003dd57  call    cs:__imp_strncpy_s
0x18003dd5d  xor     eax, eax
0x18003dd5f  mov     rcx, [rbp+57h+var_28]
0x18003dd63  xor     rcx, rsp; StackCookie
0x18003dd66  call    __security_check_cookie
0x18003dd6b  lea     r11, [rsp+0F0h+var_20]
0x18003dd73  mov     rbx, [r11+30h]
0x18003dd77  mov     rsi, [r11+40h]
0x18003dd7b  mov     rdi, [r11+48h]
0x18003dd7f  mov     rsp, r11
0x18003dd82  pop     r15
0x18003dd84  pop     r14
0x18003dd86  pop     r13
0x18003dd88  pop     r12
0x18003dd8a  pop     rbp
0x18003dd8b  retn
0x18003dd8c  mov     rbx, [rsi]
0x18003dd8f  lea     rcx, ModuleName; "mso20win32client.dll"
0x18003dd96  call    cs:__imp_GetModuleHandleW
0x18003dd9c  test    rax, rax
0x18003dd9f  jnz     short loc_18003DDB7
0x18003dda1  lea     rcx, aMso20win32serv; "mso20win32server.dll"
0x18003dda8  call    cs:__imp_GetModuleHandleW
0x18003ddae  test    rax, rax
0x18003ddb1  jz      loc_18003DE86
0x18003ddb7  mov     rdx, rbx
0x18003ddba  lea     rcx, [rbp+57h+var_48]; Src
0x18003ddbe  call    sub_18003DF7C
0x18003ddc3  cmp     qword ptr [rax+18h], 7
0x18003ddc8  jbe     short loc_18003DDCD
0x18003ddca  mov     rax, [rax]
0x18003ddcd  lea     rcx, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18003ddd4  mov     [rbp+57h+Src], rcx
0x18003ddd8  lea     rcx, aDllname; "DllName"
0x18003dddf  mov     [rbp+57h+var_60], rcx
0x18003dde3  mov     [rbp+57h+var_58], rax
0x18003dde7  mov     [rbp+57h+var_50], r13w
0x18003ddec  lea     rax, ??_7?$StructuredObject@H$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<int,1>::`vftable'
0x18003ddf3  mov     [rbp+57h+var_A8], rax
0x18003ddf7  lea     rax, aNumretries; "NumRetries"
0x18003ddfe  mov     [rbp+57h+var_A0], rax
0x18003de02  mov     dword ptr [rbp+57h+var_98], edi
0x18003de05  mov     word ptr [rbp+57h+var_98+4], r13w
0x18003de0a  xor     r9d, r9d
0x18003de0d  lea     edi, [r9+32h]
0x18003de11  mov     r8d, edi
0x18003de14  lea     ebx, [rdi+1]
0x18003de17  mov     edx, ebx
0x18003de19  mov     r14d, 30566D8h
0x18003de1f  mov     ecx, r14d
0x18003de22  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18003de28  test    al, al
0x18003de2a  jz      short loc_18003DE7D
0x18003de2c  lea     rax, [rbp+57h+var_A8]
0x18003de30  mov     [rbp+57h+var_B8], rax
0x18003de34  lea     rax, [rbp+57h+Src]
0x18003de38  mov     [rbp+57h+var_B0], rax
0x18003de3c  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18003de43  mov     [rbp+57h+var_90], rax
0x18003de47  lea     rax, [rbp+57h+var_B8]
0x18003de4b  mov     [rbp+57h+var_88], rax
0x18003de4f  lea     rax, [rbp+57h+var_A8]
0x18003de53  mov     [rbp+57h+var_80], rax
0x18003de57  xor     r9d, r9d
0x18003de5a  lea     rax, [rbp+57h+var_90]
0x18003de5e  mov     [rsp+0F0h+var_C8], rax
0x18003de63  lea     rax, aDelayloadretry; "DelayloadRetry"
0x18003de6a  mov     [rsp+0F0h+var_D0], rax
0x18003de6f  mov     r8d, edi
0x18003de72  mov     edx, ebx
0x18003de74  mov     ecx, r14d
0x18003de77  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,Mso::Logging::IStructuredTrace const &)
0x18003de7d  lea     rcx, [rbp+57h+var_48]
0x18003de81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003de86  inc     cs:dword_1807E0A34
0x18003de8c  lea     r8, byte_1806ADF48
0x18003de93  cmp     [rsi], r13
0x18003de96  cmovnz  r8, [rsi]; Source
0x18003de9a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18003de9e  lea     edx, [r9+65h]; SizeInBytes
0x18003dea2  lea     rcx, byte_1807E0A3C; Destination
0x18003dea9  call    cs:__imp_strncpy_s
0x18003deaf  mov     rax, r15
0x18003deb2  jmp     loc_18003DD5F
```

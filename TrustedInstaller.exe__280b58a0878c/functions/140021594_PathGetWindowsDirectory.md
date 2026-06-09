# PathGetWindowsDirectory

- ea: `0x140021594`
- end: `0x140021804`
- name: `PathGetWindowsDirectory`
- size: `624`
- prototype: `__int64 __fastcall(LPWSTR *, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140016210`
- `0x140017ecc`
- `0x140018630`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016fb4`
- `0x1400184fc`
- `0x14001c7a8`
- `0x14001c9a0`
- `0x14001dc7c`
- `0x140021594`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002163c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002163c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021704`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002162c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400216fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002162c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400216fa`

## string_xrefs

- `0x1400215e3`: `No path result specified`
- `0x140021658`: `Failed to get windows directory.`
- `0x14002171d`: `Failed to get windows directory.`
- `0x1400216b2`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400216e3`: `onecore\base\cbs\util\cbspath.cpp`

## pseudocode

```c
__int64 __fastcall PathGetWindowsDirectory(LPWSTR *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // r9
  __int64 v7; // rdx
  UINT SystemWindowsDirectoryW; // eax
  UINT v9; // esi
  signed int LastError; // ebx
  int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  UINT v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  unsigned __int64 v19; // rdx
  unsigned int v21; // [rsp+20h] [rbp-30h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v23[2]; // [rsp+38h] [rbp-18h] BYREF
  int v24; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  lpBuffer = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v24 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path result specified");
      *(_QWORD *)v23 = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v23);
    }
    v6 = 2147500035LL;
    v7 = 180;
    goto LABEL_18;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v9 = SystemWindowsDirectoryW;
  if ( SystemWindowsDirectoryW )
  {
    v15 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
    v4 = v15;
    if ( v15 < 0 )
    {
      v7 = 184;
LABEL_17:
      v6 = (unsigned int)v15;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)v6,
        v21);
      goto LABEL_36;
    }
    v16 = GetSystemWindowsDirectoryW(lpBuffer, v9);
    if ( v16 )
    {
      if ( v16 >= v9 )
      {
        v14 = 122;
        v13 = 192;
        goto LABEL_14;
      }
      SczEnsureBackslashTerminated(&lpBuffer);
      if ( !a2 )
      {
        if ( *a1 )
          operator delete(*a1 - 4, v19);
        *a1 = lpBuffer;
        lpBuffer = 0;
        goto LABEL_35;
      }
      v15 = SczAllocConcat2Sz(a1, lpBuffer, a2);
      v4 = v15;
      if ( v15 < 0 )
      {
        v7 = 198;
        goto LABEL_17;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        v24 = v18;
        *(_QWORD *)v23 = &v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v17,
          3,
          (unsigned int)": {0}",
          (__int64)v23);
      }
      if ( LastError )
      {
        v13 = 188;
        goto LABEL_13;
      }
    }
LABEL_35:
    v4 = 0;
    goto LABEL_36;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, v9 + 3, "Failed to get windows directory.");
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
    v24 = v12;
    *(_QWORD *)v23 = &v24;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v11,
      v9 + 3,
      (unsigned int)": {0}",
      (__int64)v23);
  }
  if ( !LastError )
    goto LABEL_35;
  v13 = 183;
LABEL_13:
  v14 = (unsigned int)LastError;
LABEL_14:
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v13,
         (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
         (const char *)v14,
         v21);
LABEL_36:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return v4;
}

```

## disassembly

```asm
0x140021594  mov     [rsp-18h+arg_10], rbx
0x140021599  mov     [rsp-18h+arg_18], rsi
0x14002159e  push    rbp
0x14002159f  push    rdi
0x1400215a0  push    r14
0x1400215a2  mov     rbp, rsp
0x1400215a5  sub     rsp, 50h
0x1400215a9  mov     rax, cs:__security_cookie
0x1400215b0  xor     rax, rsp
0x1400215b3  mov     [rbp+var_8], rax
0x1400215b7  mov     [rbp+lpBuffer], 0
0x1400215bf  mov     r14, rdx
0x1400215c2  mov     rdi, rcx
0x1400215c5  test    rcx, rcx
0x1400215c8  jnz     short loc_140021628
0x1400215ca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400215d1  mov     ebx, 80004003h
0x1400215d6  mov     [rbp+var_10], ebx
0x1400215d9  test    rcx, rcx
0x1400215dc  jz      short loc_14002161B
0x1400215de  mov     edi, 3
0x1400215e3  lea     r9, aNoPathResultSp; "No path result specified"
0x1400215ea  mov     r8d, edi
0x1400215ed  xor     edx, edx
0x1400215ef  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400215f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400215fb  lea     rax, [rbp+var_10]
0x1400215ff  mov     qword ptr [rbp+var_18], rax
0x140021603  lea     r9, asc_1400353E8; ": {}"
0x14002160a  lea     rax, [rbp+var_18]
0x14002160e  mov     r8d, edi
0x140021611  mov     qword ptr [rsp+50h+var_30], rax
0x140021616  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002161b  mov     r9d, ebx
0x14002161e  mov     edx, 0B4h
0x140021623  jmp     loc_1400216DF
0x140021628  xor     edx, edx; uSize
0x14002162a  xor     ecx, ecx; lpBuffer
0x14002162c  call    cs:__imp_GetSystemWindowsDirectoryW
0x140021632  mov     esi, eax
0x140021634  test    eax, eax
0x140021636  jnz     loc_1400216C5
0x14002163c  call    cs:__imp_GetLastError
0x140021642  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021649  mov     ebx, eax
0x14002164b  test    rcx, rcx
0x14002164e  jz      short loc_14002169E
0x140021650  lea     edi, [rsi+3]
0x140021653  xor     edx, edx
0x140021655  mov     r8d, edi
0x140021658  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x14002165f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140021664  test    ebx, ebx
0x140021666  jg      short loc_14002166C
0x140021668  mov     eax, ebx
0x14002166a  jmp     short loc_140021674
0x14002166c  movzx   eax, bx
0x14002166f  or      eax, 80070000h
0x140021674  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002167b  lea     r9, a0; ": {0}"
0x140021682  mov     [rbp+var_10], eax
0x140021685  mov     r8d, edi
0x140021688  lea     rax, [rbp+var_10]
0x14002168c  mov     qword ptr [rbp+var_18], rax
0x140021690  lea     rax, [rbp+var_18]
0x140021694  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x140021699  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002169e  test    ebx, ebx
0x1400216a0  jz      loc_1400217D6
0x1400216a6  mov     edx, 0B7h; void *
0x1400216ab  mov     r9d, ebx; char *
0x1400216ae  mov     rcx, [rbp+18h]; this
0x1400216b2  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1400216b9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400216be  mov     ebx, eax
0x1400216c0  jmp     loc_1400217D8
0x1400216c5  lea     edx, [rax+1]
0x1400216c8  lea     rcx, [rbp+lpBuffer]
0x1400216cc  call    SczAlloc
0x1400216d1  mov     ebx, eax
0x1400216d3  test    eax, eax
0x1400216d5  jns     short loc_1400216F4
0x1400216d7  mov     edx, 0B8h; void *
0x1400216dc  mov     r9d, eax; char *
0x1400216df  mov     rcx, [rbp+18h]; this
0x1400216e3  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1400216ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400216ef  jmp     loc_1400217D8
0x1400216f4  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x1400216f8  mov     edx, esi; uSize
0x1400216fa  call    cs:__imp_GetSystemWindowsDirectoryW
0x140021700  test    eax, eax
0x140021702  jnz     short loc_140021776
0x140021704  call    cs:__imp_GetLastError
0x14002170a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021711  mov     ebx, eax
0x140021713  test    rcx, rcx
0x140021716  jz      short loc_140021768
0x140021718  mov     edi, 3
0x14002171d  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x140021724  mov     r8d, edi
0x140021727  xor     edx, edx
0x140021729  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002172e  test    ebx, ebx
0x140021730  jg      short loc_140021736
0x140021732  mov     eax, ebx
0x140021734  jmp     short loc_14002173E
0x140021736  movzx   eax, bx
0x140021739  or      eax, 80070000h
0x14002173e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021745  lea     r9, a0; ": {0}"
0x14002174c  mov     [rbp+var_10], eax
0x14002174f  mov     r8d, edi
0x140021752  lea     rax, [rbp+var_10]
0x140021756  mov     qword ptr [rbp+var_18], rax
0x14002175a  lea     rax, [rbp+var_18]
0x14002175e  mov     qword ptr [rsp+50h+var_30], rax
0x140021763  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140021768  test    ebx, ebx
0x14002176a  jz      short loc_1400217D6
0x14002176c  mov     edx, 0BCh
0x140021771  jmp     loc_1400216AB
0x140021776  cmp     eax, esi
0x140021778  jb      short loc_140021789
0x14002177a  mov     r9d, 7Ah ; 'z'
0x140021780  lea     edx, [r9+46h]
0x140021784  jmp     loc_1400216AE
0x140021789  lea     rcx, [rbp+lpBuffer]
0x14002178d  call    SczEnsureBackslashTerminated
0x140021792  test    r14, r14
0x140021795  jz      short loc_1400217B6
0x140021797  mov     rdx, [rbp+lpBuffer]
0x14002179b  mov     r8, r14
0x14002179e  mov     rcx, rdi
0x1400217a1  call    SczAllocConcat2Sz
0x1400217a6  mov     ebx, eax
0x1400217a8  test    eax, eax
0x1400217aa  jns     short loc_1400217D6
0x1400217ac  mov     edx, 0C6h
0x1400217b1  jmp     loc_1400216DC
0x1400217b6  mov     rcx, [rdi]
0x1400217b9  test    rcx, rcx
0x1400217bc  jz      short loc_1400217C7
0x1400217be  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1400217c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400217c7  mov     rax, [rbp+lpBuffer]
0x1400217cb  mov     [rdi], rax
0x1400217ce  mov     [rbp+lpBuffer], 0
0x1400217d6  xor     ebx, ebx
0x1400217d8  lea     rcx, [rbp+lpBuffer]
0x1400217dc  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400217e1  mov     eax, ebx
0x1400217e3  mov     rcx, [rbp+var_8]
0x1400217e7  xor     rcx, rsp; StackCookie
0x1400217ea  call    __security_check_cookie
0x1400217ef  lea     r11, [rsp+50h+var_s0]
0x1400217f4  mov     rbx, [r11+30h]
0x1400217f8  mov     rsi, [r11+38h]
0x1400217fc  mov     rsp, r11
0x1400217ff  pop     r14
0x140021801  pop     rdi
0x140021802  pop     rbp
0x140021803  retn
```

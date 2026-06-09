# MoveFolderToUniqueFolder(wchar_t const * const,wchar_t const * const)

- ea: `0x140018180`
- end: `0x1400183ba`
- name: `?MoveFolderToUniqueFolder@@YAJQEB_W0@Z`
- size: `570`
- prototype: `__int64 __fastcall(const WCHAR *, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140017ecc`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016de8`
- `0x140016fb4`
- `0x1400175cc`
- `0x140018180`
- `0x1400184fc`
- `0x14001d404`
- `0x14001fc6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400182f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400182f6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400182e8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400182e8`

## string_xrefs

- `0x1400181d0`: `Failed to create destination folder`
- `0x140018263`: `Failed to append guid to path`
- `0x140018319`: `Failed to move {} to {}.`

## pseudocode

```c
__int64 __fastcall MoveFolderToUniqueFolder(const WCHAR *a1, const wchar_t *a2)
{
  int Directory; // eax
  unsigned int v4; // ebx
  int v5; // edx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  int appended; // eax
  int v10; // edx
  int v11; // edx
  const WCHAR *v12; // rbx
  signed int LastError; // edi
  int v14; // edx
  unsigned int v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-40h]
  unsigned int v18[2]; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR v20; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  lpExistingFileName = a1;
  lpNewFileName = 0;
  Directory = RecursivelyCreateDirectory(a2, 0);
  v4 = Directory;
  if ( Directory < 0 )
  {
    v22 = Directory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create destination folder");
      *(_QWORD *)v18 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v18);
    }
    v6 = v4;
    v7 = 499;
    goto LABEL_7;
  }
  v8 = SczAllocFromSz(&lpNewFileName, a2);
  v4 = v8;
  if ( v8 < 0 )
  {
    v6 = (unsigned int)v8;
    v7 = 501;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)v6,
      v17);
    goto LABEL_23;
  }
  appended = AppendGuidToPath((struct AutoScz *)&lpNewFileName);
  v4 = appended;
  if ( appended < 0 )
  {
    v22 = appended;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to append guid to path");
      *(_QWORD *)v18 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v18);
    }
    v6 = v4;
    v7 = 504;
    goto LABEL_7;
  }
  v12 = lpNewFileName;
  v20 = lpNewFileName;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v10) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v10,
      1,
      (unsigned int)"Moving '{}' to '{}'",
      (__int64)&lpExistingFileName,
      (__int64)&v20);
  }
  if ( MoveFileExW(lpExistingFileName, v12, 8u) )
    goto LABEL_22;
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    v20 = v12;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to move {} to {}.",
      (__int64)&lpExistingFileName,
      (__int64)&v20);
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    else
      v15 = LastError;
    v22 = v15;
    *(_QWORD *)v18 = &v22;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v14,
      3,
      (unsigned int)": {0}",
      (__int64)v18);
  }
  if ( !LastError )
LABEL_22:
    v4 = 0;
  else
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1FC,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
           (const char *)(unsigned int)LastError,
           v17);
LABEL_23:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  return v4;
}

```

## disassembly

```asm
0x140018180  mov     [rsp-8+arg_10], rbx
0x140018185  mov     [rsp-8+arg_18], rdi
0x14001818a  push    rbp
0x14001818b  mov     rbp, rsp
0x14001818e  sub     rsp, 60h
0x140018192  mov     rax, cs:__security_cookie
0x140018199  xor     rax, rsp
0x14001819c  mov     [rbp+var_8], rax
0x1400181a0  mov     rdi, rdx
0x1400181a3  mov     [rbp+lpExistingFileName], rcx
0x1400181a7  mov     rcx, rdi
0x1400181aa  mov     [rbp+lpNewFileName], 0
0x1400181b2  xor     edx, edx
0x1400181b4  call    RecursivelyCreateDirectory
0x1400181b9  mov     ebx, eax
0x1400181bb  test    eax, eax
0x1400181bd  jns     short loc_140018214
0x1400181bf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400181c6  mov     [rbp+var_10], eax
0x1400181c9  test    rcx, rcx
0x1400181cc  jz      short loc_14001820A
0x1400181ce  xor     edx, edx
0x1400181d0  lea     r9, aFailedToCreate_4; "Failed to create destination folder"
0x1400181d7  lea     r8d, [rdx+3]
0x1400181db  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400181e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400181e7  lea     rax, [rbp+var_10]
0x1400181eb  mov     qword ptr [rbp+var_30], rax
0x1400181ef  lea     r9, asc_1400353E8; ": {}"
0x1400181f6  lea     rax, [rbp+var_30]
0x1400181fa  mov     r8d, 3
0x140018200  mov     qword ptr [rsp+60h+var_40], rax
0x140018205  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001820a  mov     r9d, ebx
0x14001820d  mov     edx, 1F3h
0x140018212  jmp     short loc_14001822E
0x140018214  mov     rdx, rdi
0x140018217  lea     rcx, [rbp+lpNewFileName]
0x14001821b  call    SczAllocFromSz
0x140018220  mov     ebx, eax
0x140018222  test    eax, eax
0x140018224  jns     short loc_140018243
0x140018226  mov     r9d, eax; char *
0x140018229  mov     edx, 1F5h; void *
0x14001822e  mov     rcx, [rbp+8]; this
0x140018232  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140018239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001823e  jmp     loc_140018391
0x140018243  lea     rcx, [rbp+lpNewFileName]; struct AutoScz *
0x140018247  call    ?AppendGuidToPath@@YAJAEAVAutoScz@@@Z; AppendGuidToPath(AutoScz &)
0x14001824c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018253  mov     ebx, eax
0x140018255  test    eax, eax
0x140018257  jns     short loc_1400182A7
0x140018259  mov     [rbp+var_10], eax
0x14001825c  test    rcx, rcx
0x14001825f  jz      short loc_14001829D
0x140018261  xor     edx, edx
0x140018263  lea     r9, aFailedToAppend; "Failed to append guid to path"
0x14001826a  lea     r8d, [rdx+3]
0x14001826e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018273  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001827a  lea     rax, [rbp+var_10]
0x14001827e  mov     qword ptr [rbp+var_30], rax
0x140018282  lea     r9, asc_1400353E8; ": {}"
0x140018289  lea     rax, [rbp+var_30]
0x14001828d  mov     r8d, 3
0x140018293  mov     qword ptr [rsp+60h+var_40], rax
0x140018298  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001829d  mov     r9d, ebx
0x1400182a0  mov     edx, 1F8h
0x1400182a5  jmp     short loc_14001822E
0x1400182a7  mov     rbx, [rbp+lpNewFileName]
0x1400182ab  mov     [rbp+var_20], rbx
0x1400182af  test    rcx, rcx
0x1400182b2  jz      short loc_1400182DB
0x1400182b4  lea     rax, [rbp+var_20]
0x1400182b8  mov     r8d, 1
0x1400182be  mov     [rsp+60h+var_38], rax
0x1400182c3  lea     r9, aMovingTo; "Moving '{}' to '{}'"
0x1400182ca  lea     rax, [rbp+lpExistingFileName]
0x1400182ce  mov     dl, r8b
0x1400182d1  mov     qword ptr [rsp+60h+var_40], rax
0x1400182d6  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1400182db  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x1400182df  mov     r8d, 8; dwFlags
0x1400182e5  mov     rdx, rbx; lpNewFileName
0x1400182e8  call    cs:__imp_MoveFileExW
0x1400182ee  test    eax, eax
0x1400182f0  jnz     loc_14001838F
0x1400182f6  call    cs:__imp_GetLastError
0x1400182fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018303  mov     edi, eax
0x140018305  test    rcx, rcx
0x140018308  jz      short loc_14001836F
0x14001830a  xor     edx, edx
0x14001830c  mov     [rbp+var_20], rbx
0x140018310  lea     rax, [rbp+var_20]
0x140018314  mov     [rsp+60h+var_38], rax
0x140018319  lea     r9, aFailedToMoveTo; "Failed to move {} to {}."
0x140018320  lea     rax, [rbp+lpExistingFileName]
0x140018324  lea     r8d, [rdx+3]
0x140018328  mov     qword ptr [rsp+60h+var_40], rax
0x14001832d  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x140018332  test    edi, edi
0x140018334  jg      short loc_14001833A
0x140018336  mov     eax, edi
0x140018338  jmp     short loc_140018342
0x14001833a  movzx   eax, di
0x14001833d  or      eax, 80070000h
0x140018342  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018349  lea     r9, a0; ": {0}"
0x140018350  mov     [rbp+var_10], eax
0x140018353  mov     r8d, 3
0x140018359  lea     rax, [rbp+var_10]
0x14001835d  mov     qword ptr [rbp+var_30], rax
0x140018361  lea     rax, [rbp+var_30]
0x140018365  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x14001836a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001836f  test    edi, edi
0x140018371  jz      short loc_14001838F
0x140018373  mov     rcx, [rbp+8]; this
0x140018377  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14001837e  mov     r9d, edi; char *
0x140018381  mov     edx, 1FCh; void *
0x140018386  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001838b  mov     ebx, eax
0x14001838d  jmp     short loc_140018391
0x14001838f  xor     ebx, ebx
0x140018391  lea     rcx, [rbp+lpNewFileName]
0x140018395  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001839a  mov     eax, ebx
0x14001839c  mov     rcx, [rbp+var_8]
0x1400183a0  xor     rcx, rsp; StackCookie
0x1400183a3  call    __security_check_cookie
0x1400183a8  lea     r11, [rsp+60h+var_s0]
0x1400183ad  mov     rbx, [r11+20h]
0x1400183b1  mov     rdi, [r11+28h]
0x1400183b5  mov     rsp, r11
0x1400183b8  pop     rbp
0x1400183b9  retn
```

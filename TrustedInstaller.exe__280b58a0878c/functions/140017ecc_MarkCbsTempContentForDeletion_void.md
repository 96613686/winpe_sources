# MarkCbsTempContentForDeletion(void)

- ea: `0x140017ecc`
- end: `0x140018177`
- name: `?MarkCbsTempContentForDeletion@@YAJXZ`
- size: `683`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x140017d40`
- `0x140017ecc`
- `0x140018180`
- `0x14001fab0`
- `0x14001fc6c`
- `0x140021594`

## string_xrefs

- `0x140017f20`: `Failed to obtain the temporary CbsTemp path`
- `0x140017f61`: `CbsTemp`
- `0x140017f88`: `Failed to obtain the path to CbsTemp`
- `0x14001800c`: `Failed in IsDirectoryEmpty for '{}'`
- `0x140018099`: `Failed to move '{}'`
- `0x1400180ff`: `Failed to create delete folder path`

## pseudocode

```c
__int64 MarkCbsTempContentForDeletion(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  int v2; // edx
  __int64 v3; // rdx
  int WindowsDirectory; // eax
  int v5; // edx
  wchar_t *v6; // rbx
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // edi
  int v11; // edx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // edx
  int Directory; // eax
  int v18; // edx
  int v20; // [rsp+20h] [rbp-50h]
  _BYTE v21[8]; // [rsp+30h] [rbp-40h] BYREF
  int v22[2]; // [rsp+38h] [rbp-38h] BYREF
  int v23[2]; // [rsp+40h] [rbp-30h] BYREF
  wchar_t *v24; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *v25; // [rsp+50h] [rbp-20h] BYREF
  int v26; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v25 = 0;
  v24 = 0;
  v21[0] = 0;
  v0 = GetSystemTempCbsDeleteFolderPath((struct AutoScz *)&v24);
  v1 = v0;
  if ( v0 >= 0 )
  {
    WindowsDirectory = PathGetWindowsDirectory(&v25, L"CbsTemp");
    v1 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v26 = WindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to obtain the path to CbsTemp");
        *(_QWORD *)v22 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v5,
          3,
          (unsigned int)": {}",
          (__int64)v22);
      }
      v3 = 522;
      goto LABEL_9;
    }
    v6 = v25;
    v7 = IsDirectoryEmpty(v25, v21);
    v10 = v7;
    if ( v7 < 0 )
    {
      v26 = v7;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v22 = v6;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v8,
          v9,
          (unsigned int)"Failed in IsDirectoryEmpty for '{}'",
          (__int64)v22);
        *(_QWORD *)v23 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v23);
      }
      v12 = 525;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)v10,
        v20);
      v1 = v10;
      goto LABEL_25;
    }
    if ( !v21[0] )
    {
      v13 = MoveFolderToUniqueFolder(v6, v24);
      v10 = v13;
      if ( v13 < 0 )
      {
        v26 = v13;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v23 = v6;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v14,
            v15,
            (unsigned int)"Failed to move '{}'",
            (__int64)v23);
          *(_QWORD *)v22 = &v26;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v16,
            3,
            (unsigned int)": {}",
            (__int64)v22);
        }
        v12 = 530;
        goto LABEL_14;
      }
      Directory = RecursivelyCreateDirectory(v6, 0);
      v1 = Directory;
      if ( Directory < 0 )
      {
        v26 = Directory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create delete folder path");
          *(_QWORD *)v23 = &v26;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v18,
            3,
            (unsigned int)": {}",
            (__int64)v23);
        }
        v3 = 532;
        goto LABEL_9;
      }
    }
    v1 = 0;
    goto LABEL_25;
  }
  v26 = v0;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to obtain the temporary CbsTemp path");
    *(_QWORD *)v22 = &v26;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v2,
      3,
      (unsigned int)": {}",
      (__int64)v22);
  }
  v3 = 519;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)v1,
    v20);
LABEL_25:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v24);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v25);
  return v1;
}

```

## disassembly

```asm
0x140017ecc  mov     [rsp-8+arg_0], rbx
0x140017ed1  mov     [rsp-8+arg_8], rdi
0x140017ed6  push    rbp
0x140017ed7  mov     rbp, rsp
0x140017eda  sub     rsp, 70h
0x140017ede  mov     rax, cs:__security_cookie
0x140017ee5  xor     rax, rsp
0x140017ee8  mov     [rbp+var_10], rax
0x140017eec  lea     rcx, [rbp+var_28]; struct AutoScz *
0x140017ef0  mov     [rbp+var_20], 0
0x140017ef8  mov     [rbp+var_28], 0
0x140017f00  mov     [rbp+var_40], 0
0x140017f04  call    ?GetSystemTempCbsDeleteFolderPath@@YAJAEAVAutoScz@@@Z; GetSystemTempCbsDeleteFolderPath(AutoScz &)
0x140017f09  mov     ebx, eax
0x140017f0b  test    eax, eax
0x140017f0d  jns     short loc_140017F61
0x140017f0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f16  mov     [rbp+var_18], eax
0x140017f19  test    rcx, rcx
0x140017f1c  jz      short loc_140017F5A
0x140017f1e  xor     edx, edx
0x140017f20  lea     r9, aFailedToObtain_0; "Failed to obtain the temporary CbsTemp "...
0x140017f27  lea     r8d, [rdx+3]
0x140017f2b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017f30  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f37  lea     rax, [rbp+var_18]
0x140017f3b  mov     qword ptr [rbp+var_38], rax
0x140017f3f  lea     r9, asc_1400353E8; ": {}"
0x140017f46  lea     rax, [rbp+var_38]
0x140017f4a  mov     r8d, 3
0x140017f50  mov     qword ptr [rsp+70h+var_50], rax
0x140017f55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017f5a  mov     edx, 207h
0x140017f5f  jmp     short loc_140017FC7
0x140017f61  lea     rdx, aCbstemp; "CbsTemp"
0x140017f68  lea     rcx, [rbp+var_20]
0x140017f6c  call    PathGetWindowsDirectory
0x140017f71  mov     ebx, eax
0x140017f73  test    eax, eax
0x140017f75  jns     short loc_140017FDF
0x140017f77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f7e  mov     [rbp+var_18], eax
0x140017f81  test    rcx, rcx
0x140017f84  jz      short loc_140017FC2
0x140017f86  xor     edx, edx
0x140017f88  lea     r9, aFailedToObtain_1; "Failed to obtain the path to CbsTemp"
0x140017f8f  lea     r8d, [rdx+3]
0x140017f93  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017f98  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f9f  lea     rax, [rbp+var_18]
0x140017fa3  mov     qword ptr [rbp+var_38], rax
0x140017fa7  lea     r9, asc_1400353E8; ": {}"
0x140017fae  lea     rax, [rbp+var_38]
0x140017fb2  mov     r8d, 3
0x140017fb8  mov     qword ptr [rsp+70h+var_50], rax; int
0x140017fbd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017fc2  mov     edx, 20Ah; void *
0x140017fc7  mov     rcx, [rbp+8]; this
0x140017fcb  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140017fd2  mov     r9d, ebx; char *
0x140017fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017fda  jmp     loc_140018145
0x140017fdf  mov     rbx, [rbp+var_20]
0x140017fe3  lea     rdx, [rbp+var_40]
0x140017fe7  mov     rcx, rbx
0x140017fea  call    IsDirectoryEmpty
0x140017fef  mov     edi, eax
0x140017ff1  test    eax, eax
0x140017ff3  jns     short loc_140018066
0x140017ff5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017ffc  mov     [rbp+var_18], eax
0x140017fff  test    rcx, rcx
0x140018002  jz      short loc_140018047
0x140018004  lea     rax, [rbp+var_38]
0x140018008  mov     qword ptr [rbp+var_38], rbx
0x14001800c  lea     r9, aFailedInIsdire; "Failed in IsDirectoryEmpty for '{}'"
0x140018013  mov     qword ptr [rsp+70h+var_50], rax
0x140018018  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001801d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018024  lea     rax, [rbp+var_18]
0x140018028  mov     qword ptr [rbp+var_30], rax
0x14001802c  lea     r9, asc_1400353E8; ": {}"
0x140018033  lea     rax, [rbp+var_30]
0x140018037  mov     r8d, 3
0x14001803d  mov     qword ptr [rsp+70h+var_50], rax; int
0x140018042  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018047  mov     edx, 20Dh; void *
0x14001804c  mov     rcx, [rbp+8]; this
0x140018050  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x140018057  mov     r9d, edi; char *
0x14001805a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001805f  mov     ebx, edi
0x140018061  jmp     loc_140018145
0x140018066  cmp     [rbp+var_40], 0
0x14001806a  jnz     loc_140018143
0x140018070  mov     rdx, [rbp+var_28]; wchar_t *
0x140018074  mov     rcx, rbx; wchar_t *
0x140018077  call    ?MoveFolderToUniqueFolder@@YAJQEB_W0@Z; MoveFolderToUniqueFolder(wchar_t const * const,wchar_t const * const)
0x14001807c  mov     edi, eax
0x14001807e  test    eax, eax
0x140018080  jns     short loc_1400180DE
0x140018082  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018089  mov     [rbp+var_18], eax
0x14001808c  test    rcx, rcx
0x14001808f  jz      short loc_1400180D4
0x140018091  lea     rax, [rbp+var_30]
0x140018095  mov     qword ptr [rbp+var_30], rbx
0x140018099  lea     r9, aFailedToMove; "Failed to move '{}'"
0x1400180a0  mov     qword ptr [rsp+70h+var_50], rax
0x1400180a5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400180aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400180b1  lea     rax, [rbp+var_18]
0x1400180b5  mov     qword ptr [rbp+var_38], rax
0x1400180b9  lea     r9, asc_1400353E8; ": {}"
0x1400180c0  lea     rax, [rbp+var_38]
0x1400180c4  mov     r8d, 3
0x1400180ca  mov     qword ptr [rsp+70h+var_50], rax
0x1400180cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400180d4  mov     edx, 212h
0x1400180d9  jmp     loc_14001804C
0x1400180de  xor     edx, edx
0x1400180e0  mov     rcx, rbx
0x1400180e3  call    RecursivelyCreateDirectory
0x1400180e8  mov     ebx, eax
0x1400180ea  test    eax, eax
0x1400180ec  jns     short loc_140018143
0x1400180ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400180f5  mov     [rbp+var_18], eax
0x1400180f8  test    rcx, rcx
0x1400180fb  jz      short loc_140018139
0x1400180fd  xor     edx, edx
0x1400180ff  lea     r9, aFailedToCreate_9; "Failed to create delete folder path"
0x140018106  lea     r8d, [rdx+3]
0x14001810a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001810f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018116  lea     rax, [rbp+var_18]
0x14001811a  mov     qword ptr [rbp+var_30], rax
0x14001811e  lea     r9, asc_1400353E8; ": {}"
0x140018125  lea     rax, [rbp+var_30]
0x140018129  mov     r8d, 3
0x14001812f  mov     qword ptr [rsp+70h+var_50], rax
0x140018134  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018139  mov     edx, 214h
0x14001813e  jmp     loc_140017FC7
0x140018143  xor     ebx, ebx
0x140018145  lea     rcx, [rbp+var_28]
0x140018149  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001814e  lea     rcx, [rbp+var_20]
0x140018152  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140018157  mov     eax, ebx
0x140018159  mov     rcx, [rbp+var_10]
0x14001815d  xor     rcx, rsp; StackCookie
0x140018160  call    __security_check_cookie
0x140018165  lea     r11, [rsp+70h+var_s0]
0x14001816a  mov     rbx, [r11+10h]
0x14001816e  mov     rdi, [r11+18h]
0x140018172  mov     rsp, r11
0x140018175  pop     rbp
0x140018176  retn
```

# MarkCbsTempContentForDeletion(void)

- ea: `0x14000ed6c`
- end: `0x14000f023`
- name: `?MarkCbsTempContentForDeletion@@YAJXZ`
- size: `695`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x140007228`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000ebe0`
- `0x14000ed6c`
- `0x14000f02c`
- `0x140014ef0`
- `0x140015228`
- `0x140016d8c`

## string_xrefs

- `0x14000edc0`: `Failed to obtain the temporary CbsTemp path`
- `0x14000ee01`: `CbsTemp`
- `0x14000ee28`: `Failed to obtain the path to CbsTemp`
- `0x14000eeae`: `Failed in IsDirectoryEmpty for '{}'`
- `0x14000ef41`: `Failed to move '{}'`
- `0x14000efab`: `Failed to create delete folder path`

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
  unsigned int v8; // esi
  int v9; // edx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // edx
  int Directory; // eax
  int v14; // edx
  int v16; // [rsp+20h] [rbp-50h]
  _BYTE v17[8]; // [rsp+30h] [rbp-40h] BYREF
  int v18[2]; // [rsp+38h] [rbp-38h] BYREF
  int v19[2]; // [rsp+40h] [rbp-30h] BYREF
  wchar_t *v20; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *v21; // [rsp+50h] [rbp-20h] BYREF
  int v22; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v21 = 0;
  v20 = 0;
  v17[0] = 0;
  v0 = GetSystemTempCbsDeleteFolderPath((struct AutoScz *)&v20);
  v1 = v0;
  if ( v0 >= 0 )
  {
    WindowsDirectory = PathGetWindowsDirectory(&v21, L"CbsTemp");
    v1 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v22 = WindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to obtain the path to CbsTemp");
        *(_QWORD *)v18 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v5,
          3,
          (unsigned int)": {}",
          (__int64)v18);
      }
      v3 = 522;
      goto LABEL_9;
    }
    v6 = v21;
    v7 = IsDirectoryEmpty(v21, v17);
    v8 = v7;
    if ( v7 < 0 )
    {
      v22 = v7;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v18 = v6;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed in IsDirectoryEmpty for '{}'",
          (__int64)v18);
        *(_QWORD *)v19 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {}",
          (__int64)v19);
      }
      v10 = 525;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
        (const char *)v8,
        v16);
      v1 = v8;
      goto LABEL_25;
    }
    if ( !v17[0] )
    {
      v11 = MoveFolderToUniqueFolder(v6, v20);
      v8 = v11;
      if ( v11 < 0 )
      {
        v22 = v11;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v19 = v6;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to move '{}'",
            (__int64)v19);
          *(_QWORD *)v18 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v12,
            3,
            (unsigned int)": {}",
            (__int64)v18);
        }
        v10 = 530;
        goto LABEL_14;
      }
      Directory = RecursivelyCreateDirectory(v6, 0);
      v1 = Directory;
      if ( Directory < 0 )
      {
        v22 = Directory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create delete folder path");
          *(_QWORD *)v19 = &v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v14,
            3,
            (unsigned int)": {}",
            (__int64)v19);
        }
        v3 = 532;
        goto LABEL_9;
      }
    }
    v1 = 0;
    goto LABEL_25;
  }
  v22 = v0;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to obtain the temporary CbsTemp path");
    *(_QWORD *)v18 = &v22;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v2,
      3,
      (unsigned int)": {}",
      (__int64)v18);
  }
  v3 = 519;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)v1,
    v16);
LABEL_25:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v20);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
  return v1;
}

```

## disassembly

```asm
0x14000ed6c  mov     [rsp-8+arg_0], rbx
0x14000ed71  mov     [rsp-8+arg_8], rsi
0x14000ed76  push    rbp
0x14000ed77  mov     rbp, rsp
0x14000ed7a  sub     rsp, 70h
0x14000ed7e  mov     rax, cs:__security_cookie
0x14000ed85  xor     rax, rsp
0x14000ed88  mov     [rbp+var_10], rax
0x14000ed8c  lea     rcx, [rbp+var_28]; struct AutoScz *
0x14000ed90  mov     [rbp+var_20], 0
0x14000ed98  mov     [rbp+var_28], 0
0x14000eda0  mov     [rbp+var_40], 0
0x14000eda4  call    ?GetSystemTempCbsDeleteFolderPath@@YAJAEAVAutoScz@@@Z; GetSystemTempCbsDeleteFolderPath(AutoScz &)
0x14000eda9  mov     ebx, eax
0x14000edab  test    eax, eax
0x14000edad  jns     short loc_14000EE01
0x14000edaf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000edb6  mov     [rbp+var_18], eax
0x14000edb9  test    rcx, rcx
0x14000edbc  jz      short loc_14000EDFA
0x14000edbe  xor     edx, edx
0x14000edc0  lea     r9, aFailedToObtain_0; "Failed to obtain the temporary CbsTemp "...
0x14000edc7  lea     r8d, [rdx+3]
0x14000edcb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000edd0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000edd7  lea     rax, [rbp+var_18]
0x14000eddb  mov     qword ptr [rbp+var_38], rax
0x14000eddf  lea     r9, asc_140030534; ": {}"
0x14000ede6  lea     rax, [rbp+var_38]
0x14000edea  mov     r8d, 3
0x14000edf0  mov     qword ptr [rsp+70h+var_50], rax
0x14000edf5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000edfa  mov     edx, 207h
0x14000edff  jmp     short loc_14000EE67
0x14000ee01  lea     rdx, aCbstemp; "CbsTemp"
0x14000ee08  lea     rcx, [rbp+var_20]
0x14000ee0c  call    PathGetWindowsDirectory
0x14000ee11  mov     ebx, eax
0x14000ee13  test    eax, eax
0x14000ee15  jns     short loc_14000EE7F
0x14000ee17  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ee1e  mov     [rbp+var_18], eax
0x14000ee21  test    rcx, rcx
0x14000ee24  jz      short loc_14000EE62
0x14000ee26  xor     edx, edx
0x14000ee28  lea     r9, aFailedToObtain_1; "Failed to obtain the path to CbsTemp"
0x14000ee2f  lea     r8d, [rdx+3]
0x14000ee33  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000ee38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ee3f  lea     rax, [rbp+var_18]
0x14000ee43  mov     qword ptr [rbp+var_38], rax
0x14000ee47  lea     r9, asc_140030534; ": {}"
0x14000ee4e  lea     rax, [rbp+var_38]
0x14000ee52  mov     r8d, 3
0x14000ee58  mov     qword ptr [rsp+70h+var_50], rax; int
0x14000ee5d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ee62  mov     edx, 20Ah; void *
0x14000ee67  mov     rcx, [rbp+8]; this
0x14000ee6b  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000ee72  mov     r9d, ebx; char *
0x14000ee75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ee7a  jmp     loc_14000EFF1
0x14000ee7f  mov     rbx, [rbp+var_20]
0x14000ee83  lea     rdx, [rbp+var_40]
0x14000ee87  mov     rcx, rbx
0x14000ee8a  call    IsDirectoryEmpty
0x14000ee8f  mov     esi, eax
0x14000ee91  test    eax, eax
0x14000ee93  jns     short loc_14000EF0C
0x14000ee95  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ee9c  mov     [rbp+var_18], eax
0x14000ee9f  test    rcx, rcx
0x14000eea2  jz      short loc_14000EEED
0x14000eea4  xor     edx, edx
0x14000eea6  mov     qword ptr [rbp+var_38], rbx
0x14000eeaa  lea     rax, [rbp+var_38]
0x14000eeae  lea     r9, aFailedInIsdire; "Failed in IsDirectoryEmpty for '{}'"
0x14000eeb5  mov     qword ptr [rsp+70h+var_50], rax
0x14000eeba  lea     r8d, [rdx+3]
0x14000eebe  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000eec3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000eeca  lea     rax, [rbp+var_18]
0x14000eece  mov     qword ptr [rbp+var_30], rax
0x14000eed2  lea     r9, asc_140030534; ": {}"
0x14000eed9  lea     rax, [rbp+var_30]
0x14000eedd  mov     r8d, 3
0x14000eee3  mov     qword ptr [rsp+70h+var_50], rax; int
0x14000eee8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000eeed  mov     edx, 20Dh; void *
0x14000eef2  mov     rcx, [rbp+8]; this
0x14000eef6  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000eefd  mov     r9d, esi; char *
0x14000ef00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ef05  mov     ebx, esi
0x14000ef07  jmp     loc_14000EFF1
0x14000ef0c  cmp     [rbp+var_40], 0
0x14000ef10  jnz     loc_14000EFEF
0x14000ef16  mov     rdx, [rbp+var_28]; wchar_t *
0x14000ef1a  mov     rcx, rbx; wchar_t *
0x14000ef1d  call    ?MoveFolderToUniqueFolder@@YAJQEB_W0@Z; MoveFolderToUniqueFolder(wchar_t const * const,wchar_t const * const)
0x14000ef22  mov     esi, eax
0x14000ef24  test    eax, eax
0x14000ef26  jns     short loc_14000EF8A
0x14000ef28  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ef2f  mov     [rbp+var_18], eax
0x14000ef32  test    rcx, rcx
0x14000ef35  jz      short loc_14000EF80
0x14000ef37  xor     edx, edx
0x14000ef39  mov     qword ptr [rbp+var_30], rbx
0x14000ef3d  lea     rax, [rbp+var_30]
0x14000ef41  lea     r9, aFailedToMove; "Failed to move '{}'"
0x14000ef48  mov     qword ptr [rsp+70h+var_50], rax
0x14000ef4d  lea     r8d, [rdx+3]
0x14000ef51  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000ef56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000ef5d  lea     rax, [rbp+var_18]
0x14000ef61  mov     qword ptr [rbp+var_38], rax
0x14000ef65  lea     r9, asc_140030534; ": {}"
0x14000ef6c  lea     rax, [rbp+var_38]
0x14000ef70  mov     r8d, 3
0x14000ef76  mov     qword ptr [rsp+70h+var_50], rax
0x14000ef7b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000ef80  mov     edx, 212h
0x14000ef85  jmp     loc_14000EEF2
0x14000ef8a  xor     edx, edx
0x14000ef8c  mov     rcx, rbx
0x14000ef8f  call    RecursivelyCreateDirectory
0x14000ef94  mov     ebx, eax
0x14000ef96  test    eax, eax
0x14000ef98  jns     short loc_14000EFEF
0x14000ef9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000efa1  mov     [rbp+var_18], eax
0x14000efa4  test    rcx, rcx
0x14000efa7  jz      short loc_14000EFE5
0x14000efa9  xor     edx, edx
0x14000efab  lea     r9, aFailedToCreate_4; "Failed to create delete folder path"
0x14000efb2  lea     r8d, [rdx+3]
0x14000efb6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000efbb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000efc2  lea     rax, [rbp+var_18]
0x14000efc6  mov     qword ptr [rbp+var_30], rax
0x14000efca  lea     r9, asc_140030534; ": {}"
0x14000efd1  lea     rax, [rbp+var_30]
0x14000efd5  mov     r8d, 3
0x14000efdb  mov     qword ptr [rsp+70h+var_50], rax
0x14000efe0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000efe5  mov     edx, 214h
0x14000efea  jmp     loc_14000EE67
0x14000efef  xor     ebx, ebx
0x14000eff1  lea     rcx, [rbp+var_28]
0x14000eff5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000effa  lea     rcx, [rbp+var_20]
0x14000effe  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000f003  mov     eax, ebx
0x14000f005  mov     rcx, [rbp+var_10]
0x14000f009  xor     rcx, rsp; StackCookie
0x14000f00c  call    __security_check_cookie
0x14000f011  lea     r11, [rsp+70h+var_s0]
0x14000f016  mov     rbx, [r11+10h]
0x14000f01a  mov     rsi, [r11+18h]
0x14000f01e  mov     rsp, r11
0x14000f021  pop     rbp
0x14000f022  retn
```

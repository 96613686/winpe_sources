# PathGetModulePath

- ea: `0x140016bf8`
- end: `0x140016d84`
- name: `PathGetModulePath`
- size: `396`
- prototype: `int __fastcall(__int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140007004`
- `0x140007758`
- `0x140007eb8`
- `0x14000af9c`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000f36c`
- `0x1400149ec`
- `0x140016bf8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x140016cb1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x140016cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016ce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016ce0`

## string_xrefs

- `0x140016c8e`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016d53`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016c44`: `No path result specified`
- `0x140016cf6`: `Failed to get servicing stack path.`

## pseudocode

```c
int __fastcall PathGetModulePath(__int64 a1)
{
  int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  DWORD ModuleFileNameW; // eax
  signed int LastError; // ebx
  int v8; // edx
  unsigned int v9; // eax
  unsigned int v10; // [rsp+20h] [rbp-248h]
  unsigned int v11[2]; // [rsp+30h] [rbp-238h] BYREF
  int v12; // [rsp+38h] [rbp-230h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  memset_0(Filename, 0, 0x208u);
  if ( !a1 )
  {
    v2 = -2147467261;
    v12 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path result specified");
      *(_QWORD *)v11 = &v12;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v11);
    }
    v4 = 213;
    goto LABEL_5;
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get servicing stack path.");
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v12 = v9;
      *(_QWORD *)v11 = &v12;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {0}",
        (__int64)v11);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xD8,
               (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
               (const char *)(unsigned int)LastError,
               v10);
  }
  else
  {
    v2 = DirectoryFromPath(Filename);
    if ( v2 < 0 )
    {
      v4 = 218;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)(unsigned int)v2,
        v10);
      return v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140016bf8  push    rbx
0x140016bfa  sub     rsp, 260h
0x140016c01  mov     rax, cs:__security_cookie
0x140016c08  xor     rax, rsp
0x140016c0b  mov     [rsp+268h+var_18], rax
0x140016c13  mov     rbx, rcx
0x140016c16  xor     edx, edx; Val
0x140016c18  lea     rcx, [rsp+268h+Filename]; void *
0x140016c1d  mov     r8d, 208h; Size
0x140016c23  call    memset_0
0x140016c28  test    rbx, rbx
0x140016c2b  jnz     short loc_140016CA4
0x140016c2d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016c34  mov     ebx, 80004003h
0x140016c39  mov     [rsp+268h+var_230], ebx
0x140016c3d  test    rcx, rcx
0x140016c40  jz      short loc_140016C81
0x140016c42  xor     edx, edx
0x140016c44  lea     r9, aNoPathResultSp; "No path result specified"
0x140016c4b  lea     r8d, [rdx+3]
0x140016c4f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016c54  lea     rcx, [rsp+268h+var_238]
0x140016c59  mov     r8d, 3
0x140016c5f  mov     qword ptr [rsp+268h+var_248], rcx; int
0x140016c64  lea     rax, [rsp+268h+var_230]
0x140016c69  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016c70  lea     r9, asc_140030534; ": {}"
0x140016c77  mov     qword ptr [rsp+268h+var_238], rax
0x140016c7c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016c81  mov     edx, 0D5h; void *
0x140016c86  mov     rcx, [rsp+268h]; this
0x140016c8e  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140016c95  mov     r9d, ebx; char *
0x140016c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c9d  mov     eax, ebx
0x140016c9f  jmp     loc_140016D6B
0x140016ca4  mov     r8d, 104h; nSize
0x140016caa  lea     rdx, [rsp+268h+Filename]; lpFilename
0x140016caf  xor     ecx, ecx; hModule
0x140016cb1  call    cs:__imp_GetModuleFileNameW
0x140016cb7  test    eax, eax
0x140016cb9  jz      short loc_140016CE0
0x140016cbb  cmp     eax, 104h
0x140016cc0  jz      short loc_140016CE0
0x140016cc2  mov     rdx, rbx
0x140016cc5  lea     rcx, [rsp+268h+Filename]; wchar_t *
0x140016cca  call    DirectoryFromPath
0x140016ccf  mov     ebx, eax
0x140016cd1  test    eax, eax
0x140016cd3  jns     loc_140016D69
0x140016cd9  mov     edx, 0DAh
0x140016cde  jmp     short loc_140016C86
0x140016ce0  call    cs:__imp_GetLastError
0x140016ce6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016ced  mov     ebx, eax
0x140016cef  test    rcx, rcx
0x140016cf2  jz      short loc_140016D47
0x140016cf4  xor     edx, edx
0x140016cf6  lea     r9, aFailedToGetSer; "Failed to get servicing stack path."
0x140016cfd  lea     r8d, [rdx+3]
0x140016d01  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016d06  test    ebx, ebx
0x140016d08  jg      short loc_140016D0E
0x140016d0a  mov     eax, ebx
0x140016d0c  jmp     short loc_140016D16
0x140016d0e  movzx   eax, bx
0x140016d11  or      eax, 80070000h
0x140016d16  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016d1d  lea     r9, a0; ": {0}"
0x140016d24  mov     [rsp+268h+var_230], eax
0x140016d28  mov     r8d, 3
0x140016d2e  lea     rax, [rsp+268h+var_230]
0x140016d33  mov     qword ptr [rsp+268h+var_238], rax
0x140016d38  lea     rax, [rsp+268h+var_238]
0x140016d3d  mov     qword ptr [rsp+268h+var_248], rax; unsigned int
0x140016d42  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016d47  test    ebx, ebx
0x140016d49  jz      short loc_140016D69
0x140016d4b  mov     rcx, [rsp+268h]; this
0x140016d53  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140016d5a  mov     r9d, ebx; char *
0x140016d5d  mov     edx, 0D8h; void *
0x140016d62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016d67  jmp     short loc_140016D6B
0x140016d69  xor     eax, eax
0x140016d6b  mov     rcx, [rsp+268h+var_18]
0x140016d73  xor     rcx, rsp; StackCookie
0x140016d76  call    __security_check_cookie
0x140016d7b  add     rsp, 260h
0x140016d82  pop     rbx
0x140016d83  retn
```

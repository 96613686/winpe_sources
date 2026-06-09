# DpxLoad(HINSTANCE__ * *)

- ea: `0x180203760`
- end: `0x180203b1b`
- name: `?DpxLoad@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043ee8`
- `0x18004ab74`
- `0x18004ca94`
- `0x180062e60`
- `0x1800c52f8`
- `0x1800f995c`
- `0x1801235b4`
- `0x180156d38`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x180022940`
- `0x18014fbe0`
- `0x1801dcc08`
- `0x1802036c0`
- `0x180203760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802039f7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802039f7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180203ac5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180203ac5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180203885`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180203926`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18020394a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180203885`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180203926`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18020394a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203ad5`

## string_xrefs

- `0x18020389d`: `Servicing\dpx.dll`
- `0x180203943`: `Dpx.dll`
- `0x180203997`: `Failed to load DPX DLL`
- `0x180203809`: `dpx.dll`
- `0x180203831`: `Failed to get path to dpx.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DpxLoad(HINSTANCE *a1)
{
  LPCWSTR v2; // rdi
  HMODULE Library; // rbx
  signed int Win32PathOfSiblingFile; // esi
  int v5; // edx
  signed int LastError; // eax
  signed int v7; // eax
  HINSTANCE v8; // rax
  const struct std::nothrow_t *v9; // rdx
  LPCWSTR v11; // [rsp+30h] [rbp-40h] BYREF
  int *v12; // [rsp+38h] [rbp-38h] BYREF
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+58h] [rbp-18h]
  int v16; // [rsp+60h] [rbp-10h] BYREF

  v15 = -2;
  v2 = 0;
  v11 = 0;
  Library = 0;
  v13 = 0;
  lpLibFileName = 0;
  if ( !a1 )
  {
    Win32PathOfSiblingFile = -2147467261;
    v16 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No dpx handle specified");
      v11 = (LPCWSTR)&v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v11);
    }
    v5 = 575;
LABEL_23:
    DebugOnError("onecore\\base\\servicing\\util\\servicinghelper.cpp", v5);
    goto LABEL_34;
  }
  Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(DpxLoad, L"dpx.dll", &v13);
  v16 = Win32PathOfSiblingFile;
  if ( Win32PathOfSiblingFile < 0 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get path to dpx.dll");
      v11 = (LPCWSTR)&v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v11);
    }
    v5 = 578;
    goto LABEL_23;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 8u);
  if ( !Library )
  {
    Win32PathOfSiblingFile = PathGetWindowsDirectory(&v11, L"Servicing\\dpx.dll");
    v16 = Win32PathOfSiblingFile;
    if ( Win32PathOfSiblingFile < 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get online Windir");
        v12 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)&v12);
      }
      DebugOnError("onecore\\base\\servicing\\util\\servicinghelper.cpp", 590);
      v2 = v11;
      goto LABEL_34;
    }
    v2 = v11;
    Library = LoadLibraryExW(v11, 0, 0);
    if ( !Library )
    {
      Library = LoadLibraryExW(L"Dpx.dll", 0, 0);
      if ( !Library )
      {
        LastError = GetLastError();
        Win32PathOfSiblingFile = LastError;
        if ( LastError > 0 )
          Win32PathOfSiblingFile = (unsigned __int16)LastError | 0x80070000;
        if ( Win32PathOfSiblingFile >= 0 )
          Win32PathOfSiblingFile = -2147467259;
        v16 = Win32PathOfSiblingFile;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load DPX DLL");
          v12 = &v16;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)&v12);
        }
        v5 = 601;
        goto LABEL_23;
      }
    }
  }
  qword_1803B0530 = (__int64)GetProcAddress(Library, "DpxNewJob");
  if ( qword_1803B0530 )
  {
    v8 = Library;
    Library = 0;
    *a1 = v8;
  }
  else
  {
    v7 = GetLastError();
    Win32PathOfSiblingFile = v7;
    if ( v7 > 0 )
      Win32PathOfSiblingFile = (unsigned __int16)v7 | 0x80070000;
    if ( Win32PathOfSiblingFile >= 0 )
      Win32PathOfSiblingFile = -2147467259;
    v16 = Win32PathOfSiblingFile;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for DpxNewJob.");
      v12 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&v12);
    }
    DebugOnError("onecore\\base\\servicing\\util\\servicinghelper.cpp", 605);
    qword_1803B0530 = 0;
  }
LABEL_34:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v13);
  if ( Library && !FreeLibrary(Library) )
  {
    GetLastError();
    __fastfail(7u);
  }
  if ( v2 )
    operator delete((void *)(v2 - 4), v9);
  return (unsigned int)Win32PathOfSiblingFile;
}

```

## disassembly

```asm
0x180203760  mov     rax, rsp
0x180203763  push    rbp
0x180203764  push    rdi
0x180203765  push    r14
0x180203767  mov     rbp, rsp
0x18020376a  sub     rsp, 70h
0x18020376e  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180203776  mov     [rax+10h], rbx
0x18020377a  mov     [rax+18h], rsi
0x18020377e  mov     rax, cs:__security_cookie
0x180203785  xor     rax, rsp
0x180203788  mov     [rbp+var_8], rax
0x18020378c  mov     r14, rcx
0x18020378f  xor     edi, edi
0x180203791  mov     [rbp+var_40], rdi
0x180203795  xor     ebx, ebx
0x180203797  xorps   xmm0, xmm0
0x18020379a  xor     eax, eax
0x18020379c  movups  [rbp+var_30], xmm0
0x1802037a0  mov     [rbp+lpLibFileName], rax
0x1802037a4  test    rcx, rcx
0x1802037a7  jnz     short loc_180203805
0x1802037a9  mov     esi, 80004003h
0x1802037ae  mov     [rbp+var_10], esi
0x1802037b1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802037b8  test    rcx, rcx
0x1802037bb  jz      short loc_1802037FB
0x1802037bd  lea     r9, aNoDpxHandleSpe; "No dpx handle specified"
0x1802037c4  lea     r14d, [rdi+3]
0x1802037c8  mov     r8d, r14d
0x1802037cb  xor     edx, edx
0x1802037cd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802037d2  lea     rax, [rbp+var_10]
0x1802037d6  mov     [rbp+var_40], rax
0x1802037da  lea     rax, [rbp+var_40]
0x1802037de  mov     [rsp+70h+var_50], rax
0x1802037e3  lea     r9, a0; ": {0}"
0x1802037ea  mov     r8d, r14d
0x1802037ed  mov     dl, 1
0x1802037ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802037f6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802037fb  mov     edx, 23Fh
0x180203800  jmp     loc_1802039DC
0x180203805  lea     r8, [rbp+var_30]
0x180203809  lea     rdx, aDpxDll_0; "dpx.dll"
0x180203810  lea     rcx, ?DpxLoad@@YAJPEAPEAUHINSTANCE__@@@Z; DpxLoad(HINSTANCE__ * *)
0x180203817  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x18020381c  mov     esi, eax
0x18020381e  mov     [rbp+var_10], eax
0x180203821  test    eax, eax
0x180203823  jns     short loc_18020387B
0x180203825  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020382c  test    rcx, rcx
0x18020382f  jz      short loc_180203871
0x180203831  lea     r9, aFailedToGetPat_3; "Failed to get path to dpx.dll"
0x180203838  mov     r14d, 3
0x18020383e  mov     r8d, r14d
0x180203841  xor     edx, edx
0x180203843  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180203848  lea     rax, [rbp+var_10]
0x18020384c  mov     [rbp+var_40], rax
0x180203850  lea     rax, [rbp+var_40]
0x180203854  mov     [rsp+70h+var_50], rax
0x180203859  lea     r9, a0; ": {0}"
0x180203860  mov     r8d, r14d
0x180203863  mov     dl, 1
0x180203865  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18020386c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180203871  mov     edx, 242h
0x180203876  jmp     loc_1802039DC
0x18020387b  xor     edx, edx; hFile
0x18020387d  lea     r8d, [rdx+8]; dwFlags
0x180203881  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180203885  call    cs:__imp_LoadLibraryExW
0x18020388c  nop     dword ptr [rax+rax+00h]
0x180203891  mov     rbx, rax
0x180203894  test    rax, rax
0x180203897  jnz     loc_1802039ED
0x18020389d  lea     rdx, aServicingDpxDl; "Servicing\\dpx.dll"
0x1802038a4  lea     rcx, [rbp+var_40]
0x1802038a8  call    PathGetWindowsDirectory
0x1802038ad  mov     esi, eax
0x1802038af  mov     [rbp+var_10], eax
0x1802038b2  test    eax, eax
0x1802038b4  jns     short loc_18020391A
0x1802038b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802038bd  test    rcx, rcx
0x1802038c0  jz      short loc_180203900
0x1802038c2  lea     r9, aFailedToGetOnl; "Failed to get online Windir"
0x1802038c9  lea     r14d, [rbx+3]
0x1802038cd  mov     r8d, r14d
0x1802038d0  xor     edx, edx
0x1802038d2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802038d7  lea     rax, [rbp+var_10]
0x1802038db  mov     [rbp+var_38], rax
0x1802038df  lea     rax, [rbp+var_38]
0x1802038e3  mov     [rsp+70h+var_50], rax
0x1802038e8  lea     r9, a0; ": {0}"
0x1802038ef  mov     r8d, r14d
0x1802038f2  mov     dl, 1
0x1802038f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802038fb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180203900  mov     edx, 24Eh; int
0x180203905  lea     rcx, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x18020390c  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x180203911  mov     rdi, [rbp+var_40]
0x180203915  jmp     loc_180203AB3
0x18020391a  xor     r8d, r8d; dwFlags
0x18020391d  xor     edx, edx; hFile
0x18020391f  mov     rdi, [rbp+var_40]
0x180203923  mov     rcx, rdi; lpLibFileName
0x180203926  call    cs:__imp_LoadLibraryExW
0x18020392d  nop     dword ptr [rax+rax+00h]
0x180203932  mov     rbx, rax
0x180203935  test    rax, rax
0x180203938  jnz     loc_1802039ED
0x18020393e  xor     r8d, r8d; dwFlags
0x180203941  xor     edx, edx; hFile
0x180203943  lea     rcx, aDpxDll; "Dpx.dll"
0x18020394a  call    cs:__imp_LoadLibraryExW
0x180203951  nop     dword ptr [rax+rax+00h]
0x180203956  mov     rbx, rax
0x180203959  test    rax, rax
0x18020395c  jnz     loc_1802039ED
0x180203962  call    cs:__imp_GetLastError
0x180203969  nop     dword ptr [rax+rax+00h]
0x18020396e  mov     esi, eax
0x180203970  test    eax, eax
0x180203972  jle     short loc_18020397D
0x180203974  movzx   esi, ax
0x180203977  or      esi, 80070000h
0x18020397d  test    esi, esi
0x18020397f  js      short loc_180203986
0x180203981  mov     esi, 80004005h
0x180203986  mov     eax, esi
0x180203988  mov     [rbp+var_10], eax
0x18020398b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180203992  test    rcx, rcx
0x180203995  jz      short loc_1802039D7
0x180203997  lea     r9, aFailedToLoadDp; "Failed to load DPX DLL"
0x18020399e  mov     r14d, 3
0x1802039a4  mov     r8d, r14d
0x1802039a7  xor     edx, edx
0x1802039a9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802039ae  lea     rax, [rbp+var_10]
0x1802039b2  mov     [rbp+var_38], rax
0x1802039b6  lea     rax, [rbp+var_38]
0x1802039ba  mov     [rsp+70h+var_50], rax
0x1802039bf  lea     r9, a0; ": {0}"
0x1802039c6  mov     r8d, r14d
0x1802039c9  mov     dl, 1
0x1802039cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802039d2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802039d7  mov     edx, 259h; int
0x1802039dc  lea     rcx, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x1802039e3  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x1802039e8  jmp     loc_180203AB3
0x1802039ed  lea     rdx, aDpxnewjob; "DpxNewJob"
0x1802039f4  mov     rcx, rbx; hModule
0x1802039f7  call    cs:__imp_GetProcAddress
0x1802039fe  nop     dword ptr [rax+rax+00h]
0x180203a03  mov     cs:qword_1803B0530, rax
0x180203a0a  test    rax, rax
0x180203a0d  jnz     loc_180203AAB
0x180203a13  call    cs:__imp_GetLastError
0x180203a1a  nop     dword ptr [rax+rax+00h]
0x180203a1f  mov     esi, eax
0x180203a21  test    eax, eax
0x180203a23  jle     short loc_180203A2E
0x180203a25  movzx   esi, ax
0x180203a28  or      esi, 80070000h
0x180203a2e  test    esi, esi
0x180203a30  js      short loc_180203A37
0x180203a32  mov     esi, 80004005h
0x180203a37  mov     eax, esi
0x180203a39  mov     [rbp+var_10], eax
0x180203a3c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180203a43  test    rcx, rcx
0x180203a46  jz      short loc_180203A88
0x180203a48  lea     r9, aFailedToGetPro_4; "Failed to get proc address for DpxNewJo"...
0x180203a4f  mov     r14d, 3
0x180203a55  mov     r8d, r14d
0x180203a58  xor     edx, edx
0x180203a5a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180203a5f  lea     rax, [rbp+var_10]
0x180203a63  mov     [rbp+var_38], rax
0x180203a67  lea     rax, [rbp+var_38]
0x180203a6b  mov     [rsp+70h+var_50], rax
0x180203a70  lea     r9, a0; ": {0}"
0x180203a77  mov     r8d, r14d
0x180203a7a  mov     dl, 1
0x180203a7c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180203a83  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180203a88  mov     edx, 25Dh; int
0x180203a8d  lea     rcx, aOnecoreBaseSer_32; "onecore\\base\\servicing\\util\\servici"...
0x180203a94  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x180203a99  test    rbx, rbx
0x180203a9c  jz      short loc_180203AB3
0x180203a9e  mov     cs:qword_1803B0530, 0
0x180203aa9  jmp     short loc_180203AB3
0x180203aab  mov     rax, rbx
0x180203aae  xor     ebx, ebx
0x180203ab0  mov     [r14], rax
0x180203ab3  lea     rcx, [rbp+var_30]
0x180203ab7  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180203abc  nop
0x180203abd  test    rbx, rbx
0x180203ac0  jz      short loc_180203AE8
0x180203ac2  mov     rcx, rbx; hLibModule
0x180203ac5  call    cs:__imp_FreeLibrary
0x180203acc  nop     dword ptr [rax+rax+00h]
0x180203ad1  test    eax, eax
0x180203ad3  jnz     short loc_180203AE8
0x180203ad5  call    cs:__imp_GetLastError
0x180203adc  nop     dword ptr [rax+rax+00h]
0x180203ae1  mov     ecx, 7
0x180203ae6  int     29h; Win8: RtlFailFast(ecx)
0x180203ae8  test    rdi, rdi
0x180203aeb  jz      short loc_180203AF7
0x180203aed  lea     rcx, [rdi-8]; void *
0x180203af1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180203af6  nop
0x180203af7  mov     eax, esi
0x180203af9  mov     rcx, [rbp+var_8]
0x180203afd  xor     rcx, rsp; StackCookie
0x180203b00  call    __security_check_cookie
0x180203b05  lea     r11, [rsp+70h+var_s0]
0x180203b0a  mov     rbx, [r11+28h]
0x180203b0e  mov     rsi, [r11+30h]
0x180203b12  mov     rsp, r11
0x180203b15  pop     r14
0x180203b17  pop     rdi
0x180203b18  pop     rbp
0x180203b19  retn
```

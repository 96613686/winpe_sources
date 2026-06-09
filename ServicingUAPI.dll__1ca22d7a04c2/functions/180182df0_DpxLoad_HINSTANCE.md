# DpxLoad(HINSTANCE__ * *)

- ea: `0x180182df0`
- end: `0x1801831aa`
- name: `?DpxLoad@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `954`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006def0`
- `0x1800a2fcc`
- `0x1800cd784`
- `0x1800f3aa0`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000e098`
- `0x18000f614`
- `0x18000f874`
- `0x180046050`
- `0x180050fd0`
- `0x180182d50`
- `0x180182df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180182ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801830a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180182ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801830a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183165`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180183087`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180183087`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180183155`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180183155`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180182f15`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180182fb6`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180182fda`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180182f15`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180182fb6`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180182fda`

## string_xrefs

- `0x180182fd3`: `Dpx.dll`
- `0x180183027`: `Failed to load DPX DLL`
- `0x180182e99`: `dpx.dll`
- `0x180182f2d`: `Servicing\dpx.dll`
- `0x180182ec1`: `Failed to get path to dpx.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DpxLoad(HINSTANCE *a1)
{
  LPCWSTR v2; // rdi
  HMODULE Library; // rbx
  signed int Win32PathOfSiblingFile; // esi
  __int64 v5; // rdx
  int v6; // edx
  __int64 v7; // rdx
  __int64 v8; // rdx
  signed int LastError; // eax
  __int64 v10; // rdx
  signed int v11; // eax
  __int64 v12; // rdx
  HINSTANCE v13; // rax
  LPCWSTR v15; // [rsp+30h] [rbp-40h] BYREF
  int *v16; // [rsp+38h] [rbp-38h]
  __int128 v17; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+60h] [rbp-10h] BYREF

  v19 = -2;
  v2 = 0;
  v15 = 0;
  Library = 0;
  v17 = 0;
  lpLibFileName = 0;
  if ( !a1 )
  {
    Win32PathOfSiblingFile = -2147467261;
    v20 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No dpx handle specified");
      v15 = (LPCWSTR)&v20;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v5,
        3,
        ": {0}");
    }
    v6 = 575;
LABEL_23:
    DebugOnError("onecore\\base\\servicing\\util\\servicinghelper.cpp", v6);
    goto LABEL_34;
  }
  Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(DpxLoad, L"dpx.dll", &v17);
  v20 = Win32PathOfSiblingFile;
  if ( Win32PathOfSiblingFile < 0 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get path to dpx.dll");
      v15 = (LPCWSTR)&v20;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {0}");
    }
    v6 = 578;
    goto LABEL_23;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 8u);
  if ( !Library )
  {
    Win32PathOfSiblingFile = PathGetWindowsDirectory(&v15, L"Servicing\\dpx.dll");
    v20 = Win32PathOfSiblingFile;
    if ( Win32PathOfSiblingFile < 0 )
    {
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get online Windir");
        v16 = &v20;
        LOBYTE(v8) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v8,
          3,
          ": {0}");
      }
      DebugOnError("onecore\\base\\servicing\\util\\servicinghelper.cpp", 590);
      v2 = v15;
      goto LABEL_34;
    }
    v2 = v15;
    Library = LoadLibraryExW(v15, 0, 0);
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
        v20 = Win32PathOfSiblingFile;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load DPX DLL");
          v16 = &v20;
          LOBYTE(v10) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v10,
            3,
            ": {0}");
        }
        v6 = 601;
        goto LABEL_23;
      }
    }
  }
  qword_180243B00 = (__int64)GetProcAddress(Library, "DpxNewJob");
  if ( qword_180243B00 )
  {
    v13 = Library;
    Library = 0;
    *a1 = v13;
  }
  else
  {
    v11 = GetLastError();
    Win32PathOfSiblingFile = v11;
    if ( v11 > 0 )
      Win32PathOfSiblingFile = (unsigned __int16)v11 | 0x80070000;
    if ( Win32PathOfSiblingFile >= 0 )
      Win32PathOfSiblingFile = -2147467259;
    v20 = Win32PathOfSiblingFile;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get proc address for DpxNewJob.");
      v16 = &v20;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {0}");
    }
    DebugOnError("onecore\\base\\servicing\\util\\servicinghelper.cpp", 605);
    qword_180243B00 = 0;
  }
LABEL_34:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v17);
  if ( Library && !FreeLibrary(Library) )
  {
    GetLastError();
    __fastfail(7u);
  }
  if ( v2 )
    operator delete((void *)(v2 - 4));
  return (unsigned int)Win32PathOfSiblingFile;
}

```

## disassembly

```asm
0x180182df0  mov     rax, rsp
0x180182df3  push    rbp
0x180182df4  push    rdi
0x180182df5  push    r14
0x180182df7  mov     rbp, rsp
0x180182dfa  sub     rsp, 70h
0x180182dfe  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180182e06  mov     [rax+10h], rbx
0x180182e0a  mov     [rax+18h], rsi
0x180182e0e  mov     rax, cs:__security_cookie
0x180182e15  xor     rax, rsp
0x180182e18  mov     [rbp+var_8], rax
0x180182e1c  mov     r14, rcx
0x180182e1f  xor     edi, edi
0x180182e21  mov     [rbp+var_40], rdi
0x180182e25  xor     ebx, ebx
0x180182e27  xorps   xmm0, xmm0
0x180182e2a  xor     eax, eax
0x180182e2c  movups  [rbp+var_30], xmm0
0x180182e30  mov     [rbp+lpLibFileName], rax
0x180182e34  test    rcx, rcx
0x180182e37  jnz     short loc_180182E95
0x180182e39  mov     esi, 80004003h
0x180182e3e  mov     [rbp+var_10], esi
0x180182e41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182e48  test    rcx, rcx
0x180182e4b  jz      short loc_180182E8B
0x180182e4d  lea     r9, aNoDpxHandleSpe; "No dpx handle specified"
0x180182e54  lea     r14d, [rdi+3]
0x180182e58  mov     r8d, r14d
0x180182e5b  xor     edx, edx
0x180182e5d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182e62  lea     rax, [rbp+var_10]
0x180182e66  mov     [rbp+var_40], rax
0x180182e6a  lea     rax, [rbp+var_40]
0x180182e6e  mov     [rsp+70h+var_50], rax
0x180182e73  lea     r9, a0; ": {0}"
0x180182e7a  mov     r8d, r14d
0x180182e7d  mov     dl, 1
0x180182e7f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182e86  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182e8b  mov     edx, 23Fh
0x180182e90  jmp     loc_18018306C
0x180182e95  lea     r8, [rbp+var_30]
0x180182e99  lea     rdx, aDpxDll_0; "dpx.dll"
0x180182ea0  lea     rcx, ?DpxLoad@@YAJPEAPEAUHINSTANCE__@@@Z; DpxLoad(HINSTANCE__ * *)
0x180182ea7  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x180182eac  mov     esi, eax
0x180182eae  mov     [rbp+var_10], eax
0x180182eb1  test    eax, eax
0x180182eb3  jns     short loc_180182F0B
0x180182eb5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182ebc  test    rcx, rcx
0x180182ebf  jz      short loc_180182F01
0x180182ec1  lea     r9, aFailedToGetPat_2; "Failed to get path to dpx.dll"
0x180182ec8  mov     r14d, 3
0x180182ece  mov     r8d, r14d
0x180182ed1  xor     edx, edx
0x180182ed3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182ed8  lea     rax, [rbp+var_10]
0x180182edc  mov     [rbp+var_40], rax
0x180182ee0  lea     rax, [rbp+var_40]
0x180182ee4  mov     [rsp+70h+var_50], rax
0x180182ee9  lea     r9, a0; ": {0}"
0x180182ef0  mov     r8d, r14d
0x180182ef3  mov     dl, 1
0x180182ef5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182efc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182f01  mov     edx, 242h
0x180182f06  jmp     loc_18018306C
0x180182f0b  xor     edx, edx; hFile
0x180182f0d  lea     r8d, [rdx+8]; dwFlags
0x180182f11  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180182f15  call    cs:__imp_LoadLibraryExW
0x180182f1c  nop     dword ptr [rax+rax+00h]
0x180182f21  mov     rbx, rax
0x180182f24  test    rax, rax
0x180182f27  jnz     loc_18018307D
0x180182f2d  lea     rdx, aServicingDpxDl; "Servicing\\dpx.dll"
0x180182f34  lea     rcx, [rbp+var_40]
0x180182f38  call    PathGetWindowsDirectory
0x180182f3d  mov     esi, eax
0x180182f3f  mov     [rbp+var_10], eax
0x180182f42  test    eax, eax
0x180182f44  jns     short loc_180182FAA
0x180182f46  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182f4d  test    rcx, rcx
0x180182f50  jz      short loc_180182F90
0x180182f52  lea     r9, aFailedToGetOnl; "Failed to get online Windir"
0x180182f59  lea     r14d, [rbx+3]
0x180182f5d  mov     r8d, r14d
0x180182f60  xor     edx, edx
0x180182f62  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182f67  lea     rax, [rbp+var_10]
0x180182f6b  mov     [rbp+var_38], rax
0x180182f6f  lea     rax, [rbp+var_38]
0x180182f73  mov     [rsp+70h+var_50], rax
0x180182f78  lea     r9, a0; ": {0}"
0x180182f7f  mov     r8d, r14d
0x180182f82  mov     dl, 1
0x180182f84  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182f8b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180182f90  mov     edx, 24Eh; int
0x180182f95  lea     rcx, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180182f9c  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x180182fa1  mov     rdi, [rbp+var_40]
0x180182fa5  jmp     loc_180183143
0x180182faa  xor     r8d, r8d; dwFlags
0x180182fad  xor     edx, edx; hFile
0x180182faf  mov     rdi, [rbp+var_40]
0x180182fb3  mov     rcx, rdi; lpLibFileName
0x180182fb6  call    cs:__imp_LoadLibraryExW
0x180182fbd  nop     dword ptr [rax+rax+00h]
0x180182fc2  mov     rbx, rax
0x180182fc5  test    rax, rax
0x180182fc8  jnz     loc_18018307D
0x180182fce  xor     r8d, r8d; dwFlags
0x180182fd1  xor     edx, edx; hFile
0x180182fd3  lea     rcx, aDpxDll; "Dpx.dll"
0x180182fda  call    cs:__imp_LoadLibraryExW
0x180182fe1  nop     dword ptr [rax+rax+00h]
0x180182fe6  mov     rbx, rax
0x180182fe9  test    rax, rax
0x180182fec  jnz     loc_18018307D
0x180182ff2  call    cs:__imp_GetLastError
0x180182ff9  nop     dword ptr [rax+rax+00h]
0x180182ffe  mov     esi, eax
0x180183000  test    eax, eax
0x180183002  jle     short loc_18018300D
0x180183004  movzx   esi, ax
0x180183007  or      esi, 80070000h
0x18018300d  test    esi, esi
0x18018300f  js      short loc_180183016
0x180183011  mov     esi, 80004005h
0x180183016  mov     eax, esi
0x180183018  mov     [rbp+var_10], eax
0x18018301b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183022  test    rcx, rcx
0x180183025  jz      short loc_180183067
0x180183027  lea     r9, aFailedToLoadDp; "Failed to load DPX DLL"
0x18018302e  mov     r14d, 3
0x180183034  mov     r8d, r14d
0x180183037  xor     edx, edx
0x180183039  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018303e  lea     rax, [rbp+var_10]
0x180183042  mov     [rbp+var_38], rax
0x180183046  lea     rax, [rbp+var_38]
0x18018304a  mov     [rsp+70h+var_50], rax
0x18018304f  lea     r9, a0; ": {0}"
0x180183056  mov     r8d, r14d
0x180183059  mov     dl, 1
0x18018305b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183062  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180183067  mov     edx, 259h; int
0x18018306c  lea     rcx, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183073  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x180183078  jmp     loc_180183143
0x18018307d  lea     rdx, aDpxnewjob; "DpxNewJob"
0x180183084  mov     rcx, rbx; hModule
0x180183087  call    cs:__imp_GetProcAddress
0x18018308e  nop     dword ptr [rax+rax+00h]
0x180183093  mov     cs:qword_180243B00, rax
0x18018309a  test    rax, rax
0x18018309d  jnz     loc_18018313B
0x1801830a3  call    cs:__imp_GetLastError
0x1801830aa  nop     dword ptr [rax+rax+00h]
0x1801830af  mov     esi, eax
0x1801830b1  test    eax, eax
0x1801830b3  jle     short loc_1801830BE
0x1801830b5  movzx   esi, ax
0x1801830b8  or      esi, 80070000h
0x1801830be  test    esi, esi
0x1801830c0  js      short loc_1801830C7
0x1801830c2  mov     esi, 80004005h
0x1801830c7  mov     eax, esi
0x1801830c9  mov     [rbp+var_10], eax
0x1801830cc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801830d3  test    rcx, rcx
0x1801830d6  jz      short loc_180183118
0x1801830d8  lea     r9, aFailedToGetPro_7; "Failed to get proc address for DpxNewJo"...
0x1801830df  mov     r14d, 3
0x1801830e5  mov     r8d, r14d
0x1801830e8  xor     edx, edx
0x1801830ea  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801830ef  lea     rax, [rbp+var_10]
0x1801830f3  mov     [rbp+var_38], rax
0x1801830f7  lea     rax, [rbp+var_38]
0x1801830fb  mov     [rsp+70h+var_50], rax
0x180183100  lea     r9, a0; ": {0}"
0x180183107  mov     r8d, r14d
0x18018310a  mov     dl, 1
0x18018310c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180183113  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180183118  mov     edx, 25Dh; int
0x18018311d  lea     rcx, aOnecoreBaseSer_35; "onecore\\base\\servicing\\util\\servici"...
0x180183124  call    ?DebugOnError@@YAXPEBDH@Z; DebugOnError(char const *,int)
0x180183129  test    rbx, rbx
0x18018312c  jz      short loc_180183143
0x18018312e  mov     cs:qword_180243B00, 0
0x180183139  jmp     short loc_180183143
0x18018313b  mov     rax, rbx
0x18018313e  xor     ebx, ebx
0x180183140  mov     [r14], rax
0x180183143  lea     rcx, [rbp+var_30]
0x180183147  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x18018314c  nop
0x18018314d  test    rbx, rbx
0x180183150  jz      short loc_180183178
0x180183152  mov     rcx, rbx; hLibModule
0x180183155  call    cs:__imp_FreeLibrary
0x18018315c  nop     dword ptr [rax+rax+00h]
0x180183161  test    eax, eax
0x180183163  jnz     short loc_180183178
0x180183165  call    cs:__imp_GetLastError
0x18018316c  nop     dword ptr [rax+rax+00h]
0x180183171  mov     ecx, 7
0x180183176  int     29h; Win8: RtlFailFast(ecx)
0x180183178  test    rdi, rdi
0x18018317b  jz      short loc_180183186
0x18018317d  lea     rcx, [rdi-8]; Block
0x180183181  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180183186  mov     eax, esi
0x180183188  mov     rcx, [rbp+var_8]
0x18018318c  xor     rcx, rsp; StackCookie
0x18018318f  call    __security_check_cookie
0x180183194  lea     r11, [rsp+70h+var_s0]
0x180183199  mov     rbx, [r11+28h]
0x18018319d  mov     rsi, [r11+30h]
0x1801831a1  mov     rsp, r11
0x1801831a4  pop     r14
0x1801831a6  pop     rdi
0x1801831a7  pop     rbp
0x1801831a8  retn
```

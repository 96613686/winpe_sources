# CIUClient::Initialize(DeviceContext *)

- ea: `0x1800df08c`
- end: `0x1800df5a2`
- name: `?Initialize@CIUClient@@QEAAJPEAVDeviceContext@@@Z`
- size: `1302`
- prototype: `int(CIUClient *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180092cc4`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001b9e4`
- `0x1800296a4`
- `0x18002e3a4`
- `0x18003d278`
- `0x18003df98`
- `0x180042764`
- `0x180051984`
- `0x1800df08c`
- `0x1801133b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df4ea`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df345`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df3e2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df47f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df4aa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df4d5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df345`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df3e2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df47f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df4aa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800df4d5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800df272`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800df272`

## string_xrefs

- `0x1800df475`: `GetTokenInfo`
- `0x1800df4a0`: `FreeGetTokenInfoResults`
- `0x1800df0d4`: `System32\updateapi.dll`
- `0x1800df20e`: `updateapi.dll`
- `0x1800df1c5`: `Failed getting external stack path`
- `0x1800df0fc`: `Failed getting windows relative path`
- `0x1800df374`: `Failed to get proc address for GetInstalledPackageInfo.`
- `0x1800df33b`: `GetInstalledPackageInfo`
- `0x1800df2ae`: `Failed to load UpdateAPI DLL`
- `0x1800df254`: `Loading updateapi: {0}`
- `0x1800df4bf`: `Warning: Failed to get proc address for FreeGetTokenInfoResults.`
- `0x1800df494`: `Warning: Failed to get proc address for GetTokenInfo.`
- `0x1800df411`: `Failed to get proc address for FreeInstalledPackageInfo.`
- `0x1800df3d8`: `FreeInstalledPackageInfo`
- `0x1800df504`: `Failed to get proc address for GetStateRootStagingPath.`
- `0x1800df4cb`: `GetStateRootStagingPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIUClient::Initialize(CIUClient *this, struct DeviceContext *a2)
{
  int WindowsRelativePath; // eax
  __int64 v5; // rdx
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rdx
  _QWORD *v10; // rdx
  int v12; // eax
  __int64 v13; // rdx
  HMODULE Library; // rax
  signed int LastError; // edi
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // ebx
  FARPROC ProcAddress; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  FARPROC v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // eax
  FARPROC v26; // rax
  FARPROC v27; // rax
  FARPROC v28; // rax
  __int64 v29; // rdx
  unsigned int v30; // eax
  unsigned int *v31; // [rsp+20h] [rbp-40h]
  unsigned int v32[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v33; // [rsp+38h] [rbp-28h]
  unsigned int v34; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v33 = -2;
  lpLibFileName = 0;
  if ( InMobile() )
  {
    WindowsRelativePath = DeviceContext::GetWindowsRelativePath(
                            a2,
                            L"System32\\updateapi.dll",
                            (struct AutoScz *)&lpLibFileName);
    v6 = WindowsRelativePath;
    if ( WindowsRelativePath < 0 )
    {
      v34 = WindowsRelativePath;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting windows relative path");
        *(_QWORD *)v32 = &v34;
        v31 = v32;
        LOBYTE(v7) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v7,
          3,
          ": {}");
      }
      v8 = 12;
      goto LABEL_6;
    }
  }
  else
  {
    if ( !*(_BYTE *)a2 || !*((_QWORD *)a2 + 3) )
      goto LABEL_66;
    v10 = (_QWORD *)((char *)a2 + 8);
    if ( !(*((_QWORD *)a2 + 4) <= 7u ? (struct DeviceContext *)((char *)a2 + 8) : (struct DeviceContext *)*v10) )
      goto LABEL_66;
    if ( *((_QWORD *)a2 + 4) > 7u )
      v10 = (_QWORD *)*v10;
    v12 = SczAllocFromSzAndEnsureBackslash(&lpLibFileName, v10);
    v6 = v12;
    if ( v12 < 0 )
    {
      v34 = v12;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed getting external stack path");
        *(_QWORD *)v32 = &v34;
        v31 = v32;
        LOBYTE(v13) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v13,
          3,
          ": {}");
      }
      v8 = 17;
      goto LABEL_6;
    }
    v6 = SczAllocConcatSz(&lpLibFileName, L"updateapi.dll");
    if ( v6 < 0 )
    {
      v8 = 19;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\ciuclient.cpp",
        (const char *)(unsigned int)v6,
        (int)v31);
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4));
      return (unsigned int)v6;
    }
    if ( !(unsigned int)DoesFileExist(lpLibFileName) )
      goto LABEL_66;
  }
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(v5) = 1;
    LogAdapter::Logger::LogNumObjects<AutoScz>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v5,
      1,
      "Loading updateapi: {0}",
      &lpLibFileName);
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  if ( *(_QWORD *)this )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800DF5A1LL);
  }
  *(_QWORD *)this = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetInstalledPackageInfo");
    *((_QWORD *)this + 1) = ProcAddress;
    if ( ProcAddress )
    {
      v23 = GetProcAddress(*(HMODULE *)this, "FreeInstalledPackageInfo");
      *((_QWORD *)this + 2) = v23;
      if ( v23 )
      {
        v26 = GetProcAddress(*(HMODULE *)this, "GetTokenInfo");
        *((_QWORD *)this + 3) = v26;
        if ( !v26 )
          LogAdapter::TraceInfo<>("Warning: Failed to get proc address for GetTokenInfo.");
        v27 = GetProcAddress(*(HMODULE *)this, "FreeGetTokenInfoResults");
        *((_QWORD *)this + 4) = v27;
        if ( !v27 )
          LogAdapter::TraceInfo<>("Warning: Failed to get proc address for FreeGetTokenInfoResults.");
        v28 = GetProcAddress(*(HMODULE *)this, "GetStateRootStagingPath");
        *((_QWORD *)this + 5) = v28;
        if ( !v28 )
        {
          LastError = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to get proc address for GetStateRootStagingPath.");
            if ( LastError > 0 )
              v30 = (unsigned __int16)LastError | 0x80070000;
            else
              v30 = LastError;
            v34 = v30;
            *(_QWORD *)v32 = &v34;
            v31 = v32;
            LOBYTE(v29) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v29,
              3,
              ": {0}");
          }
          if ( LastError )
          {
            v18 = 59;
            goto LABEL_35;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to get proc address for FreeInstalledPackageInfo.");
          if ( LastError > 0 )
            v25 = (unsigned __int16)LastError | 0x80070000;
          else
            v25 = LastError;
          v34 = v25;
          *(_QWORD *)v32 = &v34;
          v31 = v32;
          LOBYTE(v24) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v24,
            3,
            ": {0}");
        }
        if ( LastError )
        {
          v18 = 43;
          goto LABEL_35;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get proc address for GetInstalledPackageInfo.");
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        else
          v22 = LastError;
        v34 = v22;
        *(_QWORD *)v32 = &v34;
        v31 = v32;
        LOBYTE(v21) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v21,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v18 = 40;
        goto LABEL_35;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to load UpdateAPI DLL");
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      else
        v17 = LastError;
      v34 = v17;
      *(_QWORD *)v32 = &v34;
      v31 = v32;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v16,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v18 = 37;
LABEL_35:
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v18,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\ciuclient.cpp",
              (const char *)(unsigned int)LastError,
              (unsigned int)v31);
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4));
      return v19;
    }
  }
LABEL_66:
  if ( lpLibFileName )
    operator delete((void *)(lpLibFileName - 4));
  return 0;
}

```

## disassembly

```asm
0x1800df08c  mov     rax, rsp
0x1800df08f  push    rbp
0x1800df090  mov     rbp, rsp
0x1800df093  sub     rsp, 60h
0x1800df097  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x1800df09f  mov     [rax+18h], rbx
0x1800df0a3  mov     [rax+20h], rdi
0x1800df0a7  mov     rax, cs:__security_cookie
0x1800df0ae  xor     rax, rsp
0x1800df0b1  mov     [rbp+var_10], rax
0x1800df0b5  mov     rdi, rdx
0x1800df0b8  mov     rbx, rcx
0x1800df0bb  mov     [rbp+lpLibFileName], 0
0x1800df0c3  call    ?InMobile@@YA_NXZ; InMobile(void)
0x1800df0c8  test    al, al
0x1800df0ca  jz      loc_1800DF16D
0x1800df0d0  lea     r8, [rbp+lpLibFileName]; struct AutoScz *
0x1800df0d4  lea     rdx, aSystem32Update_0; "System32\\updateapi.dll"
0x1800df0db  mov     rcx, rdi; this
0x1800df0de  call    ?GetWindowsRelativePath@DeviceContext@@QEBAJPEB_WPEAVAutoScz@@@Z; DeviceContext::GetWindowsRelativePath(wchar_t const *,AutoScz *)
0x1800df0e3  mov     edi, eax
0x1800df0e5  test    eax, eax
0x1800df0e7  jns     loc_1800DF23F
0x1800df0ed  mov     [rbp+var_20], eax
0x1800df0f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df0f7  test    rcx, rcx
0x1800df0fa  jz      short loc_1800DF13B
0x1800df0fc  lea     r9, aFailedGettingW_3; "Failed getting windows relative path"
0x1800df103  mov     ebx, 3
0x1800df108  mov     r8d, ebx
0x1800df10b  xor     edx, edx
0x1800df10d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800df112  lea     rax, [rbp+var_20]
0x1800df116  mov     qword ptr [rbp+var_30], rax
0x1800df11a  lea     rax, [rbp+var_30]
0x1800df11e  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800df123  lea     r9, asc_1801CAFB4; ": {}"
0x1800df12a  mov     r8d, ebx
0x1800df12d  mov     dl, 1
0x1800df12f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df136  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800df13b  mov     edx, 0Ch; void *
0x1800df140  mov     rcx, [rbp+8]; this
0x1800df144  mov     r9d, edi; char *
0x1800df147  lea     r8, aOnecoreBaseSer_16; "onecore\\base\\servicing\\arbiter\\ciuc"...
0x1800df14e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df153  nop
0x1800df154  mov     rcx, [rbp+lpLibFileName]
0x1800df158  test    rcx, rcx
0x1800df15b  jz      short loc_1800DF166
0x1800df15d  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800df161  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df166  mov     eax, edi
0x1800df168  jmp     loc_1800DF578
0x1800df16d  cmp     byte ptr [rdi], 0
0x1800df170  jz      loc_1800DF564
0x1800df176  cmp     qword ptr [rdi+18h], 0
0x1800df17b  jz      loc_1800DF564
0x1800df181  lea     rdx, [rdi+8]
0x1800df185  cmp     qword ptr [rdx+18h], 7
0x1800df18a  jbe     short loc_1800DF191
0x1800df18c  mov     rax, [rdx]
0x1800df18f  jmp     short loc_1800DF194
0x1800df191  mov     rax, rdx
0x1800df194  test    rax, rax
0x1800df197  jz      loc_1800DF564
0x1800df19d  cmp     qword ptr [rdx+18h], 7
0x1800df1a2  jbe     short loc_1800DF1A7
0x1800df1a4  mov     rdx, [rdx]
0x1800df1a7  lea     rcx, [rbp+lpLibFileName]
0x1800df1ab  call    SczAllocFromSzAndEnsureBackslash
0x1800df1b0  mov     edi, eax
0x1800df1b2  test    eax, eax
0x1800df1b4  jns     short loc_1800DF20E
0x1800df1b6  mov     [rbp+var_20], eax
0x1800df1b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df1c0  test    rcx, rcx
0x1800df1c3  jz      short loc_1800DF204
0x1800df1c5  lea     r9, aFailedGettingE_0; "Failed getting external stack path"
0x1800df1cc  mov     ebx, 3
0x1800df1d1  mov     r8d, ebx
0x1800df1d4  xor     edx, edx
0x1800df1d6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800df1db  lea     rax, [rbp+var_20]
0x1800df1df  mov     qword ptr [rbp+var_30], rax
0x1800df1e3  lea     rax, [rbp+var_30]
0x1800df1e7  mov     qword ptr [rsp+60h+var_40], rax
0x1800df1ec  lea     r9, asc_1801CAFB4; ": {}"
0x1800df1f3  mov     r8d, ebx
0x1800df1f6  mov     dl, 1
0x1800df1f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df1ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800df204  mov     edx, 11h
0x1800df209  jmp     loc_1800DF140
0x1800df20e  lea     rdx, aUpdateapiDll; "updateapi.dll"
0x1800df215  lea     rcx, [rbp+lpLibFileName]
0x1800df219  call    SczAllocConcatSz
0x1800df21e  mov     edi, eax
0x1800df220  test    eax, eax
0x1800df222  jns     short loc_1800DF22E
0x1800df224  mov     edx, 13h
0x1800df229  jmp     loc_1800DF140
0x1800df22e  mov     rcx, [rbp+lpLibFileName]
0x1800df232  call    DoesFileExist
0x1800df237  test    eax, eax
0x1800df239  jz      loc_1800DF564
0x1800df23f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df246  test    rcx, rcx
0x1800df249  jz      short loc_1800DF269
0x1800df24b  lea     rax, [rbp+lpLibFileName]
0x1800df24f  mov     qword ptr [rsp+60h+var_40], rax
0x1800df254  lea     r9, aLoadingUpdatea; "Loading updateapi: {0}"
0x1800df25b  mov     r8d, 1
0x1800df261  mov     dl, r8b
0x1800df264  call    ??$LogNumObjects@VAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<AutoScz>(bool,LogAdapter::LogLevel,char const * const,AutoScz const &)
0x1800df269  xor     r8d, r8d; dwFlags
0x1800df26c  xor     edx, edx; hFile
0x1800df26e  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800df272  call    cs:__imp_LoadLibraryExW
0x1800df279  nop     dword ptr [rax+rax+00h]
0x1800df27e  cmp     qword ptr [rbx], 0
0x1800df282  jnz     loc_1800DF597
0x1800df288  mov     [rbx], rax
0x1800df28b  test    rax, rax
0x1800df28e  jnz     loc_1800DF33B
0x1800df294  call    cs:__imp_GetLastError
0x1800df29b  nop     dword ptr [rax+rax+00h]
0x1800df2a0  mov     edi, eax
0x1800df2a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df2a9  test    rcx, rcx
0x1800df2ac  jz      short loc_1800DF300
0x1800df2ae  lea     r9, aFailedToLoadUp; "Failed to load UpdateAPI DLL"
0x1800df2b5  mov     ebx, 3
0x1800df2ba  mov     r8d, ebx
0x1800df2bd  xor     edx, edx
0x1800df2bf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800df2c4  test    edi, edi
0x1800df2c6  jg      short loc_1800DF2CC
0x1800df2c8  mov     eax, edi
0x1800df2ca  jmp     short loc_1800DF2D4
0x1800df2cc  movzx   eax, di
0x1800df2cf  or      eax, 80070000h
0x1800df2d4  mov     [rbp+var_20], eax
0x1800df2d7  lea     rax, [rbp+var_20]
0x1800df2db  mov     qword ptr [rbp+var_30], rax
0x1800df2df  lea     rax, [rbp+var_30]
0x1800df2e3  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1800df2e8  lea     r9, a0; ": {0}"
0x1800df2ef  mov     r8d, ebx
0x1800df2f2  mov     dl, 1
0x1800df2f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df2fb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800df300  test    edi, edi
0x1800df302  jz      loc_1800DF564
0x1800df308  mov     edx, 25h ; '%'; void *
0x1800df30d  lea     r8, aOnecoreBaseSer_16; "onecore\\base\\servicing\\arbiter\\ciuc"...
0x1800df314  mov     r9d, edi; char *
0x1800df317  mov     rcx, [rbp+8]; this
0x1800df31b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800df320  mov     ebx, eax
0x1800df322  mov     rcx, [rbp+lpLibFileName]
0x1800df326  test    rcx, rcx
0x1800df329  jz      short loc_1800DF334
0x1800df32b  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800df32f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800df334  mov     eax, ebx
0x1800df336  jmp     loc_1800DF578
0x1800df33b  lea     rdx, aGetinstalledpa; "GetInstalledPackageInfo"
0x1800df342  mov     rcx, rax; hModule
0x1800df345  call    cs:__imp_GetProcAddress
0x1800df34c  nop     dword ptr [rax+rax+00h]
0x1800df351  mov     [rbx+8], rax
0x1800df355  test    rax, rax
0x1800df358  jnz     short loc_1800DF3D8
0x1800df35a  call    cs:__imp_GetLastError
0x1800df361  nop     dword ptr [rax+rax+00h]
0x1800df366  mov     edi, eax
0x1800df368  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df36f  test    rcx, rcx
0x1800df372  jz      short loc_1800DF3C6
0x1800df374  lea     r9, aFailedToGetPro_18; "Failed to get proc address for GetInsta"...
0x1800df37b  mov     ebx, 3
0x1800df380  mov     r8d, ebx
0x1800df383  xor     edx, edx
0x1800df385  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800df38a  test    edi, edi
0x1800df38c  jg      short loc_1800DF392
0x1800df38e  mov     eax, edi
0x1800df390  jmp     short loc_1800DF39A
0x1800df392  movzx   eax, di
0x1800df395  or      eax, 80070000h
0x1800df39a  mov     [rbp+var_20], eax
0x1800df39d  lea     rax, [rbp+var_20]
0x1800df3a1  mov     qword ptr [rbp+var_30], rax
0x1800df3a5  lea     rax, [rbp+var_30]
0x1800df3a9  mov     qword ptr [rsp+60h+var_40], rax
0x1800df3ae  lea     r9, a0; ": {0}"
0x1800df3b5  mov     r8d, ebx
0x1800df3b8  mov     dl, 1
0x1800df3ba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df3c1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800df3c6  test    edi, edi
0x1800df3c8  jz      loc_1800DF564
0x1800df3ce  mov     edx, 28h ; '('
0x1800df3d3  jmp     loc_1800DF30D
0x1800df3d8  lea     rdx, aFreeinstalledp; "FreeInstalledPackageInfo"
0x1800df3df  mov     rcx, [rbx]; hModule
0x1800df3e2  call    cs:__imp_GetProcAddress
0x1800df3e9  nop     dword ptr [rax+rax+00h]
0x1800df3ee  mov     [rbx+10h], rax
0x1800df3f2  test    rax, rax
0x1800df3f5  jnz     short loc_1800DF475
0x1800df3f7  call    cs:__imp_GetLastError
0x1800df3fe  nop     dword ptr [rax+rax+00h]
0x1800df403  mov     edi, eax
0x1800df405  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df40c  test    rcx, rcx
0x1800df40f  jz      short loc_1800DF463
0x1800df411  lea     r9, aFailedToGetPro_0; "Failed to get proc address for FreeInst"...
0x1800df418  mov     ebx, 3
0x1800df41d  mov     r8d, ebx
0x1800df420  xor     edx, edx
0x1800df422  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800df427  test    edi, edi
0x1800df429  jg      short loc_1800DF42F
0x1800df42b  mov     eax, edi
0x1800df42d  jmp     short loc_1800DF437
0x1800df42f  movzx   eax, di
0x1800df432  or      eax, 80070000h
0x1800df437  mov     [rbp+var_20], eax
0x1800df43a  lea     rax, [rbp+var_20]
0x1800df43e  mov     qword ptr [rbp+var_30], rax
0x1800df442  lea     rax, [rbp+var_30]
0x1800df446  mov     qword ptr [rsp+60h+var_40], rax
0x1800df44b  lea     r9, a0; ": {0}"
0x1800df452  mov     r8d, ebx
0x1800df455  mov     dl, 1
0x1800df457  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df45e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800df463  test    edi, edi
0x1800df465  jz      loc_1800DF564
0x1800df46b  mov     edx, 2Bh ; '+'
0x1800df470  jmp     loc_1800DF30D
0x1800df475  lea     rdx, aGettokeninfo; "GetTokenInfo"
0x1800df47c  mov     rcx, [rbx]; hModule
0x1800df47f  call    cs:__imp_GetProcAddress
0x1800df486  nop     dword ptr [rax+rax+00h]
0x1800df48b  mov     [rbx+18h], rax
0x1800df48f  test    rax, rax
0x1800df492  jnz     short loc_1800DF4A0
0x1800df494  lea     rcx, aWarningFailedT; "Warning: Failed to get proc address for"...
0x1800df49b  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800df4a0  lea     rdx, aFreegettokenin; "FreeGetTokenInfoResults"
0x1800df4a7  mov     rcx, [rbx]; hModule
0x1800df4aa  call    cs:__imp_GetProcAddress
0x1800df4b1  nop     dword ptr [rax+rax+00h]
0x1800df4b6  mov     [rbx+20h], rax
0x1800df4ba  test    rax, rax
0x1800df4bd  jnz     short loc_1800DF4CB
0x1800df4bf  lea     rcx, aWarningFailedT_0; "Warning: Failed to get proc address for"...
0x1800df4c6  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800df4cb  lea     rdx, aGetstaterootst; "GetStateRootStagingPath"
0x1800df4d2  mov     rcx, [rbx]; hModule
0x1800df4d5  call    cs:__imp_GetProcAddress
0x1800df4dc  nop     dword ptr [rax+rax+00h]
0x1800df4e1  mov     [rbx+28h], rax
0x1800df4e5  test    rax, rax
0x1800df4e8  jnz     short loc_1800DF564
0x1800df4ea  call    cs:__imp_GetLastError
0x1800df4f1  nop     dword ptr [rax+rax+00h]
0x1800df4f6  mov     edi, eax
0x1800df4f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df4ff  test    rcx, rcx
0x1800df502  jz      short loc_1800DF556
0x1800df504  lea     r9, aFailedToGetPro_11; "Failed to get proc address for GetState"...
0x1800df50b  mov     ebx, 3
0x1800df510  mov     r8d, ebx
0x1800df513  xor     edx, edx
0x1800df515  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800df51a  test    edi, edi
0x1800df51c  jg      short loc_1800DF522
0x1800df51e  mov     eax, edi
0x1800df520  jmp     short loc_1800DF52A
0x1800df522  movzx   eax, di
0x1800df525  or      eax, 80070000h
0x1800df52a  mov     [rbp+var_20], eax
0x1800df52d  lea     rax, [rbp+var_20]
0x1800df531  mov     qword ptr [rbp+var_30], rax
0x1800df535  lea     rax, [rbp+var_30]
0x1800df539  mov     qword ptr [rsp+60h+var_40], rax
0x1800df53e  lea     r9, a0; ": {0}"
0x1800df545  mov     r8d, ebx
0x1800df548  mov     dl, 1
0x1800df54a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800df551  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800df556  test    edi, edi
0x1800df558  jz      short loc_1800DF564
0x1800df55a  mov     edx, 3Bh ; ';'
0x1800df55f  jmp     loc_1800DF30D
0x1800df564  mov     rcx, [rbp+lpLibFileName]
  ... truncated ...
```

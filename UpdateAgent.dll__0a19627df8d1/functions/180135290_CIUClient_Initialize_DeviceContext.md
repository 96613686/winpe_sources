# CIUClient::Initialize(DeviceContext *)

- ea: `0x180135290`
- end: `0x1801357a6`
- name: `?Initialize@CIUClient@@QEAAJPEAVDeviceContext@@@Z`
- size: `1302`
- prototype: `int(CIUClient *__hidden this, struct DeviceContext *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800dd0e8`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18001270c`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3ec`
- `0x1800a76dc`
- `0x180135290`
- `0x1801488f0`
- `0x18014a56c`
- `0x18014b298`
- `0x18017657c`
- `0x1801e19ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180135549`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801355e6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180135683`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801356ae`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801356d9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180135549`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801355e6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180135683`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801356ae`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801356d9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180135476`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180135476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013555e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801355fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801356ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013555e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801355fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801356ee`

## string_xrefs

- `0x1801352d8`: `System32\updateapi.dll`
- `0x180135300`: `Failed getting windows relative path`
- `0x180135412`: `updateapi.dll`
- `0x1801353c9`: `Failed getting external stack path`
- `0x1801354b2`: `Failed to load UpdateAPI DLL`
- `0x180135458`: `Loading updateapi: {0}`
- `0x180135578`: `Failed to get proc address for GetInstalledPackageInfo.`
- `0x18013553f`: `GetInstalledPackageInfo`
- `0x180135615`: `Failed to get proc address for FreeInstalledPackageInfo.`
- `0x1801355dc`: `FreeInstalledPackageInfo`
- `0x180135698`: `Warning: Failed to get proc address for GetTokenInfo.`
- `0x180135679`: `GetTokenInfo`
- `0x1801356c3`: `Warning: Failed to get proc address for FreeGetTokenInfoResults.`
- `0x1801356a4`: `FreeGetTokenInfoResults`
- `0x180135708`: `Failed to get proc address for GetStateRootStagingPath.`
- `0x1801356cf`: `GetStateRootStagingPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIUClient::Initialize(CIUClient *this, struct DeviceContext *a2)
{
  const struct std::nothrow_t *v4; // rdx
  int WindowsRelativePath; // eax
  int v6; // edi
  __int64 v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  int v11; // eax
  __int64 v12; // rdx
  HMODULE Library; // rax
  signed int LastError; // edi
  unsigned int v15; // eax
  __int64 v16; // rdx
  const struct std::nothrow_t *v17; // rdx
  unsigned int v18; // ebx
  FARPROC ProcAddress; // rax
  unsigned int v20; // eax
  FARPROC v21; // rax
  unsigned int v22; // eax
  FARPROC v23; // rax
  FARPROC v24; // rax
  FARPROC v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // [rsp+20h] [rbp-40h]
  unsigned int v28[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v29; // [rsp+38h] [rbp-28h]
  unsigned int v30; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v29 = -2;
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
      v30 = WindowsRelativePath;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting windows relative path");
        *(_QWORD *)v28 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v28);
      }
      v7 = 12;
      goto LABEL_6;
    }
  }
  else
  {
    if ( !*(_BYTE *)a2 || !*((_QWORD *)a2 + 3) )
      goto LABEL_66;
    v4 = (struct DeviceContext *)((char *)a2 + 8);
    if ( !(*((_QWORD *)a2 + 4) <= 7u ? (struct DeviceContext *)((char *)a2 + 8) : *(struct DeviceContext **)v4) )
      goto LABEL_66;
    if ( *((_QWORD *)a2 + 4) > 7u )
      v4 = *(const struct std::nothrow_t **)v4;
    v11 = SczAllocFromSzAndEnsureBackslash(&lpLibFileName, v4);
    v6 = v11;
    if ( v11 < 0 )
    {
      v30 = v11;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting external stack path");
        *(_QWORD *)v28 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v28);
      }
      v7 = 17;
      goto LABEL_6;
    }
    v6 = SczAllocConcatSz(&lpLibFileName, L"updateapi.dll");
    if ( v6 < 0 )
    {
      v7 = 19;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\ciuclient.cpp",
        (const char *)(unsigned int)v6,
        v27);
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4), v8);
      return (unsigned int)v6;
    }
    if ( !(unsigned int)DoesFileExist(lpLibFileName, v12) )
      goto LABEL_66;
  }
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(v4) = 1;
    LogAdapter::Logger::LogNumObjects<AutoScz>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v4,
      1,
      "Loading updateapi: {0}",
      &lpLibFileName);
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  if ( *(_QWORD *)this )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801357A5LL);
  }
  *(_QWORD *)this = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetInstalledPackageInfo");
    *((_QWORD *)this + 1) = ProcAddress;
    if ( ProcAddress )
    {
      v21 = GetProcAddress(*(HMODULE *)this, "FreeInstalledPackageInfo");
      *((_QWORD *)this + 2) = v21;
      if ( v21 )
      {
        v23 = GetProcAddress(*(HMODULE *)this, "GetTokenInfo");
        *((_QWORD *)this + 3) = v23;
        if ( !v23 )
          LogAdapter::TraceInfo<>("Warning: Failed to get proc address for GetTokenInfo.");
        v24 = GetProcAddress(*(HMODULE *)this, "FreeGetTokenInfoResults");
        *((_QWORD *)this + 4) = v24;
        if ( !v24 )
          LogAdapter::TraceInfo<>("Warning: Failed to get proc address for FreeGetTokenInfoResults.");
        v25 = GetProcAddress(*(HMODULE *)this, "GetStateRootStagingPath");
        *((_QWORD *)this + 5) = v25;
        if ( !v25 )
        {
          LastError = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GetStateRootStagingPath.");
            if ( LastError > 0 )
              v26 = (unsigned __int16)LastError | 0x80070000;
            else
              v26 = LastError;
            v30 = v26;
            *(_QWORD *)v28 = &v30;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
              (__int64)v28);
          }
          if ( LastError )
          {
            v16 = 59;
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
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for FreeInstalledPackageInfo.");
          if ( LastError > 0 )
            v22 = (unsigned __int16)LastError | 0x80070000;
          else
            v22 = LastError;
          v30 = v22;
          *(_QWORD *)v28 = &v30;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)v28);
        }
        if ( LastError )
        {
          v16 = 43;
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
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get proc address for GetInstalledPackageInfo.");
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        else
          v20 = LastError;
        v30 = v20;
        *(_QWORD *)v28 = &v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)v28);
      }
      if ( LastError )
      {
        v16 = 40;
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
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load UpdateAPI DLL");
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      else
        v15 = LastError;
      v30 = v15;
      *(_QWORD *)v28 = &v30;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v28);
    }
    if ( LastError )
    {
      v16 = 37;
LABEL_35:
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v16,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\ciuclient.cpp",
              (const char *)(unsigned int)LastError,
              v27);
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4), v17);
      return v18;
    }
  }
LABEL_66:
  if ( lpLibFileName )
    operator delete((void *)(lpLibFileName - 4), v4);
  return 0;
}

```

## disassembly

```asm
0x180135290  mov     rax, rsp
0x180135293  push    rbp
0x180135294  mov     rbp, rsp
0x180135297  sub     rsp, 60h
0x18013529b  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x1801352a3  mov     [rax+18h], rbx
0x1801352a7  mov     [rax+20h], rdi
0x1801352ab  mov     rax, cs:__security_cookie
0x1801352b2  xor     rax, rsp
0x1801352b5  mov     [rbp+var_10], rax
0x1801352b9  mov     rdi, rdx
0x1801352bc  mov     rbx, rcx
0x1801352bf  mov     [rbp+lpLibFileName], 0
0x1801352c7  call    ?InMobile@@YA_NXZ; InMobile(void)
0x1801352cc  test    al, al
0x1801352ce  jz      loc_180135371
0x1801352d4  lea     r8, [rbp+lpLibFileName]; struct AutoScz *
0x1801352d8  lea     rdx, aSystem32Update_0; "System32\\updateapi.dll"
0x1801352df  mov     rcx, rdi; this
0x1801352e2  call    ?GetWindowsRelativePath@DeviceContext@@QEBAJPEB_WPEAVAutoScz@@@Z; DeviceContext::GetWindowsRelativePath(wchar_t const *,AutoScz *)
0x1801352e7  mov     edi, eax
0x1801352e9  test    eax, eax
0x1801352eb  jns     loc_180135443
0x1801352f1  mov     [rbp+var_20], eax
0x1801352f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801352fb  test    rcx, rcx
0x1801352fe  jz      short loc_18013533F
0x180135300  lea     r9, aFailedGettingW_3; "Failed getting windows relative path"
0x180135307  mov     ebx, 3
0x18013530c  mov     r8d, ebx
0x18013530f  xor     edx, edx
0x180135311  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180135316  lea     rax, [rbp+var_20]
0x18013531a  mov     qword ptr [rbp+var_30], rax
0x18013531e  lea     rax, [rbp+var_30]
0x180135322  mov     qword ptr [rsp+60h+var_40], rax; int
0x180135327  lea     r9, asc_1802C6678; ": {}"
0x18013532e  mov     r8d, ebx
0x180135331  mov     dl, 1
0x180135333  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013533a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013533f  mov     edx, 0Ch; void *
0x180135344  mov     rcx, [rbp+8]; this
0x180135348  mov     r9d, edi; char *
0x18013534b  lea     r8, aOnecoreBaseSer_17; "onecore\\base\\servicing\\arbiter\\ciuc"...
0x180135352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135357  nop
0x180135358  mov     rcx, [rbp+lpLibFileName]
0x18013535c  test    rcx, rcx
0x18013535f  jz      short loc_18013536A
0x180135361  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180135365  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013536a  mov     eax, edi
0x18013536c  jmp     loc_18013577C
0x180135371  cmp     byte ptr [rdi], 0
0x180135374  jz      loc_180135768
0x18013537a  cmp     qword ptr [rdi+18h], 0
0x18013537f  jz      loc_180135768
0x180135385  lea     rdx, [rdi+8]
0x180135389  cmp     qword ptr [rdx+18h], 7
0x18013538e  jbe     short loc_180135395
0x180135390  mov     rax, [rdx]
0x180135393  jmp     short loc_180135398
0x180135395  mov     rax, rdx
0x180135398  test    rax, rax
0x18013539b  jz      loc_180135768
0x1801353a1  cmp     qword ptr [rdx+18h], 7
0x1801353a6  jbe     short loc_1801353AB
0x1801353a8  mov     rdx, [rdx]
0x1801353ab  lea     rcx, [rbp+lpLibFileName]
0x1801353af  call    SczAllocFromSzAndEnsureBackslash
0x1801353b4  mov     edi, eax
0x1801353b6  test    eax, eax
0x1801353b8  jns     short loc_180135412
0x1801353ba  mov     [rbp+var_20], eax
0x1801353bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801353c4  test    rcx, rcx
0x1801353c7  jz      short loc_180135408
0x1801353c9  lea     r9, aFailedGettingE_0; "Failed getting external stack path"
0x1801353d0  mov     ebx, 3
0x1801353d5  mov     r8d, ebx
0x1801353d8  xor     edx, edx
0x1801353da  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801353df  lea     rax, [rbp+var_20]
0x1801353e3  mov     qword ptr [rbp+var_30], rax
0x1801353e7  lea     rax, [rbp+var_30]
0x1801353eb  mov     qword ptr [rsp+60h+var_40], rax
0x1801353f0  lea     r9, asc_1802C6678; ": {}"
0x1801353f7  mov     r8d, ebx
0x1801353fa  mov     dl, 1
0x1801353fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180135403  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180135408  mov     edx, 11h
0x18013540d  jmp     loc_180135344
0x180135412  lea     rdx, aUpdateapiDll; "updateapi.dll"
0x180135419  lea     rcx, [rbp+lpLibFileName]
0x18013541d  call    SczAllocConcatSz
0x180135422  mov     edi, eax
0x180135424  test    eax, eax
0x180135426  jns     short loc_180135432
0x180135428  mov     edx, 13h
0x18013542d  jmp     loc_180135344
0x180135432  mov     rcx, [rbp+lpLibFileName]
0x180135436  call    DoesFileExist
0x18013543b  test    eax, eax
0x18013543d  jz      loc_180135768
0x180135443  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013544a  test    rcx, rcx
0x18013544d  jz      short loc_18013546D
0x18013544f  lea     rax, [rbp+lpLibFileName]
0x180135453  mov     qword ptr [rsp+60h+var_40], rax
0x180135458  lea     r9, aLoadingUpdatea; "Loading updateapi: {0}"
0x18013545f  mov     r8d, 1
0x180135465  mov     dl, r8b
0x180135468  call    ??$LogNumObjects@VAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<AutoScz>(bool,LogAdapter::LogLevel,char const * const,AutoScz const &)
0x18013546d  xor     r8d, r8d; dwFlags
0x180135470  xor     edx, edx; hFile
0x180135472  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180135476  call    cs:__imp_LoadLibraryExW
0x18013547d  nop     dword ptr [rax+rax+00h]
0x180135482  cmp     qword ptr [rbx], 0
0x180135486  jnz     loc_18013579B
0x18013548c  mov     [rbx], rax
0x18013548f  test    rax, rax
0x180135492  jnz     loc_18013553F
0x180135498  call    cs:__imp_GetLastError
0x18013549f  nop     dword ptr [rax+rax+00h]
0x1801354a4  mov     edi, eax
0x1801354a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801354ad  test    rcx, rcx
0x1801354b0  jz      short loc_180135504
0x1801354b2  lea     r9, aFailedToLoadUp; "Failed to load UpdateAPI DLL"
0x1801354b9  mov     ebx, 3
0x1801354be  mov     r8d, ebx
0x1801354c1  xor     edx, edx
0x1801354c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801354c8  test    edi, edi
0x1801354ca  jg      short loc_1801354D0
0x1801354cc  mov     eax, edi
0x1801354ce  jmp     short loc_1801354D8
0x1801354d0  movzx   eax, di
0x1801354d3  or      eax, 80070000h
0x1801354d8  mov     [rbp+var_20], eax
0x1801354db  lea     rax, [rbp+var_20]
0x1801354df  mov     qword ptr [rbp+var_30], rax
0x1801354e3  lea     rax, [rbp+var_30]
0x1801354e7  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1801354ec  lea     r9, a0; ": {0}"
0x1801354f3  mov     r8d, ebx
0x1801354f6  mov     dl, 1
0x1801354f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801354ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180135504  test    edi, edi
0x180135506  jz      loc_180135768
0x18013550c  mov     edx, 25h ; '%'; void *
0x180135511  lea     r8, aOnecoreBaseSer_17; "onecore\\base\\servicing\\arbiter\\ciuc"...
0x180135518  mov     r9d, edi; char *
0x18013551b  mov     rcx, [rbp+8]; this
0x18013551f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135524  mov     ebx, eax
0x180135526  mov     rcx, [rbp+lpLibFileName]
0x18013552a  test    rcx, rcx
0x18013552d  jz      short loc_180135538
0x18013552f  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180135533  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180135538  mov     eax, ebx
0x18013553a  jmp     loc_18013577C
0x18013553f  lea     rdx, aGetinstalledpa; "GetInstalledPackageInfo"
0x180135546  mov     rcx, rax; hModule
0x180135549  call    cs:__imp_GetProcAddress
0x180135550  nop     dword ptr [rax+rax+00h]
0x180135555  mov     [rbx+8], rax
0x180135559  test    rax, rax
0x18013555c  jnz     short loc_1801355DC
0x18013555e  call    cs:__imp_GetLastError
0x180135565  nop     dword ptr [rax+rax+00h]
0x18013556a  mov     edi, eax
0x18013556c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180135573  test    rcx, rcx
0x180135576  jz      short loc_1801355CA
0x180135578  lea     r9, aFailedToGetPro_12; "Failed to get proc address for GetInsta"...
0x18013557f  mov     ebx, 3
0x180135584  mov     r8d, ebx
0x180135587  xor     edx, edx
0x180135589  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013558e  test    edi, edi
0x180135590  jg      short loc_180135596
0x180135592  mov     eax, edi
0x180135594  jmp     short loc_18013559E
0x180135596  movzx   eax, di
0x180135599  or      eax, 80070000h
0x18013559e  mov     [rbp+var_20], eax
0x1801355a1  lea     rax, [rbp+var_20]
0x1801355a5  mov     qword ptr [rbp+var_30], rax
0x1801355a9  lea     rax, [rbp+var_30]
0x1801355ad  mov     qword ptr [rsp+60h+var_40], rax
0x1801355b2  lea     r9, a0; ": {0}"
0x1801355b9  mov     r8d, ebx
0x1801355bc  mov     dl, 1
0x1801355be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801355c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801355ca  test    edi, edi
0x1801355cc  jz      loc_180135768
0x1801355d2  mov     edx, 28h ; '('
0x1801355d7  jmp     loc_180135511
0x1801355dc  lea     rdx, aFreeinstalledp; "FreeInstalledPackageInfo"
0x1801355e3  mov     rcx, [rbx]; hModule
0x1801355e6  call    cs:__imp_GetProcAddress
0x1801355ed  nop     dword ptr [rax+rax+00h]
0x1801355f2  mov     [rbx+10h], rax
0x1801355f6  test    rax, rax
0x1801355f9  jnz     short loc_180135679
0x1801355fb  call    cs:__imp_GetLastError
0x180135602  nop     dword ptr [rax+rax+00h]
0x180135607  mov     edi, eax
0x180135609  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180135610  test    rcx, rcx
0x180135613  jz      short loc_180135667
0x180135615  lea     r9, aFailedToGetPro_0; "Failed to get proc address for FreeInst"...
0x18013561c  mov     ebx, 3
0x180135621  mov     r8d, ebx
0x180135624  xor     edx, edx
0x180135626  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013562b  test    edi, edi
0x18013562d  jg      short loc_180135633
0x18013562f  mov     eax, edi
0x180135631  jmp     short loc_18013563B
0x180135633  movzx   eax, di
0x180135636  or      eax, 80070000h
0x18013563b  mov     [rbp+var_20], eax
0x18013563e  lea     rax, [rbp+var_20]
0x180135642  mov     qword ptr [rbp+var_30], rax
0x180135646  lea     rax, [rbp+var_30]
0x18013564a  mov     qword ptr [rsp+60h+var_40], rax
0x18013564f  lea     r9, a0; ": {0}"
0x180135656  mov     r8d, ebx
0x180135659  mov     dl, 1
0x18013565b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180135662  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180135667  test    edi, edi
0x180135669  jz      loc_180135768
0x18013566f  mov     edx, 2Bh ; '+'
0x180135674  jmp     loc_180135511
0x180135679  lea     rdx, aGettokeninfo; "GetTokenInfo"
0x180135680  mov     rcx, [rbx]; hModule
0x180135683  call    cs:__imp_GetProcAddress
0x18013568a  nop     dword ptr [rax+rax+00h]
0x18013568f  mov     [rbx+18h], rax
0x180135693  test    rax, rax
0x180135696  jnz     short loc_1801356A4
0x180135698  lea     rcx, aWarningFailedT; "Warning: Failed to get proc address for"...
0x18013569f  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1801356a4  lea     rdx, aFreegettokenin; "FreeGetTokenInfoResults"
0x1801356ab  mov     rcx, [rbx]; hModule
0x1801356ae  call    cs:__imp_GetProcAddress
0x1801356b5  nop     dword ptr [rax+rax+00h]
0x1801356ba  mov     [rbx+20h], rax
0x1801356be  test    rax, rax
0x1801356c1  jnz     short loc_1801356CF
0x1801356c3  lea     rcx, aWarningFailedT_0; "Warning: Failed to get proc address for"...
0x1801356ca  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1801356cf  lea     rdx, aGetstaterootst; "GetStateRootStagingPath"
0x1801356d6  mov     rcx, [rbx]; hModule
0x1801356d9  call    cs:__imp_GetProcAddress
0x1801356e0  nop     dword ptr [rax+rax+00h]
0x1801356e5  mov     [rbx+28h], rax
0x1801356e9  test    rax, rax
0x1801356ec  jnz     short loc_180135768
0x1801356ee  call    cs:__imp_GetLastError
0x1801356f5  nop     dword ptr [rax+rax+00h]
0x1801356fa  mov     edi, eax
0x1801356fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180135703  test    rcx, rcx
0x180135706  jz      short loc_18013575A
0x180135708  lea     r9, aFailedToGetPro_6; "Failed to get proc address for GetState"...
0x18013570f  mov     ebx, 3
0x180135714  mov     r8d, ebx
0x180135717  xor     edx, edx
0x180135719  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013571e  test    edi, edi
0x180135720  jg      short loc_180135726
0x180135722  mov     eax, edi
0x180135724  jmp     short loc_18013572E
0x180135726  movzx   eax, di
0x180135729  or      eax, 80070000h
0x18013572e  mov     [rbp+var_20], eax
0x180135731  lea     rax, [rbp+var_20]
0x180135735  mov     qword ptr [rbp+var_30], rax
0x180135739  lea     rax, [rbp+var_30]
0x18013573d  mov     qword ptr [rsp+60h+var_40], rax
0x180135742  lea     r9, a0; ": {0}"
0x180135749  mov     r8d, ebx
0x18013574c  mov     dl, 1
0x18013574e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180135755  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013575a  test    edi, edi
0x18013575c  jz      short loc_180135768
0x18013575e  mov     edx, 3Bh ; ';'
0x180135763  jmp     loc_180135511
0x180135768  mov     rcx, [rbp+lpLibFileName]
  ... truncated ...
```

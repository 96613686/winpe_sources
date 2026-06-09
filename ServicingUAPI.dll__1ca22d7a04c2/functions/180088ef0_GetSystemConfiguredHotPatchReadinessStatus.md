# GetSystemConfiguredHotPatchReadinessStatus

- ea: `0x180088ef0`
- end: `0x180089229`
- name: `GetSystemConfiguredHotPatchReadinessStatus`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18008f7b8`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001b0a4`
- `0x18001b9e4`
- `0x180022a18`
- `0x1800296a4`
- `0x18004e028`
- `0x18004e0d4`
- `0x180088ef0`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008907b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008912a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008907b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008912a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800891fb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180089066`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180089066`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180089116`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800891eb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180089116`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800891eb`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180089025`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180089025`

## string_xrefs

- `0x18008901e`: `ntdll.dll`
- `0x180089095`: `arbiter: failed to get proc address for GetSystemReadyForHotPatchStatus.`
- `0x18008903d`: `arbiter: ntdll.dll is not available, skipping populating HotPatchEligibility.`
- `0x18008917c`: `arbiter: failed to get GetSystemConfiguredHotPatchReadinessStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSystemConfiguredHotPatchReadinessStatus(_BYTE *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  int v4; // eax
  HMODULE Library; // rax
  HMODULE v6; // rsi
  FARPROC ProcAddress; // rax
  signed int LastError; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  unsigned int *v16; // [rsp+20h] [rbp-89h]
  unsigned int v17[2]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v18; // [rsp+38h] [rbp-71h]
  HMODULE v19; // [rsp+40h] [rbp-69h]
  __int64 v20; // [rsp+48h] [rbp-61h]
  int v21; // [rsp+50h] [rbp-59h] BYREF
  int v22; // [rsp+54h] [rbp-55h] BYREF
  __int64 v23; // [rsp+58h] [rbp-51h] BYREF
  char v24; // [rsp+60h] [rbp-49h]
  int v25; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v26[92]; // [rsp+74h] [rbp-35h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v20 = -2;
  v19 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(&v25, 0, 0x60u);
  v22 = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v21 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No return result specified");
      *(_QWORD *)v17 = &v21;
      v16 = v17;
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v3,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8DF,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)0x80004003LL,
      (int)v16);
    goto LABEL_9;
  }
  *a1 = 0;
  *(_QWORD *)v17 = L"\n";
  v18 = 1;
  v4 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v23, v17);
  if ( v4 < 0 )
  {
    v2 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x8E5,
           (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
           (const char *)(unsigned int)v4,
           (int)v16);
LABEL_9:
    RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v23);
    return v2;
  }
  memset_0(v26, 0, sizeof(v26));
  v25 = 2;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v6 = Library;
  v19 = Library;
  if ( !Library )
  {
    LogAdapter::TraceInfo<>("arbiter: ntdll.dll is not available, skipping populating HotPatchEligibility.");
    v2 = 0;
    goto LABEL_9;
  }
  ProcAddress = GetProcAddress(Library, "NtManageHotPatch");
  if ( ProcAddress )
  {
    v13 = ((__int64 (__fastcall *)(__int64, int *, __int64, int *))ProcAddress)(2, &v25, 96, &v22);
    v14 = v13;
    switch ( v13 )
    {
      case -1073741789:
        goto LABEL_29;
      case -1073741637:
        *a1 = 0;
        goto LABEL_30;
      case 0:
LABEL_29:
        *a1 = 1;
        goto LABEL_30;
    }
    if ( v13 < 0 )
    {
      v21 = v13;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "arbiter: failed to get GetSystemConfiguredHotPatchReadinessStatus");
        *(_QWORD *)v17 = &v21;
        v16 = v17;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v15,
          3,
          ": {}");
      }
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x909,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
              (const char *)v14,
              (int)v16);
      goto LABEL_19;
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
        "arbiter: failed to get proc address for GetSystemReadyForHotPatchStatus.");
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      else
        v11 = LastError;
      v21 = v11;
      *(_QWORD *)v17 = &v21;
      v16 = v17;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x8FA,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
              (const char *)(unsigned int)LastError,
              (unsigned int)v16);
LABEL_19:
      v2 = v12;
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v23);
      if ( !FreeLibrary(v6) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return v2;
    }
  }
LABEL_30:
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v23);
  if ( !FreeLibrary(v6) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x180088ef0  push    rbp
0x180088ef2  push    rbx
0x180088ef3  push    rsi
0x180088ef4  push    rdi
0x180088ef5  lea     rbp, [rsp-3Fh]
0x180088efa  sub     rsp, 0E8h
0x180088f01  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180088f09  mov     rax, cs:__security_cookie
0x180088f10  xor     rax, rsp
0x180088f13  mov     [rbp+57h+var_30], rax
0x180088f17  mov     rdi, rcx
0x180088f1a  mov     [rbp+57h+var_C0], 0
0x180088f22  mov     [rbp+57h+var_A8], 0
0x180088f2a  mov     [rbp+57h+var_A0], 0
0x180088f2e  mov     ebx, 60h ; '`'
0x180088f33  mov     r8d, ebx; Size
0x180088f36  xor     edx, edx; Val
0x180088f38  lea     rcx, [rbp+57h+var_90]; void *
0x180088f3c  call    memset_0
0x180088f41  mov     [rbp+57h+var_AC], 0
0x180088f48  test    rdi, rdi
0x180088f4b  jnz     short loc_180088FBD
0x180088f4d  mov     ebx, 80004003h
0x180088f52  mov     [rbp+57h+var_B0], ebx
0x180088f55  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180088f5c  test    rcx, rcx
0x180088f5f  jz      short loc_180088FA0
0x180088f61  lea     r9, aNoReturnResult; "No return result specified"
0x180088f68  mov     edi, 3
0x180088f6d  mov     r8d, edi
0x180088f70  xor     edx, edx
0x180088f72  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180088f77  lea     rax, [rbp+57h+var_B0]
0x180088f7b  mov     qword ptr [rbp+57h+var_D0], rax
0x180088f7f  lea     rax, [rbp+57h+var_D0]
0x180088f83  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180088f88  lea     r9, asc_1801CAFB4; ": {}"
0x180088f8f  mov     r8d, edi
0x180088f92  mov     dl, 1
0x180088f94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180088f9b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180088fa0  mov     rcx, [rbp+5Fh]; this
0x180088fa4  mov     r9d, ebx; char *
0x180088fa7  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x180088fae  mov     edx, 8DFh; void *
0x180088fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088fb8  jmp     loc_18008904B
0x180088fbd  mov     byte ptr [rdi], 0
0x180088fc0  lea     rax, ?Privs@LoadDriverPrivilegeAcquisition@RtlSystemUtil@@0QBJB; "\n"
0x180088fc7  mov     qword ptr [rbp+57h+var_D0], rax
0x180088fcb  mov     [rbp+57h+var_C8], 1
0x180088fd3  lea     rdx, [rbp+57h+var_D0]
0x180088fd7  lea     rcx, [rbp+57h+var_A8]
0x180088fdb  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x180088fe0  test    eax, eax
0x180088fe2  jns     short loc_180089000
0x180088fe4  mov     rcx, [rbp+5Fh]; this
0x180088fe8  mov     r9d, eax; char *
0x180088feb  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x180088ff2  mov     edx, 8E5h; void *
0x180088ff7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180088ffc  mov     ebx, eax
0x180088ffe  jmp     short loc_18008904B
0x180089000  xor     edx, edx; Val
0x180089002  lea     r8d, [rdx+5Ch]; Size
0x180089006  lea     rcx, [rbp+57h+var_8C]; void *
0x18008900a  call    memset_0
0x18008900f  mov     [rbp+57h+var_90], 2
0x180089016  xor     edx, edx; hFile
0x180089018  mov     r8d, 800h; dwFlags
0x18008901e  lea     rcx, ModuleName; "ntdll.dll"
0x180089025  call    cs:__imp_LoadLibraryExW
0x18008902c  nop     dword ptr [rax+rax+00h]
0x180089031  mov     rsi, rax
0x180089034  mov     [rbp+57h+var_C0], rax
0x180089038  test    rax, rax
0x18008903b  jnz     short loc_18008905C
0x18008903d  lea     rcx, aArbiterNtdllDl; "arbiter: ntdll.dll is not available, sk"...
0x180089044  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180089049  xor     ebx, ebx
0x18008904b  lea     rcx, [rbp+57h+var_A8]; this
0x18008904f  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180089054  nop
0x180089055  mov     eax, ebx
0x180089057  jmp     loc_180089210
0x18008905c  lea     rdx, aNtmanagehotpat; "NtManageHotPatch"
0x180089063  mov     rcx, rsi; hModule
0x180089066  call    cs:__imp_GetProcAddress
0x18008906d  nop     dword ptr [rax+rax+00h]
0x180089072  test    rax, rax
0x180089075  jnz     loc_180089142
0x18008907b  call    cs:__imp_GetLastError
0x180089082  nop     dword ptr [rax+rax+00h]
0x180089087  mov     ebx, eax
0x180089089  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180089090  test    rcx, rcx
0x180089093  jz      short loc_1800890E7
0x180089095  lea     r9, aArbiterFailedT_22; "arbiter: failed to get proc address for"...
0x18008909c  mov     edi, 3
0x1800890a1  mov     r8d, edi
0x1800890a4  xor     edx, edx
0x1800890a6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800890ab  test    ebx, ebx
0x1800890ad  jg      short loc_1800890B3
0x1800890af  mov     eax, ebx
0x1800890b1  jmp     short loc_1800890BB
0x1800890b3  movzx   eax, bx
0x1800890b6  or      eax, 80070000h
0x1800890bb  mov     [rbp+57h+var_B0], eax
0x1800890be  lea     rax, [rbp+57h+var_B0]
0x1800890c2  mov     qword ptr [rbp+57h+var_D0], rax
0x1800890c6  lea     rax, [rbp+57h+var_D0]
0x1800890ca  mov     qword ptr [rsp+100h+var_E0], rax; unsigned int
0x1800890cf  lea     r9, a0; ": {0}"
0x1800890d6  mov     r8d, edi
0x1800890d9  mov     dl, 1
0x1800890db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800890e2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800890e7  test    ebx, ebx
0x1800890e9  jz      loc_1800891DE
0x1800890ef  mov     rcx, [rbp+5Fh]; this
0x1800890f3  mov     r9d, ebx; char *
0x1800890f6  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800890fd  mov     edx, 8FAh; void *
0x180089102  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180089107  mov     ebx, eax
0x180089109  lea     rcx, [rbp+57h+var_A8]; this
0x18008910d  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180089112  nop
0x180089113  mov     rcx, rsi; hLibModule
0x180089116  call    cs:__imp_FreeLibrary
0x18008911d  nop     dword ptr [rax+rax+00h]
0x180089122  test    eax, eax
0x180089124  jnz     loc_180089055
0x18008912a  call    cs:__imp_GetLastError
0x180089131  nop     dword ptr [rax+rax+00h]
0x180089136  mov     ecx, 7
0x18008913b  int     29h; Win8: RtlFailFast(ecx)
0x18008913d  jmp     loc_180089055
0x180089142  lea     r9, [rbp+57h+var_AC]
0x180089146  mov     r8d, ebx
0x180089149  lea     rdx, [rbp+57h+var_90]
0x18008914d  mov     ecx, 2
0x180089152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089157  mov     ebx, eax
0x180089159  cmp     eax, 0C0000023h
0x18008915e  jz      short loc_1800891DB
0x180089160  cmp     eax, 0C00000BBh
0x180089165  jz      short loc_1800891D6
0x180089167  test    eax, eax
0x180089169  jz      short loc_1800891DB
0x18008916b  jns     short loc_1800891DE
0x18008916d  mov     [rbp+57h+var_B0], eax
0x180089170  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180089177  test    rcx, rcx
0x18008917a  jz      short loc_1800891B9
0x18008917c  lea     r9, aArbiterFailedT_7; "arbiter: failed to get GetSystemConfigu"...
0x180089183  mov     edi, 3
0x180089188  mov     r8d, edi
0x18008918b  xor     edx, edx
0x18008918d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180089192  lea     rax, [rbp+57h+var_B0]
0x180089196  mov     qword ptr [rbp+57h+var_D0], rax
0x18008919a  lea     rax, [rbp+57h+var_D0]
0x18008919e  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800891a3  lea     r9, asc_1801CAFB4; ": {}"
0x1800891aa  mov     r8d, edi
0x1800891ad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800891b4  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1800891b9  mov     rcx, [rbp+5Fh]; this
0x1800891bd  mov     r9d, ebx; char *
0x1800891c0  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800891c7  mov     edx, 909h; void *
0x1800891cc  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800891d1  jmp     loc_180089107
0x1800891d6  mov     byte ptr [rdi], 0
0x1800891d9  jmp     short loc_1800891DE
0x1800891db  mov     byte ptr [rdi], 1
0x1800891de  lea     rcx, [rbp+57h+var_A8]; this
0x1800891e2  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x1800891e7  nop
0x1800891e8  mov     rcx, rsi; hLibModule
0x1800891eb  call    cs:__imp_FreeLibrary
0x1800891f2  nop     dword ptr [rax+rax+00h]
0x1800891f7  test    eax, eax
0x1800891f9  jnz     short loc_18008920E
0x1800891fb  call    cs:__imp_GetLastError
0x180089202  nop     dword ptr [rax+rax+00h]
0x180089207  mov     ecx, 7
0x18008920c  int     29h; Win8: RtlFailFast(ecx)
0x18008920e  xor     eax, eax
0x180089210  mov     rcx, [rbp+57h+var_30]
0x180089214  xor     rcx, rsp; StackCookie
0x180089217  call    __security_check_cookie
0x18008921c  add     rsp, 0E8h
0x180089223  pop     rdi
0x180089224  pop     rsi
0x180089225  pop     rbx
0x180089226  pop     rbp
0x180089227  retn
```

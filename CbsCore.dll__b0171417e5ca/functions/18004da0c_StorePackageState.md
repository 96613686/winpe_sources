# StorePackageState

- ea: `0x18004da0c`
- end: `0x18004dd11`
- name: `StorePackageState`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180027790`
- `0x1800b5534`

## callees

- `0x180010f54`
- `0x1800110d0`
- `0x18004da0c`
- `0x18004dd18`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x18009d010`
- `0x1800a8678`
- `0x1800ae508`
- `0x1800b5f90`
- `0x1800b693c`
- `0x1800b6a6c`
- `0x1800bd3dc`
- `0x1800eb500`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004dbe1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004dbe1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004dcbf`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004dcbf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004dc7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004dc7f`

## string_xrefs

- `0x18004dc93`: `InstallUser`
- `0x18004dbf1`: `InstallTimeHigh`
- `0x18004dc1d`: `InstallTimeLow`
- `0x18004db6c`: `Failed to write current state for package: {}`
- `0x18004dab1`: `Failed to remove from store package: {}`
- `0x18004dc30`: `Unable to set Install Time Low.`
- `0x18004dca6`: `Unable to set Install User.`
- `0x18004dc09`: `Unable to set Install Time High.`
- `0x18004dccd`: `Unable to get User SID from user token.`

## pseudocode

```c
__int64 __fastcall StorePackageState(
        HANDLE TokenHandle,
        __int64 a2,
        __int64 a3,
        CCbsStoreObject *a4,
        wchar_t *a5,
        int a6,
        int a7)
{
  signed int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  int v16; // eax
  int UserSidFromToken; // eax
  PSID v18; // rdi
  const struct std::nothrow_t *v19; // rdx
  int v20; // eax
  int v22; // [rsp+20h] [rbp-58h]
  PSID *p_Sid; // [rsp+20h] [rbp-58h]
  _QWORD v24[2]; // [rsp+30h] [rbp-48h] BYREF
  char v25; // [rsp+40h] [rbp-38h]
  wchar_t *v26; // [rsp+48h] [rbp-30h] BYREF
  PSID Sid; // [rsp+50h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v26 = a5;
  v25 = 0;
  v24[1] = &vPackageStoreLock;
  v24[0] = &PackageTrackerLocker::`vftable';
  MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v24);
  if ( !a6 && a7 )
  {
    v11 = UnstorePackage(a2, a3, a4, v26);
    v12 = v11;
    if ( v11 < 0 )
    {
      SystemTimeAsFileTime.dwLowDateTime = v11;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to remove from store package: {}",
          (__int64)&v26);
        Sid = &SystemTimeAsFileTime;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&Sid);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEBF,
        (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
        (const char *)v12,
        v22);
      goto LABEL_28;
    }
LABEL_27:
    v12 = 0;
    goto LABEL_28;
  }
  SystemTimeAsFileTime.dwLowDateTime = 0;
  p_Sid = &Sid;
  LODWORD(Sid) = 0;
  CCbsStoreObject::GetValue(a4, 1, L"CurrentState", &SystemTimeAsFileTime);
  v13 = CCbsStoreObject::SetValue(a4, L"CurrentState", a6);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( (int)SystemTimeAsFileTime.dwLowDateTime < 112 && a6 >= 96 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v15 = CCbsStoreObject::SetValue(a4, L"InstallTimeHigh", SystemTimeAsFileTime.dwHighDateTime);
      if ( v15 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v15, "Unable to set Install Time High.");
      v16 = CCbsStoreObject::SetValue(a4, L"InstallTimeLow", SystemTimeAsFileTime.dwLowDateTime);
      if ( v16 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v16, "Unable to set Install Time Low.");
      if ( TokenHandle )
      {
        Sid = 0;
        UserSidFromToken = GetUserSidFromToken(TokenHandle, &Sid);
        v18 = Sid;
        if ( UserSidFromToken < 0 )
        {
          LogAdapter::TraceAtLevelIfFailed<long,>(
            2,
            (unsigned int)UserSidFromToken,
            "Unable to get User SID from user token.");
        }
        else
        {
          Sid = 0;
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
            &Sid,
            0);
          if ( ConvertSidToStringSidW(v18, (LPWSTR *)&Sid) )
          {
            v20 = CCbsStoreObject::SetValue(a4, L"InstallUser", (const wchar_t *)Sid);
            if ( v20 < 0 )
              LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v20, "Unable to set Install User.");
          }
          if ( Sid )
            LocalFree(Sid);
        }
        if ( v18 )
          operator delete(v18, v19);
      }
    }
    goto LABEL_27;
  }
  LODWORD(Sid) = v13;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"Failed to write current state for package: {}",
      (__int64)&v26);
    SystemTimeAsFileTime = (struct _FILETIME)&Sid;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&SystemTimeAsFileTime);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xECA,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)v14,
    (int)p_Sid);
  v12 = v14;
LABEL_28:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v24);
  return v12;
}

```

## disassembly

```asm
0x18004da0c  push    rbp
0x18004da0e  push    rbx
0x18004da0f  push    rsi
0x18004da10  push    rdi
0x18004da11  push    r14
0x18004da13  push    r15
0x18004da15  mov     rbp, rsp
0x18004da18  sub     rsp, 78h
0x18004da1c  mov     rax, cs:__security_cookie
0x18004da23  xor     rax, rsp
0x18004da26  mov     [rbp+var_18], rax
0x18004da2a  mov     rax, [rbp+arg_20]
0x18004da2e  mov     r14, rcx
0x18004da31  mov     [rbp+var_30], rax
0x18004da35  lea     rcx, [rbp+var_48]; this
0x18004da39  lea     rax, ?vPackageStoreLock@@3UMonitoredCritSec@@A; MonitoredCritSec vPackageStoreLock
0x18004da40  mov     [rbp+var_38], 0
0x18004da44  mov     [rbp+var_40], rax
0x18004da48  mov     rbx, r9
0x18004da4b  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x18004da52  mov     r15, r8
0x18004da55  mov     [rbp+var_48], rax
0x18004da59  mov     rdi, rdx
0x18004da5c  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x18004da61  mov     esi, [rbp+arg_28]
0x18004da64  test    esi, esi
0x18004da66  jnz     loc_18004DB05
0x18004da6c  cmp     [rbp+arg_30], esi
0x18004da6f  jz      loc_18004DB05
0x18004da75  mov     r9, [rbp+var_30]
0x18004da79  mov     r8, rbx
0x18004da7c  mov     rdx, r15
0x18004da7f  mov     rcx, rdi
0x18004da82  call    UnstorePackage
0x18004da87  mov     ebx, eax
0x18004da89  test    eax, eax
0x18004da8b  jns     loc_18004DCEA
0x18004da91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004da98  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], eax
0x18004da9b  test    rcx, rcx
0x18004da9e  jz      short loc_18004DAE8
0x18004daa0  lea     rax, [rbp+var_30]
0x18004daa4  mov     esi, 3
0x18004daa9  mov     r8d, esi
0x18004daac  mov     qword ptr [rsp+78h+var_58], rax
0x18004dab1  lea     r9, aFailedToRemove_1; "Failed to remove from store package: {}"
0x18004dab8  xor     edx, edx
0x18004daba  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004dabf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dac6  lea     rax, [rbp+SystemTimeAsFileTime]
0x18004daca  mov     [rbp+Sid], rax
0x18004dace  lea     r9, asc_1802EE7AC; ": {}"
0x18004dad5  lea     rax, [rbp+Sid]
0x18004dad9  mov     r8d, esi
0x18004dadc  mov     dl, 1
0x18004dade  mov     qword ptr [rsp+78h+var_58], rax; int
0x18004dae3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004dae8  mov     rcx, [rbp+30h]; this
0x18004daec  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18004daf3  mov     r9d, ebx; char *
0x18004daf6  mov     edx, 0EBFh; void *
0x18004dafb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004db00  jmp     loc_18004DCEC
0x18004db05  lea     rax, [rbp+Sid]
0x18004db09  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004db10  lea     r9, [rbp+SystemTimeAsFileTime]
0x18004db14  mov     qword ptr [rsp+78h+var_58], rax
0x18004db19  lea     r8, aCurrentstate; "CurrentState"
0x18004db20  mov     dword ptr [rbp+Sid], 0
0x18004db27  mov     edx, 1
0x18004db2c  mov     rcx, rbx
0x18004db2f  call    ?GetValue@CCbsStoreObject@@QEAAJW4GetValueFlags@1@QEB_WPEAKPEAW4GetValueDisposition@1@@Z; CCbsStoreObject::GetValue(CCbsStoreObject::GetValueFlags,wchar_t const * const,ulong *,CCbsStoreObject::GetValueDisposition *)
0x18004db34  mov     r8d, esi; unsigned int
0x18004db37  lea     rdx, aCurrentstate; "CurrentState"
0x18004db3e  mov     rcx, rbx; this
0x18004db41  call    ?SetValue@CCbsStoreObject@@QEAAJPEB_WK@Z; CCbsStoreObject::SetValue(wchar_t const *,ulong)
0x18004db46  mov     edi, eax
0x18004db48  test    eax, eax
0x18004db4a  jns     short loc_18004DBC2
0x18004db4c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004db53  mov     dword ptr [rbp+Sid], eax
0x18004db56  test    rcx, rcx
0x18004db59  jz      short loc_18004DBA3
0x18004db5b  lea     rax, [rbp+var_30]
0x18004db5f  mov     esi, 3
0x18004db64  mov     r8d, esi
0x18004db67  mov     qword ptr [rsp+78h+var_58], rax
0x18004db6c  lea     r9, aFailedToWriteC; "Failed to write current state for packa"...
0x18004db73  xor     edx, edx
0x18004db75  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004db7a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004db81  lea     rax, [rbp+Sid]
0x18004db85  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004db89  lea     r9, asc_1802EE7AC; ": {}"
0x18004db90  lea     rax, [rbp+SystemTimeAsFileTime]
0x18004db94  mov     r8d, esi
0x18004db97  mov     dl, 1
0x18004db99  mov     qword ptr [rsp+78h+var_58], rax; int
0x18004db9e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004dba3  mov     rcx, [rbp+30h]; this
0x18004dba7  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x18004dbae  mov     r9d, edi; char *
0x18004dbb1  mov     edx, 0ECAh; void *
0x18004dbb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dbbb  mov     ebx, edi
0x18004dbbd  jmp     loc_18004DCEC
0x18004dbc2  cmp     [rbp+SystemTimeAsFileTime.dwLowDateTime], 70h ; 'p'
0x18004dbc6  jge     loc_18004DCEA
0x18004dbcc  cmp     esi, 60h ; '`'
0x18004dbcf  jl      loc_18004DCEA
0x18004dbd5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004dbd9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004dbe1  call    cs:__imp_GetSystemTimeAsFileTime
0x18004dbe8  nop     dword ptr [rax+rax+00h]
0x18004dbed  mov     r8d, [rbp+SystemTimeAsFileTime.dwHighDateTime]; unsigned int
0x18004dbf1  lea     rdx, aInstalltimehig; "InstallTimeHigh"
0x18004dbf8  mov     rcx, rbx; this
0x18004dbfb  call    ?SetValue@CCbsStoreObject@@QEAAJPEB_WK@Z; CCbsStoreObject::SetValue(wchar_t const *,ulong)
0x18004dc00  mov     esi, 2
0x18004dc05  test    eax, eax
0x18004dc07  jns     short loc_18004DC19
0x18004dc09  lea     r8, aUnableToSetIns_1; "Unable to set Install Time High."
0x18004dc10  mov     edx, eax
0x18004dc12  mov     ecx, esi
0x18004dc14  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18004dc19  mov     r8d, [rbp+SystemTimeAsFileTime.dwLowDateTime]; unsigned int
0x18004dc1d  lea     rdx, aInstalltimelow; "InstallTimeLow"
0x18004dc24  mov     rcx, rbx; this
0x18004dc27  call    ?SetValue@CCbsStoreObject@@QEAAJPEB_WK@Z; CCbsStoreObject::SetValue(wchar_t const *,ulong)
0x18004dc2c  test    eax, eax
0x18004dc2e  jns     short loc_18004DC40
0x18004dc30  lea     r8, aUnableToSetIns; "Unable to set Install Time Low."
0x18004dc37  mov     edx, eax
0x18004dc39  mov     ecx, esi
0x18004dc3b  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18004dc40  test    r14, r14
0x18004dc43  jz      loc_18004DCEA
0x18004dc49  lea     rdx, [rbp+Sid]
0x18004dc4d  mov     [rbp+Sid], 0
0x18004dc55  mov     rcx, r14; TokenHandle
0x18004dc58  call    GetUserSidFromToken
0x18004dc5d  mov     rdi, [rbp+Sid]
0x18004dc61  test    eax, eax
0x18004dc63  js      short loc_18004DCCD
0x18004dc65  xor     edx, edx
0x18004dc67  mov     [rbp+Sid], 0
0x18004dc6f  lea     rcx, [rbp+Sid]
0x18004dc73  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18004dc78  lea     rdx, [rbp+Sid]; StringSid
0x18004dc7c  mov     rcx, rdi; Sid
0x18004dc7f  call    cs:__imp_ConvertSidToStringSidW
0x18004dc86  nop     dword ptr [rax+rax+00h]
0x18004dc8b  test    eax, eax
0x18004dc8d  jz      short loc_18004DCB6
0x18004dc8f  mov     r8, [rbp+Sid]; wchar_t *
0x18004dc93  lea     rdx, aInstalluser; "InstallUser"
0x18004dc9a  mov     rcx, rbx; this
0x18004dc9d  call    ?SetValue@CCbsStoreObject@@QEAAJPEB_W0@Z; CCbsStoreObject::SetValue(wchar_t const *,wchar_t const *)
0x18004dca2  test    eax, eax
0x18004dca4  jns     short loc_18004DCB6
0x18004dca6  lea     r8, aUnableToSetIns_0; "Unable to set Install User."
0x18004dcad  mov     edx, eax
0x18004dcaf  mov     ecx, esi
0x18004dcb1  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18004dcb6  mov     rcx, [rbp+Sid]; hMem
0x18004dcba  test    rcx, rcx
0x18004dcbd  jz      short loc_18004DCDD
0x18004dcbf  call    cs:__imp_LocalFree
0x18004dcc6  nop     dword ptr [rax+rax+00h]
0x18004dccb  jmp     short loc_18004DCDD
0x18004dccd  lea     r8, aUnableToGetUse; "Unable to get User SID from user token."
0x18004dcd4  mov     edx, eax
0x18004dcd6  mov     ecx, esi
0x18004dcd8  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18004dcdd  test    rdi, rdi
0x18004dce0  jz      short loc_18004DCEA
0x18004dce2  mov     rcx, rdi; void *
0x18004dce5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004dcea  xor     ebx, ebx
0x18004dcec  lea     rcx, [rbp+var_48]; this
0x18004dcf0  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x18004dcf5  mov     eax, ebx
0x18004dcf7  mov     rcx, [rbp+var_18]
0x18004dcfb  xor     rcx, rsp; StackCookie
0x18004dcfe  call    __security_check_cookie
0x18004dd03  add     rsp, 78h
0x18004dd07  pop     r15
0x18004dd09  pop     r14
0x18004dd0b  pop     rdi
0x18004dd0c  pop     rsi
0x18004dd0d  pop     rbx
0x18004dd0e  pop     rbp
0x18004dd0f  retn
```

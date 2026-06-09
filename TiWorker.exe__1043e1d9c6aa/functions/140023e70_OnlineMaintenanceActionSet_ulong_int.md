# OnlineMaintenanceActionSet(ulong,int)

- ea: `0x140023e70`
- end: `0x140023fc4`
- name: `?OnlineMaintenanceActionSet@@YAJKH@Z`
- size: `340`
- prototype: `__int64 __fastcall(HKEY, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f5b0`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14001121c`
- `0x140011a30`
- `0x140023e70`

## string_xrefs

- `0x140023e9e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x140023f44`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 __fastcall OnlineMaintenanceActionSet(HKEY a1, __int64 a2, __int64 a3)
{
  HKEY v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdx
  signed int v9; // eax
  __int64 v10; // rdx
  int v11; // [rsp+20h] [rbp-38h]
  int v12[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v13 = 0;
  v4 = CbsRegQueryDWORDValue(
         a1,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
         a3,
         L"MaintenanceFlags",
         &v13);
  if ( v4 == -2147024894 )
  {
    v5 = 0;
  }
  else
  {
    if ( (v4 & 0x80000000) != 0 )
    {
      v13 = v4;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting maintenance flags.");
        *(_QWORD *)v12 = &v13;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v6,
          3,
          (__int64)": {}",
          (__int64)v12);
      }
      v7 = 94;
      goto LABEL_7;
    }
    v5 = v13;
  }
  v9 = CbsRegSetDWORDValue(
         v3,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
         1,
         (wchar_t *)L"MaintenanceFlags",
         v5 & 0x7FFEFFFF);
  v4 = v9;
  if ( v9 < 0 )
  {
    v13 = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed updating maintenance flags.");
      *(_QWORD *)v12 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v12);
    }
    v7 = 107;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsmaintenanceactions.cpp",
      (const char *)v4,
      v11);
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x140023e70  push    rbx
0x140023e72  sub     rsp, 50h
0x140023e76  mov     rax, cs:__security_cookie
0x140023e7d  xor     rax, rsp
0x140023e80  mov     [rsp+58h+var_18], rax
0x140023e85  lea     rax, [rsp+58h+var_20]
0x140023e8a  mov     [rsp+58h+var_20], 0
0x140023e92  lea     r9, aMaintenancefla; "MaintenanceFlags"
0x140023e99  mov     qword ptr [rsp+58h+var_38], rax; unsigned int *
0x140023e9e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140023ea5  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x140023eaa  mov     ebx, eax
0x140023eac  cmp     eax, 80070002h
0x140023eb1  jnz     short loc_140023EB7
0x140023eb3  xor     eax, eax
0x140023eb5  jmp     short loc_140023F2E
0x140023eb7  test    ebx, ebx
0x140023eb9  jns     short loc_140023F2A
0x140023ebb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023ec2  mov     [rsp+58h+var_20], ebx
0x140023ec6  test    rcx, rcx
0x140023ec9  jz      short loc_140023F0A
0x140023ecb  xor     edx, edx
0x140023ecd  lea     r9, aFailedGettingM; "Failed getting maintenance flags."
0x140023ed4  lea     r8d, [rdx+3]
0x140023ed8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023edd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023ee4  lea     rax, [rsp+58h+var_20]
0x140023ee9  mov     qword ptr [rsp+58h+var_28], rax
0x140023eee  lea     r9, asc_140030534; ": {}"
0x140023ef5  lea     rax, [rsp+58h+var_28]
0x140023efa  mov     r8d, 3
0x140023f00  mov     qword ptr [rsp+58h+var_38], rax; int
0x140023f05  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023f0a  mov     edx, 5Eh ; '^'; void *
0x140023f0f  mov     rcx, [rsp+58h]; this
0x140023f14  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x140023f1b  mov     r9d, ebx; char *
0x140023f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023f23  mov     eax, ebx
0x140023f25  jmp     loc_140023FB1
0x140023f2a  mov     eax, [rsp+58h+var_20]
0x140023f2e  and     eax, 7FFEFFFFh
0x140023f33  lea     r9, aMaintenancefla; "MaintenanceFlags"
0x140023f3a  mov     r8d, 1; unsigned int
0x140023f40  mov     [rsp+58h+var_38], eax; unsigned int
0x140023f44  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140023f4b  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x140023f50  mov     ebx, eax
0x140023f52  test    eax, eax
0x140023f54  jns     short loc_140023FAF
0x140023f56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023f5d  mov     [rsp+58h+var_20], eax
0x140023f61  test    rcx, rcx
0x140023f64  jz      short loc_140023FA5
0x140023f66  xor     edx, edx
0x140023f68  lea     r9, aFailedUpdating; "Failed updating maintenance flags."
0x140023f6f  lea     r8d, [rdx+3]
0x140023f73  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023f78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023f7f  lea     rax, [rsp+58h+var_20]
0x140023f84  mov     qword ptr [rsp+58h+var_28], rax
0x140023f89  lea     r9, asc_140030534; ": {}"
0x140023f90  lea     rax, [rsp+58h+var_28]
0x140023f95  mov     r8d, 3
0x140023f9b  mov     qword ptr [rsp+58h+var_38], rax
0x140023fa0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023fa5  mov     edx, 6Bh ; 'k'
0x140023faa  jmp     loc_140023F0F
0x140023faf  xor     eax, eax
0x140023fb1  mov     rcx, [rsp+58h+var_18]
0x140023fb6  xor     rcx, rsp; StackCookie
0x140023fb9  call    __security_check_cookie
0x140023fbe  add     rsp, 50h
0x140023fc2  pop     rbx
0x140023fc3  retn
```

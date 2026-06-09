# OnlineMaintenanceActionSet(ulong,int)

- ea: `0x14002126c`
- end: `0x1400213c6`
- name: `?OnlineMaintenanceActionSet@@YAJKH@Z`
- size: `346`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018630`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001a16c`
- `0x14001acbc`
- `0x14002126c`

## string_xrefs

- `0x1400212a0`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`
- `0x140021346`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 __fastcall OnlineMaintenanceActionSet(HKEY a1)
{
  HKEY v1; // rcx
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rdx
  signed int v7; // eax
  __int64 v8; // rdx
  int v9; // [rsp+20h] [rbp-38h]
  int v10[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v11 = 0;
  v2 = CbsRegQueryDWORDValue(
         a1,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
         1,
         L"MaintenanceFlags",
         &v11);
  if ( v2 == -2147024894 )
  {
    v3 = 0;
  }
  else
  {
    if ( (v2 & 0x80000000) != 0 )
    {
      v11 = v2;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting maintenance flags.");
        *(_QWORD *)v10 = &v11;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v4,
          3,
          (__int64)": {}",
          (__int64)v10);
      }
      v5 = 94;
      goto LABEL_7;
    }
    v3 = v11;
  }
  v7 = CbsRegSetDWORDValue(
         v1,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
         1,
         L"MaintenanceFlags",
         v3 & 0x7FFEFFFF);
  v2 = v7;
  if ( v7 < 0 )
  {
    v11 = v7;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed updating maintenance flags.");
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v10);
    }
    v5 = 107;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsmaintenanceactions.cpp",
      (const char *)v2,
      v9);
    return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x14002126c  push    rbx
0x14002126e  sub     rsp, 50h
0x140021272  mov     rax, cs:__security_cookie
0x140021279  xor     rax, rsp
0x14002127c  mov     [rsp+58h+var_18], rax
0x140021281  lea     rax, [rsp+58h+var_20]
0x140021286  mov     [rsp+58h+var_20], 0
0x14002128e  lea     r9, aMaintenancefla; "MaintenanceFlags"
0x140021295  mov     qword ptr [rsp+58h+var_38], rax; unsigned int *
0x14002129a  mov     r8d, 1; unsigned int
0x1400212a0  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400212a7  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1400212ac  mov     ebx, eax
0x1400212ae  cmp     eax, 80070002h
0x1400212b3  jnz     short loc_1400212B9
0x1400212b5  xor     eax, eax
0x1400212b7  jmp     short loc_140021330
0x1400212b9  test    ebx, ebx
0x1400212bb  jns     short loc_14002132C
0x1400212bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400212c4  mov     [rsp+58h+var_20], ebx
0x1400212c8  test    rcx, rcx
0x1400212cb  jz      short loc_14002130C
0x1400212cd  xor     edx, edx
0x1400212cf  lea     r9, aFailedGettingM; "Failed getting maintenance flags."
0x1400212d6  lea     r8d, [rdx+3]
0x1400212da  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400212df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400212e6  lea     rax, [rsp+58h+var_20]
0x1400212eb  mov     qword ptr [rsp+58h+var_28], rax
0x1400212f0  lea     r9, asc_1400353E8; ": {}"
0x1400212f7  lea     rax, [rsp+58h+var_28]
0x1400212fc  mov     r8d, 3
0x140021302  mov     qword ptr [rsp+58h+var_38], rax; int
0x140021307  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002130c  mov     edx, 5Eh ; '^'; void *
0x140021311  mov     rcx, [rsp+58h]; this
0x140021316  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x14002131d  mov     r9d, ebx; char *
0x140021320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021325  mov     eax, ebx
0x140021327  jmp     loc_1400213B3
0x14002132c  mov     eax, [rsp+58h+var_20]
0x140021330  and     eax, 7FFEFFFFh
0x140021335  lea     r9, aMaintenancefla; "MaintenanceFlags"
0x14002133c  mov     r8d, 1; unsigned int
0x140021342  mov     [rsp+58h+var_38], eax; unsigned int
0x140021346  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14002134d  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x140021352  mov     ebx, eax
0x140021354  test    eax, eax
0x140021356  jns     short loc_1400213B1
0x140021358  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002135f  mov     [rsp+58h+var_20], eax
0x140021363  test    rcx, rcx
0x140021366  jz      short loc_1400213A7
0x140021368  xor     edx, edx
0x14002136a  lea     r9, aFailedUpdating; "Failed updating maintenance flags."
0x140021371  lea     r8d, [rdx+3]
0x140021375  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002137a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021381  lea     rax, [rsp+58h+var_20]
0x140021386  mov     qword ptr [rsp+58h+var_28], rax
0x14002138b  lea     r9, asc_1400353E8; ": {}"
0x140021392  lea     rax, [rsp+58h+var_28]
0x140021397  mov     r8d, 3
0x14002139d  mov     qword ptr [rsp+58h+var_38], rax
0x1400213a2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400213a7  mov     edx, 6Bh ; 'k'
0x1400213ac  jmp     loc_140021311
0x1400213b1  xor     eax, eax
0x1400213b3  mov     rcx, [rsp+58h+var_18]
0x1400213b8  xor     rcx, rsp; StackCookie
0x1400213bb  call    __security_check_cookie
0x1400213c0  add     rsp, 50h
0x1400213c4  pop     rbx
0x1400213c5  retn
```

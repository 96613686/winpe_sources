# OnlineMaintenanceActionGet(ulong,int *)

- ea: `0x140020ffc`
- end: `0x140021263`
- name: `?OnlineMaintenanceActionGet@@YAJKPEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(HKEY, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140012540`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001a16c`
- `0x14001a4c0`
- `0x140020ffc`

## string_xrefs

- `0x14002109a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 __fastcall OnlineMaintenanceActionGet(HKEY a1, int *a2)
{
  int DWORDValue; // ebx
  int v4; // edx
  __int64 v5; // rdx
  const wchar_t *v7; // rdx
  HKEY v8; // rcx
  unsigned int v9; // r8d
  int v10; // eax
  int v11; // edx
  int v12; // eax
  const wchar_t *v13; // rdx
  HKEY v14; // rcx
  unsigned int v15; // r8d
  int v16; // edx
  int QWORDValue; // eax
  int v18; // edx
  int v19; // [rsp+20h] [rbp-30h]
  unsigned __int64 v20; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v21[2]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( !a2 )
  {
    DWORDValue = -2147467261;
    v21[0] = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No set result specified");
      v20 = (unsigned __int64)v21;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&v20);
    }
    v5 = 27;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsmaintenanceactions.cpp",
      (const char *)(unsigned int)DWORDValue,
      v19);
    return (unsigned int)DWORDValue;
  }
  *a2 = 0;
  v21[0] = 0;
  DWORDValue = CbsRegQueryDWORDValue(
                 a1,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
                 1u,
                 L"MaintenanceFlags",
                 v21);
  if ( DWORDValue == -2147024894 )
  {
    v10 = 0;
  }
  else
  {
    if ( DWORDValue < 0 )
    {
      v21[0] = DWORDValue;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting maintenance flags.");
        v20 = (unsigned __int64)v21;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)&v20);
      }
      v5 = 39;
      goto LABEL_5;
    }
    v10 = v21[0];
  }
  if ( v10 < 0 )
  {
    v20 = 0;
    *(_QWORD *)v21 = 0;
    v12 = CbsRegQueryQWORDValue(v8, v7, v9, L"PublisherPolicyChangeTime", &v20);
    DWORDValue = v12;
    if ( v12 != -2147024894 )
    {
      if ( v12 < 0 )
      {
        v21[0] = v12;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting PublisherPolicyChangeTime.");
          v20 = (unsigned __int64)v21;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v16,
            3,
            (unsigned int)": {}",
            (__int64)&v20);
        }
        v5 = 61;
        goto LABEL_5;
      }
      QWORDValue = CbsRegQueryQWORDValue(v14, v13, v15, L"LastScavengeCookie", (unsigned __int64 *)v21);
      DWORDValue = QWORDValue;
      if ( QWORDValue != -2147024894 )
      {
        if ( QWORDValue < 0 )
        {
          v21[0] = QWORDValue;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting LastScavengeCookie.");
            v20 = (unsigned __int64)v21;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v18,
              3,
              (unsigned int)": {}",
              (__int64)&v20);
          }
          v5 = 69;
          goto LABEL_5;
        }
        if ( v20 == *(_QWORD *)v21 )
          *a2 = 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140020ffc  mov     [rsp-8+arg_0], rbx
0x140021001  mov     [rsp-8+arg_10], rdi
0x140021006  push    rbp
0x140021007  mov     rbp, rsp
0x14002100a  sub     rsp, 50h
0x14002100e  mov     rax, cs:__security_cookie
0x140021015  xor     rax, rsp
0x140021018  mov     [rbp+var_10], rax
0x14002101c  mov     rdi, rdx
0x14002101f  test    rdx, rdx
0x140021022  jnz     short loc_140021090
0x140021024  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002102b  mov     ebx, 80004003h
0x140021030  mov     [rbp+var_18], ebx
0x140021033  test    rcx, rcx
0x140021036  jz      short loc_140021071
0x140021038  lea     edi, [rdx+3]
0x14002103b  mov     r8d, edi
0x14002103e  lea     r9, aNoSetResultSpe; "No set result specified"
0x140021045  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002104a  lea     rcx, [rbp+var_20]
0x14002104e  mov     r8d, edi
0x140021051  mov     qword ptr [rsp+50h+var_30], rcx; int
0x140021056  lea     rax, [rbp+var_18]
0x14002105a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021061  lea     r9, asc_1400353E8; ": {}"
0x140021068  mov     [rbp+var_20], rax
0x14002106c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140021071  mov     edx, 1Bh; void *
0x140021076  mov     rcx, [rbp+8]; this
0x14002107a  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x140021081  mov     r9d, ebx; char *
0x140021084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021089  mov     eax, ebx
0x14002108b  jmp     loc_140021247
0x140021090  mov     dword ptr [rdx], 0
0x140021096  lea     rax, [rbp+var_18]
0x14002109a  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400210a1  mov     qword ptr [rsp+50h+var_30], rax; unsigned int *
0x1400210a6  lea     r9, aMaintenancefla; "MaintenanceFlags"
0x1400210ad  mov     [rbp+var_18], 0
0x1400210b4  mov     r8d, 1; unsigned int
0x1400210ba  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1400210bf  mov     ebx, eax
0x1400210c1  cmp     eax, 80070002h
0x1400210c6  jnz     short loc_1400210CC
0x1400210c8  xor     eax, eax
0x1400210ca  jmp     short loc_140021129
0x1400210cc  test    ebx, ebx
0x1400210ce  jns     short loc_140021126
0x1400210d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400210d7  mov     [rbp+var_18], ebx
0x1400210da  test    rcx, rcx
0x1400210dd  jz      short loc_14002111C
0x1400210df  mov     edi, 3
0x1400210e4  lea     r9, aFailedGettingM; "Failed getting maintenance flags."
0x1400210eb  mov     r8d, edi
0x1400210ee  xor     edx, edx
0x1400210f0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400210f5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400210fc  lea     rax, [rbp+var_18]
0x140021100  mov     [rbp+var_20], rax
0x140021104  lea     r9, asc_1400353E8; ": {}"
0x14002110b  lea     rax, [rbp+var_20]
0x14002110f  mov     r8d, edi
0x140021112  mov     qword ptr [rsp+50h+var_30], rax
0x140021117  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002111c  mov     edx, 27h ; '''
0x140021121  jmp     loc_140021076
0x140021126  mov     eax, [rbp+var_18]
0x140021129  test    eax, eax
0x14002112b  jns     loc_140021245
0x140021131  lea     rax, [rbp+var_20]
0x140021135  mov     [rbp+var_20], 0
0x14002113d  lea     r9, aPublisherpolic; "PublisherPolicyChangeTime"
0x140021144  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64 *
0x140021149  mov     qword ptr [rbp+var_18], 0
0x140021151  call    ?CbsRegQueryQWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEA_K@Z; CbsRegQueryQWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,unsigned __int64 *)
0x140021156  mov     ebx, eax
0x140021158  cmp     eax, 80070002h
0x14002115d  jz      loc_140021245
0x140021163  test    eax, eax
0x140021165  jns     short loc_1400211BD
0x140021167  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002116e  mov     [rbp+var_18], eax
0x140021171  test    rcx, rcx
0x140021174  jz      short loc_1400211B3
0x140021176  mov     edi, 3
0x14002117b  lea     r9, aFailedGettingP; "Failed getting PublisherPolicyChangeTim"...
0x140021182  mov     r8d, edi
0x140021185  xor     edx, edx
0x140021187  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002118c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021193  lea     rax, [rbp+var_18]
0x140021197  mov     [rbp+var_20], rax
0x14002119b  lea     r9, asc_1400353E8; ": {}"
0x1400211a2  lea     rax, [rbp+var_20]
0x1400211a6  mov     r8d, edi
0x1400211a9  mov     qword ptr [rsp+50h+var_30], rax
0x1400211ae  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400211b3  mov     edx, 3Dh ; '='
0x1400211b8  jmp     loc_140021076
0x1400211bd  lea     rax, [rbp+var_18]
0x1400211c1  lea     r9, aLastscavengeco; "LastScavengeCookie"
0x1400211c8  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64 *
0x1400211cd  call    ?CbsRegQueryQWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEA_K@Z; CbsRegQueryQWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,unsigned __int64 *)
0x1400211d2  mov     ebx, eax
0x1400211d4  cmp     eax, 80070002h
0x1400211d9  jz      short loc_140021245
0x1400211db  test    eax, eax
0x1400211dd  jns     short loc_140021235
0x1400211df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400211e6  mov     [rbp+var_18], eax
0x1400211e9  test    rcx, rcx
0x1400211ec  jz      short loc_14002122B
0x1400211ee  mov     edi, 3
0x1400211f3  lea     r9, aFailedGettingL; "Failed getting LastScavengeCookie."
0x1400211fa  mov     r8d, edi
0x1400211fd  xor     edx, edx
0x1400211ff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140021204  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002120b  lea     rax, [rbp+var_18]
0x14002120f  mov     [rbp+var_20], rax
0x140021213  lea     r9, asc_1400353E8; ": {}"
0x14002121a  lea     rax, [rbp+var_20]
0x14002121e  mov     r8d, edi
0x140021221  mov     qword ptr [rsp+50h+var_30], rax
0x140021226  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002122b  mov     edx, 45h ; 'E'
0x140021230  jmp     loc_140021076
0x140021235  mov     rax, qword ptr [rbp+var_18]
0x140021239  cmp     [rbp+var_20], rax
0x14002123d  jnz     short loc_140021245
0x14002123f  mov     dword ptr [rdi], 1
0x140021245  xor     eax, eax
0x140021247  mov     rcx, [rbp+var_10]
0x14002124b  xor     rcx, rsp; StackCookie
0x14002124e  call    __security_check_cookie
0x140021253  mov     rbx, [rsp+50h+arg_0]
0x140021258  mov     rdi, [rsp+50h+arg_10]
0x14002125d  add     rsp, 50h
0x140021261  pop     rbp
0x140021262  retn
```

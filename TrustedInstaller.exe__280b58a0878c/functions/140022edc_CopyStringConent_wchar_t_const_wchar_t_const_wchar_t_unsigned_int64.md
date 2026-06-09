# CopyStringConent(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x140022edc`
- end: `0x14002327a`
- name: `?CopyStringConent@@YAJPEB_W0PEA_W_K@Z`
- size: `926`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140023280`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001c5fc`
- `0x140022edc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140023016`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140023016`

## string_xrefs

- `0x140023255`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x1400231b8`: `Failed to copy string`

## pseudocode

```c
__int64 __fastcall CopyStringConent(const wchar_t *a1, const wchar_t *a2, wchar_t *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  wchar_t *v9; // rax
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  wchar_t i; // ax
  __int64 v13; // rdx
  wchar_t v14; // dx
  _WORD *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-30h]
  int v22[2]; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        v9 = wcsstr(a1, a2);
        v10 = v9;
        if ( v9 )
        {
          for ( i = *v9; i && i != 34; i = *v10 )
            ++v10;
          if ( *v10 )
          {
            v14 = v10[1];
            v15 = v10 + 1;
            if ( !v14 )
              goto LABEL_38;
            do
            {
              if ( v14 == 34 )
                break;
              v14 = *++v15;
            }
            while ( *v15 );
            if ( *v15 )
            {
              if ( (unsigned __int64)(v15 - v10) <= 0xFF )
              {
                v17 = StringCchCopyNW(a3, 0xFFu, v10 + 1, v15 - v10 - 1);
                v4 = v17;
                if ( v17 >= 0 )
                  return 0;
                v23 = v17;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy string");
                  *(_QWORD *)v22 = &v23;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    v18,
                    3,
                    (__int64)": {}",
                    (__int64)v22);
                }
                v6 = 785;
              }
              else
              {
                v4 = -2147024809;
                v23 = -2147024809;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Value too long");
                  *(_QWORD *)v22 = &v23;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    v16,
                    3,
                    (__int64)": {}",
                    (__int64)v22);
                }
                v6 = 782;
              }
            }
            else
            {
LABEL_38:
              v4 = -2147024809;
              v23 = -2147024809;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"No quote found");
                *(_QWORD *)v22 = &v23;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  v20,
                  3,
                  (__int64)": {}",
                  (__int64)v22);
              }
              v6 = 776;
            }
          }
          else
          {
            v4 = -2147024809;
            v23 = -2147024809;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"No quote found");
              *(_QWORD *)v22 = &v23;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v13,
                3,
                (__int64)": {}",
                (__int64)v22);
            }
            v6 = 768;
          }
        }
        else
        {
          v4 = -2147024809;
          v23 = -2147024809;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"No tag found");
            *(_QWORD *)v22 = &v23;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v11,
              3,
              (__int64)": {}",
              (__int64)v22);
          }
          v6 = 760;
        }
      }
      else
      {
        v4 = -2147467261;
        v23 = -2147467261;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No result buffer specified");
          *(_QWORD *)v22 = &v23;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v8,
            3,
            (__int64)": {}",
            (__int64)v22);
        }
        v6 = 757;
      }
    }
    else
    {
      v4 = -2147024809;
      v23 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No tag specified");
        *(_QWORD *)v22 = &v23;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v7,
          3,
          (__int64)": {}",
          (__int64)v22);
      }
      v6 = 756;
    }
  }
  else
  {
    v4 = -2147024809;
    v23 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No start specified");
      *(_QWORD *)v22 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v22);
    }
    v6 = 755;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
    (const char *)v4,
    v21);
  return v4;
}

```

## disassembly

```asm
0x140022edc  push    rbp
0x140022ede  push    rbx
0x140022edf  push    rdi
0x140022ee0  mov     rbp, rsp
0x140022ee3  sub     rsp, 50h
0x140022ee7  mov     rax, cs:__security_cookie
0x140022eee  xor     rax, rsp
0x140022ef1  mov     [rbp+var_10], rax
0x140022ef5  xor     edi, edi
0x140022ef7  mov     rbx, r8
0x140022efa  test    rcx, rcx
0x140022efd  jnz     short loc_140022F5A
0x140022eff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022f06  mov     ebx, 80070057h
0x140022f0b  mov     [rbp+var_18], ebx
0x140022f0e  test    rcx, rcx
0x140022f11  jz      short loc_140022F50
0x140022f13  mov     edi, 3
0x140022f18  lea     r9, aNoStartSpecifi; "No start specified"
0x140022f1f  mov     r8d, edi
0x140022f22  xor     edx, edx
0x140022f24  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022f29  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022f30  lea     rax, [rbp+var_18]
0x140022f34  mov     qword ptr [rbp+var_20], rax
0x140022f38  lea     r9, asc_1400353E8; ": {}"
0x140022f3f  lea     rax, [rbp+var_20]
0x140022f43  mov     r8d, edi
0x140022f46  mov     qword ptr [rsp+50h+var_30], rax
0x140022f4b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022f50  mov     edx, 2F3h
0x140022f55  jmp     loc_140023251
0x140022f5a  test    rdx, rdx
0x140022f5d  jnz     short loc_140022FB6
0x140022f5f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022f66  mov     ebx, 80070057h
0x140022f6b  mov     [rbp+var_18], ebx
0x140022f6e  test    rcx, rcx
0x140022f71  jz      short loc_140022FAC
0x140022f73  lea     edi, [rdx+3]
0x140022f76  mov     r8d, edi
0x140022f79  lea     r9, aNoTagSpecified; "No tag specified"
0x140022f80  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022f85  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022f8c  lea     rax, [rbp+var_18]
0x140022f90  mov     qword ptr [rbp+var_20], rax
0x140022f94  lea     r9, asc_1400353E8; ": {}"
0x140022f9b  lea     rax, [rbp+var_20]
0x140022f9f  mov     r8d, edi
0x140022fa2  mov     qword ptr [rsp+50h+var_30], rax
0x140022fa7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022fac  mov     edx, 2F4h
0x140022fb1  jmp     loc_140023251
0x140022fb6  test    rbx, rbx
0x140022fb9  jnz     short loc_140023016
0x140022fbb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022fc2  mov     ebx, 80004003h
0x140022fc7  mov     [rbp+var_18], ebx
0x140022fca  test    rcx, rcx
0x140022fcd  jz      short loc_14002300C
0x140022fcf  mov     edi, 3
0x140022fd4  lea     r9, aNoResultBuffer; "No result buffer specified"
0x140022fdb  mov     r8d, edi
0x140022fde  xor     edx, edx
0x140022fe0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022fe5  lea     rcx, [rbp+var_20]
0x140022fe9  mov     r8d, edi
0x140022fec  mov     qword ptr [rsp+50h+var_30], rcx
0x140022ff1  lea     rax, [rbp+var_18]
0x140022ff5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022ffc  lea     r9, asc_1400353E8; ": {}"
0x140023003  mov     qword ptr [rbp+var_20], rax
0x140023007  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002300c  mov     edx, 2F5h; SubStr
0x140023011  jmp     loc_140023251
0x140023016  call    cs:__imp_wcsstr
0x14002301c  mov     rcx, rax
0x14002301f  test    rax, rax
0x140023022  jnz     short loc_14002307D
0x140023024  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002302b  mov     ebx, 80070057h
0x140023030  mov     [rbp+var_18], ebx
0x140023033  test    rcx, rcx
0x140023036  jz      short loc_140023073
0x140023038  lea     edi, [rax+3]
0x14002303b  xor     edx, edx
0x14002303d  mov     r8d, edi
0x140023040  lea     r9, aNoTagFound; "No tag found"
0x140023047  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002304c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023053  lea     rax, [rbp+var_18]
0x140023057  mov     qword ptr [rbp+var_20], rax
0x14002305b  lea     r9, asc_1400353E8; ": {}"
0x140023062  lea     rax, [rbp+var_20]
0x140023066  mov     r8d, edi
0x140023069  mov     qword ptr [rsp+50h+var_30], rax
0x14002306e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023073  mov     edx, 2F8h
0x140023078  jmp     loc_140023251
0x14002307d  movzx   eax, word ptr [rax]
0x140023080  jmp     short loc_14002308F
0x140023082  cmp     ax, 22h ; '"'
0x140023086  jz      short loc_140023094
0x140023088  add     rcx, 2
0x14002308c  movzx   eax, word ptr [rcx]
0x14002308f  test    ax, ax
0x140023092  jnz     short loc_140023082
0x140023094  cmp     [rcx], di
0x140023097  jnz     short loc_1400230F4
0x140023099  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400230a0  mov     ebx, 80070057h
0x1400230a5  mov     [rbp+var_18], ebx
0x1400230a8  test    rcx, rcx
0x1400230ab  jz      short loc_1400230EA
0x1400230ad  mov     edi, 3
0x1400230b2  lea     r9, aNoQuoteFound; "No quote found"
0x1400230b9  mov     r8d, edi
0x1400230bc  xor     edx, edx
0x1400230be  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400230c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400230ca  lea     rax, [rbp+var_18]
0x1400230ce  mov     qword ptr [rbp+var_20], rax
0x1400230d2  lea     r9, asc_1400353E8; ": {}"
0x1400230d9  lea     rax, [rbp+var_20]
0x1400230dd  mov     r8d, edi
0x1400230e0  mov     qword ptr [rsp+50h+var_30], rax
0x1400230e5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400230ea  mov     edx, 300h
0x1400230ef  jmp     loc_140023251
0x1400230f4  lea     r8, [rcx+2]; wchar_t *
0x1400230f8  movzx   edx, word ptr [r8]
0x1400230fc  mov     rax, r8
0x1400230ff  test    dx, dx
0x140023102  jz      loc_1400231FB
0x140023108  cmp     dx, 22h ; '"'
0x14002310c  jz      short loc_14002311A
0x14002310e  add     rax, 2
0x140023112  movzx   edx, word ptr [rax]
0x140023115  test    dx, dx
0x140023118  jnz     short loc_140023108
0x14002311a  cmp     [rax], di
0x14002311d  jz      loc_1400231FB
0x140023123  sub     rax, rcx
0x140023126  mov     edx, 0FFh; unsigned __int64
0x14002312b  sar     rax, 1
0x14002312e  lea     r9, [rax-1]; unsigned __int64
0x140023132  lea     rax, [r9+1]
0x140023136  cmp     rax, rdx
0x140023139  jbe     short loc_140023196
0x14002313b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023142  mov     ebx, 80070057h
0x140023147  mov     [rbp+var_18], ebx
0x14002314a  test    rcx, rcx
0x14002314d  jz      short loc_14002318C
0x14002314f  mov     edi, 3
0x140023154  lea     r9, aValueTooLong; "Value too long"
0x14002315b  mov     r8d, edi
0x14002315e  xor     edx, edx
0x140023160  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023165  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002316c  lea     rax, [rbp+var_18]
0x140023170  mov     qword ptr [rbp+var_20], rax
0x140023174  lea     r9, asc_1400353E8; ": {}"
0x14002317b  lea     rax, [rbp+var_20]
0x14002317f  mov     r8d, edi
0x140023182  mov     qword ptr [rsp+50h+var_30], rax
0x140023187  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002318c  mov     edx, 30Eh
0x140023191  jmp     loc_140023251
0x140023196  mov     rcx, rbx; wchar_t *
0x140023199  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x14002319e  mov     ebx, eax
0x1400231a0  test    eax, eax
0x1400231a2  jns     short loc_1400231F7
0x1400231a4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400231ab  mov     [rbp+var_18], eax
0x1400231ae  test    rcx, rcx
0x1400231b1  jz      short loc_1400231F0
0x1400231b3  mov     edi, 3
0x1400231b8  lea     r9, aFailedToCopySt; "Failed to copy string"
0x1400231bf  mov     r8d, edi
0x1400231c2  xor     edx, edx
0x1400231c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400231c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400231d0  lea     rax, [rbp+var_18]
0x1400231d4  mov     qword ptr [rbp+var_20], rax
0x1400231d8  lea     r9, asc_1400353E8; ": {}"
0x1400231df  lea     rax, [rbp+var_20]
0x1400231e3  mov     r8d, edi
0x1400231e6  mov     qword ptr [rsp+50h+var_30], rax
0x1400231eb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400231f0  mov     edx, 311h
0x1400231f5  jmp     short loc_140023251
0x1400231f7  xor     eax, eax
0x1400231f9  jmp     short loc_140023266
0x1400231fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023202  mov     ebx, 80070057h
0x140023207  mov     [rbp+var_18], ebx
0x14002320a  test    rcx, rcx
0x14002320d  jz      short loc_14002324C
0x14002320f  mov     edi, 3
0x140023214  lea     r9, aNoQuoteFound; "No quote found"
0x14002321b  mov     r8d, edi
0x14002321e  xor     edx, edx
0x140023220  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023225  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002322c  lea     rax, [rbp+var_18]
0x140023230  mov     qword ptr [rbp+var_20], rax
0x140023234  lea     r9, asc_1400353E8; ": {}"
0x14002323b  lea     rax, [rbp+var_20]
0x14002323f  mov     r8d, edi
0x140023242  mov     qword ptr [rsp+50h+var_30], rax; int
0x140023247  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002324c  mov     edx, 308h; void *
0x140023251  mov     rcx, [rbp+18h]; this
0x140023255  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x14002325c  mov     r9d, ebx; char *
0x14002325f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023264  mov     eax, ebx
0x140023266  mov     rcx, [rbp+var_10]
0x14002326a  xor     rcx, rsp; StackCookie
0x14002326d  call    __security_check_cookie
0x140023272  add     rsp, 50h
0x140023276  pop     rdi
0x140023277  pop     rbx
0x140023278  pop     rbp
0x140023279  retn
```

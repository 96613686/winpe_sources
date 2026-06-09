# CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x180045544`
- end: `0x180045900`
- name: `?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z`
- size: `956`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046680`
- `0x180070418`
- `0x18007150c`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x180043c70`
- `0x180044170`
- `0x180045544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800456c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045805`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800458bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800456c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045805`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800458bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800457d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800457d1`

## string_xrefs

- `0x180045634`: `Failed to create key: {}`
- `0x180045756`: `Failed to open key: {}`
- `0x180045847`: `Failed to set registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegSetDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, wchar_t *a4, unsigned int Data)
{
  const WCHAR *v5; // rax
  char v6; // si
  unsigned int v7; // ebx
  __int64 v8; // rdx
  LSTATUS v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  HKEY v15; // rcx
  bool v16; // zf
  LSTATUS v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  LSTATUS v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned int *lpData; // [rsp+20h] [rbp-31h]
  unsigned int *lpDataa; // [rsp+20h] [rbp-31h]
  DWORD cbData; // [rsp+28h] [rbp-29h]
  struct _SECURITY_ATTRIBUTES *v26; // [rsp+30h] [rbp-21h]
  unsigned int v27[2]; // [rsp+50h] [rbp-1h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp+Fh] BYREF
  wchar_t *v29; // [rsp+70h] [rbp+1Fh] BYREF
  int v30; // [rsp+78h] [rbp+27h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]

  v28[0] = a2;
  v5 = a4;
  v29 = a4;
  v6 = a3;
  if ( !a4 )
  {
    v7 = -2147024809;
    v30 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No value name specified");
      *(_QWORD *)v27 = &v30;
      LOBYTE(v8) = 1;
      lpData = v27;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v8,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28A,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
      (const char *)0x80070057LL,
      (int)lpData);
    return v7;
  }
  hKey = 0;
  if ( a2 )
  {
    if ( (a3 & 2) != 0 )
    {
      v10 = CbsRegCreateKeyExW(a1, a2, a3, a4, (unsigned int)lpData, cbData, v26, &hKey);
      if ( v10 )
      {
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to create key: {}",
            v28);
          if ( v10 > 0 )
            v12 = (unsigned __int16)v10 | 0x80070000;
          else
            v12 = v10;
          v30 = v12;
          LOBYTE(v11) = 1;
          *(_QWORD *)v27 = &v30;
          lpDataa = v27;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v11,
            3,
            ": {0}");
        }
        v13 = 660;
        goto LABEL_15;
      }
    }
    else
    {
      v17 = CbsRegOpenKeyExW(a1, a2, 0, 2u, &hKey);
      v10 = v17;
      if ( (v6 & 1) != 0 && (v17 == 2 || v17 == 3) )
      {
        v7 = (unsigned __int16)v17 | 0x80070000;
        v15 = hKey;
        if ( hKey )
        {
          v16 = ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) == 0xFFFFFFFF80000000uLL;
          goto LABEL_17;
        }
        return v7;
      }
      if ( v17 )
      {
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to open key: {}",
            v28);
          if ( v10 > 0 )
            v19 = (unsigned __int16)v10 | 0x80070000;
          else
            v19 = v10;
          v30 = v19;
          LOBYTE(v18) = 1;
          *(_QWORD *)v27 = &v30;
          lpDataa = v27;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v18,
            3,
            ": {0}");
        }
        v13 = 669;
LABEL_15:
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v13,
                (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
                (const char *)(unsigned int)v10,
                (unsigned int)lpDataa);
        v15 = hKey;
        v7 = v14;
        if ( hKey )
        {
          v16 = ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) == 0xFFFFFFFF80000000uLL;
LABEL_17:
          if ( !v16 && RegCloseKey(v15) )
          {
            GetLastError();
            __fastfail(7u);
          }
          return v7;
        }
        return v7;
      }
    }
    a1 = hKey;
    v5 = v29;
  }
  v20 = RegSetValueExW(a1, v5, 0, 4u, (const BYTE *)&Data, 4u);
  v10 = v20;
  if ( (v6 & 1) != 0 && v20 == 2 )
  {
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
    {
      GetLastError();
      __fastfail(v10 + 5);
    }
    return 2147942402LL;
  }
  if ( v20 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to set registry value: {}",
        &v29);
      if ( v10 > 0 )
        v22 = (unsigned __int16)v10 | 0x80070000;
      else
        v22 = v10;
      v30 = v22;
      LOBYTE(v21) = 1;
      *(_QWORD *)v27 = &v30;
      lpDataa = v27;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {0}");
    }
    v13 = 686;
    goto LABEL_15;
  }
  if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x180045544  mov     [rsp-8+arg_10], rbx
0x180045549  push    rbp
0x18004554a  push    rsi
0x18004554b  push    rdi
0x18004554c  lea     rbp, [rsp-3Fh]
0x180045551  sub     rsp, 90h
0x180045558  mov     rax, cs:__security_cookie
0x18004555f  xor     rax, rsp
0x180045562  mov     [rbp+4Fh+var_18], rax
0x180045566  mov     [rbp+4Fh+var_40], rdx
0x18004556a  mov     rax, r9
0x18004556d  mov     [rbp+4Fh+var_30], rax
0x180045571  mov     esi, r8d
0x180045574  test    r9, r9
0x180045577  jnz     short loc_1800455E9
0x180045579  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045580  mov     ebx, 80070057h
0x180045585  mov     [rbp+4Fh+var_28], ebx
0x180045588  test    rcx, rcx
0x18004558b  jz      short loc_1800455CA
0x18004558d  lea     edi, [rax+3]
0x180045590  xor     edx, edx
0x180045592  mov     r8d, edi
0x180045595  lea     r9, aNoValueNameSpe; "No value name specified"
0x18004559c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800455a1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800455a8  lea     rax, [rbp+4Fh+var_28]
0x1800455ac  mov     qword ptr [rbp+4Fh+var_50], rax
0x1800455b0  lea     r9, asc_1801CAFB4; ": {}"
0x1800455b7  lea     rax, [rbp+4Fh+var_50]
0x1800455bb  mov     r8d, edi
0x1800455be  mov     dl, 1
0x1800455c0  mov     [rsp+0A0h+lpData], rax; int
0x1800455c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800455ca  mov     rcx, [rbp+57h]; this
0x1800455ce  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800455d5  mov     r9d, ebx; char *
0x1800455d8  mov     edx, 28Ah; void *
0x1800455dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800455e2  mov     eax, ebx
0x1800455e4  jmp     loc_1800458E0
0x1800455e9  mov     [rbp+4Fh+hKey], 0
0x1800455f1  mov     edi, 3
0x1800455f6  test    rdx, rdx
0x1800455f9  jz      loc_1800457B7
0x1800455ff  lea     rax, [rbp+4Fh+hKey]
0x180045603  test    sil, 2
0x180045607  jz      loc_1800456EC
0x18004560d  mov     [rsp+0A0h+var_68], rax; HKEY *
0x180045612  call    ?CbsRegCreateKeyExW@@YAKPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; CbsRegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x180045617  mov     ebx, eax
0x180045619  test    eax, eax
0x18004561b  jz      loc_1800457AF
0x180045621  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045628  test    rcx, rcx
0x18004562b  jz      short loc_180045683
0x18004562d  lea     rax, [rbp+4Fh+var_40]
0x180045631  mov     r8d, edi
0x180045634  lea     r9, aFailedToCreate_23; "Failed to create key: {}"
0x18004563b  mov     [rsp+0A0h+lpData], rax
0x180045640  xor     edx, edx
0x180045642  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180045647  test    ebx, ebx
0x180045649  jg      short loc_18004564F
0x18004564b  mov     eax, ebx
0x18004564d  jmp     short loc_180045657
0x18004564f  movzx   eax, bx
0x180045652  or      eax, 80070000h
0x180045657  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004565e  lea     r9, a0; ": {0}"
0x180045665  mov     [rbp+4Fh+var_28], eax
0x180045668  mov     r8d, edi
0x18004566b  lea     rax, [rbp+4Fh+var_28]
0x18004566f  mov     dl, 1
0x180045671  mov     qword ptr [rbp+4Fh+var_50], rax
0x180045675  lea     rax, [rbp+4Fh+var_50]
0x180045679  mov     [rsp+0A0h+lpData], rax; unsigned int
0x18004567e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180045683  mov     edx, 294h; void *
0x180045688  mov     rcx, [rbp+57h]; this
0x18004568c  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180045693  mov     r9d, ebx; char *
0x180045696  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004569b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004569f  mov     ebx, eax
0x1800456a1  test    rcx, rcx
0x1800456a4  jz      loc_1800455E2
0x1800456aa  mov     r8, 0FFFFFFFF80000000h
0x1800456b1  mov     rdx, rcx
0x1800456b4  and     rdx, r8
0x1800456b7  cmp     rdx, r8
0x1800456ba  jz      loc_1800455E2
0x1800456c0  call    cs:__imp_RegCloseKey
0x1800456c7  nop     dword ptr [rax+rax+00h]
0x1800456cc  test    eax, eax
0x1800456ce  jz      loc_1800455E2
0x1800456d4  call    cs:__imp_GetLastError
0x1800456db  nop     dword ptr [rax+rax+00h]
0x1800456e0  mov     ecx, 7; hKey
0x1800456e5  int     29h; Win8: RtlFailFast(ecx)
0x1800456e7  jmp     loc_1800455E2
0x1800456ec  mov     r9d, 2; samDesired
0x1800456f2  mov     [rsp+0A0h+lpData], rax; PHKEY
0x1800456f7  xor     r8d, r8d; ulOptions
0x1800456fa  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800456ff  mov     ebx, eax
0x180045701  test    sil, 1
0x180045705  jz      short loc_18004573F
0x180045707  cmp     eax, 2
0x18004570a  jz      short loc_180045714
0x18004570c  cmp     eax, edi
0x18004570e  jnz     short loc_18004573F
0x180045710  test    eax, eax
0x180045712  jle     short loc_18004571D
0x180045714  movzx   ebx, bx
0x180045717  or      ebx, 80070000h
0x18004571d  mov     rcx, [rbp+4Fh+hKey]
0x180045721  test    rcx, rcx
0x180045724  jz      loc_1800455E2
0x18004572a  mov     r8, 0FFFFFFFF80000000h
0x180045731  mov     rax, rcx
0x180045734  and     rax, r8
0x180045737  cmp     rax, r8
0x18004573a  jmp     loc_1800456BA
0x18004573f  test    ebx, ebx
0x180045741  jz      short loc_1800457AF
0x180045743  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004574a  test    rcx, rcx
0x18004574d  jz      short loc_1800457A5
0x18004574f  lea     rax, [rbp+4Fh+var_40]
0x180045753  mov     r8d, edi
0x180045756  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x18004575d  mov     [rsp+0A0h+lpData], rax
0x180045762  xor     edx, edx
0x180045764  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180045769  test    ebx, ebx
0x18004576b  jg      short loc_180045771
0x18004576d  mov     eax, ebx
0x18004576f  jmp     short loc_180045779
0x180045771  movzx   eax, bx
0x180045774  or      eax, 80070000h
0x180045779  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045780  lea     r9, a0; ": {0}"
0x180045787  mov     [rbp+4Fh+var_28], eax
0x18004578a  mov     r8d, edi
0x18004578d  lea     rax, [rbp+4Fh+var_28]
0x180045791  mov     dl, 1
0x180045793  mov     qword ptr [rbp+4Fh+var_50], rax
0x180045797  lea     rax, [rbp+4Fh+var_50]
0x18004579b  mov     [rsp+0A0h+lpData], rax
0x1800457a0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800457a5  mov     edx, 29Dh
0x1800457aa  jmp     loc_180045688
0x1800457af  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800457b3  mov     rax, [rbp+4Fh+var_30]
0x1800457b7  mov     r9d, 4; dwType
0x1800457bd  lea     rdx, [rbp+4Fh+Data]
0x1800457c1  mov     [rsp+0A0h+cbData], r9d; cbData
0x1800457c6  xor     r8d, r8d; Reserved
0x1800457c9  mov     [rsp+0A0h+lpData], rdx; lpData
0x1800457ce  mov     rdx, rax; lpValueName
0x1800457d1  call    cs:__imp_RegSetValueExW
0x1800457d8  nop     dword ptr [rax+rax+00h]
0x1800457dd  mov     ebx, eax
0x1800457df  test    sil, 1
0x1800457e3  jz      short loc_180045830
0x1800457e5  cmp     eax, 2
0x1800457e8  jnz     short loc_180045830
0x1800457ea  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800457ee  test    rcx, rcx
0x1800457f1  jz      short loc_180045826
0x1800457f3  mov     r8, 0FFFFFFFF80000000h
0x1800457fa  mov     rax, rcx
0x1800457fd  and     rax, r8
0x180045800  cmp     rax, r8
0x180045803  jz      short loc_180045826
0x180045805  call    cs:__imp_RegCloseKey
0x18004580c  nop     dword ptr [rax+rax+00h]
0x180045811  test    eax, eax
0x180045813  jz      short loc_180045826
0x180045815  call    cs:__imp_GetLastError
0x18004581c  nop     dword ptr [rax+rax+00h]
0x180045821  lea     ecx, [rbx+5]
0x180045824  int     29h; Win8: RtlFailFast(ecx)
0x180045826  mov     eax, 80070002h
0x18004582b  jmp     loc_1800458E0
0x180045830  test    ebx, ebx
0x180045832  jz      short loc_1800458A0
0x180045834  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004583b  test    rcx, rcx
0x18004583e  jz      short loc_180045896
0x180045840  lea     rax, [rbp+4Fh+var_30]
0x180045844  mov     r8d, edi
0x180045847  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x18004584e  mov     [rsp+0A0h+lpData], rax
0x180045853  xor     edx, edx
0x180045855  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004585a  test    ebx, ebx
0x18004585c  jg      short loc_180045862
0x18004585e  mov     eax, ebx
0x180045860  jmp     short loc_18004586A
0x180045862  movzx   eax, bx
0x180045865  or      eax, 80070000h
0x18004586a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180045871  lea     r9, a0; ": {0}"
0x180045878  mov     [rbp+4Fh+var_28], eax
0x18004587b  mov     r8d, edi
0x18004587e  lea     rax, [rbp+4Fh+var_28]
0x180045882  mov     dl, 1
0x180045884  mov     qword ptr [rbp+4Fh+var_50], rax
0x180045888  lea     rax, [rbp+4Fh+var_50]
0x18004588c  mov     [rsp+0A0h+lpData], rax
0x180045891  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180045896  mov     edx, 2AEh
0x18004589b  jmp     loc_180045688
0x1800458a0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800458a4  test    rcx, rcx
0x1800458a7  jz      short loc_1800458DE
0x1800458a9  mov     r8, 0FFFFFFFF80000000h
0x1800458b0  mov     rax, rcx
0x1800458b3  and     rax, r8
0x1800458b6  cmp     rax, r8
0x1800458b9  jz      short loc_1800458DE
0x1800458bb  call    cs:__imp_RegCloseKey
0x1800458c2  nop     dword ptr [rax+rax+00h]
0x1800458c7  test    eax, eax
0x1800458c9  jz      short loc_1800458DE
0x1800458cb  call    cs:__imp_GetLastError
0x1800458d2  nop     dword ptr [rax+rax+00h]
0x1800458d7  mov     ecx, 7
0x1800458dc  int     29h; Win8: RtlFailFast(ecx)
0x1800458de  xor     eax, eax
0x1800458e0  mov     rcx, [rbp+4Fh+var_18]
0x1800458e4  xor     rcx, rsp; StackCookie
0x1800458e7  call    __security_check_cookie
0x1800458ec  mov     rbx, [rsp+0A0h+arg_10]
0x1800458f4  add     rsp, 90h
0x1800458fb  pop     rdi
0x1800458fc  pop     rsi
0x1800458fd  pop     rbp
0x1800458fe  retn
```

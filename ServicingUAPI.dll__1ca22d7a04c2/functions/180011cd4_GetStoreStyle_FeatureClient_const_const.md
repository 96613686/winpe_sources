# GetStoreStyle(FeatureClient const * const)

- ea: `0x180011cd4`
- end: `0x180012112`
- name: `?GetStoreStyle@@YA?AW4StoreStyle@@QEBUFeatureClient@@@Z`
- size: `1086`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d090`
- `0x18000d6c0`
- `0x18000ea40`
- `0x18000f310`

## callees

- `0x1800031d0`
- `0x180004c70`
- `0x180008a90`
- `0x180009750`
- `0x18000c468`
- `0x18000f614`
- `0x18000f874`
- `0x18000fb10`
- `0x180011cd4`
- `0x180012418`
- `0x18001268c`
- `0x18002bc54`
- `0x18002e804`
- `0x180179140`
- `0x180195ea4`
- `0x18019602c`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012015`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180012005`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180012005`

## string_xrefs

- `0x1800120ac`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x180012096`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x1800120c1`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x1800120d6`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x1800120eb`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180012100`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011f4b`: `wszOfflineWinDir and wszOfflineBootDir are required if UpdateAPI is not available`
- `0x180011d4d`: `\System32\config\SOFTWARE`
- `0x180011dcc`: `Failed to open software hive at {0}`
- `0x180011e6c`: `Microsoft\Windows\CurrentVersion\SideBySide\Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall GetStoreStyle(__int64 a1)
{
  __int64 v2; // rbx
  const wchar_t *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rax
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  __int16 *trivial_2; // rax
  const char *v10; // r9
  __int64 v11; // rax
  int RegistryDWORD; // eax
  int v13; // edi
  __int64 v14; // rdx
  int AdjacentLibraryAndFunction; // eax
  int v17; // ebx
  __int64 v18; // rdx
  int v19; // eax
  int v20; // ebx
  __int64 v21; // rdx
  char v22; // bl
  const char *v23; // r9
  void *v24; // [rsp+28h] [rbp-49h]
  int *v25; // [rsp+28h] [rbp-49h]
  int v26[2]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v27; // [rsp+40h] [rbp-31h]
  HMODULE hLibModule[2]; // [rsp+48h] [rbp-29h] BYREF
  __int64 v29; // [rsp+58h] [rbp-19h] BYREF
  __int64 (*v30[2])(void); // [rsp+60h] [rbp-11h] BYREF
  int v31; // [rsp+70h] [rbp-1h] BYREF
  int v32; // [rsp+74h] [rbp+3h] BYREF
  _QWORD v33[4]; // [rsp+78h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v30[1] = (__int64 (*)(void))-2LL;
  ValidateClient((const struct FeatureClient *const)a1);
  v2 = 0;
  v29 = 0;
  v32 = 0;
  if ( (*(_BYTE *)(a1 + 160) & 1) == 0 )
  {
LABEL_13:
    trivial_2 = (__int16 *)_std_find_trivial_2(L"SOFTWARE", word_1801CAECA, 0);
    if ( trivial_2 == word_1801CAECA || (v11 = ((char *)trivial_2 - (char *)L"SOFTWARE") >> 1, v11 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
        v10);
    *(_QWORD *)v26 = L"SOFTWARE";
    v27 = v11;
    v25 = &v32;
    RegistryDWORD = GetRegistryDWORD(
                      v2,
                      v26,
                      L"Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
                      L"MobileStoreVersion");
    v13 = RegistryDWORD;
    if ( RegistryDWORD < 0 )
    {
      v31 = RegistryDWORD;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Could not query SxS version value");
        *(_QWORD *)v26 = &v31;
        v25 = v26;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v14,
          3,
          ": {}");
      }
    }
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        (const char *)(unsigned int)v13,
        (int)v25);
    switch ( v32 )
    {
      case 1:
        if ( v2 && (unsigned int)ORCloseHive(v2) )
          __fastfail(7u);
        return 1;
      case 2:
        if ( v2 && (unsigned int)ORCloseHive(v2) )
          __fastfail(7u);
        return 2;
      case 4:
        if ( v2 )
        {
          if ( (unsigned int)ORCloseHive(v2) )
            __fastfail(7u);
        }
        return 4;
      default:
        v23 = (const char *)(unsigned int)EnsureNTSTATUS<long>(2149090053LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
          v23,
          (int)v25);
    }
  }
  v3 = *(const wchar_t **)(a1 + 192);
  if ( v3 && *v3 )
  {
    *(_QWORD *)v26 = L"\\System32\\config\\SOFTWARE";
    v27 = 25;
    hLibModule[0] = (HMODULE)v3;
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    hLibModule[1] = (HMODULE)v4;
    CreatePath(v33, hLibModule, v26);
    v5 = v33;
    if ( v33[3] > 7u )
      v5 = (_QWORD *)v33[0];
    *(_QWORD *)v26 = v5;
    v27 = v33[2];
    v6 = OpenHive(v26, &v29);
    v7 = v6;
    if ( v6 < 0 )
    {
      v31 = v6;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<std::wstring>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to open software hive at {0}",
          v33);
        hLibModule[0] = (HMODULE)&v31;
        v24 = hLibModule;
        LOBYTE(v8) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v8,
          3,
          ": {}");
      }
    }
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        (const char *)(unsigned int)v7,
        (int)v24);
    std::wstring::~wstring(v33);
    v2 = v29;
    goto LABEL_13;
  }
  hLibModule[0] = 0;
  v30[0] = 0;
  AdjacentLibraryAndFunction = LoadAdjacentLibraryAndFunction(v3, "GetMobileStoreVersion", hLibModule, v30);
  v17 = AdjacentLibraryAndFunction;
  if ( AdjacentLibraryAndFunction < 0 )
  {
    v31 = AdjacentLibraryAndFunction;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "wszOfflineWinDir and wszOfflineBootDir are required if UpdateAPI is not available");
      *(_QWORD *)v26 = &v31;
      v24 = v26;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v18,
        3,
        ": {}");
    }
  }
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
      (const char *)(unsigned int)v17,
      (int)v24);
  v19 = ((__int64 (__fastcall *)(int *))v30[0])(&v32);
  v20 = v19;
  if ( v19 < 0 )
  {
    v31 = v19;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Could not query SxS mobile store version value");
      *(_QWORD *)v26 = &v31;
      v24 = v26;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {}");
    }
  }
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
      (const char *)(unsigned int)v20,
      (int)v24);
  v22 = v32;
  if ( hLibModule[0] && !FreeLibrary(hLibModule[0]) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return v22;
}

```

## disassembly

```asm
0x180011cd4  mov     rax, rsp
0x180011cd7  push    rbp
0x180011cd8  push    rdi
0x180011cd9  push    r12
0x180011cdb  push    r14
0x180011cdd  push    r15
0x180011cdf  lea     rbp, [rax-5Fh]
0x180011ce3  sub     rsp, 0A0h
0x180011cea  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x180011cf2  mov     [rax+10h], rbx
0x180011cf6  mov     [rax+18h], rsi
0x180011cfa  mov     rax, cs:__security_cookie
0x180011d01  xor     rax, rsp
0x180011d04  mov     [rbp+57h+var_30], rax
0x180011d08  mov     rdi, rcx
0x180011d0b  call    ?ValidateClient@@YAXQEBUFeatureClient@@@Z; ValidateClient(FeatureClient const * const)
0x180011d10  xor     r14d, r14d
0x180011d13  mov     ebx, r14d
0x180011d16  mov     [rbp+57h+var_70], rbx
0x180011d1a  mov     [rbp+57h+var_54], r14d
0x180011d1e  lea     esi, [r14+3]
0x180011d22  lea     r15d, [r14+7]
0x180011d26  test    byte ptr [rdi+0A0h], 1
0x180011d2d  jz      loc_180011E1F
0x180011d33  mov     rcx, [rdi+0C0h]; wchar_t *
0x180011d3a  test    rcx, rcx
0x180011d3d  jz      loc_180011F15
0x180011d43  cmp     r14w, [rcx]
0x180011d47  jz      loc_180011F15
0x180011d4d  lea     rax, aSystem32Config_0; "\\System32\\config\\SOFTWARE"
0x180011d54  mov     qword ptr [rbp+57h+var_90], rax
0x180011d58  mov     [rbp+57h+var_88], 19h
0x180011d60  mov     [rbp+57h+hLibModule], rcx
0x180011d64  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011d68  inc     rax
0x180011d6b  cmp     [rcx+rax*2], r14w
0x180011d70  jnz     short loc_180011D68
0x180011d72  mov     [rbp+57h+var_78], rax
0x180011d76  lea     r8, [rbp+57h+var_90]
0x180011d7a  lea     rdx, [rbp+57h+hLibModule]
0x180011d7e  lea     rcx, [rbp+57h+var_50]
0x180011d82  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x180011d87  nop
0x180011d88  mov     rcx, [rbp+57h+var_40]
0x180011d8c  lea     rax, [rbp+57h+var_50]
0x180011d90  cmp     [rbp+57h+var_38], r15
0x180011d94  cmova   rax, [rbp+57h+var_50]
0x180011d99  mov     qword ptr [rbp+57h+var_90], rax
0x180011d9d  mov     [rbp+57h+var_88], rcx
0x180011da1  lea     rdx, [rbp+57h+var_70]
0x180011da5  lea     rcx, [rbp+57h+var_90]
0x180011da9  call    ?OpenHive@@YAJV?$basic_zstring_view@_W@wil@@PEAPEAX@Z; OpenHive(wil::basic_zstring_view<wchar_t>,void * *)
0x180011dae  mov     ebx, eax
0x180011db0  test    eax, eax
0x180011db2  jns     short loc_180011E06
0x180011db4  mov     [rbp+57h+var_58], eax
0x180011db7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011dbe  test    rcx, rcx
0x180011dc1  jz      short loc_180011E06
0x180011dc3  lea     rax, [rbp+57h+var_50]
0x180011dc7  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180011dcc  lea     r9, aFailedToOpenSo; "Failed to open software hive at {0}"
0x180011dd3  mov     r8d, esi
0x180011dd6  xor     edx, edx
0x180011dd8  call    ??$LogNumObjects@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::Logger::LogNumObjects<std::wstring>(bool,LogAdapter::LogLevel,char const * const,std::wstring const &)
0x180011ddd  lea     rax, [rbp+57h+var_58]
0x180011de1  mov     [rbp+57h+hLibModule], rax
0x180011de5  lea     rax, [rbp+57h+hLibModule]
0x180011de9  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180011dee  lea     r9, asc_1801CAFB4; ": {}"
0x180011df5  mov     r8d, esi
0x180011df8  mov     dl, 1
0x180011dfa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011e01  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011e06  mov     rcx, [rbp+5Fh]; this
0x180011e0a  test    ebx, ebx
0x180011e0c  js      loc_1800120BE
0x180011e12  lea     rcx, [rbp+57h+var_50]; void *
0x180011e16  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e1b  mov     rbx, [rbp+57h+var_70]
0x180011e1f  xor     r8d, r8d
0x180011e22  lea     rdi, word_1801CAECA
0x180011e29  mov     rdx, rdi
0x180011e2c  lea     r12, aSoftware; "SOFTWARE"
0x180011e33  mov     rcx, r12
0x180011e36  call    __std_find_trivial_2
0x180011e3b  cmp     rax, rdi
0x180011e3e  jz      loc_1800120A8
0x180011e44  sub     rax, r12
0x180011e47  sar     rax, 1
0x180011e4a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011e4e  jz      loc_1800120A8
0x180011e54  mov     qword ptr [rbp+57h+var_90], r12
0x180011e58  mov     [rbp+57h+var_88], rax
0x180011e5c  lea     rax, [rbp+57h+var_54]
0x180011e60  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180011e65  lea     r9, aMobilestorever; "MobileStoreVersion"
0x180011e6c  lea     r8, aMicrosoftWindo_10; "Microsoft\\Windows\\CurrentVersion\\Sid"...
0x180011e73  lea     rdx, [rbp+57h+var_90]
0x180011e77  mov     rcx, rbx
0x180011e7a  call    ?GetRegistryDWORD@@YAJQEAXV?$basic_zstring_view@_W@wil@@QEB_W2PEAK@Z; GetRegistryDWORD(void * const,wil::basic_zstring_view<wchar_t>,wchar_t const * const,wchar_t const * const,ulong *)
0x180011e7f  mov     edi, eax
0x180011e81  test    eax, eax
0x180011e83  jns     short loc_180011ECE
0x180011e85  mov     [rbp+57h+var_58], eax
0x180011e88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011e8f  test    rcx, rcx
0x180011e92  jz      short loc_180011ECE
0x180011e94  lea     r9, aCouldNotQueryS; "Could not query SxS version value"
0x180011e9b  mov     r8d, esi
0x180011e9e  xor     edx, edx
0x180011ea0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011ea5  lea     rax, [rbp+57h+var_58]
0x180011ea9  mov     qword ptr [rbp+57h+var_90], rax
0x180011ead  lea     rax, [rbp+57h+var_90]
0x180011eb1  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180011eb6  lea     r9, asc_1801CAFB4; ": {}"
0x180011ebd  mov     r8d, esi
0x180011ec0  mov     dl, 1
0x180011ec2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011ec9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011ece  mov     rcx, [rbp+5Fh]; this
0x180011ed2  test    edi, edi
0x180011ed4  js      loc_1800120D3
0x180011eda  mov     eax, [rbp+57h+var_54]
0x180011edd  sub     eax, 1
0x180011ee0  jz      loc_18001206B
0x180011ee6  sub     eax, 1
0x180011ee9  jz      loc_180012051
0x180011eef  cmp     eax, 2
0x180011ef2  jnz     loc_180012085
0x180011ef8  test    rbx, rbx
0x180011efb  jz      short loc_180011F0E
0x180011efd  mov     rcx, rbx
0x180011f00  call    ORCloseHive
0x180011f05  test    eax, eax
0x180011f07  jz      short loc_180011F0E
0x180011f09  mov     rcx, r15
0x180011f0c  int     29h; Win8: RtlFailFast(ecx)
0x180011f0e  mov     al, 4
0x180011f10  jmp     loc_180012028
0x180011f15  mov     [rbp+57h+hLibModule], r14
0x180011f19  mov     [rbp+57h+var_68], r14
0x180011f1d  lea     r9, [rbp+57h+var_68]; __int64 (**)(void)
0x180011f21  lea     r8, [rbp+57h+hLibModule]; HINSTANCE *
0x180011f25  lea     rdx, aGetmobilestore; "GetMobileStoreVersion"
0x180011f2c  call    ?LoadAdjacentLibraryAndFunction@@YAJQEB_WQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; LoadAdjacentLibraryAndFunction(wchar_t const * const,char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x180011f31  mov     ebx, eax
0x180011f33  mov     esi, 3
0x180011f38  test    eax, eax
0x180011f3a  jns     short loc_180011F85
0x180011f3c  mov     [rbp+57h+var_58], eax
0x180011f3f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011f46  test    rcx, rcx
0x180011f49  jz      short loc_180011F85
0x180011f4b  lea     r9, aWszofflinewind; "wszOfflineWinDir and wszOfflineBootDir "...
0x180011f52  mov     r8d, esi
0x180011f55  xor     edx, edx
0x180011f57  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011f5c  lea     rax, [rbp+57h+var_58]
0x180011f60  mov     qword ptr [rbp+57h+var_90], rax
0x180011f64  lea     rax, [rbp+57h+var_90]
0x180011f68  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180011f6d  lea     r9, asc_1801CAFB4; ": {}"
0x180011f74  mov     r8d, esi
0x180011f77  mov     dl, 1
0x180011f79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011f80  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011f85  mov     rcx, [rbp+5Fh]; this
0x180011f89  test    ebx, ebx
0x180011f8b  js      loc_1800120E8
0x180011f91  lea     rcx, [rbp+57h+var_54]
0x180011f95  mov     rax, [rbp+57h+var_68]
0x180011f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f9e  mov     ebx, eax
0x180011fa0  test    eax, eax
0x180011fa2  jns     short loc_180011FED
0x180011fa4  mov     [rbp+57h+var_58], eax
0x180011fa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011fae  test    rcx, rcx
0x180011fb1  jz      short loc_180011FED
0x180011fb3  lea     r9, aCouldNotQueryS_0; "Could not query SxS mobile store versio"...
0x180011fba  mov     r8d, esi
0x180011fbd  xor     edx, edx
0x180011fbf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011fc4  lea     rax, [rbp+57h+var_58]
0x180011fc8  mov     qword ptr [rbp+57h+var_90], rax
0x180011fcc  lea     rax, [rbp+57h+var_90]
0x180011fd0  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180011fd5  lea     r9, asc_1801CAFB4; ": {}"
0x180011fdc  mov     r8d, esi
0x180011fdf  mov     dl, 1
0x180011fe1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011fe8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011fed  mov     rcx, [rbp+5Fh]; this
0x180011ff1  test    ebx, ebx
0x180011ff3  js      loc_1800120FD
0x180011ff9  mov     bl, byte ptr [rbp+57h+var_54]
0x180011ffc  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180012000  test    rcx, rcx
0x180012003  jz      short loc_180012026
0x180012005  call    cs:__imp_FreeLibrary
0x18001200c  nop     dword ptr [rax+rax+00h]
0x180012011  test    eax, eax
0x180012013  jnz     short loc_180012026
0x180012015  call    cs:__imp_GetLastError
0x18001201c  nop     dword ptr [rax+rax+00h]
0x180012021  mov     rcx, r15
0x180012024  int     29h; Win8: RtlFailFast(ecx)
0x180012026  mov     al, bl
0x180012028  mov     rcx, [rbp+57h+var_30]
0x18001202c  xor     rcx, rsp; StackCookie
0x18001202f  call    __security_check_cookie
0x180012034  lea     r11, [rsp+0C0h+var_20]
0x18001203c  mov     rbx, [r11+38h]
0x180012040  mov     rsi, [r11+40h]
0x180012044  mov     rsp, r11
0x180012047  pop     r15
0x180012049  pop     r14
0x18001204b  pop     r12
0x18001204d  pop     rdi
0x18001204e  pop     rbp
0x18001204f  retn
0x180012051  test    rbx, rbx
0x180012054  jz      short loc_180012067
0x180012056  mov     rcx, rbx
0x180012059  call    ORCloseHive
0x18001205e  test    eax, eax
0x180012060  jz      short loc_180012067
0x180012062  mov     rcx, r15
0x180012065  int     29h; Win8: RtlFailFast(ecx)
0x180012067  mov     al, 2
0x180012069  jmp     short loc_180012028
0x18001206b  test    rbx, rbx
0x18001206e  jz      short loc_180012081
0x180012070  mov     rcx, rbx
0x180012073  call    ORCloseHive
0x180012078  test    eax, eax
0x18001207a  jz      short loc_180012081
0x18001207c  mov     rcx, r15
0x18001207f  int     29h; Win8: RtlFailFast(ecx)
0x180012081  mov     al, 1
0x180012083  jmp     short loc_180012028
0x180012085  mov     ecx, 80188305h
0x18001208a  call    ??$EnsureNTSTATUS@J@@YAJJ@Z; EnsureNTSTATUS<long>(long)
0x18001208f  mov     r9d, eax; char *
0x180012092  mov     rcx, [rbp+5Fh]; this
0x180012096  lea     r8, aOnecoreBaseSer_5; "onecore\\base\\servicing\\uapi\\lib\\co"...
0x18001209d  mov     edx, 0A9h; void *
0x1800120a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800120a8  mov     rcx, [rbp+5Fh]; this
0x1800120ac  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800120b3  mov     edx, 0EBh; void *
0x1800120b8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800120be  mov     r9d, ebx; char *
0x1800120c1  lea     r8, aOnecoreBaseSer_5; "onecore\\base\\servicing\\uapi\\lib\\co"...
0x1800120c8  mov     edx, 99h; void *
0x1800120cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800120d3  mov     r9d, edi; char *
0x1800120d6  lea     r8, aOnecoreBaseSer_5; "onecore\\base\\servicing\\uapi\\lib\\co"...
0x1800120dd  mov     edx, 9Eh; void *
0x1800120e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800120e8  mov     r9d, ebx; char *
0x1800120eb  lea     r8, aOnecoreBaseSer_5; "onecore\\base\\servicing\\uapi\\lib\\co"...
0x1800120f2  mov     edx, 8Fh; void *
0x1800120f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800120fd  mov     r9d, ebx; char *
0x180012100  lea     r8, aOnecoreBaseSer_5; "onecore\\base\\servicing\\uapi\\lib\\co"...
0x180012107  mov     edx, 92h; void *
0x18001210c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# CDeviceInfo::PopulateServicingStackVersion(IDeviceInfoGather *)

- ea: `0x1800926fc`
- end: `0x180092cbb`
- name: `?PopulateServicingStackVersion@CDeviceInfo@@AEAAJPEAVIDeviceInfoGather@@@Z`
- size: `1471`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, struct IDeviceInfoGather *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18008bb10`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x180007f68`
- `0x180009750`
- `0x18000aedc`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x18003f554`
- `0x180043dd4`
- `0x180051984`
- `0x18008716c`
- `0x1800926fc`
- `0x180112e48`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180092b64`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180092b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800928b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800929f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800928b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800929f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092c59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092917`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092917`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800928a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800929e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092c49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800928a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800929e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092c49`

## string_xrefs

- `0x18009282c`: `Failed getting win32 path to software hive`
- `0x180092950`: `Failed opening {0}`
- `0x180092801`: `Microsoft\Windows\CurrentVersion\Component Based Servicing\Version`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDeviceInfo::PopulateServicingStackVersion(CDeviceInfo *this, struct IDeviceInfoGather *a2)
{
  __int64 v3; // rbx
  int Win32RegistryPath; // eax
  unsigned int v5; // esi
  __int64 v6; // rdx
  unsigned int v8; // edx
  LSTATUS v9; // esi
  unsigned int v10; // r9d
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  wchar_t *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  wchar_t *v20; // rbx
  unsigned int *phkResult; // [rsp+28h] [rbp-E0h]
  unsigned int *phkResulta; // [rsp+28h] [rbp-E0h]
  unsigned int *phkResultb; // [rsp+28h] [rbp-E0h]
  unsigned int v24[2]; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *v25; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t *v26[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-B0h]
  __int64 v28; // [rsp+68h] [rbp-A0h]
  __int64 v29; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp-88h] BYREF
  wchar_t Str[264]; // [rsp+88h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v28 = -2;
  v3 = (*(__int64 (__fastcall **)(struct IDeviceInfoGather *))(*(_QWORD *)a2 + 56LL))(a2);
  lpSubKey = 0;
  hKey = 0;
  memset_0(Str, 0, 0x208u);
  v25 = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v26);
  CDeviceInfo::AddValuePair(this, v26, 0);
  std::wstring::~wstring(v26);
  *(_OWORD *)v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v26);
  CDeviceInfo::AddValuePair(this, v26, 0);
  std::wstring::~wstring(v26);
  Win32RegistryPath = DeviceContext::GetWin32RegistryPath(
                        v3,
                        0,
                        L"Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Version",
                        &lpSubKey);
  v5 = Win32RegistryPath;
  if ( Win32RegistryPath < 0 )
  {
    LODWORD(v29) = Win32RegistryPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed getting win32 path to software hive");
      *(_QWORD *)v24 = &v29;
      phkResult = v24;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v6,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x884,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)v5,
      (int)phkResult);
    if ( !hKey )
      goto LABEL_9;
    if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      goto LABEL_7;
LABEL_8:
    hKey = 0;
LABEL_9:
    if ( lpSubKey )
      operator delete((void *)(lpSubKey - 4));
    return v5;
  }
  if ( hKey )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180092CBALL);
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v9 < 0 )
    __fastfail(7u);
  if ( v9 )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<AutoScz>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed opening {0}",
        &lpSubKey);
      LODWORD(v29) = (unsigned __int16)v9 | 0x80070000;
      *(_QWORD *)v24 = &v29;
      phkResulta = v24;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v11,
        3,
        ": {0}");
    }
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x887,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
            (const char *)(unsigned int)v9,
            (unsigned int)phkResulta);
    if ( hKey )
    {
      if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
      hKey = 0;
    }
    if ( lpSubKey )
      operator delete((void *)(lpSubKey - 4));
    return v12;
  }
  v13 = CbsRegEnumStringValue(hKey, v8, Str, v10, &v25);
  v5 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v29) = v13;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed getting servicing stack version");
      *(_QWORD *)v24 = &v29;
      phkResultb = v24;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {}");
    }
    v15 = 2189;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)v5,
      (int)phkResultb);
    if ( v25 )
      operator delete(v25 - 4);
    if ( !hKey )
      goto LABEL_9;
    if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
    {
LABEL_7:
      GetLastError();
      __fastfail(7u);
    }
    goto LABEL_8;
  }
  *(_OWORD *)v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v26);
  CDeviceInfo::AddValuePair(this, v26, Str);
  std::wstring::~wstring(v26);
  v16 = wcsrchr(Str, 0x2Eu);
  if ( !v16 )
  {
    v5 = -2147024883;
    LODWORD(v29) = -2147024883;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogPartial<wchar_t [260]>(v18, v17, "Failed extracting the revision from: {0}", Str);
      *(_QWORD *)v24 = &v29;
      phkResultb = v24;
      LOBYTE(v19) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v19,
        3,
        ": {}");
    }
    v15 = 2198;
    goto LABEL_30;
  }
  v20 = v16 + 1;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v26);
  CDeviceInfo::AddValuePair(this, v26, v20);
  std::wstring::~wstring(v26);
  if ( v25 )
    operator delete(v25 - 4);
  if ( hKey )
  {
    if ( ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
    {
      GetLastError();
      __fastfail(7u);
    }
    hKey = 0;
  }
  if ( lpSubKey )
    operator delete((void *)(lpSubKey - 4));
  return 0;
}

```

## disassembly

```asm
0x1800926fc  mov     rax, rsp
0x1800926ff  push    rbp
0x180092700  push    rdi
0x180092701  push    r14
0x180092703  lea     rbp, [rax-1B8h]
0x18009270a  sub     rsp, 2A0h
0x180092711  mov     [rsp+2B0h+var_250], 0FFFFFFFFFFFFFFFEh
0x18009271a  mov     [rax+18h], rbx
0x18009271e  mov     [rax+20h], rsi
0x180092722  mov     rax, cs:__security_cookie
0x180092729  xor     rax, rsp
0x18009272c  mov     [rbp+1B0h+var_20], rax
0x180092733  mov     r14, rcx
0x180092736  mov     rax, [rdx]
0x180092739  mov     rcx, rdx
0x18009273c  mov     rax, [rax+38h]
0x180092740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092745  mov     rbx, rax
0x180092748  mov     [rsp+2B0h+lpSubKey], 0
0x180092751  mov     [rsp+2B0h+hKey], 0
0x18009275a  xor     edx, edx; Val
0x18009275c  mov     r8d, 208h; Size
0x180092762  lea     rcx, [rbp+1B0h+Str]; void *
0x180092766  call    memset_0
0x18009276b  mov     [rsp+2B0h+var_278], 0
0x180092774  xorps   xmm0, xmm0
0x180092777  movups  xmmword ptr [rsp+2B0h+var_278+8], xmm0
0x18009277c  xorps   xmm1, xmm1
0x18009277f  movdqu  xmmword ptr [rsp+2B0h+var_268+8], xmm1
0x180092785  mov     r8d, 15h
0x18009278b  lea     rdx, aServicingstack_0; "ServicingStackVersion"
0x180092792  lea     rcx, [rsp+2B0h+var_278+8]
0x180092797  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18009279c  nop
0x18009279d  xor     r8d, r8d
0x1800927a0  lea     rdx, [rsp+2B0h+var_278+8]
0x1800927a5  mov     rcx, r14
0x1800927a8  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800927ad  nop
0x1800927ae  lea     rcx, [rsp+2B0h+var_278+8]; void *
0x1800927b3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800927b8  xorps   xmm0, xmm0
0x1800927bb  movups  xmmword ptr [rsp+2B0h+var_278+8], xmm0
0x1800927c0  xorps   xmm1, xmm1
0x1800927c3  movdqu  xmmword ptr [rsp+2B0h+var_268+8], xmm1
0x1800927c9  mov     r8d, 16h
0x1800927cf  lea     rdx, aServicingstack_3; "ServicingStackRevision"
0x1800927d6  lea     rcx, [rsp+2B0h+var_278+8]
0x1800927db  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800927e0  nop
0x1800927e1  xor     r8d, r8d
0x1800927e4  lea     rdx, [rsp+2B0h+var_278+8]
0x1800927e9  mov     rcx, r14
0x1800927ec  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x1800927f1  nop
0x1800927f2  lea     rcx, [rsp+2B0h+var_278+8]; void *
0x1800927f7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800927fc  lea     r9, [rsp+2B0h+lpSubKey]
0x180092801  lea     r8, aMicrosoftWindo_5; "Microsoft\\Windows\\CurrentVersion\\Com"...
0x180092808  xor     edx, edx
0x18009280a  mov     rcx, rbx
0x18009280d  call    ?GetWin32RegistryPath@DeviceContext@@QEAAJW4RegistryHive@1@PEB_WPEAVAutoScz@@@Z; DeviceContext::GetWin32RegistryPath(DeviceContext::RegistryHive,wchar_t const *,AutoScz *)
0x180092812  mov     esi, eax
0x180092814  test    eax, eax
0x180092816  jns     loc_1800928EC
0x18009281c  mov     dword ptr [rsp+2B0h+var_248], eax
0x180092820  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092827  test    rcx, rcx
0x18009282a  jz      short loc_18009286E
0x18009282c  lea     r9, aFailedGettingW_4; "Failed getting win32 path to software h"...
0x180092833  mov     ebx, 3
0x180092838  mov     r8d, ebx
0x18009283b  xor     edx, edx
0x18009283d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180092842  lea     rax, [rsp+2B0h+var_248]
0x180092847  mov     qword ptr [rsp+2B0h+var_280], rax
0x18009284c  lea     rax, [rsp+2B0h+var_280]
0x180092851  mov     [rsp+2B0h+phkResult], rax; int
0x180092856  lea     r9, asc_1801CAFB4; ": {}"
0x18009285d  mov     r8d, ebx
0x180092860  mov     dl, 1
0x180092862  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092869  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009286e  mov     rcx, [rbp+1B8h]; this
0x180092875  mov     r9d, esi; char *
0x180092878  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x18009287f  mov     edx, 884h; void *
0x180092884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092889  nop
0x18009288a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18009288f  test    rcx, rcx
0x180092892  jz      short loc_1800928D2
0x180092894  mov     rax, rcx
0x180092897  mov     rdx, 0FFFFFFFF80000000h
0x18009289e  and     rax, rdx
0x1800928a1  cmp     rax, rdx
0x1800928a4  jz      short loc_1800928C9
0x1800928a6  call    cs:__imp_RegCloseKey
0x1800928ad  nop     dword ptr [rax+rax+00h]
0x1800928b2  test    eax, eax
0x1800928b4  jz      short loc_1800928C9
0x1800928b6  call    cs:__imp_GetLastError
0x1800928bd  nop     dword ptr [rax+rax+00h]
0x1800928c2  mov     ecx, 7
0x1800928c7  int     29h; Win8: RtlFailFast(ecx)
0x1800928c9  mov     [rsp+2B0h+hKey], 0
0x1800928d2  mov     rcx, [rsp+2B0h+lpSubKey]
0x1800928d7  test    rcx, rcx
0x1800928da  jz      short loc_1800928E5
0x1800928dc  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800928e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800928e5  mov     eax, esi
0x1800928e7  jmp     loc_180092C88
0x1800928ec  cmp     [rsp+2B0h+hKey], 0
0x1800928f2  jnz     loc_180092CB0
0x1800928f8  lea     rax, [rsp+2B0h+hKey]
0x1800928fd  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180092902  mov     r9d, 20019h; samDesired
0x180092908  xor     r8d, r8d; ulOptions
0x18009290b  mov     rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x180092910  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180092917  call    cs:__imp_RegOpenKeyExW
0x18009291e  nop     dword ptr [rax+rax+00h]
0x180092923  mov     esi, eax
0x180092925  mov     edi, 7
0x18009292a  test    eax, eax
0x18009292c  jns     short loc_180092932
0x18009292e  mov     ecx, edi
0x180092930  int     29h; Win8: RtlFailFast(ecx)
0x180092932  test    esi, esi
0x180092934  jz      loc_180092A26
0x18009293a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092941  test    rcx, rcx
0x180092944  jz      short loc_1800929A6
0x180092946  lea     rax, [rsp+2B0h+lpSubKey]
0x18009294b  mov     [rsp+2B0h+phkResult], rax
0x180092950  lea     r9, aFailedOpening0; "Failed opening {0}"
0x180092957  mov     ebx, 3
0x18009295c  mov     r8d, ebx
0x18009295f  xor     edx, edx
0x180092961  call    ??$LogNumObjects@VAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<AutoScz>(bool,LogAdapter::LogLevel,char const * const,AutoScz const &)
0x180092966  test    esi, esi
0x180092968  jg      short loc_18009296E
0x18009296a  mov     eax, esi
0x18009296c  jmp     short loc_180092976
0x18009296e  movzx   eax, si
0x180092971  or      eax, 80070000h
0x180092976  mov     dword ptr [rsp+2B0h+var_248], eax
0x18009297a  lea     rax, [rsp+2B0h+var_248]
0x18009297f  mov     qword ptr [rsp+2B0h+var_280], rax
0x180092984  lea     rax, [rsp+2B0h+var_280]
0x180092989  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18009298e  lea     r9, a0; ": {0}"
0x180092995  mov     r8d, ebx
0x180092998  mov     dl, 1
0x18009299a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800929a1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800929a6  mov     rcx, [rbp+1B8h]; this
0x1800929ad  mov     r9d, esi; char *
0x1800929b0  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800929b7  mov     edx, 887h; void *
0x1800929bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800929c1  mov     ebx, eax
0x1800929c3  mov     r8, [rsp+2B0h+hKey]
0x1800929c8  test    r8, r8
0x1800929cb  jz      short loc_180092A0C
0x1800929cd  mov     rcx, r8
0x1800929d0  mov     rdx, 0FFFFFFFF80000000h
0x1800929d7  and     rcx, rdx
0x1800929da  cmp     rcx, rdx
0x1800929dd  jz      short loc_180092A03
0x1800929df  mov     rcx, r8; hKey
0x1800929e2  call    cs:__imp_RegCloseKey
0x1800929e9  nop     dword ptr [rax+rax+00h]
0x1800929ee  test    eax, eax
0x1800929f0  jz      short loc_180092A03
0x1800929f2  call    cs:__imp_GetLastError
0x1800929f9  nop     dword ptr [rax+rax+00h]
0x1800929fe  mov     rcx, rdi
0x180092a01  int     29h; Win8: RtlFailFast(ecx)
0x180092a03  mov     [rsp+2B0h+hKey], 0
0x180092a0c  mov     rcx, [rsp+2B0h+lpSubKey]
0x180092a11  test    rcx, rcx
0x180092a14  jz      short loc_180092A1F
0x180092a16  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180092a1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092a1f  mov     eax, ebx
0x180092a21  jmp     loc_180092C88
0x180092a26  lea     rax, [rsp+2B0h+var_278]
0x180092a2b  mov     [rsp+2B0h+phkResult], rax; wchar_t **
0x180092a30  lea     r8, [rbp+1B0h+Str]; wchar_t *
0x180092a34  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180092a39  call    ?CbsRegEnumStringValue@@YAJPEAUHKEY__@@KPEA_WKPEAPEA_W@Z; CbsRegEnumStringValue(HKEY__ *,ulong,wchar_t *,ulong,wchar_t * *)
0x180092a3e  mov     esi, eax
0x180092a40  test    eax, eax
0x180092a42  jns     loc_180092B16
0x180092a48  mov     dword ptr [rsp+2B0h+var_248], eax
0x180092a4c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092a53  test    rcx, rcx
0x180092a56  jz      short loc_180092A9A
0x180092a58  lea     r9, aFailedGettingS; "Failed getting servicing stack version"
0x180092a5f  mov     ebx, 3
0x180092a64  mov     r8d, ebx
0x180092a67  xor     edx, edx
0x180092a69  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180092a6e  lea     rax, [rsp+2B0h+var_248]
0x180092a73  mov     qword ptr [rsp+2B0h+var_280], rax
0x180092a78  lea     rax, [rsp+2B0h+var_280]
0x180092a7d  mov     [rsp+2B0h+phkResult], rax; int
0x180092a82  lea     r9, asc_1801CAFB4; ": {}"
0x180092a89  mov     r8d, ebx
0x180092a8c  mov     dl, 1
0x180092a8e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092a95  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092a9a  mov     edx, 88Dh; void *
0x180092a9f  mov     r9d, esi; char *
0x180092aa2  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x180092aa9  mov     rcx, [rbp+1B8h]; this
0x180092ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092ab5  nop
0x180092ab6  mov     rcx, [rsp+2B0h+var_278]
0x180092abb  test    rcx, rcx
0x180092abe  jz      short loc_180092ACA
0x180092ac0  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180092ac4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180092ac9  nop
0x180092aca  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180092acf  test    rcx, rcx
0x180092ad2  jz      loc_1800928D2
0x180092ad8  mov     rax, rcx
0x180092adb  mov     rdx, 0FFFFFFFF80000000h
0x180092ae2  and     rax, rdx
0x180092ae5  cmp     rax, rdx
0x180092ae8  jz      loc_1800928C9
0x180092aee  call    cs:__imp_RegCloseKey
0x180092af5  nop     dword ptr [rax+rax+00h]
0x180092afa  test    eax, eax
0x180092afc  jz      loc_1800928C9
0x180092b02  call    cs:__imp_GetLastError
0x180092b09  nop     dword ptr [rax+rax+00h]
0x180092b0e  mov     rcx, rdi
0x180092b11  jmp     loc_1800928C7
0x180092b16  xorps   xmm0, xmm0
0x180092b19  movups  xmmword ptr [rsp+2B0h+var_278+8], xmm0
0x180092b1e  xorps   xmm1, xmm1
0x180092b21  movdqu  xmmword ptr [rsp+2B0h+var_268+8], xmm1
0x180092b27  mov     r8d, 15h
0x180092b2d  lea     rdx, aServicingstack_0; "ServicingStackVersion"
0x180092b34  lea     rcx, [rsp+2B0h+var_278+8]
0x180092b39  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180092b3e  nop
0x180092b3f  lea     r8, [rbp+1B0h+Str]
0x180092b43  lea     rdx, [rsp+2B0h+var_278+8]
0x180092b48  mov     rcx, r14
0x180092b4b  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x180092b50  nop
0x180092b51  lea     rcx, [rsp+2B0h+var_278+8]; void *
0x180092b56  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180092b5b  mov     edx, 2Eh ; '.'; Ch
0x180092b60  lea     rcx, [rbp+1B0h+Str]; Str
0x180092b64  call    cs:__imp_wcsrchr
0x180092b6b  nop     dword ptr [rax+rax+00h]
0x180092b70  test    rax, rax
0x180092b73  jnz     short loc_180092BD0
0x180092b75  mov     esi, 8007000Dh
0x180092b7a  mov     dword ptr [rsp+2B0h+var_248], esi
0x180092b7e  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rax; LogAdapter::Logger * LogAdapter::g_Logger
0x180092b85  jz      short loc_180092BC6
0x180092b87  lea     r9, [rbp+1B0h+Str]
0x180092b8b  lea     r8, aFailedExtracti_0; "Failed extracting the revision from: {0"...
0x180092b92  call    ??$LogPartial@$$BY0BAE@_W@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEAY0BAE@$$CB_W@Z; LogAdapter::Logger::LogPartial<wchar_t [260]>(LogAdapter::LogLevel,char const * const,wchar_t const (&)[260])
0x180092b97  lea     rax, [rsp+2B0h+var_248]
0x180092b9c  mov     qword ptr [rsp+2B0h+var_280], rax
0x180092ba1  lea     rax, [rsp+2B0h+var_280]
0x180092ba6  mov     [rsp+2B0h+phkResult], rax
0x180092bab  lea     r9, asc_1801CAFB4; ": {}"
0x180092bb2  mov     r8d, 3
0x180092bb8  mov     dl, 1
0x180092bba  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180092bc1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180092bc6  mov     edx, 896h
0x180092bcb  jmp     loc_180092A9F
0x180092bd0  lea     rbx, [rax+2]
0x180092bd4  xorps   xmm0, xmm0
0x180092bd7  movups  xmmword ptr [rsp+2B0h+var_278+8], xmm0
0x180092bdc  xorps   xmm1, xmm1
0x180092bdf  movdqu  xmmword ptr [rsp+2B0h+var_268+8], xmm1
0x180092be5  mov     r8d, 16h
0x180092beb  lea     rdx, aServicingstack_3; "ServicingStackRevision"
0x180092bf2  lea     rcx, [rsp+2B0h+var_278+8]
0x180092bf7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180092bfc  nop
0x180092bfd  mov     r8, rbx
0x180092c00  lea     rdx, [rsp+2B0h+var_278+8]
0x180092c05  mov     rcx, r14
0x180092c08  call    ?AddValuePair@CDeviceInfo@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; CDeviceInfo::AddValuePair(std::wstring &&,wchar_t const * const)
0x180092c0d  nop
0x180092c0e  lea     rcx, [rsp+2B0h+var_278+8]; void *
0x180092c13  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180092c18  nop
  ... truncated ...
```

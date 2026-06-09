# PluginResourceManager::LoadPluginDataFromRegistry(void)

- ea: `0x1800e8214`
- end: `0x1800e8663`
- name: `?LoadPluginDataFromRegistry@PluginResourceManager@@AEAAJXZ`
- size: `1103`
- prototype: `__int64 __fastcall(PluginResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f4b8`

## callees

- `0x180010e60`
- `0x180012120`
- `0x18002bf00`
- `0x1800555f0`
- `0x180055ac4`
- `0x1800569e0`
- `0x1800758b0`
- `0x180082a00`
- `0x18009f1f0`
- `0x1800a3a38`
- `0x1800aeefc`
- `0x1800b0760`
- `0x1800c7cd0`
- `0x1800e2374`
- `0x1800e8214`
- `0x1800e95f0`
- `0x1800fba00`
- `0x1800fbae4`
- `0x1801244c0`
- `0x18012540e`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e82c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e82fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e82c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e82fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8357`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800e8514`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800e8514`

## string_xrefs

- `0x1800e82d0`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800e831b`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800e8361`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800e8529`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800e857c`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\pluginresourcemanager.cxx`
- `0x1800e82e4`: `PluginResourceData`
- `0x1800e8332`: `PluginResourceData`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall PluginResourceManager::LoadPluginDataFromRegistry(PluginResourceManager *this)
{
  const char *v2; // r9
  const char *v3; // r9
  const char *v5; // r9
  unsigned int *v6; // rdi
  unsigned int *v7; // r14
  unsigned int v8; // esi
  HRESULT v9; // eax
  int v10; // eax
  const wchar_t *v12; // [rsp+20h] [rbp-6D8h]
  unsigned int v13; // [rsp+20h] [rbp-6D8h]
  unsigned int v14; // [rsp+30h] [rbp-6C8h] BYREF
  unsigned int v15[2]; // [rsp+38h] [rbp-6C0h] BYREF
  unsigned int v16[2]; // [rsp+40h] [rbp-6B8h] BYREF
  unsigned int v17[2]; // [rsp+48h] [rbp-6B0h] BYREF
  _BYTE v18[8]; // [rsp+50h] [rbp-6A8h] BYREF
  _BYTE v19[16]; // [rsp+58h] [rbp-6A0h] BYREF
  GUID pclsid; // [rsp+68h] [rbp-690h] BYREF
  _BYTE v21[40]; // [rsp+78h] [rbp-680h] BYREF
  _BYTE v22[192]; // [rsp+A0h] [rbp-658h] BYREF
  _QWORD v23[42]; // [rsp+160h] [rbp-598h] BYREF
  _BYTE v24[192]; // [rsp+2B0h] [rbp-448h] BYREF
  _QWORD v25[42]; // [rsp+370h] [rbp-388h] BYREF
  OLECHAR sz[264]; // [rsp+4C0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6F8h] [rbp+0h]

  wil::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v25);
  v25[0] = &SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::`vftable';
  wil::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v23);
  v23[0] = &SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::`vftable';
  SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::StartActivity((SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry *)v23);
  SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::~LoadPluginDataFromRegistry((SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry *)v23);
  wil::EnterCriticalSection(v18, (char *)this + 152);
  CRegistry::CRegistry((CRegistry *)v24, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Search", 0x20019u, v12);
  if ( GetLastError() )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      v2);
  if ( !(unsigned int)CRegistry::CreateSubKey((CRegistry *)v24, L"PluginResourceData") && GetLastError() != 183 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      v3);
  CRegistry::CRegistry((CRegistry *)v22, (struct CRegistry *)v24, L"PluginResourceData", 0x20019u);
  if ( GetLastError() )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
      v5);
  v6 = (unsigned int *)((char *)this + 200);
  CRegistry::GetValue((CRegistry *)v22, L"MaxProcesses", (unsigned int *)this + 50);
  v7 = (unsigned int *)((char *)this + 196);
  CRegistry::GetValue((CRegistry *)v22, L"ShutoffThreshold", (unsigned int *)this + 49);
  CRegistry::GetValue((CRegistry *)v22, L"PenaltyBoxTimeout", (unsigned int *)this + 51);
  if ( *((_DWORD *)this + 50) > 0xAu )
    *v6 = 10;
  v8 = 0;
  memset_0(sz, 0, 0x208u);
  v14 = 260;
  while ( CRegistry::EnumSubKey((CRegistry *)v22, v8, sz, &v14) )
  {
    CRegistry::CRegistry((CRegistry *)v23, (struct CRegistry *)v22, sz, 0x20019u);
    *(_QWORD *)v15 = 0;
    *(_QWORD *)v16 = 0;
    *(_QWORD *)v17 = 0;
    CRegistry::GetValue((CRegistry *)v23, L"CpuCycles", &v15[1]);
    CRegistry::GetValue((CRegistry *)v23, L"CpuMax", v15);
    CRegistry::GetValue((CRegistry *)v23, L"Memory", v16);
    CRegistry::GetValue((CRegistry *)v23, L"PenaltyBox", &v16[1]);
    CRegistry::GetValue((CRegistry *)v23, L"Duration", v17);
    CRegistry::GetValue((CRegistry *)v23, L"Items", &v17[1]);
    if ( v16[1] >= *v7 )
    {
      pclsid = 0;
      v9 = CLSIDFromString(sz, &pclsid);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          (const char *)(unsigned int)v9,
          v13);
      v10 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(**((_QWORD **)g_pGatheringService + 914) + 88LL))(
              *((_QWORD *)g_pGatheringService + 914),
              &pclsid,
              (*((_QWORD *)g_pGatheringService + 47) + 72LL) & -(__int64)(*((_QWORD *)g_pGatheringService + 47) != 0));
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\pluginresourcemanager.cxx",
          (const char *)(unsigned int)v10,
          v13);
    }
    std::wstring::wstring(v21, sz);
    std::_Hash<std::_Umap_traits<std::wstring,PluginResourceData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,PluginResourceData>>,0>>::emplace<std::wstring,PluginResourceData &>(
      (char *)this + 24,
      v19,
      v21,
      v15);
    ++v8;
    v14 = 260;
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v21);
    CRegistry::~CRegistry((CRegistry *)v23);
  }
  SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::Stop(
    (SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry *)v25,
    *((_DWORD *)this + 10),
    *v6,
    *v7,
    *((_DWORD *)this + 51));
  CRegistry::~CRegistry((CRegistry *)v22);
  CRegistry::~CRegistry((CRegistry *)v24);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v18);
  SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::~LoadPluginDataFromRegistry((SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry *)v25);
  return 0;
}

```

## disassembly

```asm
0x1800e8214  mov     [rsp+arg_8], rbx
0x1800e8219  mov     [rsp+arg_10], rsi
0x1800e821e  push    rdi
0x1800e821f  push    r14
0x1800e8221  push    r15
0x1800e8223  sub     rsp, 6E0h
0x1800e822a  mov     rax, cs:__security_cookie
0x1800e8231  xor     rax, rsp
0x1800e8234  mov     [rsp+6F8h+var_28], rax
0x1800e823c  mov     rbx, rcx
0x1800e823f  lea     rcx, [rsp+6F8h+var_388]; struct wil::details::IFailureCallback *
0x1800e8247  call    ??0?$ActivityBase@VSearchIndexerPluginIsolationLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800e824c  lea     rdi, ??_7LoadPluginDataFromRegistry@SearchIndexerPluginIsolationTelemetry@@6B@; const SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::`vftable'
0x1800e8253  mov     [rsp+6F8h+var_388], rdi
0x1800e825b  lea     rcx, [rsp+6F8h+var_598]; struct wil::details::IFailureCallback *
0x1800e8263  call    ??0?$ActivityBase@VSearchIndexerPluginIsolationLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SearchIndexerPluginIsolationLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800e8268  mov     [rsp+6F8h+var_598], rdi
0x1800e8270  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e8278  call    ?StartActivity@LoadPluginDataFromRegistry@SearchIndexerPluginIsolationTelemetry@@QEAAXXZ; SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::StartActivity(void)
0x1800e827d  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e8285  call    ??1LoadPluginDataFromRegistry@SearchIndexerPluginIsolationTelemetry@@QEAA@XZ; SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::~LoadPluginDataFromRegistry(void)
0x1800e828a  lea     rdx, [rbx+98h]
0x1800e8291  lea     rcx, [rsp+6F8h+var_6A8]
0x1800e8296  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800e829b  nop
0x1800e829c  mov     r9d, 20019h; unsigned int
0x1800e82a2  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows Search"
0x1800e82a9  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800e82b0  lea     rcx, [rsp+6F8h+var_448]; this
0x1800e82b8  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z; CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x1800e82bd  nop
0x1800e82be  mov     rdi, [rsp+6F8h]
0x1800e82c6  call    cs:__imp_GetLastError
0x1800e82cc  test    eax, eax
0x1800e82ce  jz      short loc_1800E82E4
0x1800e82d0  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e82d7  mov     edx, 0ACh; void *
0x1800e82dc  mov     rcx, rdi; this
0x1800e82df  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e82e4  lea     rdx, aPluginresource; "PluginResourceData"
0x1800e82eb  lea     rcx, [rsp+6F8h+var_448]; this
0x1800e82f3  call    ?CreateSubKey@CRegistry@@UEAAHPEB_W@Z; CRegistry::CreateSubKey(wchar_t const *)
0x1800e82f8  test    eax, eax
0x1800e82fa  jnz     short loc_1800E830D
0x1800e82fc  call    cs:__imp_GetLastError
0x1800e8302  cmp     eax, 0B7h
0x1800e8307  jz      short loc_1800E830D
0x1800e8309  mov     al, 1
0x1800e830b  jmp     short loc_1800E830F
0x1800e830d  xor     al, al
0x1800e830f  mov     rcx, [rsp+6F8h]; this
0x1800e8317  test    al, al
0x1800e8319  jz      short loc_1800E832C
0x1800e831b  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e8322  mov     edx, 0AFh; void *
0x1800e8327  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e832c  mov     r9d, 20019h; unsigned int
0x1800e8332  lea     r8, aPluginresource; "PluginResourceData"
0x1800e8339  lea     rdx, [rsp+6F8h+var_448]; struct CRegistry *
0x1800e8341  lea     rcx, [rsp+6F8h+var_658]; this
0x1800e8349  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x1800e834e  nop
0x1800e834f  mov     rdi, [rsp+6F8h]
0x1800e8357  call    cs:__imp_GetLastError
0x1800e835d  test    eax, eax
0x1800e835f  jz      short loc_1800E8375
0x1800e8361  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e8368  mov     edx, 0B2h; void *
0x1800e836d  mov     rcx, rdi; this
0x1800e8370  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e8375  lea     rdi, [rbx+0C8h]
0x1800e837c  mov     r8, rdi; unsigned int *
0x1800e837f  lea     rdx, aMaxprocesses; "MaxProcesses"
0x1800e8386  lea     rcx, [rsp+6F8h+var_658]; this
0x1800e838e  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e8393  lea     r14, [rbx+0C4h]
0x1800e839a  mov     r8, r14; unsigned int *
0x1800e839d  lea     rdx, aShutoffthresho; "ShutoffThreshold"
0x1800e83a4  lea     rcx, [rsp+6F8h+var_658]; this
0x1800e83ac  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e83b1  lea     r15, [rbx+0CCh]
0x1800e83b8  mov     r8, r15; unsigned int *
0x1800e83bb  lea     rdx, aPenaltyboxtime; "PenaltyBoxTimeout"
0x1800e83c2  lea     rcx, [rsp+6F8h+var_658]; this
0x1800e83ca  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e83cf  cmp     dword ptr [rdi], 0Ah
0x1800e83d2  jbe     short loc_1800E83DA
0x1800e83d4  mov     dword ptr [rdi], 0Ah
0x1800e83da  xor     esi, esi
0x1800e83dc  xor     edx, edx; Val
0x1800e83de  mov     r8d, 208h; Size
0x1800e83e4  lea     rcx, [rsp+6F8h+sz]; void *
0x1800e83ec  call    memset_0
0x1800e83f1  mov     [rsp+6F8h+var_6C8], 104h
0x1800e83f9  lea     r9, [rsp+6F8h+var_6C8]; unsigned int *
0x1800e83fe  lea     r8, [rsp+6F8h+sz]; wchar_t *
0x1800e8406  mov     edx, esi; unsigned int
0x1800e8408  lea     rcx, [rsp+6F8h+var_658]; this
0x1800e8410  call    ?EnumSubKey@CRegistry@@QEAAHIPEA_WPEAK@Z; CRegistry::EnumSubKey(uint,wchar_t *,ulong *)
0x1800e8415  test    eax, eax
0x1800e8417  jz      loc_1800E85DF
0x1800e841d  mov     r9d, 20019h; unsigned int
0x1800e8423  lea     r8, [rsp+6F8h+sz]; wchar_t *
0x1800e842b  lea     rdx, [rsp+6F8h+var_658]; struct CRegistry *
0x1800e8433  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e843b  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x1800e8440  nop
0x1800e8441  mov     qword ptr [rsp+6F8h+var_6C0], 0
0x1800e844a  mov     qword ptr [rsp+6F8h+var_6B8], 0
0x1800e8453  mov     qword ptr [rsp+6F8h+var_6B0], 0
0x1800e845c  lea     r8, [rsp+6F8h+var_6C0+4]; unsigned int *
0x1800e8461  lea     rdx, aCpucycles; "CpuCycles"
0x1800e8468  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e8470  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e8475  lea     r8, [rsp+6F8h+var_6C0]; unsigned int *
0x1800e847a  lea     rdx, aCpumax; "CpuMax"
0x1800e8481  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e8489  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e848e  lea     r8, [rsp+6F8h+var_6B8]; unsigned int *
0x1800e8493  lea     rdx, aMemory; "Memory"
0x1800e849a  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e84a2  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e84a7  lea     r8, [rsp+6F8h+var_6B8+4]; unsigned int *
0x1800e84ac  lea     rdx, aPenaltybox; "PenaltyBox"
0x1800e84b3  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e84bb  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e84c0  lea     r8, [rsp+6F8h+var_6B0]; unsigned int *
0x1800e84c5  lea     rdx, aDuration; "Duration"
0x1800e84cc  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e84d4  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e84d9  lea     r8, [rsp+6F8h+var_6B0+4]; unsigned int *
0x1800e84de  lea     rdx, aItems; "Items"
0x1800e84e5  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e84ed  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z; CRegistry::GetValue(wchar_t const *,ulong *)
0x1800e84f2  mov     eax, [r14]
0x1800e84f5  cmp     [rsp+6F8h+var_6B8+4], eax
0x1800e84f9  jb      loc_1800E858D
0x1800e84ff  xorps   xmm0, xmm0
0x1800e8502  movups  xmmword ptr [rsp+6F8h+pclsid.Data1], xmm0
0x1800e8507  lea     rdx, [rsp+6F8h+pclsid]; pclsid
0x1800e850c  lea     rcx, [rsp+6F8h+sz]; lpsz
0x1800e8514  call    cs:__imp_CLSIDFromString
0x1800e851a  mov     rcx, [rsp+6F8h]; this
0x1800e8522  test    eax, eax
0x1800e8524  jns     short loc_1800E853A
0x1800e8526  mov     r9d, eax; char *
0x1800e8529  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e8530  mov     edx, 0D6h; void *
0x1800e8535  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e853a  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800e8541  mov     rcx, [rax+1C90h]
0x1800e8548  mov     rdx, [rax+178h]
0x1800e854f  mov     r9, [rcx]
0x1800e8552  lea     rax, [rdx+48h]
0x1800e8556  neg     rdx
0x1800e8559  sbb     r8, r8
0x1800e855c  and     r8, rax
0x1800e855f  lea     rdx, [rsp+6F8h+pclsid]
0x1800e8564  mov     rax, [r9+58h]
0x1800e8568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e856d  mov     rcx, [rsp+6F8h]; this
0x1800e8575  test    eax, eax
0x1800e8577  jns     short loc_1800E858D
0x1800e8579  mov     r9d, eax; char *
0x1800e857c  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800e8583  mov     edx, 0D7h; void *
0x1800e8588  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e858d  lea     rdx, [rsp+6F8h+sz]
0x1800e8595  lea     rcx, [rsp+6F8h+var_680]
0x1800e859a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800e859f  nop
0x1800e85a0  lea     rcx, [rbx+18h]
0x1800e85a4  lea     r9, [rsp+6F8h+var_6C0]
0x1800e85a9  lea     r8, [rsp+6F8h+var_680]
0x1800e85ae  lea     rdx, [rsp+6F8h+var_6A0]
0x1800e85b3  call    ??$emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUPluginResourceData@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginResourceData@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginResourceData@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UPluginResourceData@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAUPluginResourceData@@@Z; std::_Hash<std::_Umap_traits<std::wstring,PluginResourceData,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,PluginResourceData>>,0>>::emplace<std::wstring,PluginResourceData &>(std::wstring &&,PluginResourceData &)
0x1800e85b8  inc     esi
0x1800e85ba  mov     [rsp+6F8h+var_6C8], 104h
0x1800e85c2  lea     rcx, [rsp+6F8h+var_680]; this
0x1800e85c7  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e85cc  nop
0x1800e85cd  lea     rcx, [rsp+6F8h+var_598]; this
0x1800e85d5  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800e85da  jmp     loc_1800E83F9
0x1800e85df  mov     eax, [r15]
0x1800e85e2  mov     [rsp+6F8h+var_6D8], eax; unsigned int
0x1800e85e6  mov     r9d, [r14]; unsigned int
0x1800e85e9  mov     r8d, [rdi]; unsigned int
0x1800e85ec  mov     edx, [rbx+28h]; unsigned int
0x1800e85ef  lea     rcx, [rsp+6F8h+var_388]; this
0x1800e85f7  call    ?Stop@LoadPluginDataFromRegistry@SearchIndexerPluginIsolationTelemetry@@QEAAXKKKK@Z; SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::Stop(ulong,ulong,ulong,ulong)
0x1800e85fc  nop
0x1800e85fd  lea     rcx, [rsp+6F8h+var_658]; this
0x1800e8605  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800e860a  nop
0x1800e860b  lea     rcx, [rsp+6F8h+var_448]; this
0x1800e8613  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800e8618  nop
0x1800e8619  lea     rcx, [rsp+6F8h+var_6A8]
0x1800e861e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800e8623  nop
0x1800e8624  lea     rcx, [rsp+6F8h+var_388]; this
0x1800e862c  call    ??1LoadPluginDataFromRegistry@SearchIndexerPluginIsolationTelemetry@@QEAA@XZ; SearchIndexerPluginIsolationTelemetry::LoadPluginDataFromRegistry::~LoadPluginDataFromRegistry(void)
0x1800e8631  xor     eax, eax
0x1800e8633  jmp     short loc_1800E8639
0x1800e8635  mov     eax, [rsp+6F8h+var_6C8]
0x1800e8639  mov     rcx, [rsp+6F8h+var_28]
0x1800e8641  xor     rcx, rsp; StackCookie
0x1800e8644  call    __security_check_cookie
0x1800e8649  lea     r11, [rsp+6F8h+var_18]
0x1800e8651  mov     rbx, [r11+28h]
0x1800e8655  mov     rsi, [r11+30h]
0x1800e8659  mov     rsp, r11
0x1800e865c  pop     r15
0x1800e865e  pop     r14
0x1800e8660  pop     rdi
0x1800e8661  retn
```

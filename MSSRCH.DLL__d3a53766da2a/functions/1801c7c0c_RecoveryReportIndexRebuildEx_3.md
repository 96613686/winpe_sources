# RecoveryReportIndexRebuildEx_3

- ea: `0x1801c7c0c`
- end: `0x1801c8003`
- name: `RecoveryReportIndexRebuildEx_3`
- size: `1015`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180045fe0`
- `0x1800cb940`

## callees

- `0x18000ee60`
- `0x18000f880`
- `0x180012120`
- `0x18002751c`
- `0x180052460`
- `0x180056b90`
- `0x18005e788`
- `0x18009491c`
- `0x1800a3a38`
- `0x1800b827c`
- `0x1800b837c`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800e1320`
- `0x1800e4710`
- `0x18010839c`
- `0x1801244c0`
- `0x1801249ec`
- `0x18013dd98`
- `0x180141a94`
- `0x1801c56ec`
- `0x1801c7c0c`
- `0x1801ca410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801c7f0d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801c7f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801c7fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801c7fa1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801c7dc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801c7dc4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801c7c98`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801c7c98`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801c7e11`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801c7f96`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801c7e11`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801c7f96`

## string_xrefs

- `0x1801c7e03`: `SetupCompletedSuccessfully`
- `0x1801c7dd9`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801c7e26`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801c7ec1`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecoveryReportIndexRebuildEx_3(
        __int64 a1,
        struct CEventLog *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  const wchar_t *v9; // rcx
  unsigned int v10; // r9d
  const wchar_t *Catalog; // rbx
  const size_t *v12; // rdx
  HKEY *phkResult; // rax
  const WCHAR *v14; // rdx
  unsigned int Key; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // kr10_8
  wchar_t *v21; // rax
  unsigned int v22; // ebx
  __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  void *v26; // r11
  int v28; // eax
  bool v29; // sf
  unsigned int dwOptions; // [rsp+20h] [rbp-A28h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A28h]
  HKEY hkey; // [rsp+50h] [rbp-9F8h] BYREF
  int pvData; // [rsp+58h] [rbp-9F0h] BYREF
  HANDLE v34[2]; // [rsp+60h] [rbp-9E8h] BYREF
  int v35; // [rsp+70h] [rbp-9D8h] BYREF
  __int64 v36; // [rsp+78h] [rbp-9D0h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-9C8h] BYREF
  _BYTE v38[8]; // [rsp+A0h] [rbp-9A8h] BYREF
  _BYTE v39[160]; // [rsp+A8h] [rbp-9A0h] BYREF
  _BYTE v40[2248]; // [rsp+148h] [rbp-900h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A48h] [rbp+0h]

  v35 = 0;
  v36 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v35);
  LogIndexCorruptionEx_1((_DWORD)a2, 0, 0, a5, a6, a7, a8);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    (PINIT_ONCE_FN)_lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = (const wchar_t *)PerUserCatalogNameForCorruption::GetCatalog();
    v34[0] = (HANDLE)Catalog;
    if ( a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v38, a2);
      v12 = &cchOriginalDestLength;
      if ( Catalog )
        v12 = (const size_t *)Catalog;
      CLMString::operator=(v39, v12);
      CLMString::operator=(v40, &cchOriginalDestLength);
      CSearchEventEntry::SetError((CSearchEventEntry *)v38, -1073473535);
      CSearchEventEntry::ReportError((CSearchEventEntry *)v38, 0xC0001B80, L"The catalog is corrupt", 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v38);
    }
    try
    {
      std::wstring::wstring(lpSubKey, Catalog);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v14 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v14 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v14, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v16 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v16 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v16,
          dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpSubKey);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        253,
        "onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h");
    }
    v17 = -1;
    do
      ++v17;
    while ( Catalog[v17] );
    v18 = v17 + 1;
    v20 = v17 + 1;
    v19 = 2 * (v17 + 1);
    if ( !is_mul_ok(v20, 2u) )
      v19 = -1;
    v21 = (wchar_t *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v21;
    if ( !v21 )
    {
      v22 = -2147024882;
      v23 = 2147942414LL;
      v24 = 257;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v23,
        dwOptionsa);
      std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v35);
      return v22;
    }
    v25 = StringCchCopyW(v21, v18, Catalog);
    v22 = v25;
    if ( v25 < 0 )
    {
      v23 = (unsigned int)v25;
      v24 = 259;
      goto LABEL_22;
    }
    hkey = 0;
    v34[0] = CreateThread(0, 0, ResetUserCatalog, v26, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v34);
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
  }
  else
  {
    hkey = 0;
    v28 = WSearchRegOpenKeyEx(v9, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v10, 0xF003Fu, &hkey);
    v29 = v28 < 0;
    if ( v28 > 0 )
      v29 = 1;
    if ( !v29 )
    {
      pvData = 3;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      ShutdownSelf_1(a2, (__int64)L"The catalog is corrupt");
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v35);
  return 0;
}

```

## disassembly

```asm
0x1801c7c0c  push    rbx
0x1801c7c0e  push    rsi
0x1801c7c0f  push    rdi
0x1801c7c10  push    r14
0x1801c7c12  push    r15
0x1801c7c14  sub     rsp, 0A20h
0x1801c7c1b  mov     rax, cs:__security_cookie
0x1801c7c22  xor     rax, rsp
0x1801c7c25  mov     [rsp+0A48h+var_38], rax
0x1801c7c2d  mov     r15, rdx
0x1801c7c30  mov     edi, [rsp+0A48h+arg_28]
0x1801c7c37  mov     rbx, [rsp+0A48h+arg_30]
0x1801c7c3f  xor     esi, esi
0x1801c7c41  mov     [rsp+0A48h+var_9D8], esi
0x1801c7c45  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801c7c49  mov     [rsp+0A48h+var_9D0], r14
0x1801c7c4e  lea     rcx, [rsp+0A48h+var_9D8]; this
0x1801c7c53  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1801c7c58  nop
0x1801c7c59  mov     rax, [rsp+0A48h+arg_38]
0x1801c7c61  mov     [rsp+0A48h+lpSecurityAttributes], rax
0x1801c7c66  mov     qword ptr [rsp+0A48h+samDesired], rbx
0x1801c7c6b  mov     [rsp+0A48h+dwOptions], edi
0x1801c7c6f  mov     r9d, [rsp+0A48h+arg_20]
0x1801c7c77  xor     r8d, r8d
0x1801c7c7a  xor     edx, edx
0x1801c7c7c  mov     rcx, r15
0x1801c7c7f  call    LogIndexCorruptionEx_1
0x1801c7c84  xor     r9d, r9d; Context
0x1801c7c87  xor     r8d, r8d; Parameter
0x1801c7c8a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801c7c91  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1801c7c98  call    cs:__imp_InitOnceExecuteOnce
0x1801c7c9e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, sil; bool g_isPerUserCatalogEnabled
0x1801c7ca5  jz      loc_1801C7F31
0x1801c7cab  call    PerUserCatalogNameForCorruption__GetCatalog
0x1801c7cb0  test    rax, rax
0x1801c7cb3  jz      loc_1801C7F31
0x1801c7cb9  call    PerUserCatalogNameForCorruption__GetCatalog
0x1801c7cbe  mov     rbx, rax
0x1801c7cc1  mov     [rsp+0A48h+var_9E8], rax
0x1801c7cc6  test    r15, r15
0x1801c7cc9  jz      short loc_1801C7D48
0x1801c7ccb  mov     rdx, r15; struct CEventLog *
0x1801c7cce  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1801c7cd6  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1801c7cdb  nop
0x1801c7cdc  lea     rdx, cchOriginalDestLength
0x1801c7ce3  test    rbx, rbx
0x1801c7ce6  cmovnz  rdx, rbx
0x1801c7cea  lea     rcx, [rsp+0A48h+var_9A0]
0x1801c7cf2  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801c7cf7  lea     rdx, cchOriginalDestLength
0x1801c7cfe  lea     rcx, [rsp+0A48h+var_900]
0x1801c7d06  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801c7d0b  mov     edx, 0C0041801h; int
0x1801c7d10  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1801c7d18  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1801c7d1d  xor     r9d, r9d
0x1801c7d20  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x1801c7d27  mov     edx, 0C0001B80h; unsigned int
0x1801c7d2c  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1801c7d34  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1801c7d39  nop
0x1801c7d3a  lea     rcx, [rsp+0A48h+var_9A8]; this
0x1801c7d42  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1801c7d47  nop
0x1801c7d48  mov     rdx, rbx
0x1801c7d4b  lea     rcx, [rsp+0A48h+lpSubKey]
0x1801c7d53  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801c7d58  nop
0x1801c7d59  mov     r8d, 22h ; '"'
0x1801c7d5f  lea     rdx, aSoftwareMicros_14; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1801c7d66  lea     rcx, [rsp+0A48h+lpSubKey]; Src
0x1801c7d6e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801c7d73  mov     [rsp+0A48h+hkey], rsi
0x1801c7d78  lea     rcx, [rsp+0A48h+hkey]
0x1801c7d7d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801c7d82  lea     rdx, [rsp+0A48h+lpSubKey]
0x1801c7d8a  cmp     [rsp+0A48h+var_9B0], 7
0x1801c7d93  cmova   rdx, [rsp+0A48h+lpSubKey]; lpSubKey
0x1801c7d9c  mov     [rsp+0A48h+lpdwDisposition], rsi; lpdwDisposition
0x1801c7da1  mov     [rsp+0A48h+phkResult], rax; phkResult
0x1801c7da6  mov     [rsp+0A48h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1801c7dab  mov     [rsp+0A48h+samDesired], 0F003Fh; samDesired
0x1801c7db3  mov     [rsp+0A48h+dwOptions], esi; unsigned int
0x1801c7db7  xor     r9d, r9d; lpClass
0x1801c7dba  xor     r8d, r8d; Reserved
0x1801c7dbd  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1801c7dc4  call    cs:__imp_RegCreateKeyExW
0x1801c7dca  mov     rcx, [rsp+0A48h]; this
0x1801c7dd2  test    eax, eax
0x1801c7dd4  jz      short loc_1801C7DEA
0x1801c7dd6  mov     r9d, eax; char *
0x1801c7dd9  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801c7de0  mov     edx, 0F7h; void *
0x1801c7de5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801c7dea  mov     [rsp+0A48h+pvData], esi
0x1801c7dee  mov     r9d, 4; dwType
0x1801c7df4  mov     [rsp+0A48h+samDesired], r9d; cbData
0x1801c7df9  lea     rax, [rsp+0A48h+pvData]
0x1801c7dfe  mov     qword ptr [rsp+0A48h+dwOptions], rax; unsigned int
0x1801c7e03  lea     r8, pszValue; "SetupCompletedSuccessfully"
0x1801c7e0a  xor     edx, edx; pszSubKey
0x1801c7e0c  mov     rcx, [rsp+0A48h+hkey]; hkey
0x1801c7e11  call    cs:__imp_SHSetValueW
0x1801c7e17  mov     rcx, [rsp+0A48h]; this
0x1801c7e1f  test    eax, eax
0x1801c7e21  jz      short loc_1801C7E38
0x1801c7e23  mov     r9d, eax; char *
0x1801c7e26  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801c7e2d  mov     edx, 0FBh; void *
0x1801c7e32  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801c7e38  lea     rcx, [rsp+0A48h+hkey]
0x1801c7e3d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801c7e42  nop
0x1801c7e43  lea     rcx, [rsp+0A48h+lpSubKey]; this
0x1801c7e4b  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1801c7e50  nop
0x1801c7e51  jmp     short loc_1801C7E5E
0x1801c7e53  xor     esi, esi
0x1801c7e55  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801c7e59  mov     rbx, [rsp+0A48h+var_9E8]
0x1801c7e5e  mov     rax, r14
0x1801c7e61  inc     rax
0x1801c7e64  cmp     [rbx+rax*2], si
0x1801c7e68  jnz     short loc_1801C7E61
0x1801c7e6a  lea     rdi, [rax+1]
0x1801c7e6e  mov     eax, 2
0x1801c7e73  mul     rdi
0x1801c7e76  cmovb   rax, r14
0x1801c7e7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801c7e81  mov     rcx, rax; unsigned __int64
0x1801c7e84  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801c7e89  mov     r11, rax
0x1801c7e8c  mov     [rsp+0A48h+hkey], rax
0x1801c7e91  test    rax, rax
0x1801c7e94  jnz     short loc_1801C7EA5
0x1801c7e96  mov     ebx, 8007000Eh
0x1801c7e9b  mov     r9d, ebx
0x1801c7e9e  mov     edx, 101h
0x1801c7ea3  jmp     short loc_1801C7EC1
0x1801c7ea5  mov     r8, rbx; wchar_t *
0x1801c7ea8  mov     rdx, rdi; unsigned __int64
0x1801c7eab  mov     rcx, r11; wchar_t *
0x1801c7eae  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1801c7eb3  mov     ebx, eax
0x1801c7eb5  test    eax, eax
0x1801c7eb7  jns     short loc_1801C7EF1
0x1801c7eb9  mov     r9d, eax; char *
0x1801c7ebc  mov     edx, 103h; void *
0x1801c7ec1  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801c7ec8  mov     rcx, [rsp+0A48h]; this
0x1801c7ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c7ed5  lea     rcx, [rsp+0A48h+hkey]
0x1801c7eda  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1801c7edf  nop
0x1801c7ee0  lea     rcx, [rsp+0A48h+var_9D8]; this
0x1801c7ee5  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801c7eea  mov     eax, ebx
0x1801c7eec  jmp     loc_1801C7FE4
0x1801c7ef1  mov     [rsp+0A48h+hkey], rsi
0x1801c7ef6  mov     qword ptr [rsp+0A48h+samDesired], rsi; lpThreadId
0x1801c7efb  mov     [rsp+0A48h+dwOptions], esi; dwCreationFlags
0x1801c7eff  mov     r9, r11; lpParameter
0x1801c7f02  lea     r8, ResetUserCatalog; lpStartAddress
0x1801c7f09  xor     edx, edx; dwStackSize
0x1801c7f0b  xor     ecx, ecx; lpThreadAttributes
0x1801c7f0d  call    cs:__imp_CreateThread
0x1801c7f13  mov     [rsp+0A48h+var_9E8], rax
0x1801c7f18  lea     rcx, [rsp+0A48h+var_9E8]
0x1801c7f1d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c7f22  lea     rcx, [rsp+0A48h+hkey]
0x1801c7f27  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1801c7f2c  jmp     loc_1801C7FD8
0x1801c7f31  mov     [rsp+0A48h+hkey], rsi
0x1801c7f36  lea     rax, [rsp+0A48h+hkey]
0x1801c7f3b  mov     qword ptr [rsp+0A48h+samDesired], rax; HKEY *
0x1801c7f40  mov     [rsp+0A48h+dwOptions], 0F003Fh; unsigned int
0x1801c7f48  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x1801c7f4f  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1801c7f56  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1801c7f5b  test    eax, eax
0x1801c7f5d  jle     short loc_1801C7F69
0x1801c7f5f  movzx   eax, ax
0x1801c7f62  or      eax, 80070000h
0x1801c7f67  test    eax, eax
0x1801c7f69  js      short loc_1801C7FA7
0x1801c7f6b  mov     [rsp+0A48h+pvData], 3
0x1801c7f73  mov     r9d, 4; dwType
0x1801c7f79  mov     [rsp+0A48h+samDesired], r9d; cbData
0x1801c7f7e  lea     rax, [rsp+0A48h+pvData]
0x1801c7f83  mov     qword ptr [rsp+0A48h+dwOptions], rax; pvData
0x1801c7f88  lea     r8, aRebuildindex; "RebuildIndex"
0x1801c7f8f  xor     edx, edx; pszSubKey
0x1801c7f91  mov     rcx, [rsp+0A48h+hkey]; hkey
0x1801c7f96  call    cs:__imp_SHSetValueW
0x1801c7f9c  mov     rcx, [rsp+0A48h+hkey]; hKey
0x1801c7fa1  call    cs:__imp_RegCloseKey
0x1801c7fa7  cmp     cs:?g_fStopLogged@@3HA, esi; int g_fStopLogged
0x1801c7fad  jnz     short loc_1801C7FD8
0x1801c7faf  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x1801c7fb6  mov     qword ptr [rsp+0A48h+dwOptions], rax; __int64
0x1801c7fbb  mov     r9d, 0C0041801h
0x1801c7fc1  xor     r8d, r8d
0x1801c7fc4  xor     edx, edx
0x1801c7fc6  mov     rcx, r15; struct CEventLog *
0x1801c7fc9  call    ShutdownSelf_1
0x1801c7fce  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1801c7fd8  lea     rcx, [rsp+0A48h+var_9D8]; this
0x1801c7fdd  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801c7fe2  xor     eax, eax
0x1801c7fe4  mov     rcx, [rsp+0A48h+var_38]
0x1801c7fec  xor     rcx, rsp; StackCookie
0x1801c7fef  call    __security_check_cookie
0x1801c7ff4  add     rsp, 0A20h
0x1801c7ffb  pop     r15
0x1801c7ffd  pop     r14
0x1801c7fff  pop     rdi
0x1801c8000  pop     rsi
0x1801c8001  pop     rbx
0x1801c8002  retn
```

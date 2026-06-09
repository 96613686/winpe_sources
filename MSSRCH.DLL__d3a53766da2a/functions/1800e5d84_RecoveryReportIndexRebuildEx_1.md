# RecoveryReportIndexRebuildEx_1

- ea: `0x1800e5d84`
- end: `0x1800e6161`
- name: `RecoveryReportIndexRebuildEx_1`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007bee0`

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
- `0x1800e5d84`
- `0x18010839c`
- `0x1801244c0`
- `0x1801249ec`
- `0x18013dd98`
- `0x180141a94`
- `0x1801ca410`
- `0x1801e7ec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e6060`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e6060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e60f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e60f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e5f1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e5f1a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e5df1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e5df1`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e5f67`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e60e9`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e5f67`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e60e9`

## string_xrefs

- `0x1800e5f59`: `SetupCompletedSuccessfully`
- `0x1800e5f2f`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800e5f7c`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800e6014`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecoveryReportIndexRebuildEx_1(__int64 a1, struct CEventLog *a2, __int64 a3, const size_t *a4)
{
  const wchar_t *v7; // rcx
  unsigned int v8; // r9d
  const wchar_t *Catalog; // rdi
  const size_t *v10; // rdx
  HKEY *phkResult; // rax
  const WCHAR *v12; // rdx
  unsigned int Key; // eax
  unsigned int v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // kr10_8
  wchar_t *v19; // rax
  unsigned int v20; // edi
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  void *v24; // r11
  int v26; // eax
  bool v27; // sf
  unsigned int dwOptions; // [rsp+20h] [rbp-A18h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A18h]
  HKEY hkey; // [rsp+50h] [rbp-9E8h] BYREF
  int pvData; // [rsp+58h] [rbp-9E0h] BYREF
  HANDLE Thread; // [rsp+60h] [rbp-9D8h] BYREF
  int v33; // [rsp+68h] [rbp-9D0h] BYREF
  __int64 v34; // [rsp+70h] [rbp-9C8h]
  LPCWSTR lpSubKey[5]; // [rsp+78h] [rbp-9C0h] BYREF
  _BYTE v36[8]; // [rsp+A0h] [rbp-998h] BYREF
  _BYTE v37[160]; // [rsp+A8h] [rbp-990h] BYREF
  _BYTE v38[2248]; // [rsp+148h] [rbp-8F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A38h] [rbp+0h]

  v33 = 0;
  v34 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v33);
  LogIndexCorruptionEx_2(a2, a3, a4);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    (PINIT_ONCE_FN)_lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = (const wchar_t *)PerUserCatalogNameForCorruption::GetCatalog();
    Thread = (HANDLE)Catalog;
    if ( a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v36, a2);
      v10 = &cchOriginalDestLength;
      if ( Catalog )
        v10 = (const size_t *)Catalog;
      CLMString::operator=(v37, v10);
      if ( !a4 )
        a4 = &cchOriginalDestLength;
      CLMString::operator=(v38, a4);
      CSearchEventEntry::SetError((CSearchEventEntry *)v36, -1073473535);
      CSearchEventEntry::ReportError((CSearchEventEntry *)v36, 0xC0001B80, L"The catalog is corrupt", 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v36);
    }
    try
    {
      std::wstring::wstring(lpSubKey, Catalog);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v12 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v12 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v12, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v14 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v14,
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
    v15 = -1;
    do
      ++v15;
    while ( Catalog[v15] );
    v16 = v15 + 1;
    v18 = v15 + 1;
    v17 = 2 * (v15 + 1);
    if ( !is_mul_ok(v18, 2u) )
      v17 = -1;
    v19 = (wchar_t *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v19;
    if ( !v19 )
    {
      v20 = -2147024882;
      v21 = 2147942414LL;
      v22 = 257;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v21,
        dwOptionsa);
      std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v33);
      return v20;
    }
    v23 = StringCchCopyW(v19, v16, Catalog);
    v20 = v23;
    if ( v23 < 0 )
    {
      v21 = (unsigned int)v23;
      v22 = 259;
      goto LABEL_24;
    }
    hkey = 0;
    Thread = CreateThread(0, 0, ResetUserCatalog, v24, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
  }
  else
  {
    hkey = 0;
    v26 = WSearchRegOpenKeyEx(v7, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v8, 0xF003Fu, &hkey);
    v27 = v26 < 0;
    if ( v26 > 0 )
      v27 = 1;
    if ( !v27 )
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
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v33);
  return 0;
}

```

## disassembly

```asm
0x1800e5d84  mov     [rsp+arg_0], rbx
0x1800e5d89  mov     [rsp+arg_8], rsi
0x1800e5d8e  push    rdi
0x1800e5d8f  push    r14
0x1800e5d91  push    r15
0x1800e5d93  sub     rsp, 0A20h
0x1800e5d9a  mov     rax, cs:__security_cookie
0x1800e5da1  xor     rax, rsp
0x1800e5da4  mov     [rsp+0A38h+var_28], rax
0x1800e5dac  mov     r15, r9
0x1800e5daf  mov     rdi, r8
0x1800e5db2  mov     r14, rdx
0x1800e5db5  xor     ebx, ebx
0x1800e5db7  mov     [rsp+0A38h+var_9D0], ebx
0x1800e5dbb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e5dbf  mov     [rsp+0A38h+var_9C8], rsi
0x1800e5dc4  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1800e5dc9  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1800e5dce  nop
0x1800e5dcf  mov     r8, r15
0x1800e5dd2  mov     rdx, rdi
0x1800e5dd5  mov     rcx, r14
0x1800e5dd8  call    LogIndexCorruptionEx_2
0x1800e5ddd  xor     r9d, r9d; Context
0x1800e5de0  xor     r8d, r8d; Parameter
0x1800e5de3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800e5dea  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800e5df1  call    cs:__imp_InitOnceExecuteOnce
0x1800e5df7  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1800e5dfd  jz      loc_1800E6084
0x1800e5e03  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800e5e08  test    rax, rax
0x1800e5e0b  jz      loc_1800E6084
0x1800e5e11  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800e5e16  mov     rdi, rax
0x1800e5e19  mov     [rsp+0A38h+var_9D8], rax
0x1800e5e1e  test    r14, r14
0x1800e5e21  jz      loc_1800E5EAA
0x1800e5e27  mov     rdx, r14; struct CEventLog *
0x1800e5e2a  lea     rcx, [rsp+0A38h+var_998]; this
0x1800e5e32  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800e5e37  nop
0x1800e5e38  lea     r14, cchOriginalDestLength
0x1800e5e3f  mov     rdx, r14
0x1800e5e42  test    rdi, rdi
0x1800e5e45  cmovnz  rdx, rdi
0x1800e5e49  lea     rcx, [rsp+0A38h+var_990]
0x1800e5e51  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e5e56  test    r15, r15
0x1800e5e59  cmovz   r15, r14
0x1800e5e5d  mov     rdx, r15
0x1800e5e60  lea     rcx, [rsp+0A38h+var_8F0]
0x1800e5e68  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800e5e6d  mov     edx, 0C0041801h; int
0x1800e5e72  lea     rcx, [rsp+0A38h+var_998]; this
0x1800e5e7a  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1800e5e7f  xor     r9d, r9d
0x1800e5e82  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x1800e5e89  mov     edx, 0C0001B80h; unsigned int
0x1800e5e8e  lea     rcx, [rsp+0A38h+var_998]; this
0x1800e5e96  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800e5e9b  nop
0x1800e5e9c  lea     rcx, [rsp+0A38h+var_998]; this
0x1800e5ea4  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800e5ea9  nop
0x1800e5eaa  mov     rdx, rdi
0x1800e5ead  lea     rcx, [rsp+0A38h+lpSubKey]
0x1800e5eb2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800e5eb7  nop
0x1800e5eb8  mov     r8d, 22h ; '"'
0x1800e5ebe  lea     rdx, aSoftwareMicros_14; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1800e5ec5  lea     rcx, [rsp+0A38h+lpSubKey]; Src
0x1800e5eca  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e5ecf  mov     [rsp+0A38h+hkey], rbx
0x1800e5ed4  lea     rcx, [rsp+0A38h+hkey]
0x1800e5ed9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e5ede  lea     rdx, [rsp+0A38h+lpSubKey]
0x1800e5ee3  cmp     [rsp+0A38h+var_9A8], 7
0x1800e5eec  cmova   rdx, [rsp+0A38h+lpSubKey]; lpSubKey
0x1800e5ef2  mov     [rsp+0A38h+lpdwDisposition], rbx; lpdwDisposition
0x1800e5ef7  mov     [rsp+0A38h+phkResult], rax; phkResult
0x1800e5efc  mov     [rsp+0A38h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800e5f01  mov     [rsp+0A38h+samDesired], 0F003Fh; samDesired
0x1800e5f09  mov     [rsp+0A38h+dwOptions], ebx; unsigned int
0x1800e5f0d  xor     r9d, r9d; lpClass
0x1800e5f10  xor     r8d, r8d; Reserved
0x1800e5f13  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800e5f1a  call    cs:__imp_RegCreateKeyExW
0x1800e5f20  mov     rcx, [rsp+0A38h]; this
0x1800e5f28  test    eax, eax
0x1800e5f2a  jz      short loc_1800E5F40
0x1800e5f2c  mov     r9d, eax; char *
0x1800e5f2f  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e5f36  mov     edx, 0F7h; void *
0x1800e5f3b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e5f40  mov     [rsp+0A38h+pvData], ebx
0x1800e5f44  mov     r9d, 4; dwType
0x1800e5f4a  mov     [rsp+0A38h+samDesired], r9d; cbData
0x1800e5f4f  lea     rax, [rsp+0A38h+pvData]
0x1800e5f54  mov     qword ptr [rsp+0A38h+dwOptions], rax; unsigned int
0x1800e5f59  lea     r8, pszValue; "SetupCompletedSuccessfully"
0x1800e5f60  xor     edx, edx; pszSubKey
0x1800e5f62  mov     rcx, [rsp+0A38h+hkey]; hkey
0x1800e5f67  call    cs:__imp_SHSetValueW
0x1800e5f6d  mov     rcx, [rsp+0A38h]; this
0x1800e5f75  test    eax, eax
0x1800e5f77  jz      short loc_1800E5F8E
0x1800e5f79  mov     r9d, eax; char *
0x1800e5f7c  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e5f83  mov     edx, 0FBh; void *
0x1800e5f88  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e5f8e  lea     rcx, [rsp+0A38h+hkey]
0x1800e5f93  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e5f98  nop
0x1800e5f99  lea     rcx, [rsp+0A38h+lpSubKey]; this
0x1800e5f9e  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e5fa3  nop
0x1800e5fa4  jmp     short loc_1800E5FB1
0x1800e5fa6  xor     ebx, ebx
0x1800e5fa8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e5fac  mov     rdi, [rsp+0A38h+var_9D8]
0x1800e5fb1  mov     rax, rsi
0x1800e5fb4  inc     rax
0x1800e5fb7  cmp     [rdi+rax*2], bx
0x1800e5fbb  jnz     short loc_1800E5FB4
0x1800e5fbd  lea     r14, [rax+1]
0x1800e5fc1  mov     eax, 2
0x1800e5fc6  mul     r14
0x1800e5fc9  cmovb   rax, rsi
0x1800e5fcd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e5fd4  mov     rcx, rax; unsigned __int64
0x1800e5fd7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800e5fdc  mov     r11, rax
0x1800e5fdf  mov     [rsp+0A38h+hkey], rax
0x1800e5fe4  test    rax, rax
0x1800e5fe7  jnz     short loc_1800E5FF8
0x1800e5fe9  mov     edi, 8007000Eh
0x1800e5fee  mov     r9d, edi
0x1800e5ff1  mov     edx, 101h
0x1800e5ff6  jmp     short loc_1800E6014
0x1800e5ff8  mov     r8, rdi; wchar_t *
0x1800e5ffb  mov     rdx, r14; unsigned __int64
0x1800e5ffe  mov     rcx, r11; wchar_t *
0x1800e6001  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800e6006  mov     edi, eax
0x1800e6008  test    eax, eax
0x1800e600a  jns     short loc_1800E6044
0x1800e600c  mov     r9d, eax; char *
0x1800e600f  mov     edx, 103h; void *
0x1800e6014  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e601b  mov     rcx, [rsp+0A38h]; this
0x1800e6023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6028  lea     rcx, [rsp+0A38h+hkey]
0x1800e602d  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800e6032  nop
0x1800e6033  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1800e6038  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800e603d  mov     eax, edi
0x1800e603f  jmp     loc_1800E6138
0x1800e6044  mov     [rsp+0A38h+hkey], rbx
0x1800e6049  mov     qword ptr [rsp+0A38h+samDesired], rbx; lpThreadId
0x1800e604e  mov     [rsp+0A38h+dwOptions], ebx; dwCreationFlags
0x1800e6052  mov     r9, r11; lpParameter
0x1800e6055  lea     r8, ResetUserCatalog; lpStartAddress
0x1800e605c  xor     edx, edx; dwStackSize
0x1800e605e  xor     ecx, ecx; lpThreadAttributes
0x1800e6060  call    cs:__imp_CreateThread
0x1800e6066  mov     [rsp+0A38h+var_9D8], rax
0x1800e606b  lea     rcx, [rsp+0A38h+var_9D8]
0x1800e6070  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e6075  lea     rcx, [rsp+0A38h+hkey]
0x1800e607a  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800e607f  jmp     loc_1800E612C
0x1800e6084  mov     [rsp+0A38h+hkey], rbx
0x1800e6089  lea     rax, [rsp+0A38h+hkey]
0x1800e608e  mov     qword ptr [rsp+0A38h+samDesired], rax; HKEY *
0x1800e6093  mov     [rsp+0A38h+dwOptions], 0F003Fh; unsigned int
0x1800e609b  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x1800e60a2  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800e60a9  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800e60ae  test    eax, eax
0x1800e60b0  jle     short loc_1800E60BC
0x1800e60b2  movzx   eax, ax
0x1800e60b5  or      eax, 80070000h
0x1800e60ba  test    eax, eax
0x1800e60bc  js      short loc_1800E60FA
0x1800e60be  mov     [rsp+0A38h+pvData], 3
0x1800e60c6  mov     r9d, 4; dwType
0x1800e60cc  mov     [rsp+0A38h+samDesired], r9d; cbData
0x1800e60d1  lea     rax, [rsp+0A38h+pvData]
0x1800e60d6  mov     qword ptr [rsp+0A38h+dwOptions], rax; pvData
0x1800e60db  lea     r8, aRebuildindex; "RebuildIndex"
0x1800e60e2  xor     edx, edx; pszSubKey
0x1800e60e4  mov     rcx, [rsp+0A38h+hkey]; hkey
0x1800e60e9  call    cs:__imp_SHSetValueW
0x1800e60ef  mov     rcx, [rsp+0A38h+hkey]; hKey
0x1800e60f4  call    cs:__imp_RegCloseKey
0x1800e60fa  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1800e6100  jnz     short loc_1800E612C
0x1800e6102  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x1800e6109  mov     qword ptr [rsp+0A38h+dwOptions], rax; __int64
0x1800e610e  mov     r9d, 0C0041801h
0x1800e6114  mov     r8, r15
0x1800e6117  mov     rdx, rdi
0x1800e611a  mov     rcx, r14; struct CEventLog *
0x1800e611d  call    ShutdownSelf_1
0x1800e6122  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1800e612c  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1800e6131  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800e6136  xor     eax, eax
0x1800e6138  mov     rcx, [rsp+0A38h+var_28]
0x1800e6140  xor     rcx, rsp; StackCookie
0x1800e6143  call    __security_check_cookie
0x1800e6148  lea     r11, [rsp+0A38h+var_18]
0x1800e6150  mov     rbx, [r11+20h]
0x1800e6154  mov     rsi, [r11+28h]
0x1800e6158  mov     rsp, r11
0x1800e615b  pop     r15
0x1800e615d  pop     r14
0x1800e615f  pop     rdi
0x1800e6160  retn
```

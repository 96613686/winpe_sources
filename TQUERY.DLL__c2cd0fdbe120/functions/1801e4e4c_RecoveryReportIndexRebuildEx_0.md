# RecoveryReportIndexRebuildEx_0

- ea: `0x1801e4e4c`
- end: `0x1801e5291`
- name: `RecoveryReportIndexRebuildEx_0`
- size: `1093`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18011726c`
- `0x1801e46f0`

## callees

- `0x18002e6fc`
- `0x180043d18`
- `0x18006380c`
- `0x180075d8c`
- `0x180078410`
- `0x18008b084`
- `0x18008facc`
- `0x1800983c0`
- `0x18009e510`
- `0x18009e614`
- `0x1800f7bfc`
- `0x1801199cc`
- `0x18013edc0`
- `0x1801710e4`
- `0x180188d90`
- `0x180189280`
- `0x18018e778`
- `0x18019b924`
- `0x1801a40f0`
- `0x1801a444c`
- `0x1801a4aa8`
- `0x1801a8e38`
- `0x1801e4b44`
- `0x1801e4e4c`
- `0x1801e5734`
- `0x1801f9f0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e5178`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e5178`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801e4f04`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801e4f04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e51e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e51e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e5232`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e5232`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801e502f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801e502f`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801e507c`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801e5227`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801e507c`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801e5227`

## string_xrefs

- `0x1801e5044`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801e5091`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801e512c`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801e506e`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecoveryReportIndexRebuildEx_0(
        __int64 a1,
        struct CEventLog *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int v10; // edx
  int v11; // r8d
  void *v12; // rdi
  const wchar_t *v13; // rcx
  const wchar_t *Catalog; // rdi
  const OLECHAR *v15; // rdx
  HKEY *phkResult; // rax
  const WCHAR *v17; // rdx
  unsigned int Key; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // kr10_8
  wchar_t *v24; // rax
  unsigned int v25; // edi
  __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  void *v29; // r11
  bool v31; // al
  wchar_t *v32; // rdx
  LSTATUS v33; // eax
  bool v34; // sf
  unsigned int dwOptions; // [rsp+20h] [rbp-A38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A38h]
  HKEY hkey; // [rsp+50h] [rbp-A08h] BYREF
  int pvData; // [rsp+58h] [rbp-A00h] BYREF
  HANDLE v39[2]; // [rsp+60h] [rbp-9F8h] BYREF
  int v40; // [rsp+70h] [rbp-9E8h] BYREF
  __int64 v41; // [rsp+78h] [rbp-9E0h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-9D8h] BYREF
  wchar_t v43; // [rsp+A0h] [rbp-9B8h] BYREF
  _BYTE v44[160]; // [rsp+A8h] [rbp-9B0h] BYREF
  _BYTE v45[2248]; // [rsp+148h] [rbp-910h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A58h] [rbp+0h]

  v40 = 0;
  v41 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v40);
  if ( a9 )
    v12 = (void *)std::_Func_class<unsigned char *,long>::operator()(a9, a6);
  else
    v12 = 0;
  LogIndexCorruptionEx((_DWORD)a2, v10, v11, a5, a6, a7, a8);
  if ( v12 )
    operator delete(v12);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = (const wchar_t *)PerUserCatalogNameForCorruption::GetCatalog();
    v39[0] = (HANDLE)Catalog;
    if ( a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)&v43, a2);
      v15 = &psz;
      if ( Catalog )
        v15 = Catalog;
      CLMString::operator=(v44, v15);
      CLMString::operator=(v45, &psz);
      CSearchEventEntry::SetError((CSearchEventEntry *)&v43, -1073473535);
      CSearchEventEntry::ReportError((CSearchEventEntry *)&v43, 0xC0001B80, L"The catalog is corrupt", 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)&v43);
    }
    try
    {
      std::wstring::wstring(lpSubKey, Catalog);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v17 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v17 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v17, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v19 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v19 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v19,
          dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      std::wstring::_Tidy_deallocate(lpSubKey);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        253,
        "onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h");
    }
    v20 = -1;
    do
      ++v20;
    while ( Catalog[v20] );
    v21 = v20 + 1;
    v23 = v20 + 1;
    v22 = 2 * (v20 + 1);
    if ( !is_mul_ok(v23, 2u) )
      v22 = -1;
    v24 = (wchar_t *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v24;
    if ( !v24 )
    {
      v25 = -2147024882;
      v26 = 2147942414LL;
      v27 = 257;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v26,
        dwOptionsa);
      SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v40);
      return v25;
    }
    v28 = StringCchCopyW(v24, v21, Catalog);
    v25 = v28;
    if ( v28 < 0 )
    {
      v26 = (unsigned int)v28;
      v27 = 259;
      goto LABEL_27;
    }
    hkey = 0;
    v39[0] = CreateThread(0, 0, ResetUserCatalog, v29, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v39);
    SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
  }
  else
  {
    hkey = 0;
    v31 = MapRegistryKeyPath(v13, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", &v43);
    v32 = &v43;
    if ( !v31 )
      v32 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
    v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 0xF003Fu, &hkey);
    v34 = v33 < 0;
    if ( v33 > 0 )
      v34 = 1;
    if ( !v34 )
    {
      pvData = 3;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      ShutdownSelf(a2, (__int64)L"The catalog is corrupt");
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v40);
  return 0;
}

```

## disassembly

```asm
0x1801e4e4c  push    rbx
0x1801e4e4e  push    rsi
0x1801e4e4f  push    rdi
0x1801e4e50  push    r12
0x1801e4e52  push    r14
0x1801e4e54  push    r15
0x1801e4e56  sub     rsp, 0A28h
0x1801e4e5d  mov     rax, cs:__security_cookie
0x1801e4e64  xor     rax, rsp
0x1801e4e67  mov     [rsp+0A58h+var_48], rax
0x1801e4e6f  mov     rsi, rdx
0x1801e4e72  mov     r15d, [rsp+0A58h+arg_28]
0x1801e4e7a  mov     r12, [rsp+0A58h+arg_30]
0x1801e4e82  mov     rdi, [rsp+0A58h+arg_40]
0x1801e4e8a  xor     ebx, ebx
0x1801e4e8c  mov     [rsp+0A58h+var_9E8], ebx
0x1801e4e90  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801e4e94  mov     [rsp+0A58h+var_9E0], r14
0x1801e4e99  lea     rcx, [rsp+0A58h+var_9E8]; this
0x1801e4e9e  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1801e4ea3  nop
0x1801e4ea4  test    rdi, rdi
0x1801e4ea7  jz      short loc_1801E4EB9
0x1801e4ea9  mov     edx, r15d
0x1801e4eac  mov     rcx, rdi
0x1801e4eaf  call    ??R?$_Func_class@PEAEJ@std@@QEBAPEAEJ@Z; std::_Func_class<uchar *,long>::operator()(long)
0x1801e4eb4  mov     rdi, rax
0x1801e4eb7  jmp     short loc_1801E4EBC
0x1801e4eb9  mov     rdi, rbx
0x1801e4ebc  mov     rax, [rsp+0A58h+arg_38]
0x1801e4ec4  mov     [rsp+0A58h+lpSecurityAttributes], rax
0x1801e4ec9  mov     qword ptr [rsp+0A58h+samDesired], r12
0x1801e4ece  mov     [rsp+0A58h+dwOptions], r15d; unsigned int
0x1801e4ed3  mov     r9d, [rsp+0A58h+arg_20]
0x1801e4edb  mov     rcx, rsi
0x1801e4ede  call    LogIndexCorruptionEx
0x1801e4ee3  test    rdi, rdi
0x1801e4ee6  jz      short loc_1801E4EF0
0x1801e4ee8  mov     rcx, rdi; Block
0x1801e4eeb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e4ef0  xor     r9d, r9d; Context
0x1801e4ef3  xor     r8d, r8d; Parameter
0x1801e4ef6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801e4efd  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1801e4f04  call    cs:__imp_InitOnceExecuteOnce
0x1801e4f0a  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1801e4f10  jz      loc_1801E519C
0x1801e4f16  call    PerUserCatalogNameForCorruption__GetCatalog
0x1801e4f1b  test    rax, rax
0x1801e4f1e  jz      loc_1801E519C
0x1801e4f24  call    PerUserCatalogNameForCorruption__GetCatalog
0x1801e4f29  mov     rdi, rax
0x1801e4f2c  mov     [rsp+0A58h+var_9F8], rax
0x1801e4f31  test    rsi, rsi
0x1801e4f34  jz      short loc_1801E4FB3
0x1801e4f36  mov     rdx, rsi; struct CEventLog *
0x1801e4f39  lea     rcx, [rsp+0A58h+var_9B8]; this
0x1801e4f41  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1801e4f46  nop
0x1801e4f47  lea     rdx, psz
0x1801e4f4e  test    rdi, rdi
0x1801e4f51  cmovnz  rdx, rdi
0x1801e4f55  lea     rcx, [rsp+0A58h+var_9B0]
0x1801e4f5d  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801e4f62  lea     rdx, psz
0x1801e4f69  lea     rcx, [rsp+0A58h+var_910]
0x1801e4f71  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801e4f76  mov     edx, 0C0041801h; int
0x1801e4f7b  lea     rcx, [rsp+0A58h+var_9B8]; this
0x1801e4f83  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1801e4f88  xor     r9d, r9d
0x1801e4f8b  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x1801e4f92  mov     edx, 0C0001B80h; unsigned int
0x1801e4f97  lea     rcx, [rsp+0A58h+var_9B8]; this
0x1801e4f9f  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1801e4fa4  nop
0x1801e4fa5  lea     rcx, [rsp+0A58h+var_9B8]; this
0x1801e4fad  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1801e4fb2  nop
0x1801e4fb3  mov     rdx, rdi
0x1801e4fb6  lea     rcx, [rsp+0A58h+lpSubKey]
0x1801e4fbe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e4fc3  nop
0x1801e4fc4  mov     r8d, 22h ; '"'
0x1801e4fca  lea     rdx, aSoftwareMicros_7; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1801e4fd1  lea     rcx, [rsp+0A58h+lpSubKey]; Src
0x1801e4fd9  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801e4fde  mov     [rsp+0A58h+hkey], rbx
0x1801e4fe3  lea     rcx, [rsp+0A58h+hkey]
0x1801e4fe8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801e4fed  lea     rdx, [rsp+0A58h+lpSubKey]
0x1801e4ff5  cmp     [rsp+0A58h+var_9C0], 7
0x1801e4ffe  cmova   rdx, [rsp+0A58h+lpSubKey]; lpSubKey
0x1801e5007  mov     [rsp+0A58h+lpdwDisposition], rbx; lpdwDisposition
0x1801e500c  mov     [rsp+0A58h+phkResult], rax; phkResult
0x1801e5011  mov     [rsp+0A58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1801e5016  mov     [rsp+0A58h+samDesired], 0F003Fh; samDesired
0x1801e501e  mov     [rsp+0A58h+dwOptions], ebx; unsigned int
0x1801e5022  xor     r9d, r9d; lpClass
0x1801e5025  xor     r8d, r8d; Reserved
0x1801e5028  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1801e502f  call    cs:__imp_RegCreateKeyExW
0x1801e5035  mov     rcx, [rsp+0A58h]; this
0x1801e503d  test    eax, eax
0x1801e503f  jz      short loc_1801E5055
0x1801e5041  mov     r9d, eax; char *
0x1801e5044  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801e504b  mov     edx, 0F7h; void *
0x1801e5050  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801e5055  mov     [rsp+0A58h+pvData], ebx
0x1801e5059  mov     r9d, 4; dwType
0x1801e505f  mov     [rsp+0A58h+samDesired], r9d; cbData
0x1801e5064  lea     rax, [rsp+0A58h+pvData]
0x1801e5069  mov     qword ptr [rsp+0A58h+dwOptions], rax; unsigned int
0x1801e506e  lea     r8, aSetupcompleted; "SetupCompletedSuccessfully"
0x1801e5075  xor     edx, edx; pszSubKey
0x1801e5077  mov     rcx, [rsp+0A58h+hkey]; hkey
0x1801e507c  call    cs:__imp_SHSetValueW
0x1801e5082  mov     rcx, [rsp+0A58h]; this
0x1801e508a  test    eax, eax
0x1801e508c  jz      short loc_1801E50A3
0x1801e508e  mov     r9d, eax; char *
0x1801e5091  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801e5098  mov     edx, 0FBh; void *
0x1801e509d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801e50a3  lea     rcx, [rsp+0A58h+hkey]
0x1801e50a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801e50ad  nop
0x1801e50ae  lea     rcx, [rsp+0A58h+lpSubKey]
0x1801e50b6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801e50bb  nop
0x1801e50bc  jmp     short loc_1801E50C9
0x1801e50be  xor     ebx, ebx
0x1801e50c0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801e50c4  mov     rdi, [rsp+0A58h+var_9F8]
0x1801e50c9  mov     rax, r14
0x1801e50cc  inc     rax
0x1801e50cf  cmp     [rdi+rax*2], bx
0x1801e50d3  jnz     short loc_1801E50CC
0x1801e50d5  lea     rsi, [rax+1]
0x1801e50d9  mov     eax, 2
0x1801e50de  mul     rsi
0x1801e50e1  cmovb   rax, r14
0x1801e50e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801e50ec  mov     rcx, rax; unsigned __int64
0x1801e50ef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801e50f4  mov     r11, rax
0x1801e50f7  mov     [rsp+0A58h+hkey], rax
0x1801e50fc  test    rax, rax
0x1801e50ff  jnz     short loc_1801E5110
0x1801e5101  mov     edi, 8007000Eh
0x1801e5106  mov     r9d, edi
0x1801e5109  mov     edx, 101h
0x1801e510e  jmp     short loc_1801E512C
0x1801e5110  mov     r8, rdi; wchar_t *
0x1801e5113  mov     rdx, rsi; unsigned __int64
0x1801e5116  mov     rcx, r11; wchar_t *
0x1801e5119  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1801e511e  mov     edi, eax
0x1801e5120  test    eax, eax
0x1801e5122  jns     short loc_1801E515C
0x1801e5124  mov     r9d, eax; char *
0x1801e5127  mov     edx, 103h; void *
0x1801e512c  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801e5133  mov     rcx, [rsp+0A58h]; this
0x1801e513b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e5140  lea     rcx, [rsp+0A58h+hkey]; this
0x1801e5145  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801e514a  nop
0x1801e514b  lea     rcx, [rsp+0A58h+var_9E8]; this
0x1801e5150  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801e5155  mov     eax, edi
0x1801e5157  jmp     loc_1801E5270
0x1801e515c  mov     [rsp+0A58h+hkey], rbx
0x1801e5161  mov     qword ptr [rsp+0A58h+samDesired], rbx; lpThreadId
0x1801e5166  mov     [rsp+0A58h+dwOptions], ebx; dwCreationFlags
0x1801e516a  mov     r9, r11; lpParameter
0x1801e516d  lea     r8, ResetUserCatalog; lpStartAddress
0x1801e5174  xor     edx, edx; dwStackSize
0x1801e5176  xor     ecx, ecx; lpThreadAttributes
0x1801e5178  call    cs:__imp_CreateThread
0x1801e517e  mov     [rsp+0A58h+var_9F8], rax
0x1801e5183  lea     rcx, [rsp+0A58h+var_9F8]
0x1801e5188  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e518d  lea     rcx, [rsp+0A58h+hkey]; this
0x1801e5192  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801e5197  jmp     loc_1801E5264
0x1801e519c  mov     [rsp+0A58h+hkey], rbx
0x1801e51a1  lea     r9, [rsp+0A58h+var_9B8]; wchar_t *
0x1801e51a9  lea     rdi, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows Search"
0x1801e51b0  mov     r8, rdi; wchar_t *
0x1801e51b3  mov     r14, 0FFFFFFFF80000002h
0x1801e51ba  mov     rdx, r14; HKEY
0x1801e51bd  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1801e51c2  lea     rdx, [rsp+0A58h+var_9B8]
0x1801e51ca  test    al, al
0x1801e51cc  cmovz   rdx, rdi; lpSubKey
0x1801e51d0  lea     rax, [rsp+0A58h+hkey]
0x1801e51d5  mov     qword ptr [rsp+0A58h+dwOptions], rax; phkResult
0x1801e51da  mov     r9d, 0F003Fh; samDesired
0x1801e51e0  xor     r8d, r8d; ulOptions
0x1801e51e3  mov     rcx, r14; hKey
0x1801e51e6  call    cs:__imp_RegOpenKeyExW
0x1801e51ec  test    eax, eax
0x1801e51ee  jle     short loc_1801E51FA
0x1801e51f0  movzx   eax, ax
0x1801e51f3  or      eax, 80070000h
0x1801e51f8  test    eax, eax
0x1801e51fa  js      short loc_1801E5238
0x1801e51fc  mov     [rsp+0A58h+pvData], 3
0x1801e5204  mov     r9d, 4; dwType
0x1801e520a  mov     [rsp+0A58h+samDesired], r9d; cbData
0x1801e520f  lea     rax, [rsp+0A58h+pvData]
0x1801e5214  mov     qword ptr [rsp+0A58h+dwOptions], rax; pvData
0x1801e5219  lea     r8, aRebuildindex; "RebuildIndex"
0x1801e5220  xor     edx, edx; pszSubKey
0x1801e5222  mov     rcx, [rsp+0A58h+hkey]; hkey
0x1801e5227  call    cs:__imp_SHSetValueW
0x1801e522d  mov     rcx, [rsp+0A58h+hkey]; hKey
0x1801e5232  call    cs:__imp_RegCloseKey
0x1801e5238  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1801e523e  jnz     short loc_1801E5264
0x1801e5240  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x1801e5247  mov     qword ptr [rsp+0A58h+dwOptions], rax; __int64
0x1801e524c  mov     r9d, 0C0041801h
0x1801e5252  mov     rcx, rsi; struct CEventLog *
0x1801e5255  call    ShutdownSelf
0x1801e525a  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1801e5264  lea     rcx, [rsp+0A58h+var_9E8]; this
0x1801e5269  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801e526e  xor     eax, eax
0x1801e5270  mov     rcx, [rsp+0A58h+var_48]
0x1801e5278  xor     rcx, rsp; StackCookie
0x1801e527b  call    __security_check_cookie
0x1801e5280  add     rsp, 0A28h
0x1801e5287  pop     r15
0x1801e5289  pop     r14
0x1801e528b  pop     r12
0x1801e528d  pop     rdi
0x1801e528e  pop     rsi
0x1801e528f  pop     rbx
0x1801e5290  retn
```

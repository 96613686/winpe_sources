# RecoveryReportIndexRebuildEx

- ea: `0x1800b7e9c`
- end: `0x1800b8273`
- name: `RecoveryReportIndexRebuildEx`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c5670`

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
- `0x1800b7e9c`
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
- `0x1801a5730`
- `0x1801a5ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b8178`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b8178`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b820c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b820c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b8032`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b8032`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b7f09`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b7f09`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800b807f`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800b8201`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800b807f`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800b8201`

## string_xrefs

- `0x1800b8071`: `SetupCompletedSuccessfully`
- `0x1800b8047`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800b8094`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800b812c`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecoveryReportIndexRebuildEx(__int64 a1, struct CEventLog *a2, __int64 a3, const size_t *a4)
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
  LogIndexCorruptionEx_0(a2, a3, a4);
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
      ShutdownSelf_0(a2, (__int64)L"The catalog is corrupt");
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v33);
  return 0;
}

```

## disassembly

```asm
0x1800b7e9c  mov     [rsp+arg_0], rbx
0x1800b7ea1  mov     [rsp+arg_8], rsi
0x1800b7ea6  push    rdi
0x1800b7ea7  push    r14
0x1800b7ea9  push    r15
0x1800b7eab  sub     rsp, 0A20h
0x1800b7eb2  mov     rax, cs:__security_cookie
0x1800b7eb9  xor     rax, rsp
0x1800b7ebc  mov     [rsp+0A38h+var_28], rax
0x1800b7ec4  mov     r15, r9
0x1800b7ec7  mov     rdi, r8
0x1800b7eca  mov     r14, rdx
0x1800b7ecd  xor     ebx, ebx
0x1800b7ecf  mov     [rsp+0A38h+var_9D0], ebx
0x1800b7ed3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b7ed7  mov     [rsp+0A38h+var_9C8], rsi
0x1800b7edc  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1800b7ee1  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1800b7ee6  nop
0x1800b7ee7  mov     r8, r15
0x1800b7eea  mov     rdx, rdi
0x1800b7eed  mov     rcx, r14
0x1800b7ef0  call    LogIndexCorruptionEx_0
0x1800b7ef5  xor     r9d, r9d; Context
0x1800b7ef8  xor     r8d, r8d; Parameter
0x1800b7efb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800b7f02  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800b7f09  call    cs:__imp_InitOnceExecuteOnce
0x1800b7f0f  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1800b7f15  jz      loc_1800B819C
0x1800b7f1b  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800b7f20  test    rax, rax
0x1800b7f23  jz      loc_1800B819C
0x1800b7f29  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800b7f2e  mov     rdi, rax
0x1800b7f31  mov     [rsp+0A38h+var_9D8], rax
0x1800b7f36  test    r14, r14
0x1800b7f39  jz      loc_1800B7FC2
0x1800b7f3f  mov     rdx, r14; struct CEventLog *
0x1800b7f42  lea     rcx, [rsp+0A38h+var_998]; this
0x1800b7f4a  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800b7f4f  nop
0x1800b7f50  lea     r14, cchOriginalDestLength
0x1800b7f57  mov     rdx, r14
0x1800b7f5a  test    rdi, rdi
0x1800b7f5d  cmovnz  rdx, rdi
0x1800b7f61  lea     rcx, [rsp+0A38h+var_990]
0x1800b7f69  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b7f6e  test    r15, r15
0x1800b7f71  cmovz   r15, r14
0x1800b7f75  mov     rdx, r15
0x1800b7f78  lea     rcx, [rsp+0A38h+var_8F0]
0x1800b7f80  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800b7f85  mov     edx, 0C0041801h; int
0x1800b7f8a  lea     rcx, [rsp+0A38h+var_998]; this
0x1800b7f92  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1800b7f97  xor     r9d, r9d
0x1800b7f9a  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x1800b7fa1  mov     edx, 0C0001B80h; unsigned int
0x1800b7fa6  lea     rcx, [rsp+0A38h+var_998]; this
0x1800b7fae  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800b7fb3  nop
0x1800b7fb4  lea     rcx, [rsp+0A38h+var_998]; this
0x1800b7fbc  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800b7fc1  nop
0x1800b7fc2  mov     rdx, rdi
0x1800b7fc5  lea     rcx, [rsp+0A38h+lpSubKey]
0x1800b7fca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800b7fcf  nop
0x1800b7fd0  mov     r8d, 22h ; '"'
0x1800b7fd6  lea     rdx, aSoftwareMicros_14; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1800b7fdd  lea     rcx, [rsp+0A38h+lpSubKey]; Src
0x1800b7fe2  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800b7fe7  mov     [rsp+0A38h+hkey], rbx
0x1800b7fec  lea     rcx, [rsp+0A38h+hkey]
0x1800b7ff1  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800b7ff6  lea     rdx, [rsp+0A38h+lpSubKey]
0x1800b7ffb  cmp     [rsp+0A38h+var_9A8], 7
0x1800b8004  cmova   rdx, [rsp+0A38h+lpSubKey]; lpSubKey
0x1800b800a  mov     [rsp+0A38h+lpdwDisposition], rbx; lpdwDisposition
0x1800b800f  mov     [rsp+0A38h+phkResult], rax; phkResult
0x1800b8014  mov     [rsp+0A38h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800b8019  mov     [rsp+0A38h+samDesired], 0F003Fh; samDesired
0x1800b8021  mov     [rsp+0A38h+dwOptions], ebx; unsigned int
0x1800b8025  xor     r9d, r9d; lpClass
0x1800b8028  xor     r8d, r8d; Reserved
0x1800b802b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800b8032  call    cs:__imp_RegCreateKeyExW
0x1800b8038  mov     rcx, [rsp+0A38h]; this
0x1800b8040  test    eax, eax
0x1800b8042  jz      short loc_1800B8058
0x1800b8044  mov     r9d, eax; char *
0x1800b8047  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b804e  mov     edx, 0F7h; void *
0x1800b8053  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b8058  mov     [rsp+0A38h+pvData], ebx
0x1800b805c  mov     r9d, 4; dwType
0x1800b8062  mov     [rsp+0A38h+samDesired], r9d; cbData
0x1800b8067  lea     rax, [rsp+0A38h+pvData]
0x1800b806c  mov     qword ptr [rsp+0A38h+dwOptions], rax; unsigned int
0x1800b8071  lea     r8, pszValue; "SetupCompletedSuccessfully"
0x1800b8078  xor     edx, edx; pszSubKey
0x1800b807a  mov     rcx, [rsp+0A38h+hkey]; hkey
0x1800b807f  call    cs:__imp_SHSetValueW
0x1800b8085  mov     rcx, [rsp+0A38h]; this
0x1800b808d  test    eax, eax
0x1800b808f  jz      short loc_1800B80A6
0x1800b8091  mov     r9d, eax; char *
0x1800b8094  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b809b  mov     edx, 0FBh; void *
0x1800b80a0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b80a6  lea     rcx, [rsp+0A38h+hkey]
0x1800b80ab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b80b0  nop
0x1800b80b1  lea     rcx, [rsp+0A38h+lpSubKey]; this
0x1800b80b6  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800b80bb  nop
0x1800b80bc  jmp     short loc_1800B80C9
0x1800b80be  xor     ebx, ebx
0x1800b80c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b80c4  mov     rdi, [rsp+0A38h+var_9D8]
0x1800b80c9  mov     rax, rsi
0x1800b80cc  inc     rax
0x1800b80cf  cmp     [rdi+rax*2], bx
0x1800b80d3  jnz     short loc_1800B80CC
0x1800b80d5  lea     r14, [rax+1]
0x1800b80d9  mov     eax, 2
0x1800b80de  mul     r14
0x1800b80e1  cmovb   rax, rsi
0x1800b80e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b80ec  mov     rcx, rax; unsigned __int64
0x1800b80ef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b80f4  mov     r11, rax
0x1800b80f7  mov     [rsp+0A38h+hkey], rax
0x1800b80fc  test    rax, rax
0x1800b80ff  jnz     short loc_1800B8110
0x1800b8101  mov     edi, 8007000Eh
0x1800b8106  mov     r9d, edi
0x1800b8109  mov     edx, 101h
0x1800b810e  jmp     short loc_1800B812C
0x1800b8110  mov     r8, rdi; wchar_t *
0x1800b8113  mov     rdx, r14; unsigned __int64
0x1800b8116  mov     rcx, r11; wchar_t *
0x1800b8119  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800b811e  mov     edi, eax
0x1800b8120  test    eax, eax
0x1800b8122  jns     short loc_1800B815C
0x1800b8124  mov     r9d, eax; char *
0x1800b8127  mov     edx, 103h; void *
0x1800b812c  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b8133  mov     rcx, [rsp+0A38h]; this
0x1800b813b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8140  lea     rcx, [rsp+0A38h+hkey]
0x1800b8145  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800b814a  nop
0x1800b814b  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1800b8150  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800b8155  mov     eax, edi
0x1800b8157  jmp     loc_1800B824A
0x1800b815c  mov     [rsp+0A38h+hkey], rbx
0x1800b8161  mov     qword ptr [rsp+0A38h+samDesired], rbx; lpThreadId
0x1800b8166  mov     [rsp+0A38h+dwOptions], ebx; dwCreationFlags
0x1800b816a  mov     r9, r11; lpParameter
0x1800b816d  lea     r8, ResetUserCatalog; lpStartAddress
0x1800b8174  xor     edx, edx; dwStackSize
0x1800b8176  xor     ecx, ecx; lpThreadAttributes
0x1800b8178  call    cs:__imp_CreateThread
0x1800b817e  mov     [rsp+0A38h+var_9D8], rax
0x1800b8183  lea     rcx, [rsp+0A38h+var_9D8]
0x1800b8188  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b818d  lea     rcx, [rsp+0A38h+hkey]
0x1800b8192  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800b8197  jmp     loc_1800B823E
0x1800b819c  mov     [rsp+0A38h+hkey], rbx
0x1800b81a1  lea     rax, [rsp+0A38h+hkey]
0x1800b81a6  mov     qword ptr [rsp+0A38h+samDesired], rax; HKEY *
0x1800b81ab  mov     [rsp+0A38h+dwOptions], 0F003Fh; unsigned int
0x1800b81b3  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x1800b81ba  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800b81c1  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800b81c6  test    eax, eax
0x1800b81c8  jle     short loc_1800B81D4
0x1800b81ca  movzx   eax, ax
0x1800b81cd  or      eax, 80070000h
0x1800b81d2  test    eax, eax
0x1800b81d4  js      short loc_1800B8212
0x1800b81d6  mov     [rsp+0A38h+pvData], 3
0x1800b81de  mov     r9d, 4; dwType
0x1800b81e4  mov     [rsp+0A38h+samDesired], r9d; cbData
0x1800b81e9  lea     rax, [rsp+0A38h+pvData]
0x1800b81ee  mov     qword ptr [rsp+0A38h+dwOptions], rax; pvData
0x1800b81f3  lea     r8, aRebuildindex; "RebuildIndex"
0x1800b81fa  xor     edx, edx; pszSubKey
0x1800b81fc  mov     rcx, [rsp+0A38h+hkey]; hkey
0x1800b8201  call    cs:__imp_SHSetValueW
0x1800b8207  mov     rcx, [rsp+0A38h+hkey]; hKey
0x1800b820c  call    cs:__imp_RegCloseKey
0x1800b8212  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1800b8218  jnz     short loc_1800B823E
0x1800b821a  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x1800b8221  mov     qword ptr [rsp+0A38h+dwOptions], rax; __int64
0x1800b8226  mov     r8, r15
0x1800b8229  mov     rdx, rdi
0x1800b822c  mov     rcx, r14; struct CEventLog *
0x1800b822f  call    ShutdownSelf_0
0x1800b8234  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1800b823e  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1800b8243  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800b8248  xor     eax, eax
0x1800b824a  mov     rcx, [rsp+0A38h+var_28]
0x1800b8252  xor     rcx, rsp; StackCookie
0x1800b8255  call    __security_check_cookie
0x1800b825a  lea     r11, [rsp+0A38h+var_18]
0x1800b8262  mov     rbx, [r11+20h]
0x1800b8266  mov     rsi, [r11+28h]
0x1800b826a  mov     rsp, r11
0x1800b826d  pop     r15
0x1800b826f  pop     r14
0x1800b8271  pop     rdi
0x1800b8272  retn
```

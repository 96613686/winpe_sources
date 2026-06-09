# RecoveryReportIndexRebuildEx

- ea: `0x1801a8a3c`
- end: `0x1801a8daf`
- name: `RecoveryReportIndexRebuildEx`
- size: `883`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801a8898`

## callees

- `0x18002e6fc`
- `0x180044c48`
- `0x18006380c`
- `0x180075d8c`
- `0x180078410`
- `0x18008b084`
- `0x1800983c0`
- `0x18009e510`
- `0x18009e614`
- `0x1800f7bfc`
- `0x1801199cc`
- `0x18013edc0`
- `0x1801710e4`
- `0x18017791c`
- `0x180188d90`
- `0x18018e778`
- `0x18019b924`
- `0x1801a8a3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a8c79`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a8d61`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a8c79`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801a8d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8d6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a8d6f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801a8a89`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801a8a89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a8ce7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a8ce7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a8d33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a8d33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801a8b30`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801a8b30`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801a8b7d`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801a8d28`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801a8b7d`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801a8d28`

## string_xrefs

- `0x1801a8b45`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801a8b92`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801a8c2d`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801a8b6f`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 RecoveryReportIndexRebuildEx()
{
  const wchar_t *v0; // rcx
  __int64 Catalog_0; // rax
  const wchar_t *v2; // rdi
  HKEY *phkResult; // rax
  const WCHAR *v4; // rdx
  unsigned int Key; // eax
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr10_8
  wchar_t *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  void *v16; // r11
  bool v18; // al
  wchar_t *v19; // rdx
  LSTATUS v20; // eax
  bool v21; // sf
  HANDLE v22; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-2C8h]
  DWORD pvData; // [rsp+50h] [rbp-298h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-290h] BYREF
  HANDLE v27[2]; // [rsp+60h] [rbp-288h] BYREF
  int v28; // [rsp+70h] [rbp-278h] BYREF
  __int64 v29; // [rsp+78h] [rbp-270h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-268h] BYREF
  wchar_t v31[264]; // [rsp+A0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v28 = 0;
  v29 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v28);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog_0() )
  {
    Catalog_0 = PerUserCatalogNameForCorruption::GetCatalog_0();
    try
    {
      v2 = (const wchar_t *)Catalog_0;
      v27[0] = (HANDLE)Catalog_0;
      std::wstring::wstring(lpSubKey, Catalog_0);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v4 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v4 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v4, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v6 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v6 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v6,
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
    v7 = -1;
    do
      ++v7;
    while ( v2[v7] );
    v8 = v7 + 1;
    v10 = v7 + 1;
    v9 = 2 * (v7 + 1);
    if ( !is_mul_ok(v10, 2u) )
      v9 = -1;
    v11 = (wchar_t *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v11;
    if ( !v11 )
    {
      v12 = -2147024882;
      v13 = 2147942414LL;
      v14 = 257;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v13,
        dwOptionsa);
      SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v28);
      return v12;
    }
    v15 = StringCchCopyW(v11, v8, v2);
    v12 = v15;
    if ( v15 < 0 )
    {
      v13 = (unsigned int)v15;
      v14 = 259;
      goto LABEL_19;
    }
    hkey = 0;
    v27[0] = CreateThread(0, 0, ResetUserCatalog, v16, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
    SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
  }
  else
  {
    hkey = 0;
    v18 = MapRegistryKeyPath(v0, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v31);
    v19 = v31;
    if ( !v18 )
      v19 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
    v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0xF003Fu, &hkey);
    v21 = v20 < 0;
    if ( v20 > 0 )
      v21 = 1;
    if ( !v21 )
    {
      pvData = 13;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      pvData = 0;
      v22 = CreateThread(0, 0, ShutdownSelfThread, 0, 0, &pvData);
      if ( v22 )
        CloseHandle(v22);
      else
        GetLastScode();
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v28);
  return 0;
}

```

## disassembly

```asm
0x1801a8a3c  push    rbx
0x1801a8a3e  push    rsi
0x1801a8a3f  push    rdi
0x1801a8a40  push    r14
0x1801a8a42  sub     rsp, 2C8h
0x1801a8a49  mov     rax, cs:__security_cookie
0x1801a8a50  xor     rax, rsp
0x1801a8a53  mov     [rsp+2E8h+var_38], rax
0x1801a8a5b  xor     ebx, ebx
0x1801a8a5d  mov     [rsp+2E8h+var_278], ebx
0x1801a8a61  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801a8a65  mov     [rsp+2E8h+var_270], rsi
0x1801a8a6a  lea     rcx, [rsp+2E8h+var_278]; this
0x1801a8a6f  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1801a8a74  nop
0x1801a8a75  xor     r9d, r9d; Context
0x1801a8a78  xor     r8d, r8d; Parameter
0x1801a8a7b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801a8a82  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1801a8a89  call    cs:__imp_InitOnceExecuteOnce
0x1801a8a8f  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1801a8a95  jz      loc_1801A8C9D
0x1801a8a9b  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x1801a8aa0  test    rax, rax
0x1801a8aa3  jz      loc_1801A8C9D
0x1801a8aa9  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x1801a8aae  mov     rdi, rax
0x1801a8ab1  mov     [rsp+2E8h+var_288], rax
0x1801a8ab6  mov     rdx, rax
0x1801a8ab9  lea     rcx, [rsp+2E8h+lpSubKey]
0x1801a8ac1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801a8ac6  nop
0x1801a8ac7  lea     r8d, [rbx+22h]
0x1801a8acb  lea     rdx, aSoftwareMicros_7; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1801a8ad2  lea     rcx, [rsp+2E8h+lpSubKey]; Src
0x1801a8ada  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801a8adf  mov     [rsp+2E8h+hkey], rbx
0x1801a8ae4  lea     rcx, [rsp+2E8h+hkey]
0x1801a8ae9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801a8aee  lea     rdx, [rsp+2E8h+lpSubKey]
0x1801a8af6  cmp     [rsp+2E8h+var_250], 7
0x1801a8aff  cmova   rdx, [rsp+2E8h+lpSubKey]; lpSubKey
0x1801a8b08  mov     [rsp+2E8h+lpdwDisposition], rbx; lpdwDisposition
0x1801a8b0d  mov     [rsp+2E8h+phkResult], rax; phkResult
0x1801a8b12  mov     [rsp+2E8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1801a8b17  mov     [rsp+2E8h+samDesired], 0F003Fh; samDesired
0x1801a8b1f  mov     [rsp+2E8h+dwOptions], ebx; unsigned int
0x1801a8b23  xor     r9d, r9d; lpClass
0x1801a8b26  xor     r8d, r8d; Reserved
0x1801a8b29  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1801a8b30  call    cs:__imp_RegCreateKeyExW
0x1801a8b36  mov     rcx, [rsp+2E8h]; this
0x1801a8b3e  test    eax, eax
0x1801a8b40  jz      short loc_1801A8B56
0x1801a8b42  mov     r9d, eax; char *
0x1801a8b45  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801a8b4c  mov     edx, 0F7h; void *
0x1801a8b51  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801a8b56  mov     [rsp+2E8h+pvData], ebx
0x1801a8b5a  mov     r9d, 4; dwType
0x1801a8b60  mov     [rsp+2E8h+samDesired], r9d; cbData
0x1801a8b65  lea     rax, [rsp+2E8h+pvData]
0x1801a8b6a  mov     qword ptr [rsp+2E8h+dwOptions], rax; unsigned int
0x1801a8b6f  lea     r8, aSetupcompleted; "SetupCompletedSuccessfully"
0x1801a8b76  xor     edx, edx; pszSubKey
0x1801a8b78  mov     rcx, [rsp+2E8h+hkey]; hkey
0x1801a8b7d  call    cs:__imp_SHSetValueW
0x1801a8b83  mov     rcx, [rsp+2E8h]; this
0x1801a8b8b  test    eax, eax
0x1801a8b8d  jz      short loc_1801A8BA4
0x1801a8b8f  mov     r9d, eax; char *
0x1801a8b92  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801a8b99  mov     edx, 0FBh; void *
0x1801a8b9e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801a8ba4  lea     rcx, [rsp+2E8h+hkey]
0x1801a8ba9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a8bae  nop
0x1801a8baf  lea     rcx, [rsp+2E8h+lpSubKey]
0x1801a8bb7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a8bbc  nop
0x1801a8bbd  jmp     short loc_1801A8BCA
0x1801a8bbf  xor     ebx, ebx
0x1801a8bc1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801a8bc5  mov     rdi, [rsp+2E8h+var_288]
0x1801a8bca  mov     rax, rsi
0x1801a8bcd  inc     rax
0x1801a8bd0  cmp     [rdi+rax*2], bx
0x1801a8bd4  jnz     short loc_1801A8BCD
0x1801a8bd6  lea     r14, [rax+1]
0x1801a8bda  mov     eax, 2
0x1801a8bdf  mul     r14
0x1801a8be2  cmovb   rax, rsi
0x1801a8be6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801a8bed  mov     rcx, rax; unsigned __int64
0x1801a8bf0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801a8bf5  mov     r11, rax
0x1801a8bf8  mov     [rsp+2E8h+hkey], rax
0x1801a8bfd  test    rax, rax
0x1801a8c00  jnz     short loc_1801A8C11
0x1801a8c02  mov     edi, 8007000Eh
0x1801a8c07  mov     r9d, edi
0x1801a8c0a  mov     edx, 101h
0x1801a8c0f  jmp     short loc_1801A8C2D
0x1801a8c11  mov     r8, rdi; wchar_t *
0x1801a8c14  mov     rdx, r14; unsigned __int64
0x1801a8c17  mov     rcx, r11; wchar_t *
0x1801a8c1a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1801a8c1f  mov     edi, eax
0x1801a8c21  test    eax, eax
0x1801a8c23  jns     short loc_1801A8C5D
0x1801a8c25  mov     r9d, eax; char *
0x1801a8c28  mov     edx, 103h; void *
0x1801a8c2d  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801a8c34  mov     rcx, [rsp+2E8h]; this
0x1801a8c3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8c41  lea     rcx, [rsp+2E8h+hkey]; this
0x1801a8c46  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801a8c4b  nop
0x1801a8c4c  lea     rcx, [rsp+2E8h+var_278]; this
0x1801a8c51  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801a8c56  mov     eax, edi
0x1801a8c58  jmp     loc_1801A8D92
0x1801a8c5d  mov     [rsp+2E8h+hkey], rbx
0x1801a8c62  mov     qword ptr [rsp+2E8h+samDesired], rbx; lpThreadId
0x1801a8c67  mov     [rsp+2E8h+dwOptions], ebx; dwCreationFlags
0x1801a8c6b  mov     r9, r11; lpParameter
0x1801a8c6e  lea     r8, ResetUserCatalog; lpStartAddress
0x1801a8c75  xor     edx, edx; dwStackSize
0x1801a8c77  xor     ecx, ecx; lpThreadAttributes
0x1801a8c79  call    cs:__imp_CreateThread
0x1801a8c7f  mov     [rsp+2E8h+var_288], rax
0x1801a8c84  lea     rcx, [rsp+2E8h+var_288]
0x1801a8c89  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801a8c8e  lea     rcx, [rsp+2E8h+hkey]; this
0x1801a8c93  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801a8c98  jmp     loc_1801A8D86
0x1801a8c9d  mov     [rsp+2E8h+hkey], rbx
0x1801a8ca2  lea     r9, [rsp+2E8h+var_248]; wchar_t *
0x1801a8caa  lea     rdi, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows Search"
0x1801a8cb1  mov     r8, rdi; wchar_t *
0x1801a8cb4  mov     rsi, 0FFFFFFFF80000002h
0x1801a8cbb  mov     rdx, rsi; HKEY
0x1801a8cbe  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1801a8cc3  lea     rdx, [rsp+2E8h+var_248]
0x1801a8ccb  test    al, al
0x1801a8ccd  cmovz   rdx, rdi; lpSubKey
0x1801a8cd1  lea     rax, [rsp+2E8h+hkey]
0x1801a8cd6  mov     qword ptr [rsp+2E8h+dwOptions], rax; phkResult
0x1801a8cdb  mov     r9d, 0F003Fh; samDesired
0x1801a8ce1  xor     r8d, r8d; ulOptions
0x1801a8ce4  mov     rcx, rsi; hKey
0x1801a8ce7  call    cs:__imp_RegOpenKeyExW
0x1801a8ced  test    eax, eax
0x1801a8cef  jle     short loc_1801A8CFB
0x1801a8cf1  movzx   eax, ax
0x1801a8cf4  or      eax, 80070000h
0x1801a8cf9  test    eax, eax
0x1801a8cfb  js      short loc_1801A8D39
0x1801a8cfd  mov     [rsp+2E8h+pvData], 0Dh
0x1801a8d05  mov     r9d, 4; dwType
0x1801a8d0b  mov     [rsp+2E8h+samDesired], r9d; cbData
0x1801a8d10  lea     rax, [rsp+2E8h+pvData]
0x1801a8d15  mov     qword ptr [rsp+2E8h+dwOptions], rax; pvData
0x1801a8d1a  lea     r8, aRebuildindex; "RebuildIndex"
0x1801a8d21  xor     edx, edx; pszSubKey
0x1801a8d23  mov     rcx, [rsp+2E8h+hkey]; hkey
0x1801a8d28  call    cs:__imp_SHSetValueW
0x1801a8d2e  mov     rcx, [rsp+2E8h+hkey]; hKey
0x1801a8d33  call    cs:__imp_RegCloseKey
0x1801a8d39  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1801a8d3f  jnz     short loc_1801A8D86
0x1801a8d41  mov     [rsp+2E8h+pvData], ebx
0x1801a8d45  lea     rax, [rsp+2E8h+pvData]
0x1801a8d4a  mov     qword ptr [rsp+2E8h+samDesired], rax; lpThreadId
0x1801a8d4f  mov     [rsp+2E8h+dwOptions], ebx; dwCreationFlags
0x1801a8d53  xor     r9d, r9d; lpParameter
0x1801a8d56  lea     r8, ShutdownSelfThread; lpStartAddress
0x1801a8d5d  xor     edx, edx; dwStackSize
0x1801a8d5f  xor     ecx, ecx; lpThreadAttributes
0x1801a8d61  call    cs:__imp_CreateThread
0x1801a8d67  test    rax, rax
0x1801a8d6a  jz      short loc_1801A8D77
0x1801a8d6c  mov     rcx, rax; hObject
0x1801a8d6f  call    cs:__imp_CloseHandle
0x1801a8d75  jmp     short loc_1801A8D7C
0x1801a8d77  call    ?GetLastScode@@YAJXZ; GetLastScode(void)
0x1801a8d7c  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1801a8d86  lea     rcx, [rsp+2E8h+var_278]; this
0x1801a8d8b  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801a8d90  xor     eax, eax
0x1801a8d92  mov     rcx, [rsp+2E8h+var_38]
0x1801a8d9a  xor     rcx, rsp; StackCookie
0x1801a8d9d  call    __security_check_cookie
0x1801a8da2  add     rsp, 2C8h
0x1801a8da9  pop     r14
0x1801a8dab  pop     rdi
0x1801a8dac  pop     rsi
0x1801a8dad  pop     rbx
0x1801a8dae  retn
```

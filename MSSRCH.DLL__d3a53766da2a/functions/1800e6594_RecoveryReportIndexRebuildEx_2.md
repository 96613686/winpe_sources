# RecoveryReportIndexRebuildEx_2

- ea: `0x1800e6594`
- end: `0x1800e68e1`
- name: `RecoveryReportIndexRebuildEx_2`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18011d330`

## callees

- `0x18000ee60`
- `0x18000f880`
- `0x180012120`
- `0x180022710`
- `0x180056b90`
- `0x18005e788`
- `0x18009491c`
- `0x1800a3a38`
- `0x1800b827c`
- `0x1800b837c`
- `0x1800e1320`
- `0x1800e4710`
- `0x1800e6594`
- `0x18010839c`
- `0x1801244c0`
- `0x1801249ec`
- `0x18013dd98`
- `0x180141a94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e67d1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e6893`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e67d1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800e6893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e68a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e68a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6865`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e6688`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e6688`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e65e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e65e1`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e66d5`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e685a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e66d5`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800e685a`

## string_xrefs

- `0x1800e66c7`: `SetupCompletedSuccessfully`
- `0x1800e669d`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800e66ea`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1800e6785`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 RecoveryReportIndexRebuildEx_2()
{
  const wchar_t *v0; // rcx
  unsigned int v1; // r9d
  __int64 Catalog; // rax
  const wchar_t *v3; // rdi
  HKEY *phkResult; // rax
  const WCHAR *v5; // rdx
  unsigned int Key; // eax
  unsigned int v7; // eax
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // kr10_8
  wchar_t *v12; // rax
  unsigned int v13; // edi
  __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  void *v17; // r11
  int v19; // eax
  bool v20; // sf
  HANDLE v21; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-B8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-B8h]
  DWORD pvData; // [rsp+50h] [rbp-88h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-80h] BYREF
  HANDLE v26[2]; // [rsp+60h] [rbp-78h] BYREF
  int v27; // [rsp+70h] [rbp-68h] BYREF
  __int64 v28; // [rsp+78h] [rbp-60h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v27 = 0;
  v28 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v27);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    (PINIT_ONCE_FN)_lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = PerUserCatalogNameForCorruption::GetCatalog();
    try
    {
      v3 = (const wchar_t *)Catalog;
      v26[0] = (HANDLE)Catalog;
      std::wstring::wstring(lpSubKey, Catalog);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v5 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v5 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v5, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v7 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v7 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v7,
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
    v8 = -1;
    do
      ++v8;
    while ( v3[v8] );
    v9 = v8 + 1;
    v11 = v8 + 1;
    v10 = 2 * (v8 + 1);
    if ( !is_mul_ok(v11, 2u) )
      v10 = -1;
    v12 = (wchar_t *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v12;
    if ( !v12 )
    {
      v13 = -2147024882;
      v14 = 2147942414LL;
      v15 = 257;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v14,
        dwOptionsa);
      std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v27);
      return v13;
    }
    v16 = StringCchCopyW(v12, v9, v3);
    v13 = v16;
    if ( v16 < 0 )
    {
      v14 = (unsigned int)v16;
      v15 = 259;
      goto LABEL_19;
    }
    hkey = 0;
    v26[0] = CreateThread(0, 0, ResetUserCatalog, v17, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v26);
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&hkey);
  }
  else
  {
    hkey = 0;
    v19 = WSearchRegOpenKeyEx(v0, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v1, 0xF003Fu, &hkey);
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
    if ( !v20 )
    {
      pvData = 13;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      pvData = 0;
      v21 = CreateThread(0, 0, ShutdownSelfThread, 0, 0, &pvData);
      if ( v21 )
        CloseHandle(v21);
      else
        ResultFromLastError();
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v27);
  return 0;
}

```

## disassembly

```asm
0x1800e6594  push    rbx
0x1800e6596  push    rsi
0x1800e6597  push    rdi
0x1800e6598  push    r14
0x1800e659a  sub     rsp, 0B8h
0x1800e65a1  mov     rax, cs:__security_cookie
0x1800e65a8  xor     rax, rsp
0x1800e65ab  mov     [rsp+0D8h+var_38], rax
0x1800e65b3  xor     ebx, ebx
0x1800e65b5  mov     [rsp+0D8h+var_68], ebx
0x1800e65b9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e65bd  mov     [rsp+0D8h+var_60], rsi
0x1800e65c2  lea     rcx, [rsp+0D8h+var_68]; this
0x1800e65c7  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1800e65cc  nop
0x1800e65cd  xor     r9d, r9d; Context
0x1800e65d0  xor     r8d, r8d; Parameter
0x1800e65d3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800e65da  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800e65e1  call    cs:__imp_InitOnceExecuteOnce
0x1800e65e7  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1800e65ed  jz      loc_1800E67F5
0x1800e65f3  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800e65f8  test    rax, rax
0x1800e65fb  jz      loc_1800E67F5
0x1800e6601  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800e6606  mov     rdi, rax
0x1800e6609  mov     [rsp+0D8h+var_78], rax
0x1800e660e  mov     rdx, rax
0x1800e6611  lea     rcx, [rsp+0D8h+lpSubKey]
0x1800e6619  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800e661e  nop
0x1800e661f  lea     r8d, [rbx+22h]
0x1800e6623  lea     rdx, aSoftwareMicros_14; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1800e662a  lea     rcx, [rsp+0D8h+lpSubKey]; Src
0x1800e6632  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e6637  mov     [rsp+0D8h+hkey], rbx
0x1800e663c  lea     rcx, [rsp+0D8h+hkey]
0x1800e6641  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800e6646  lea     rdx, [rsp+0D8h+lpSubKey]
0x1800e664e  cmp     [rsp+0D8h+var_40], 7
0x1800e6657  cmova   rdx, [rsp+0D8h+lpSubKey]; lpSubKey
0x1800e6660  mov     [rsp+0D8h+lpdwDisposition], rbx; lpdwDisposition
0x1800e6665  mov     [rsp+0D8h+phkResult], rax; phkResult
0x1800e666a  mov     [rsp+0D8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800e666f  mov     [rsp+0D8h+samDesired], 0F003Fh; samDesired
0x1800e6677  mov     [rsp+0D8h+dwOptions], ebx; unsigned int
0x1800e667b  xor     r9d, r9d; lpClass
0x1800e667e  xor     r8d, r8d; Reserved
0x1800e6681  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800e6688  call    cs:__imp_RegCreateKeyExW
0x1800e668e  mov     rcx, [rsp+0D8h]; this
0x1800e6696  test    eax, eax
0x1800e6698  jz      short loc_1800E66AE
0x1800e669a  mov     r9d, eax; char *
0x1800e669d  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e66a4  mov     edx, 0F7h; void *
0x1800e66a9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e66ae  mov     [rsp+0D8h+pvData], ebx
0x1800e66b2  mov     r9d, 4; dwType
0x1800e66b8  mov     [rsp+0D8h+samDesired], r9d; cbData
0x1800e66bd  lea     rax, [rsp+0D8h+pvData]
0x1800e66c2  mov     qword ptr [rsp+0D8h+dwOptions], rax; unsigned int
0x1800e66c7  lea     r8, pszValue; "SetupCompletedSuccessfully"
0x1800e66ce  xor     edx, edx; pszSubKey
0x1800e66d0  mov     rcx, [rsp+0D8h+hkey]; hkey
0x1800e66d5  call    cs:__imp_SHSetValueW
0x1800e66db  mov     rcx, [rsp+0D8h]; this
0x1800e66e3  test    eax, eax
0x1800e66e5  jz      short loc_1800E66FC
0x1800e66e7  mov     r9d, eax; char *
0x1800e66ea  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e66f1  mov     edx, 0FBh; void *
0x1800e66f6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e66fc  lea     rcx, [rsp+0D8h+hkey]
0x1800e6701  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e6706  nop
0x1800e6707  lea     rcx, [rsp+0D8h+lpSubKey]; this
0x1800e670f  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800e6714  nop
0x1800e6715  jmp     short loc_1800E6722
0x1800e6717  xor     ebx, ebx
0x1800e6719  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e671d  mov     rdi, [rsp+0D8h+var_78]
0x1800e6722  mov     rax, rsi
0x1800e6725  inc     rax
0x1800e6728  cmp     [rdi+rax*2], bx
0x1800e672c  jnz     short loc_1800E6725
0x1800e672e  lea     r14, [rax+1]
0x1800e6732  mov     eax, 2
0x1800e6737  mul     r14
0x1800e673a  cmovb   rax, rsi
0x1800e673e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e6745  mov     rcx, rax; unsigned __int64
0x1800e6748  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800e674d  mov     r11, rax
0x1800e6750  mov     [rsp+0D8h+hkey], rax
0x1800e6755  test    rax, rax
0x1800e6758  jnz     short loc_1800E6769
0x1800e675a  mov     edi, 8007000Eh
0x1800e675f  mov     r9d, edi
0x1800e6762  mov     edx, 101h
0x1800e6767  jmp     short loc_1800E6785
0x1800e6769  mov     r8, rdi; wchar_t *
0x1800e676c  mov     rdx, r14; unsigned __int64
0x1800e676f  mov     rcx, r11; wchar_t *
0x1800e6772  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800e6777  mov     edi, eax
0x1800e6779  test    eax, eax
0x1800e677b  jns     short loc_1800E67B5
0x1800e677d  mov     r9d, eax; char *
0x1800e6780  mov     edx, 103h; void *
0x1800e6785  lea     r8, aOnecoreuapBase_145; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800e678c  mov     rcx, [rsp+0D8h]; this
0x1800e6794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6799  lea     rcx, [rsp+0D8h+hkey]
0x1800e679e  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800e67a3  nop
0x1800e67a4  lea     rcx, [rsp+0D8h+var_68]; this
0x1800e67a9  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800e67ae  mov     eax, edi
0x1800e67b0  jmp     loc_1800E68C4
0x1800e67b5  mov     [rsp+0D8h+hkey], rbx
0x1800e67ba  mov     qword ptr [rsp+0D8h+samDesired], rbx; lpThreadId
0x1800e67bf  mov     [rsp+0D8h+dwOptions], ebx; dwCreationFlags
0x1800e67c3  mov     r9, r11; lpParameter
0x1800e67c6  lea     r8, ResetUserCatalog; lpStartAddress
0x1800e67cd  xor     edx, edx; dwStackSize
0x1800e67cf  xor     ecx, ecx; lpThreadAttributes
0x1800e67d1  call    cs:__imp_CreateThread
0x1800e67d7  mov     [rsp+0D8h+var_78], rax
0x1800e67dc  lea     rcx, [rsp+0D8h+var_78]
0x1800e67e1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e67e6  lea     rcx, [rsp+0D8h+hkey]
0x1800e67eb  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800e67f0  jmp     loc_1800E68B8
0x1800e67f5  mov     [rsp+0D8h+hkey], rbx
0x1800e67fa  lea     rax, [rsp+0D8h+hkey]
0x1800e67ff  mov     qword ptr [rsp+0D8h+samDesired], rax; HKEY *
0x1800e6804  mov     [rsp+0D8h+dwOptions], 0F003Fh; unsigned int
0x1800e680c  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x1800e6813  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800e681a  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1800e681f  test    eax, eax
0x1800e6821  jle     short loc_1800E682D
0x1800e6823  movzx   eax, ax
0x1800e6826  or      eax, 80070000h
0x1800e682b  test    eax, eax
0x1800e682d  js      short loc_1800E686B
0x1800e682f  mov     [rsp+0D8h+pvData], 0Dh
0x1800e6837  mov     r9d, 4; dwType
0x1800e683d  mov     [rsp+0D8h+samDesired], r9d; cbData
0x1800e6842  lea     rax, [rsp+0D8h+pvData]
0x1800e6847  mov     qword ptr [rsp+0D8h+dwOptions], rax; pvData
0x1800e684c  lea     r8, aRebuildindex; "RebuildIndex"
0x1800e6853  xor     edx, edx; pszSubKey
0x1800e6855  mov     rcx, [rsp+0D8h+hkey]; hkey
0x1800e685a  call    cs:__imp_SHSetValueW
0x1800e6860  mov     rcx, [rsp+0D8h+hkey]; hKey
0x1800e6865  call    cs:__imp_RegCloseKey
0x1800e686b  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1800e6871  jnz     short loc_1800E68B8
0x1800e6873  mov     [rsp+0D8h+pvData], ebx
0x1800e6877  lea     rax, [rsp+0D8h+pvData]
0x1800e687c  mov     qword ptr [rsp+0D8h+samDesired], rax; lpThreadId
0x1800e6881  mov     [rsp+0D8h+dwOptions], ebx; dwCreationFlags
0x1800e6885  xor     r9d, r9d; lpParameter
0x1800e6888  lea     r8, ShutdownSelfThread; lpStartAddress
0x1800e688f  xor     edx, edx; dwStackSize
0x1800e6891  xor     ecx, ecx; lpThreadAttributes
0x1800e6893  call    cs:__imp_CreateThread
0x1800e6899  test    rax, rax
0x1800e689c  jz      short loc_1800E68A9
0x1800e689e  mov     rcx, rax; hObject
0x1800e68a1  call    cs:__imp_CloseHandle
0x1800e68a7  jmp     short loc_1800E68AE
0x1800e68a9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800e68ae  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1800e68b8  lea     rcx, [rsp+0D8h+var_68]; this
0x1800e68bd  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1800e68c2  xor     eax, eax
0x1800e68c4  mov     rcx, [rsp+0D8h+var_38]
0x1800e68cc  xor     rcx, rsp; StackCookie
0x1800e68cf  call    __security_check_cookie
0x1800e68d4  add     rsp, 0B8h
0x1800e68db  pop     r14
0x1800e68dd  pop     rdi
0x1800e68de  pop     rsi
0x1800e68df  pop     rbx
0x1800e68e0  retn
```

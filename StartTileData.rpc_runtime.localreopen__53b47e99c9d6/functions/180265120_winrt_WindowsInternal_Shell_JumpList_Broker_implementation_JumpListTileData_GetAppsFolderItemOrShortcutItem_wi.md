# winrt::WindowsInternal::Shell::JumpList::Broker::implementation::JumpListTileData::GetAppsFolderItemOrShortcutItem(winrt::hstring const &,bool,winrt::hstring const &)

- ea: `0x180265120`
- end: `0x18026546d`
- name: `?GetAppsFolderItemOrShortcutItem@JumpListTileData@implementation@Broker@JumpList@Shell@WindowsInternal@winrt@@CA?AV?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@AEBUhstring@7@_N0@Z`
- size: `845`
- prototype: `__int64 __fastcall(int, winrt::hstring *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bb94`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18002edec`
- `0x180050efc`
- `0x1800bfce0`
- `0x1800fbbcc`
- `0x18010a668`
- `0x180115e7c`
- `0x180161204`
- `0x18019804c`
- `0x1801acee0`
- `0x18020c3de`
- `0x180260604`
- `0x180265120`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18026538a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18026538a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180265262`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180265262`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026537f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026537f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180265364`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180265364`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180265175`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180265175`
- `ext-ms-win-shell-shell32-l1-2-0!SHCreateItemInKnownFolder` at `0x1802651b3`
- `ext-ms-win-shell-shell32-l1-2-0!SHCreateItemInKnownFolder` at `0x1802651b3`

## string_xrefs

- `0x18026522f`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x1802653b7`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x1802653cc`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x180265407`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x18026541c`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x180265431`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x180265446`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`
- `0x18026545b`: `shellcommon\shell\tiles\jumplist\broker\jumplisttiledata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void **__fastcall winrt::WindowsInternal::Shell::JumpList::Broker::implementation::JumpListTileData::GetAppsFolderItemOrShortcutItem(
        void **a1,
        winrt::hstring *this,
        char a3,
        winrt::hstring *a4)
{
  const WCHAR *v7; // rax
  const WCHAR *v8; // rax
  HRESULT v9; // eax
  int v10; // r8d
  int v11; // eax
  int FailIf; // eax
  const struct _GUID *v13; // rdx
  HRESULT Instance; // eax
  LPCITEMIDLIST v15; // rdi
  __int64 (__fastcall *v16)(LPCITEMIDLIST, const unsigned __int16 *, void **); // r14
  void *v17; // rcx
  const unsigned __int16 *v18; // rax
  int v19; // eax
  void *v20; // rcx
  int ObjectW; // eax
  int v22; // eax
  void *v23; // rcx
  HRESULT v24; // eax
  ITEMIDLIST *v25; // rcx
  const struct winrt::impl::slim_source_location *v27; // rax
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int ppvb; // [rsp+20h] [rbp-60h]
  __int64 v31; // [rsp+38h] [rbp-48h] BYREF
  __int128 v32; // [rsp+40h] [rbp-40h] BYREF
  int v33; // [rsp+50h] [rbp-30h]
  PROPVARIANT pvar[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  LPCITEMIDLIST pidl; // [rsp+C8h] [rbp+48h] BYREF

  *a1 = 0;
  if ( *(_QWORD *)a4 )
  {
    *a1 = 0;
    v7 = winrt::hstring::c_str(a4);
    SHCreateItemFromParsingName(v7, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a1);
  }
  if ( !*a1 )
  {
    if ( !*(_QWORD *)this )
    {
      v27 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(&v32);
      winrt::hresult_invalid_argument::hresult_invalid_argument((winrt::hresult_invalid_argument *)pvar, v27);
      throw (winrt::hresult_invalid_argument *)pvar;
    }
    *a1 = 0;
    v8 = winrt::hstring::c_str(this);
    v9 = SHCreateItemInKnownFolder(&FOLDERID_AppsFolder, 0x4000u, v8, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a1);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    if ( a3 )
    {
      v31 = 0;
      v11 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(
              (unsigned int)&v31,
              (unsigned int)*a1,
              v10,
              (unsigned int)&PKEY_AppUserModel_BestShortcut,
              1);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
          (const char *)(unsigned int)v11,
          ppva);
      LOWORD(pvar[0]) = 0;
      v32 = PKEY_AppUserModel_BestShortcut;
      v33 = 10;
      FailIf = wil::PropertyStoreHelperBase<IPropertyStore>::GetFailIfEmpty<_tagpropertykey>(&v31, &v32, pvar);
      if ( FailIf >= 0 )
      {
        if ( LOWORD(pvar[0]) == 13 )
        {
          v20 = *a1;
          *a1 = 0;
          if ( v20 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
          ObjectW = wil::PropVariant::GetObjectW((wil::PropVariant *)pvar, v13, a1);
          if ( ObjectW < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x14E,
              (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
              (const char *)(unsigned int)ObjectW,
              ppva);
        }
        else
        {
          pidl = 0;
          *(_QWORD *)&v32 = &pidl;
          *((_QWORD *)&v32 + 1) = 0;
          LOBYTE(v33) = 1;
          v22 = PropVariantToIDList(pvar, (char *)&v32 + 8);
          if ( v22 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x154,
              (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
              (const char *)(unsigned int)v22,
              ppva);
          wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v32);
          v23 = *a1;
          *a1 = 0;
          if ( v23 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
          v24 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a1);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x155,
              (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
              (const char *)(unsigned int)v24,
              ppva);
          v25 = (ITEMIDLIST *)pidl;
          pidl = 0;
          if ( v25 )
            CoTaskMemFree(v25);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
          (const char *)(unsigned int)FailIf,
          ppva);
        pidl = 0;
        Instance = CoCreateInstance(
                     &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
                     0,
                     3u,
                     &GUID_de25675a_72de_44b4_9373_05170450c140,
                     (LPVOID *)&pidl);
        if ( Instance < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x15C,
            (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
            (const char *)(unsigned int)Instance,
            ppvb);
        v15 = pidl;
        v16 = *(__int64 (__fastcall **)(LPCITEMIDLIST, const unsigned __int16 *, void **))(*(_QWORD *)&pidl->mkid.cb
                                                                                         + 64LL);
        v17 = *a1;
        *a1 = 0;
        if ( v17 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
        v18 = winrt::hstring::c_str(this);
        v19 = v16(v15, v18, a1);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"shellcommon\\shell\\tiles\\jumplist\\broker\\jumplisttiledata.cpp",
            (const char *)(unsigned int)v19,
            ppvb);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&pidl);
      }
      PropVariantClear(pvar);
      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>::~ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>(&v31);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180265120  mov     [rsp-28h+arg_8], rbx
0x180265125  mov     [rsp-28h+arg_0], rcx
0x18026512a  push    rbp
0x18026512b  push    rsi
0x18026512c  push    rdi
0x18026512d  push    r14
0x18026512f  push    r15
0x180265131  mov     rbp, rsp
0x180265134  sub     rsp, 80h
0x18026513b  mov     dil, r8b
0x18026513e  mov     rsi, rdx
0x180265141  mov     rbx, rcx
0x180265144  xor     r15d, r15d
0x180265147  mov     [rbp+var_50], r15d
0x18026514b  mov     [rcx], r15
0x18026514e  lea     r14d, [r15+1]
0x180265152  mov     [rbp+var_50], r14d
0x180265156  cmp     [r9], r15
0x180265159  jz      short loc_18026517B
0x18026515b  mov     [rcx], r15
0x18026515e  mov     rcx, r9; this
0x180265161  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180265166  mov     r9, rbx; ppv
0x180265169  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180265170  xor     edx, edx; pbc
0x180265172  mov     rcx, rax; pszPath
0x180265175  call    cs:__imp_SHCreateItemFromParsingName
0x18026517b  cmp     [rbx], r15
0x18026517e  jnz     loc_18026539A
0x180265184  cmp     [rsi], r15
0x180265187  jz      loc_1802653DE
0x18026518d  mov     [rbx], r15
0x180265190  mov     rcx, rsi; this
0x180265193  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180265198  mov     qword ptr [rsp+80h+ppv], rbx; int
0x18026519d  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1802651a4  mov     r8, rax; pszItem
0x1802651a7  mov     edx, 4000h; dwKFFlags
0x1802651ac  lea     rcx, FOLDERID_AppsFolder; kfid
0x1802651b3  call    cs:__imp_SHCreateItemInKnownFolder
0x1802651b9  mov     rcx, [rbp+28h]; this
0x1802651bd  test    eax, eax
0x1802651bf  js      loc_180265404
0x1802651c5  test    dil, dil
0x1802651c8  jz      loc_18026539A
0x1802651ce  mov     [rbp+var_48], r15
0x1802651d2  mov     [rsp+80h+ppv], r14d; int
0x1802651d7  lea     r9, PKEY_AppUserModel_BestShortcut
0x1802651de  mov     rdx, [rbx]
0x1802651e1  lea     rcx, [rbp+var_48]
0x1802651e5  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x1802651ea  mov     rcx, [rbp+28h]; this
0x1802651ee  test    eax, eax
0x1802651f0  js      loc_180265419
0x1802651f6  mov     word ptr [rbp+pvar], r15w
0x1802651fb  movups  xmm0, cs:PKEY_AppUserModel_BestShortcut
0x180265202  movaps  [rbp+var_40], xmm0
0x180265206  mov     eax, cs:dword_18041CFB8
0x18026520c  mov     [rbp+var_30], eax
0x18026520f  lea     r8, [rbp+pvar]
0x180265213  lea     rdx, [rbp+var_40]
0x180265217  lea     rcx, [rbp+var_48]
0x18026521b  call    ??$GetFailIfEmpty@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetFailIfEmpty<_tagpropertykey>(_tagpropertykey,tagPROPVARIANT *)
0x180265220  mov     rcx, [rbp+28h]; this
0x180265224  test    eax, eax
0x180265226  jns     loc_1802652CA
0x18026522c  mov     r9d, eax; char *
0x18026522f  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x180265236  mov     edx, 149h; void *
0x18026523b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180265240  nop
0x180265241  mov     [rbp+pidl], r15
0x180265245  lea     rax, [rbp+pidl]
0x180265249  mov     qword ptr [rsp+80h+ppv], rax; int
0x18026524e  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180265255  xor     edx, edx; pUnkOuter
0x180265257  lea     r8d, [rdx+3]; dwClsContext
0x18026525b  lea     rcx, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x180265262  call    cs:__imp_CoCreateInstance
0x180265268  mov     rcx, [rbp+28h]; this
0x18026526c  test    eax, eax
0x18026526e  js      loc_18026542E
0x180265274  mov     rdi, [rbp+pidl]
0x180265278  mov     rax, [rdi]
0x18026527b  mov     r14, [rax+40h]
0x18026527f  mov     rcx, [rbx]
0x180265282  mov     [rbx], r15
0x180265285  test    rcx, rcx
0x180265288  jz      short loc_180265297
0x18026528a  mov     rax, [rcx]
0x18026528d  mov     rax, [rax+10h]
0x180265291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180265296  nop
0x180265297  mov     rcx, rsi; this
0x18026529a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18026529f  mov     r8, rbx
0x1802652a2  mov     rdx, rax
0x1802652a5  mov     rcx, rdi
0x1802652a8  mov     rax, r14
0x1802652ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802652b0  mov     rcx, [rbp+28h]; this
0x1802652b4  test    eax, eax
0x1802652b6  js      loc_180265443
0x1802652bc  lea     rcx, [rbp+pidl]; void *
0x1802652c0  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1802652c5  jmp     loc_180265386
0x1802652ca  mov     eax, 0Dh
0x1802652cf  cmp     ax, word ptr [rbp+pvar]
0x1802652d3  jnz     short loc_180265307
0x1802652d5  mov     rcx, [rbx]
0x1802652d8  mov     [rbx], r15
0x1802652db  test    rcx, rcx
0x1802652de  jz      short loc_1802652ED
0x1802652e0  mov     rax, [rcx]
0x1802652e3  mov     rax, [rax+10h]
0x1802652e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802652ec  nop
0x1802652ed  mov     r8, rbx; void **
0x1802652f0  lea     rcx, [rbp+pvar]; this
0x1802652f4  call    ?GetObjectW@PropVariant@wil@@QEBAJAEBU_GUID@@PEAPEAX@Z; wil::PropVariant::GetObjectW(_GUID const &,void * *)
0x1802652f9  mov     rcx, [rbp+28h]; this
0x1802652fd  test    eax, eax
0x1802652ff  js      loc_1802653C9
0x180265305  jmp     short loc_180265386
0x180265307  mov     [rbp+pidl], r15
0x18026530b  lea     rax, [rbp+pidl]
0x18026530f  mov     qword ptr [rbp+var_40], rax
0x180265313  mov     qword ptr [rbp+var_40+8], r15
0x180265317  mov     byte ptr [rbp+var_30], r14b
0x18026531b  lea     rdx, [rbp+var_40+8]
0x18026531f  lea     rcx, [rbp+pvar]
0x180265323  call    PropVariantToIDList
0x180265328  mov     rcx, [rbp+28h]; this
0x18026532c  test    eax, eax
0x18026532e  js      loc_180265458
0x180265334  lea     rcx, [rbp+var_40]
0x180265338  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18026533d  nop
0x18026533e  mov     rcx, [rbx]
0x180265341  mov     [rbx], r15
0x180265344  test    rcx, rcx
0x180265347  jz      short loc_180265356
0x180265349  mov     rax, [rcx]
0x18026534c  mov     rax, [rax+10h]
0x180265350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180265355  nop
0x180265356  mov     r8, rbx; ppv
0x180265359  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180265360  mov     rcx, [rbp+pidl]; pidl
0x180265364  call    cs:__imp_SHCreateItemFromIDList
0x18026536a  mov     rcx, [rbp+28h]; this
0x18026536e  test    eax, eax
0x180265370  js      short loc_1802653B4
0x180265372  mov     rcx, [rbp+pidl]; pv
0x180265376  mov     [rbp+pidl], r15
0x18026537a  test    rcx, rcx
0x18026537d  jz      short loc_180265386
0x18026537f  call    cs:__imp_CoTaskMemFree
0x180265385  nop
0x180265386  lea     rcx, [rbp+pvar]; pvar
0x18026538a  call    cs:__imp_PropVariantClear
0x180265390  nop
0x180265391  lea     rcx, [rbp+var_48]; void *
0x180265395  call    ??1?$ComPtr@UITileImageResourceOptions@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>::~ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>(void)
0x18026539a  mov     rax, rbx
0x18026539d  mov     rbx, [rsp+80h+arg_8]
0x1802653a5  add     rsp, 80h
0x1802653ac  pop     r15
0x1802653ae  pop     r14
0x1802653b0  pop     rdi
0x1802653b1  pop     rsi
0x1802653b2  pop     rbp
0x1802653b3  retn
0x1802653b4  mov     r9d, eax; char *
0x1802653b7  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x1802653be  mov     edx, 155h; void *
0x1802653c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802653c9  mov     r9d, eax; char *
0x1802653cc  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x1802653d3  mov     edx, 14Eh; void *
0x1802653d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802653de  lea     rcx, [rbp+var_40]
0x1802653e2  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1802653e7  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1802653ea  lea     rcx, [rbp+pvar]; this
0x1802653ee  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::impl::slim_source_location const &)
0x1802653f3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1802653fa  lea     rcx, [rbp+pvar]; pExceptionObject
0x1802653fe  call    _CxxThrowException_0
0x180265404  mov     r9d, eax; char *
0x180265407  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x18026540e  mov     edx, 141h; void *
0x180265413  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180265419  mov     r9d, eax; char *
0x18026541c  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x180265423  mov     edx, 146h; void *
0x180265428  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18026542e  mov     r9d, eax; char *
0x180265431  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x180265438  mov     edx, 15Ch; void *
0x18026543d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180265443  mov     r9d, eax; char *
0x180265446  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x18026544d  mov     edx, 15Dh; void *
0x180265452  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180265458  mov     r9d, eax; char *
0x18026545b  lea     r8, aShellcommonShe_133; "shellcommon\\shell\\tiles\\jumplist\\br"...
0x180265462  mov     edx, 154h; void *
0x180265467  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

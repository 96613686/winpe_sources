# DebugWindowBehavior::ApplyTaskbarCustomizationProperties(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x180022958`
- end: `0x180022c90`
- name: `?ApplyTaskbarCustomizationProperties@DebugWindowBehavior@@AEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `824`
- prototype: `void __fastcall(DebugWindowBehavior *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800274d0`
- `0x180027b10`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000d810`
- `0x18000e1a4`
- `0x18000e1c8`
- `0x180017024`
- `0x180017514`
- `0x18001a8cc`
- `0x18001f48c`
- `0x18001fa94`
- `0x180020cac`
- `0x1800218bc`
- `0x180021bc4`
- `0x180021ff4`
- `0x18002210c`
- `0x180022958`
- `0x180055d04`
- `0x180055dd0`
- `0x18005a010`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180022a0f`
- `USER32!GetWindowThreadProcessId` at `0x180022a0f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022a24`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022a24`
- `ext-ms-win-shell-shell32-l1-2-0!SHGetPropertyStoreForWindow` at `0x180022b25`
- `ext-ms-win-shell-shell32-l1-2-0!SHGetPropertyStoreForWindow` at `0x180022b25`

## string_xrefs

- `0x180022c7e`: `pcshell\shell\uxframe\dll\DebugWindowBehavior.h`
- `0x180022ac4`: `PreventTaskbarPinning`
- `0x180022a99`: `TaskbarDisplayNameResource`
- `0x180022a6e`: `TaskbarIconResource`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall DebugWindowBehavior::ApplyTaskbarCustomizationProperties(
        HWND *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  CallerIdentity *v4; // rbx
  unsigned __int16 **v5; // r8
  unsigned __int16 **v6; // r8
  char v7; // di
  HRESULT v8; // eax
  __int64 v9; // rbx
  const wchar_t *v10; // rax
  const wchar_t *v11; // rax
  const wchar_t *v12; // rax
  int v13; // [rsp+20h] [rbp-60h] BYREF
  const wchar_t *v14; // [rsp+28h] [rbp-58h]
  HANDLE v15; // [rsp+38h] [rbp-48h] BYREF
  DWORD dwProcessId; // [rsp+40h] [rbp-40h] BYREF
  struct HWND__ v17[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v18; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h] BYREF
  void *ppv; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  winrt::hstring::hstring((winrt::hstring *)v17, L"CustomAppId");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v18, v17, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v17);
  if ( !v18 )
  {
    winrt::hstring::hstring((winrt::hstring *)&dwProcessId, L"CloneAumidFromWindow");
    v4 = (CallerIdentity *)ValueSetUtils::get_value_or<__int64,winrt::Windows::Foundation::Collections::ValueSet>(
                             &dwProcessId,
                             a2);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&dwProcessId);
    *(_QWORD *)&v17[0].unused = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      v17,
      0);
    CallerIdentity::GetWeakWindowAppId(v4, v17, v5);
    if ( *(_QWORD *)&v17[0].unused )
      goto LABEL_6;
    dwProcessId = 0;
    if ( GetWindowThreadProcessId((HWND)v4, &dwProcessId) )
    {
      v15 = OpenProcess(0x1000u, 0, dwProcessId);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        v17,
        0);
      CallerIdentity::GetProcessAppIdWithAppResolverFallback(v15, v17, v6);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
    }
    if ( *(_QWORD *)&v17[0].unused )
LABEL_6:
      winrt::hstring::operator=(&v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v17);
  }
  winrt::hstring::hstring((winrt::hstring *)v17, L"TaskbarIconResource");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v20, v17, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v17);
  winrt::hstring::hstring((winrt::hstring *)v17, L"TaskbarDisplayNameResource");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v19, v17, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v17);
  winrt::hstring::hstring((winrt::hstring *)v17, L"PreventTaskbarPinning");
  v7 = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(v17, a2, 0);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v17);
  if ( v18 || v20 || v19 || v7 )
  {
    ppv = 0;
    v8 = SHGetPropertyStoreForWindow(this[5], &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\DebugWindowBehavior.h",
        (const char *)(unsigned int)v8,
        v13);
    *(_QWORD *)&v17[0].unused = 0;
    wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)v17, (struct IPropertyStore *)ppv);
    v9 = *(_QWORD *)&v17[0].unused;
    if ( v7 )
    {
      LOWORD(v13) = 11;
      LOWORD(v14) = -1;
      (*(void (__fastcall **)(_QWORD, const PROPERTYKEY *, int *))(**(_QWORD **)&v17[0].unused + 48LL))(
        *(_QWORD *)&v17[0].unused,
        &PKEY_AppUserModel_PreventPinning,
        &v13);
    }
    if ( v20 )
    {
      v10 = winrt::hstring::c_str((winrt::hstring *)&v20);
      LOWORD(v13) = 31;
      v14 = v10;
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v9 + 48LL))(
        v9,
        &PKEY_AppUserModel_RelaunchIconResource,
        &v13);
    }
    if ( v19 )
    {
      v11 = winrt::hstring::c_str((winrt::hstring *)&v19);
      LOWORD(v13) = 31;
      v14 = v11;
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v9 + 48LL))(
        v9,
        &PKEY_AppUserModel_RelaunchDisplayNameResource,
        &v13);
    }
    if ( v18 )
    {
      v12 = winrt::hstring::c_str((winrt::hstring *)&v18);
      LOWORD(v13) = 31;
      v14 = v12;
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v9 + 48LL))(
        v9,
        &PKEY_AppUserModel_ID,
        &v13);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9);
    wil::PropertyStoreHelper::~PropertyStoreHelper((wil::PropertyStoreHelper *)v17);
    wil::com_ptr_t<IServiceProvider,wil::err_exception_policy>::~com_ptr_t<IServiceProvider,wil::err_exception_policy>(&ppv);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v19);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v20);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
}

```

## disassembly

```asm
0x180022958  mov     [rsp-18h+arg_10], rbx
0x18002295d  push    rbp
0x18002295e  push    rsi
0x18002295f  push    rdi
0x180022960  mov     rbp, rsp
0x180022963  sub     rsp, 80h
0x18002296a  mov     rax, cs:__security_cookie
0x180022971  xor     rax, rsp
0x180022974  mov     [rbp+var_10], rax
0x180022978  mov     rdi, rdx
0x18002297b  mov     rsi, rcx
0x18002297e  lea     rdx, aCustomappid; "CustomAppId"
0x180022985  lea     rcx, [rbp+var_38]; this
0x180022989  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002298e  nop
0x18002298f  mov     r8, rdi
0x180022992  lea     rdx, [rbp+var_38]
0x180022996  lea     rcx, [rbp+var_30]
0x18002299a  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002299f  nop
0x1800229a0  lea     rcx, [rbp+var_38]
0x1800229a4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800229a9  cmp     [rbp+var_30], 0
0x1800229ae  jnz     loc_180022A6E
0x1800229b4  lea     rdx, aCloneaumidfrom; "CloneAumidFromWindow"
0x1800229bb  lea     rcx, [rbp+dwProcessId]; this
0x1800229bf  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800229c4  nop
0x1800229c5  mov     rdx, rdi
0x1800229c8  lea     rcx, [rbp+dwProcessId]
0x1800229cc  call    ??$get_value_or@_JUValueSet@Collections@Foundation@Windows@winrt@@@ValueSetUtils@@YA_JAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@2@_J@Z; ValueSetUtils::get_value_or<__int64,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,__int64)
0x1800229d1  mov     rbx, rax
0x1800229d4  lea     rcx, [rbp+dwProcessId]
0x1800229d8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800229dd  mov     qword ptr [rbp+var_38.unused], 0
0x1800229e5  xor     edx, edx
0x1800229e7  lea     rcx, [rbp+var_38]
0x1800229eb  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1800229f0  lea     rdx, [rbp+var_38]; HWND
0x1800229f4  mov     rcx, rbx; this
0x1800229f7  call    ?GetWeakWindowAppId@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetWeakWindowAppId(HWND__ *,ushort * *)
0x1800229fc  mov     rdx, qword ptr [rbp+var_38.unused]
0x180022a00  test    rdx, rdx
0x180022a03  jnz     short loc_180022A5B
0x180022a05  mov     [rbp+dwProcessId], edx
0x180022a08  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180022a0c  mov     rcx, rbx; hWnd
0x180022a0f  call    cs:__imp_GetWindowThreadProcessId
0x180022a15  test    eax, eax
0x180022a17  jz      short loc_180022A52
0x180022a19  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180022a1d  xor     edx, edx; bInheritHandle
0x180022a1f  mov     ecx, 1000h; dwDesiredAccess
0x180022a24  call    cs:__imp_OpenProcess
0x180022a2a  mov     rbx, rax
0x180022a2d  mov     [rbp+var_48], rax
0x180022a31  xor     edx, edx
0x180022a33  lea     rcx, [rbp+var_38]
0x180022a37  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180022a3c  lea     rdx, [rbp+var_38]; void *
0x180022a40  mov     rcx, rbx; Process
0x180022a43  call    ?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)
0x180022a48  nop
0x180022a49  lea     rcx, [rbp+var_48]
0x180022a4d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180022a52  mov     rdx, qword ptr [rbp+var_38.unused]
0x180022a56  test    rdx, rdx
0x180022a59  jz      short loc_180022A65
0x180022a5b  lea     rcx, [rbp+var_30]
0x180022a5f  call    ??4hstring@winrt@@QEAAAEAU01@QEB_W@Z; winrt::hstring::operator=(wchar_t const * const)
0x180022a64  nop
0x180022a65  lea     rcx, [rbp+var_38]
0x180022a69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022a6e  lea     rdx, aTaskbariconres; "TaskbarIconResource"
0x180022a75  lea     rcx, [rbp+var_38]; this
0x180022a79  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022a7e  nop
0x180022a7f  mov     r8, rdi
0x180022a82  lea     rdx, [rbp+var_38]
0x180022a86  lea     rcx, [rbp+var_20]
0x180022a8a  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180022a8f  nop
0x180022a90  lea     rcx, [rbp+var_38]
0x180022a94  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022a99  lea     rdx, aTaskbardisplay; "TaskbarDisplayNameResource"
0x180022aa0  lea     rcx, [rbp+var_38]; this
0x180022aa4  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022aa9  nop
0x180022aaa  mov     r8, rdi
0x180022aad  lea     rdx, [rbp+var_38]
0x180022ab1  lea     rcx, [rbp+var_28]
0x180022ab5  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180022aba  nop
0x180022abb  lea     rcx, [rbp+var_38]
0x180022abf  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022ac4  lea     rdx, aPreventtaskbar; "PreventTaskbarPinning"
0x180022acb  lea     rcx, [rbp+var_38]; this
0x180022acf  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022ad4  nop
0x180022ad5  xor     r8d, r8d
0x180022ad8  mov     rdx, rdi
0x180022adb  lea     rcx, [rbp+var_38]
0x180022adf  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x180022ae4  mov     dil, al
0x180022ae7  lea     rcx, [rbp+var_38]
0x180022aeb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022af0  cmp     [rbp+var_30], 0
0x180022af5  jnz     short loc_180022B0E
0x180022af7  cmp     [rbp+var_20], 0
0x180022afc  jnz     short loc_180022B0E
0x180022afe  cmp     [rbp+var_28], 0
0x180022b03  jnz     short loc_180022B0E
0x180022b05  test    dil, dil
0x180022b08  jz      loc_180022C3F
0x180022b0e  mov     [rbp+ppv], 0
0x180022b16  lea     r8, [rbp+ppv]; ppv
0x180022b1a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180022b21  mov     rcx, [rsi+28h]; hwnd
0x180022b25  call    cs:__imp_SHGetPropertyStoreForWindow
0x180022b2b  mov     rcx, [rbp+18h]; this
0x180022b2f  test    eax, eax
0x180022b31  js      loc_180022C7B
0x180022b37  mov     qword ptr [rbp+var_38.unused], 0
0x180022b3f  mov     rdx, [rbp+ppv]; struct IPropertyStore *
0x180022b43  lea     rcx, [rbp+var_38]; this
0x180022b47  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x180022b4c  nop
0x180022b4d  mov     rbx, qword ptr [rbp+var_38.unused]
0x180022b51  test    dil, dil
0x180022b54  jz      short loc_180022B80
0x180022b56  mov     eax, 0Bh
0x180022b5b  mov     word ptr [rbp+var_60], ax
0x180022b5f  or      eax, 0FFFFFFFFh
0x180022b62  mov     word ptr [rbp+var_58], ax
0x180022b66  mov     rax, [rbx]
0x180022b69  lea     r8, [rbp+var_60]
0x180022b6d  lea     rdx, PKEY_AppUserModel_PreventPinning
0x180022b74  mov     rcx, rbx
0x180022b77  mov     rax, [rax+30h]
0x180022b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b80  mov     edi, 1Fh
0x180022b85  cmp     [rbp+var_20], 0
0x180022b8a  jz      short loc_180022BB7
0x180022b8c  lea     rcx, [rbp+var_20]; this
0x180022b90  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180022b95  mov     word ptr [rbp+var_60], di
0x180022b99  mov     [rbp+var_58], rax
0x180022b9d  mov     rax, [rbx]
0x180022ba0  lea     r8, [rbp+var_60]
0x180022ba4  lea     rdx, PKEY_AppUserModel_RelaunchIconResource
0x180022bab  mov     rcx, rbx
0x180022bae  mov     rax, [rax+30h]
0x180022bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bb7  cmp     [rbp+var_28], 0
0x180022bbc  jz      short loc_180022BE9
0x180022bbe  lea     rcx, [rbp+var_28]; this
0x180022bc2  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180022bc7  mov     word ptr [rbp+var_60], di
0x180022bcb  mov     [rbp+var_58], rax
0x180022bcf  mov     rax, [rbx]
0x180022bd2  lea     r8, [rbp+var_60]
0x180022bd6  lea     rdx, PKEY_AppUserModel_RelaunchDisplayNameResource
0x180022bdd  mov     rcx, rbx
0x180022be0  mov     rax, [rax+30h]
0x180022be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022be9  cmp     [rbp+var_30], 0
0x180022bee  jz      short loc_180022C1B
0x180022bf0  lea     rcx, [rbp+var_30]; this
0x180022bf4  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180022bf9  mov     word ptr [rbp+var_60], di
0x180022bfd  mov     [rbp+var_58], rax
0x180022c01  mov     rax, [rbx]
0x180022c04  lea     r8, [rbp+var_60]
0x180022c08  lea     rdx, PKEY_AppUserModel_ID
0x180022c0f  mov     rcx, rbx
0x180022c12  mov     rax, [rax+30h]
0x180022c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c1b  mov     rax, [rbx]
0x180022c1e  mov     rcx, rbx
0x180022c21  mov     rax, [rax+38h]
0x180022c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c2a  nop
0x180022c2b  lea     rcx, [rbp+var_38]; this
0x180022c2f  call    ??1PropertyStoreHelper@wil@@QEAA@XZ; wil::PropertyStoreHelper::~PropertyStoreHelper(void)
0x180022c34  nop
0x180022c35  lea     rcx, [rbp+ppv]
0x180022c39  call    ??1?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IServiceProvider,wil::err_exception_policy>::~com_ptr_t<IServiceProvider,wil::err_exception_policy>(void)
0x180022c3e  nop
0x180022c3f  lea     rcx, [rbp+var_28]
0x180022c43  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022c48  nop
0x180022c49  lea     rcx, [rbp+var_20]
0x180022c4d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022c52  nop
0x180022c53  lea     rcx, [rbp+var_30]
0x180022c57  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022c5c  mov     rcx, [rbp+var_10]
0x180022c60  xor     rcx, rsp; StackCookie
0x180022c63  call    __security_check_cookie
0x180022c68  mov     rbx, [rsp+80h+arg_10]
0x180022c70  add     rsp, 80h
0x180022c77  pop     rdi
0x180022c78  pop     rsi
0x180022c79  pop     rbp
0x180022c7a  retn
0x180022c7b  mov     r9d, eax; char *
0x180022c7e  lea     r8, aPcshellShellUx_5; "pcshell\\shell\\uxframe\\dll\\DebugWind"...
0x180022c85  mov     edx, 0B9h; void *
0x180022c8a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

# OverlappedWindowBehavior::ApplyTaskbarCustomizationProperties(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x180022c98`
- end: `0x180022eea`
- name: `?ApplyTaskbarCustomizationProperties@OverlappedWindowBehavior@@AEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `594`
- prototype: `void __fastcall(OverlappedWindowBehavior *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027e20`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000d810`
- `0x180017024`
- `0x180017514`
- `0x18001fbcc`
- `0x180020cac`
- `0x1800218bc`
- `0x180021bc4`
- `0x180021ff4`
- `0x1800223d4`
- `0x180022c98`
- `0x18005a010`

## import_xrefs

- `ext-ms-win-shell-shell32-l1-2-0!SHGetPropertyStoreForWindow` at `0x180022d85`
- `ext-ms-win-shell-shell32-l1-2-0!SHGetPropertyStoreForWindow` at `0x180022d85`

## string_xrefs

- `0x180022d96`: `pcshell\shell\uxframe\dll\OverlappedWindowBehavior.h`
- `0x180022d24`: `PreventTaskbarPinning`
- `0x180022cf9`: `TaskbarDisplayNameResource`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall OverlappedWindowBehavior::ApplyTaskbarCustomizationProperties(
        HWND *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  char v4; // si
  HRESULT v5; // eax
  const struct winrt::Windows::Foundation::Collections::ValueSet *v6; // rbx
  const wchar_t *v7; // rax
  const wchar_t *v8; // rax
  const wchar_t *v9; // rax
  __int64 v10; // [rsp+20h] [rbp-50h] BYREF
  __int16 v11; // [rsp+28h] [rbp-48h] BYREF
  const wchar_t *v12; // [rsp+30h] [rbp-40h]
  const struct winrt::Windows::Foundation::Collections::ValueSet *v13; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  void *ppv; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  winrt::hstring::hstring((winrt::hstring *)&v13, L"CustomAppId");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v15, &v13, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v13);
  v13 = a2;
  _lambda_2ac8fe0392921df34437e8d03cccd24f_::operator()(&v13, &v10);
  winrt::hstring::hstring((winrt::hstring *)&v13, L"TaskbarDisplayNameResource");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v14, &v13, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v13);
  winrt::hstring::hstring((winrt::hstring *)&v13, L"PreventTaskbarPinning");
  v4 = ValueSetUtils::get_value_or<bool,winrt::Windows::Foundation::Collections::ValueSet>(&v13, a2, 0);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v13);
  if ( v15 || v10 || v14 || v4 )
  {
    ppv = 0;
    v5 = SHGetPropertyStoreForWindow(this[5], &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\OverlappedWindowBehavior.h",
        (const char *)(unsigned int)v5,
        v10);
    v13 = 0;
    wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&v13, (struct IPropertyStore *)ppv);
    v6 = v13;
    if ( v4 )
    {
      v11 = 11;
      LOWORD(v12) = -1;
      (*(void (__fastcall **)(const struct winrt::Windows::Foundation::Collections::ValueSet *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)v13 + 48LL))(
        v13,
        &PKEY_AppUserModel_PreventPinning,
        &v11);
    }
    if ( v10 )
    {
      v7 = winrt::hstring::c_str((winrt::hstring *)&v10);
      v11 = 31;
      v12 = v7;
      (*(void (__fastcall **)(const struct winrt::Windows::Foundation::Collections::ValueSet *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)v6 + 48LL))(
        v6,
        &PKEY_AppUserModel_RelaunchIconResource,
        &v11);
    }
    if ( v14 )
    {
      v8 = winrt::hstring::c_str((winrt::hstring *)&v14);
      v11 = 31;
      v12 = v8;
      (*(void (__fastcall **)(const struct winrt::Windows::Foundation::Collections::ValueSet *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)v6 + 48LL))(
        v6,
        &PKEY_AppUserModel_RelaunchDisplayNameResource,
        &v11);
    }
    if ( v15 )
    {
      v9 = winrt::hstring::c_str((winrt::hstring *)&v15);
      v11 = 31;
      v12 = v9;
      (*(void (__fastcall **)(const struct winrt::Windows::Foundation::Collections::ValueSet *, const PROPERTYKEY *, __int16 *))(*(_QWORD *)v6 + 48LL))(
        v6,
        &PKEY_AppUserModel_ID,
        &v11);
    }
    (*(void (__fastcall **)(const struct winrt::Windows::Foundation::Collections::ValueSet *))(*(_QWORD *)v6 + 56LL))(v6);
    wil::PropertyStoreHelper::~PropertyStoreHelper((wil::PropertyStoreHelper *)&v13);
    wil::com_ptr_t<IServiceProvider,wil::err_exception_policy>::~com_ptr_t<IServiceProvider,wil::err_exception_policy>(&ppv);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v14);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v10);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v15);
}

```

## disassembly

```asm
0x180022c98  mov     [rsp-18h+arg_10], rbx
0x180022c9d  push    rbp
0x180022c9e  push    rsi
0x180022c9f  push    r14
0x180022ca1  mov     rbp, rsp
0x180022ca4  sub     rsp, 70h
0x180022ca8  mov     rax, cs:__security_cookie
0x180022caf  xor     rax, rsp
0x180022cb2  mov     [rbp+var_10], rax
0x180022cb6  mov     rbx, rdx
0x180022cb9  mov     r14, rcx
0x180022cbc  lea     rdx, aCustomappid; "CustomAppId"
0x180022cc3  lea     rcx, [rbp+var_30]; this
0x180022cc7  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022ccc  nop
0x180022ccd  mov     r8, rbx
0x180022cd0  lea     rdx, [rbp+var_30]
0x180022cd4  lea     rcx, [rbp+var_20]
0x180022cd8  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180022cdd  nop
0x180022cde  lea     rcx, [rbp+var_30]
0x180022ce2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022ce7  mov     [rbp+var_30], rbx
0x180022ceb  lea     rdx, [rbp+var_50]
0x180022cef  lea     rcx, [rbp+var_30]
0x180022cf3  call    ??R_lambda_2ac8fe0392921df34437e8d03cccd24f_@@QEBA?AUhstring@winrt@@XZ; _lambda_2ac8fe0392921df34437e8d03cccd24f_::operator()(void)
0x180022cf8  nop
0x180022cf9  lea     rdx, aTaskbardisplay; "TaskbarDisplayNameResource"
0x180022d00  lea     rcx, [rbp+var_30]; this
0x180022d04  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022d09  nop
0x180022d0a  mov     r8, rbx
0x180022d0d  lea     rdx, [rbp+var_30]
0x180022d11  lea     rcx, [rbp+var_28]
0x180022d15  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180022d1a  nop
0x180022d1b  lea     rcx, [rbp+var_30]
0x180022d1f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022d24  lea     rdx, aPreventtaskbar; "PreventTaskbarPinning"
0x180022d2b  lea     rcx, [rbp+var_30]; this
0x180022d2f  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022d34  nop
0x180022d35  xor     r8d, r8d
0x180022d38  mov     rdx, rbx
0x180022d3b  lea     rcx, [rbp+var_30]
0x180022d3f  call    ??$get_value_or@_NUValueSet@Collections@Foundation@Windows@winrt@@@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@2@_N@Z; ValueSetUtils::get_value_or<bool,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x180022d44  mov     sil, al
0x180022d47  lea     rcx, [rbp+var_30]
0x180022d4b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022d50  cmp     [rbp+var_20], 0
0x180022d55  jnz     short loc_180022D6E
0x180022d57  cmp     [rbp+var_50], 0
0x180022d5c  jnz     short loc_180022D6E
0x180022d5e  cmp     [rbp+var_28], 0
0x180022d63  jnz     short loc_180022D6E
0x180022d65  test    sil, sil
0x180022d68  jz      loc_180022EB0
0x180022d6e  mov     [rbp+ppv], 0
0x180022d76  lea     r8, [rbp+ppv]; ppv
0x180022d7a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180022d81  mov     rcx, [r14+28h]; hwnd
0x180022d85  call    cs:__imp_SHGetPropertyStoreForWindow
0x180022d8b  mov     rcx, [rbp+18h]; this
0x180022d8f  test    eax, eax
0x180022d91  jns     short loc_180022DA8
0x180022d93  mov     r9d, eax; char *
0x180022d96  lea     r8, aPcshellShellUx_10; "pcshell\\shell\\uxframe\\dll\\Overlappe"...
0x180022d9d  mov     edx, 0F6h; void *
0x180022da2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022da8  mov     [rbp+var_30], 0
0x180022db0  mov     rdx, [rbp+ppv]; struct IPropertyStore *
0x180022db4  lea     rcx, [rbp+var_30]; this
0x180022db8  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x180022dbd  nop
0x180022dbe  mov     rbx, [rbp+var_30]
0x180022dc2  test    sil, sil
0x180022dc5  jz      short loc_180022DF1
0x180022dc7  mov     eax, 0Bh
0x180022dcc  mov     [rbp+var_48], ax
0x180022dd0  or      eax, 0FFFFFFFFh
0x180022dd3  mov     word ptr [rbp+var_40], ax
0x180022dd7  mov     rax, [rbx]
0x180022dda  lea     r8, [rbp+var_48]
0x180022dde  lea     rdx, PKEY_AppUserModel_PreventPinning
0x180022de5  mov     rcx, rbx
0x180022de8  mov     rax, [rax+30h]
0x180022dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022df1  mov     esi, 1Fh
0x180022df6  cmp     [rbp+var_50], 0
0x180022dfb  jz      short loc_180022E28
0x180022dfd  lea     rcx, [rbp+var_50]; this
0x180022e01  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180022e06  mov     [rbp+var_48], si
0x180022e0a  mov     [rbp+var_40], rax
0x180022e0e  mov     rax, [rbx]
0x180022e11  lea     r8, [rbp+var_48]
0x180022e15  lea     rdx, PKEY_AppUserModel_RelaunchIconResource
0x180022e1c  mov     rcx, rbx
0x180022e1f  mov     rax, [rax+30h]
0x180022e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e28  cmp     [rbp+var_28], 0
0x180022e2d  jz      short loc_180022E5A
0x180022e2f  lea     rcx, [rbp+var_28]; this
0x180022e33  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180022e38  mov     [rbp+var_48], si
0x180022e3c  mov     [rbp+var_40], rax
0x180022e40  mov     rax, [rbx]
0x180022e43  lea     r8, [rbp+var_48]
0x180022e47  lea     rdx, PKEY_AppUserModel_RelaunchDisplayNameResource
0x180022e4e  mov     rcx, rbx
0x180022e51  mov     rax, [rax+30h]
0x180022e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e5a  cmp     [rbp+var_20], 0
0x180022e5f  jz      short loc_180022E8C
0x180022e61  lea     rcx, [rbp+var_20]; this
0x180022e65  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180022e6a  mov     [rbp+var_48], si
0x180022e6e  mov     [rbp+var_40], rax
0x180022e72  mov     rax, [rbx]
0x180022e75  lea     r8, [rbp+var_48]
0x180022e79  lea     rdx, PKEY_AppUserModel_ID
0x180022e80  mov     rcx, rbx
0x180022e83  mov     rax, [rax+30h]
0x180022e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e8c  mov     rax, [rbx]
0x180022e8f  mov     rcx, rbx
0x180022e92  mov     rax, [rax+38h]
0x180022e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e9b  nop
0x180022e9c  lea     rcx, [rbp+var_30]; this
0x180022ea0  call    ??1PropertyStoreHelper@wil@@QEAA@XZ; wil::PropertyStoreHelper::~PropertyStoreHelper(void)
0x180022ea5  nop
0x180022ea6  lea     rcx, [rbp+ppv]
0x180022eaa  call    ??1?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IServiceProvider,wil::err_exception_policy>::~com_ptr_t<IServiceProvider,wil::err_exception_policy>(void)
0x180022eaf  nop
0x180022eb0  lea     rcx, [rbp+var_28]
0x180022eb4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022eb9  nop
0x180022eba  lea     rcx, [rbp+var_50]
0x180022ebe  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022ec3  nop
0x180022ec4  lea     rcx, [rbp+var_20]
0x180022ec8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022ecd  mov     rcx, [rbp+var_10]
0x180022ed1  xor     rcx, rsp; StackCookie
0x180022ed4  call    __security_check_cookie
0x180022ed9  mov     rbx, [rsp+70h+arg_10]
0x180022ee1  add     rsp, 70h
0x180022ee5  pop     r14
0x180022ee7  pop     rsi
0x180022ee8  pop     rbp
0x180022ee9  retn
```

# ??$call@P6A?AUAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z

- ea: `0x18000c6c4`
- end: `0x18000c802`
- name: `??$call@P6A?AUAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800105d8`

## callees

- `0x18000c6c4`
- `0x180018068`
- `0x18002d1a4`
- `0x1800563c8`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x18000c708`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallOptions`

## pseudocode

```c
__int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        __int64 a1,
        __int64 *a2,
        void (__fastcall **a3)(__int64 *, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-38h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-20h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+48h] [rbp-18h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-10h] BYREF

  v10 = a2;
  if ( aWindowsApplica[71] )
    abort();
  v7[0] = 1;
  v7[1] = 71;
  v8 = L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallOptions";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_18009F7C8;
    _InterlockedIncrement64(&qword_18009F7C8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009F7D0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18009F7C8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v9);
  }
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18000c6c4  mov     [rsp-18h+arg_0], rbx
0x18000c6c9  push    rbp
0x18000c6ca  push    rsi
0x18000c6cb  push    rdi
0x18000c6cc  mov     rbp, rsp
0x18000c6cf  sub     rsp, 60h
0x18000c6d3  mov     rax, cs:__security_cookie
0x18000c6da  xor     rax, rsp
0x18000c6dd  mov     [rbp+var_8], rax
0x18000c6e1  mov     rdi, r8
0x18000c6e4  mov     rbx, rdx
0x18000c6e7  mov     [rbp+var_10], rdx
0x18000c6eb  xor     esi, esi
0x18000c6ed  cmp     word ptr cs:aWindowsApplica+8Eh, si; ""
0x18000c6f4  jnz     loc_18000C7FC
0x18000c6fa  mov     [rbp+var_30], 1
0x18000c701  mov     [rbp+var_2C], 47h ; 'G'
0x18000c708  lea     rax, aWindowsApplica; "Windows.ApplicationModel.Store.Preview."...
0x18000c70f  mov     [rbp+var_20], rax
0x18000c713  lea     rax, [rbp+var_30]
0x18000c717  mov     [rbp+var_38], rax
0x18000c71b  lea     rdx, [rbp+var_38]
0x18000c71f  lea     rcx, [rbp+var_18]
0x18000c723  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18000c728  nop
0x18000c729  mov     rcx, [rbp+var_18]
0x18000c72d  test    rcx, rcx
0x18000c730  jz      loc_18000C7BE
0x18000c736  mov     [rbp+var_10], rsi
0x18000c73a  mov     rax, [rcx]
0x18000c73d  lea     r8, [rbp+var_10]
0x18000c741  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000c748  mov     rax, [rax]
0x18000c74b  call    _guard_dispatch_icall
0x18000c750  mov     rax, [rbp+var_10]
0x18000c754  mov     [rbp+var_10], rax
0x18000c758  test    rax, rax
0x18000c75b  jz      short loc_18000C7BE
0x18000c75d  lea     rcx, [rbp+var_10]
0x18000c761  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c766  lea     rax, qword_18009F7C8
0x18000c76d  mov     [rbp+var_10], rax
0x18000c771  lock inc cs:qword_18009F7C8
0x18000c779  mov     rcx, [rbp+var_18]
0x18000c77d  xor     eax, eax
0x18000c77f  lock cmpxchg cs:??$factory_cache_entry_v@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rcx; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>
0x18000c788  jnz     short loc_18000C7A1
0x18000c78a  mov     [rbp+var_18], rsi
0x18000c78e  lea     rdx, stru_18009F7D0; ListEntry
0x18000c795  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000c79c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000c7a1  lea     rdx, ??$factory_cache_entry_v@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>
0x18000c7a8  mov     rcx, rbx
0x18000c7ab  mov     rax, [rdi]
0x18000c7ae  call    _guard_dispatch_icall
0x18000c7b3  nop
0x18000c7b4  lock dec cs:qword_18009F7C8
0x18000c7bc  jmp     short loc_18000C7CE
0x18000c7be  lea     rdx, [rbp+var_18]
0x18000c7c2  mov     rcx, rbx
0x18000c7c5  mov     rax, [rdi]
0x18000c7c8  call    _guard_dispatch_icall
0x18000c7cd  nop
0x18000c7ce  cmp     [rbp+var_18], rsi
0x18000c7d2  jz      short loc_18000C7DD
0x18000c7d4  lea     rcx, [rbp+var_18]
0x18000c7d8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c7dd  mov     rax, rbx
0x18000c7e0  mov     rcx, [rbp+var_8]
0x18000c7e4  xor     rcx, rsp; StackCookie
0x18000c7e7  call    __security_check_cookie
0x18000c7ec  mov     rbx, [rsp+60h+arg_0]
0x18000c7f4  add     rsp, 60h
0x18000c7f8  pop     rdi
0x18000c7f9  pop     rsi
0x18000c7fa  pop     rbp
0x18000c7fb  retn
0x18000c7fc  call    abort
```

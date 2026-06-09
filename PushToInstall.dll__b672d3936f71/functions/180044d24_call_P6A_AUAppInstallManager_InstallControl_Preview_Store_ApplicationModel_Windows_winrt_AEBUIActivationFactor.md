# ??$call@P6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z

- ea: `0x180044d24`
- end: `0x180044e43`
- name: `??$call@P6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z`
- size: `287`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180044fd8`

## callees

- `0x18000e119`
- `0x180021cdc`
- `0x18002db60`
- `0x180044d24`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044d49`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044d49`

## string_xrefs

- `0x180044d5e`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-10h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+88h] [rbp+38h] BYREF

  v9 = a1;
  if ( aWindowsApplica[71] )
    abort();
  v7[0] = 1;
  v7[1] = 71;
  v8 = L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v10);
    v10 = &qword_18007F9C8;
    _InterlockedIncrement64(&qword_18007F9C8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18007F9D0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18007F9C8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v9);
  }
  if ( v9 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x180044d24  mov     [rsp-18h+arg_8], rbx
0x180044d29  mov     [rsp-18h+arg_0], rcx
0x180044d2e  push    rbp
0x180044d2f  push    rsi
0x180044d30  push    rdi
0x180044d31  mov     rbp, rsp
0x180044d34  sub     rsp, 50h
0x180044d38  mov     rdi, r8
0x180044d3b  mov     rbx, rdx
0x180044d3e  xor     esi, esi
0x180044d40  cmp     word ptr cs:aWindowsApplica+8Eh, si; ""
0x180044d47  jz      short loc_180044D50
0x180044d49  call    cs:__imp_abort
0x180044d50  mov     [rbp+var_20], 1
0x180044d57  mov     [rbp+var_1C], 47h ; 'G'
0x180044d5e  lea     rax, aWindowsApplica; "Windows.ApplicationModel.Store.Preview."...
0x180044d65  mov     [rbp+var_10], rax
0x180044d69  lea     rax, [rbp+var_20]
0x180044d6d  mov     [rbp+var_28], rax
0x180044d71  lea     rdx, [rbp+var_28]
0x180044d75  lea     rcx, [rbp+arg_0]
0x180044d79  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x180044d7e  nop
0x180044d7f  mov     rcx, [rbp+arg_0]
0x180044d83  test    rcx, rcx
0x180044d86  jz      loc_180044E14
0x180044d8c  mov     [rbp+arg_18], rsi
0x180044d90  mov     rax, [rcx]
0x180044d93  lea     r8, [rbp+arg_18]
0x180044d97  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180044d9e  mov     rax, [rax]
0x180044da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044da6  mov     rax, [rbp+arg_18]
0x180044daa  mov     [rbp+arg_18], rax
0x180044dae  test    rax, rax
0x180044db1  jz      short loc_180044E14
0x180044db3  lea     rcx, [rbp+arg_18]
0x180044db7  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180044dbc  lea     rax, qword_18007F9C8
0x180044dc3  mov     [rbp+arg_18], rax
0x180044dc7  lock inc cs:qword_18007F9C8
0x180044dcf  mov     rcx, [rbp+arg_0]
0x180044dd3  xor     eax, eax
0x180044dd5  lock cmpxchg cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rcx; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x180044dde  jnz     short loc_180044DF7
0x180044de0  mov     [rbp+arg_0], rsi
0x180044de4  lea     rdx, stru_18007F9D0; ListEntry
0x180044deb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180044df2  call    WINRT_IMPL_InterlockedPushEntrySList
0x180044df7  lea     rdx, ??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x180044dfe  mov     rcx, rbx
0x180044e01  mov     rax, [rdi]
0x180044e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e09  nop
0x180044e0a  lock dec cs:qword_18007F9C8
0x180044e12  jmp     short loc_180044E24
0x180044e14  lea     rdx, [rbp+arg_0]
0x180044e18  mov     rcx, rbx
0x180044e1b  mov     rax, [rdi]
0x180044e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e23  nop
0x180044e24  cmp     [rbp+arg_0], rsi
0x180044e28  jz      short loc_180044E33
0x180044e2a  lea     rcx, [rbp+arg_0]
0x180044e2e  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180044e33  mov     rax, rbx
0x180044e36  mov     rbx, [rsp+50h+arg_8]
0x180044e3b  add     rsp, 50h
0x180044e3f  pop     rdi
0x180044e40  pop     rsi
0x180044e41  pop     rbp
0x180044e42  retn
```

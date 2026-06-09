# ??$call@P6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z

- ea: `0x18000c4a4`
- end: `0x18000c5e2`
- name: `??$call@P6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800105d8`
- `0x1800120a0`

## callees

- `0x18000c4a4`
- `0x180018068`
- `0x18002d1a4`
- `0x1800563c8`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x18000c4e8`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
__int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  if ( aWindowsApplica_0[71] )
    abort();
  v7[0] = 1;
  v7[1] = 71;
  v8 = L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_18009F7E8;
    _InterlockedIncrement64(&qword_18009F7E8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009F7F0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18009F7E8);
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
0x18000c4a4  mov     [rsp-18h+arg_0], rbx
0x18000c4a9  push    rbp
0x18000c4aa  push    rsi
0x18000c4ab  push    rdi
0x18000c4ac  mov     rbp, rsp
0x18000c4af  sub     rsp, 60h
0x18000c4b3  mov     rax, cs:__security_cookie
0x18000c4ba  xor     rax, rsp
0x18000c4bd  mov     [rbp+var_8], rax
0x18000c4c1  mov     rdi, r8
0x18000c4c4  mov     rbx, rdx
0x18000c4c7  mov     [rbp+var_10], rdx
0x18000c4cb  xor     esi, esi
0x18000c4cd  cmp     word ptr cs:aWindowsApplica_0+8Eh, si; ""
0x18000c4d4  jnz     loc_18000C5DC
0x18000c4da  mov     [rbp+var_30], 1
0x18000c4e1  mov     [rbp+var_2C], 47h ; 'G'
0x18000c4e8  lea     rax, aWindowsApplica_0; "Windows.ApplicationModel.Store.Preview."...
0x18000c4ef  mov     [rbp+var_20], rax
0x18000c4f3  lea     rax, [rbp+var_30]
0x18000c4f7  mov     [rbp+var_38], rax
0x18000c4fb  lea     rdx, [rbp+var_38]
0x18000c4ff  lea     rcx, [rbp+var_18]
0x18000c503  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18000c508  nop
0x18000c509  mov     rcx, [rbp+var_18]
0x18000c50d  test    rcx, rcx
0x18000c510  jz      loc_18000C59E
0x18000c516  mov     [rbp+var_10], rsi
0x18000c51a  mov     rax, [rcx]
0x18000c51d  lea     r8, [rbp+var_10]
0x18000c521  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000c528  mov     rax, [rax]
0x18000c52b  call    _guard_dispatch_icall
0x18000c530  mov     rax, [rbp+var_10]
0x18000c534  mov     [rbp+var_10], rax
0x18000c538  test    rax, rax
0x18000c53b  jz      short loc_18000C59E
0x18000c53d  lea     rcx, [rbp+var_10]
0x18000c541  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c546  lea     rax, qword_18009F7E8
0x18000c54d  mov     [rbp+var_10], rax
0x18000c551  lock inc cs:qword_18009F7E8
0x18000c559  mov     rcx, [rbp+var_18]
0x18000c55d  xor     eax, eax
0x18000c55f  lock cmpxchg cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rcx; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x18000c568  jnz     short loc_18000C581
0x18000c56a  mov     [rbp+var_18], rsi
0x18000c56e  lea     rdx, stru_18009F7F0; ListEntry
0x18000c575  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000c57c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000c581  lea     rdx, ??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x18000c588  mov     rcx, rbx
0x18000c58b  mov     rax, [rdi]
0x18000c58e  call    _guard_dispatch_icall
0x18000c593  nop
0x18000c594  lock dec cs:qword_18009F7E8
0x18000c59c  jmp     short loc_18000C5AE
0x18000c59e  lea     rdx, [rbp+var_18]
0x18000c5a2  mov     rcx, rbx
0x18000c5a5  mov     rax, [rdi]
0x18000c5a8  call    _guard_dispatch_icall
0x18000c5ad  nop
0x18000c5ae  cmp     [rbp+var_18], rsi
0x18000c5b2  jz      short loc_18000C5BD
0x18000c5b4  lea     rcx, [rbp+var_18]
0x18000c5b8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c5bd  mov     rax, rbx
0x18000c5c0  mov     rcx, [rbp+var_8]
0x18000c5c4  xor     rcx, rsp; StackCookie
0x18000c5c7  call    __security_check_cookie
0x18000c5cc  mov     rbx, [rsp+60h+arg_0]
0x18000c5d4  add     rsp, 60h
0x18000c5d8  pop     rdi
0x18000c5d9  pop     rsi
0x18000c5da  pop     rbp
0x18000c5db  retn
0x18000c5dc  call    abort
```

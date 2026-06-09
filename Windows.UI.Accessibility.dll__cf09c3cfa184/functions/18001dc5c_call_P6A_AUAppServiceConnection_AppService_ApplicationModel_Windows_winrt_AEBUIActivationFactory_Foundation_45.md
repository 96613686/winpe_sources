# ??$call@P6A?AUAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppServiceConnection@AppService@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001dc5c`
- end: `0x18001dd72`
- name: `??$call@P6A?AUAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppServiceConnection@AppService@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023898`

## callees

- `0x180005236`
- `0x1800072d8`
- `0x18000dfc0`
- `0x18001dc5c`
- `0x18001e558`
- `0x180020388`
- `0x180035010`

## string_xrefs

- `0x18001dc79`: `Windows.ApplicationModel.AppService.AppServiceConnection`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::AppService::AppServiceConnection (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.ApplicationModel.AppService.AppServiceConnection";
  v6[1] = 56;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_180046BF8;
    _InterlockedIncrement64(&qword_180046BF8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180046C00);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180046BF8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v8);
  return a2;
}

```

## disassembly

```asm
0x18001dc5c  mov     [rsp-8+arg_8], rbx
0x18001dc61  mov     [rsp-8+arg_10], rdi
0x18001dc66  mov     [rsp-8+arg_0], rcx
0x18001dc6b  push    rbp
0x18001dc6c  mov     rbp, rsp
0x18001dc6f  sub     rsp, 60h
0x18001dc73  mov     rdi, r8
0x18001dc76  mov     rbx, rdx
0x18001dc79  lea     rax, aWindowsApplica_0; "Windows.ApplicationModel.AppService.App"...
0x18001dc80  mov     [rbp+var_38], rax
0x18001dc84  mov     [rbp+var_30], 38h ; '8'
0x18001dc8c  lea     rdx, [rbp+var_38]
0x18001dc90  lea     rcx, [rbp+var_28]
0x18001dc94  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001dc99  lea     rdx, [rbp+var_28]
0x18001dc9d  lea     rcx, [rbp+arg_0]
0x18001dca1  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18001dca6  nop
0x18001dca7  mov     rcx, [rbp+arg_0]
0x18001dcab  test    rcx, rcx
0x18001dcae  jz      loc_18001DD44
0x18001dcb4  mov     [rbp+arg_18], 0
0x18001dcbc  mov     rax, [rcx]
0x18001dcbf  lea     r8, [rbp+arg_18]
0x18001dcc3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001dcca  mov     rax, [rax]
0x18001dccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcd2  mov     rax, [rbp+arg_18]
0x18001dcd6  mov     [rbp+arg_18], rax
0x18001dcda  test    rax, rax
0x18001dcdd  jz      short loc_18001DD44
0x18001dcdf  lea     rcx, [rbp+arg_18]
0x18001dce3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001dce8  lea     rax, qword_180046BF8
0x18001dcef  mov     [rbp+arg_18], rax
0x18001dcf3  lock inc cs:qword_180046BF8
0x18001dcfb  mov     rcx, [rbp+arg_0]
0x18001dcff  xor     eax, eax
0x18001dd01  lock cmpxchg cs:??$factory_cache_entry_v@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>
0x18001dd0a  jnz     short loc_18001DD27
0x18001dd0c  mov     [rbp+arg_0], 0
0x18001dd14  lea     rdx, stru_180046C00; ListEntry
0x18001dd1b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001dd22  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001dd27  lea     rdx, ??$factory_cache_entry_v@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::AppService::AppServiceConnection,winrt::Windows::Foundation::IActivationFactory>
0x18001dd2e  mov     rcx, rbx
0x18001dd31  mov     rax, [rdi]
0x18001dd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd39  nop
0x18001dd3a  lock dec cs:qword_180046BF8
0x18001dd42  jmp     short loc_18001DD54
0x18001dd44  lea     rdx, [rbp+arg_0]
0x18001dd48  mov     rcx, rbx
0x18001dd4b  mov     rax, [rdi]
0x18001dd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd53  nop
0x18001dd54  lea     rcx, [rbp+arg_0]
0x18001dd58  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001dd5d  mov     rax, rbx
0x18001dd60  lea     r11, [rsp+60h+var_s0]
0x18001dd65  mov     rbx, [r11+18h]
0x18001dd69  mov     rdi, [r11+20h]
0x18001dd6d  mov     rsp, r11
0x18001dd70  pop     rbp
0x18001dd71  retn
```

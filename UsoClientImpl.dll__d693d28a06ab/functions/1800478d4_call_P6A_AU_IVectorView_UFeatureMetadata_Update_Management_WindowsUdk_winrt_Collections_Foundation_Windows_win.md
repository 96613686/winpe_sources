# ??$call@P6A?AU?$IVectorView@UFeatureMetadata@Update@Management@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@AEBUIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@5@@Z@?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IVectorView@UFeatureMetadata@Update@Management@WindowsUdk@winrt@@@Collections@Foundation@Windows@2@AEBUIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@2@@Z@Z

- ea: `0x1800478d4`
- end: `0x180047a0b`
- name: `??$call@P6A?AU?$IVectorView@UFeatureMetadata@Update@Management@WindowsUdk@winrt@@@Collections@Foundation@Windows@winrt@@AEBUIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@5@@Z@?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IVectorView@UFeatureMetadata@Update@Management@WindowsUdk@winrt@@@Collections@Foundation@Windows@2@AEBUIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@2@@Z@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041540`

## callees

- `0x18002d1a4`
- `0x180047864`
- `0x1800478d4`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x18004790c`: `WindowsUdk.Management.Update.FeatureMetadataManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>::call<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUdk::Management::Update::FeatureMetadata> (*)(winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics const &)>(
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
  v7[0] = 1;
  v7[1] = 51;
  v8 = L"WindowsUdk.Management.Update.FeatureMetadataManager";
  v6 = v7;
  winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_18009FAF8;
    _InterlockedIncrement64(&qword_18009FAF8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009FB00);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>);
    _InterlockedDecrement64(&qword_18009FAF8);
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
0x1800478d4  mov     [rsp-8+arg_0], rbx
0x1800478d9  mov     [rsp-8+arg_18], rdi
0x1800478de  push    rbp
0x1800478df  mov     rbp, rsp
0x1800478e2  sub     rsp, 60h
0x1800478e6  mov     rax, cs:__security_cookie
0x1800478ed  xor     rax, rsp
0x1800478f0  mov     [rbp+var_8], rax
0x1800478f4  mov     rdi, r8
0x1800478f7  mov     rbx, rdx
0x1800478fa  mov     [rbp+var_10], rdx
0x1800478fe  mov     [rbp+var_30], 1
0x180047905  mov     [rbp+var_2C], 33h ; '3'
0x18004790c  lea     rax, aWindowsudkMana_0; "WindowsUdk.Management.Update.FeatureMet"...
0x180047913  mov     [rbp+var_20], rax
0x180047917  lea     rax, [rbp+var_30]
0x18004791b  mov     [rbp+var_38], rax
0x18004791f  lea     rdx, [rbp+var_38]
0x180047923  lea     rcx, [rbp+var_18]
0x180047927  call    ??$get_activation_factory@UIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@winrt@@@winrt@@YA?AUIFeatureMetadataManagerStatics@Update@Management@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>(winrt::param::hstring const &)
0x18004792c  nop
0x18004792d  mov     rcx, [rbp+var_18]
0x180047931  test    rcx, rcx
0x180047934  jz      loc_1800479CA
0x18004793a  mov     [rbp+var_10], 0
0x180047942  mov     rax, [rcx]
0x180047945  lea     r8, [rbp+var_10]
0x180047949  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180047950  mov     rax, [rax]
0x180047953  call    _guard_dispatch_icall
0x180047958  mov     rax, [rbp+var_10]
0x18004795c  mov     [rbp+var_10], rax
0x180047960  test    rax, rax
0x180047963  jz      short loc_1800479CA
0x180047965  lea     rcx, [rbp+var_10]
0x180047969  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004796e  lea     rax, qword_18009FAF8
0x180047975  mov     [rbp+var_10], rax
0x180047979  lock inc cs:qword_18009FAF8
0x180047981  mov     rcx, [rbp+var_18]
0x180047985  xor     eax, eax
0x180047987  lock cmpxchg cs:??$factory_cache_entry_v@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@12@A, rcx; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>
0x180047990  jnz     short loc_1800479AD
0x180047992  mov     [rbp+var_18], 0
0x18004799a  lea     rdx, stru_18009FB00; ListEntry
0x1800479a1  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800479a8  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800479ad  lea     rdx, ??$factory_cache_entry_v@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureMetadataManager@Update@Management@WindowsUdk@winrt@@UIFeatureMetadataManagerStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureMetadataManager,winrt::WindowsUdk::Management::Update::IFeatureMetadataManagerStatics>
0x1800479b4  mov     rcx, rbx
0x1800479b7  mov     rax, [rdi]
0x1800479ba  call    _guard_dispatch_icall
0x1800479bf  nop
0x1800479c0  lock dec cs:qword_18009FAF8
0x1800479c8  jmp     short loc_1800479DA
0x1800479ca  lea     rdx, [rbp+var_18]
0x1800479ce  mov     rcx, rbx
0x1800479d1  mov     rax, [rdi]
0x1800479d4  call    _guard_dispatch_icall
0x1800479d9  nop
0x1800479da  cmp     [rbp+var_18], 0
0x1800479df  jz      short loc_1800479EA
0x1800479e1  lea     rcx, [rbp+var_18]
0x1800479e5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800479ea  mov     rax, rbx
0x1800479ed  mov     rcx, [rbp+var_8]
0x1800479f1  xor     rcx, rsp; StackCookie
0x1800479f4  call    __security_check_cookie
0x1800479f9  lea     r11, [rsp+60h+var_s0]
0x1800479fe  mov     rbx, [r11+10h]
0x180047a02  mov     rdi, [r11+28h]
0x180047a06  mov     rsp, r11
0x180047a09  pop     rbp
0x180047a0a  retn
```

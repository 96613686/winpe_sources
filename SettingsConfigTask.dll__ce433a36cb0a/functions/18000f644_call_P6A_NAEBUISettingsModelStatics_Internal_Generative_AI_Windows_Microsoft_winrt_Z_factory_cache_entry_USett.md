# ??$call@P6A_NAEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@2@@Z@Z

- ea: `0x18000f644`
- end: `0x18000f746`
- name: `??$call@P6A_NAEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@2@@Z@Z`
- size: `258`
- prototype: `char __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64 (__fastcall **)(__int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f9a8`

## callees

- `0x1800033e1`
- `0x18000f644`
- `0x18000fb04`
- `0x180012048`
- `0x180012514`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
char __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::call<bool (*)(winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 (__fastcall **a2)(__int64 *))
{
  char v3; // bl
  _QWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v6[32]; // [rsp+30h] [rbp-20h] BYREF
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v8; // [rsp+70h] [rbp+20h] BYREF

  v7 = a1;
  v5[0] = L"Microsoft.Windows.AI.Generative.Internal.SettingsModel";
  v5[1] = 54;
  winrt::param::hstring::hstring(v6, v5);
  winrt::get_activation_factory<winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>(&v7, v6);
  if ( v7 && (v8 = 0, (**v7)(v7, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
    v8 = &qword_18002ED68;
    _InterlockedIncrement64(&qword_18002ED68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>,
            (signed __int64)v7,
            0) )
    {
      v7 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002ED70);
    }
    v3 = (*a2)(&winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>);
    _InterlockedDecrement64(&qword_18002ED68);
  }
  else
  {
    v3 = (*a2)((__int64 *)&v7);
  }
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v7);
  return v3;
}

```

## disassembly

```asm
0x18000f644  mov     [rsp-8+arg_8], rbx
0x18000f649  mov     [rsp-8+arg_0], rcx
0x18000f64e  push    rbp
0x18000f64f  mov     rbp, rsp
0x18000f652  sub     rsp, 50h
0x18000f656  mov     rbx, rdx
0x18000f659  lea     rax, aMicrosoftWindo_1; "Microsoft.Windows.AI.Generative.Interna"...
0x18000f660  mov     [rbp+var_30], rax
0x18000f664  mov     [rbp+var_28], 36h ; '6'
0x18000f66c  lea     rdx, [rbp+var_30]
0x18000f670  lea     rcx, [rbp+var_20]
0x18000f674  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f679  lea     rdx, [rbp+var_20]
0x18000f67d  lea     rcx, [rbp+arg_0]
0x18000f681  call    ??$get_activation_factory@UISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@winrt@@YA?AUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>(winrt::param::hstring const &)
0x18000f686  nop
0x18000f687  mov     rcx, [rbp+arg_0]
0x18000f68b  test    rcx, rcx
0x18000f68e  jz      loc_18000F722
0x18000f694  mov     [rbp+arg_10], 0
0x18000f69c  mov     rax, [rcx]
0x18000f69f  lea     r8, [rbp+arg_10]
0x18000f6a3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f6aa  mov     rax, [rax]
0x18000f6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6b2  mov     rax, [rbp+arg_10]
0x18000f6b6  mov     [rbp+arg_10], rax
0x18000f6ba  test    rax, rax
0x18000f6bd  jz      short loc_18000F722
0x18000f6bf  lea     rcx, [rbp+arg_10]
0x18000f6c3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f6c8  lea     rax, qword_18002ED68
0x18000f6cf  mov     [rbp+arg_10], rax
0x18000f6d3  lock inc cs:qword_18002ED68
0x18000f6db  mov     rcx, [rbp+arg_0]
0x18000f6df  xor     eax, eax
0x18000f6e1  lock cmpxchg cs:??$factory_cache_entry_v@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>
0x18000f6ea  jnz     short loc_18000F707
0x18000f6ec  mov     [rbp+arg_0], 0
0x18000f6f4  lea     rdx, stru_18002ED70; ListEntry
0x18000f6fb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f702  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f707  lea     rcx, ??$factory_cache_entry_v@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>
0x18000f70e  mov     rax, [rbx]
0x18000f711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f716  mov     bl, al
0x18000f718  lock dec cs:qword_18002ED68
0x18000f720  jmp     short loc_18000F730
0x18000f722  lea     rcx, [rbp+arg_0]
0x18000f726  mov     rax, [rbx]
0x18000f729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f72e  mov     bl, al
0x18000f730  lea     rcx, [rbp+arg_0]
0x18000f734  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f739  mov     al, bl
0x18000f73b  mov     rbx, [rsp+50h+arg_8]
0x18000f740  add     rsp, 50h
0x18000f744  pop     rbp
0x18000f745  retn
```

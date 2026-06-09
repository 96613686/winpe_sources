# ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUISettingsModelStatics@Internal@Generative@AI@3Microsoft@4@@Z@?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUISettingsModelStatics@Internal@Generative@AI@5Microsoft@2@@Z@Z

- ea: `0x18000f0c0`
- end: `0x18000f1d6`
- name: `??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUISettingsModelStatics@Internal@Generative@AI@3Microsoft@4@@Z@?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUISettingsModelStatics@Internal@Generative@AI@5Microsoft@2@@Z@Z`
- size: `278`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001871c`
- `0x1800193e0`

## callees

- `0x1800033e1`
- `0x18000f0c0`
- `0x18000fb04`
- `0x180012048`
- `0x180012514`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Microsoft.Windows.AI.Generative.Internal.SettingsModel";
  v6[1] = 54;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_18002ED68;
    _InterlockedIncrement64(&qword_18002ED68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002ED70);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>);
    _InterlockedDecrement64(&qword_18002ED68);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v8);
  return a2;
}

```

## disassembly

```asm
0x18000f0c0  mov     [rsp-8+arg_8], rbx
0x18000f0c5  mov     [rsp-8+arg_10], rdi
0x18000f0ca  mov     [rsp-8+arg_0], rcx
0x18000f0cf  push    rbp
0x18000f0d0  mov     rbp, rsp
0x18000f0d3  sub     rsp, 60h
0x18000f0d7  mov     rdi, r8
0x18000f0da  mov     rbx, rdx
0x18000f0dd  lea     rax, aMicrosoftWindo_1; "Microsoft.Windows.AI.Generative.Interna"...
0x18000f0e4  mov     [rbp+var_38], rax
0x18000f0e8  mov     [rbp+var_30], 36h ; '6'
0x18000f0f0  lea     rdx, [rbp+var_38]
0x18000f0f4  lea     rcx, [rbp+var_28]
0x18000f0f8  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f0fd  lea     rdx, [rbp+var_28]
0x18000f101  lea     rcx, [rbp+arg_0]
0x18000f105  call    ??$get_activation_factory@UISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@winrt@@@winrt@@YA?AUISettingsModelStatics@Internal@Generative@AI@Windows@Microsoft@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>(winrt::param::hstring const &)
0x18000f10a  nop
0x18000f10b  mov     rcx, [rbp+arg_0]
0x18000f10f  test    rcx, rcx
0x18000f112  jz      loc_18000F1A8
0x18000f118  mov     [rbp+arg_18], 0
0x18000f120  mov     rax, [rcx]
0x18000f123  lea     r8, [rbp+arg_18]
0x18000f127  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f12e  mov     rax, [rax]
0x18000f131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f136  mov     rax, [rbp+arg_18]
0x18000f13a  mov     [rbp+arg_18], rax
0x18000f13e  test    rax, rax
0x18000f141  jz      short loc_18000F1A8
0x18000f143  lea     rcx, [rbp+arg_18]
0x18000f147  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f14c  lea     rax, qword_18002ED68
0x18000f153  mov     [rbp+arg_18], rax
0x18000f157  lock inc cs:qword_18002ED68
0x18000f15f  mov     rcx, [rbp+arg_0]
0x18000f163  xor     eax, eax
0x18000f165  lock cmpxchg cs:??$factory_cache_entry_v@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>
0x18000f16e  jnz     short loc_18000F18B
0x18000f170  mov     [rbp+arg_0], 0
0x18000f178  lea     rdx, stru_18002ED70; ListEntry
0x18000f17f  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f186  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f18b  lea     rdx, ??$factory_cache_entry_v@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USettingsModel@Internal@Generative@AI@Windows@Microsoft@winrt@@UISettingsModelStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::AI::Generative::Internal::SettingsModel,winrt::Microsoft::Windows::AI::Generative::Internal::ISettingsModelStatics>
0x18000f192  mov     rcx, rbx
0x18000f195  mov     rax, [rdi]
0x18000f198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f19d  nop
0x18000f19e  lock dec cs:qword_18002ED68
0x18000f1a6  jmp     short loc_18000F1B8
0x18000f1a8  lea     rdx, [rbp+arg_0]
0x18000f1ac  mov     rcx, rbx
0x18000f1af  mov     rax, [rdi]
0x18000f1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1b7  nop
0x18000f1b8  lea     rcx, [rbp+arg_0]
0x18000f1bc  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f1c1  mov     rax, rbx
0x18000f1c4  lea     r11, [rsp+60h+var_s0]
0x18000f1c9  mov     rbx, [r11+18h]
0x18000f1cd  mov     rdi, [r11+20h]
0x18000f1d1  mov     rsp, r11
0x18000f1d4  pop     rbp
0x18000f1d5  retn
```

# ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUIQueryBlockListStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUIQueryBlockListStatics@SemanticSearch@5Microsoft@2@@Z@Z

- ea: `0x18000f1dc`
- end: `0x18000f2f2`
- name: `??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUIQueryBlockListStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUIQueryBlockListStatics@SemanticSearch@5Microsoft@2@@Z@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019368`

## callees

- `0x1800033e1`
- `0x18000f1dc`
- `0x18000faa4`
- `0x180012048`
- `0x180012514`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Microsoft.Windows.SemanticSearch.QueryBlockList";
  v6[1] = 47;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_18002ED48;
    _InterlockedIncrement64(&qword_18002ED48);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002ED50);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>);
    _InterlockedDecrement64(&qword_18002ED48);
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
0x18000f1dc  mov     [rsp-8+arg_8], rbx
0x18000f1e1  mov     [rsp-8+arg_10], rdi
0x18000f1e6  mov     [rsp-8+arg_0], rcx
0x18000f1eb  push    rbp
0x18000f1ec  mov     rbp, rsp
0x18000f1ef  sub     rsp, 60h
0x18000f1f3  mov     rdi, r8
0x18000f1f6  mov     rbx, rdx
0x18000f1f9  lea     rax, aMicrosoftWindo_3; "Microsoft.Windows.SemanticSearch.QueryB"...
0x18000f200  mov     [rbp+var_38], rax
0x18000f204  mov     [rbp+var_30], 2Fh ; '/'
0x18000f20c  lea     rdx, [rbp+var_38]
0x18000f210  lea     rcx, [rbp+var_28]
0x18000f214  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f219  lea     rdx, [rbp+var_28]
0x18000f21d  lea     rcx, [rbp+arg_0]
0x18000f221  call    ??$get_activation_factory@UIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@winrt@@@winrt@@YA?AUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>(winrt::param::hstring const &)
0x18000f226  nop
0x18000f227  mov     rcx, [rbp+arg_0]
0x18000f22b  test    rcx, rcx
0x18000f22e  jz      loc_18000F2C4
0x18000f234  mov     [rbp+arg_18], 0
0x18000f23c  mov     rax, [rcx]
0x18000f23f  lea     r8, [rbp+arg_18]
0x18000f243  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f24a  mov     rax, [rax]
0x18000f24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f252  mov     rax, [rbp+arg_18]
0x18000f256  mov     [rbp+arg_18], rax
0x18000f25a  test    rax, rax
0x18000f25d  jz      short loc_18000F2C4
0x18000f25f  lea     rcx, [rbp+arg_18]
0x18000f263  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f268  lea     rax, qword_18002ED48
0x18000f26f  mov     [rbp+arg_18], rax
0x18000f273  lock inc cs:qword_18002ED48
0x18000f27b  mov     rcx, [rbp+arg_0]
0x18000f27f  xor     eax, eax
0x18000f281  lock cmpxchg cs:??$factory_cache_entry_v@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
0x18000f28a  jnz     short loc_18000F2A7
0x18000f28c  mov     [rbp+arg_0], 0
0x18000f294  lea     rdx, stru_18002ED50; ListEntry
0x18000f29b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f2a2  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f2a7  lea     rdx, ??$factory_cache_entry_v@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
0x18000f2ae  mov     rcx, rbx
0x18000f2b1  mov     rax, [rdi]
0x18000f2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b9  nop
0x18000f2ba  lock dec cs:qword_18002ED48
0x18000f2c2  jmp     short loc_18000F2D4
0x18000f2c4  lea     rdx, [rbp+arg_0]
0x18000f2c8  mov     rcx, rbx
0x18000f2cb  mov     rax, [rdi]
0x18000f2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2d3  nop
0x18000f2d4  lea     rcx, [rbp+arg_0]
0x18000f2d8  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f2dd  mov     rax, rbx
0x18000f2e0  lea     r11, [rsp+60h+var_s0]
0x18000f2e5  mov     rbx, [r11+18h]
0x18000f2e9  mov     rdi, [r11+20h]
0x18000f2ed  mov     rsp, r11
0x18000f2f0  pop     rbp
0x18000f2f1  retn
```

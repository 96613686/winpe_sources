# ??$call@P6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z

- ea: `0x18000f53c`
- end: `0x18000f63e`
- name: `??$call@P6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f910`

## callees

- `0x1800033e1`
- `0x18000f53c`
- `0x18000faa4`
- `0x180012048`
- `0x180012514`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
char __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 (__fastcall **a2)(__int64 *))
{
  char v3; // bl
  _QWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v6[32]; // [rsp+30h] [rbp-20h] BYREF
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v8; // [rsp+70h] [rbp+20h] BYREF

  v7 = a1;
  v5[0] = L"Microsoft.Windows.SemanticSearch.QueryBlockList";
  v5[1] = 47;
  winrt::param::hstring::hstring(v6, v5);
  winrt::get_activation_factory<winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>(&v7, v6);
  if ( v7 && (v8 = 0, (**v7)(v7, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v8);
    v8 = &qword_18002ED48;
    _InterlockedIncrement64(&qword_18002ED48);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>,
            (signed __int64)v7,
            0) )
    {
      v7 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002ED50);
    }
    v3 = (*a2)(&winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>);
    _InterlockedDecrement64(&qword_18002ED48);
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
0x18000f53c  mov     [rsp-8+arg_8], rbx
0x18000f541  mov     [rsp-8+arg_0], rcx
0x18000f546  push    rbp
0x18000f547  mov     rbp, rsp
0x18000f54a  sub     rsp, 50h
0x18000f54e  mov     rbx, rdx
0x18000f551  lea     rax, aMicrosoftWindo_3; "Microsoft.Windows.SemanticSearch.QueryB"...
0x18000f558  mov     [rbp+var_30], rax
0x18000f55c  mov     [rbp+var_28], 2Fh ; '/'
0x18000f564  lea     rdx, [rbp+var_30]
0x18000f568  lea     rcx, [rbp+var_20]
0x18000f56c  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f571  lea     rdx, [rbp+var_20]
0x18000f575  lea     rcx, [rbp+arg_0]
0x18000f579  call    ??$get_activation_factory@UIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@winrt@@@winrt@@YA?AUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>(winrt::param::hstring const &)
0x18000f57e  nop
0x18000f57f  mov     rcx, [rbp+arg_0]
0x18000f583  test    rcx, rcx
0x18000f586  jz      loc_18000F61A
0x18000f58c  mov     [rbp+arg_10], 0
0x18000f594  mov     rax, [rcx]
0x18000f597  lea     r8, [rbp+arg_10]
0x18000f59b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f5a2  mov     rax, [rax]
0x18000f5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5aa  mov     rax, [rbp+arg_10]
0x18000f5ae  mov     [rbp+arg_10], rax
0x18000f5b2  test    rax, rax
0x18000f5b5  jz      short loc_18000F61A
0x18000f5b7  lea     rcx, [rbp+arg_10]
0x18000f5bb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f5c0  lea     rax, qword_18002ED48
0x18000f5c7  mov     [rbp+arg_10], rax
0x18000f5cb  lock inc cs:qword_18002ED48
0x18000f5d3  mov     rcx, [rbp+arg_0]
0x18000f5d7  xor     eax, eax
0x18000f5d9  lock cmpxchg cs:??$factory_cache_entry_v@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
0x18000f5e2  jnz     short loc_18000F5FF
0x18000f5e4  mov     [rbp+arg_0], 0
0x18000f5ec  lea     rdx, stru_18002ED50; ListEntry
0x18000f5f3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f5fa  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f5ff  lea     rcx, ??$factory_cache_entry_v@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
0x18000f606  mov     rax, [rbx]
0x18000f609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f60e  mov     bl, al
0x18000f610  lock dec cs:qword_18002ED48
0x18000f618  jmp     short loc_18000F628
0x18000f61a  lea     rcx, [rbp+arg_0]
0x18000f61e  mov     rax, [rbx]
0x18000f621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f626  mov     bl, al
0x18000f628  lea     rcx, [rbp+arg_0]
0x18000f62c  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f631  mov     al, bl
0x18000f633  mov     rbx, [rsp+50h+arg_8]
0x18000f638  add     rsp, 50h
0x18000f63c  pop     rbp
0x18000f63d  retn
```

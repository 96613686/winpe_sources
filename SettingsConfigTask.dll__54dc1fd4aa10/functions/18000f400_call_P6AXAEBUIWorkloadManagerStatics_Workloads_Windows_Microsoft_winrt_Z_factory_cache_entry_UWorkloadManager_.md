# ??$call@P6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@2@@Z@Z

- ea: `0x18000f400`
- end: `0x18000f533`
- name: `??$call@P6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@2@@Z@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000f884`

## callees

- `0x1800033e1`
- `0x18000f400`
- `0x18000fbc4`
- `0x180012048`
- `0x180012514`
- `0x18001d2e8`
- `0x1800215e8`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>::call<void (*)(winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics const &)>(
        __int64 *a1,
        void (__fastcall **a2)(__int64 *))
{
  const wchar_t *v4; // [rsp+20h] [rbp-40h] BYREF
  __int128 v5; // [rsp+28h] [rbp-38h]
  _QWORD v6[5]; // [rsp+38h] [rbp-28h] BYREF
  __int64 *v7; // [rsp+70h] [rbp+10h] BYREF
  void (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp+20h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+88h] [rbp+28h] BYREF

  v7 = a1;
  v4 = L"Microsoft.Windows.Workloads.WorkloadManager";
  *(_QWORD *)&v5 = 43;
  winrt::param::hstring::hstring(v6, &v4);
  v9 = 0;
  LODWORD(v4) = 0;
  v5 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v7,
    v6,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>,
    (__int64)&v9);
  winrt::check_hresult(&v7, (unsigned int)v7, &v4);
  v8 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v9;
  if ( v9 && (v7 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v7), v7) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v7);
    v7 = &qword_18002EBE8;
    _InterlockedIncrement64(&qword_18002EBE8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18002EBF0);
    }
    (*a2)(&winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>);
    _InterlockedDecrement64(&qword_18002EBE8);
  }
  else
  {
    (*a2)((__int64 *)&v8);
  }
  return winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v8);
}

```

## disassembly

```asm
0x18000f400  mov     [rsp-8+arg_8], rbx
0x18000f405  mov     [rsp-8+arg_0], rcx
0x18000f40a  push    rbp
0x18000f40b  mov     rbp, rsp
0x18000f40e  sub     rsp, 60h
0x18000f412  mov     rbx, rdx
0x18000f415  lea     rax, aMicrosoftWindo_0; "Microsoft.Windows.Workloads.WorkloadMan"...
0x18000f41c  mov     [rbp+var_40], rax
0x18000f420  mov     qword ptr [rbp+var_38], 2Bh ; '+'
0x18000f428  lea     rdx, [rbp+var_40]
0x18000f42c  lea     rcx, [rbp+var_28]
0x18000f430  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f435  mov     [rbp+arg_18], 0
0x18000f43d  mov     dword ptr [rbp+var_40], 0
0x18000f444  xorps   xmm0, xmm0
0x18000f447  movdqu  [rbp+var_38], xmm0
0x18000f44c  lea     r9, [rbp+arg_18]
0x18000f450  lea     r8, ??$guid_v@UIWorkloadManagerStatics@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>
0x18000f457  lea     rdx, [rbp+var_28]
0x18000f45b  lea     rcx, [rbp+arg_0]
0x18000f45f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000f464  lea     r8, [rbp+var_40]
0x18000f468  mov     edx, dword ptr [rbp+arg_0]
0x18000f46b  lea     rcx, [rbp+arg_0]
0x18000f46f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000f474  mov     rcx, [rbp+arg_18]
0x18000f478  mov     [rbp+arg_10], rcx
0x18000f47c  test    rcx, rcx
0x18000f47f  jz      loc_18000F512
0x18000f485  mov     [rbp+arg_0], 0
0x18000f48d  mov     rax, [rcx]
0x18000f490  lea     r8, [rbp+arg_0]
0x18000f494  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f49b  mov     rax, [rax]
0x18000f49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a3  mov     rax, [rbp+arg_0]
0x18000f4a7  mov     [rbp+arg_0], rax
0x18000f4ab  test    rax, rax
0x18000f4ae  jz      short loc_18000F512
0x18000f4b0  lea     rcx, [rbp+arg_0]
0x18000f4b4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f4b9  lea     rax, qword_18002EBE8
0x18000f4c0  mov     [rbp+arg_0], rax
0x18000f4c4  lock inc cs:qword_18002EBE8
0x18000f4cc  mov     rcx, [rbp+arg_10]
0x18000f4d0  xor     eax, eax
0x18000f4d2  lock cmpxchg cs:??$factory_cache_entry_v@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>
0x18000f4db  jnz     short loc_18000F4F8
0x18000f4dd  mov     [rbp+arg_10], 0
0x18000f4e5  lea     rdx, stru_18002EBF0; ListEntry
0x18000f4ec  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f4f3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f4f8  lea     rcx, ??$factory_cache_entry_v@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>
0x18000f4ff  mov     rax, [rbx]
0x18000f502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f507  nop
0x18000f508  lock dec cs:qword_18002EBE8
0x18000f510  jmp     short loc_18000F51F
0x18000f512  lea     rcx, [rbp+arg_10]
0x18000f516  mov     rax, [rbx]
0x18000f519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f51e  nop
0x18000f51f  lea     rcx, [rbp+arg_10]
0x18000f523  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x18000f528  mov     rbx, [rsp+60h+arg_8]
0x18000f52d  add     rsp, 60h
0x18000f531  pop     rbp
0x18000f532  retn
```

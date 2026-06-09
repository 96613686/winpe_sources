# ??$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@1@I@Z

- ea: `0x1800116b4`
- end: `0x18001179e`
- name: `??$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@1@I@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001871c`

## callees

- `0x1800025d8`
- `0x180002d7f`
- `0x1800033d5`
- `0x18000fa40`
- `0x1800120e4`
- `0x180012514`
- `0x18001d2e8`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncAction>(__int64 *a1, int a2)
{
  HANDLE EventW; // rax
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // rsi
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+28h] [rbp-28h]
  int v13; // [rsp+38h] [rbp-18h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h]
  char *v15; // [rsp+70h] [rbp+20h]
  int v16; // [rsp+78h] [rbp+28h] BYREF

  v16 = a2;
  LODWORD(v11) = 0;
  v12 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  v4 = winrt::check_pointer<void>(EventW, &v11);
  v11 = v4;
  *(_QWORD *)&v12 = 0;
  v15 = (char *)operator new(0x20u);
  winrt::impl::implements_delegate_base::implements_delegate_base((winrt::impl::implements_delegate_base *)(v15 + 8));
  v6 = v5 + 16;
  *(_QWORD *)(v5 + 16) = v4;
  *(_DWORD *)(v5 + 24) = 0;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v5 = ___7__delegate_UAsyncActionCompletedHandler_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_UIAsyncAction_Foundation_Windows_winrt___impl_4_YA_A_PAEBUIAsyncAction_234_I_Z__impl_winrt__6B_;
  v11 = v5;
  *(_QWORD *)&v12 = v5 + 16;
  v7 = *a1;
  v13 = 0;
  v14 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 48LL))(v7, v5);
  winrt::check_hresult(&v16, v8, &v13);
  WaitForSingleObject_0(*(HANDLE *)v6, 0xFFFFFFFF);
  v9 = *(_DWORD *)(v6 + 8);
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v11);
  return v9;
}

```

## disassembly

```asm
0x1800116b4  mov     [rsp-18h+arg_10], rbx
0x1800116b9  mov     [rsp-18h+arg_18], rsi
0x1800116be  mov     [rsp-18h+arg_8], edx
0x1800116c2  push    rbp
0x1800116c3  push    rdi
0x1800116c4  push    r14
0x1800116c6  mov     rbp, rsp
0x1800116c9  sub     rsp, 50h
0x1800116cd  mov     r14, rcx
0x1800116d0  mov     dword ptr [rbp+var_30], 0
0x1800116d7  xorps   xmm0, xmm0
0x1800116da  movdqu  [rbp+var_28], xmm0
0x1800116df  xor     r9d, r9d; lpName
0x1800116e2  xor     r8d, r8d; bInitialState
0x1800116e5  lea     edx, [r9+1]; bManualReset
0x1800116e9  xor     ecx, ecx; lpEventAttributes
0x1800116eb  call    WINRT_IMPL_CreateEventW
0x1800116f0  lea     rdx, [rbp+var_30]
0x1800116f4  mov     rcx, rax
0x1800116f7  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x1800116fc  mov     rdi, rax
0x1800116ff  mov     [rbp+var_30], rax
0x180011703  xor     ebx, ebx
0x180011705  mov     qword ptr [rbp+var_28], rbx
0x180011709  lea     ecx, [rbx+20h]; Size
0x18001170c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011711  mov     r8, rax
0x180011714  mov     [rbp+arg_0], rax
0x180011718  lea     rcx, [rax+8]; this
0x18001171c  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x180011721  lea     rsi, [r8+10h]
0x180011725  mov     [rsi], rdi
0x180011728  mov     [rsi+8], ebx
0x18001172b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011732  lea     rax, ??_7?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@6B@
0x180011739  mov     [r8], rax
0x18001173c  mov     [rbp+var_30], r8
0x180011740  mov     qword ptr [rbp+var_28], rsi
0x180011744  mov     rcx, [r14]
0x180011747  mov     [rbp+var_18], ebx
0x18001174a  xorps   xmm0, xmm0
0x18001174d  movdqu  [rbp+var_10], xmm0
0x180011752  mov     rax, [rcx]
0x180011755  mov     rdx, r8
0x180011758  mov     rax, [rax+30h]
0x18001175c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011761  lea     r8, [rbp+var_18]
0x180011765  mov     edx, eax
0x180011767  lea     rcx, [rbp+arg_8]
0x18001176b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180011770  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011773  mov     rcx, [rsi]; hHandle
0x180011776  call    WaitForSingleObject_0
0x18001177b  mov     ebx, [rsi+8]
0x18001177e  lea     rcx, [rbp+var_30]
0x180011782  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x180011787  mov     eax, ebx
0x180011789  lea     r11, [rsp+50h+var_s0]
0x18001178e  mov     rbx, [r11+30h]
0x180011792  mov     rsi, [r11+38h]
0x180011796  mov     rsp, r11
0x180011799  pop     r14
0x18001179b  pop     rdi
0x18001179c  pop     rbp
0x18001179d  retn
```

# ??$wait_for_completed@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@I@Z

- ea: `0x1800115c4`
- end: `0x1800116ae`
- name: `??$wait_for_completed@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@I@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011844`

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
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>(
        __int64 *a1,
        int a2)
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
  *(_QWORD *)v5 = ___7__delegate_U__AsyncOperationWithProgressCompletedHandler_UPackageDeploymentResult_Deployment_Management_Windows_Microsoft_winrt__UPackageDeploymentProgress_23456__Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperationWithProgress_UPackageDeploymentResult_Deployment_Management_Windows_Microsoft_winrt__UPackageDeploymentProgress_23456__Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperationWithProgress_UPackageDeploymentResult_Deployment_Management_Windows_Microsoft_winrt__UPackageDeploymentProgress_23456__234_I_Z__impl_winrt__6B_;
  v11 = v5;
  *(_QWORD *)&v12 = v5 + 16;
  v7 = *a1;
  v13 = 0;
  v14 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 64LL))(v7, v5);
  winrt::check_hresult(&v16, v8, &v13);
  WaitForSingleObject_0(*(HANDLE *)v6, 0xFFFFFFFF);
  v9 = *(_DWORD *)(v6 + 8);
  winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(&v11);
  return v9;
}

```

## disassembly

```asm
0x1800115c4  mov     [rsp-18h+arg_10], rbx
0x1800115c9  mov     [rsp-18h+arg_18], rsi
0x1800115ce  mov     [rsp-18h+arg_8], edx
0x1800115d2  push    rbp
0x1800115d3  push    rdi
0x1800115d4  push    r14
0x1800115d6  mov     rbp, rsp
0x1800115d9  sub     rsp, 50h
0x1800115dd  mov     r14, rcx
0x1800115e0  mov     dword ptr [rbp+var_30], 0
0x1800115e7  xorps   xmm0, xmm0
0x1800115ea  movdqu  [rbp+var_28], xmm0
0x1800115ef  xor     r9d, r9d; lpName
0x1800115f2  xor     r8d, r8d; bInitialState
0x1800115f5  lea     edx, [r9+1]; bManualReset
0x1800115f9  xor     ecx, ecx; lpEventAttributes
0x1800115fb  call    WINRT_IMPL_CreateEventW
0x180011600  lea     rdx, [rbp+var_30]
0x180011604  mov     rcx, rax
0x180011607  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x18001160c  mov     rdi, rax
0x18001160f  mov     [rbp+var_30], rax
0x180011613  xor     ebx, ebx
0x180011615  mov     qword ptr [rbp+var_28], rbx
0x180011619  lea     ecx, [rbx+20h]; Size
0x18001161c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011621  mov     r8, rax
0x180011624  mov     [rbp+arg_0], rax
0x180011628  lea     rcx, [rax+8]; this
0x18001162c  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x180011631  lea     rsi, [r8+10h]
0x180011635  mov     [rsi], rdi
0x180011638  mov     [rsi+8], ebx
0x18001163b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011642  lea     rax, ??_7?$delegate@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@234@I@Z@@impl@winrt@@6B@
0x180011649  mov     [r8], rax
0x18001164c  mov     [rbp+var_30], r8
0x180011650  mov     qword ptr [rbp+var_28], rsi
0x180011654  mov     rcx, [r14]
0x180011657  mov     [rbp+var_18], ebx
0x18001165a  xorps   xmm0, xmm0
0x18001165d  movdqu  [rbp+var_10], xmm0
0x180011662  mov     rax, [rcx]
0x180011665  mov     rdx, r8
0x180011668  mov     rax, [rax+40h]
0x18001166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011671  lea     r8, [rbp+var_18]
0x180011675  mov     edx, eax
0x180011677  lea     rcx, [rbp+arg_8]
0x18001167b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180011680  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011683  mov     rcx, [rsi]; hHandle
0x180011686  call    WaitForSingleObject_0
0x18001168b  mov     ebx, [rsi+8]
0x18001168e  lea     rcx, [rbp+var_30]
0x180011692  call    ??1?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(void)
0x180011697  mov     eax, ebx
0x180011699  lea     r11, [rsp+50h+var_s0]
0x18001169e  mov     rbx, [r11+30h]
0x1800116a2  mov     rsi, [r11+38h]
0x1800116a6  mov     rsp, r11
0x1800116a9  pop     r14
0x1800116ab  pop     rdi
0x1800116ac  pop     rbp
0x1800116ad  retn
```

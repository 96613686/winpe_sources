# winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,winrt::Windows::Foundation::AsyncStatus const &)

- ea: `0x1800196b0`
- end: `0x1800196f1`
- name: `??$invoke@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBU?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@01@AEBW4AsyncStatus@341@@Z`
- size: `65`
- prototype: `char __fastcall(_QWORD *, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800182e0`
- `0x180018910`
- `0x18002c9c0`

## callees

- `0x180004810`
- `0x1800196b0`
- `0x18003bed0`

## pseudocode

```c
char __fastcall winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,enum winrt::Windows::Foundation::AsyncStatus>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3)
{
  int v3; // eax
  winrt::impl *v5; // rcx
  __int64 *v6; // rdx
  __int64 v7; // [rsp+0h] [rbp-38h] BYREF
  char v8; // [rsp+20h] [rbp-18h]
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = a2 + 16;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*a1 + 24LL))(*a1, a2 + 16, *a3);
  if ( v3 < 0 )
  {
    _mm_lfence();
    try
    {
      winrt::throw_hresult((unsigned int)v3);
    }
    catch ( ... )
    {
      v6 = &v7;
      *((_BYTE *)v6 + 32) = winrt::impl::report_failed_invoke(v5);
      return v8;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800196b0  sub     rsp, 38h
0x1800196b4  add     rdx, 10h
0x1800196b8  mov     [rsp+38h+var_10], rdx
0x1800196bd  mov     rcx, [rcx]
0x1800196c0  mov     rax, [rcx]
0x1800196c3  mov     r8d, [r8]
0x1800196c6  mov     rax, [rax+18h]
0x1800196ca  call    cs:__guard_dispatch_icall_fptr
0x1800196d0  test    eax, eax
0x1800196d2  js      short loc_1800196E5
0x1800196d4  mov     al, 1
0x1800196d6  add     rsp, 38h
0x1800196da  retn
0x1800196db  movzx   eax, [rsp+38h+var_18]
0x1800196e0  add     rsp, 38h
0x1800196e4  retn
0x1800196e5  lfence
0x1800196e8  mov     ecx, eax
0x1800196ea  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

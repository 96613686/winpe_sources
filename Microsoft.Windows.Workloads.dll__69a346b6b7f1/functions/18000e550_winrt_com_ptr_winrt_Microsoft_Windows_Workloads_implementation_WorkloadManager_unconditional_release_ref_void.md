# winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(void)

- ea: `0x18000e550`
- end: `0x18000e595`
- name: `?unconditional_release_ref@?$com_ptr@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000dfd0`
- `0x180018da0`
- `0x18001d320`
- `0x1800398d0`
- `0x18003a020`
- `0x18003aec0`

## callees

- `0x18000c530`
- `0x18000e550`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  result = winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(v1);
  if ( !(_DWORD)result )
  {
    v1[1] = 1;
    return (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v1 + 8LL))(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000e550  push    rbx
0x18000e552  sub     rsp, 20h
0x18000e556  mov     rbx, [rcx]
0x18000e559  mov     qword ptr [rcx], 0
0x18000e560  mov     rcx, rbx
0x18000e563  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x18000e568  test    eax, eax
0x18000e56a  jnz     short loc_18000E58F
0x18000e56c  mov     qword ptr [rbx+8], 1
0x18000e574  mov     edx, 1
0x18000e579  mov     rax, [rbx]
0x18000e57c  mov     rcx, rbx
0x18000e57f  mov     rax, [rax+8]
0x18000e583  add     rsp, 20h
0x18000e587  pop     rbx
0x18000e588  jmp     cs:__guard_dispatch_icall_fptr
0x18000e58f  add     rsp, 20h
0x18000e593  pop     rbx
0x18000e594  retn
```

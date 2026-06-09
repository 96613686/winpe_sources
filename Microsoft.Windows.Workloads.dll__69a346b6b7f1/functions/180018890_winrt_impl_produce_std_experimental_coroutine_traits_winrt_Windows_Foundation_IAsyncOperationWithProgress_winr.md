# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>::get_Completed(void * *)

- ea: `0x180018890`
- end: `0x180018909`
- name: `?get_Completed@?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkloadManager@implementation@Workloads@3Microsoft@4@Uhstring@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180018890`
- `0x180030af1`
- `0x180030af7`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>::get_Completed(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 result; // rax

  *a2 = 0;
  v2 = a1 + 56;
  if ( !a1 )
    v2 = 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)v2);
  v5 = a1 + 64;
  if ( !a1 )
    v5 = 80;
  v6 = *(_QWORD *)v5;
  if ( *(_QWORD *)v5 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*(_QWORD *)v5);
  ReleaseSRWLockExclusive_0((PSRWLOCK)v2);
  result = 0;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180018890  mov     [rsp+arg_0], rbx
0x180018895  mov     [rsp+arg_8], rsi
0x18001889a  push    rdi
0x18001889b  sub     rsp, 20h
0x18001889f  test    rcx, rcx
0x1800188a2  mov     qword ptr [rdx], 0
0x1800188a9  lea     rdi, [rcx+38h]
0x1800188ad  mov     eax, 48h ; 'H'
0x1800188b2  cmovz   rdi, rax
0x1800188b6  mov     rbx, rcx
0x1800188b9  mov     rcx, rdi; SRWLock
0x1800188bc  mov     rsi, rdx
0x1800188bf  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800188c4  test    rbx, rbx
0x1800188c7  lea     rax, [rbx+40h]
0x1800188cb  mov     ecx, 50h ; 'P'
0x1800188d0  cmovz   rax, rcx
0x1800188d4  mov     rbx, [rax]
0x1800188d7  test    rbx, rbx
0x1800188da  jz      short loc_1800188EC
0x1800188dc  mov     rax, [rbx]
0x1800188df  mov     rcx, rbx
0x1800188e2  mov     rax, [rax+8]
0x1800188e6  call    cs:__guard_dispatch_icall_fptr
0x1800188ec  mov     rcx, rdi; SRWLock
0x1800188ef  call    ReleaseSRWLockExclusive_0
0x1800188f4  xor     eax, eax
0x1800188f6  mov     [rsi], rbx
0x1800188f9  mov     rbx, [rsp+28h+arg_0]
0x1800188fe  mov     rsi, [rsp+28h+arg_8]
0x180018903  add     rsp, 20h
0x180018907  pop     rdi
0x180018908  retn
```

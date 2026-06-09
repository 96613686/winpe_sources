# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>::put_Completed(void *)

- ea: `0x180018910`
- end: `0x180018a1e`
- name: `?put_Completed@?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkloadManager@implementation@Workloads@3Microsoft@4@Uhstring@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAX@Z`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800040a0`
- `0x180018910`
- `0x1800196b0`
- `0x180019700`
- `0x18001af50`
- `0x180030af1`
- `0x180030af7`
- `0x180034ef0`
- `0x180036f4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>::put_Completed(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdi
  RTL_SRWLOCK *v4; // rbx
  __int64 *v5; // rsi
  __int64 *v6; // rdi
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h] BYREF

  v11 = a2;
  v3 = a1 - 16;
  if ( !a1 )
    v3 = 0;
  v4 = (RTL_SRWLOCK *)(v3 + 72);
  v9 = v3 + 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(v3 + 72));
  if ( *(_BYTE *)(v3 + 100) )
  {
    winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment((winrt::hresult_illegal_delegate_assignment *)pExceptionObject);
    throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
  }
  *(_BYTE *)(v3 + 100) = 1;
  LODWORD(v9) = *(_DWORD *)(v3 + 96);
  if ( (_DWORD)v9 )
  {
    ReleaseSRWLockExclusive_0((PSRWLOCK)(v3 + 72));
    if ( a2 )
      winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,enum winrt::Windows::Foundation::AsyncStatus>(
        &v11,
        v3,
        (unsigned int *)&v9);
  }
  else
  {
    v5 = winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>(
           &v9,
           &v11);
    v6 = (__int64 *)(v3 + 80);
    if ( v6 != v5 )
    {
      if ( *v6 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
      v7 = *v5;
      *v5 = 0;
      *v6 = v7;
    }
    if ( v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    ReleaseSRWLockExclusive_0(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180018910  mov     [rsp+arg_10], rbx
0x180018915  push    rsi
0x180018916  push    rdi
0x180018917  push    r14
0x180018919  sub     rsp, 50h
0x18001891d  mov     rax, cs:__security_cookie
0x180018924  xor     rax, rsp
0x180018927  mov     [rsp+68h+var_20], rax
0x18001892c  mov     rsi, rdx
0x18001892f  mov     [rsp+68h+var_28], rdx
0x180018934  lea     rdi, [rcx-10h]
0x180018938  xor     r14d, r14d
0x18001893b  test    rcx, rcx
0x18001893e  cmovz   rdi, r14
0x180018942  lea     rbx, [rdi+48h]
0x180018946  mov     [rsp+68h+var_48], rbx
0x18001894b  mov     rcx, rbx; SRWLock
0x18001894e  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180018953  nop
0x180018954  cmp     [rdi+64h], r14b
0x180018958  jnz     loc_180018A01
0x18001895e  mov     byte ptr [rdi+64h], 1
0x180018962  mov     eax, [rdi+60h]
0x180018965  mov     dword ptr [rsp+68h+var_48], eax
0x180018969  test    eax, eax
0x18001896b  jnz     short loc_1800189BC
0x18001896d  lea     rdx, [rsp+68h+var_28]
0x180018972  lea     rcx, [rsp+68h+var_48]
0x180018977  call    ??$make_agile_delegate@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>>(winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &)
0x18001897c  mov     rsi, rax
0x18001897f  add     rdi, 50h ; 'P'
0x180018983  cmp     rdi, rax
0x180018986  jz      short loc_18001899F
0x180018988  cmp     qword ptr [rdi], 0
0x18001898c  jz      short loc_180018996
0x18001898e  mov     rcx, rdi
0x180018991  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180018996  mov     rcx, [rsi]
0x180018999  mov     [rsi], r14
0x18001899c  mov     [rdi], rcx
0x18001899f  cmp     [rsp+68h+var_48], 0
0x1800189a5  jz      short loc_1800189B2
0x1800189a7  lea     rcx, [rsp+68h+var_48]
0x1800189ac  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800189b1  nop
0x1800189b2  mov     rcx, rbx; SRWLock
0x1800189b5  call    ReleaseSRWLockExclusive_0
0x1800189ba  jmp     short loc_1800189DB
0x1800189bc  mov     rcx, rbx; SRWLock
0x1800189bf  call    ReleaseSRWLockExclusive_0
0x1800189c4  test    rsi, rsi
0x1800189c7  jz      short loc_1800189DB
0x1800189c9  lea     r8, [rsp+68h+var_48]
0x1800189ce  mov     rdx, rdi
0x1800189d1  lea     rcx, [rsp+68h+var_28]
0x1800189d6  call    ??$invoke@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBU?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UPackageDeploymentProgress@Deployment@Management@7Microsoft@8@@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x1800189db  xor     eax, eax
0x1800189dd  jmp     short loc_1800189E3
0x1800189df  mov     eax, dword ptr [rsp+68h+var_48]
0x1800189e3  mov     rcx, [rsp+68h+var_20]
0x1800189e8  xor     rcx, rsp; StackCookie
0x1800189eb  call    __security_check_cookie
0x1800189f0  mov     rbx, [rsp+68h+arg_10]
0x1800189f8  add     rsp, 50h
0x1800189fc  pop     r14
0x1800189fe  pop     rdi
0x1800189ff  pop     rsi
0x180018a00  retn
0x180018a01  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180018a06  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@XZ; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(void)
0x180018a0b  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180018a12  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180018a17  call    _CxxThrowException
```

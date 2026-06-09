# winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator::`scalar deleting destructor'(uint)

- ea: `0x18000dfd0`
- end: `0x18000e034`
- name: `??_Giterator@?$iterable_base@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWorkload@Workloads@Windows@Microsoft@3@Ucollection_version@23@@winrt@@UEAAPEAXI@Z`
- size: `100`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c530`
- `0x18000dfd0`
- `0x18000e550`
- `0x18003509c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000e02d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000e02d`

## pseudocode

```c
_QWORD *__fastcall winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  if ( a1[4] )
    winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref();
  winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(a1);
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
    abort();
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000dfd0  mov     [rsp+arg_8], rbx
0x18000dfd5  push    rdi
0x18000dfd6  sub     rsp, 20h
0x18000dfda  mov     rbx, rcx
0x18000dfdd  mov     edi, edx
0x18000dfdf  add     rcx, 20h ; ' '
0x18000dfe3  cmp     qword ptr [rcx], 0
0x18000dfe7  jz      short loc_18000DFEE
0x18000dfe9  call    ?unconditional_release_ref@?$com_ptr@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(void)
0x18000dfee  mov     rcx, rbx
0x18000dff1  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x18000dff6  mov     eax, 0FFFFFFFFh
0x18000dffb  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000e003  sub     eax, 1
0x18000e006  jnz     short loc_18000E029
0x18000e008  test    dil, 1
0x18000e00c  jz      short loc_18000E01B
0x18000e00e  mov     edx, 38h ; '8'; unsigned __int64
0x18000e013  mov     rcx, rbx; void *
0x18000e016  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e01b  mov     rax, rbx
0x18000e01e  mov     rbx, [rsp+28h+arg_8]
0x18000e023  add     rsp, 20h
0x18000e027  pop     rdi
0x18000e028  retn
0x18000e029  test    eax, eax
0x18000e02b  jns     short loc_18000E008
0x18000e02d  call    cs:__imp_abort
```

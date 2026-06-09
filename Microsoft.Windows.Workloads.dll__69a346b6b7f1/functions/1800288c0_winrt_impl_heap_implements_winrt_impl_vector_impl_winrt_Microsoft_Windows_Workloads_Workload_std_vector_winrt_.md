# winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>>::`scalar deleting destructor'(uint)

- ea: `0x1800288c0`
- end: `0x18002891e`
- name: `??_G?$heap_implements@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `94`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c530`
- `0x180025380`
- `0x1800288c0`
- `0x18003509c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180028917`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180028917`

## pseudocode

```c
char *__fastcall winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>>::`scalar deleting destructor'(
        char *a1,
        char a2)
{
  std::vector<winrt::Microsoft::Windows::Workloads::Workload>::~vector<winrt::Microsoft::Windows::Workloads::Workload>(a1 + 48);
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
0x1800288c0  mov     [rsp+arg_8], rbx
0x1800288c5  push    rdi
0x1800288c6  sub     rsp, 20h
0x1800288ca  mov     rbx, rcx
0x1800288cd  mov     edi, edx
0x1800288cf  add     rcx, 30h ; '0'
0x1800288d3  call    ??1?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Microsoft::Windows::Workloads::Workload>::~vector<winrt::Microsoft::Windows::Workloads::Workload>(void)
0x1800288d8  mov     rcx, rbx
0x1800288db  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x1800288e0  mov     eax, 0FFFFFFFFh
0x1800288e5  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800288ed  sub     eax, 1
0x1800288f0  jnz     short loc_180028913
0x1800288f2  test    dil, 1
0x1800288f6  jz      short loc_180028905
0x1800288f8  mov     edx, 48h ; 'H'; unsigned __int64
0x1800288fd  mov     rcx, rbx; void *
0x180028900  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028905  mov     rax, rbx
0x180028908  mov     rbx, [rsp+28h+arg_8]
0x18002890d  add     rsp, 20h
0x180028911  pop     rdi
0x180028912  retn
0x180028913  test    eax, eax
0x180028915  jns     short loc_1800288F2
0x180028917  call    cs:__imp_abort
```

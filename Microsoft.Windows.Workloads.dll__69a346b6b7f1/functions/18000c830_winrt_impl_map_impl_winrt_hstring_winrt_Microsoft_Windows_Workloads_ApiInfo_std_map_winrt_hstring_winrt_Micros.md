# winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>::`vector deleting destructor'(uint)

- ea: `0x18000c830`
- end: `0x18000c88e`
- name: `??_E?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@UEAAPEAXI@Z`
- size: `94`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a350`
- `0x18000c530`
- `0x18000c830`
- `0x18003509c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000c887`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000c887`

## pseudocode

```c
char *__fastcall winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vector deleting destructor'(
        char *a1,
        char a2)
{
  std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::~_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>(a1 + 48);
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
0x18000c830  mov     [rsp+arg_8], rbx
0x18000c835  push    rdi
0x18000c836  sub     rsp, 20h
0x18000c83a  mov     rbx, rcx
0x18000c83d  mov     edi, edx
0x18000c83f  add     rcx, 30h ; '0'
0x18000c843  call    ??1?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::~_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>(void)
0x18000c848  mov     rcx, rbx
0x18000c84b  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x18000c850  mov     eax, 0FFFFFFFFh
0x18000c855  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000c85d  sub     eax, 1
0x18000c860  jnz     short loc_18000C883
0x18000c862  test    dil, 1
0x18000c866  jz      short loc_18000C875
0x18000c868  mov     edx, 40h ; '@'; unsigned __int64
0x18000c86d  mov     rcx, rbx; void *
0x18000c870  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c875  mov     rax, rbx
0x18000c878  mov     rbx, [rsp+28h+arg_8]
0x18000c87d  add     rsp, 20h
0x18000c881  pop     rdi
0x18000c882  retn
0x18000c883  test    eax, eax
0x18000c885  jns     short loc_18000C862
0x18000c887  call    cs:__imp_abort
```

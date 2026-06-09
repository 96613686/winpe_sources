# winrt::implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::~implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>(void)

- ea: `0x180004be0`
- end: `0x180004c0b`
- name: `??1?$implements@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@5673@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@5673@@winrt@@UEAA@XZ`
- size: `43`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003caec`
- `0x18003cbac`
- `0x18003e030`
- `0x18003e990`
- `0x18003e9e0`
- `0x18003efbc`

## callees

- `0x180004be0`
- `0x18000c530`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004c04`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004c04`

## pseudocode

```c
__int64 winrt::implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::~implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>()
{
  __int64 result; // rax

  winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference();
  result = (unsigned int)_InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock);
  if ( (int)result < 0 )
    abort();
  return result;
}

```

## disassembly

```asm
0x180004be0  sub     rsp, 28h
0x180004be4  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x180004be9  mov     eax, 0FFFFFFFFh
0x180004bee  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180004bf6  sub     eax, 1
0x180004bf9  jnz     short loc_180004C00
0x180004bfb  add     rsp, 28h
0x180004bff  retn
0x180004c00  test    eax, eax
0x180004c02  jns     short loc_180004BFB
0x180004c04  call    cs:__imp_abort
```

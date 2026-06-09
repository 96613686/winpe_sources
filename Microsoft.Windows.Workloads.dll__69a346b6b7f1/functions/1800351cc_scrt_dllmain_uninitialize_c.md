# __scrt_dllmain_uninitialize_c

- ea: `0x1800351cc`
- end: `0x1800351fc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035668`

## callees

- `0x18000a3c0`
- `0x1800351cc`
- `0x180035e70`
- `0x18003977b`
- `0x180039787`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !(unsigned int)winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::Close() )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x1800351cc  sub     rsp, 28h
0x1800351d0  call    __scrt_is_ucrt_dll_in_use
0x1800351d5  test    eax, eax
0x1800351d7  jz      short loc_1800351E9
0x1800351d9  lea     rcx, Table; Table
0x1800351e0  add     rsp, 28h
0x1800351e4  jmp     _execute_onexit_table_0
0x1800351e9  call    ?Close@?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkloadManager@implementation@Workloads@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@UEAAHXZ; winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::Close(void)
0x1800351ee  test    eax, eax
0x1800351f0  jnz     short loc_1800351F7
0x1800351f2  call    _cexit_0
0x1800351f7  add     rsp, 28h
0x1800351fb  retn
```

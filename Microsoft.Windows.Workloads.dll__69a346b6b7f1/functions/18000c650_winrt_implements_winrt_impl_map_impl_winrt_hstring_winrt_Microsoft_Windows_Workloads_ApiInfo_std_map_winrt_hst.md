# winrt::implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c650`
- end: `0x18000c6d5`
- name: `?QueryInterface@?$implements@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@5673@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@5673@@winrt@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `133`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a4f0`
- `0x18000a790`
- `0x18000a940`
- `0x18000ab70`
- `0x180025be0`
- `0x180026030`

## callees

- `0x18000c650`
- `0x18000ec80`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::QueryInterface(
        volatile signed __int64 *a1,
        const void *a2,
        __int64 *a3)
{
  __int64 v6; // rax
  signed __int64 v7; // rax
  signed __int64 v8; // rtt

  v6 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 48))(a1);
  *a3 = v6;
  if ( !v6 )
    return winrt::impl::root_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::query_interface_common(
             a1,
             a2,
             a3);
  v7 = *((_QWORD *)a1 + 1);
  if ( v7 < 0 )
  {
LABEL_5:
    _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
  }
  else
  {
    while ( 1 )
    {
      v8 = v7;
      v7 = _InterlockedCompareExchange64(a1 + 1, v7 + 1, v7);
      if ( v8 == v7 )
        break;
      if ( v7 < 0 )
        goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c650  mov     [rsp+arg_0], rbx
0x18000c655  mov     [rsp+arg_8], rsi
0x18000c65a  push    rdi
0x18000c65b  sub     rsp, 20h
0x18000c65f  mov     rax, [rcx]
0x18000c662  mov     rdi, r8
0x18000c665  mov     rsi, rdx
0x18000c668  mov     rbx, rcx
0x18000c66b  mov     rax, [rax+30h]
0x18000c66f  call    cs:__guard_dispatch_icall_fptr
0x18000c675  mov     [rdi], rax
0x18000c678  test    rax, rax
0x18000c67b  jz      short loc_18000C6B8
0x18000c67d  mov     rax, [rbx+8]
0x18000c681  test    rax, rax
0x18000c684  js      short loc_18000C6A1
0x18000c686  nop     word ptr [rax+rax+00000000h]
0x18000c690  lea     rcx, [rax+1]
0x18000c694  lock cmpxchg [rbx+8], rcx
0x18000c69a  jz      short loc_18000C6A6
0x18000c69c  test    rax, rax
0x18000c69f  jns     short loc_18000C690
0x18000c6a1  lock inc dword ptr [rax+rax+18h]
0x18000c6a6  xor     eax, eax
0x18000c6a8  mov     rbx, [rsp+28h+arg_0]
0x18000c6ad  mov     rsi, [rsp+28h+arg_8]
0x18000c6b2  add     rsp, 20h
0x18000c6b6  pop     rdi
0x18000c6b7  retn
0x18000c6b8  mov     r8, rdi
0x18000c6bb  mov     rdx, rsi
0x18000c6be  mov     rcx, rbx
0x18000c6c1  mov     rbx, [rsp+28h+arg_0]
0x18000c6c6  mov     rsi, [rsp+28h+arg_8]
0x18000c6cb  add     rsp, 20h
0x18000c6cf  pop     rdi
0x18000c6d0  jmp     ?query_interface_common@?$root_implements@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@U13456@UIWorkloadManager2@3456@UIWorkloadManager3@3456@UIWorkloadManager4@3456@UIWorkloadManager5@3456@UIWorkloadManager6@3456@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager,winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManager2,winrt::Microsoft::Windows::Workloads::IWorkloadManager3,winrt::Microsoft::Windows::Workloads::IWorkloadManager4,winrt::Microsoft::Windows::Workloads::IWorkloadManager5,winrt::Microsoft::Windows::Workloads::IWorkloadManager6>::query_interface_common(winrt::guid const &,void * *)
```

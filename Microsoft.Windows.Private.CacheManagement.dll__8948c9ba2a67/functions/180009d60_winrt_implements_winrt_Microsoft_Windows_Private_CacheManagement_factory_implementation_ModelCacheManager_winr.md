# winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009d60`
- end: `0x180009de5`
- name: `?QueryInterface@?$implements@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@UIModelCacheManagerStatics@34567@@winrt@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(volatile signed __int64 *, const void *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008fd0`
- `0x1800090d0`

## callees

- `0x180009d60`
- `0x18000bb30`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::QueryInterface(
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
    return winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(
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
0x180009d60  mov     [rsp+arg_0], rbx
0x180009d65  mov     [rsp+arg_8], rsi
0x180009d6a  push    rdi
0x180009d6b  sub     rsp, 20h
0x180009d6f  mov     rax, [rcx]
0x180009d72  mov     rdi, r8
0x180009d75  mov     rsi, rdx
0x180009d78  mov     rbx, rcx
0x180009d7b  mov     rax, [rax+30h]
0x180009d7f  call    cs:__guard_dispatch_icall_fptr
0x180009d85  mov     [rdi], rax
0x180009d88  test    rax, rax
0x180009d8b  jz      short loc_180009DC8
0x180009d8d  mov     rax, [rbx+8]
0x180009d91  test    rax, rax
0x180009d94  js      short loc_180009DB1
0x180009d96  nop     word ptr [rax+rax+00000000h]
0x180009da0  lea     rcx, [rax+1]
0x180009da4  lock cmpxchg [rbx+8], rcx
0x180009daa  jz      short loc_180009DB6
0x180009dac  test    rax, rax
0x180009daf  jns     short loc_180009DA0
0x180009db1  lock inc dword ptr [rax+rax+18h]
0x180009db6  xor     eax, eax
0x180009db8  mov     rbx, [rsp+28h+arg_0]
0x180009dbd  mov     rsi, [rsp+28h+arg_8]
0x180009dc2  add     rsp, 20h
0x180009dc6  pop     rdi
0x180009dc7  retn
0x180009dc8  mov     r8, rdi
0x180009dcb  mov     rdx, rsi
0x180009dce  mov     rcx, rbx
0x180009dd1  mov     rbx, [rsp+28h+arg_0]
0x180009dd6  mov     rsi, [rsp+28h+arg_8]
0x180009ddb  add     rsp, 20h
0x180009ddf  pop     rdi
0x180009de0  jmp     ?query_interface_common@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(winrt::guid const &,void * *)
```

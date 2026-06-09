# winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Release(void)

- ea: `0x180008a30`
- end: `0x180008a7d`
- name: `?Release@?$produce_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@UEAAIXZ`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008a30`
- `0x180009b70`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Release(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = a1 - 16;
  if ( !a1 )
    v1 = 0;
  result = winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(v1);
  if ( !(_DWORD)result )
  {
    *(_QWORD *)(v1 + 8) = 1;
    *(_QWORD *)(v1 + 120) |= 1uLL;
    (*(void (__fastcall **)(__int64))(v1 + 112))(v1 + 112);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008a30  mov     [rsp+arg_8], rbx
0x180008a35  push    rdi
0x180008a36  sub     rsp, 20h
0x180008a3a  xor     eax, eax
0x180008a3c  lea     rbx, [rcx-10h]
0x180008a40  test    rcx, rcx
0x180008a43  cmovz   rbx, rax
0x180008a47  mov     rcx, rbx
0x180008a4a  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180008a4f  mov     edi, eax
0x180008a51  test    eax, eax
0x180008a53  jnz     short loc_180008A72
0x180008a55  mov     qword ptr [rbx+8], 1
0x180008a5d  or      qword ptr [rbx+78h], 1
0x180008a62  lea     rcx, [rbx+70h]
0x180008a66  mov     rax, [rbx+70h]
0x180008a6a  call    cs:__guard_dispatch_icall_fptr
0x180008a70  mov     eax, edi
0x180008a72  mov     rbx, [rsp+28h+arg_8]
0x180008a77  add     rsp, 20h
0x180008a7b  pop     rdi
0x180008a7c  retn
```

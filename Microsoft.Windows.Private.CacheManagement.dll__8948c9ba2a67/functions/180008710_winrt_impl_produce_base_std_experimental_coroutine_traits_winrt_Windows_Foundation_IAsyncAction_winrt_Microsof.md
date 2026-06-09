# winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo,void>::Release(void)

- ea: `0x180008710`
- end: `0x18000875d`
- name: `?Release@?$produce_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@X@impl@winrt@@UEAAIXZ`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008710`
- `0x180009b70`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo,void>::Release(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = a1 - 24;
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
0x180008710  mov     [rsp+arg_8], rbx
0x180008715  push    rdi
0x180008716  sub     rsp, 20h
0x18000871a  xor     eax, eax
0x18000871c  lea     rbx, [rcx-18h]
0x180008720  test    rcx, rcx
0x180008723  cmovz   rbx, rax
0x180008727  mov     rcx, rbx
0x18000872a  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x18000872f  mov     edi, eax
0x180008731  test    eax, eax
0x180008733  jnz     short loc_180008752
0x180008735  mov     qword ptr [rbx+8], 1
0x18000873d  or      qword ptr [rbx+78h], 1
0x180008742  lea     rcx, [rbx+70h]
0x180008746  mov     rax, [rbx+70h]
0x18000874a  call    cs:__guard_dispatch_icall_fptr
0x180008750  mov     eax, edi
0x180008752  mov     rbx, [rsp+28h+arg_8]
0x180008757  add     rsp, 20h
0x18000875b  pop     rdi
0x18000875c  retn
```

# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type::~promise_type(void)

- ea: `0x180005d90`
- end: `0x180005dec`
- name: `??1promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UEAA@XZ`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001dbd9`
- `0x18001dca5`

## callees

- `0x180003840`
- `0x180005d90`
- `0x180009b70`
- `0x180017d94`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005de5`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005de5`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type::~promise_type(
        _QWORD *a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  v2 = a1 + 11;
  if ( *v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
  if ( a1[10] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 10);
  __ExceptionPtrDestroy(a1 + 7);
  winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(a1);
  result = (unsigned int)_InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock);
  if ( (int)result < 0 )
    abort();
  return result;
}

```

## disassembly

```asm
0x180005d90  push    rbx
0x180005d92  sub     rsp, 20h
0x180005d96  mov     rbx, rcx
0x180005d99  add     rcx, 58h ; 'X'
0x180005d9d  cmp     qword ptr [rcx], 0
0x180005da1  jz      short loc_180005DA8
0x180005da3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005da8  cmp     qword ptr [rbx+50h], 0
0x180005dad  lea     rcx, [rbx+50h]
0x180005db1  jz      short loc_180005DB8
0x180005db3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005db8  lea     rcx, [rbx+38h]; void *
0x180005dbc  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180005dc1  mov     rcx, rbx
0x180005dc4  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180005dc9  mov     eax, 0FFFFFFFFh
0x180005dce  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005dd6  sub     eax, 1
0x180005dd9  jnz     short loc_180005DE1
0x180005ddb  add     rsp, 20h
0x180005ddf  pop     rbx
0x180005de0  retn
0x180005de1  test    eax, eax
0x180005de3  jns     short loc_180005DDB
0x180005de5  call    cs:__imp_abort
```

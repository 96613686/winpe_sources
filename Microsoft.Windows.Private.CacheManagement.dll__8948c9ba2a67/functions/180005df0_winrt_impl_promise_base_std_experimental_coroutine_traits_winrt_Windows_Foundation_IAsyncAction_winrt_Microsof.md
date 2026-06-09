# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`scalar deleting destructor'(uint)

- ea: `0x180005df0`
- end: `0x180005e6d`
- name: `??_G?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@UEAAPEAXI@Z`
- size: `125`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003840`
- `0x180005df0`
- `0x180009b70`
- `0x180017d94`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005e66`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180005e66`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  _QWORD *v4; // rcx

  v4 = a1 + 11;
  if ( *v4 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4);
  if ( a1[10] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 10);
  __ExceptionPtrDestroy(a1 + 7);
  winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(a1);
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
    abort();
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180005df0  mov     [rsp+arg_8], rbx
0x180005df5  push    rdi
0x180005df6  sub     rsp, 20h
0x180005dfa  mov     rbx, rcx
0x180005dfd  mov     edi, edx
0x180005dff  add     rcx, 58h ; 'X'
0x180005e03  cmp     qword ptr [rcx], 0
0x180005e07  jz      short loc_180005E0E
0x180005e09  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005e0e  cmp     qword ptr [rbx+50h], 0
0x180005e13  lea     rcx, [rbx+50h]
0x180005e17  jz      short loc_180005E1E
0x180005e19  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005e1e  lea     rcx, [rbx+38h]; void *
0x180005e22  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180005e27  mov     rcx, rbx
0x180005e2a  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180005e2f  mov     eax, 0FFFFFFFFh
0x180005e34  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005e3c  sub     eax, 1
0x180005e3f  jnz     short loc_180005E62
0x180005e41  test    dil, 1
0x180005e45  jz      short loc_180005E54
0x180005e47  mov     edx, 68h ; 'h'; unsigned __int64
0x180005e4c  mov     rcx, rbx; void *
0x180005e4f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005e54  mov     rax, rbx
0x180005e57  mov     rbx, [rsp+28h+arg_8]
0x180005e5c  add     rsp, 20h
0x180005e60  pop     rdi
0x180005e61  retn
0x180005e62  test    eax, eax
0x180005e64  jns     short loc_180005E41
0x180005e66  call    cs:__imp_abort
```

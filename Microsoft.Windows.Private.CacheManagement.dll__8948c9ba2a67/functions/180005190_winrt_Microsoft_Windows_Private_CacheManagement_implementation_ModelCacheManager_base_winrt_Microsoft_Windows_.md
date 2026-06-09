# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::~ModelCacheManager_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>(void)

- ea: `0x180005190`
- end: `0x1800051bb`
- name: `??1?$ModelCacheManager_base@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@$$V@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UEAA@XZ`
- size: `43`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180005190`
- `0x180009b70`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800051b4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800051b4`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::~ModelCacheManager_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>(
        __int64 a1)
{
  __int64 result; // rax

  winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(a1);
  result = (unsigned int)_InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock);
  if ( (int)result < 0 )
    abort();
  return result;
}

```

## disassembly

```asm
0x180005190  sub     rsp, 28h
0x180005194  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x180005199  mov     eax, 0FFFFFFFFh
0x18000519e  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800051a6  sub     eax, 1
0x1800051a9  jnz     short loc_1800051B0
0x1800051ab  add     rsp, 28h
0x1800051af  retn
0x1800051b0  test    eax, eax
0x1800051b2  jns     short loc_1800051AB
0x1800051b4  call    cs:__imp_abort
```

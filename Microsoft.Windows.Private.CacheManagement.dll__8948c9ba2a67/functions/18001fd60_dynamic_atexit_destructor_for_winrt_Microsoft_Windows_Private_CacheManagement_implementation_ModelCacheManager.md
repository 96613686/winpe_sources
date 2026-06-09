# _dynamic_atexit_destructor_for__winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance__

- ea: `0x18001fd60`
- end: `0x18001fd77`
- name: `_dynamic_atexit_destructor_for__winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance__`
- size: `23`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003840`
- `0x18001fd60`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance__()
{
  __int64 result; // rax

  if ( winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance);
  return result;
}

```

## disassembly

```asm
0x18001fd60  cmp     cs:?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A, 0; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x18001fd68  jz      short locret_18001FD76
0x18001fd6a  lea     rcx, ?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x18001fd71  jmp     ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fd76  retn
```

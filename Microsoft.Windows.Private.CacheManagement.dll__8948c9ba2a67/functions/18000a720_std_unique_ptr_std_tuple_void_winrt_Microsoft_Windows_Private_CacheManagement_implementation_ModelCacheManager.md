# std::unique_ptr<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>,std::default_delete<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>>>::~unique_ptr<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>,std::default_delete<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>>>(void)

- ea: `0x18000a720`
- end: `0x18000a733`
- name: `??1?$unique_ptr@V?$tuple@P8ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@EAAXXZPEAU1234567@@std@@U?$default_delete@V?$tuple@P8ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@EAAXXZPEAU1234567@@std@@@2@@std@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001db10`

## callees

- `0x18000a720`
- `0x180018238`

## pseudocode

```c
void __fastcall std::unique_ptr<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>>::~unique_ptr<std::tuple<void (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::*)(void),winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1, 0x18u);
}

```

## disassembly

```asm
0x18000a720  mov     rcx, [rcx]; void *
0x18000a723  test    rcx, rcx
0x18000a726  jz      short locret_18000A732
0x18000a728  mov     edx, 18h; unsigned __int64
0x18000a72d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a732  retn
```

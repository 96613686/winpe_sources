# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2,void>::GetRuntimeClassName(void * *)

- ea: `0x180008f30`
- end: `0x180008f46`
- name: `?GetRuntimeClassName@?$produce_base@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager2@34567@X@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000abb0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2,void>::GetRuntimeClassName(
        __int64 a1)
{
  __int64 v1; // rax

  v1 = a1 - 24;
  if ( !a1 )
    v1 = 0;
  return winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::NonDelegatingGetRuntimeClassName(v1);
}

```

## disassembly

```asm
0x180008f30  xor     r8d, r8d
0x180008f33  lea     rax, [rcx-18h]
0x180008f37  test    rcx, rcx
0x180008f3a  cmovz   rax, r8
0x180008f3e  mov     rcx, rax
0x180008f41  jmp     ?NonDelegatingGetRuntimeClassName@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAHPEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::NonDelegatingGetRuntimeClassName(void * *)
```

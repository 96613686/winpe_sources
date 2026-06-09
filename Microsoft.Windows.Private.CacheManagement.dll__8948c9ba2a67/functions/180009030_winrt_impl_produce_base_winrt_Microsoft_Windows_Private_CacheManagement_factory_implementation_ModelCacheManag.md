# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::GetRuntimeClassName(void * *)

- ea: `0x180009030`
- end: `0x180009046`
- name: `?GetRuntimeClassName@?$produce_base@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@X@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000abb0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,void>::GetRuntimeClassName(
        __int64 a1)
{
  __int64 v1; // rax

  v1 = a1 - 16;
  if ( !a1 )
    v1 = 0;
  return winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::NonDelegatingGetRuntimeClassName(v1);
}

```

## disassembly

```asm
0x180009030  xor     r8d, r8d
0x180009033  lea     rax, [rcx-10h]
0x180009037  test    rcx, rcx
0x18000903a  cmovz   rax, r8
0x18000903e  mov     rcx, rax
0x180009041  jmp     ?NonDelegatingGetRuntimeClassName@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAHPEAPEAX@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::NonDelegatingGetRuntimeClassName(void * *)
```

# winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180009050`
- end: `0x180009066`
- name: `?GetIids@?$produce_base@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager@34567@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009cc0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v3; // rax

  v3 = a1 - 16;
  if ( !a1 )
    v3 = 0;
  return winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::GetIids(
           v3,
           a2,
           a3);
}

```

## disassembly

```asm
0x180009050  xor     r9d, r9d
0x180009053  lea     rax, [rcx-10h]
0x180009057  test    rcx, rcx
0x18000905a  cmovz   rax, r9
0x18000905e  mov     rcx, rax
0x180009061  jmp     ?GetIids@?$implements@UModelCacheManager@factory_implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@57@UIModelCacheManagerStatics@34567@@winrt@@QEAAJPEAKPEAPEAU_GUID@@@Z; winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::factory_implementation::ModelCacheManager,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManagerStatics>::GetIids(ulong *,_GUID * *)
```

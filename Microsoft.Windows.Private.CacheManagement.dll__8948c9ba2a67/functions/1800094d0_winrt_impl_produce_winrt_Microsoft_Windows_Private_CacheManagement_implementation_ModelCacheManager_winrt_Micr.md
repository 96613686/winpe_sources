# winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>::EnsureModelsAreCached(void)

- ea: `0x1800094d0`
- end: `0x18000952b`
- name: `?EnsureModelsAreCached@?$produce@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager@34567@@impl@winrt@@UEAAHXZ`
- size: `91`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800060e0`
- `0x180007ef0`
- `0x1800094d0`
- `0x18000ab70`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>::EnsureModelsAreCached(
        __int64 a1)
{
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *v1; // rbx
  __int64 result; // rax
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF
  int v4; // [rsp+40h] [rbp+8h] BYREF

  v1 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)(a1 - 16);
  if ( !a1 )
    v1 = 0;
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl'::`2'::impl) )
    {
      *((_DWORD *)v1 + 8) = 0;
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::UpdateActivityCoordinatorPolicy(v1);
    }
    v3[8] = 0;
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork(
      (__int64)v1,
      (__int64)v3,
      1u);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800094d0  mov     [rsp+arg_8], rbx
0x1800094d5  push    rdi
0x1800094d6  sub     rsp, 30h
0x1800094da  lea     rbx, [rcx-10h]
0x1800094de  xor     edi, edi
0x1800094e0  test    rcx, rcx
0x1800094e3  cmovz   rbx, rdi
0x1800094e7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55709058@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058> `wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl(void)'::`2'::impl
0x1800094ee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(void)
0x1800094f3  test    al, al
0x1800094f5  jz      short loc_180009502
0x1800094f7  mov     [rbx+20h], edi
0x1800094fa  mov     rcx, rbx; this
0x1800094fd  call    ?UpdateActivityCoordinatorPolicy@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAXXZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::UpdateActivityCoordinatorPolicy(void)
0x180009502  mov     [rsp+38h+var_10], dil
0x180009507  mov     r8b, 1
0x18000950a  lea     rdx, [rsp+38h+var_18]
0x18000950f  mov     rcx, rbx
0x180009512  call    ?EnqueueAllPackagesForCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXV?$optional@Uhstring@winrt@@@std@@_N@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork(std::optional<winrt::hstring>,bool)
0x180009517  xor     eax, eax
0x180009519  jmp     short loc_18000951F
0x18000951b  mov     eax, [rsp+38h+arg_0]
0x18000951f  mov     rbx, [rsp+38h+arg_8]
0x180009524  add     rsp, 30h
0x180009528  pop     rdi
0x180009529  retn
```

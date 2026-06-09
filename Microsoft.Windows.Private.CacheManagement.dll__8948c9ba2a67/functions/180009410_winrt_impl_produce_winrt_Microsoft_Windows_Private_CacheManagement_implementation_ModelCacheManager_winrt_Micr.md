# winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>::CacheModelsWithOfflineDriver(void *)

- ea: `0x180009410`
- end: `0x1800094c8`
- name: `?CacheModelsWithOfflineDriver@?$produce@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager@34567@@impl@winrt@@UEAAHPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(__int64, winrt::impl *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800060e0`
- `0x180007ef0`
- `0x180009410`
- `0x18000ab70`
- `0x1800127e0`
- `0x180016298`
- `0x18001629e`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094c0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>::CacheModelsWithOfflineDriver(
        __int64 a1,
        winrt::impl *a2)
{
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *v2; // rbx
  struct winrt::impl::hstring_header *v3; // rdx
  void *v4; // rbx
  int v5; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-28h] BYREF
  struct winrt::impl::hstring_header *v9; // [rsp+28h] [rbp-20h] BYREF
  char v10; // [rsp+30h] [rbp-18h]
  LPVOID *p_lpMem; // [rsp+38h] [rbp-10h]

  v2 = (winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)(a1 - 16);
  if ( !a1 )
    v2 = 0;
  try
  {
    lpMem = winrt::impl::duplicate_hstring(a2, a2);
    p_lpMem = &lpMem;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl'::`2'::impl) )
    {
      *((_DWORD *)v2 + 8) = 0;
      winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::UpdateActivityCoordinatorPolicy(v2);
    }
    v9 = winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v3);
    v10 = 1;
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork(
      (__int64)v2,
      (__int64)&v9,
      0);
    v4 = lpMem;
    if ( lpMem )
    {
      v5 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v5 )
      {
        if ( v5 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v4);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x180009410  mov     [rsp+arg_10], rbx
0x180009415  push    rdi
0x180009416  sub     rsp, 40h
0x18000941a  lea     rbx, [rcx-10h]
0x18000941e  xor     edi, edi
0x180009420  test    rcx, rcx
0x180009423  cmovz   rbx, rdi
0x180009427  mov     rcx, rdx; this
0x18000942a  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000942f  mov     [rsp+48h+lpMem], rax
0x180009434  lea     rax, [rsp+48h+lpMem]
0x180009439  mov     [rsp+48h+var_10], rax
0x18000943e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55709058@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058> `wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl(void)'::`2'::impl
0x180009445  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(void)
0x18000944a  test    al, al
0x18000944c  jz      short loc_180009459
0x18000944e  mov     [rbx+20h], edi
0x180009451  mov     rcx, rbx; this
0x180009454  call    ?UpdateActivityCoordinatorPolicy@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAAXXZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::UpdateActivityCoordinatorPolicy(void)
0x180009459  mov     rcx, [rsp+48h+lpMem]; this
0x18000945e  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180009463  mov     [rsp+48h+var_20], rax
0x180009468  mov     [rsp+48h+var_18], 1
0x18000946d  xor     r8d, r8d
0x180009470  lea     rdx, [rsp+48h+var_20]
0x180009475  mov     rcx, rbx
0x180009478  call    ?EnqueueAllPackagesForCacheWork@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXV?$optional@Uhstring@winrt@@@std@@_N@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::EnqueueAllPackagesForCacheWork(std::optional<winrt::hstring>,bool)
0x18000947d  nop
0x18000947e  mov     rbx, [rsp+48h+lpMem]
0x180009483  test    rbx, rbx
0x180009486  jz      short loc_1800094A9
0x180009488  mov     eax, 0FFFFFFFFh
0x18000948d  lock xadd [rbx+18h], eax
0x180009492  sub     eax, 1
0x180009495  jnz     short loc_1800094BC
0x180009497  call    WINRT_IMPL_GetProcessHeap
0x18000949c  mov     rcx, rax; hHeap
0x18000949f  mov     r8, rbx; lpMem
0x1800094a2  xor     edx, edx; dwFlags
0x1800094a4  call    WINRT_IMPL_HeapFree
0x1800094a9  xor     eax, eax
0x1800094ab  jmp     short loc_1800094B1
0x1800094ad  mov     eax, dword ptr [rsp+48h+lpMem]
0x1800094b1  mov     rbx, [rsp+48h+arg_10]
0x1800094b6  add     rsp, 40h
0x1800094ba  pop     rdi
0x1800094bb  retn
0x1800094bc  test    eax, eax
0x1800094be  jns     short loc_1800094A9
0x1800094c0  call    cs:__imp_abort
```

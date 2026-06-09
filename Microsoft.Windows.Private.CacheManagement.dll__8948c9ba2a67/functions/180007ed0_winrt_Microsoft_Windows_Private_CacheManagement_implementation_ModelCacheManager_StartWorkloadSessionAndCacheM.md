# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)

- ea: `0x180007ed0`
- end: `0x180007ee4`
- name: `?StartWorkloadSessionAndCacheModels_NoThrow@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUCacheQueueItem@1234567@@Z`
- size: `20`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__hidden this, const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005740`

## callees

- `0x180007410`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this,
        const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *a2)
{
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(
      this,
      a2);
  }
  catch ( ... )
  {
    if ( *(_QWORD *)a2 )
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
        "StartWorkloadSessionAndCacheModel failed with package: %ws",
        *(const char **)(*(_QWORD *)a2 + 16LL));
    else
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
        "StartWorkloadSessionAndCacheModel failed with package: %ws",
        (const char *)&S2);
  }
}

```

## disassembly

```asm
0x180007ed0  mov     [rsp+arg_8], rdx
0x180007ed5  sub     rsp, 38h
0x180007ed9  call    ?StartWorkloadSessionAndCacheModels@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUCacheQueueItem@1234567@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)
0x180007ede  nop
0x180007edf  add     rsp, 38h
0x180007ee3  retn
```

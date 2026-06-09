# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::~ModelCacheManager(void)

- ea: `0x1800050f0`
- end: `0x180005182`
- name: `??1ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UEAA@XZ`
- size: `146`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800050b0`

## callees

- `0x1800050f0`
- `0x1800091e0`
- `0x180009b70`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180005117`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005117`
- `USER32!UnregisterPowerSettingNotification` at `0x180005105`
- `USER32!UnregisterPowerSettingNotification` at `0x180005105`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!UnsubscribeActivityCoordinatorPolicy` at `0x180005129`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!UnsubscribeActivityCoordinatorPolicy` at `0x180005129`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!DestroyActivityCoordinatorPolicy` at `0x18000513b`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!DestroyActivityCoordinatorPolicy` at `0x18000513b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000517b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000517b`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x180005147`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x180005147`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::~ModelCacheManager(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this)
{
  void *v2; // rcx
  struct _TP_TIMER *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = (void *)*((_QWORD *)this + 34);
  if ( v2 )
    UnregisterPowerSettingNotification(v2);
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 32);
  if ( v3 )
    CloseThreadpoolTimer(v3);
  v4 = *((_QWORD *)this + 31);
  if ( v4 )
    UnsubscribeActivityCoordinatorPolicy(v4);
  v5 = *((_QWORD *)this + 30);
  if ( v5 )
    DestroyActivityCoordinatorPolicy(v5);
  if ( *((_DWORD *)this + 18) )
    terminate();
  std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::~vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>((__int64)this + 40);
  winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(this);
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
    abort();
}

```

## disassembly

```asm
0x1800050f0  push    rbx
0x1800050f2  sub     rsp, 20h
0x1800050f6  mov     rbx, rcx
0x1800050f9  mov     rcx, [rcx+110h]; Handle
0x180005100  test    rcx, rcx
0x180005103  jz      short loc_18000510B
0x180005105  call    cs:__imp_UnregisterPowerSettingNotification
0x18000510b  mov     rcx, [rbx+100h]; pti
0x180005112  test    rcx, rcx
0x180005115  jz      short loc_18000511D
0x180005117  call    cs:__imp_CloseThreadpoolTimer
0x18000511d  mov     rcx, [rbx+0F8h]
0x180005124  test    rcx, rcx
0x180005127  jz      short loc_18000512F
0x180005129  call    cs:__imp_UnsubscribeActivityCoordinatorPolicy
0x18000512f  mov     rcx, [rbx+0F0h]
0x180005136  test    rcx, rcx
0x180005139  jz      short loc_180005141
0x18000513b  call    cs:__imp_DestroyActivityCoordinatorPolicy
0x180005141  cmp     dword ptr [rbx+48h], 0
0x180005145  jz      short loc_18000514E
0x180005147  call    cs:__imp_terminate
0x18000514e  lea     rcx, [rbx+28h]
0x180005152  call    ??1?$vector@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@V?$allocator@UCacheQueueItem@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>::~vector<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem>(void)
0x180005157  mov     rcx, rbx
0x18000515a  call    ?subtract_final_reference@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::subtract_final_reference(void)
0x18000515f  mov     eax, 0FFFFFFFFh
0x180005164  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000516c  sub     eax, 1
0x18000516f  jnz     short loc_180005177
0x180005171  add     rsp, 20h
0x180005175  pop     rbx
0x180005176  retn
0x180005177  test    eax, eax
0x180005179  jns     short loc_180005171
0x18000517b  call    cs:__imp_abort
```

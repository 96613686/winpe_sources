# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ModelCacheManager(void)

- ea: `0x180004e80`
- end: `0x1800050a5`
- name: `??0ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ`
- size: `549`
- prototype: `winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005200`

## callees

- `0x180004e80`
- `0x18000ab70`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004fa4`
- `KERNEL32!GetLastError` at `0x180004fdf`
- `KERNEL32!GetLastError` at `0x18000503c`
- `KERNEL32!GetLastError` at `0x180004fa4`
- `KERNEL32!GetLastError` at `0x180004fdf`
- `KERNEL32!GetLastError` at `0x18000503c`
- `KERNEL32!SetLastError` at `0x180004fb7`
- `KERNEL32!SetLastError` at `0x180004ff2`
- `KERNEL32!SetLastError` at `0x18000504f`
- `KERNEL32!SetLastError` at `0x180004fb7`
- `KERNEL32!SetLastError` at `0x180004ff2`
- `KERNEL32!SetLastError` at `0x18000504f`
- `USER32!UnregisterPowerSettingNotification` at `0x180005047`
- `USER32!UnregisterPowerSettingNotification` at `0x180005047`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180005074`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180005074`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!UnsubscribeActivityCoordinatorPolicy` at `0x180004fea`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!UnsubscribeActivityCoordinatorPolicy` at `0x180004fea`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!DestroyActivityCoordinatorPolicy` at `0x180004faf`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!DestroyActivityCoordinatorPolicy` at `0x180004faf`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!CreateActivityCoordinatorPolicy` at `0x180004fcd`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!CreateActivityCoordinatorPolicy` at `0x180004fcd`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!SubscribeActivityCoordinatorPolicy` at `0x180005017`
- `ext-ms-win-resourcemanager-activitycoordinator-l1-1-0!SubscribeActivityCoordinatorPolicy` at `0x180005017`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ModelCacheManager(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this)
{
  __int64 v2; // rbp
  DWORD v3; // ebx
  __int64 v4; // rbp
  DWORD v5; // ebx
  void *v6; // rsi
  DWORD LastError; // ebx
  _QWORD Recipient[2]; // [rsp+20h] [rbp-48h] BYREF

  Recipient[0] = this;
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>::`vftable';
  *((_QWORD *)this + 3) = &winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::`vftable';
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_OWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 38) = -1;
  *((_DWORD *)this + 20) = 2;
  *((_DWORD *)this + 39) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_OWORD *)this + 11) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_OWORD *)this + 13) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_WORD *)this + 116) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 66) = 28800;
  *((_QWORD *)this + 34) = 0;
  *((_BYTE *)this + 280) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl'::`2'::impl) )
  {
    Recipient[0] = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::BatterySaverStateChangeCallback;
    Recipient[1] = this;
    v6 = (void *)*((_QWORD *)this + 34);
    if ( v6 )
    {
      LastError = GetLastError();
      UnregisterPowerSettingNotification(v6);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 34) = 0;
    PowerSettingRegisterNotification(&GUID_POWER_SAVING_STATUS, 2u, Recipient, (PHPOWERNOTIFY)this + 34);
  }
  else
  {
    v2 = *((_QWORD *)this + 30);
    if ( v2 )
    {
      v3 = GetLastError();
      DestroyActivityCoordinatorPolicy(v2);
      SetLastError(v3);
    }
    *((_QWORD *)this + 30) = 0;
    CreateActivityCoordinatorPolicy(0, (char *)this + 240);
    v4 = *((_QWORD *)this + 31);
    if ( v4 )
    {
      v5 = GetLastError();
      UnsubscribeActivityCoordinatorPolicy(v4);
      SetLastError(v5);
    }
    *((_QWORD *)this + 31) = 0;
    SubscribeActivityCoordinatorPolicy(
      *((_QWORD *)this + 30),
      &winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback,
      this,
      (char *)this + 248);
  }
  return this;
}

```

## disassembly

```asm
0x180004e80  mov     [rsp+arg_8], rbx
0x180004e85  mov     [rsp+arg_10], rbp
0x180004e8a  push    rsi
0x180004e8b  push    rdi
0x180004e8c  push    r12
0x180004e8e  push    r14
0x180004e90  push    r15
0x180004e92  sub     rsp, 40h
0x180004e96  mov     rax, cs:__security_cookie
0x180004e9d  xor     rax, rsp
0x180004ea0  mov     [rsp+68h+var_38], rax
0x180004ea5  mov     rdi, rcx
0x180004ea8  mov     [rsp+68h+Recipient], rcx
0x180004ead  lea     rax, ??_7?$produce@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>::`vftable'
0x180004eb4  mov     [rcx+10h], rax
0x180004eb8  lea     rax, ??_7?$produce@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UIModelCacheManager2@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::`vftable'
0x180004ebf  mov     [rcx+18h], rax
0x180004ec3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180004eca  mov     qword ptr [rcx+8], 1
0x180004ed2  lea     rax, ??_7?$heap_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::`vftable'
0x180004ed9  mov     [rcx], rax
0x180004edc  xor     r12d, r12d
0x180004edf  mov     [rcx+20h], r12d
0x180004ee3  mov     [rcx+28h], r12
0x180004ee7  mov     [rcx+30h], r12
0x180004eeb  mov     [rcx+38h], r12
0x180004eef  xorps   xmm0, xmm0
0x180004ef2  movups  xmmword ptr [rcx+40h], xmm0
0x180004ef6  movups  xmmword ptr [rcx+68h], xmm0
0x180004efa  movups  xmmword ptr [rcx+78h], xmm0
0x180004efe  movups  xmmword ptr [rcx+88h], xmm0
0x180004f05  mov     [rcx+58h], r12
0x180004f09  mov     [rcx+60h], r12
0x180004f0d  mov     dword ptr [rcx+98h], 0FFFFFFFFh
0x180004f17  mov     dword ptr [rcx+50h], 2
0x180004f1e  mov     [rcx+9Ch], r12d
0x180004f25  mov     [rcx+0A0h], r12
0x180004f2c  mov     [rcx+0A8h], r12
0x180004f33  xor     eax, eax
0x180004f35  movups  xmmword ptr [rcx+0B0h], xmm0
0x180004f3c  movups  xmmword ptr [rcx+0C0h], xmm0
0x180004f43  movups  xmmword ptr [rcx+0D0h], xmm0
0x180004f4a  mov     [rcx+0E0h], rax
0x180004f51  mov     [rcx+0E8h], ax
0x180004f58  mov     [rcx+0F0h], r12
0x180004f5f  mov     [rcx+0F8h], r12
0x180004f66  mov     [rcx+100h], r12
0x180004f6d  mov     dword ptr [rcx+108h], 7080h
0x180004f77  mov     [rcx+110h], r12
0x180004f7e  mov     [rcx+118h], al
0x180004f84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55709058@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058> `wil::Feature<__WilFeatureTraits_Feature_55709058>::GetImpl(void)'::`2'::impl
0x180004f8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::__private_IsEnabled(void)
0x180004f90  test    al, al
0x180004f92  jnz     loc_18000501F
0x180004f98  mov     rbp, [rdi+0F0h]
0x180004f9f  test    rbp, rbp
0x180004fa2  jz      short loc_180004FBD
0x180004fa4  call    cs:__imp_GetLastError
0x180004faa  mov     ebx, eax
0x180004fac  mov     rcx, rbp
0x180004faf  call    cs:__imp_DestroyActivityCoordinatorPolicy
0x180004fb5  mov     ecx, ebx; dwErrCode
0x180004fb7  call    cs:__imp_SetLastError
0x180004fbd  mov     [rdi+0F0h], r12
0x180004fc4  lea     rdx, [rdi+0F0h]
0x180004fcb  xor     ecx, ecx
0x180004fcd  call    cs:__imp_CreateActivityCoordinatorPolicy
0x180004fd3  mov     rbp, [rdi+0F8h]
0x180004fda  test    rbp, rbp
0x180004fdd  jz      short loc_180004FF8
0x180004fdf  call    cs:__imp_GetLastError
0x180004fe5  mov     ebx, eax
0x180004fe7  mov     rcx, rbp
0x180004fea  call    cs:__imp_UnsubscribeActivityCoordinatorPolicy
0x180004ff0  mov     ecx, ebx; dwErrCode
0x180004ff2  call    cs:__imp_SetLastError
0x180004ff8  mov     [rdi+0F8h], r12
0x180004fff  lea     r9, [rdi+0F8h]
0x180005006  mov     r8, rdi
0x180005009  lea     rdx, ?DeferredWorkEventCallback@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SAXW4_ACTIVITY_COORDINATOR_NOTIFICATION@@PEAX@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback(_ACTIVITY_COORDINATOR_NOTIFICATION,void *)
0x180005010  mov     rcx, [rdi+0F0h]
0x180005017  call    cs:__imp_SubscribeActivityCoordinatorPolicy
0x18000501d  jmp     short loc_18000507B
0x18000501f  lea     rax, ?BatterySaverStateChangeCallback@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SAKPEAXK0@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::BatterySaverStateChangeCallback(void *,ulong,void *)
0x180005026  mov     [rsp+68h+Recipient], rax
0x18000502b  mov     [rsp+68h+var_40], rdi
0x180005030  mov     rsi, [rdi+110h]
0x180005037  test    rsi, rsi
0x18000503a  jz      short loc_180005055
0x18000503c  call    cs:__imp_GetLastError
0x180005042  mov     ebx, eax
0x180005044  mov     rcx, rsi; Handle
0x180005047  call    cs:__imp_UnregisterPowerSettingNotification
0x18000504d  mov     ecx, ebx; dwErrCode
0x18000504f  call    cs:__imp_SetLastError
0x180005055  mov     [rdi+110h], r12
0x18000505c  lea     r9, [rdi+110h]; RegistrationHandle
0x180005063  lea     r8, [rsp+68h+Recipient]; Recipient
0x180005068  mov     edx, 2; Flags
0x18000506d  lea     rcx, GUID_POWER_SAVING_STATUS; SettingGuid
0x180005074  call    cs:__imp_PowerSettingRegisterNotification
0x18000507a  nop
0x18000507b  mov     rax, rdi
0x18000507e  mov     rcx, [rsp+68h+var_38]
0x180005083  xor     rcx, rsp; StackCookie
0x180005086  call    __security_check_cookie
0x18000508b  mov     rbx, [rsp+68h+arg_8]
0x180005090  mov     rbp, [rsp+68h+arg_10]
0x180005098  add     rsp, 40h
0x18000509c  pop     r15
0x18000509e  pop     r14
0x1800050a0  pop     r12
0x1800050a2  pop     rdi
0x1800050a3  pop     rsi
0x1800050a4  retn
```

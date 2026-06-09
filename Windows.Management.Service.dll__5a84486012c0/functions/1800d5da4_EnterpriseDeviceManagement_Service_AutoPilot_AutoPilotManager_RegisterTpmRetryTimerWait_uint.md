# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RegisterTpmRetryTimerWait(uint)

- ea: `0x1800d5da4`
- end: `0x1800d5fa7`
- name: `?RegisterTpmRetryTimerWait@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJI@Z`
- size: `515`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d2eb4`
- `0x1800d4320`
- `0x1800d5388`
- `0x1800d5890`

## callees

- `0x180067a34`
- `0x180067a54`
- `0x18006e0e8`
- `0x18007748c`
- `0x1800801fc`
- `0x180080708`
- `0x1800d03b8`
- `0x1800d1988`
- `0x1800d54a4`
- `0x1800d5da4`
- `0x1800d639c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5f06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5f06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5f87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d5e32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d5e32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d5f56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d5f56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d5eb0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d5eb0`

## string_xrefs

- `0x1800d5de8`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d5e10`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d5e92`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d5ec8`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RegisterTpmRetryTimerWait(
        EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *this,
        unsigned int a2)
{
  __int64 v2; // r14
  bool *v4; // rdx
  int ShouldUseNewAttestationForLegacyCodePaths; // eax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rcx
  int v9; // eax
  const char *v10; // r9
  unsigned int LastError; // ebx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF
  char *v13; // [rsp+28h] [rbp-40h]
  int *v14; // [rsp+30h] [rbp-38h]
  EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *v15; // [rsp+38h] [rbp-30h]
  char v16; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v18; // [rsp+80h] [rbp+18h] BYREF
  PTP_TIMER ThreadpoolTimer; // [rsp+88h] [rbp+20h] BYREF

  v2 = a2;
  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
      goto LABEL_7;
    LOBYTE(ThreadpoolTimer) = 0;
    ShouldUseNewAttestationForLegacyCodePaths = EnterpriseDeviceManagement::Service::AutoPilot::ShouldUseNewAttestationForLegacyCodePaths(
                                                  (EnterpriseDeviceManagement::Service::AutoPilot *)&ThreadpoolTimer,
                                                  v4);
    if ( ShouldUseNewAttestationForLegacyCodePaths < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x61F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
        (const char *)(unsigned int)ShouldUseNewAttestationForLegacyCodePaths,
        pftDueTime.dwLowDateTime);
    if ( (_BYTE)ThreadpoolTimer )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x622,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
        (const char *)0x8000FFFFLL,
        pftDueTime.dwLowDateTime);
      result = 2147549183LL;
    }
    else
    {
LABEL_7:
      EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
      v13 = (char *)this + 200;
      EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(this, 1);
      LOBYTE(v18) = 1;
      v14 = &v18;
      v15 = this;
      v16 = 1;
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v8, AutopilotManagerRetryTimerUpdated, (unsigned int)v2);
      v9 = EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::ClearTpmRetryTimer(this);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x639,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
          (const char *)(unsigned int)v9,
          pftDueTime.dwLowDateTime);
      ThreadpoolTimer = CreateThreadpoolTimer(
                          EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::TpmRetryTimerCallback,
                          this,
                          0);
      if ( ThreadpoolTimer )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(
          (char *)this + 184,
          &ThreadpoolTimer);
        LOBYTE(v18) = 0;
        pftDueTime = (struct _FILETIME)(-10000 * v2);
        SetThreadpoolTimer(*((PTP_TIMER *)this + 23), &pftDueTime, 0, 0x3E8u);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
        if ( (_BYTE)v18 )
          EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(this, 0);
        if ( this != (EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *)-200LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
        result = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x63D,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
                      v10);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
        if ( (_BYTE)v18 )
          EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(this, 0);
        if ( this != (EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *)-200LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
        result = LastError;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x64E,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800d5da4  mov     [rsp+arg_0], rbx
0x1800d5da9  push    rsi
0x1800d5daa  push    rdi
0x1800d5dab  push    r14
0x1800d5dad  sub     rsp, 50h
0x1800d5db1  mov     r14d, edx
0x1800d5db4  mov     rdi, rcx
0x1800d5db7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1800d5dbe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1800d5dc3  test    al, al
0x1800d5dc5  jz      short loc_1800D5E28
0x1800d5dc7  mov     byte ptr [rsp+68h+arg_18], 0
0x1800d5dcf  lea     rcx, [rsp+68h+arg_18]; this
0x1800d5dd7  call    ?ShouldUseNewAttestationForLegacyCodePaths@AutoPilot@Service@EnterpriseDeviceManagement@@YAJAEA_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::ShouldUseNewAttestationForLegacyCodePaths(bool &)
0x1800d5ddc  mov     rcx, [rsp+68h]; this
0x1800d5de1  test    eax, eax
0x1800d5de3  jns     short loc_1800D5DF9
0x1800d5de5  mov     r9d, eax; char *
0x1800d5de8  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5def  mov     edx, 61Fh; void *
0x1800d5df4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d5df9  cmp     byte ptr [rsp+68h+arg_18], 0
0x1800d5e01  jz      short loc_1800D5E28
0x1800d5e03  mov     rcx, [rsp+68h]; this
0x1800d5e08  mov     ebx, 8000FFFFh
0x1800d5e0d  mov     r9d, ebx; char *
0x1800d5e10  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5e17  mov     edx, 622h; void *
0x1800d5e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5e21  mov     eax, ebx
0x1800d5e23  jmp     loc_1800D5F98
0x1800d5e28  lea     rsi, [rdi+0C8h]
0x1800d5e2f  mov     rcx, rsi; lpCriticalSection
0x1800d5e32  call    cs:__imp_EnterCriticalSection
0x1800d5e38  mov     [rsp+68h+var_40], rsi
0x1800d5e3d  mov     dl, 1; bool
0x1800d5e3f  mov     rcx, rdi; this
0x1800d5e42  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d5e47  mov     byte ptr [rsp+68h+arg_10], 1
0x1800d5e4f  lea     rax, [rsp+68h+arg_10]
0x1800d5e57  mov     [rsp+68h+var_38], rax
0x1800d5e5c  mov     [rsp+68h+var_30], rdi
0x1800d5e61  mov     [rsp+68h+var_28], 1
0x1800d5e66  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800d5e6d  jz      short loc_1800D5E7E
0x1800d5e6f  mov     r8d, r14d
0x1800d5e72  lea     rdx, AutopilotManagerRetryTimerUpdated
0x1800d5e79  call    McTemplateU0q_EventWriteTransfer
0x1800d5e7e  mov     rcx, rdi; this
0x1800d5e81  call    ?ClearTpmRetryTimer@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::ClearTpmRetryTimer(void)
0x1800d5e86  mov     rcx, [rsp+68h]; this
0x1800d5e8b  test    eax, eax
0x1800d5e8d  jns     short loc_1800D5EA3
0x1800d5e8f  mov     r9d, eax; char *
0x1800d5e92  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5e99  mov     edx, 639h; void *
0x1800d5e9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d5ea3  xor     r8d, r8d; pcbe
0x1800d5ea6  mov     rdx, rdi; pv
0x1800d5ea9  lea     rcx, ?TpmRetryTimerCallback@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800d5eb0  call    cs:__imp_CreateThreadpoolTimer
0x1800d5eb6  mov     [rsp+68h+arg_18], rax
0x1800d5ebe  test    rax, rax
0x1800d5ec1  jnz     short loc_1800D5F13
0x1800d5ec3  mov     rcx, [rsp+68h]; this
0x1800d5ec8  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d5ecf  mov     edx, 63Dh; void *
0x1800d5ed4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d5ed9  mov     ebx, eax
0x1800d5edb  lea     rcx, [rsp+68h+arg_18]
0x1800d5ee3  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d5ee8  nop
0x1800d5ee9  cmp     byte ptr [rsp+68h+arg_10], 0
0x1800d5ef1  jz      short loc_1800D5EFE
0x1800d5ef3  xor     edx, edx; bool
0x1800d5ef5  mov     rcx, rdi; this
0x1800d5ef8  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d5efd  nop
0x1800d5efe  test    rsi, rsi
0x1800d5f01  jz      short loc_1800D5F0C
0x1800d5f03  mov     rcx, rsi; lpCriticalSection
0x1800d5f06  call    cs:__imp_LeaveCriticalSection
0x1800d5f0c  mov     eax, ebx
0x1800d5f0e  jmp     loc_1800D5F98
0x1800d5f13  lea     rbx, [rdi+0B8h]
0x1800d5f1a  lea     rdx, [rsp+68h+arg_18]
0x1800d5f22  mov     rcx, rbx
0x1800d5f25  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &&)
0x1800d5f2a  mov     byte ptr [rsp+68h+arg_10], 0
0x1800d5f32  imul    rax, r14, 0FFFFFFFFFFFFD8F0h
0x1800d5f39  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x1800d5f3d  shr     rax, 20h
0x1800d5f41  mov     [rsp+68h+pftDueTime.dwHighDateTime], eax
0x1800d5f45  mov     r9d, 3E8h; msWindowLength
0x1800d5f4b  xor     r8d, r8d; msPeriod
0x1800d5f4e  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800d5f53  mov     rcx, [rbx]; pti
0x1800d5f56  call    cs:__imp_SetThreadpoolTimer
0x1800d5f5c  lea     rcx, [rsp+68h+arg_18]
0x1800d5f64  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d5f69  nop
0x1800d5f6a  cmp     byte ptr [rsp+68h+arg_10], 0
0x1800d5f72  jz      short loc_1800D5F7F
0x1800d5f74  xor     edx, edx; bool
0x1800d5f76  mov     rcx, rdi; this
0x1800d5f79  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d5f7e  nop
0x1800d5f7f  test    rsi, rsi
0x1800d5f82  jz      short loc_1800D5F8D
0x1800d5f84  mov     rcx, rsi; lpCriticalSection
0x1800d5f87  call    cs:__imp_LeaveCriticalSection
0x1800d5f8d  xor     eax, eax
0x1800d5f8f  jmp     short loc_1800D5F98
0x1800d5f91  mov     eax, [rsp+68h+arg_10]
0x1800d5f98  mov     rbx, [rsp+68h+arg_0]
0x1800d5f9d  add     rsp, 50h
0x1800d5fa1  pop     r14
0x1800d5fa3  pop     rdi
0x1800d5fa4  pop     rsi
0x1800d5fa5  retn
```

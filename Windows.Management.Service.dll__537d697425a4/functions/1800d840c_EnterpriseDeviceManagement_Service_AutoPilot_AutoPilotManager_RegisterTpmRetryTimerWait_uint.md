# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RegisterTpmRetryTimerWait(uint)

- ea: `0x1800d840c`
- end: `0x1800d862d`
- name: `?RegisterTpmRetryTimerWait@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJI@Z`
- size: `545`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d5474`
- `0x1800d6920`
- `0x1800d79a8`
- `0x1800d7ee8`

## callees

- `0x180067e34`
- `0x180067e54`
- `0x18006e650`
- `0x180077d0c`
- `0x180080c10`
- `0x180081150`
- `0x1800d2860`
- `0x1800d3e98`
- `0x1800d7ac4`
- `0x1800d840c`
- `0x1800d8a48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d857a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d8607`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d857a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d8607`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d849a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d849a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d85d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d85d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d851e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d851e`

## string_xrefs

- `0x1800d8450`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d8478`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d8500`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`
- `0x1800d853c`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

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
0x1800d840c  mov     [rsp+arg_0], rbx
0x1800d8411  push    rsi
0x1800d8412  push    rdi
0x1800d8413  push    r14
0x1800d8415  sub     rsp, 50h
0x1800d8419  mov     r14d, edx
0x1800d841c  mov     rdi, rcx
0x1800d841f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1800d8426  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1800d842b  test    al, al
0x1800d842d  jz      short loc_1800D8490
0x1800d842f  mov     byte ptr [rsp+68h+arg_18], 0
0x1800d8437  lea     rcx, [rsp+68h+arg_18]; this
0x1800d843f  call    ?ShouldUseNewAttestationForLegacyCodePaths@AutoPilot@Service@EnterpriseDeviceManagement@@YAJAEA_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::ShouldUseNewAttestationForLegacyCodePaths(bool &)
0x1800d8444  mov     rcx, [rsp+68h]; this
0x1800d8449  test    eax, eax
0x1800d844b  jns     short loc_1800D8461
0x1800d844d  mov     r9d, eax; char *
0x1800d8450  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d8457  mov     edx, 61Fh; void *
0x1800d845c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d8461  cmp     byte ptr [rsp+68h+arg_18], 0
0x1800d8469  jz      short loc_1800D8490
0x1800d846b  mov     rcx, [rsp+68h]; this
0x1800d8470  mov     ebx, 8000FFFFh
0x1800d8475  mov     r9d, ebx; char *
0x1800d8478  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d847f  mov     edx, 622h; void *
0x1800d8484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8489  mov     eax, ebx
0x1800d848b  jmp     loc_1800D861E
0x1800d8490  lea     rsi, [rdi+0C8h]
0x1800d8497  mov     rcx, rsi; lpCriticalSection
0x1800d849a  call    cs:__imp_EnterCriticalSection
0x1800d84a1  nop     dword ptr [rax+rax+00h]
0x1800d84a6  mov     [rsp+68h+var_40], rsi
0x1800d84ab  mov     dl, 1; bool
0x1800d84ad  mov     rcx, rdi; this
0x1800d84b0  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d84b5  mov     byte ptr [rsp+68h+arg_10], 1
0x1800d84bd  lea     rax, [rsp+68h+arg_10]
0x1800d84c5  mov     [rsp+68h+var_38], rax
0x1800d84ca  mov     [rsp+68h+var_30], rdi
0x1800d84cf  mov     [rsp+68h+var_28], 1
0x1800d84d4  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800d84db  jz      short loc_1800D84EC
0x1800d84dd  mov     r8d, r14d
0x1800d84e0  lea     rdx, AutopilotManagerRetryTimerUpdated
0x1800d84e7  call    McTemplateU0q_EventWriteTransfer
0x1800d84ec  mov     rcx, rdi; this
0x1800d84ef  call    ?ClearTpmRetryTimer@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::ClearTpmRetryTimer(void)
0x1800d84f4  mov     rcx, [rsp+68h]; this
0x1800d84f9  test    eax, eax
0x1800d84fb  jns     short loc_1800D8511
0x1800d84fd  mov     r9d, eax; char *
0x1800d8500  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d8507  mov     edx, 639h; void *
0x1800d850c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d8511  xor     r8d, r8d; pcbe
0x1800d8514  mov     rdx, rdi; pv
0x1800d8517  lea     rcx, ?TpmRetryTimerCallback@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800d851e  call    cs:__imp_CreateThreadpoolTimer
0x1800d8525  nop     dword ptr [rax+rax+00h]
0x1800d852a  mov     [rsp+68h+arg_18], rax
0x1800d8532  test    rax, rax
0x1800d8535  jnz     short loc_1800D858D
0x1800d8537  mov     rcx, [rsp+68h]; this
0x1800d853c  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d8543  mov     edx, 63Dh; void *
0x1800d8548  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d854d  mov     ebx, eax
0x1800d854f  lea     rcx, [rsp+68h+arg_18]
0x1800d8557  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d855c  nop
0x1800d855d  cmp     byte ptr [rsp+68h+arg_10], 0
0x1800d8565  jz      short loc_1800D8572
0x1800d8567  xor     edx, edx; bool
0x1800d8569  mov     rcx, rdi; this
0x1800d856c  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d8571  nop
0x1800d8572  test    rsi, rsi
0x1800d8575  jz      short loc_1800D8586
0x1800d8577  mov     rcx, rsi; lpCriticalSection
0x1800d857a  call    cs:__imp_LeaveCriticalSection
0x1800d8581  nop     dword ptr [rax+rax+00h]
0x1800d8586  mov     eax, ebx
0x1800d8588  jmp     loc_1800D861E
0x1800d858d  lea     rbx, [rdi+0B8h]
0x1800d8594  lea     rdx, [rsp+68h+arg_18]
0x1800d859c  mov     rcx, rbx
0x1800d859f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &&)
0x1800d85a4  mov     byte ptr [rsp+68h+arg_10], 0
0x1800d85ac  imul    rax, r14, 0FFFFFFFFFFFFD8F0h
0x1800d85b3  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x1800d85b7  shr     rax, 20h
0x1800d85bb  mov     [rsp+68h+pftDueTime.dwHighDateTime], eax
0x1800d85bf  mov     r9d, 3E8h; msWindowLength
0x1800d85c5  xor     r8d, r8d; msPeriod
0x1800d85c8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800d85cd  mov     rcx, [rbx]; pti
0x1800d85d0  call    cs:__imp_SetThreadpoolTimer
0x1800d85d7  nop     dword ptr [rax+rax+00h]
0x1800d85dc  lea     rcx, [rsp+68h+arg_18]
0x1800d85e4  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d85e9  nop
0x1800d85ea  cmp     byte ptr [rsp+68h+arg_10], 0
0x1800d85f2  jz      short loc_1800D85FF
0x1800d85f4  xor     edx, edx; bool
0x1800d85f6  mov     rcx, rdi; this
0x1800d85f9  call    ?RefCountHost@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJ_N@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RefCountHost(bool)
0x1800d85fe  nop
0x1800d85ff  test    rsi, rsi
0x1800d8602  jz      short loc_1800D8613
0x1800d8604  mov     rcx, rsi; lpCriticalSection
0x1800d8607  call    cs:__imp_LeaveCriticalSection
0x1800d860e  nop     dword ptr [rax+rax+00h]
0x1800d8613  xor     eax, eax
0x1800d8615  jmp     short loc_1800D861E
0x1800d8617  mov     eax, [rsp+68h+arg_10]
0x1800d861e  mov     rbx, [rsp+68h+arg_0]
0x1800d8623  add     rsp, 50h
0x1800d8627  pop     r14
0x1800d8629  pop     rdi
0x1800d862a  pop     rsi
0x1800d862b  retn
```

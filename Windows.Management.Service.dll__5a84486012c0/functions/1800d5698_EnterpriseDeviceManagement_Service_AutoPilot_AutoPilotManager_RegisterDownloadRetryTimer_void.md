# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RegisterDownloadRetryTimer(void)

- ea: `0x1800d5698`
- end: `0x1800d57c9`
- name: `?RegisterDownloadRetryTimer@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ`
- size: `305`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d0e84`

## callees

- `0x180067a34`
- `0x18006e0e8`
- `0x180080708`
- `0x1800d03b8`
- `0x1800d2b98`
- `0x1800d5698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d56dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d574d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d57aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d56dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d574d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d57aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d56b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d56b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d5792`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d5792`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d5713`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d5713`

## string_xrefs

- `0x1800d5728`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RegisterDownloadRetryTimer(
        char *pv)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v3; // rcx
  unsigned int v4; // esi
  unsigned int v6; // esi
  const char *v7; // r9
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PTP_TIMER RetryConfigValues; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  ++*((_DWORD *)pv + 45);
  RetryConfigValues = (PTP_TIMER)EnterpriseDeviceManagement::Service::AutoPilot::GetRetryConfigValues();
  v4 = *((_DWORD *)pv + 45);
  if ( v4 <= (unsigned int)RetryConfigValues )
  {
    v6 = HIDWORD(RetryConfigValues) * v4;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v3, AutopilotManagerDownloadRetryTimerUpdated, v6);
    RetryConfigValues = CreateThreadpoolTimer(
                          EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::DownloadRetryTimerCallback,
                          pv,
                          0);
    if ( RetryConfigValues )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(
        pv + 192,
        &RetryConfigValues);
      pftDueTime = (struct _FILETIME)(-10000LL * v6);
      SetThreadpoolTimer(*((PTP_TIMER *)pv + 24), &pftDueTime, 0, 0x3E8u);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&RetryConfigValues);
      if ( v2 )
        LeaveCriticalSection(v2);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6C3,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\autopilotmanager.cpp",
                    v7);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&RetryConfigValues);
      if ( v2 )
        LeaveCriticalSection(v2);
      return LastError;
    }
  }
  else
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x1800d5698  mov     [rsp+arg_10], rbx
0x1800d569d  mov     [rsp+arg_18], rsi
0x1800d56a2  push    rdi
0x1800d56a3  sub     rsp, 20h
0x1800d56a7  mov     rbx, rcx
0x1800d56aa  lea     rdi, [rcx+0C8h]
0x1800d56b1  mov     rcx, rdi; lpCriticalSection
0x1800d56b4  call    cs:__imp_EnterCriticalSection
0x1800d56ba  inc     dword ptr [rbx+0B4h]
0x1800d56c0  call    ?GetRetryConfigValues@AutoPilot@Service@EnterpriseDeviceManagement@@YA?AURetryConfigValues@123@XZ; EnterpriseDeviceManagement::Service::AutoPilot::GetRetryConfigValues(void)
0x1800d56c5  mov     [rsp+28h+arg_0], rax
0x1800d56ca  mov     esi, [rbx+0B4h]
0x1800d56d0  cmp     esi, eax
0x1800d56d2  jbe     short loc_1800D56E9
0x1800d56d4  test    rdi, rdi
0x1800d56d7  jz      short loc_1800D56E2
0x1800d56d9  mov     rcx, rdi; lpCriticalSection
0x1800d56dc  call    cs:__imp_LeaveCriticalSection
0x1800d56e2  xor     eax, eax
0x1800d56e4  jmp     loc_1800D57B8
0x1800d56e9  imul    esi, dword ptr [rsp+28h+arg_0+4]
0x1800d56ee  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800d56f5  jz      short loc_1800D5706
0x1800d56f7  mov     r8d, esi
0x1800d56fa  lea     rdx, AutopilotManagerDownloadRetryTimerUpdated
0x1800d5701  call    McTemplateU0q_EventWriteTransfer
0x1800d5706  xor     r8d, r8d; pcbe
0x1800d5709  mov     rdx, rbx; pv
0x1800d570c  lea     rcx, ?DownloadRetryTimerCallback@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800d5713  call    cs:__imp_CreateThreadpoolTimer
0x1800d5719  mov     [rsp+28h+arg_0], rax
0x1800d571e  test    rax, rax
0x1800d5721  jnz     short loc_1800D5757
0x1800d5723  mov     rcx, [rsp+28h]; this
0x1800d5728  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d572f  mov     edx, 6C3h; void *
0x1800d5734  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d5739  mov     ebx, eax
0x1800d573b  lea     rcx, [rsp+28h+arg_0]
0x1800d5740  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d5745  test    rdi, rdi
0x1800d5748  jz      short loc_1800D5753
0x1800d574a  mov     rcx, rdi; lpCriticalSection
0x1800d574d  call    cs:__imp_LeaveCriticalSection
0x1800d5753  mov     eax, ebx
0x1800d5755  jmp     short loc_1800D57B8
0x1800d5757  lea     rdx, [rsp+28h+arg_0]
0x1800d575c  lea     rcx, [rbx+0C0h]
0x1800d5763  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &&)
0x1800d5768  mov     eax, esi
0x1800d576a  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800d5771  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800d5775  shr     rax, 20h
0x1800d5779  mov     [rsp+28h+pftDueTime.dwHighDateTime], eax
0x1800d577d  mov     r9d, 3E8h; msWindowLength
0x1800d5783  xor     r8d, r8d; msPeriod
0x1800d5786  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800d578b  mov     rcx, [rbx+0C0h]; pti
0x1800d5792  call    cs:__imp_SetThreadpoolTimer
0x1800d5798  lea     rcx, [rsp+28h+arg_0]
0x1800d579d  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d57a2  test    rdi, rdi
0x1800d57a5  jz      short loc_1800D57B0
0x1800d57a7  mov     rcx, rdi; lpCriticalSection
0x1800d57aa  call    cs:__imp_LeaveCriticalSection
0x1800d57b0  xor     eax, eax
0x1800d57b2  jmp     short loc_1800D57B8
0x1800d57b4  mov     eax, dword ptr [rsp+28h+arg_0]
0x1800d57b8  mov     rbx, [rsp+28h+arg_10]
0x1800d57bd  mov     rsi, [rsp+28h+arg_18]
0x1800d57c2  add     rsp, 20h
0x1800d57c6  pop     rdi
0x1800d57c7  retn
```

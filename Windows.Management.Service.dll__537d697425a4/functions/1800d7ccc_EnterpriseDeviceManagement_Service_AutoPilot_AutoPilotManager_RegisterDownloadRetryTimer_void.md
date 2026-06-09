# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager::RegisterDownloadRetryTimer(void)

- ea: `0x1800d7ccc`
- end: `0x1800d7e21`
- name: `?RegisterDownloadRetryTimer@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@AEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d3378`

## callees

- `0x180067e34`
- `0x18006e650`
- `0x180081150`
- `0x1800d2860`
- `0x1800d5158`
- `0x1800d7ccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7d16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7d93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7dfc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7d16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7d93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7ce8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7ce8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d7dde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d7dde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d7d53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d7d53`

## string_xrefs

- `0x1800d7d6e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\autopilotmanager.cpp`

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
0x1800d7ccc  mov     [rsp+arg_10], rbx
0x1800d7cd1  mov     [rsp+arg_18], rsi
0x1800d7cd6  push    rdi
0x1800d7cd7  sub     rsp, 20h
0x1800d7cdb  mov     rbx, rcx
0x1800d7cde  lea     rdi, [rcx+0C8h]
0x1800d7ce5  mov     rcx, rdi; lpCriticalSection
0x1800d7ce8  call    cs:__imp_EnterCriticalSection
0x1800d7cef  nop     dword ptr [rax+rax+00h]
0x1800d7cf4  inc     dword ptr [rbx+0B4h]
0x1800d7cfa  call    ?GetRetryConfigValues@AutoPilot@Service@EnterpriseDeviceManagement@@YA?AURetryConfigValues@123@XZ; EnterpriseDeviceManagement::Service::AutoPilot::GetRetryConfigValues(void)
0x1800d7cff  mov     [rsp+28h+arg_0], rax
0x1800d7d04  mov     esi, [rbx+0B4h]
0x1800d7d0a  cmp     esi, eax
0x1800d7d0c  jbe     short loc_1800D7D29
0x1800d7d0e  test    rdi, rdi
0x1800d7d11  jz      short loc_1800D7D22
0x1800d7d13  mov     rcx, rdi; lpCriticalSection
0x1800d7d16  call    cs:__imp_LeaveCriticalSection
0x1800d7d1d  nop     dword ptr [rax+rax+00h]
0x1800d7d22  xor     eax, eax
0x1800d7d24  jmp     loc_1800D7E10
0x1800d7d29  imul    esi, dword ptr [rsp+28h+arg_0+4]
0x1800d7d2e  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800d7d35  jz      short loc_1800D7D46
0x1800d7d37  mov     r8d, esi
0x1800d7d3a  lea     rdx, AutopilotManagerDownloadRetryTimerUpdated
0x1800d7d41  call    McTemplateU0q_EventWriteTransfer
0x1800d7d46  xor     r8d, r8d; pcbe
0x1800d7d49  mov     rdx, rbx; pv
0x1800d7d4c  lea     rcx, ?DownloadRetryTimerCallback@AutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800d7d53  call    cs:__imp_CreateThreadpoolTimer
0x1800d7d5a  nop     dword ptr [rax+rax+00h]
0x1800d7d5f  mov     [rsp+28h+arg_0], rax
0x1800d7d64  test    rax, rax
0x1800d7d67  jnz     short loc_1800D7DA3
0x1800d7d69  mov     rcx, [rsp+28h]; this
0x1800d7d6e  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d7d75  mov     edx, 6C3h; void *
0x1800d7d7a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d7d7f  mov     ebx, eax
0x1800d7d81  lea     rcx, [rsp+28h+arg_0]
0x1800d7d86  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d7d8b  test    rdi, rdi
0x1800d7d8e  jz      short loc_1800D7D9F
0x1800d7d90  mov     rcx, rdi; lpCriticalSection
0x1800d7d93  call    cs:__imp_LeaveCriticalSection
0x1800d7d9a  nop     dword ptr [rax+rax+00h]
0x1800d7d9f  mov     eax, ebx
0x1800d7da1  jmp     short loc_1800D7E10
0x1800d7da3  lea     rdx, [rsp+28h+arg_0]
0x1800d7da8  lea     rcx, [rbx+0C0h]
0x1800d7daf  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &&)
0x1800d7db4  mov     eax, esi
0x1800d7db6  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800d7dbd  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800d7dc1  shr     rax, 20h
0x1800d7dc5  mov     [rsp+28h+pftDueTime.dwHighDateTime], eax
0x1800d7dc9  mov     r9d, 3E8h; msWindowLength
0x1800d7dcf  xor     r8d, r8d; msPeriod
0x1800d7dd2  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800d7dd7  mov     rcx, [rbx+0C0h]; pti
0x1800d7dde  call    cs:__imp_SetThreadpoolTimer
0x1800d7de5  nop     dword ptr [rax+rax+00h]
0x1800d7dea  lea     rcx, [rsp+28h+arg_0]
0x1800d7def  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800d7df4  test    rdi, rdi
0x1800d7df7  jz      short loc_1800D7E08
0x1800d7df9  mov     rcx, rdi; lpCriticalSection
0x1800d7dfc  call    cs:__imp_LeaveCriticalSection
0x1800d7e03  nop     dword ptr [rax+rax+00h]
0x1800d7e08  xor     eax, eax
0x1800d7e0a  jmp     short loc_1800D7E10
0x1800d7e0c  mov     eax, dword ptr [rsp+28h+arg_0]
0x1800d7e10  mov     rbx, [rsp+28h+arg_10]
0x1800d7e15  mov     rsi, [rsp+28h+arg_18]
0x1800d7e1a  add     rsp, 20h
0x1800d7e1e  pop     rdi
0x1800d7e1f  retn
```

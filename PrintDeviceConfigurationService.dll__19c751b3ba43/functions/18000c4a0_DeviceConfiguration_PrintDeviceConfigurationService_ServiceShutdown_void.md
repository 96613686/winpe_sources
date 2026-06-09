# DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown(void)

- ea: `0x18000c4a0`
- end: `0x18000c64f`
- name: `?_ServiceShutdown@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAXXZ`
- size: `431`
- prototype: `void __fastcall(DeviceConfiguration::PrintDeviceConfigurationService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c6c0`

## callees

- `0x180004e44`
- `0x18000aeac`
- `0x18000af54`
- `0x18000c34c`
- `0x18000c384`
- `0x18000c4a0`
- `0x18000dcfc`
- `0x18000ddb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c4ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c529`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c4ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c529`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c580`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c580`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c573`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c573`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000c55d`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000c55d`

## string_xrefs

- `0x18000c4ad`: `Shutting down the Print Device Configuration Service...`
- `0x18000c4b4`: `DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown`
- `0x18000c636`: `DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown`
- `0x18000c62f`: `Print Device Configuration Service is shut down!`

## pseudocode

```c
void __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown(
        DeviceConfiguration::PrintDeviceConfigurationService *this)
{
  signed int v2; // eax
  __int64 v3; // r8
  __int64 v4; // rsi
  _BYTE *v5; // rcx
  struct _TP_TIMER *v6; // rcx
  signed int v7; // eax
  __int64 v8; // r8
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp+8h] BYREF

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown",
    L"Shutting down the Print Device Configuration Service...");
  v2 = DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus((SERVICE_STATUS_HANDLE *)this, 3u);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x6E, v3, (const char *)(unsigned int)v2);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  *((_BYTE *)this + 36) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
  v4 = *((_QWORD *)this + 19);
  if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load(v4 + 88) )
  {
    *v5 = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
    v13 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
      v4 + 16,
      0);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
      v4 + 40,
      0);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  if ( v6 && IsThreadpoolTimerSet(v6) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 3), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
  }
  *(_BYTE *)(*((_QWORD *)this + 15) + 16LL) = 1;
  **((_BYTE **)this + 17) = 1;
  v7 = DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus((SERVICE_STATUS_HANDLE *)this, 1u);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x88, v8, (const char *)(unsigned int)v7);
  *((_QWORD *)this + 15) = 0;
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 16);
  *((_QWORD *)this + 16) = 0;
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  *((_QWORD *)this + 17) = 0;
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 18) = 0;
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  *((_QWORD *)this + 19) = 0;
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 20);
  *((_QWORD *)this + 20) = 0;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown",
    L"Print Device Configuration Service is shut down!");
}

```

## disassembly

```asm
0x18000c4a0  push    rbx
0x18000c4a2  push    rsi
0x18000c4a3  push    rdi
0x18000c4a4  push    r15
0x18000c4a6  sub     rsp, 28h
0x18000c4aa  mov     rdi, rcx
0x18000c4ad  lea     rdx, aShuttingDownTh; "Shutting down the Print Device Configur"...
0x18000c4b4  lea     rcx, aDeviceconfigur_11; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c4bb  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c4c0  mov     edx, 3; unsigned int
0x18000c4c5  mov     rcx, rdi; this
0x18000c4c8  call    ?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z; DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)
0x18000c4cd  mov     rcx, [rsp+48h]; this
0x18000c4d2  test    eax, eax
0x18000c4d4  jns     short loc_18000C4E3
0x18000c4d6  mov     r9d, eax; char *
0x18000c4d9  mov     edx, 6Eh ; 'n'; void *
0x18000c4de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c4e3  lea     rbx, [rdi+28h]
0x18000c4e7  mov     rcx, rbx; lpCriticalSection
0x18000c4ea  call    cs:__imp_EnterCriticalSection
0x18000c4f0  mov     [rsp+48h+arg_0], rbx
0x18000c4f5  mov     r15d, 1
0x18000c4fb  mov     [rdi+24h], r15b
0x18000c4ff  lea     rcx, [rsp+48h+arg_0]
0x18000c504  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000c509  mov     rsi, [rdi+98h]
0x18000c510  lea     rcx, [rsi+58h]
0x18000c514  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18000c519  test    al, al
0x18000c51b  jnz     short loc_18000C554
0x18000c51d  mov     eax, r15d
0x18000c520  xchg    al, [rcx]
0x18000c522  lea     rbx, [rsi+30h]
0x18000c526  mov     rcx, rbx; lpCriticalSection
0x18000c529  call    cs:__imp_EnterCriticalSection
0x18000c52f  mov     [rsp+48h+arg_0], rbx
0x18000c534  lea     rcx, [rsi+10h]
0x18000c538  xor     edx, edx
0x18000c53a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x18000c53f  lea     rcx, [rsi+28h]
0x18000c543  xor     edx, edx
0x18000c545  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x18000c54a  lea     rcx, [rsp+48h+arg_0]
0x18000c54f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000c554  mov     rcx, [rdi+18h]; pti
0x18000c558  test    rcx, rcx
0x18000c55b  jz      short loc_18000C586
0x18000c55d  call    cs:__imp_IsThreadpoolTimerSet
0x18000c563  test    eax, eax
0x18000c565  jz      short loc_18000C586
0x18000c567  xor     r9d, r9d; msWindowLength
0x18000c56a  xor     r8d, r8d; msPeriod
0x18000c56d  xor     edx, edx; pftDueTime
0x18000c56f  mov     rcx, [rdi+18h]; pti
0x18000c573  call    cs:__imp_SetThreadpoolTimer
0x18000c579  mov     edx, r15d; fCancelPendingCallbacks
0x18000c57c  mov     rcx, [rdi+18h]; pti
0x18000c580  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c586  mov     rcx, [rdi+78h]
0x18000c58a  mov     eax, r15d
0x18000c58d  xchg    al, [rcx+10h]
0x18000c590  mov     ecx, r15d
0x18000c593  mov     rax, [rdi+88h]
0x18000c59a  xchg    cl, [rax]
0x18000c59c  mov     edx, r15d; unsigned int
0x18000c59f  mov     rcx, rdi; this
0x18000c5a2  call    ?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z; DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)
0x18000c5a7  mov     rcx, [rsp+48h]; this
0x18000c5ac  test    eax, eax
0x18000c5ae  jns     short loc_18000C5BD
0x18000c5b0  mov     r9d, eax; char *
0x18000c5b3  mov     edx, 88h; void *
0x18000c5b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c5bd  mov     qword ptr [rdi+78h], 0
0x18000c5c5  mov     rcx, [rdi+80h]; this
0x18000c5cc  mov     qword ptr [rdi+80h], 0
0x18000c5d7  test    rcx, rcx
0x18000c5da  jz      short loc_18000C5E1
0x18000c5dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c5e1  mov     qword ptr [rdi+88h], 0
0x18000c5ec  mov     rcx, [rdi+90h]; this
0x18000c5f3  mov     qword ptr [rdi+90h], 0
0x18000c5fe  test    rcx, rcx
0x18000c601  jz      short loc_18000C608
0x18000c603  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c608  mov     qword ptr [rdi+98h], 0
0x18000c613  mov     rcx, [rdi+0A0h]; this
0x18000c61a  mov     qword ptr [rdi+0A0h], 0
0x18000c625  test    rcx, rcx
0x18000c628  jz      short loc_18000C62F
0x18000c62a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c62f  lea     rdx, aPrintDeviceCon_0; "Print Device Configuration Service is s"...
0x18000c636  lea     rcx, aDeviceconfigur_11; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000c63d  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000c642  nop
0x18000c643  jmp     short $+2
0x18000c645  add     rsp, 28h
0x18000c649  pop     r15
0x18000c64b  pop     rdi
0x18000c64c  pop     rsi
0x18000c64d  pop     rbx
0x18000c64e  retn
```

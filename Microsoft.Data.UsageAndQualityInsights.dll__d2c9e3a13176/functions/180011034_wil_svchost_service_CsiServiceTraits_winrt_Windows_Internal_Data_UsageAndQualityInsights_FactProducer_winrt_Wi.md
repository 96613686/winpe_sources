# wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::stop(ulong)

- ea: `0x180011034`
- end: `0x180011125`
- name: `?stop@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXK@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d4c0`
- `0x180102975`

## callees

- `0x180003870`
- `0x18000c268`
- `0x18000ef68`
- `0x180010898`
- `0x180011034`
- `0x1800113b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011082`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001106b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011099`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001106b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001108d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001108d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180011063`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180011063`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800110ab`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800110ab`

## string_xrefs

- `0x180011113`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800110bd`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::stop(
        _QWORD *a1,
        DWORD a2)
{
  void *v4; // rsi
  DWORD LastError; // ebx
  void *v6; // rbx
  DWORD v7; // esi
  const char *v8; // r9
  int v9; // eax
  _QWORD *v10; // rbx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
    (__int64)a1,
    3u,
    a2);
  v4 = (void *)a1[1];
  if ( v4 )
  {
    LastError = GetLastError();
    UnregisterWait(v4);
    SetLastError(LastError);
  }
  a1[1] = 0;
  v6 = (void *)a1[2];
  if ( v6 )
  {
    v7 = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(v7);
  }
  a1[2] = 0;
  v9 = CoRegisterServerShutdownDelay(0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h",
      (const char *)(unsigned int)v9,
      v12);
  v10 = (_QWORD *)a1[3];
  a1[3] = 0;
  if ( v10 )
  {
    wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::~svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>(v10);
    operator delete(v10, 0x18u);
  }
  return wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
           (__int64)a1,
           1u,
           a2);
}

```

## disassembly

```asm
0x180011034  push    rbx
0x180011036  push    rbp
0x180011037  push    rsi
0x180011038  push    rdi
0x180011039  sub     rsp, 28h
0x18001103d  mov     ebp, edx
0x18001103f  mov     rdi, rcx
0x180011042  mov     r8d, edx
0x180011045  mov     edx, 3
0x18001104a  call    ?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)
0x18001104f  mov     rsi, [rdi+8]
0x180011053  test    rsi, rsi
0x180011056  jz      short loc_180011071
0x180011058  call    cs:__imp_GetLastError
0x18001105e  mov     ebx, eax
0x180011060  mov     rcx, rsi; WaitHandle
0x180011063  call    cs:__imp_UnregisterWait
0x180011069  mov     ecx, ebx; dwErrCode
0x18001106b  call    cs:__imp_SetLastError
0x180011071  mov     qword ptr [rdi+8], 0
0x180011079  mov     rbx, [rdi+10h]
0x18001107d  test    rbx, rbx
0x180011080  jz      short loc_18001109F
0x180011082  call    cs:__imp_GetLastError
0x180011088  mov     esi, eax
0x18001108a  mov     rcx, rbx; hObject
0x18001108d  call    cs:__imp_CloseHandle
0x180011093  test    eax, eax
0x180011095  jz      short loc_18001110E
0x180011097  mov     ecx, esi; dwErrCode
0x180011099  call    cs:__imp_SetLastError
0x18001109f  mov     qword ptr [rdi+10h], 0
0x1800110a7  xor     edx, edx
0x1800110a9  xor     ecx, ecx
0x1800110ab  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800110b1  test    eax, eax
0x1800110b3  jns     short loc_1800110CE
0x1800110b5  mov     rcx, [rsp+48h]; this
0x1800110ba  mov     r9d, eax; char *
0x1800110bd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x1800110c4  mov     edx, 1EEh; void *
0x1800110c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800110ce  mov     rbx, [rdi+18h]
0x1800110d2  mov     qword ptr [rdi+18h], 0
0x1800110da  test    rbx, rbx
0x1800110dd  jz      short loc_1800110F4
0x1800110df  mov     rcx, rbx
0x1800110e2  call    ??1?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::~svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>(void)
0x1800110e7  mov     edx, 18h; unsigned __int64
0x1800110ec  mov     rcx, rbx; void *
0x1800110ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800110f4  mov     r8d, ebp
0x1800110f7  mov     edx, 1
0x1800110fc  mov     rcx, rdi
0x1800110ff  call    ?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)
0x180011104  nop
0x180011105  add     rsp, 28h
0x180011109  pop     rdi
0x18001110a  pop     rsi
0x18001110b  pop     rbp
0x18001110c  pop     rbx
0x18001110d  retn
0x18001110e  mov     rcx, [rsp+48h]; this
0x180011113  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001111a  mov     edx, 0A0Bh; void *
0x18001111f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

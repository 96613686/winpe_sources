# wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(ulong,ulong)

- ea: `0x1800113b8`
- end: `0x18001145a`
- name: `?update_status@?$svchost_service@UCsiServiceTraits@@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@34567@UUQIMaintenanceTaskRun@Private@34567@UTestAPI@Private@34567@UTestConfigurationRegistration@Private@34567@@wil@@AEAAXKK@Z`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000d360`
- `0x180010d9c`
- `0x180011034`

## callees

- `0x1800033d0`
- `0x180011358`
- `0x1800113b8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011434`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011434`

## string_xrefs

- `0x180011416`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<CsiServiceTraits,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::update_status(
        __int64 a1,
        DWORD a2,
        DWORD a3)
{
  SERVICE_STATUS_HANDLE v3; // rcx
  BOOL result; // eax
  const struct winrt::impl::slim_source_location *v5; // rdx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  const char *v7; // [rsp+28h] [rbp-38h]
  __int64 v8; // [rsp+30h] [rbp-30h]
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ServiceStatus.dwServiceType = 96;
  ServiceStatus.dwCurrentState = a2;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwWin32ExitCode = a3;
  if ( a2 == 4 || a2 == 1 )
  {
    ServiceStatus.dwControlsAccepted = 1025;
  }
  else
  {
    ServiceStatus.dwWaitHint = 5000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  }
  v3 = *(SERVICE_STATUS_HANDLE *)(a1 + 32);
  v7 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v6 = 422;
  v8 = 0;
  result = SetServiceStatus(v3, &ServiceStatus);
  if ( !result )
    winrt::throw_last_error((winrt *)&v6, v5);
  return result;
}

```

## disassembly

```asm
0x1800113b8  push    rbp
0x1800113ba  mov     rbp, rsp
0x1800113bd  sub     rsp, 60h
0x1800113c1  mov     rax, cs:__security_cookie
0x1800113c8  xor     rax, rsp
0x1800113cb  mov     [rbp+var_8], rax
0x1800113cf  xor     eax, eax
0x1800113d1  mov     [rbp+ServiceStatus.dwServiceType], 60h ; '`'
0x1800113d8  mov     [rbp+ServiceStatus.dwCurrentState], edx
0x1800113db  xorps   xmm0, xmm0
0x1800113de  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x1800113e1  movups  xmmword ptr [rbp+ServiceStatus.dwControlsAccepted], xmm0
0x1800113e5  mov     [rbp+ServiceStatus.dwWin32ExitCode], r8d
0x1800113e9  cmp     edx, 4
0x1800113ec  jz      short loc_18001140B
0x1800113ee  cmp     edx, 1
0x1800113f1  jz      short loc_18001140B
0x1800113f3  mov     eax, 1
0x1800113f8  lock xadd [rcx+28h], eax
0x1800113fd  inc     eax
0x1800113ff  mov     [rbp+ServiceStatus.dwWaitHint], 1388h
0x180011406  mov     [rbp+ServiceStatus.dwCheckPoint], eax
0x180011409  jmp     short loc_180011412
0x18001140b  mov     [rbp+ServiceStatus.dwControlsAccepted], 401h
0x180011412  mov     rcx, [rcx+20h]; hServiceStatus
0x180011416  lea     rax, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x18001141d  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180011421  mov     [rbp+var_38], rax
0x180011425  mov     [rbp+var_40], 1A6h
0x18001142c  mov     [rbp+var_30], 0
0x180011434  call    cs:__imp_SetServiceStatus
0x18001143a  test    eax, eax
0x18001143c  jz      short loc_180011450
0x18001143e  mov     rcx, [rbp+var_8]
0x180011442  xor     rcx, rsp; StackCookie
0x180011445  call    __security_check_cookie
0x18001144a  add     rsp, 60h
0x18001144e  pop     rbp
0x18001144f  retn
0x180011450  lea     rcx, [rbp+var_40]; this
0x180011454  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```

# _StopIsoEnvBrokerSvcAsync(void)

- ea: `0x180062934`
- end: `0x1800629a8`
- name: `?_StopIsoEnvBrokerSvcAsync@@YAXXZ`
- size: `116`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000da40`
- `0x18005fbc4`
- `0x180062b20`

## callees

- `0x18000bd98`
- `0x180011e18`
- `0x180062914`
- `0x180062934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180062982`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180062982`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180062962`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180062962`

## string_xrefs

- `0x180062996`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void _StopIsoEnvBrokerSvcAsync(void)
{
  unsigned int v0; // r8d
  const char *v1; // r9
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Log(4u, L"Stopping...");
  *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
  if ( !SetServiceStatus(g_serviceState, &ServiceStatus) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xA4, v0, v1);
  if ( !SetEvent(g_shutdownEvent) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
}

```

## disassembly

```asm
0x180062934  sub     rsp, 28h
0x180062938  lea     rdx, aStopping; "Stopping..."
0x18006293f  mov     ecx, 4; unsigned __int8
0x180062944  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180062949  mov     rcx, cs:?g_serviceState@@3UServiceState@@A; hServiceStatus
0x180062950  lea     rdx, ServiceStatus; lpServiceStatus
0x180062957  mov     qword ptr cs:ServiceStatus.dwCurrentState, 3
0x180062962  call    cs:__imp_SetServiceStatus
0x180062968  test    eax, eax
0x18006296a  jnz     short loc_18006297B
0x18006296c  mov     rcx, [rsp+28h]; this
0x180062971  mov     edx, 0A4h; void *
0x180062976  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006297b  mov     rcx, cs:?g_shutdownEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x180062982  call    cs:__imp_SetEvent
0x180062988  test    eax, eax
0x18006298a  jz      short loc_180062991
0x18006298c  add     rsp, 28h
0x180062990  retn
0x180062991  mov     rcx, [rsp+28h]; this
0x180062996  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006299d  mov     edx, 0A01h; void *
0x1800629a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# TiControlHandler(ulong,ulong,void *,void *)

- ea: `0x1400091f0`
- end: `0x14000932d`
- name: `?TiControlHandler@@YAKKKPEAX0@Z`
- size: `317`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400091f0`
- `0x14000a7cc`
- `0x140016948`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140009307`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140009307`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x1400092ef`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x1400092ef`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140009291`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400092e2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140009291`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1400092e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000926c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000926c`

## string_xrefs

- `0x14000924c`: `TI: the computer is suspending`

## pseudocode

```c
__int64 __fastcall TiControlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v5; // ebx

  v5 = 0;
  if ( (unsigned int)TiTryChangeState(2) )
  {
    switch ( dwControl )
    {
      case 1u:
        goto LABEL_13;
      case 4u:
        if ( vhTiService )
        {
          SetServiceStatus(vhTiService, &vTiStatus);
          goto LABEL_19;
        }
LABEL_18:
        MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_19;
      case 5u:
LABEL_13:
        *(_QWORD *)&vTiStatus.dwCurrentState = 3;
        vTiStatus.dwWin32ExitCode = 0;
        vTiStatus.dwWaitHint = 30000;
        vTiStatus.dwCheckPoint = 1;
        vbServiceShuttingDown = 1;
        if ( vhTiService )
          SetServiceStatus(vhTiService, &vTiStatus);
        else
          MicrosoftTelemetryAssertTriggeredNoArgs();
        CoSuspendClassObjects();
        vControlCommand = dwControl;
        if ( vhShutdownEvent )
        {
          SetEvent(vhShutdownEvent);
          goto LABEL_19;
        }
        goto LABEL_18;
    }
    if ( dwControl != 13 )
    {
      if ( dwControl != 15 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v5 = 120;
        goto LABEL_19;
      }
      goto LABEL_13;
    }
    if ( dwEventType == 4 )
    {
      CBSWdsLogLight(0x4000000u, 0, 0, "TI: the computer is suspending");
      vbAboutToSleep = 1;
      _InterlockedExchange64((volatile __int64 *)&vullLatestSleepTickCount, GetTickCount64());
    }
  }
LABEL_19:
  TiTryChangeState(0);
  return v5;
}

```

## disassembly

```asm
0x1400091f0  mov     [rsp+arg_0], rbx
0x1400091f5  mov     [rsp+arg_8], rsi
0x1400091fa  push    rdi
0x1400091fb  sub     rsp, 20h
0x1400091ff  mov     edi, ecx
0x140009201  xor     ebx, ebx
0x140009203  mov     esi, edx
0x140009205  lea     ecx, [rbx+2]; int
0x140009208  call    ?TiTryChangeState@@YAHJ@Z; TiTryChangeState(long)
0x14000920d  test    eax, eax
0x14000920f  jz      loc_140009314
0x140009215  mov     eax, edi
0x140009217  sub     eax, 1
0x14000921a  jz      loc_1400092A0
0x140009220  sub     eax, 3
0x140009223  jz      short loc_14000927E
0x140009225  sub     eax, 1
0x140009228  jz      short loc_1400092A0
0x14000922a  sub     eax, 8
0x14000922d  jz      short loc_140009243
0x14000922f  cmp     eax, 2
0x140009232  jz      short loc_1400092A0
0x140009234  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140009239  mov     ebx, 78h ; 'x'
0x14000923e  jmp     loc_140009314
0x140009243  cmp     esi, 4
0x140009246  jnz     loc_140009314
0x14000924c  lea     r9, aTiTheComputerI; "TI: the computer is suspending"
0x140009253  xor     r8d, r8d
0x140009256  xor     edx, edx
0x140009258  mov     ecx, 4000000h
0x14000925d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009262  mov     cs:?vbAboutToSleep@@3HA, 1; int vbAboutToSleep
0x14000926c  call    cs:__imp_GetTickCount64
0x140009272  xchg    rax, cs:?vullLatestSleepTickCount@@3_KA; unsigned __int64 vullLatestSleepTickCount
0x140009279  jmp     loc_140009314
0x14000927e  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x140009285  test    rcx, rcx
0x140009288  jz      short loc_140009299
0x14000928a  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x140009291  call    cs:__imp_SetServiceStatus
0x140009297  jmp     short loc_140009314
0x140009299  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000929e  jmp     short loc_140009314
0x1400092a0  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1400092a7  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS vTiStatus ...
0x1400092b2  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS vTiStatus ...
0x1400092b8  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 7530h; _SERVICE_STATUS vTiStatus ...
0x1400092c2  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS vTiStatus ...
0x1400092cc  mov     cs:?vbServiceShuttingDown@@3HA, 1; int vbServiceShuttingDown
0x1400092d6  test    rcx, rcx
0x1400092d9  jz      short loc_1400092EA
0x1400092db  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1400092e2  call    cs:__imp_SetServiceStatus
0x1400092e8  jmp     short loc_1400092EF
0x1400092ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400092ef  call    cs:__imp_CoSuspendClassObjects
0x1400092f5  mov     rcx, cs:?vhShutdownEvent@@3PEAXEA; hEvent
0x1400092fc  mov     cs:?vControlCommand@@3KA, edi; ulong vControlCommand
0x140009302  test    rcx, rcx
0x140009305  jz      short loc_14000930F
0x140009307  call    cs:__imp_SetEvent
0x14000930d  jmp     short loc_140009314
0x14000930f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140009314  xor     ecx, ecx; int
0x140009316  call    ?TiTryChangeState@@YAHJ@Z; TiTryChangeState(long)
0x14000931b  mov     rsi, [rsp+28h+arg_8]
0x140009320  mov     eax, ebx
0x140009322  mov     rbx, [rsp+28h+arg_0]
0x140009327  add     rsp, 20h
0x14000932b  pop     rdi
0x14000932c  retn
```

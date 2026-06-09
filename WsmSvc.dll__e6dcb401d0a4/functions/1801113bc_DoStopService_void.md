# DoStopService(void)

- ea: `0x1801113bc`
- end: `0x180111563`
- name: `?DoStopService@@YAXXZ`
- size: `423`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180111bc0`
- `0x180111de0`

## callees

- `0x180005d10`
- `0x180019950`
- `0x18002dd20`
- `0x180068b24`
- `0x18007e530`
- `0x1801113bc`
- `0x180111c40`
- `0x180111d20`
- `0x180112380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011146f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801114f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011146f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801114f2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180111465`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180111465`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1801114e8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1801114e8`
- `WS2_32!__imp_WSACleanup` at `0x1801114ae`
- `WS2_32!__imp_WSACleanup` at `0x1801114ae`

## string_xrefs

- `0x180111497`: `onecore\admin\wmi\wmx\binaries\service\wsmanservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void DoStopService(void)
{
  PVOID *v0; // rcx
  DWORD *v1; // [rsp+30h] [rbp-18h] BYREF
  int v2; // [rsp+38h] [rbp-10h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_SERVICE_STOPPING) )
    WSMan::EventHandler::Write(&LOG_WSMAN_OP_SERVICE_STOPPING, 0, 0);
  v1 = &g_serviceCriticalSection;
  v2 = 0;
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)&g_serviceCriticalSection);
  StopWatchingForConfigErrors();
  StopSoapProcessor();
  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_SERVICE_STOPPED) )
    WSMan::EventHandler::Write(&LOG_WSMAN_OP_SERVICE_STOPPED, 0, 0);
  if ( g_waitObject )
  {
    if ( !UnregisterWait(g_waitObject) && GetLastError() != 997 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanservice.cpp", 512, L"512", 0x54Fu, 0);
    g_waitObject = 0;
  }
  WSACleanup();
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  g_serviceStatus.dwCurrentState = 1;
  g_serviceStatus.dwWin32ExitCode = g_serviceExitCode;
  if ( !g_serviceStatusHandle || SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus) )
    goto LABEL_18;
  g_serviceStatus.dwWin32ExitCode = GetLastError();
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_22;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
LABEL_18:
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_DWORD *)v0 + 7) & 0x400) != 0 )
    WPP_SF_(v0[2], 40, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
LABEL_22:
  InCritSec::~InCritSec((InCritSec *)&v1);
}

```

## disassembly

```asm
0x1801113bc  push    rdi
0x1801113be  sub     rsp, 40h
0x1801113c2  lea     rdi, WPP_GLOBAL_Control
0x1801113c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801113d0  cmp     rcx, rdi
0x1801113d3  jz      short loc_1801113F3
0x1801113d5  test    dword ptr [rcx+1Ch], 400h
0x1801113dc  jz      short loc_1801113F3
0x1801113de  mov     edx, 26h ; '&'
0x1801113e3  lea     r8, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids
0x1801113ea  mov     rcx, [rcx+10h]
0x1801113ee  call    WPP_SF_
0x1801113f3  lea     rcx, LOG_WSMAN_OP_SERVICE_STOPPING; struct _EVENT_DESCRIPTOR *
0x1801113fa  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x1801113ff  test    al, al
0x180111401  jz      short loc_180111414
0x180111403  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x180111406  xor     edx, edx; unsigned int
0x180111408  lea     rcx, LOG_WSMAN_OP_SERVICE_STOPPING; struct _EVENT_DESCRIPTOR *
0x18011140f  call    ?Write@EventHandler@WSMan@@SAXAEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; WSMan::EventHandler::Write(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180111414  lea     rcx, ?g_serviceCriticalSection@@3VCWSManCriticalSection@@A; this
0x18011141b  mov     [rsp+48h+var_18], rcx
0x180111420  mov     [rsp+48h+var_10], 0
0x180111428  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x18011142d  nop
0x18011142e  call    ?StopWatchingForConfigErrors@@YAXXZ; StopWatchingForConfigErrors(void)
0x180111433  call    ?StopSoapProcessor@@YAHXZ; StopSoapProcessor(void)
0x180111438  lea     rcx, LOG_WSMAN_OP_SERVICE_STOPPED; struct _EVENT_DESCRIPTOR *
0x18011143f  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x180111444  test    al, al
0x180111446  jz      short loc_180111459
0x180111448  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x18011144b  xor     edx, edx; unsigned int
0x18011144d  lea     rcx, LOG_WSMAN_OP_SERVICE_STOPPED; struct _EVENT_DESCRIPTOR *
0x180111454  call    ?Write@EventHandler@WSMan@@SAXAEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; WSMan::EventHandler::Write(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180111459  mov     rcx, cs:?g_waitObject@@3PEAXEA; WaitHandle
0x180111460  test    rcx, rcx
0x180111463  jz      short loc_1801114AE
0x180111465  call    cs:__imp_UnregisterWait
0x18011146b  test    eax, eax
0x18011146d  jnz     short loc_1801114A3
0x18011146f  call    cs:__imp_GetLastError
0x180111475  cmp     eax, 3E5h
0x18011147a  jz      short loc_1801114A3
0x18011147c  mov     [rsp+48h+var_28], 0; struct IRequestContext *
0x180111485  mov     r9d, 54Fh; unsigned int
0x18011148b  lea     r8, a512; "512"
0x180111492  mov     edx, 200h; unsigned int
0x180111497  lea     rcx, aOnecoreAdminWm_65; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18011149e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801114a3  mov     cs:?g_waitObject@@3PEAXEA, 0; void * g_waitObject
0x1801114ae  call    cs:__imp_WSACleanup
0x1801114b4  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x1801114bf  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x1801114c9  mov     eax, cs:?g_serviceExitCode@@3KA; ulong g_serviceExitCode
0x1801114cf  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS g_serviceStatus ...
0x1801114d5  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1801114dc  test    rcx, rcx
0x1801114df  jz      short loc_180111528
0x1801114e1  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1801114e8  call    cs:__imp_SetServiceStatus
0x1801114ee  test    eax, eax
0x1801114f0  jnz     short loc_180111528
0x1801114f2  call    cs:__imp_GetLastError
0x1801114f8  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS g_serviceStatus ...
0x1801114fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180111505  cmp     rcx, rdi
0x180111508  jz      short loc_180111553
0x18011150a  test    dword ptr [rcx+1Ch], 200h
0x180111511  jz      short loc_18011152F
0x180111513  mov     edx, 27h ; '''
0x180111518  lea     r8, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids
0x18011151f  mov     rcx, [rcx+10h]
0x180111523  call    WPP_SF_
0x180111528  mov     rcx, cs:WPP_GLOBAL_Control
0x18011152f  cmp     rcx, rdi
0x180111532  jz      short loc_180111553
0x180111534  test    dword ptr [rcx+1Ch], 400h
0x18011153b  jz      short loc_180111553
0x18011153d  mov     edx, 28h ; '('
0x180111542  lea     r8, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids
0x180111549  mov     rcx, [rcx+10h]
0x18011154d  call    WPP_SF_
0x180111552  nop
0x180111553  lea     rcx, [rsp+48h+var_18]; this
0x180111558  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18011155d  add     rsp, 40h
0x180111561  pop     rdi
0x180111562  retn
```

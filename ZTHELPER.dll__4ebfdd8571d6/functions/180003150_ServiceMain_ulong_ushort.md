# ServiceMain(ulong,ushort * *)

- ea: `0x180003150`
- end: `0x180003443`
- name: `?ServiceMain@@YAKKPEAPEAG@Z`
- size: `755`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180002814`
- `0x180002c6c`
- `0x180002fc8`
- `0x180003150`
- `0x180003450`
- `0x180003570`
- `0x18000376c`
- `0x180015008`
- `0x180015114`
- `0x180018010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000323f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000323f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000325a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000325a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003273`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800031a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800031a4`

## pseudocode

```c
__int64 __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  DWORD LastError; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  char v6; // al
  unsigned int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_(1026, 31, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
  g_InitState = 0;
  g_fStopFlag = 0;
  _InterlockedExchange(&g_dwServiceControlFlags, 0);
  g_hStopServiceEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hStopServiceEvent )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_12;
    LastError = GetLastError();
    v3 = 32;
    goto LABEL_11;
  }
  g_InitState |= 1u;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_(1026, 33, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
  ServiceStatusHandle = 0;
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 5000;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"ZTHELPER", (LPHANDLER_FUNCTION_EX)ControlHandler, 0);
  if ( !ServiceStatusHandle )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_12;
    LastError = GetLastError();
    v3 = 34;
LABEL_11:
    WPP_SF_d(1026, v3, WPP_fd30cb189484364f2633d135959507bb_Traceguids, LastError);
LABEL_12:
    v4 = GetLastError();
    if ( !v4 )
      goto LABEL_14;
    goto LABEL_13;
  }
  UpdateStatus();
  if ( g_fVelocityZthelperProcessMitigations && (GetEnforceMitigationsRegValue(&v7), (v4 = EnableMitigations(v7)) != 0)
    || (v4 = ZtHelperInit()) != 0 )
  {
LABEL_13:
    StopService(0, 0);
    goto LABEL_14;
  }
  g_InitState |= 8u;
  UpdateStatus();
  v4 = Rpc_Initialize();
  if ( v4 )
  {
    v6 = xmmword_18001F260;
    if ( (xmmword_18001F260 & 4) != 0 )
    {
      WPP_SF_(1026, 35, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
      v6 = xmmword_18001F260;
    }
    if ( v4 != 1712 && v4 != -1073610739 )
    {
      if ( (v6 & 4) != 0 )
        WPP_SF_d(1026, 37, WPP_fd30cb189484364f2633d135959507bb_Traceguids, v4);
      goto LABEL_13;
    }
    if ( (v6 & 4) != 0 )
      WPP_SF_(1026, 36, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
  }
  g_InitState |= 4u;
  UpdateStatus();
  v4 = 13;
  if ( g_pSvchostData )
    v4 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pSvchostData
          + 24))(
           &g_hRegisteredStopServiceEvent,
           L"ZTHELPER",
           g_hStopServiceEvent,
           StopService,
           0,
           8);
  if ( v4 )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_(1026, 38, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
    goto LABEL_13;
  }
  g_InitState |= 2u;
  UpdateStatus();
  ServiceStatus.dwCurrentState = 4;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 77;
  ServiceStatus.dwWaitHint = 0;
  UpdateStatus();
  if ( (xmmword_18001F260 & 4) == 0 )
    return v4;
  WPP_SF_(1026, 39, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
LABEL_14:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 40, WPP_fd30cb189484364f2633d135959507bb_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180003150  mov     rax, rsp
0x180003153  push    rbx
0x180003154  push    rdi
0x180003155  push    r14
0x180003157  push    r15
0x180003159  sub     rsp, 48h
0x18000315d  xor     edi, edi
0x18000315f  mov     [rax+18h], edi
0x180003162  test    byte ptr cs:xmmword_18001F260, 4
0x180003169  lea     r15, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003170  mov     r14d, 402h
0x180003176  jz      short loc_180003186
0x180003178  lea     edx, [rdi+1Fh]
0x18000317b  mov     ecx, r14d
0x18000317e  mov     r8, r15
0x180003181  call    WPP_SF_
0x180003186  mov     cs:?g_InitState@@3JC, edi; long volatile g_InitState
0x18000318c  mov     eax, edi
0x18000318e  mov     cs:?g_fStopFlag@@3KC, edi; ulong volatile g_fStopFlag
0x180003194  xor     r9d, r9d; lpName
0x180003197  xchg    eax, cs:?g_dwServiceControlFlags@@3JC; long volatile g_dwServiceControlFlags
0x18000319d  xor     r8d, r8d; bInitialState
0x1800031a0  xor     edx, edx; bManualReset
0x1800031a2  xor     ecx, ecx; lpEventAttributes
0x1800031a4  call    cs:__imp_CreateEventW
0x1800031aa  mov     cs:?g_hStopServiceEvent@@3PEAXEA, rax; void * g_hStopServiceEvent
0x1800031b1  test    rax, rax
0x1800031b4  jnz     short loc_1800031D3
0x1800031b6  test    byte ptr cs:xmmword_18001F260, 4
0x1800031bd  jz      loc_180003273
0x1800031c3  call    cs:__imp_GetLastError
0x1800031c9  mov     edx, 20h ; ' '
0x1800031ce  jmp     loc_180003265
0x1800031d3  mov     eax, cs:?g_InitState@@3JC; long volatile g_InitState
0x1800031d9  or      eax, 1
0x1800031dc  mov     cs:?g_InitState@@3JC, eax; long volatile g_InitState
0x1800031e2  test    byte ptr cs:xmmword_18001F260, 4
0x1800031e9  jz      short loc_1800031FB
0x1800031eb  mov     edx, 21h ; '!'
0x1800031f0  mov     ecx, r14d
0x1800031f3  mov     r8, r15
0x1800031f6  call    WPP_SF_
0x1800031fb  xor     r8d, r8d; lpContext
0x1800031fe  mov     cs:?ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rdi; SERVICE_STATUS_HANDLE__ * ServiceStatusHandle
0x180003205  lea     rdx, ?ControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18000320c  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS ServiceStatus ...
0x180003216  lea     rcx, ServiceName; "ZTHELPER"
0x18000321d  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS ServiceStatus ...
0x180003228  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS ServiceStatus ...
0x18000322e  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 1388h; _SERVICE_STATUS ServiceStatus ...
0x180003238  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rdi; _SERVICE_STATUS ServiceStatus ...
0x18000323f  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180003245  mov     cs:?ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ServiceStatusHandle
0x18000324c  test    rax, rax
0x18000324f  jnz     short loc_1800032B1
0x180003251  test    byte ptr cs:xmmword_18001F260, 4
0x180003258  jz      short loc_180003273
0x18000325a  call    cs:__imp_GetLastError
0x180003260  mov     edx, 22h ; '"'
0x180003265  mov     r9d, eax
0x180003268  mov     r8, r15
0x18000326b  mov     ecx, r14d
0x18000326e  call    WPP_SF_d
0x180003273  call    cs:__imp_GetLastError
0x180003279  mov     ebx, eax
0x18000327b  test    eax, eax
0x18000327d  jz      short loc_180003288
0x18000327f  xor     edx, edx; unsigned __int8
0x180003281  xor     ecx, ecx; void *
0x180003283  call    ?StopService@@YAXPEAXE@Z; StopService(void *,uchar)
0x180003288  test    byte ptr cs:xmmword_18001F260, 4
0x18000328f  jz      short loc_1800032A4
0x180003291  mov     edx, 28h ; '('
0x180003296  mov     ecx, r14d
0x180003299  mov     r9d, ebx
0x18000329c  mov     r8, r15
0x18000329f  call    WPP_SF_d
0x1800032a4  mov     eax, ebx
0x1800032a6  add     rsp, 48h
0x1800032aa  pop     r15
0x1800032ac  pop     r14
0x1800032ae  pop     rdi
0x1800032af  pop     rbx
0x1800032b0  retn
0x1800032b1  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x1800032b6  cmp     cs:g_fVelocityZthelperProcessMitigations, edi
0x1800032bc  jz      short loc_1800032DD
0x1800032be  lea     rcx, [rsp+68h+arg_10]
0x1800032c6  call    GetEnforceMitigationsRegValue
0x1800032cb  mov     ecx, [rsp+68h+arg_10]
0x1800032d2  call    EnableMitigations
0x1800032d7  mov     ebx, eax
0x1800032d9  test    eax, eax
0x1800032db  jnz     short loc_18000327F
0x1800032dd  call    ?ZtHelperInit@@YAKXZ; ZtHelperInit(void)
0x1800032e2  mov     ebx, eax
0x1800032e4  test    eax, eax
0x1800032e6  jnz     short loc_18000327F
0x1800032e8  mov     eax, cs:?g_InitState@@3JC; long volatile g_InitState
0x1800032ee  or      eax, 8
0x1800032f1  mov     cs:?g_InitState@@3JC, eax; long volatile g_InitState
0x1800032f7  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x1800032fc  call    ?Rpc_Initialize@@YAKXZ; Rpc_Initialize(void)
0x180003301  mov     ebx, eax
0x180003303  test    eax, eax
0x180003305  jz      short loc_18000336B
0x180003307  mov     al, byte ptr cs:xmmword_18001F260
0x18000330d  test    al, 4
0x18000330f  jz      short loc_180003327
0x180003311  mov     edx, 23h ; '#'
0x180003316  mov     ecx, r14d
0x180003319  mov     r8, r15
0x18000331c  call    WPP_SF_
0x180003321  mov     al, byte ptr cs:xmmword_18001F260
0x180003327  cmp     ebx, 6B0h
0x18000332d  jz      short loc_180003357
0x18000332f  cmp     ebx, 0C002000Dh
0x180003335  jz      short loc_180003357
0x180003337  test    al, 4
0x180003339  jz      loc_18000327F
0x18000333f  mov     edx, 25h ; '%'
0x180003344  mov     ecx, r14d
0x180003347  mov     r9d, ebx
0x18000334a  mov     r8, r15
0x18000334d  call    WPP_SF_d
0x180003352  jmp     loc_18000327F
0x180003357  test    al, 4
0x180003359  jz      short loc_18000336B
0x18000335b  mov     edx, 24h ; '$'
0x180003360  mov     ecx, r14d
0x180003363  mov     r8, r15
0x180003366  call    WPP_SF_
0x18000336b  mov     eax, cs:?g_InitState@@3JC; long volatile g_InitState
0x180003371  or      eax, 4
0x180003374  mov     cs:?g_InitState@@3JC, eax; long volatile g_InitState
0x18000337a  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x18000337f  mov     rax, cs:?g_pSvchostData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostData
0x180003386  mov     ebx, 0Dh
0x18000338b  test    rax, rax
0x18000338e  jz      short loc_1800033C7
0x180003390  mov     r8, cs:?g_hStopServiceEvent@@3PEAXEA; void * g_hStopServiceEvent
0x180003397  lea     r9, ?StopService@@YAXPEAXE@Z; StopService(void *,uchar)
0x18000339e  mov     rax, [rax+0C0h]
0x1800033a5  lea     rdx, ServiceName; "ZTHELPER"
0x1800033ac  mov     [rsp+68h+var_40], 8
0x1800033b4  lea     rcx, ?g_hRegisteredStopServiceEvent@@3PEAXEA; void * g_hRegisteredStopServiceEvent
0x1800033bb  mov     [rsp+68h+var_48], rdi
0x1800033c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c5  mov     ebx, eax
0x1800033c7  test    ebx, ebx
0x1800033c9  jz      short loc_1800033ED
0x1800033cb  test    byte ptr cs:xmmword_18001F260, 4
0x1800033d2  jz      loc_18000327F
0x1800033d8  mov     edx, 26h ; '&'
0x1800033dd  mov     ecx, r14d
0x1800033e0  mov     r8, r15
0x1800033e3  call    WPP_SF_
0x1800033e8  jmp     loc_18000327F
0x1800033ed  mov     eax, cs:?g_InitState@@3JC; long volatile g_InitState
0x1800033f3  or      eax, 2
0x1800033f6  mov     cs:?g_InitState@@3JC, eax; long volatile g_InitState
0x1800033fc  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x180003401  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS ServiceStatus ...
0x18000340b  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 4Dh ; 'M'; _SERVICE_STATUS ServiceStatus ...
0x180003416  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, edi; _SERVICE_STATUS ServiceStatus ...
0x18000341c  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x180003421  test    byte ptr cs:xmmword_18001F260, 4
0x180003428  jz      loc_1800032A4
0x18000342e  mov     edx, 27h ; '''
0x180003433  mov     ecx, r14d
0x180003436  mov     r8, r15
0x180003439  call    WPP_SF_
0x18000343e  jmp     loc_180003288
```

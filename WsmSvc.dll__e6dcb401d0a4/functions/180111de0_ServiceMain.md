# ServiceMain

- ea: `0x180111de0`
- end: `0x180112325`
- name: `ServiceMain`
- size: `1349`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180019950`
- `0x18002dd20`
- `0x18002dd80`
- `0x18004e0d0`
- `0x180068b24`
- `0x18007e530`
- `0x1800973c0`
- `0x180111270`
- `0x1801113bc`
- `0x180111790`
- `0x1801118c4`
- `0x180111de0`
- `0x180112380`
- `0x1801123a8`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801120bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801120f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801121c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801120bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801120f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801121c1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18011228a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18011228a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180112275`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180112275`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180112013`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180112013`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180111e9c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180111e9c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180112079`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1801121b3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180112079`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1801121b3`
- `WS2_32!__imp_WSAStartup` at `0x180111fd6`
- `WS2_32!__imp_WSAStartup` at `0x180111fd6`

## string_xrefs

- `0x18011226e`: `ntdll`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, LPCWSTR *a2)
{
  DWORD LastError; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  HANDLE EventW; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  void (__fastcall *v13)(_QWORD, _QWORD, _QWORD); // rbx
  DWORD *v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+48h] [rbp-B8h]
  struct WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF

  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_SERVICE_STARTING) )
    WSMan::EventHandler::Write(&LOG_WSMAN_OP_SERVICE_STARTING, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
  g_serviceStatus.dwServiceType = 32;
  *(_OWORD *)&g_serviceStatus.dwControlsAccepted = 0;
  g_serviceStatus.dwCurrentState = 2;
  g_serviceStatus.dwWaitHint = 60000;
  g_serviceStatusHandle = RegisterServiceCtrlHandlerExW(*a2, ServiceControlHandler, 0);
  if ( !g_serviceStatusHandle )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids, LastError);
    goto LABEL_53;
  }
  if ( !(unsigned int)CWSManCriticalSection::IsValid((CWSManCriticalSection *)&g_serviceCriticalSection) )
  {
    v4 = g_serviceCriticalSection;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
    goto LABEL_53;
  }
  v14 = &g_serviceCriticalSection;
  v15 = 0;
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)&g_serviceCriticalSection);
  if ( !g_svcHostGlobalData )
  {
    v4 = 6;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v6 = 27;
    goto LABEL_18;
  }
  if ( !WSManMemory::GetHeap() )
  {
    v4 = 14;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v6 = 28;
LABEL_18:
    WPP_SF_(v5[2], v6, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
LABEL_52:
    InCritSec::~InCritSec((InCritSec *)&v14);
LABEL_53:
    if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_SERVICE_START_FAILED) )
      WSMan::LogEvent<long>((struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_OP_SERVICE_START_FAILED, v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids, v4);
    DoStopService();
    return;
  }
  memset_0(&WSAData, 0, sizeof(WSAData));
  v7 = WSAStartup(0x202u, &WSAData);
  v4 = v7;
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_52;
    v9 = 29;
    goto LABEL_51;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  AutoHandle::operator=(&g_stopServiceEvent, EventW);
  if ( !g_stopServiceEvent )
  {
    v7 = GetLastError();
    v4 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v9 = 30;
    goto LABEL_51;
  }
  g_serviceStatus.dwCurrentState = 2;
  if ( !SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus) )
  {
    v7 = GetLastError();
    v4 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v9 = 31;
    goto LABEL_51;
  }
  if ( !(unsigned int)StartWatchingForConfigErrors() )
  {
    v7 = GetLastError();
    v4 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v9 = 32;
    goto LABEL_51;
  }
  if ( !(unsigned int)StartSoapProcessor() )
  {
    v7 = GetLastError();
    v4 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v9 = 33;
    goto LABEL_51;
  }
  if ( (*((unsigned int (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_svcHostGlobalData
        + 24))(
         &g_waitObject,
         *a2,
         g_stopServiceEvent,
         StopService,
         0,
         24) )
  {
    v7 = GetLastError();
    v4 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v9 = 34;
    goto LABEL_51;
  }
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  g_serviceStatus.dwCurrentState = 4;
  g_serviceStatus.dwControlsAccepted = 5;
  if ( !SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus) )
  {
    v7 = GetLastError();
    v4 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_52;
    v9 = 35;
LABEL_51:
    WPP_SF_d(v8[2], v9, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids, v7);
    goto LABEL_52;
  }
  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_SERVICE_STARTED) )
    WSMan::EventHandler::Write(&LOG_WSMAN_OP_SERVICE_STARTED, 0, 0);
  ModuleHandleW = GetModuleHandleW(L"ntdll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WinSqmSetDWORD");
    v13 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress;
    if ( ProcAddress )
    {
      ((void (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 12245, 1);
      v13(0, 12247, 3);
      v13(0, 12248, 0);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids);
  InCritSec::~InCritSec((InCritSec *)&v14);
}

```

## disassembly

```asm
0x180111de0  mov     [rsp-8+arg_0], rbx
0x180111de5  mov     [rsp-8+arg_10], rdi
0x180111dea  push    rbp
0x180111deb  push    r14
0x180111ded  push    r15
0x180111def  lea     rbp, [rsp-100h]
0x180111df7  sub     rsp, 200h
0x180111dfe  mov     rax, cs:__security_cookie
0x180111e05  xor     rax, rsp
0x180111e08  mov     [rbp+110h+var_20], rax
0x180111e0f  lea     rcx, LOG_WSMAN_OP_SERVICE_STARTING; struct _EVENT_DESCRIPTOR *
0x180111e16  mov     rdi, rdx
0x180111e19  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x180111e1e  test    al, al
0x180111e20  jz      short loc_180111E33
0x180111e22  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x180111e25  lea     rcx, LOG_WSMAN_OP_SERVICE_STARTING; struct _EVENT_DESCRIPTOR *
0x180111e2c  xor     edx, edx; unsigned int
0x180111e2e  call    ?Write@EventHandler@WSMan@@SAXAEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; WSMan::EventHandler::Write(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180111e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180111e3a  lea     r14, WPP_GLOBAL_Control
0x180111e41  lea     r15, WPP_c4d52ca20ba03ba6a65e29d73195871a_Traceguids
0x180111e48  cmp     rcx, r14
0x180111e4b  jz      short loc_180111E67
0x180111e4d  test    dword ptr [rcx+1Ch], 400h
0x180111e54  jz      short loc_180111E67
0x180111e56  mov     rcx, [rcx+10h]
0x180111e5a  mov     edx, 17h
0x180111e5f  mov     r8, r15
0x180111e62  call    WPP_SF_
0x180111e67  xorps   xmm0, xmm0
0x180111e6a  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_serviceStatus ...
0x180111e74  movups  xmmword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, xmm0; _SERVICE_STATUS g_serviceStatus ...
0x180111e7b  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_serviceStatus ...
0x180111e85  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180111e8c  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS g_serviceStatus ...
0x180111e96  xor     r8d, r8d; lpContext
0x180111e99  mov     rcx, [rdi]; lpServiceName
0x180111e9c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180111ea2  mov     cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_serviceStatusHandle
0x180111ea9  test    rax, rax
0x180111eac  jnz     short loc_180111EEC
0x180111eae  call    cs:__imp_GetLastError
0x180111eb4  mov     ebx, eax
0x180111eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180111ebd  cmp     rcx, r14
0x180111ec0  jz      loc_1801121FC
0x180111ec6  test    dword ptr [rcx+1Ch], 200h
0x180111ecd  jz      loc_1801121FC
0x180111ed3  mov     rcx, [rcx+10h]
0x180111ed7  mov     edx, 18h
0x180111edc  mov     r9d, eax
0x180111edf  mov     r8, r15
0x180111ee2  call    WPP_SF_d
0x180111ee7  jmp     loc_1801121FC
0x180111eec  lea     rbx, ?g_serviceCriticalSection@@3VCWSManCriticalSection@@A; CWSManCriticalSection g_serviceCriticalSection
0x180111ef3  mov     rcx, rbx; this
0x180111ef6  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x180111efb  test    eax, eax
0x180111efd  jnz     short loc_180111F36
0x180111eff  mov     ebx, cs:?g_serviceCriticalSection@@3VCWSManCriticalSection@@A; CWSManCriticalSection g_serviceCriticalSection
0x180111f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180111f0c  cmp     rcx, r14
0x180111f0f  jz      loc_1801121FC
0x180111f15  test    dword ptr [rcx+1Ch], 200h
0x180111f1c  jz      loc_1801121FC
0x180111f22  mov     rcx, [rcx+10h]
0x180111f26  lea     edx, [rax+1Ah]
0x180111f29  mov     r8, r15
0x180111f2c  call    WPP_SF_
0x180111f31  jmp     loc_1801121FC
0x180111f36  mov     rcx, rbx; this
0x180111f39  mov     [rsp+210h+var_1D0], rbx
0x180111f3e  mov     [rsp+210h+var_1C8], 0
0x180111f46  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x180111f4b  cmp     cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
0x180111f53  jnz     short loc_180111F8B
0x180111f55  mov     ebx, 6
0x180111f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180111f61  cmp     rcx, r14
0x180111f64  jz      loc_1801121F2
0x180111f6a  test    dword ptr [rcx+1Ch], 200h
0x180111f71  jz      loc_1801121F2
0x180111f77  lea     edx, [rbx+15h]
0x180111f7a  mov     rcx, [rcx+10h]
0x180111f7e  mov     r8, r15
0x180111f81  call    WPP_SF_
0x180111f86  jmp     loc_1801121F2
0x180111f8b  call    ?GetHeap@WSManMemory@@SAPEAXXZ; WSManMemory::GetHeap(void)
0x180111f90  test    rax, rax
0x180111f93  jnz     short loc_180111FBA
0x180111f95  lea     ebx, [rax+0Eh]
0x180111f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180111f9f  cmp     rcx, r14
0x180111fa2  jz      loc_1801121F2
0x180111fa8  test    dword ptr [rcx+1Ch], 200h
0x180111faf  jz      loc_1801121F2
0x180111fb5  lea     edx, [rax+1Ch]
0x180111fb8  jmp     short loc_180111F7A
0x180111fba  xor     edx, edx; Val
0x180111fbc  lea     rcx, [rsp+210h+WSAData]; void *
0x180111fc1  mov     r8d, 198h; Size
0x180111fc7  call    memset_0
0x180111fcc  mov     ecx, 202h; wVersionRequested
0x180111fd1  lea     rdx, [rsp+210h+WSAData]; lpWSAData
0x180111fd6  call    cs:__imp_WSAStartup
0x180111fdc  mov     ebx, eax
0x180111fde  test    eax, eax
0x180111fe0  jz      short loc_180112009
0x180111fe2  mov     rcx, cs:WPP_GLOBAL_Control
0x180111fe9  cmp     rcx, r14
0x180111fec  jz      loc_1801121F2
0x180111ff2  test    dword ptr [rcx+1Ch], 800h
0x180111ff9  jz      loc_1801121F2
0x180111fff  mov     edx, 1Dh
0x180112004  jmp     loc_1801121E3
0x180112009  xor     r9d, r9d; lpName
0x18011200c  xor     r8d, r8d; bInitialState
0x18011200f  xor     edx, edx; bManualReset
0x180112011  xor     ecx, ecx; lpEventAttributes
0x180112013  call    cs:__imp_CreateEventW
0x180112019  mov     rdx, rax
0x18011201c  lea     rcx, ?g_stopServiceEvent@@3VAutoHandle@@A; AutoHandle g_stopServiceEvent
0x180112023  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180112028  cmp     cs:?g_stopServiceEvent@@3VAutoHandle@@A, 0; AutoHandle g_stopServiceEvent
0x180112030  jnz     short loc_180112061
0x180112032  call    cs:__imp_GetLastError
0x180112038  mov     ebx, eax
0x18011203a  mov     rcx, cs:WPP_GLOBAL_Control
0x180112041  cmp     rcx, r14
0x180112044  jz      loc_1801121F2
0x18011204a  test    dword ptr [rcx+1Ch], 200h
0x180112051  jz      loc_1801121F2
0x180112057  mov     edx, 1Eh
0x18011205c  jmp     loc_1801121E3
0x180112061  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180112068  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18011206f  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_serviceStatus ...
0x180112079  call    cs:__imp_SetServiceStatus
0x18011207f  test    eax, eax
0x180112081  jnz     short loc_1801120B2
0x180112083  call    cs:__imp_GetLastError
0x180112089  mov     ebx, eax
0x18011208b  mov     rcx, cs:WPP_GLOBAL_Control
0x180112092  cmp     rcx, r14
0x180112095  jz      loc_1801121F2
0x18011209b  test    dword ptr [rcx+1Ch], 200h
0x1801120a2  jz      loc_1801121F2
0x1801120a8  mov     edx, 1Fh
0x1801120ad  jmp     loc_1801121E3
0x1801120b2  call    ?StartWatchingForConfigErrors@@YAHXZ; StartWatchingForConfigErrors(void)
0x1801120b7  test    eax, eax
0x1801120b9  jnz     short loc_1801120EA
0x1801120bb  call    cs:__imp_GetLastError
0x1801120c1  mov     ebx, eax
0x1801120c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801120ca  cmp     rcx, r14
0x1801120cd  jz      loc_1801121F2
0x1801120d3  test    dword ptr [rcx+1Ch], 200h
0x1801120da  jz      loc_1801121F2
0x1801120e0  mov     edx, 20h ; ' '
0x1801120e5  jmp     loc_1801121E3
0x1801120ea  call    ?StartSoapProcessor@@YAHXZ; StartSoapProcessor(void)
0x1801120ef  test    eax, eax
0x1801120f1  jnz     short loc_180112122
0x1801120f3  call    cs:__imp_GetLastError
0x1801120f9  mov     ebx, eax
0x1801120fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180112102  cmp     rcx, r14
0x180112105  jz      loc_1801121F2
0x18011210b  test    dword ptr [rcx+1Ch], 200h
0x180112112  jz      loc_1801121F2
0x180112118  mov     edx, 21h ; '!'
0x18011211d  jmp     loc_1801121E3
0x180112122  mov     rax, cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
0x180112129  lea     r9, ?StopService@@YAXPEAXE@Z; StopService(void *,uchar)
0x180112130  mov     r8, cs:?g_stopServiceEvent@@3VAutoHandle@@A; AutoHandle g_stopServiceEvent
0x180112137  lea     rcx, ?g_waitObject@@3PEAXEA; void * g_waitObject
0x18011213e  mov     rdx, [rdi]
0x180112141  mov     [rsp+210h+var_1E8], 18h
0x180112149  mov     rax, [rax+0C0h]
0x180112150  mov     [rsp+210h+var_1F0], 0
0x180112159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011215e  test    eax, eax
0x180112160  jz      short loc_180112186
0x180112162  call    cs:__imp_GetLastError
0x180112168  mov     ebx, eax
0x18011216a  mov     rcx, cs:WPP_GLOBAL_Control
0x180112171  cmp     rcx, r14
0x180112174  jz      short loc_1801121F2
0x180112176  test    dword ptr [rcx+1Ch], 200h
0x18011217d  jz      short loc_1801121F2
0x18011217f  mov     edx, 22h ; '"'
0x180112184  jmp     short loc_1801121E3
0x180112186  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18011218d  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180112194  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x18011219f  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_serviceStatus ...
0x1801121a9  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS g_serviceStatus ...
0x1801121b3  call    cs:__imp_SetServiceStatus
0x1801121b9  test    eax, eax
0x1801121bb  jnz     loc_18011224D
0x1801121c1  call    cs:__imp_GetLastError
0x1801121c7  mov     ebx, eax
0x1801121c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801121d0  cmp     rcx, r14
0x1801121d3  jz      short loc_1801121F2
0x1801121d5  test    dword ptr [rcx+1Ch], 200h
0x1801121dc  jz      short loc_1801121F2
0x1801121de  mov     edx, 23h ; '#'
0x1801121e3  mov     rcx, [rcx+10h]
0x1801121e7  mov     r9d, eax
0x1801121ea  mov     r8, r15
0x1801121ed  call    WPP_SF_d
0x1801121f2  lea     rcx, [rsp+210h+var_1D0]; this
0x1801121f7  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1801121fc  lea     rcx, LOG_WSMAN_OP_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180112203  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x180112208  test    al, al
0x18011220a  jz      short loc_18011221A
0x18011220c  mov     edx, ebx
0x18011220e  lea     rcx, LOG_WSMAN_OP_SERVICE_START_FAILED; struct _EVENT_DESCRIPTOR *
0x180112215  call    ??$LogEvent@J@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@J@Z; WSMan::LogEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x18011221a  mov     rcx, cs:WPP_GLOBAL_Control
0x180112221  cmp     rcx, r14
0x180112224  jz      short loc_180112243
0x180112226  test    dword ptr [rcx+1Ch], 400h
0x18011222d  jz      short loc_180112243
0x18011222f  mov     rcx, [rcx+10h]
0x180112233  mov     edx, 25h ; '%'
0x180112238  mov     r9d, ebx
0x18011223b  mov     r8, r15
0x18011223e  call    WPP_SF_d
0x180112243  call    ?DoStopService@@YAXXZ; DoStopService(void)
0x180112248  jmp     loc_1801122FD
0x18011224d  lea     rcx, LOG_WSMAN_OP_SERVICE_STARTED; struct _EVENT_DESCRIPTOR *
0x180112254  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x180112259  test    al, al
0x18011225b  jz      short loc_18011226E
0x18011225d  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x180112260  lea     rcx, LOG_WSMAN_OP_SERVICE_STARTED; struct _EVENT_DESCRIPTOR *
0x180112267  xor     edx, edx; unsigned int
0x180112269  call    ?Write@EventHandler@WSMan@@SAXAEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; WSMan::EventHandler::Write(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18011226e  lea     rcx, ModuleName; "ntdll"
0x180112275  call    cs:__imp_GetModuleHandleW
0x18011227b  test    rax, rax
0x18011227e  jz      short loc_1801122CD
0x180112280  lea     rdx, aWinsqmsetdword; "WinSqmSetDWORD"
0x180112287  mov     rcx, rax; hModule
0x18011228a  call    cs:__imp_GetProcAddress
0x180112290  mov     rbx, rax
0x180112293  test    rax, rax
0x180112296  jz      short loc_1801122CD
0x180112298  xor     ecx, ecx
0x18011229a  mov     edx, 2FD5h
0x18011229f  lea     r8d, [rcx+1]
0x1801122a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801122a8  xor     ecx, ecx
0x1801122aa  mov     edx, 2FD7h
0x1801122af  mov     rax, rbx
0x1801122b2  lea     r8d, [rcx+3]
0x1801122b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801122bb  xor     r8d, r8d
0x1801122be  mov     edx, 2FD8h
0x1801122c3  xor     ecx, ecx
0x1801122c5  mov     rax, rbx
0x1801122c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801122cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801122d4  cmp     rcx, r14
0x1801122d7  jz      short loc_1801122F3
0x1801122d9  test    dword ptr [rcx+1Ch], 400h
0x1801122e0  jz      short loc_1801122F3
0x1801122e2  mov     rcx, [rcx+10h]
0x1801122e6  mov     edx, 24h ; '$'
0x1801122eb  mov     r8, r15
0x1801122ee  call    WPP_SF_
0x1801122f3  lea     rcx, [rsp+210h+var_1D0]; this
0x1801122f8  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1801122fd  mov     rcx, [rbp+110h+var_20]
0x180112304  xor     rcx, rsp; StackCookie
0x180112307  call    __security_check_cookie
0x18011230c  lea     r11, [rsp+210h+var_10]
0x180112314  mov     rbx, [r11+20h]
0x180112318  mov     rdi, [r11+30h]
0x18011231c  mov     rsp, r11
0x18011231f  pop     r15
0x180112321  pop     r14
0x180112323  pop     rbp
0x180112324  retn
```

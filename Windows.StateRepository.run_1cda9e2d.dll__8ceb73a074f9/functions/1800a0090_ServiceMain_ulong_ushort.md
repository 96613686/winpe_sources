# ServiceMain(ulong,ushort * *)

- ea: `0x1800a0090`
- end: `0x1800a0337`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `679`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x1800611fc`
- `0x180068758`
- `0x1800a0090`
- `0x1800afa0c`
- `0x1800b15d8`
- `0x1800b1630`
- `0x1800b937c`
- `0x1800bf01c`
- `0x1800c06cc`
- `0x1801a3958`
- `0x1801a3984`
- `0x1801a3f6c`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a0176`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a0176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a0302`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a0302`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a00b6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a00b6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a024c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a024c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a01fa`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a01fa`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a02da`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a02da`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800a011c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800a011c`

## string_xrefs

- `0x1800a02bb`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1800a02e8`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1800a0281`: `ServiceLastKnownStatus`
- `0x1800a029a`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ServiceMain(StateRepository::Globals *a1, unsigned __int16 **a2)
{
  int v3; // esi
  const unsigned int *v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  HANDLE EventW; // r8
  signed int v8; // eax
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // ebx
  const char *v14; // r9
  DWORD CurrentProcessId; // eax
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-30h]
  _BYTE v18[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v21; // [rsp+88h] [rbp+38h] BYREF

  v3 = (int)a1;
  if ( StateRepository::Globals::GetServiceDebugOnStartup(a1) )
    DebugBreak();
  v18[0] = 1;
  v19 = 0;
  if ( ServiceGlobals::g_status.dwCurrentState )
  {
    WaitHandle = 0;
    qword_1804DFA40 = 0;
    byte_1804DFA3C = 0;
    *(_OWORD *)&ServiceGlobals::g_status.dwServiceType = 0;
    *(_OWORD *)&ServiceGlobals::g_status.dwWin32ExitCode = 0;
    ServiceGlobals::g_statusHandle = 0;
    _InterlockedAnd(&qword_1804E01A0 + 1, 0xFFFFFFFE);
  }
  CheckServiceLastKnownStatusAtStartup();
  ServiceGlobals::g_statusHandle = RegisterServiceCtrlHandlerExW(L"StateRepository", ServiceControl, 0);
  if ( !ServiceGlobals::g_statusHandle )
  {
    AutoUnregister::SetFailureFromLastError((AutoUnregister *)v18);
    v5 = 100;
LABEL_7:
    v6 = v19;
LABEL_8:
    StateRepository::ServiceMain::AutoLog_ServiceStart::LogError(v5, v6);
LABEL_9:
    _InterlockedOr(&qword_1804E01A0 + 1, 1u);
    goto LABEL_37;
  }
  ServiceGlobals::g_status.dwServiceType = 32;
  ServiceGlobals::g_status.dwServiceSpecificExitCode = 0;
  StateRepository::Service::UpdateStatusForStartPending(0, v4);
  EventW = CreateEventW(0, 1, 0, 0);
  qword_1804DFA40 = (__int64)EventW;
  if ( !EventW )
  {
    AutoUnregister::SetFailureFromLastError((AutoUnregister *)v18);
    v5 = 200;
    goto LABEL_7;
  }
  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)()))(qword_1804DFA50 + 192))(
         &WaitHandle,
         L"StateRepository",
         EventW,
         StopService);
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v19 = v8;
    v6 = (unsigned int)v8;
    v5 = 300;
    goto LABEL_8;
  }
  v9 = -2147221008;
  v21 = -2147221008;
  v10 = RoInitialize(1);
  if ( v10 < 0 )
  {
    if ( v10 == -2147417850 )
    {
      v19 = 1;
      goto LABEL_23;
    }
  }
  else
  {
    v21 = v10;
    v9 = v10;
  }
  v19 = v10;
  if ( v10 < 0 )
  {
    StateRepository::ServiceMain::AutoLog_ServiceStart::LogError(400, (unsigned int)v10);
LABEL_20:
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v21);
    goto LABEL_9;
  }
LABEL_23:
  if ( (int)SvcInitialize(v3, a2) < 0 )
    goto LABEL_20;
  if ( v9 >= 0 )
    RoUninitialize();
  ServiceGlobals::g_status.dwControlsAccepted = 13;
  ServiceGlobals::g_status.dwCurrentState = 4;
  ServiceGlobals::g_status.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceGlobals::g_status.dwCheckPoint = 0;
  if ( dword_1804DFA10 != 4 )
  {
    v12 = StateRepository::Globals::SetStatus(
            (StateRepository::Globals *)L"ServiceLastKnownStatus",
            (const unsigned __int16 *)4,
            v11);
    v13 = v12;
    if ( v12 >= 0 )
      v13 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x493,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v12,
        0);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
        (const char *)(unsigned int)v13,
        v17);
  }
  if ( !SetServiceStatus(ServiceGlobals::g_statusHandle, &ServiceGlobals::g_status) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
      v14);
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 2) != 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0q_EventWriteTransfer(v16, &ServiceStarted, CurrentProcessId);
  }
  v18[0] = 0;
LABEL_37:
  AutoUnregister::~AutoUnregister((AutoUnregister *)v18);
}

```

## disassembly

```asm
0x1800a0090  mov     [rsp-18h+arg_0], rbx
0x1800a0095  mov     [rsp-18h+arg_8], rsi
0x1800a009a  push    rbp
0x1800a009b  push    rdi
0x1800a009c  push    r14
0x1800a009e  mov     rbp, rsp
0x1800a00a1  sub     rsp, 50h
0x1800a00a5  mov     rdi, rdx
0x1800a00a8  mov     esi, ecx
0x1800a00aa  call    ?GetServiceDebugOnStartup@Globals@StateRepository@@YA_NXZ; StateRepository::Globals::GetServiceDebugOnStartup(void)
0x1800a00af  xor     r14d, r14d
0x1800a00b2  test    al, al
0x1800a00b4  jz      short loc_1800A00BC
0x1800a00b6  call    cs:__imp_DebugBreak
0x1800a00bc  mov     [rbp+var_10], 1
0x1800a00c0  mov     [rbp+var_C], r14d
0x1800a00c4  mov     [rbp+arg_10], 1
0x1800a00c8  cmp     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwCurrentState, r14d; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a00cf  jbe     short loc_1800A0106
0x1800a00d1  mov     cs:WaitHandle, r14
0x1800a00d8  mov     cs:qword_1804DFA40, r14
0x1800a00df  mov     cs:byte_1804DFA3C, r14b
0x1800a00e6  xorps   xmm0, xmm0
0x1800a00e9  movups  xmmword ptr cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwServiceType, xmm0; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a00f0  movups  xmmword ptr cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a00f7  mov     cs:?g_statusHandle@ServiceGlobals@@3PEAUSERVICE_STATUS_HANDLE__@@EA, r14; SERVICE_STATUS_HANDLE__ * ServiceGlobals::g_statusHandle
0x1800a00fe  lock and dword ptr cs:qword_1804E01A0+4, 0FFFFFFFEh
0x1800a0106  call    CheckServiceLastKnownStatusAtStartup
0x1800a010b  xor     r8d, r8d; lpContext
0x1800a010e  lea     rdx, ServiceControl; lpHandlerProc
0x1800a0115  lea     rcx, ServiceName; "StateRepository"
0x1800a011c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800a0122  mov     cs:?g_statusHandle@ServiceGlobals@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ServiceGlobals::g_statusHandle
0x1800a0129  test    rax, rax
0x1800a012c  jnz     short loc_1800A0152
0x1800a012e  lea     rcx, [rbp+var_10]; this
0x1800a0132  call    ?SetFailureFromLastError@AutoUnregister@@QEAAJXZ; AutoUnregister::SetFailureFromLastError(void)
0x1800a0137  mov     ecx, 64h ; 'd'
0x1800a013c  mov     edx, [rbp+var_C]
0x1800a013f  call    ?LogError@AutoLog_ServiceStart@ServiceMain@StateRepository@@SAXW4Checkpoint@123@J@Z; StateRepository::ServiceMain::AutoLog_ServiceStart::LogError(StateRepository::ServiceMain::AutoLog_ServiceStart::Checkpoint,long)
0x1800a0144  nop
0x1800a0145  lock or dword ptr cs:qword_1804E01A0+4, 1
0x1800a014d  jmp     loc_1800A031B
0x1800a0152  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a015c  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, r14d; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a0163  xor     ecx, ecx; this
0x1800a0165  call    ?UpdateStatusForStartPending@Service@StateRepository@@YAXPEBI@Z; StateRepository::Service::UpdateStatusForStartPending(uint const *)
0x1800a016a  xor     r9d, r9d; lpName
0x1800a016d  xor     r8d, r8d; bInitialState
0x1800a0170  lea     edx, [r9+1]; bManualReset
0x1800a0174  xor     ecx, ecx; lpEventAttributes
0x1800a0176  call    cs:__imp_CreateEventW
0x1800a017c  mov     r8, rax
0x1800a017f  mov     cs:qword_1804DFA40, rax
0x1800a0186  test    rax, rax
0x1800a0189  jnz     short loc_1800A019B
0x1800a018b  lea     rcx, [rbp+var_10]; this
0x1800a018f  call    ?SetFailureFromLastError@AutoUnregister@@QEAAJXZ; AutoUnregister::SetFailureFromLastError(void)
0x1800a0194  mov     ecx, 0C8h
0x1800a0199  jmp     short loc_1800A013C
0x1800a019b  mov     rax, cs:qword_1804DFA50
0x1800a01a2  mov     [rsp+50h+var_28], 18h
0x1800a01aa  mov     qword ptr [rsp+50h+var_30], r14; int
0x1800a01af  lea     r9, StopService
0x1800a01b6  lea     rdx, ServiceName; "StateRepository"
0x1800a01bd  lea     rcx, WaitHandle
0x1800a01c4  mov     rax, [rax+0C0h]
0x1800a01cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a01d0  test    eax, eax
0x1800a01d2  jz      short loc_1800A01ED
0x1800a01d4  jle     short loc_1800A01DE
0x1800a01d6  movzx   eax, ax
0x1800a01d9  or      eax, 80070000h
0x1800a01de  mov     [rbp+var_C], eax
0x1800a01e1  mov     edx, eax
0x1800a01e3  mov     ecx, 12Ch
0x1800a01e8  jmp     loc_1800A013F
0x1800a01ed  mov     ebx, 800401F0h
0x1800a01f2  mov     [rbp+arg_18], ebx
0x1800a01f5  mov     ecx, 1
0x1800a01fa  call    cs:__imp_RoInitialize
0x1800a0200  test    eax, eax
0x1800a0202  js      short loc_1800A022B
0x1800a0204  mov     [rbp+arg_18], eax
0x1800a0207  mov     ebx, eax
0x1800a0209  mov     [rbp+var_C], eax
0x1800a020c  test    eax, eax
0x1800a020e  jns     short loc_1800A0239
0x1800a0210  mov     edx, eax
0x1800a0212  mov     ecx, 190h
0x1800a0217  call    ?LogError@AutoLog_ServiceStart@ServiceMain@StateRepository@@SAXW4Checkpoint@123@J@Z; StateRepository::ServiceMain::AutoLog_ServiceStart::LogError(StateRepository::ServiceMain::AutoLog_ServiceStart::Checkpoint,long)
0x1800a021c  nop
0x1800a021d  lea     rcx, [rbp+arg_18]; this
0x1800a0221  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x1800a0226  jmp     loc_1800A0145
0x1800a022b  cmp     eax, 80010106h
0x1800a0230  jnz     short loc_1800A0209
0x1800a0232  mov     [rbp+var_C], 1
0x1800a0239  mov     rdx, rdi; unsigned __int16 **
0x1800a023c  mov     ecx, esi; unsigned int
0x1800a023e  call    ?SvcInitialize@@YAJKPEAPEAG@Z; SvcInitialize(ulong,ushort * *)
0x1800a0243  nop
0x1800a0244  test    eax, eax
0x1800a0246  js      short loc_1800A021D
0x1800a0248  test    ebx, ebx
0x1800a024a  js      short loc_1800A0252
0x1800a024c  call    cs:__imp_RoUninitialize
0x1800a0252  mov     [rbp+arg_10], r14b
0x1800a0256  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0Dh; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a0260  mov     edx, 4; unsigned __int16 *
0x1800a0265  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwCurrentState, edx; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a026b  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r14d; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a0272  mov     qword ptr cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a0279  cmp     cs:dword_1804DFA10, edx
0x1800a027f  jz      short loc_1800A02CC
0x1800a0281  lea     rcx, ?stateRepositoryRegistryNameServiceLastKnownStatus@StateRepository@@3QBGB; "ServiceLastKnownStatus"
0x1800a0288  call    ?SetStatus@Globals@StateRepository@@YAJPEBGI@Z; StateRepository::Globals::SetStatus(ushort const *,uint)
0x1800a028d  mov     ebx, eax
0x1800a028f  test    eax, eax
0x1800a0291  jns     short loc_1800A02AD
0x1800a0293  mov     rcx, [rbp+18h]; this
0x1800a0297  mov     r9d, eax; char *
0x1800a029a  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1800a02a1  mov     edx, 493h; void *
0x1800a02a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a02ab  jmp     short loc_1800A02B0
0x1800a02ad  mov     ebx, r14d
0x1800a02b0  mov     rcx, [rbp+18h]; this
0x1800a02b4  test    ebx, ebx
0x1800a02b6  jns     short loc_1800A02CC
0x1800a02b8  mov     r9d, ebx; char *
0x1800a02bb  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1800a02c2  mov     edx, 2E9h; void *
0x1800a02c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a02cc  lea     rdx, ?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800a02d3  mov     rcx, cs:?g_statusHandle@ServiceGlobals@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800a02da  call    cs:__imp_SetServiceStatus
0x1800a02e0  mov     rcx, [rbp+18h]; this
0x1800a02e4  test    eax, eax
0x1800a02e6  jnz     short loc_1800A02F9
0x1800a02e8  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1800a02ef  mov     edx, 2EDh; void *
0x1800a02f4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800a02f9  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 2
0x1800a0300  jz      short loc_1800A0317
0x1800a0302  call    cs:__imp_GetCurrentProcessId
0x1800a0308  mov     r8d, eax
0x1800a030b  lea     rdx, ServiceStarted
0x1800a0312  call    McTemplateU0q_EventWriteTransfer
0x1800a0317  mov     [rbp+var_10], r14b
0x1800a031b  lea     rcx, [rbp+var_10]; this
0x1800a031f  call    ??1AutoUnregister@@QEAA@XZ; AutoUnregister::~AutoUnregister(void)
0x1800a0324  mov     rbx, [rsp+50h+arg_0]
0x1800a0329  mov     rsi, [rsp+50h+arg_8]
0x1800a032e  add     rsp, 50h
0x1800a0332  pop     r14
0x1800a0334  pop     rdi
0x1800a0335  pop     rbp
0x1800a0336  retn
```

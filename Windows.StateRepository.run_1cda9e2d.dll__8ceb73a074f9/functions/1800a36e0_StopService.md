# StopService

- ea: `0x1800a36e0`
- end: `0x1800a38e3`
- name: `StopService`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x1800611fc`
- `0x180068758`
- `0x1800a36e0`
- `0x1800afacc`
- `0x1800b1140`
- `0x1800bd5a8`
- `0x1801a3f6c`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a38c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a38c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a37fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a37fc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800a37dd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800a37dd`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800a36ef`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800a36ef`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a37c9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800a37c9`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a3784`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800a3784`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a389f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800a389f`

## string_xrefs

- `0x1800a3701`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1800a37ae`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1800a3880`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1800a38ae`: `onecore\base\appmodel\staterepository\winrt\client\srv\servicemain.cpp`
- `0x1800a384d`: `ServiceLastKnownStatus`
- `0x1800a3867`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StopService(StateRepository::Service *a1)
{
  int v1; // eax
  int v2; // ebx
  int v3; // eax
  unsigned int v4; // r8d
  void *v5; // rcx
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  DWORD CurrentProcessId; // eax
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  StateRepository::Service::UpdateStatusForStopPending(a1);
  v1 = CoRegisterServerShutdownDelay(0, 0);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x305,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
      (const char *)(unsigned int)v1,
      v12);
  if ( disconnectableContextCallback )
  {
    v12 = 5;
    (*(void (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *))(*(_QWORD *)disconnectableContextCallback + 24LL))(
      disconnectableContextCallback,
      RevokeActivationFactoryCallback,
      0,
      &IID_IContextCallback);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)disconnectableContextCallback + 16LL))(disconnectableContextCallback);
    disconnectableContextCallback = 0;
  }
  StateRepository::WinRT::Client::RequestInProgress::WaitForNoUse(UpdateStatusDuringWaitForRequestsInUse);
  v2 = -2147221008;
  v3 = RoInitialize(1);
  if ( v3 < 0 )
  {
    if ( v3 == -2147417850 )
      v3 = 1;
  }
  else
  {
    v2 = v3;
  }
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x317,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
      (const char *)(unsigned int)v3,
      v12);
  SvcUninitialize();
  if ( v2 >= 0 )
    RoUninitialize();
  if ( WaitHandle )
  {
    UnregisterWaitEx(WaitHandle, 0);
    WaitHandle = 0;
  }
  v5 = (void *)_InterlockedExchange64(&qword_1804DFA40, 0);
  if ( v5 )
    CloseHandle(v5);
  qword_1804DFA50 = 0;
  ServiceGlobals::g_status.dwControlsAccepted = 1;
  ServiceGlobals::g_status.dwCurrentState = 1;
  ServiceGlobals::g_status.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceGlobals::g_status.dwCheckPoint = 0;
  v6 = (const unsigned __int16 *)(byte_1804DFA3C != 0 ? 101 : 1);
  if ( (_DWORD)v6 != dword_1804DFA10 )
  {
    v7 = StateRepository::Globals::SetStatus((StateRepository::Globals *)L"ServiceLastKnownStatus", v6, v4);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x493,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v7,
        v12);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
        (const char *)v8,
        v13);
    }
  }
  if ( !SetServiceStatus(ServiceGlobals::g_statusHandle, &ServiceGlobals::g_status) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\srv\\servicemain.cpp",
      v9);
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 2) != 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0q_EventWriteTransfer(v11, &ServiceStopped, CurrentProcessId);
  }
}

```

## disassembly

```asm
0x1800a36e0  push    rbx
0x1800a36e2  sub     rsp, 40h
0x1800a36e6  call    ?UpdateStatusForStopPending@Service@StateRepository@@YAXXZ; StateRepository::Service::UpdateStatusForStopPending(void)
0x1800a36eb  xor     edx, edx
0x1800a36ed  xor     ecx, ecx
0x1800a36ef  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800a36f5  mov     rcx, [rsp+48h]; this
0x1800a36fa  test    eax, eax
0x1800a36fc  jns     short loc_1800A3712
0x1800a36fe  mov     r9d, eax; char *
0x1800a3701  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1800a3708  mov     edx, 305h; void *
0x1800a370d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a3712  mov     rcx, cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1800a3719  test    rcx, rcx
0x1800a371c  jz      short loc_1800A376A
0x1800a371e  mov     rax, [rcx]
0x1800a3721  mov     [rsp+48h+var_20], 0
0x1800a372a  mov     [rsp+48h+var_28], 5; int
0x1800a3732  lea     r9, IID_IContextCallback
0x1800a3739  xor     r8d, r8d
0x1800a373c  lea     rdx, ?RevokeActivationFactoryCallback@@YAJPEAUtagComCallData@@@Z; RevokeActivationFactoryCallback(tagComCallData *)
0x1800a3743  mov     rax, [rax+18h]
0x1800a3747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a374c  mov     rcx, cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * disconnectableContextCallback
0x1800a3753  mov     rax, [rcx]
0x1800a3756  mov     rax, [rax+10h]
0x1800a375a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a375f  mov     cs:?disconnectableContextCallback@@3PEAUIContextCallback@@EA, 0; IContextCallback * disconnectableContextCallback
0x1800a376a  lea     rcx, UpdateStatusDuringWaitForRequestsInUse; void (*)(void)
0x1800a3771  call    ?WaitForNoUse@RequestInProgress@Client@WinRT@StateRepository@@SAXP6AXXZ@Z; StateRepository::WinRT::Client::RequestInProgress::WaitForNoUse(void (*)(void))
0x1800a3776  mov     ebx, 800401F0h
0x1800a377b  mov     [rsp+48h+arg_10], ebx
0x1800a377f  mov     ecx, 1
0x1800a3784  call    cs:__imp_RoInitialize
0x1800a378a  test    eax, eax
0x1800a378c  js      short loc_1800A3796
0x1800a378e  mov     ebx, eax
0x1800a3790  mov     [rsp+48h+arg_10], eax
0x1800a3794  jmp     short loc_1800A37A2
0x1800a3796  cmp     eax, 80010106h
0x1800a379b  jnz     short loc_1800A37A2
0x1800a379d  mov     eax, 1
0x1800a37a2  mov     rcx, [rsp+48h]; this
0x1800a37a7  test    eax, eax
0x1800a37a9  jns     short loc_1800A37BF
0x1800a37ab  mov     r9d, eax; char *
0x1800a37ae  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1800a37b5  mov     edx, 317h; void *
0x1800a37ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a37bf  call    ?SvcUninitialize@@YAXXZ; SvcUninitialize(void)
0x1800a37c4  nop
0x1800a37c5  test    ebx, ebx
0x1800a37c7  js      short loc_1800A37CF
0x1800a37c9  call    cs:__imp_RoUninitialize
0x1800a37cf  mov     rcx, cs:WaitHandle; WaitHandle
0x1800a37d6  test    rcx, rcx
0x1800a37d9  jz      short loc_1800A37EE
0x1800a37db  xor     edx, edx; CompletionEvent
0x1800a37dd  call    cs:__imp_UnregisterWaitEx
0x1800a37e3  mov     cs:WaitHandle, 0
0x1800a37ee  xor     ecx, ecx
0x1800a37f0  xchg    rcx, cs:qword_1804DFA40; hObject
0x1800a37f7  test    rcx, rcx
0x1800a37fa  jz      short loc_1800A3802
0x1800a37fc  call    cs:__imp_CloseHandle
0x1800a3802  mov     cs:qword_1804DFA50, 0
0x1800a380d  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a3817  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a3821  mov     cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a382b  mov     qword ptr cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS ServiceGlobals::g_status ...
0x1800a3836  mov     al, cs:byte_1804DFA3C
0x1800a383c  neg     al
0x1800a383e  sbb     edx, edx
0x1800a3840  and     edx, 64h
0x1800a3843  inc     edx; unsigned __int16 *
0x1800a3845  cmp     edx, cs:dword_1804DFA10
0x1800a384b  jz      short loc_1800A3891
0x1800a384d  lea     rcx, ?stateRepositoryRegistryNameServiceLastKnownStatus@StateRepository@@3QBGB; "ServiceLastKnownStatus"
0x1800a3854  call    ?SetStatus@Globals@StateRepository@@YAJPEBGI@Z; StateRepository::Globals::SetStatus(ushort const *,uint)
0x1800a3859  mov     ebx, eax
0x1800a385b  test    eax, eax
0x1800a385d  jns     short loc_1800A3891
0x1800a385f  mov     rcx, [rsp+48h]; this
0x1800a3864  mov     r9d, eax; char *
0x1800a3867  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1800a386e  mov     edx, 493h; void *
0x1800a3873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3878  mov     rcx, [rsp+48h]; this
0x1800a387d  mov     r9d, ebx; char *
0x1800a3880  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1800a3887  mov     edx, 2E9h; void *
0x1800a388c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a3891  lea     rdx, ?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800a3898  mov     rcx, cs:?g_statusHandle@ServiceGlobals@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800a389f  call    cs:__imp_SetServiceStatus
0x1800a38a5  test    eax, eax
0x1800a38a7  jnz     short loc_1800A38BF
0x1800a38a9  mov     rcx, [rsp+48h]; this
0x1800a38ae  lea     r8, aOnecoreBaseApp_353; "onecore\\base\\appmodel\\staterepositor"...
0x1800a38b5  mov     edx, 2EDh; void *
0x1800a38ba  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800a38bf  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 2
0x1800a38c6  jz      short loc_1800A38DD
0x1800a38c8  call    cs:__imp_GetCurrentProcessId
0x1800a38ce  mov     r8d, eax
0x1800a38d1  lea     rdx, ServiceStopped
0x1800a38d8  call    McTemplateU0q_EventWriteTransfer
0x1800a38dd  add     rsp, 40h
0x1800a38e1  pop     rbx
0x1800a38e2  retn
```

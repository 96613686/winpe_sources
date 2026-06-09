# CalaisStopService(void *,uchar)

- ea: `0x180024710`
- end: `0x1800249d8`
- name: `?CalaisStopService@@YAXPEAXE@Z`
- size: `712`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x180010f50`

## callees

- `0x180001900`
- `0x180012380`
- `0x1800123a0`
- `0x18001a1bc`
- `0x18001a1ec`
- `0x18001a21c`
- `0x18001a2ac`
- `0x18002438c`
- `0x180024710`
- `0x180028a98`
- `0x180029314`
- `0x18002a504`
- `0x18002a7e4`
- `0x18002b214`
- `0x18002f64c`
- `0x180030c98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002487c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002487c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024918`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024724`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180024929`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180024944`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180024929`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180024944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002484f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002488e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800248c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002484f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002488e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800248c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024904`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002478e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800249be`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002478e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800249be`
- `ADVAPI32!DeregisterEventSource` at `0x180024966`
- `ADVAPI32!DeregisterEventSource` at `0x180024966`
- `KERNEL32!UnregisterWait` at `0x1800247b4`
- `KERNEL32!UnregisterWait` at `0x1800247b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall CalaisStopService(void *a1)
{
  const unsigned __int8 *v1; // r8
  const unsigned __int8 *v2; // r9
  HANDLE v3; // rax
  HANDLE v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  const unsigned __int8 *v7; // r8
  const unsigned __int8 *v8; // r9
  BOOL v9; // eax
  char v10; // [rsp+40h] [rbp+18h] BYREF

  if ( g_hCalaisShutdown )
    SetEvent(g_hCalaisShutdown);
  if ( dword_18004BE68 )
  {
    CalRpcSetCallerId((void *)_InterlockedIncrement(&dword_18004BF90));
    if ( dword_18004BE64 )
    {
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v10, qword_18004BD38, v1, v2);
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwCheckPoint = 0;
      ServiceStatus.dwWaitHint = 30000;
      if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
        GetLastError();
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v10);
    }
    if ( WaitHandle )
    {
      if ( !UnregisterWait(WaitHandle) )
        GetLastError();
      WaitHandle = 0;
    }
    v3 = AccessStartedEvent();
    if ( v3 )
      _ResetEvent(v3);
    v4 = AccessStoppedEvent();
    if ( v4 )
      _SetEvent(v4);
    AppTerminateDeviceRegistration();
    if ( dword_18004BE58 == 1 )
      CalaisPreStop();
    if ( dword_18004BE5C == 1 )
    {
      CalRpcStop();
      dword_18004BE5C = 0;
    }
    if ( dword_18004BE58 == 1 )
    {
      CalaisStop(v6, v5, v7, v8);
      dword_18004BE58 = 0;
    }
    if ( dword_18004BE60 == 1 )
    {
      I_ServerCacheWriteDataToDisk(v6);
      ScCacheDeleteCache();
      dword_18004BE60 = 0;
    }
    if ( hEvent )
    {
      v9 = CloseHandle(hEvent);
      hEvent = 0;
      if ( !v9 )
        GetLastError();
      hEvent = 0;
    }
    if ( dword_18004BF0C )
    {
      EnterCriticalSection(&stru_18004BAD0);
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      LeaveCriticalSection(&stru_18004BAD0);
    }
    if ( dword_18004BF08 )
    {
      EnterCriticalSection(&CriticalSection);
      if ( qword_18004BEF8 )
      {
        CloseHandle(qword_18004BEF8);
        qword_18004BEF8 = 0;
      }
      LeaveCriticalSection(&CriticalSection);
    }
    if ( dword_18004BEF0 )
    {
      EnterCriticalSection(&stru_18004BAA8);
      if ( qword_18004BF10 )
      {
        CloseHandle(qword_18004BF10);
        qword_18004BF10 = 0;
      }
      LeaveCriticalSection(&stru_18004BAA8);
    }
    if ( dwTlsIndex != -1 )
    {
      TlsFree(dwTlsIndex);
      dwTlsIndex = -1;
    }
    if ( dword_18004B240 != -1 )
    {
      TlsFree(dword_18004B240);
      dword_18004B240 = -1;
    }
    dword_18004BE68 = 0;
    if ( hEventLog )
      DeregisterEventSource(hEventLog);
    hEventLog = 0;
    if ( qword_18004BD38 )
    {
      CCriticalSectionObject::`scalar deleting destructor'(qword_18004BD38, v5);
      qword_18004BD38 = 0;
    }
    if ( dword_18004BE64 )
    {
      dword_18004BE64 = 0;
      ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwWin32ExitCode = 0;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
        GetLastError();
    }
  }
  McGenEventUnregister_EventUnregister();
}

```

## disassembly

```asm
0x180024710  push    rbx
0x180024712  sub     rsp, 20h
0x180024716  mov     rcx, cs:?g_hCalaisShutdown@@3PEAXEA; hEvent
0x18002471d  xor     ebx, ebx
0x18002471f  test    rcx, rcx
0x180024722  jz      short loc_18002472A
0x180024724  call    cs:__imp_SetEvent
0x18002472a  cmp     cs:dword_18004BE68, ebx
0x180024730  jz      loc_1800249CE
0x180024736  mov     eax, 1
0x18002473b  lock xadd cs:dword_18004BF90, eax
0x180024743  inc     eax
0x180024745  movsxd  rcx, eax; lpTlsValue
0x180024748  call    ?CalRpcSetCallerId@@YAKPEAX@Z; CalRpcSetCallerId(void *)
0x18002474d  cmp     cs:dword_18004BE64, ebx
0x180024753  jz      short loc_1800247A8
0x180024755  mov     rdx, cs:qword_18004BD38; struct CCriticalSectionObject *
0x18002475c  lea     rcx, [rsp+28h+arg_10]; this
0x180024761  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x180024766  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18002476d  lea     rdx, ServiceStatus; lpServiceStatus
0x180024774  mov     cs:ServiceStatus.dwCurrentState, 3
0x18002477e  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x180024784  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x18002478e  call    cs:__imp_SetServiceStatus
0x180024794  test    eax, eax
0x180024796  jnz     short loc_18002479E
0x180024798  call    cs:__imp_GetLastError
0x18002479e  lea     rcx, [rsp+28h+arg_10]; this
0x1800247a3  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x1800247a8  mov     rcx, cs:WaitHandle; WaitHandle
0x1800247af  test    rcx, rcx
0x1800247b2  jz      short loc_1800247CB
0x1800247b4  call    cs:__imp_UnregisterWait
0x1800247ba  test    eax, eax
0x1800247bc  jnz     short loc_1800247C4
0x1800247be  call    cs:__imp_GetLastError
0x1800247c4  mov     cs:WaitHandle, rbx
0x1800247cb  call    ?AccessStartedEvent@@YAPEAXXZ; AccessStartedEvent(void)
0x1800247d0  test    rax, rax
0x1800247d3  jz      short loc_1800247DD
0x1800247d5  mov     rcx, rax; void *
0x1800247d8  call    ?_ResetEvent@@YAHPEAX@Z; _ResetEvent(void *)
0x1800247dd  call    ?AccessStoppedEvent@@YAPEAXXZ; AccessStoppedEvent(void)
0x1800247e2  test    rax, rax
0x1800247e5  jz      short loc_1800247EF
0x1800247e7  mov     rcx, rax; void *
0x1800247ea  call    ?_SetEvent@@YAHPEAX@Z; _SetEvent(void *)
0x1800247ef  call    ?AppTerminateDeviceRegistration@@YAXXZ; AppTerminateDeviceRegistration(void)
0x1800247f4  cmp     cs:dword_18004BE58, 1
0x1800247fb  jnz     short loc_180024802
0x1800247fd  call    ?CalaisPreStop@@YAXXZ; CalaisPreStop(void)
0x180024802  cmp     cs:dword_18004BE5C, 1
0x180024809  jnz     short loc_180024816
0x18002480b  call    ?CalRpcStop@@YAXXZ; CalRpcStop(void)
0x180024810  mov     cs:dword_18004BE5C, ebx
0x180024816  cmp     cs:dword_18004BE58, 1
0x18002481d  jnz     short loc_18002482A
0x18002481f  call    ?CalaisStop@@YAXXZ; CalaisStop(void)
0x180024824  mov     cs:dword_18004BE58, ebx
0x18002482a  cmp     cs:dword_18004BE60, 1
0x180024831  jnz     short loc_180024843
0x180024833  call    ?I_ServerCacheWriteDataToDisk@@YAKXZ; I_ServerCacheWriteDataToDisk(void)
0x180024838  call    ScCacheDeleteCache
0x18002483d  mov     cs:dword_18004BE60, ebx
0x180024843  mov     rcx, cs:hEvent; hObject
0x18002484a  test    rcx, rcx
0x18002484d  jz      short loc_18002486D
0x18002484f  call    cs:__imp_CloseHandle
0x180024855  mov     cs:hEvent, rbx
0x18002485c  test    eax, eax
0x18002485e  jnz     short loc_180024866
0x180024860  call    cs:__imp_GetLastError
0x180024866  mov     cs:hEvent, rbx
0x18002486d  cmp     cs:dword_18004BF0C, ebx
0x180024873  jz      short loc_1800248A8
0x180024875  lea     rcx, stru_18004BAD0; lpCriticalSection
0x18002487c  call    cs:__imp_EnterCriticalSection
0x180024882  mov     rcx, cs:hObject; hObject
0x180024889  test    rcx, rcx
0x18002488c  jz      short loc_18002489B
0x18002488e  call    cs:__imp_CloseHandle
0x180024894  mov     cs:hObject, rbx
0x18002489b  lea     rcx, stru_18004BAD0; lpCriticalSection
0x1800248a2  call    cs:__imp_LeaveCriticalSection
0x1800248a8  cmp     cs:dword_18004BF08, ebx
0x1800248ae  jz      short loc_1800248E3
0x1800248b0  lea     rcx, CriticalSection; lpCriticalSection
0x1800248b7  call    cs:__imp_EnterCriticalSection
0x1800248bd  mov     rcx, cs:qword_18004BEF8; hObject
0x1800248c4  test    rcx, rcx
0x1800248c7  jz      short loc_1800248D6
0x1800248c9  call    cs:__imp_CloseHandle
0x1800248cf  mov     cs:qword_18004BEF8, rbx
0x1800248d6  lea     rcx, CriticalSection; lpCriticalSection
0x1800248dd  call    cs:__imp_LeaveCriticalSection
0x1800248e3  cmp     cs:dword_18004BEF0, ebx
0x1800248e9  jz      short loc_18002491E
0x1800248eb  lea     rcx, stru_18004BAA8; lpCriticalSection
0x1800248f2  call    cs:__imp_EnterCriticalSection
0x1800248f8  mov     rcx, cs:qword_18004BF10; hObject
0x1800248ff  test    rcx, rcx
0x180024902  jz      short loc_180024911
0x180024904  call    cs:__imp_CloseHandle
0x18002490a  mov     cs:qword_18004BF10, rbx
0x180024911  lea     rcx, stru_18004BAA8; lpCriticalSection
0x180024918  call    cs:__imp_LeaveCriticalSection
0x18002491e  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180024924  cmp     ecx, 0FFFFFFFFh
0x180024927  jz      short loc_180024939
0x180024929  call    cs:__imp_TlsFree
0x18002492f  mov     cs:dwTlsIndex, 0FFFFFFFFh
0x180024939  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18002493f  cmp     ecx, 0FFFFFFFFh
0x180024942  jz      short loc_180024954
0x180024944  call    cs:__imp_TlsFree
0x18002494a  mov     cs:dword_18004B240, 0FFFFFFFFh
0x180024954  mov     rcx, cs:hEventLog; hEventLog
0x18002495b  mov     cs:dword_18004BE68, ebx
0x180024961  test    rcx, rcx
0x180024964  jz      short loc_18002496C
0x180024966  call    cs:__imp_DeregisterEventSource
0x18002496c  mov     rcx, cs:qword_18004BD38; this
0x180024973  mov     cs:hEventLog, rbx
0x18002497a  test    rcx, rcx
0x18002497d  jz      short loc_18002498B
0x18002497f  call    ??_GCCriticalSectionObject@@QEAAPEAXI@Z; CCriticalSectionObject::`scalar deleting destructor'(uint)
0x180024984  mov     cs:qword_18004BD38, rbx
0x18002498b  cmp     cs:dword_18004BE64, ebx
0x180024991  jz      short loc_1800249CE
0x180024993  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18002499a  lea     rdx, ServiceStatus; lpServiceStatus
0x1800249a1  mov     cs:dword_18004BE64, ebx
0x1800249a7  mov     cs:ServiceStatus.dwCurrentState, 1
0x1800249b1  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x1800249b7  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbx
0x1800249be  call    cs:__imp_SetServiceStatus
0x1800249c4  test    eax, eax
0x1800249c6  jnz     short loc_1800249CE
0x1800249c8  call    cs:__imp_GetLastError
0x1800249ce  add     rsp, 20h
0x1800249d2  pop     rbx
0x1800249d3  jmp     McGenEventUnregister_EventUnregister
```

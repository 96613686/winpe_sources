# AipStopCallback(void *,uchar)

- ea: `0x1800258a0`
- end: `0x180025a8e`
- name: `?AipStopCallback@@YAXPEAXE@Z`
- size: `494`
- prototype: `void __fastcall(HLOCAL hMem, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000d7a0`
- `0x18001a8e4`
- `0x1800257a4`
- `0x1800258a0`
- `0x180026790`
- `0x18003ba48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025919`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025919`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800258ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800258ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025983`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025946`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025946`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025a73`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800258fc`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800258fc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025a64`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025a64`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800258b2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800258b2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002599e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002599e`
- `ntdll!EtwEventUnregister` at `0x180025a0a`
- `ntdll!EtwEventUnregister` at `0x180025a2a`
- `ntdll!EtwEventUnregister` at `0x180025a0a`
- `ntdll!EtwEventUnregister` at `0x180025a2a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800259f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800259f2`

## pseudocode

```c
void __fastcall AipStopCallback(HANDLE *hMem, char a2)
{
  __int64 i; // rbx
  HLOCAL v5; // rcx
  _QWORD *v6; // rdx
  HLOCAL *v7; // rax

  UnregisterWait(*hMem);
  if ( !a2 )
  {
    CloseHandle(hMem[1]);
    AipDisableRpcInterface();
    if ( _InterlockedExchangeAdd(&g_ulProfileReferences, 0xFFFFFFFF) != 1 )
    {
      g_hssService = RegisterServiceCtrlHandlerExW(L"AppInfo", AipServiceCtrlHandler, 0);
      WaitForSingleObject(g_hProfileRefEvent, 0xFFFFFFFF);
    }
    AiRemoveAllPolicyClients();
    for ( i = 0; (unsigned int)i < g_dwSessions; i = (unsigned int)(i + 1) )
    {
      AipCleanupSessionEntry(i);
      LocalFree(*((HLOCAL *)g_SessionLocks + i));
    }
    LocalFree(g_SessionLocks);
    g_SessionLocks = 0;
    AiFreeDirectories();
    CloseHandle(g_hProfileRefEvent);
    g_hProfileRefEvent = 0;
    RtlAcquireSRWLockExclusive(&g_SessionIdListLock);
    while ( 1 )
    {
      v5 = g_SessionIdList;
      if ( g_SessionIdList == &g_SessionIdList )
        break;
      v6 = *(_QWORD **)g_SessionIdList;
      if ( *(HLOCAL *)(*(_QWORD *)g_SessionIdList + 8LL) != g_SessionIdList
        || (v7 = (HLOCAL *)*((_QWORD *)g_SessionIdList + 1), *v7 != g_SessionIdList) )
      {
        __fastfail(3u);
      }
      *v7 = v6;
      v6[1] = v7;
      LocalFree(v5);
    }
    RtlReleaseSRWLockExclusive(&g_SessionIdListLock);
    if ( g_EventRegHandleLua )
    {
      EtwEventUnregister();
      g_EventRegHandleLua = 0;
    }
    if ( g_EventRegHandleAppModelRuntime )
    {
      EtwEventUnregister();
      g_EventRegHandleAppModelRuntime = 0;
    }
    g_ssService.dwCheckPoint = 0;
    g_ssService.dwWaitHint = 0;
    g_ssService.dwCurrentState = 1;
    SetServiceStatus(g_hssService, &g_ssService);
  }
  LocalFree(hMem);
  WppCleanupUm();
}

```

## disassembly

```asm
0x1800258a0  mov     [rsp+arg_0], rbx
0x1800258a5  push    rdi
0x1800258a6  sub     rsp, 20h
0x1800258aa  mov     rdi, rcx
0x1800258ad  mov     bl, dl
0x1800258af  mov     rcx, [rcx]; WaitHandle
0x1800258b2  call    cs:__imp_UnregisterWait
0x1800258b9  nop     dword ptr [rax+rax+00h]
0x1800258be  test    bl, bl
0x1800258c0  jnz     loc_180025A70
0x1800258c6  mov     rcx, [rdi+8]; hObject
0x1800258ca  call    cs:__imp_CloseHandle
0x1800258d1  nop     dword ptr [rax+rax+00h]
0x1800258d6  call    ?AipDisableRpcInterface@@YAXXZ; AipDisableRpcInterface(void)
0x1800258db  or      eax, 0FFFFFFFFh
0x1800258de  lock xadd cs:?g_ulProfileReferences@@3JA, eax; long g_ulProfileReferences
0x1800258e6  cmp     eax, 1
0x1800258e9  jz      short loc_180025925
0x1800258eb  xor     r8d, r8d; lpContext
0x1800258ee  lea     rdx, ?AipServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800258f5  lea     rcx, ServiceName; "AppInfo"
0x1800258fc  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180025903  nop     dword ptr [rax+rax+00h]
0x180025908  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hHandle
0x18002590f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025912  mov     cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hssService
0x180025919  call    cs:__imp_WaitForSingleObject
0x180025920  nop     dword ptr [rax+rax+00h]
0x180025925  call    ?AiRemoveAllPolicyClients@@YAXXZ; AiRemoveAllPolicyClients(void)
0x18002592a  xor     ebx, ebx
0x18002592c  cmp     cs:?g_dwSessions@@3KA, ebx; ulong g_dwSessions
0x180025932  jbe     short loc_18002595C
0x180025934  mov     ecx, ebx; unsigned int
0x180025936  call    ?AipCleanupSessionEntry@@YAXK@Z; AipCleanupSessionEntry(ulong)
0x18002593b  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x180025942  mov     rcx, [rcx+rbx*8]; hMem
0x180025946  call    cs:__imp_LocalFree
0x18002594d  nop     dword ptr [rax+rax+00h]
0x180025952  inc     ebx
0x180025954  cmp     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18002595a  jb      short loc_180025934
0x18002595c  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; hMem
0x180025963  call    cs:__imp_LocalFree
0x18002596a  nop     dword ptr [rax+rax+00h]
0x18002596f  and     cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA, 0; _SESSION_LOCK * * g_SessionLocks
0x180025977  call    ?AiFreeDirectories@@YAXXZ; AiFreeDirectories(void)
0x18002597c  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hObject
0x180025983  call    cs:__imp_CloseHandle
0x18002598a  nop     dword ptr [rax+rax+00h]
0x18002598f  and     cs:?g_hProfileRefEvent@@3PEAXEA, 0; void * g_hProfileRefEvent
0x180025997  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x18002599e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800259a5  nop     dword ptr [rax+rax+00h]
0x1800259aa  mov     rcx, cs:?g_SessionIdList@@3U_LIST_ENTRY@@A; hMem
0x1800259b1  lea     rax, ?g_SessionIdList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SessionIdList
0x1800259b8  cmp     rcx, rax
0x1800259bb  jz      short loc_1800259EB
0x1800259bd  mov     rdx, [rcx]
0x1800259c0  cmp     [rdx+8], rcx
0x1800259c4  jnz     short loc_1800259E4
0x1800259c6  mov     rax, [rcx+8]
0x1800259ca  cmp     [rax], rcx
0x1800259cd  jnz     short loc_1800259E4
0x1800259cf  mov     [rax], rdx
0x1800259d2  mov     [rdx+8], rax
0x1800259d6  call    cs:__imp_LocalFree
0x1800259dd  nop     dword ptr [rax+rax+00h]
0x1800259e2  jmp     short loc_1800259AA
0x1800259e4  mov     ecx, 3
0x1800259e9  int     29h; Win8: RtlFailFast(ecx)
0x1800259eb  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x1800259f2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800259f9  nop     dword ptr [rax+rax+00h]
0x1800259fe  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x180025a05  test    rcx, rcx
0x180025a08  jz      short loc_180025A1E
0x180025a0a  call    cs:__imp_EtwEventUnregister
0x180025a11  nop     dword ptr [rax+rax+00h]
0x180025a16  and     cs:?g_EventRegHandleLua@@3_KA, 0; unsigned __int64 g_EventRegHandleLua
0x180025a1e  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x180025a25  test    rcx, rcx
0x180025a28  jz      short loc_180025A3E
0x180025a2a  call    cs:__imp_EtwEventUnregister
0x180025a31  nop     dword ptr [rax+rax+00h]
0x180025a36  and     cs:?g_EventRegHandleAppModelRuntime@@3_KA, 0; unsigned __int64 g_EventRegHandleAppModelRuntime
0x180025a3e  and     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x180025a45  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180025a4c  and     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwWaitHint, 0; _SERVICE_STATUS g_ssService ...
0x180025a53  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180025a5a  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_ssService ...
0x180025a64  call    cs:__imp_SetServiceStatus
0x180025a6b  nop     dword ptr [rax+rax+00h]
0x180025a70  mov     rcx, rdi; hMem
0x180025a73  call    cs:__imp_LocalFree
0x180025a7a  nop     dword ptr [rax+rax+00h]
0x180025a7f  mov     rbx, [rsp+28h+arg_0]
0x180025a84  add     rsp, 20h
0x180025a88  pop     rdi
0x180025a89  jmp     WppCleanupUm
```

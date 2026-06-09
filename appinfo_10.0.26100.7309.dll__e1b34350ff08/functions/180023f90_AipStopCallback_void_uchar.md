# AipStopCallback(void *,uchar)

- ea: `0x180023f90`
- end: `0x18002417e`
- name: `?AipStopCallback@@YAXPEAXE@Z`
- size: `494`
- prototype: `void __fastcall(HLOCAL hMem, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000d7a0`
- `0x18001acb4`
- `0x180023e94`
- `0x180023f90`
- `0x180024e9c`
- `0x18003cb04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024009`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024163`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180024154`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180024154`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180023fec`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180023fec`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180023fa2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180023fa2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002408e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002408e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800240e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800240e2`
- `ntdll!EtwEventUnregister` at `0x1800240fa`
- `ntdll!EtwEventUnregister` at `0x18002411a`
- `ntdll!EtwEventUnregister` at `0x1800240fa`
- `ntdll!EtwEventUnregister` at `0x18002411a`

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
0x180023f90  mov     [rsp+arg_0], rbx
0x180023f95  push    rdi
0x180023f96  sub     rsp, 20h
0x180023f9a  mov     rdi, rcx
0x180023f9d  mov     bl, dl
0x180023f9f  mov     rcx, [rcx]; WaitHandle
0x180023fa2  call    cs:__imp_UnregisterWait
0x180023fa9  nop     dword ptr [rax+rax+00h]
0x180023fae  test    bl, bl
0x180023fb0  jnz     loc_180024160
0x180023fb6  mov     rcx, [rdi+8]; hObject
0x180023fba  call    cs:__imp_CloseHandle
0x180023fc1  nop     dword ptr [rax+rax+00h]
0x180023fc6  call    ?AipDisableRpcInterface@@YAXXZ; AipDisableRpcInterface(void)
0x180023fcb  or      eax, 0FFFFFFFFh
0x180023fce  lock xadd cs:?g_ulProfileReferences@@3JA, eax; long g_ulProfileReferences
0x180023fd6  cmp     eax, 1
0x180023fd9  jz      short loc_180024015
0x180023fdb  xor     r8d, r8d; lpContext
0x180023fde  lea     rdx, ?AipServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180023fe5  lea     rcx, ServiceName; "AppInfo"
0x180023fec  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180023ff3  nop     dword ptr [rax+rax+00h]
0x180023ff8  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hHandle
0x180023fff  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180024002  mov     cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hssService
0x180024009  call    cs:__imp_WaitForSingleObject
0x180024010  nop     dword ptr [rax+rax+00h]
0x180024015  call    ?AiRemoveAllPolicyClients@@YAXXZ; AiRemoveAllPolicyClients(void)
0x18002401a  xor     ebx, ebx
0x18002401c  cmp     cs:?g_dwSessions@@3KA, ebx; ulong g_dwSessions
0x180024022  jbe     short loc_18002404C
0x180024024  mov     ecx, ebx; unsigned int
0x180024026  call    ?AipCleanupSessionEntry@@YAXK@Z; AipCleanupSessionEntry(ulong)
0x18002402b  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x180024032  mov     rcx, [rcx+rbx*8]; hMem
0x180024036  call    cs:__imp_LocalFree
0x18002403d  nop     dword ptr [rax+rax+00h]
0x180024042  inc     ebx
0x180024044  cmp     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18002404a  jb      short loc_180024024
0x18002404c  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; hMem
0x180024053  call    cs:__imp_LocalFree
0x18002405a  nop     dword ptr [rax+rax+00h]
0x18002405f  and     cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA, 0; _SESSION_LOCK * * g_SessionLocks
0x180024067  call    ?AiFreeDirectories@@YAXXZ; AiFreeDirectories(void)
0x18002406c  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hObject
0x180024073  call    cs:__imp_CloseHandle
0x18002407a  nop     dword ptr [rax+rax+00h]
0x18002407f  and     cs:?g_hProfileRefEvent@@3PEAXEA, 0; void * g_hProfileRefEvent
0x180024087  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x18002408e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024095  nop     dword ptr [rax+rax+00h]
0x18002409a  mov     rcx, cs:?g_SessionIdList@@3U_LIST_ENTRY@@A; hMem
0x1800240a1  lea     rax, ?g_SessionIdList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SessionIdList
0x1800240a8  cmp     rcx, rax
0x1800240ab  jz      short loc_1800240DB
0x1800240ad  mov     rdx, [rcx]
0x1800240b0  cmp     [rdx+8], rcx
0x1800240b4  jnz     short loc_1800240D4
0x1800240b6  mov     rax, [rcx+8]
0x1800240ba  cmp     [rax], rcx
0x1800240bd  jnz     short loc_1800240D4
0x1800240bf  mov     [rax], rdx
0x1800240c2  mov     [rdx+8], rax
0x1800240c6  call    cs:__imp_LocalFree
0x1800240cd  nop     dword ptr [rax+rax+00h]
0x1800240d2  jmp     short loc_18002409A
0x1800240d4  mov     ecx, 3
0x1800240d9  int     29h; Win8: RtlFailFast(ecx)
0x1800240db  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x1800240e2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800240e9  nop     dword ptr [rax+rax+00h]
0x1800240ee  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x1800240f5  test    rcx, rcx
0x1800240f8  jz      short loc_18002410E
0x1800240fa  call    cs:__imp_EtwEventUnregister
0x180024101  nop     dword ptr [rax+rax+00h]
0x180024106  and     cs:?g_EventRegHandleLua@@3_KA, 0; unsigned __int64 g_EventRegHandleLua
0x18002410e  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x180024115  test    rcx, rcx
0x180024118  jz      short loc_18002412E
0x18002411a  call    cs:__imp_EtwEventUnregister
0x180024121  nop     dword ptr [rax+rax+00h]
0x180024126  and     cs:?g_EventRegHandleAppModelRuntime@@3_KA, 0; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18002412e  and     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x180024135  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18002413c  and     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwWaitHint, 0; _SERVICE_STATUS g_ssService ...
0x180024143  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18002414a  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_ssService ...
0x180024154  call    cs:__imp_SetServiceStatus
0x18002415b  nop     dword ptr [rax+rax+00h]
0x180024160  mov     rcx, rdi; hMem
0x180024163  call    cs:__imp_LocalFree
0x18002416a  nop     dword ptr [rax+rax+00h]
0x18002416f  mov     rbx, [rsp+28h+arg_0]
0x180024174  add     rsp, 20h
0x180024178  pop     rdi
0x180024179  jmp     WppCleanupUm
```

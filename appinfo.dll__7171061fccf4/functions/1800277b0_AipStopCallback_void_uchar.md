# AipStopCallback(void *,uchar)

- ea: `0x1800277b0`
- end: `0x1800279c5`
- name: `?AipStopCallback@@YAXPEAXE@Z`
- size: `533`
- prototype: `void __fastcall(HANDLE *hMem, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000ce00`
- `0x18000d240`
- `0x18001cd20`
- `0x18001e3d0`
- `0x18001e46c`
- `0x1800276dc`
- `0x1800277b0`
- `0x18003f868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002781f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002781f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800278dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800278dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800278a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800278bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027926`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800278a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800278bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027926`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279a8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002799f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002799f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180027808`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180027808`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800277ca`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800277ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800278f4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800278f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002793c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002793c`
- `ntdll!EtwEventUnregister` at `0x18002794e`
- `ntdll!EtwEventUnregister` at `0x18002796b`
- `ntdll!EtwEventUnregister` at `0x18002794e`
- `ntdll!EtwEventUnregister` at `0x18002796b`

## pseudocode

```c
void __fastcall AipStopCallback(HANDLE *hMem, char a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  struct _SESSION_LOCK *v6; // rbp
  char *v7; // rsi
  char *j; // rdi
  __int64 v9; // rbx
  HLOCAL v10; // rcx
  _QWORD *v11; // rax
  HLOCAL *v12; // rdx
  struct _SESSION_LOCK *i; // [rsp+40h] [rbp+8h] BYREF

  UnregisterWait(*hMem);
  if ( !a2 )
  {
    CloseHandle(hMem[1]);
    AipDisableRpcInterface();
    if ( _InterlockedExchangeAdd(&g_ulProfileReferences, 0xFFFFFFFF) != 1 )
    {
      g_hssService = RegisterServiceCtrlHandlerExW(L"AppInfo", (LPHANDLER_FUNCTION_EX)AipServiceCtrlHandler, 0);
      WaitForSingleObject(g_hProfileRefEvent, 0xFFFFFFFF);
    }
    v4 = g_dwSessions;
    v5 = 1;
    for ( i = 0; v5 <= g_dwSessions; ++v5 )
    {
      if ( !(unsigned int)AipGetSessionLock(v5, 1, &i) )
      {
        v6 = i;
        v7 = (char *)i + 16;
        for ( j = (char *)*((_QWORD *)i + 2); j != v7; AipRemovePolicyClientCallback(*((PVOID *)j + 1), 1) )
          j = *(char **)j;
        AipReleaseSessionLock(v6);
        i = 0;
      }
      v4 = g_dwSessions;
    }
    v9 = 0;
    if ( v4 )
    {
      do
      {
        AipCleanupSessionEntry(v9);
        LocalFree(*((HLOCAL *)g_SessionLocks + v9));
        v9 = (unsigned int)(v9 + 1);
      }
      while ( (unsigned int)v9 < g_dwSessions );
    }
    LocalFree(g_SessionLocks);
    g_SessionLocks = 0;
    AiFreeDirectories();
    CloseHandle(g_hProfileRefEvent);
    g_hProfileRefEvent = 0;
    RtlAcquireSRWLockExclusive(&g_SessionIdListLock);
    while ( 1 )
    {
      v10 = g_SessionIdList;
      if ( g_SessionIdList == &g_SessionIdList )
        break;
      v11 = *(_QWORD **)g_SessionIdList;
      if ( *(HLOCAL *)(*(_QWORD *)g_SessionIdList + 8LL) != g_SessionIdList
        || (v12 = (HLOCAL *)*((_QWORD *)g_SessionIdList + 1), *v12 != g_SessionIdList) )
      {
        __fastfail(3u);
      }
      *v12 = v11;
      v11[1] = v12;
      LocalFree(v10);
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
    g_ssService.dwCurrentState = 1;
    *(_QWORD *)&g_ssService.dwCheckPoint = 0;
    SetServiceStatus(g_hssService, &g_ssService);
  }
  LocalFree(hMem);
  WppCleanupUm();
}

```

## disassembly

```asm
0x1800277b0  mov     [rsp+arg_8], rbx
0x1800277b5  mov     [rsp+arg_10], rbp
0x1800277ba  push    rsi
0x1800277bb  push    rdi
0x1800277bc  push    r14
0x1800277be  sub     rsp, 20h
0x1800277c2  mov     r14, rcx
0x1800277c5  mov     bl, dl
0x1800277c7  mov     rcx, [rcx]; WaitHandle
0x1800277ca  call    cs:__imp_UnregisterWait
0x1800277d0  test    bl, bl
0x1800277d2  jnz     loc_1800279A5
0x1800277d8  mov     rcx, [r14+8]; hObject
0x1800277dc  call    cs:__imp_CloseHandle
0x1800277e2  call    ?AipDisableRpcInterface@@YAXXZ; AipDisableRpcInterface(void)
0x1800277e7  or      eax, 0FFFFFFFFh
0x1800277ea  lock xadd cs:?g_ulProfileReferences@@3JA, eax; long g_ulProfileReferences
0x1800277f2  cmp     eax, 1
0x1800277f5  jz      short loc_180027825
0x1800277f7  xor     r8d, r8d; lpContext
0x1800277fa  lea     rdx, ?AipServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180027801  lea     rcx, ServiceName; "AppInfo"
0x180027808  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002780e  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hHandle
0x180027815  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180027818  mov     cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hssService
0x18002781f  call    cs:__imp_WaitForSingleObject
0x180027825  mov     eax, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18002782b  mov     ebx, 1
0x180027830  mov     [rsp+38h+arg_0], 0
0x180027839  cmp     eax, ebx
0x18002783b  jb      short loc_180027890
0x18002783d  lea     r8, [rsp+38h+arg_0]; struct _SESSION_LOCK **
0x180027842  mov     edx, 1; int
0x180027847  mov     ecx, ebx; unsigned int
0x180027849  call    ?AipGetSessionLock@@YAKKHPEAPEAU_SESSION_LOCK@@@Z; AipGetSessionLock(ulong,int,_SESSION_LOCK * *)
0x18002784e  test    eax, eax
0x180027850  jnz     short loc_180027884
0x180027852  mov     rbp, [rsp+38h+arg_0]
0x180027857  lea     rsi, [rbp+10h]
0x18002785b  mov     rdi, [rsi]
0x18002785e  jmp     short loc_18002786E
0x180027860  mov     rdi, [rdi]
0x180027863  mov     dl, 1; BOOLEAN
0x180027865  mov     rcx, [rdi+8]; PVOID
0x180027869  call    ?AipRemovePolicyClientCallback@@YAXPEAXE@Z; AipRemovePolicyClientCallback(void *,uchar)
0x18002786e  cmp     rdi, rsi
0x180027871  jnz     short loc_180027860
0x180027873  mov     rcx, rbp; struct _SESSION_LOCK *
0x180027876  call    ?AipReleaseSessionLock@@YAXPEAU_SESSION_LOCK@@@Z; AipReleaseSessionLock(_SESSION_LOCK *)
0x18002787b  mov     [rsp+38h+arg_0], 0
0x180027884  mov     eax, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x18002788a  inc     ebx
0x18002788c  cmp     ebx, eax
0x18002788e  jbe     short loc_18002783D
0x180027890  xor     ebx, ebx
0x180027892  test    eax, eax
0x180027894  jz      short loc_1800278B8
0x180027896  mov     ecx, ebx; unsigned int
0x180027898  call    ?AipCleanupSessionEntry@@YAXK@Z; AipCleanupSessionEntry(ulong)
0x18002789d  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; _SESSION_LOCK * * g_SessionLocks
0x1800278a4  mov     rcx, [rcx+rbx*8]; hMem
0x1800278a8  call    cs:__imp_LocalFree
0x1800278ae  inc     ebx
0x1800278b0  cmp     ebx, cs:?g_dwSessions@@3KA; ulong g_dwSessions
0x1800278b6  jb      short loc_180027896
0x1800278b8  mov     rcx, cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA; hMem
0x1800278bf  call    cs:__imp_LocalFree
0x1800278c5  mov     cs:?g_SessionLocks@@3PEAPEAU_SESSION_LOCK@@EA, 0; _SESSION_LOCK * * g_SessionLocks
0x1800278d0  call    ?AiFreeDirectories@@YAXXZ; AiFreeDirectories(void)
0x1800278d5  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hObject
0x1800278dc  call    cs:__imp_CloseHandle
0x1800278e2  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x1800278e9  mov     cs:?g_hProfileRefEvent@@3PEAXEA, 0; void * g_hProfileRefEvent
0x1800278f4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800278fa  mov     rcx, cs:?g_SessionIdList@@3U_LIST_ENTRY@@A; hMem
0x180027901  lea     rax, ?g_SessionIdList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SessionIdList
0x180027908  cmp     rcx, rax
0x18002790b  jz      short loc_180027935
0x18002790d  mov     rax, [rcx]
0x180027910  cmp     [rax+8], rcx
0x180027914  jnz     short loc_18002792E
0x180027916  mov     rdx, [rcx+8]
0x18002791a  cmp     [rdx], rcx
0x18002791d  jnz     short loc_18002792E
0x18002791f  mov     [rdx], rax
0x180027922  mov     [rax+8], rdx
0x180027926  call    cs:__imp_LocalFree
0x18002792c  jmp     short loc_1800278FA
0x18002792e  mov     ecx, 3
0x180027933  int     29h; Win8: RtlFailFast(ecx)
0x180027935  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x18002793c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180027942  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x180027949  test    rcx, rcx
0x18002794c  jz      short loc_18002795F
0x18002794e  call    cs:__imp_EtwEventUnregister
0x180027954  mov     cs:?g_EventRegHandleLua@@3_KA, 0; unsigned __int64 g_EventRegHandleLua
0x18002795f  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x180027966  test    rcx, rcx
0x180027969  jz      short loc_18002797C
0x18002796b  call    cs:__imp_EtwEventUnregister
0x180027971  mov     cs:?g_EventRegHandleAppModelRuntime@@3_KA, 0; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18002797c  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180027983  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18002798a  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_ssService ...
0x180027994  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x18002799f  call    cs:__imp_SetServiceStatus
0x1800279a5  mov     rcx, r14; hMem
0x1800279a8  call    cs:__imp_LocalFree
0x1800279ae  mov     rbx, [rsp+38h+arg_8]
0x1800279b3  mov     rbp, [rsp+38h+arg_10]
0x1800279b8  add     rsp, 20h
0x1800279bc  pop     r14
0x1800279be  pop     rdi
0x1800279bf  pop     rsi
0x1800279c0  jmp     WppCleanupUm
```

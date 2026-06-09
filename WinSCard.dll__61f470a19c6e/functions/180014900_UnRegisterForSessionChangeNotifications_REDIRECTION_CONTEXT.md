# UnRegisterForSessionChangeNotifications(_REDIRECTION_CONTEXT *)

- ea: `0x180014900`
- end: `0x180014968`
- name: `?UnRegisterForSessionChangeNotifications@@YAHPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007940`

## callees

- `0x180014900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014909`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014909`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014957`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180014928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180014937`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180014928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180014937`
- `ntdll!RtlDllShutdownInProgress` at `0x180014915`
- `ntdll!RtlDllShutdownInProgress` at `0x180014915`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x180014946`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x180014946`

## pseudocode

```c
__int64 __fastcall UnRegisterForSessionChangeNotifications(LPCRITICAL_SECTION lpCriticalSection)
{
  EnterCriticalSection(lpCriticalSection);
  if ( !LOBYTE(lpCriticalSection[1].DebugInfo) && !RtlDllShutdownInProgress() )
  {
    SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].OwningThread, 0, 0);
    SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].SpinCount, 0, 0);
  }
  if ( lpCriticalSection[3].DebugInfo )
  {
    WinStationUnRegisterNotificationEvent();
    lpCriticalSection[3].DebugInfo = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return 1;
}

```

## disassembly

```asm
0x180014900  push    rbx
0x180014902  sub     rsp, 20h
0x180014906  mov     rbx, rcx
0x180014909  call    cs:__imp_EnterCriticalSection
0x18001490f  cmp     byte ptr [rbx+28h], 0
0x180014913  jnz     short loc_18001493D
0x180014915  call    cs:__imp_RtlDllShutdownInProgress
0x18001491b  test    al, al
0x18001491d  jnz     short loc_18001493D
0x18001491f  mov     rcx, [rbx+60h]; pwa
0x180014923  xor     r8d, r8d; pftTimeout
0x180014926  xor     edx, edx; h
0x180014928  call    cs:__imp_SetThreadpoolWait
0x18001492e  mov     rcx, [rbx+70h]; pwa
0x180014932  xor     r8d, r8d; pftTimeout
0x180014935  xor     edx, edx; h
0x180014937  call    cs:__imp_SetThreadpoolWait
0x18001493d  mov     rcx, [rbx+78h]
0x180014941  test    rcx, rcx
0x180014944  jz      short loc_180014954
0x180014946  call    cs:__imp_WinStationUnRegisterNotificationEvent
0x18001494c  mov     qword ptr [rbx+78h], 0
0x180014954  mov     rcx, rbx; lpCriticalSection
0x180014957  call    cs:__imp_LeaveCriticalSection
0x18001495d  mov     eax, 1
0x180014962  add     rsp, 20h
0x180014966  pop     rbx
0x180014967  retn
```

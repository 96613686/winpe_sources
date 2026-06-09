# ReaderMonitorStopThread

- ea: `0x18001c970`
- end: `0x18001ca01`
- name: `ReaderMonitorStopThread`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cb00`

## callees

- `0x18001c970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c9aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c9aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c9d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c9d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c9b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001c9e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001c9e9`
- `WinSCard!SCardCancel` at `0x18001c9c8`
- `WinSCard!SCardCancel` at `0x18001c9c8`

## pseudocode

```c
__int64 __fastcall ReaderMonitorStopThread(__int64 a1)
{
  DWORD LastError; // edi
  void *v4; // rcx
  SCARDCONTEXT v5; // rcx
  struct _TP_CLEANUP_GROUP *v6; // rcx

  if ( !*(_DWORD *)(a1 + 216) )
    return 1359;
  LastError = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v4 = *(void **)(a1 + 240);
  if ( v4 && !SetEvent(v4) )
    LastError = GetLastError();
  v5 = *(_QWORD *)(a1 + 232);
  if ( v5 )
    SCardCancel(v5);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v6 = *(struct _TP_CLEANUP_GROUP **)(a1 + 208);
  if ( v6 )
    CloseThreadpoolCleanupGroupMembers(v6, 0, 0);
  return LastError;
}

```

## disassembly

```asm
0x18001c970  mov     [rsp+arg_0], rbx
0x18001c975  mov     [rsp+arg_8], rsi
0x18001c97a  push    rdi
0x18001c97b  sub     rsp, 20h
0x18001c97f  cmp     dword ptr [rcx+0D8h], 0
0x18001c986  mov     rbx, rcx
0x18001c989  jnz     short loc_18001C992
0x18001c98b  mov     eax, 54Fh
0x18001c990  jmp     short loc_18001C9F1
0x18001c992  add     rcx, 30h ; '0'; lpCriticalSection
0x18001c996  xor     edi, edi
0x18001c998  call    cs:__imp_EnterCriticalSection
0x18001c99e  mov     rcx, [rbx+0F0h]; hEvent
0x18001c9a5  test    rcx, rcx
0x18001c9a8  jz      short loc_18001C9BC
0x18001c9aa  call    cs:__imp_SetEvent
0x18001c9b0  test    eax, eax
0x18001c9b2  jnz     short loc_18001C9BC
0x18001c9b4  call    cs:__imp_GetLastError
0x18001c9ba  mov     edi, eax
0x18001c9bc  mov     rcx, [rbx+0E8h]; hContext
0x18001c9c3  test    rcx, rcx
0x18001c9c6  jz      short loc_18001C9CE
0x18001c9c8  call    cs:__imp_SCardCancel
0x18001c9ce  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001c9d2  call    cs:__imp_LeaveCriticalSection
0x18001c9d8  mov     rcx, [rbx+0D0h]; ptpcg
0x18001c9df  test    rcx, rcx
0x18001c9e2  jz      short loc_18001C9EF
0x18001c9e4  xor     r8d, r8d; pvCleanupContext
0x18001c9e7  xor     edx, edx; fCancelPendingCallbacks
0x18001c9e9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001c9ef  mov     eax, edi
0x18001c9f1  mov     rbx, [rsp+28h+arg_0]
0x18001c9f6  mov     rsi, [rsp+28h+arg_8]
0x18001c9fb  add     rsp, 20h
0x18001c9ff  pop     rdi
0x18001ca00  retn
```

# LocalCorePerformanceTelemetryCollector::~LocalCorePerformanceTelemetryCollector(void)

- ea: `0x18000a95c`
- end: `0x18000a9c7`
- name: `??1LocalCorePerformanceTelemetryCollector@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(LocalCorePerformanceTelemetryCollector *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a850`
- `0x18000c9d8`
- `0x18000ec0c`

## callees

- `0x18000a95c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a977`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a98a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a98a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a9a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a998`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a998`

## pseudocode

```c
void __fastcall LocalCorePerformanceTelemetryCollector::~LocalCorePerformanceTelemetryCollector(
        LocalCorePerformanceTelemetryCollector *this)
{
  struct _TP_TIMER *v1; // rsi
  DWORD LastError; // ebx

  v1 = (struct _TP_TIMER *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000a95c  mov     [rsp+arg_0], rbx
0x18000a961  mov     [rsp+arg_8], rsi
0x18000a966  push    rdi
0x18000a967  sub     rsp, 20h
0x18000a96b  mov     rsi, [rcx+8]
0x18000a96f  mov     rdi, rcx
0x18000a972  test    rsi, rsi
0x18000a975  jz      short loc_18000A9AF
0x18000a977  call    cs:__imp_GetLastError
0x18000a97d  xor     r9d, r9d; msWindowLength
0x18000a980  xor     r8d, r8d; msPeriod
0x18000a983  xor     edx, edx; pftDueTime
0x18000a985  mov     rcx, rsi; pti
0x18000a988  mov     ebx, eax
0x18000a98a  call    cs:__imp_SetThreadpoolTimer
0x18000a990  mov     edx, 1; fCancelPendingCallbacks
0x18000a995  mov     rcx, rsi; pti
0x18000a998  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a99e  mov     rcx, rsi; pti
0x18000a9a1  call    cs:__imp_CloseThreadpoolTimer
0x18000a9a7  mov     ecx, ebx; dwErrCode
0x18000a9a9  call    cs:__imp_SetLastError
0x18000a9af  mov     rbx, [rsp+28h+arg_0]
0x18000a9b4  mov     rsi, [rsp+28h+arg_8]
0x18000a9b9  mov     qword ptr [rdi+8], 0
0x18000a9c1  add     rsp, 20h
0x18000a9c5  pop     rdi
0x18000a9c6  retn
```

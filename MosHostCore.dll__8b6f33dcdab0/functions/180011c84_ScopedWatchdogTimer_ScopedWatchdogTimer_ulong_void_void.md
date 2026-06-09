# ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))

- ea: `0x180011c84`
- end: `0x180011d83`
- name: `??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z`
- size: `255`
- prototype: `ScopedWatchdogTimer *__fastcall(PVOID Context, __int64, void (*)(void))`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x18001d760`

## callees

- `0x180011c84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011cd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c9b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011cbb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011cbb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180011d38`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180011d38`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180011d6f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180011d6f`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180011d13`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180011d13`

## pseudocode

```c
ScopedWatchdogTimer *__fastcall ScopedWatchdogTimer::ScopedWatchdogTimer(PVOID Context, __int64 a2, void (*a3)(void))
{
  HANDLE EventW; // rax
  signed int v5; // eax
  signed int LastError; // eax

  *(_QWORD *)Context = ScopedWatchdogHandlers::MosHostServiceUninitialize_CrashOnTimerExpired;
  *((_DWORD *)Context + 2) = GetCurrentThreadId();
  *((_DWORD *)Context + 3) = 300000;
  *((_QWORD *)Context + 2) = 0;
  *((_QWORD *)Context + 3) = 0;
  if ( !IsDebuggerPresent() )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)Context + 3) = EventW;
    if ( EventW )
    {
      if ( !RegisterWaitForSingleObject(
              (PHANDLE)Context + 2,
              EventW,
              ScopedWatchdogTimer::WaitCallback,
              Context,
              *((_DWORD *)Context + 3),
              0) )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          LastError = -2143748092;
        }
        ZTraceReportIgnore(LastError, "ScopedWatchdogTimer::ScopedWatchdogTimer", 49, Context);
      }
    }
    else
    {
      v5 = GetLastError();
      if ( v5 )
      {
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
      }
      else
      {
        v5 = -2143748092;
      }
      ZTraceReportOrigination(v5, "ScopedWatchdogTimer::ScopedWatchdogTimer", 40, Context);
    }
  }
  return (ScopedWatchdogTimer *)Context;
}

```

## disassembly

```asm
0x180011c84  mov     [rsp+arg_0], rbx
0x180011c89  push    rdi
0x180011c8a  sub     rsp, 30h
0x180011c8e  lea     rax, ?MosHostServiceUninitialize_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; ScopedWatchdogHandlers::MosHostServiceUninitialize_CrashOnTimerExpired(void)
0x180011c95  mov     rbx, rcx
0x180011c98  mov     [rcx], rax
0x180011c9b  call    cs:__imp_GetCurrentThreadId
0x180011ca1  mov     [rbx+8], eax
0x180011ca4  mov     dword ptr [rbx+0Ch], 493E0h
0x180011cab  mov     qword ptr [rbx+10h], 0
0x180011cb3  mov     qword ptr [rbx+18h], 0
0x180011cbb  call    cs:__imp_IsDebuggerPresent
0x180011cc1  test    eax, eax
0x180011cc3  jnz     loc_180011D75
0x180011cc9  xor     r9d, r9d; lpName
0x180011ccc  lea     edx, [rax+1]; bManualReset
0x180011ccf  xor     r8d, r8d; bInitialState
0x180011cd2  xor     ecx, ecx; lpEventAttributes
0x180011cd4  call    cs:__imp_CreateEventW
0x180011cda  mov     [rbx+18h], rax
0x180011cde  mov     rdx, rax; hObject
0x180011ce1  test    rax, rax
0x180011ce4  jnz     short loc_180011D1B
0x180011ce6  call    cs:__imp_GetLastError
0x180011cec  test    eax, eax
0x180011cee  jz      short loc_180011CFC
0x180011cf0  jle     short loc_180011D01
0x180011cf2  movzx   eax, ax
0x180011cf5  or      eax, 80070000h
0x180011cfa  jmp     short loc_180011D01
0x180011cfc  mov     eax, 80390004h
0x180011d01  mov     r9, rbx
0x180011d04  lea     rdx, aScopedwatchdog; "ScopedWatchdogTimer::ScopedWatchdogTime"...
0x180011d0b  mov     r8d, 28h ; '('
0x180011d11  mov     ecx, eax
0x180011d13  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180011d19  jmp     short loc_180011D75
0x180011d1b  mov     eax, [rbx+0Ch]
0x180011d1e  lea     r8, ?WaitCallback@ScopedWatchdogTimer@@SAXPEAXE@Z; Callback
0x180011d25  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180011d2d  lea     rcx, [rbx+10h]; phNewWaitObject
0x180011d31  mov     r9, rbx; Context
0x180011d34  mov     [rsp+38h+dwMilliseconds], eax; dwMilliseconds
0x180011d38  call    cs:__imp_RegisterWaitForSingleObject
0x180011d3e  test    eax, eax
0x180011d40  jnz     short loc_180011D75
0x180011d42  call    cs:__imp_GetLastError
0x180011d48  test    eax, eax
0x180011d4a  jz      short loc_180011D58
0x180011d4c  jle     short loc_180011D5D
0x180011d4e  movzx   eax, ax
0x180011d51  or      eax, 80070000h
0x180011d56  jmp     short loc_180011D5D
0x180011d58  mov     eax, 80390004h
0x180011d5d  mov     r9, rbx
0x180011d60  lea     rdx, aScopedwatchdog; "ScopedWatchdogTimer::ScopedWatchdogTime"...
0x180011d67  mov     r8d, 31h ; '1'
0x180011d6d  mov     ecx, eax
0x180011d6f  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180011d75  mov     rax, rbx
0x180011d78  mov     rbx, [rsp+38h+arg_0]
0x180011d7d  add     rsp, 30h
0x180011d81  pop     rdi
0x180011d82  retn
```

# TelemetryOperationWatchdog::WatchdogCallback(void)

- ea: `0x180034240`
- end: `0x1800343eb`
- name: `?WatchdogCallback@TelemetryOperationWatchdog@@MEAAXXZ`
- size: `427`
- prototype: `void __fastcall(TelemetryOperationWatchdog *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180023aac`
- `0x180026530`
- `0x18002c580`
- `0x180034240`
- `0x18003fab0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003430b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003430b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034377`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003436c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003436c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003429f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18003429f`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800342f4`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800342f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800343ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800343ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180034285`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180034285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800343a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800343a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180034267`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180034267`

## pseudocode

```c
void __fastcall TelemetryOperationWatchdog::WatchdogCallback(TelemetryOperationWatchdog *this)
{
  ULONGLONG v2; // rbx
  HANDLE v3; // rsi
  signed int LastError; // eax
  bool v5; // sf
  int v6; // ebp
  signed int v7; // eax
  bool v8; // sf
  int Dump; // eax
  signed int v10; // eax
  bool v11; // sf
  int v12; // ebx
  DWORD TickCount; // eax
  const unsigned __int16 *v14; // rdx

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 11, 1, 0)
    && !IsDebuggerPresent()
    && TelemetryOperationWatchdog::_IsShellReady() )
  {
    v2 = *((unsigned int *)this + 12);
    if ( GetTickCount64() > v2 )
    {
      v3 = OpenThread(0x1FFFFFu, 0, *((_DWORD *)this + 10));
      if ( !v3 )
      {
        LastError = GetLastError();
        v5 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v5 = LastError < 0;
        }
        if ( v5 )
          Log_HREvent_7(
            (unsigned int)LastError,
            0,
            "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h",
            111);
        return;
      }
      (*(void (__fastcall **)(TelemetryOperationWatchdog *))(*(_QWORD *)this + 16LL))(this);
      if ( SuspendThread(v3) == -1 )
      {
        v6 = 0;
        v7 = GetLastError();
        v8 = v7 < 0;
        if ( v7 > 0 )
        {
          v7 = (unsigned __int16)v7 | 0x80070000;
          v8 = v7 < 0;
        }
        if ( v8 )
          Log_HREvent_7((unsigned int)v7, 0, "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h", 121);
      }
      else
      {
        v6 = 1;
      }
      Dump = TelemetryOperationWatchdog::CreateDump(this);
      if ( Dump < 0 )
        Log_HREvent_7((unsigned int)Dump, 0, "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h", 129);
      (*(void (__fastcall **)(TelemetryOperationWatchdog *))(*(_QWORD *)this + 24LL))(this);
      if ( v6 && ResumeThread(v3) == -1 )
      {
        v10 = GetLastError();
        v11 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v11 = v10 < 0;
        }
        if ( v11 )
          Log_HREvent_7((unsigned int)v10, 0, "onecoreuap\\private\\net\\inc\\phone\\TelemetryOperationWatchdog.h", 125);
      }
      CloseHandle(v3);
    }
  }
  v12 = *((_DWORD *)this + 3);
  TickCount = GetTickCount();
  v14 = &byte_18009A505;
  if ( *((_QWORD *)this + 4) )
    v14 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  EventWriteOperationTimedOut(*((unsigned int *)this + 2), v14, *((unsigned int *)this + 6), TickCount - v12);
  *((_DWORD *)this + 11) = 1;
}

```

## disassembly

```asm
0x180034240  mov     [rsp+arg_8], rbx
0x180034245  mov     [rsp+arg_10], rbp
0x18003424a  push    rsi
0x18003424b  push    rdi
0x18003424c  push    r14
0x18003424e  sub     rsp, 40h
0x180034252  xor     eax, eax
0x180034254  mov     rdi, rcx
0x180034257  lea     r14d, [rax+1]
0x18003425b  lock cmpxchg [rcx+2Ch], r14d
0x180034261  jnz     loc_1800343A9
0x180034267  call    cs:__imp_IsDebuggerPresent
0x18003426d  test    eax, eax
0x18003426f  jnz     loc_1800343A9
0x180034275  call    ?_IsShellReady@TelemetryOperationWatchdog@@KA_NXZ; TelemetryOperationWatchdog::_IsShellReady(void)
0x18003427a  test    al, al
0x18003427c  jz      loc_1800343A9
0x180034282  mov     ebx, [rdi+30h]
0x180034285  call    cs:__imp_GetTickCount64
0x18003428b  cmp     rax, rbx
0x18003428e  jbe     loc_1800343A9
0x180034294  mov     r8d, [rdi+28h]; dwThreadId
0x180034298  xor     edx, edx; bInheritHandle
0x18003429a  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18003429f  call    cs:__imp_OpenThread
0x1800342a5  mov     rsi, rax
0x1800342a8  test    rax, rax
0x1800342ab  jnz     short loc_1800342E2
0x1800342ad  call    cs:__imp_GetLastError
0x1800342b3  test    eax, eax
0x1800342b5  jle     short loc_1800342C1
0x1800342b7  movzx   eax, ax
0x1800342ba  or      eax, 80070000h
0x1800342bf  test    eax, eax
0x1800342c1  jns     loc_1800343D8
0x1800342c7  mov     r9d, 6Fh ; 'o'
0x1800342cd  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x1800342d4  xor     edx, edx
0x1800342d6  mov     ecx, eax
0x1800342d8  call    Log_HREvent_7
0x1800342dd  jmp     loc_1800343D8
0x1800342e2  mov     rax, [rdi]
0x1800342e5  mov     rcx, rdi
0x1800342e8  mov     rax, [rax+10h]
0x1800342ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342f1  mov     rcx, rsi; hThread
0x1800342f4  call    cs:__imp_SuspendThread
0x1800342fa  mov     ebx, 80070000h
0x1800342ff  cmp     eax, 0FFFFFFFFh
0x180034302  jz      short loc_180034309
0x180034304  mov     ebp, r14d
0x180034307  jmp     short loc_180034334
0x180034309  xor     ebp, ebp
0x18003430b  call    cs:__imp_GetLastError
0x180034311  test    eax, eax
0x180034313  jle     short loc_18003431C
0x180034315  movzx   eax, ax
0x180034318  or      eax, ebx
0x18003431a  test    eax, eax
0x18003431c  jns     short loc_180034334
0x18003431e  mov     r9d, 79h ; 'y'
0x180034324  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x18003432b  xor     edx, edx
0x18003432d  mov     ecx, eax
0x18003432f  call    Log_HREvent_7
0x180034334  mov     rcx, rdi; this
0x180034337  call    ?CreateDump@TelemetryOperationWatchdog@@IEAAJXZ; TelemetryOperationWatchdog::CreateDump(void)
0x18003433c  test    eax, eax
0x18003433e  jns     short loc_180034356
0x180034340  mov     r9d, 81h
0x180034346  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x18003434d  xor     edx, edx
0x18003434f  mov     ecx, eax
0x180034351  call    Log_HREvent_7
0x180034356  mov     rax, [rdi]
0x180034359  mov     rcx, rdi
0x18003435c  mov     rax, [rax+18h]
0x180034360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034365  test    ebp, ebp
0x180034367  jz      short loc_1800343A0
0x180034369  mov     rcx, rsi; hThread
0x18003436c  call    cs:__imp_ResumeThread
0x180034372  cmp     eax, 0FFFFFFFFh
0x180034375  jnz     short loc_1800343A0
0x180034377  call    cs:__imp_GetLastError
0x18003437d  test    eax, eax
0x18003437f  jle     short loc_180034388
0x180034381  movzx   eax, ax
0x180034384  or      eax, ebx
0x180034386  test    eax, eax
0x180034388  jns     short loc_1800343A0
0x18003438a  mov     r9d, 7Dh ; '}'
0x180034390  lea     r8, aOnecoreuapPriv_1; "onecoreuap\\private\\net\\inc\\phone\\T"...
0x180034397  xor     edx, edx
0x180034399  mov     ecx, eax
0x18003439b  call    Log_HREvent_7
0x1800343a0  mov     rcx, rsi; hObject
0x1800343a3  call    cs:__imp_CloseHandle
0x1800343a9  mov     ebx, [rdi+0Ch]
0x1800343ac  call    cs:__imp_GetTickCount
0x1800343b2  mov     r8d, [rdi+18h]
0x1800343b6  lea     rdx, byte_18009A505
0x1800343bd  mov     ecx, [rdi+8]
0x1800343c0  sub     eax, ebx
0x1800343c2  cmp     qword ptr [rdi+20h], 0
0x1800343c7  mov     r9d, eax
0x1800343ca  cmovnz  rdx, [rdi+20h]
0x1800343cf  call    EventWriteOperationTimedOut
0x1800343d4  mov     [rdi+2Ch], r14d
0x1800343d8  mov     rbx, [rsp+58h+arg_8]
0x1800343dd  mov     rbp, [rsp+58h+arg_10]
0x1800343e2  add     rsp, 40h
0x1800343e6  pop     r14
0x1800343e8  pop     rdi
0x1800343e9  pop     rsi
0x1800343ea  retn
```

# OperationWatchdog::End(void)

- ea: `0x180025ae4`
- end: `0x180025b7b`
- name: `?End@OperationWatchdog@@QEAAXXZ`
- size: `151`
- prototype: `void __fastcall(OperationWatchdog *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001de50`
- `0x18001f514`
- `0x180020ff0`
- `0x180024c00`
- `0x18003723c`
- `0x18006278c`
- `0x180062c5c`
- `0x180062ee0`
- `0x180063320`
- `0x180064b20`

## callees

- `0x180025ae4`
- `0x18002658c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025aff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025b46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025b46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025b12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025b12`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025b29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025b29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025b20`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025b20`

## pseudocode

```c
void __fastcall OperationWatchdog::End(OperationWatchdog *this)
{
  struct _TP_TIMER *v1; // rsi
  DWORD LastError; // ebx
  DWORD TickCount; // eax
  const unsigned __int16 *v5; // rdx

  v1 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
    SetLastError(LastError);
    *((_QWORD *)this + 2) = 0;
    if ( *((_DWORD *)this + 11) )
    {
      TickCount = GetTickCount();
      v5 = &byte_18009A505;
      if ( *((_QWORD *)this + 4) )
        v5 = (const unsigned __int16 *)*((_QWORD *)this + 4);
      EventWriteOperationTimedOutComplete(*((unsigned int *)this + 2), v5, TickCount - *((_DWORD *)this + 3));
    }
  }
}

```

## disassembly

```asm
0x180025ae4  mov     [rsp+arg_0], rbx
0x180025ae9  mov     [rsp+arg_8], rsi
0x180025aee  push    rdi
0x180025aef  sub     rsp, 20h
0x180025af3  mov     rsi, [rcx+10h]
0x180025af7  mov     rdi, rcx
0x180025afa  test    rsi, rsi
0x180025afd  jz      short loc_180025B6B
0x180025aff  call    cs:__imp_GetLastError
0x180025b05  xor     r9d, r9d; msWindowLength
0x180025b08  xor     r8d, r8d; msPeriod
0x180025b0b  xor     edx, edx; pftDueTime
0x180025b0d  mov     rcx, rsi; pti
0x180025b10  mov     ebx, eax
0x180025b12  call    cs:__imp_SetThreadpoolTimer
0x180025b18  mov     edx, 1; fCancelPendingCallbacks
0x180025b1d  mov     rcx, rsi; pti
0x180025b20  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025b26  mov     rcx, rsi; pti
0x180025b29  call    cs:__imp_CloseThreadpoolTimer
0x180025b2f  mov     ecx, ebx; dwErrCode
0x180025b31  call    cs:__imp_SetLastError
0x180025b37  mov     qword ptr [rdi+10h], 0
0x180025b3f  mov     eax, [rdi+2Ch]
0x180025b42  test    eax, eax
0x180025b44  jz      short loc_180025B6B
0x180025b46  call    cs:__imp_GetTickCount
0x180025b4c  mov     ecx, [rdi+8]
0x180025b4f  lea     rdx, byte_18009A505
0x180025b56  sub     eax, [rdi+0Ch]
0x180025b59  cmp     qword ptr [rdi+20h], 0
0x180025b5e  mov     r8d, eax
0x180025b61  cmovnz  rdx, [rdi+20h]
0x180025b66  call    EventWriteOperationTimedOutComplete
0x180025b6b  mov     rbx, [rsp+28h+arg_0]
0x180025b70  mov     rsi, [rsp+28h+arg_8]
0x180025b75  add     rsp, 20h
0x180025b79  pop     rdi
0x180025b7a  retn
```

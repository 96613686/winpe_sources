# ConnectedStorage::ThreadPoolTimer::Cancel(void)

- ea: `0x180013f48`
- end: `0x180013f86`
- name: `?Cancel@ThreadPoolTimer@ConnectedStorage@@QEAAXXZ`
- size: `62`
- prototype: `void __fastcall(ConnectedStorage::ThreadPoolTimer *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180013e1c`
- `0x180013f8c`
- `0x18006cab8`
- `0x18006cfa4`
- `0x18006d4ec`
- `0x18006d74c`
- `0x18006d9b0`
- `0x18006dbf0`

## callees

- `0x180013f48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013f63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013f63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013f71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013f71`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013f7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013f7a`

## pseudocode

```c
void __fastcall ConnectedStorage::ThreadPoolTimer::Cancel(ConnectedStorage::ThreadPoolTimer *this)
{
  struct _TP_TIMER *v1; // rbx

  if ( *(_QWORD *)this )
  {
    v1 = (struct _TP_TIMER *)_InterlockedExchange64((volatile __int64 *)this, 0);
    SetThreadpoolTimer(v1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
  }
}

```

## disassembly

```asm
0x180013f48  push    rbx
0x180013f4a  sub     rsp, 20h
0x180013f4e  xor     ebx, ebx
0x180013f50  cmp     [rcx], rbx
0x180013f53  jz      short loc_180013F80
0x180013f55  xchg    rbx, [rcx]
0x180013f58  mov     rcx, rbx; pti
0x180013f5b  xor     r9d, r9d; msWindowLength
0x180013f5e  xor     r8d, r8d; msPeriod
0x180013f61  xor     edx, edx; pftDueTime
0x180013f63  call    cs:__imp_SetThreadpoolTimer
0x180013f69  mov     edx, 1; fCancelPendingCallbacks
0x180013f6e  mov     rcx, rbx; pti
0x180013f71  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013f77  mov     rcx, rbx; pti
0x180013f7a  call    cs:__imp_CloseThreadpoolTimer
0x180013f80  add     rsp, 20h
0x180013f84  pop     rbx
0x180013f85  retn
```

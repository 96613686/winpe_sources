# ProcessRefCount::ScheduleExitTimer(void)

- ea: `0x18000a8f0`
- end: `0x18000a921`
- name: `?ScheduleExitTimer@ProcessRefCount@@AEAAXXZ`
- size: `49`
- prototype: `void __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800012a0`
- `0x18000b520`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x18000a916`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x18000a916`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a910`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a910`

## pseudocode

```c
void __fastcall ProcessRefCount::ScheduleExitTimer(ProcessRefCount *this)
{
  struct _TP_TIMER *v1; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v1 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
  pftDueTime = (struct _FILETIME)-50000000LL;
  SetThreadpoolTimer(v1, &pftDueTime, 0, 0);
  CoFreeUnusedLibraries();
}

```

## disassembly

```asm
0x18000a8f0  sub     rsp, 28h
0x18000a8f4  lock inc dword ptr [rcx+8]
0x18000a8f8  mov     rcx, [rcx+20h]; pti
0x18000a8fc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000a901  xor     r9d, r9d; msWindowLength
0x18000a904  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a90d  xor     r8d, r8d; msPeriod
0x18000a910  call    cs:__imp_SetThreadpoolTimer
0x18000a916  call    cs:__imp_CoFreeUnusedLibraries
0x18000a91c  add     rsp, 28h
0x18000a920  retn
```

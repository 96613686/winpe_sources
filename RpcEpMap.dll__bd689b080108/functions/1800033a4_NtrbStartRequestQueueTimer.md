# NtrbStartRequestQueueTimer

- ea: `0x1800033a4`
- end: `0x1800033e4`
- name: `NtrbStartRequestQueueTimer`
- size: `64`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003288`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033d9`

## pseudocode

```c
void __fastcall NtrbStartRequestQueueTimer(__int64 a1)
{
  struct _TP_TIMER *v1; // rcx
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = 0;
  _InterlockedOr64((volatile signed __int64 *)(a1 + 48), 2u);
  v1 = *(struct _TP_TIMER **)(a1 + 24);
  pftDueTime = (_FILETIME)(-10000LL * NtrbRequestTimeoutLength);
  SetThreadpoolTimer(v1, &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x1800033a4  sub     rsp, 28h
0x1800033a8  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x1800033b1  lock or qword ptr [rcx+30h], 2
0x1800033b7  movsxd  rax, cs:NtrbRequestTimeoutLength
0x1800033be  xor     r9d, r9d; msWindowLength
0x1800033c1  mov     rcx, [rcx+18h]; pti
0x1800033c5  xor     r8d, r8d; msPeriod
0x1800033c8  imul    rdx, rax, 0FFFFFFFFFFFFD8F0h
0x1800033cf  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rdx
0x1800033d4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800033d9  call    cs:__imp_SetThreadpoolTimer
0x1800033df  add     rsp, 28h
0x1800033e3  retn
```

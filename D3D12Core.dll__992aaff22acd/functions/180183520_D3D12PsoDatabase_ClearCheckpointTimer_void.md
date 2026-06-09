# D3D12PsoDatabase::ClearCheckpointTimer(void)

- ea: `0x180183520`
- end: `0x180183573`
- name: `?ClearCheckpointTimer@D3D12PsoDatabase@@AEAAXXZ`
- size: `83`
- prototype: `void __fastcall(D3D12PsoDatabase *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1801818c8`
- `0x180188c64`
- `0x180188da8`

## callees

- `0x180183520`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18018353d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18018353d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18018355c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18018355c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18018354f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18018354f`

## pseudocode

```c
void __fastcall D3D12PsoDatabase::ClearCheckpointTimer(D3D12PsoDatabase *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 37);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 37), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 37));
    *((_QWORD *)this + 37) = 0;
  }
}

```

## disassembly

```asm
0x180183520  push    rbx
0x180183522  sub     rsp, 20h
0x180183526  mov     rbx, rcx
0x180183529  mov     rcx, [rcx+128h]; pti
0x180183530  test    rcx, rcx
0x180183533  jz      short loc_18018356D
0x180183535  xor     r9d, r9d; msWindowLength
0x180183538  xor     r8d, r8d; msPeriod
0x18018353b  xor     edx, edx; pftDueTime
0x18018353d  call    cs:__imp_SetThreadpoolTimer
0x180183543  mov     rcx, [rbx+128h]; pti
0x18018354a  mov     edx, 1; fCancelPendingCallbacks
0x18018354f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180183555  mov     rcx, [rbx+128h]; pti
0x18018355c  call    cs:__imp_CloseThreadpoolTimer
0x180183562  mov     qword ptr [rbx+128h], 0
0x18018356d  add     rsp, 20h
0x180183571  pop     rbx
0x180183572  retn
```

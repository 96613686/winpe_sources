# CancelTimerCallbacksAndDeleteTimer

- ea: `0x14015672c`
- end: `0x14015678d`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140083c00`
- `0x140156ed8`

## callees

- `0x140017adc`
- `0x14015672c`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140156769`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140156769`
- `KERNEL32!CloseThreadpoolTimer` at `0x140156776`
- `KERNEL32!CloseThreadpoolTimer` at `0x140156776`
- `KERNEL32!SetThreadpoolTimer` at `0x140156757`
- `KERNEL32!SetThreadpoolTimer` at `0x140156757`

## pseudocode

```c
void __fastcall CancelTimerCallbacksAndDeleteTimer(PTP_TIMER *a1)
{
  if ( a1[43] )
  {
    if ( !CommonUtil::IsDuringProcessShutdown((CommonUtil *)a1) )
    {
      SetThreadpoolTimer(a1[43], 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(a1[43], 1);
      CloseThreadpoolTimer(a1[43]);
    }
    a1[43] = 0;
  }
}

```

## disassembly

```asm
0x14015672c  push    rbx
0x14015672e  sub     rsp, 20h
0x140156732  cmp     qword ptr [rcx+158h], 0
0x14015673a  mov     rbx, rcx
0x14015673d  jz      short loc_140156787
0x14015673f  call    ?IsDuringProcessShutdown@CommonUtil@@YA_NXZ; CommonUtil::IsDuringProcessShutdown(void)
0x140156744  test    al, al
0x140156746  jnz     short loc_14015677C
0x140156748  mov     rcx, [rbx+158h]; pti
0x14015674f  xor     r9d, r9d; msWindowLength
0x140156752  xor     r8d, r8d; msPeriod
0x140156755  xor     edx, edx; pftDueTime
0x140156757  call    cs:__imp_SetThreadpoolTimer
0x14015675d  mov     rcx, [rbx+158h]; pti
0x140156764  mov     edx, 1; fCancelPendingCallbacks
0x140156769  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14015676f  mov     rcx, [rbx+158h]; pti
0x140156776  call    cs:__imp_CloseThreadpoolTimer
0x14015677c  mov     qword ptr [rbx+158h], 0
0x140156787  add     rsp, 20h
0x14015678b  pop     rbx
0x14015678c  retn
```

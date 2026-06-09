# WUComTimeout::ComTimeout::~ComTimeout(void)

- ea: `0x14004484c`
- end: `0x140044896`
- name: `??1ComTimeout@WUComTimeout@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(PTP_TIMER *this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14003e598`
- `0x14003eb78`
- `0x14003ed44`
- `0x14003eeec`
- `0x14004fe98`
- `0x14004ff16`

## callees

- `0x14004484c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14004487c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14004487c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140044873`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140044873`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140044865`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140044865`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x14004488a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x14004488a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WUComTimeout::ComTimeout::~ComTimeout(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    CloseThreadpoolTimer(*this);
  }
  if ( *((_BYTE *)this + 12) )
    CoDisableCallCancellation(0);
}

```

## disassembly

```asm
0x14004484c  push    rbx
0x14004484e  sub     rsp, 20h
0x140044852  mov     rbx, rcx
0x140044855  mov     rcx, [rcx]; pti
0x140044858  test    rcx, rcx
0x14004485b  jz      short loc_140044882
0x14004485d  xor     r9d, r9d; msWindowLength
0x140044860  xor     r8d, r8d; msPeriod
0x140044863  xor     edx, edx; pftDueTime
0x140044865  call    cs:__imp_SetThreadpoolTimer
0x14004486b  mov     rcx, [rbx]; pti
0x14004486e  mov     edx, 1; fCancelPendingCallbacks
0x140044873  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140044879  mov     rcx, [rbx]; pti
0x14004487c  call    cs:__imp_CloseThreadpoolTimer
0x140044882  cmp     byte ptr [rbx+0Ch], 0
0x140044886  jz      short loc_140044890
0x140044888  xor     ecx, ecx; pReserved
0x14004488a  call    cs:__imp_CoDisableCallCancellation
0x140044890  add     rsp, 20h
0x140044894  pop     rbx
0x140044895  retn
```

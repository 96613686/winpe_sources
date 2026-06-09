# PowerProfileMgr::~PowerProfileMgr(void)

- ea: `0x180090314`
- end: `0x18009037f`
- name: `??1PowerProfileMgr@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(PowerProfileMgr *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800679d8`
- `0x1800684e0`

## callees

- `0x180090314`
- `0x180090680`
- `0x180096944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180090378`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009034a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009034a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009033b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009033b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180090354`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180090354`

## pseudocode

```c
void __fastcall PowerProfileMgr::~PowerProfileMgr(PowerProfileMgr *this)
{
  struct _TP_TIMER *v2; // rcx
  void *v3; // rcx

  if ( *((_BYTE *)this + 56) )
    PowerProfileMgr::StopPerfBoost((LPCRITICAL_SECTION)this, 0);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 8), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
    PubSebUnregisterRpc(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180090314  push    rbx
0x180090316  sub     rsp, 20h
0x18009031a  mov     rbx, rcx
0x18009031d  cmp     byte ptr [rcx+38h], 0
0x180090321  jz      short loc_18009032A
0x180090323  xor     edx, edx; bool
0x180090325  call    ?StopPerfBoost@PowerProfileMgr@@AEAAJ_N@Z; PowerProfileMgr::StopPerfBoost(bool)
0x18009032a  mov     rcx, [rbx+40h]; pti
0x18009032e  test    rcx, rcx
0x180090331  jz      short loc_180090362
0x180090333  xor     r9d, r9d; msWindowLength
0x180090336  xor     r8d, r8d; msPeriod
0x180090339  xor     edx, edx; pftDueTime
0x18009033b  call    cs:__imp_SetThreadpoolTimer
0x180090341  mov     edx, 1; fCancelPendingCallbacks
0x180090346  mov     rcx, [rbx+40h]; pti
0x18009034a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180090350  mov     rcx, [rbx+40h]; pti
0x180090354  call    cs:__imp_CloseThreadpoolTimer
0x18009035a  mov     qword ptr [rbx+40h], 0
0x180090362  mov     rcx, [rbx+30h]; P
0x180090366  test    rcx, rcx
0x180090369  jz      short loc_180090370
0x18009036b  call    PubSebUnregisterRpc
0x180090370  mov     rcx, rbx
0x180090373  add     rsp, 20h
0x180090377  pop     rbx
0x180090378  jmp     cs:__imp_DeleteCriticalSection
```

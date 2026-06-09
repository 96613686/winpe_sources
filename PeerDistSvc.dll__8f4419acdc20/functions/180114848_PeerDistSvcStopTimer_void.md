# PeerDistSvcStopTimer(void)

- ea: `0x180114848`
- end: `0x1801148cc`
- name: `?PeerDistSvcStopTimer@@YAXXZ`
- size: `132`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800069d4`

## callees

- `0x180004510`
- `0x180004874`
- `0x180114848`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1801148c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801148b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801148b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18011488d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18011488d`

## pseudocode

```c
void PeerDistSvcStopTimer(void)
{
  struct _TP_TIMER *v0; // rbx
  _BYTE v1[40]; // [rsp+20h] [rbp-28h] BYREF

  InCritSec::InCritSec((InCritSec *)v1, (struct CritSec *)&qword_1801A72D0, 1);
  byte_1801A76D0 = 1;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    v0 = pti;
    pti = 0;
    InCritSec::~InCritSec((InCritSec *)v1);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
  }
  else
  {
    InCritSec::~InCritSec((InCritSec *)v1);
  }
}

```

## disassembly

```asm
0x180114848  push    rbx
0x18011484a  sub     rsp, 40h
0x18011484e  mov     r8b, 1; bool
0x180114851  lea     rdx, qword_1801A72D0; struct CritSec *
0x180114858  lea     rcx, [rsp+48h+var_28]; this
0x18011485d  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180114862  mov     rcx, cs:pti; pti
0x180114869  mov     cs:byte_1801A76D0, 1
0x180114870  test    rcx, rcx
0x180114873  jnz     short loc_180114885
0x180114875  lea     rcx, [rsp+48h+var_28]; this
0x18011487a  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18011487f  add     rsp, 40h
0x180114883  pop     rbx
0x180114884  retn
0x180114885  xor     r9d, r9d; msWindowLength
0x180114888  xor     r8d, r8d; msPeriod
0x18011488b  xor     edx, edx; pftDueTime
0x18011488d  call    cs:__imp_SetThreadpoolTimer
0x180114893  mov     rbx, cs:pti
0x18011489a  lea     rcx, [rsp+48h+var_28]; this
0x18011489f  mov     cs:pti, 0
0x1801148aa  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1801148af  mov     edx, 1; fCancelPendingCallbacks
0x1801148b4  mov     rcx, rbx; pti
0x1801148b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801148bd  mov     rcx, rbx
0x1801148c0  add     rsp, 40h
0x1801148c4  pop     rbx
0x1801148c5  jmp     cs:__imp_CloseThreadpoolTimer
```

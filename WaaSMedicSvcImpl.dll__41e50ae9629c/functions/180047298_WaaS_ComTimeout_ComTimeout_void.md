# WaaS::ComTimeout::~ComTimeout(void)

- ea: `0x180047298`
- end: `0x1800472e2`
- name: `??1ComTimeout@WaaS@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(WaaS::ComTimeout *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006cc57`

## callees

- `0x180047298`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800472d6`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800472d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800472c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800472c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800472b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800472b1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800472bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800472bf`

## pseudocode

```c
void __fastcall WaaS::ComTimeout::~ComTimeout(PTP_TIMER *this)
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
0x180047298  push    rbx
0x18004729a  sub     rsp, 20h
0x18004729e  mov     rbx, rcx
0x1800472a1  mov     rcx, [rcx]; pti
0x1800472a4  test    rcx, rcx
0x1800472a7  jz      short loc_1800472CE
0x1800472a9  xor     r9d, r9d; msWindowLength
0x1800472ac  xor     r8d, r8d; msPeriod
0x1800472af  xor     edx, edx; pftDueTime
0x1800472b1  call    cs:__imp_SetThreadpoolTimer
0x1800472b7  mov     rcx, [rbx]; pti
0x1800472ba  mov     edx, 1; fCancelPendingCallbacks
0x1800472bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800472c5  mov     rcx, [rbx]; pti
0x1800472c8  call    cs:__imp_CloseThreadpoolTimer
0x1800472ce  cmp     byte ptr [rbx+0Ch], 0
0x1800472d2  jz      short loc_1800472DC
0x1800472d4  xor     ecx, ecx; pReserved
0x1800472d6  call    cs:__imp_CoDisableCallCancellation
0x1800472dc  add     rsp, 20h
0x1800472e0  pop     rbx
0x1800472e1  retn
```

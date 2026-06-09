# Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(void)

- ea: `0x140004aec`
- end: `0x140004b7c`
- name: `??1FlightDataRecorder@Session@Speech@Windows@@MEAA@XZ`
- size: `144`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140004d50`
- `0x140004d90`
- `0x140015708`
- `0x140015da0`
- `0x14001bd30`
- `0x14001c23e`

## callees

- `0x140004aec`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004b33`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004b33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004b10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004b10`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004b29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004b29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004b1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004b1f`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &Windows::Speech::Session::FlightDataRecorder::`vftable';
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 12));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x140004aec  push    rbx
0x140004aee  sub     rsp, 20h
0x140004af2  mov     rbx, rcx
0x140004af5  lea     rax, ??_7FlightDataRecorder@Session@Speech@Windows@@6B@; const Windows::Speech::Session::FlightDataRecorder::`vftable'
0x140004afc  mov     [rcx], rax
0x140004aff  mov     rcx, [rcx+60h]; pti
0x140004b03  test    rcx, rcx
0x140004b06  jz      short loc_140004B2F
0x140004b08  xor     r9d, r9d; msWindowLength
0x140004b0b  xor     r8d, r8d; msPeriod
0x140004b0e  xor     edx, edx; pftDueTime
0x140004b10  call    cs:__imp_SetThreadpoolTimer
0x140004b16  mov     edx, 1; fCancelPendingCallbacks
0x140004b1b  mov     rcx, [rbx+60h]; pti
0x140004b1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004b25  mov     rcx, [rbx+60h]; pti
0x140004b29  call    cs:__imp_CloseThreadpoolTimer
0x140004b2f  lea     rcx, [rbx+70h]; lpCriticalSection
0x140004b33  call    cs:__imp_DeleteCriticalSection
0x140004b39  nop
0x140004b3a  mov     rcx, [rbx+50h]
0x140004b3e  test    rcx, rcx
0x140004b41  jz      short loc_140004B58
0x140004b43  mov     qword ptr [rbx+50h], 0
0x140004b4b  mov     rax, [rcx]
0x140004b4e  mov     rax, [rax+10h]
0x140004b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b57  nop
0x140004b58  mov     rcx, [rbx+48h]
0x140004b5c  test    rcx, rcx
0x140004b5f  jz      short loc_140004B76
0x140004b61  mov     qword ptr [rbx+48h], 0
0x140004b69  mov     rax, [rcx]
0x140004b6c  mov     rax, [rax+10h]
0x140004b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b75  nop
0x140004b76  add     rsp, 20h
0x140004b7a  pop     rbx
0x140004b7b  retn
```

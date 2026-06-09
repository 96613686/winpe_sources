# Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(void)

- ea: `0x140008064`
- end: `0x1400080c8`
- name: `??1FlightDataRecorder@Session@Speech@Windows@@MEAA@XZ`
- size: `100`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400081b0`
- `0x140008870`
- `0x14002f550`

## callees

- `0x140008064`
- `0x14000c32c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400080ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400080ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008097`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008097`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400080a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400080a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008088`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008088`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::~FlightDataRecorder(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  struct _TP_TIMER *v2; // rcx

  *(_QWORD *)this = &Windows::Speech::Session::FlightDataRecorder::`vftable';
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 12));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 72);
}

```

## disassembly

```asm
0x140008064  push    rbx
0x140008066  sub     rsp, 20h
0x14000806a  lea     rax, ??_7FlightDataRecorder@Session@Speech@Windows@@6B@; const Windows::Speech::Session::FlightDataRecorder::`vftable'
0x140008071  mov     rbx, rcx
0x140008074  mov     [rcx], rax
0x140008077  mov     rcx, [rcx+60h]; pti
0x14000807b  test    rcx, rcx
0x14000807e  jz      short loc_1400080A7
0x140008080  xor     r9d, r9d; msWindowLength
0x140008083  xor     r8d, r8d; msPeriod
0x140008086  xor     edx, edx; pftDueTime
0x140008088  call    cs:__imp_SetThreadpoolTimer
0x14000808e  mov     rcx, [rbx+60h]; pti
0x140008092  mov     edx, 1; fCancelPendingCallbacks
0x140008097  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000809d  mov     rcx, [rbx+60h]; pti
0x1400080a1  call    cs:__imp_CloseThreadpoolTimer
0x1400080a7  lea     rcx, [rbx+70h]; lpCriticalSection
0x1400080ab  call    cs:__imp_DeleteCriticalSection
0x1400080b1  lea     rcx, [rbx+50h]
0x1400080b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400080ba  lea     rcx, [rbx+48h]
0x1400080be  add     rsp, 20h
0x1400080c2  pop     rbx
0x1400080c3  jmp     ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
```

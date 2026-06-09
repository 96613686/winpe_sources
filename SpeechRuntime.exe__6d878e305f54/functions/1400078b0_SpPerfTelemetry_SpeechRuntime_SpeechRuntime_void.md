# SpPerfTelemetry::SpeechRuntime::SpeechRuntime(void)

- ea: `0x1400078b0`
- end: `0x140007a14`
- name: `??0SpeechRuntime@SpPerfTelemetry@@QEAA@XZ`
- size: `356`
- prototype: `__int64 __fastcall(SpPerfTelemetry::SpeechRuntime *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002810`

## callees

- `0x140007358`
- `0x1400078b0`
- `0x14000aa18`
- `0x14000dd88`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000792f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000792f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400079d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400079d5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000793c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000793c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall SpPerfTelemetry::SpeechRuntime::SpeechRuntime(SpPerfTelemetry::SpeechRuntime *this)
{
  g_telemetry = &Windows::Speech::Session::FlightDataRecorder::`vftable';
  qword_14004D6B8 = 0x1000000;
  dword_14004D6C0 = -2147286526;
  qword_14004D6E0 = 0;
  xmmword_14004D6E8 = 0;
  qword_14004D6F8 = 0;
  qword_14004D700 = 0;
  dword_14004D708 = 0;
  qword_14004D710 = 0;
  InitializeCriticalSection(&stru_14004D720);
  QueryPerformanceFrequency(&Frequency);
  Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId((Windows::Speech::Session::FlightDataRecorder *)&g_telemetry);
  g_telemetry = &SpPerfTelemetry::SpeechRuntime::`vftable';
  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&qword_14004D748);
  qword_14004D748 = &SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::`vftable';
  (*(void (__fastcall **)(void *))(g_telemetry + 64LL))(&g_telemetry);
  (*(void (__fastcall **)(void *))(g_telemetry + 72LL))(&g_telemetry);
  (*(void (__fastcall **)(void *))(g_telemetry + 80LL))(&g_telemetry);
  (*(void (__fastcall **)(void *))(g_telemetry + 88LL))(&g_telemetry);
  if ( HIBYTE(qword_14004D6B8) )
  {
    qword_14004D710 = (__int64)CreateThreadpoolTimer(
                                 Windows::Speech::Session::EndSessionDueToNoActivityTimerCallback,
                                 &g_telemetry,
                                 0);
    if ( qword_14004D710 && (_BYTE)qword_14004D6B8 )
      Windows::Speech::Session::FlightDataRecorder::ResetInactivityTimer((Windows::Speech::Session::FlightDataRecorder *)&g_telemetry);
  }
  else
  {
    qword_14004D710 = 0;
  }
  return &g_telemetry;
}

```

## disassembly

```asm
0x1400078b0  mov     rax, rsp
0x1400078b3  mov     [rax+10h], rbx
0x1400078b7  mov     [rax+18h], rsi
0x1400078bb  mov     [rax+8], rcx
0x1400078bf  push    rdi
0x1400078c0  sub     rsp, 20h
0x1400078c4  lea     rsi, ?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x1400078cb  mov     [rax+8], rsi
0x1400078cf  lea     rbx, __ImageBase
0x1400078d6  lea     rax, rva ??_7FlightDataRecorder@Session@Speech@Windows@@6B@[rbx]; const Windows::Speech::Session::FlightDataRecorder::`vftable' ...
0x1400078dd  mov     cs:?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A, rax; SpPerfTelemetry::SpeechRuntime g_telemetry
0x1400078e4  xor     edi, edi
0x1400078e6  mov     cs:qword_14004D6B8, 1000000h
0x1400078f1  mov     cs:dword_14004D6C0, 80030202h
0x1400078fb  mov     cs:qword_14004D6E0, rdi
0x140007902  xorps   xmm0, xmm0
0x140007905  movdqu  cs:xmmword_14004D6E8, xmm0
0x14000790d  mov     cs:qword_14004D6F8, rdi
0x140007914  mov     cs:qword_14004D700, rdi
0x14000791b  mov     cs:dword_14004D708, edi
0x140007921  mov     cs:qword_14004D710, rdi
0x140007928  lea     rcx, stru_14004D720; lpCriticalSection
0x14000792f  call    cs:__imp_InitializeCriticalSection
0x140007935  lea     rcx, Frequency; lpFrequency
0x14000793c  call    cs:__imp_QueryPerformanceFrequency
0x140007942  mov     rcx, rsi; this
0x140007945  call    ?CreateNewSessionId@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ; Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(void)
0x14000794a  nop
0x14000794b  lea     rax, rva ??_7SpeechRuntime@SpPerfTelemetry@@6B@[rbx]; const SpPerfTelemetry::SpeechRuntime::`vftable' ...
0x140007952  mov     cs:?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A, rax; SpPerfTelemetry::SpeechRuntime g_telemetry
0x140007959  lea     rcx, qword_14004D748; struct wil::details::IFailureCallback *
0x140007960  call    ??0?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140007965  lea     rax, ??_7SpeechRuntime@ActivityContainer@0SpPerfTelemetry@@6B@; const SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::`vftable'
0x14000796c  mov     cs:qword_14004D748, rax
0x140007973  mov     rax, cs:?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x14000797a  mov     rcx, rsi
0x14000797d  mov     rax, [rax+40h]
0x140007981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007986  mov     rax, cs:?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x14000798d  mov     rcx, rsi
0x140007990  mov     rax, [rax+48h]
0x140007994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007999  mov     rax, cs:?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x1400079a0  mov     rcx, rsi
0x1400079a3  mov     rax, [rax+50h]
0x1400079a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079ac  mov     rax, cs:?g_telemetry@@3VSpeechRuntime@SpPerfTelemetry@@A; SpPerfTelemetry::SpeechRuntime g_telemetry
0x1400079b3  mov     rcx, rsi
0x1400079b6  mov     rax, [rax+58h]
0x1400079ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079bf  cmp     byte ptr cs:qword_14004D6B8+7, dil
0x1400079c6  jz      short loc_1400079FA
0x1400079c8  xor     r8d, r8d; pcbe
0x1400079cb  mov     rdx, rsi; pv
0x1400079ce  lea     rcx, Windows__Speech__Session__EndSessionDueToNoActivityTimerCallback; pfnti
0x1400079d5  call    cs:__imp_CreateThreadpoolTimer
0x1400079db  mov     cs:qword_14004D710, rax
0x1400079e2  test    rax, rax
0x1400079e5  jz      short loc_140007A01
0x1400079e7  cmp     byte ptr cs:qword_14004D6B8, dil
0x1400079ee  jz      short loc_140007A01
0x1400079f0  mov     rcx, rsi; this
0x1400079f3  call    ?ResetInactivityTimer@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ; Windows::Speech::Session::FlightDataRecorder::ResetInactivityTimer(void)
0x1400079f8  jmp     short loc_140007A01
0x1400079fa  mov     cs:qword_14004D710, rdi
0x140007a01  mov     rax, rsi
0x140007a04  mov     rbx, [rsp+28h+arg_8]
0x140007a09  mov     rsi, [rsp+28h+arg_10]
0x140007a0e  add     rsp, 20h
0x140007a12  pop     rdi
0x140007a13  retn
```

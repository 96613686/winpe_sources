# SPTelemetry::ModelUpdate::ModelUpdate(void)

- ea: `0x140004748`
- end: `0x14000483b`
- name: `??0ModelUpdate@SPTelemetry@@QEAA@XZ`
- size: `243`
- prototype: `SPTelemetry::ModelUpdate *__fastcall(SPTelemetry::ModelUpdate *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140009698`

## callees

- `0x140004748`
- `0x140005bfc`
- `0x140006f90`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140004794`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140004794`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400047ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400047ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004821`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004821`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000479e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x14000479e`

## pseudocode

```c
SPTelemetry::ModelUpdate *__fastcall SPTelemetry::ModelUpdate::ModelUpdate(SPTelemetry::ModelUpdate *this)
{
  int v2; // edx
  unsigned __int64 v3; // r8
  struct _TP_TIMER *ThreadpoolTimer; // rax

  *(_QWORD *)this = &Windows::Speech::Session::FlightDataRecorder::`vftable';
  *((_QWORD *)this + 1) = 0x1000000;
  *((_DWORD *)this + 4) = -2147286526;
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 12) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  QueryPerformanceFrequency((LARGE_INTEGER *)this + 3);
  Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(this);
  *(_QWORD *)this = &SPTelemetry::ModelUpdate::`vftable';
  Windows::Speech::Session::FlightDataRecorder::StopActivity(this, v2, v3);
  (*(void (__fastcall **)(SPTelemetry::ModelUpdate *))(*(_QWORD *)this + 72LL))(this);
  (*(void (__fastcall **)(SPTelemetry::ModelUpdate *))(*(_QWORD *)this + 80LL))(this);
  (*(void (__fastcall **)(SPTelemetry::ModelUpdate *))(*(_QWORD *)this + 88LL))(this);
  if ( *((_BYTE *)this + 15) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(Windows::Speech::Session::EndSessionDueToNoActivityTimerCallback, this, 0);
    *((_QWORD *)this + 12) = ThreadpoolTimer;
    if ( ThreadpoolTimer && *((_BYTE *)this + 8) )
      SetThreadpoolTimer(ThreadpoolTimer, (PFILETIME)this + 13, 0, 0);
  }
  else
  {
    *((_QWORD *)this + 12) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x140004748  mov     [rsp+arg_8], rbx
0x14000474d  mov     [rsp+arg_0], rcx
0x140004752  push    rdi
0x140004753  sub     rsp, 20h
0x140004757  mov     rbx, rcx
0x14000475a  lea     rax, ??_7FlightDataRecorder@Session@Speech@Windows@@6B@; const Windows::Speech::Session::FlightDataRecorder::`vftable'
0x140004761  mov     [rcx], rax
0x140004764  xor     edi, edi
0x140004766  mov     qword ptr [rcx+8], 1000000h
0x14000476e  mov     dword ptr [rcx+10h], 80030202h
0x140004775  mov     [rcx+30h], rdi
0x140004779  xorps   xmm0, xmm0
0x14000477c  movdqu  xmmword ptr [rcx+38h], xmm0
0x140004781  mov     [rcx+48h], rdi
0x140004785  mov     [rcx+50h], rdi
0x140004789  mov     [rcx+58h], edi
0x14000478c  mov     [rcx+60h], rdi
0x140004790  add     rcx, 70h ; 'p'; lpCriticalSection
0x140004794  call    cs:__imp_InitializeCriticalSection
0x14000479a  lea     rcx, [rbx+18h]; lpFrequency
0x14000479e  call    cs:__imp_QueryPerformanceFrequency
0x1400047a4  mov     rcx, rbx; this
0x1400047a7  call    ?CreateNewSessionId@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ; Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(void)
0x1400047ac  nop
0x1400047ad  lea     rax, ??_7ModelUpdate@SPTelemetry@@6B@; const SPTelemetry::ModelUpdate::`vftable'
0x1400047b4  mov     [rbx], rax
0x1400047b7  mov     rcx, rbx; this
0x1400047ba  call    ?StopActivity@FlightDataRecorder@Session@Speech@Windows@@MEAAXJ_K@Z; Windows::Speech::Session::FlightDataRecorder::StopActivity(long,unsigned __int64)
0x1400047bf  mov     rax, [rbx]
0x1400047c2  mov     rcx, rbx
0x1400047c5  mov     rax, [rax+48h]
0x1400047c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047ce  mov     rax, [rbx]
0x1400047d1  mov     rcx, rbx
0x1400047d4  mov     rax, [rax+50h]
0x1400047d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047dd  mov     rax, [rbx]
0x1400047e0  mov     rcx, rbx
0x1400047e3  mov     rax, [rax+58h]
0x1400047e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047ec  cmp     [rbx+0Fh], dil
0x1400047f0  jz      short loc_140004829
0x1400047f2  xor     r8d, r8d; pcbe
0x1400047f5  mov     rdx, rbx; pv
0x1400047f8  lea     rcx, Windows__Speech__Session__EndSessionDueToNoActivityTimerCallback; pfnti
0x1400047ff  call    cs:__imp_CreateThreadpoolTimer
0x140004805  mov     [rbx+60h], rax
0x140004809  test    rax, rax
0x14000480c  jz      short loc_14000482D
0x14000480e  cmp     [rbx+8], dil
0x140004812  jz      short loc_14000482D
0x140004814  lea     rdx, [rbx+68h]; pftDueTime
0x140004818  xor     r9d, r9d; msWindowLength
0x14000481b  xor     r8d, r8d; msPeriod
0x14000481e  mov     rcx, rax; pti
0x140004821  call    cs:__imp_SetThreadpoolTimer
0x140004827  jmp     short loc_14000482D
0x140004829  mov     [rbx+60h], rdi
0x14000482d  mov     rax, rbx
0x140004830  mov     rbx, [rsp+28h+arg_8]
0x140004835  add     rsp, 20h
0x140004839  pop     rdi
0x14000483a  retn
```

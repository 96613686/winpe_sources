# SpeechOneSettingsTelemetry::LifeTime::LifeTime(void)

- ea: `0x140015068`
- end: `0x1400151ff`
- name: `??0LifeTime@SpeechOneSettingsTelemetry@@QEAA@XZ`
- size: `407`
- prototype: `SpeechOneSettingsTelemetry::LifeTime *__fastcall(SpeechOneSettingsTelemetry::LifeTime *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140015208`

## callees

- `0x1400030dc`
- `0x140005bfc`
- `0x140015068`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400150b2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400150b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400151c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400151c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400151e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400151e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1400150bc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1400150bc`

## pseudocode

```c
SpeechOneSettingsTelemetry::LifeTime *__fastcall SpeechOneSettingsTelemetry::LifeTime::LifeTime(
        SpeechOneSettingsTelemetry::LifeTime *this)
{
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
  *(_QWORD *)this = &SpeechOneSettingsTelemetry::LifeTime::`vftable';
  *((_DWORD *)this + 40) = 0;
  *((_BYTE *)this + 164) = 0;
  *((_BYTE *)this + 224) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 26) = "LifeTime";
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  memset_0((char *)this + 240, 0, 0x98u);
  *((_DWORD *)this + 102) = 1;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = (char *)this + 160;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = (char *)this + 152;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 116) = 0;
  *((_QWORD *)this + 59) = (char *)this + 200;
  *((_BYTE *)this + 480) = 0;
  *((_QWORD *)this + 19) = &SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::`vftable';
  (*(void (__fastcall **)(SpeechOneSettingsTelemetry::LifeTime *))(*(_QWORD *)this + 64LL))(this);
  (*(void (__fastcall **)(SpeechOneSettingsTelemetry::LifeTime *))(*(_QWORD *)this + 72LL))(this);
  (*(void (__fastcall **)(SpeechOneSettingsTelemetry::LifeTime *))(*(_QWORD *)this + 80LL))(this);
  (*(void (__fastcall **)(SpeechOneSettingsTelemetry::LifeTime *))(*(_QWORD *)this + 88LL))(this);
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
0x140015068  mov     [rsp+arg_0], rcx
0x14001506d  push    rbx
0x14001506e  push    rbp
0x14001506f  push    rsi
0x140015070  push    rdi
0x140015071  sub     rsp, 28h
0x140015075  mov     rsi, rcx
0x140015078  lea     rax, ??_7FlightDataRecorder@Session@Speech@Windows@@6B@; const Windows::Speech::Session::FlightDataRecorder::`vftable'
0x14001507f  mov     [rcx], rax
0x140015082  xor     ebp, ebp
0x140015084  mov     qword ptr [rcx+8], 1000000h
0x14001508c  mov     dword ptr [rcx+10h], 80030202h
0x140015093  mov     [rcx+30h], rbp
0x140015097  xorps   xmm0, xmm0
0x14001509a  movdqu  xmmword ptr [rcx+38h], xmm0
0x14001509f  mov     [rcx+48h], rbp
0x1400150a3  mov     [rcx+50h], rbp
0x1400150a7  mov     [rcx+58h], ebp
0x1400150aa  mov     [rcx+60h], rbp
0x1400150ae  add     rcx, 70h ; 'p'; lpCriticalSection
0x1400150b2  call    cs:__imp_InitializeCriticalSection
0x1400150b8  lea     rcx, [rsi+18h]; lpFrequency
0x1400150bc  call    cs:__imp_QueryPerformanceFrequency
0x1400150c2  mov     rcx, rsi; this
0x1400150c5  call    ?CreateNewSessionId@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ; Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(void)
0x1400150ca  nop
0x1400150cb  lea     rax, ??_7LifeTime@SpeechOneSettingsTelemetry@@6B@; const SpeechOneSettingsTelemetry::LifeTime::`vftable'
0x1400150d2  mov     [rsi], rax
0x1400150d5  lea     rdi, [rsi+98h]
0x1400150dc  lea     rbx, [rdi+8]
0x1400150e0  mov     [rbx], ebp
0x1400150e2  mov     [rbx+4], bpl
0x1400150e6  mov     [rbx+40h], bpl
0x1400150ea  mov     [rbx+28h], ebp
0x1400150ed  lea     rax, aLifetime; "LifeTime"
0x1400150f4  mov     [rbx+30h], rax
0x1400150f8  mov     [rbx+38h], rbp
0x1400150fc  mov     [rbx+48h], ebp
0x1400150ff  lea     rcx, [rbx+50h]; void *
0x140015103  mov     [rcx+98h], rbp
0x14001510a  mov     [rcx+0A0h], rbp
0x140015111  xor     edx, edx; Val
0x140015113  mov     r8d, 98h; Size
0x140015119  call    memset_0
0x14001511e  mov     dword ptr [rbx+0F8h], 1
0x140015128  xor     eax, eax
0x14001512a  mov     [rbx+100h], rax
0x140015131  mov     [rdi+110h], rbx
0x140015138  mov     [rdi+118h], rbp
0x14001513f  mov     [rdi+120h], rbp
0x140015146  mov     [rdi+128h], rdi
0x14001514d  mov     [rdi+130h], rbp
0x140015154  mov     [rdi+138h], ebp
0x14001515a  lea     rax, [rdi+30h]
0x14001515e  mov     [rdi+140h], rax
0x140015165  mov     [rdi+148h], bpl
0x14001516c  lea     rax, ??_7LifeTime@ActivityContainer@0SpeechOneSettingsTelemetry@@6B@; const SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::`vftable'
0x140015173  mov     [rdi], rax
0x140015176  mov     rax, [rsi]
0x140015179  mov     rcx, rsi
0x14001517c  mov     rax, [rax+40h]
0x140015180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015185  mov     rax, [rsi]
0x140015188  mov     rcx, rsi
0x14001518b  mov     rax, [rax+48h]
0x14001518f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015194  mov     rax, [rsi]
0x140015197  mov     rcx, rsi
0x14001519a  mov     rax, [rax+50h]
0x14001519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151a3  mov     rax, [rsi]
0x1400151a6  mov     rcx, rsi
0x1400151a9  mov     rax, [rax+58h]
0x1400151ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151b2  cmp     [rsi+0Fh], bpl
0x1400151b6  jz      short loc_1400151EF
0x1400151b8  xor     r8d, r8d; pcbe
0x1400151bb  mov     rdx, rsi; pv
0x1400151be  lea     rcx, Windows__Speech__Session__EndSessionDueToNoActivityTimerCallback; pfnti
0x1400151c5  call    cs:__imp_CreateThreadpoolTimer
0x1400151cb  mov     [rsi+60h], rax
0x1400151cf  test    rax, rax
0x1400151d2  jz      short loc_1400151F3
0x1400151d4  cmp     [rsi+8], bpl
0x1400151d8  jz      short loc_1400151F3
0x1400151da  lea     rdx, [rsi+68h]; pftDueTime
0x1400151de  xor     r9d, r9d; msWindowLength
0x1400151e1  xor     r8d, r8d; msPeriod
0x1400151e4  mov     rcx, rax; pti
0x1400151e7  call    cs:__imp_SetThreadpoolTimer
0x1400151ed  jmp     short loc_1400151F3
0x1400151ef  mov     [rsi+60h], rbp
0x1400151f3  mov     rax, rsi
0x1400151f6  add     rsp, 28h
0x1400151fa  pop     rdi
0x1400151fb  pop     rsi
0x1400151fc  pop     rbp
0x1400151fd  pop     rbx
0x1400151fe  retn
```

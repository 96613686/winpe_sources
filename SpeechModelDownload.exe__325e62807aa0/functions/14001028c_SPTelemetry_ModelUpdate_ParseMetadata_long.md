# SPTelemetry::ModelUpdate::ParseMetadata(long)

- ea: `0x14001028c`
- end: `0x14001040e`
- name: `?ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z`
- size: `386`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000d5a4`

## callees

- `0x140003c64`
- `0x1400077b0`
- `0x14000ad94`
- `0x14000ae78`
- `0x14000c2d4`
- `0x14001028c`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010303`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010303`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010381`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400102ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400102ec`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14001032e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14001032e`

## string_xrefs

- `0x1400103d2`: `ModelUpdate_ParseMetadata`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::ParseMetadata(SPTelemetry::ModelUpdate *this, int a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  struct _TP_TIMER *v5; // rcx
  int v6; // r9d
  unsigned __int64 v7; // rbp
  unsigned int v8; // r8d
  _BYTE *v9; // rsi
  int v10; // [rsp+58h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+18h] BYREF
  char *v12; // [rsp+68h] [rbp+20h]

  v10 = a2;
  v3 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    v4 = 0x400000000000LL;
    if ( (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v3 + 3) & 0x400000000000LL) == *((_QWORD *)v3 + 3) )
    {
      v5 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
      if ( v5 )
        SetThreadpoolTimer(v5, (PFILETIME)this + 13, 0, 0);
      v12 = (char *)this + 112;
      if ( this != (SPTelemetry::ModelUpdate *)-112LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      if ( !*((_BYTE *)this + 8) )
      {
        LOBYTE(v4) = 1;
        (**(void (__fastcall ***)(SPTelemetry::ModelUpdate *, __int64))this)(this, v4);
      }
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v7 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
      if ( `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::minSecondsBetweenEvents )
      {
        v8 = v7 / 0x989680 - `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::lastFiredEventTimeInSeconds;
        if ( v8 < `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::ParseMetadata'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovParseMetadata_Suppressed(
            this,
            `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::numSuppressed,
            v8);
          `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::ParseMetadata'::`2'::lastFiredEventTimeInSeconds = v7 / 0x989680;
      }
      v9 = (char *)this + 10;
      if ( (*((_BYTE *)this + 9) || *v9)
        && (Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<unsigned short [3],long>(
              (_DWORD)this,
              (unsigned int)"ModelUpdate_ParseMetadata",
              v7,
              v6,
              (__int64)&v10),
            *v9) )
      {
        SPTelemetry::ModelUpdate::AsimovParseMetadataLocal<long &>((__int64)this, v7, &v10);
      }
      else
      {
        SPTelemetry::ModelUpdate::AsimovParseMetadata<long &>((__int64)this, v7, &v10);
      }
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x14001028c  mov     [rsp+arg_0], rbx
0x140010291  mov     [rsp+arg_8], edx
0x140010295  push    rbp
0x140010296  push    rsi
0x140010297  push    rdi
0x140010298  sub     rsp, 30h
0x14001029c  mov     rbx, rcx
0x14001029f  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x1400102a4  mov     edx, [rax]
0x1400102a6  cmp     edx, 5
0x1400102a9  jbe     loc_140010387
0x1400102af  mov     rcx, [rax+18h]
0x1400102b3  mov     rax, [rax+10h]
0x1400102b7  mov     rdx, 400000000000h
0x1400102c1  test    rdx, rax
0x1400102c4  jz      loc_140010387
0x1400102ca  mov     rax, rcx
0x1400102cd  and     rax, rdx
0x1400102d0  cmp     rax, rcx
0x1400102d3  jnz     loc_140010387
0x1400102d9  mov     rcx, [rbx+60h]; pti
0x1400102dd  test    rcx, rcx
0x1400102e0  jz      short loc_1400102F2
0x1400102e2  lea     rdx, [rbx+68h]; pftDueTime
0x1400102e6  xor     r9d, r9d; msWindowLength
0x1400102e9  xor     r8d, r8d; msPeriod
0x1400102ec  call    cs:__imp_SetThreadpoolTimer
0x1400102f2  lea     rdi, [rbx+70h]
0x1400102f6  mov     [rsp+48h+arg_18], rdi
0x1400102fb  test    rdi, rdi
0x1400102fe  jz      short loc_14001030A
0x140010300  mov     rcx, rdi; lpCriticalSection
0x140010303  call    cs:__imp_EnterCriticalSection
0x140010309  nop
0x14001030a  cmp     byte ptr [rbx+8], 0
0x14001030e  jnz     short loc_140010320
0x140010310  mov     rax, [rbx]
0x140010313  mov     dl, 1
0x140010315  mov     rcx, rbx
0x140010318  mov     rax, [rax]
0x14001031b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010320  mov     qword ptr [rsp+48h+PerformanceCount], 0
0x140010329  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x14001032e  call    cs:__imp_QueryPerformanceCounter
0x140010334  imul    rax, qword ptr [rsp+48h+PerformanceCount], 989680h
0x14001033d  cqo
0x14001033f  idiv    qword ptr [rbx+18h]
0x140010343  mov     rbp, rax
0x140010346  mov     ecx, cs:?minSecondsBetweenEvents@?1??ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; uint `SPTelemetry::ModelUpdate::ParseMetadata(long)'::`2'::minSecondsBetweenEvents
0x14001034c  test    ecx, ecx
0x14001034e  jz      short loc_1400103B6
0x140010350  mov     rax, 0D6BF94D5E57A42BDh
0x14001035a  mul     rbp
0x14001035d  mov     rsi, rdx
0x140010360  shr     rsi, 17h
0x140010364  mov     r8d, esi
0x140010367  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; unsigned int
0x14001036e  cmp     r8d, ecx
0x140010371  jnb     short loc_140010394
0x140010373  inc     cs:?numSuppressed@?1??ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; uint `SPTelemetry::ModelUpdate::ParseMetadata(long)'::`2'::numSuppressed
0x140010379  test    rdi, rdi
0x14001037c  jz      short loc_140010387
0x14001037e  mov     rcx, rdi; lpCriticalSection
0x140010381  call    cs:__imp_LeaveCriticalSection
0x140010387  mov     rbx, [rsp+48h+arg_0]
0x14001038c  add     rsp, 30h
0x140010390  pop     rdi
0x140010391  pop     rsi
0x140010392  pop     rbp
0x140010393  retn
0x140010394  mov     edx, cs:?numSuppressed@?1??ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; unsigned int
0x14001039a  test    edx, edx
0x14001039c  jz      short loc_1400103B0
0x14001039e  mov     rcx, rbx; this
0x1400103a1  call    ?AsimovParseMetadata_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovParseMetadata_Suppressed(uint,uint)
0x1400103a6  mov     cs:?numSuppressed@?1??ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::ParseMetadata(long)'::`2'::numSuppressed
0x1400103b0  mov     cs:?lastFiredEventTimeInSeconds@?1??ParseMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::ParseMetadata(long)'::`2'::lastFiredEventTimeInSeconds
0x1400103b6  lea     rsi, [rbx+0Ah]
0x1400103ba  cmp     byte ptr [rbx+9], 0
0x1400103be  jnz     short loc_1400103C5
0x1400103c0  cmp     byte ptr [rsi], 0
0x1400103c3  jz      short loc_1400103E6
0x1400103c5  lea     rax, [rsp+48h+arg_8]
0x1400103ca  mov     [rsp+48h+var_28], rax
0x1400103cf  mov     r8, rbp
0x1400103d2  lea     rdx, aModelupdatePar; "ModelUpdate_ParseMetadata"
0x1400103d9  mov     rcx, rbx
0x1400103dc  call    ??$AddEventToEventQueue@$$BY02GJ@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_KAEAY02$$CBGAEBJ@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<ushort [3],long>(char const *,unsigned __int64,ushort const (&)[3],long const &)
0x1400103e1  cmp     byte ptr [rsi], 0
0x1400103e4  jnz     short loc_1400103F8
0x1400103e6  lea     r8, [rsp+48h+arg_8]
0x1400103eb  mov     rdx, rbp
0x1400103ee  mov     rcx, rbx
0x1400103f1  call    ??$AsimovParseMetadata@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z; SPTelemetry::ModelUpdate::AsimovParseMetadata<long &>(unsigned __int64,long &)
0x1400103f6  jmp     short loc_140010379
0x1400103f8  lea     r8, [rsp+48h+arg_8]
0x1400103fd  mov     rdx, rbp
0x140010400  mov     rcx, rbx
0x140010403  call    ??$AsimovParseMetadataLocal@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z; SPTelemetry::ModelUpdate::AsimovParseMetadataLocal<long &>(unsigned __int64,long &)
0x140010408  jmp     loc_140010379
```

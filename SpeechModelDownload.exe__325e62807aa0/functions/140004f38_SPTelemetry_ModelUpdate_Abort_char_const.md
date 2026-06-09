# SPTelemetry::ModelUpdate::Abort(char const *)

- ea: `0x140004f38`
- end: `0x14000514a`
- name: `?Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z`
- size: `530`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x140009698`
- `0x14000d890`

## callees

- `0x140003840`
- `0x140003d38`
- `0x140003dd4`
- `0x140004f38`
- `0x140005520`
- `0x140005668`
- `0x140005ea0`
- `0x14000732c`
- `0x1400077b0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004fbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004fbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005036`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005036`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004fa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004fa5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140004fe4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140004fe4`

## string_xrefs

- `0x140005092`: `ModelUpdate_Abort`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::Abort(SPTelemetry::ModelUpdate *this, const char *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  struct _TP_TIMER *v6; // rcx
  unsigned __int64 v7; // r14
  unsigned int v8; // r8d
  LARGE_INTEGER v9; // rcx
  const char *v10; // [rsp+68h] [rbp+38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp+40h] BYREF
  LARGE_INTEGER v12; // [rsp+78h] [rbp+48h] BYREF

  v10 = a2;
  v4 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v5 = 0x400000000000LL;
    if ( (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v4 + 3) & 0x400000000000LL) == *((_QWORD *)v4 + 3) )
    {
      v6 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
      if ( v6 )
        SetThreadpoolTimer(v6, (PFILETIME)this + 13, 0, 0);
      if ( this != (SPTelemetry::ModelUpdate *)-112LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      if ( !*((_BYTE *)this + 8) )
      {
        LOBYTE(v5) = 1;
        (**(void (__fastcall ***)(SPTelemetry::ModelUpdate *, __int64))this)(this, v5);
      }
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v7 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
      if ( `SPTelemetry::ModelUpdate::Abort'::`2'::minSecondsBetweenEvents )
      {
        v8 = v7 / 0x989680 - `SPTelemetry::ModelUpdate::Abort'::`2'::lastFiredEventTimeInSeconds;
        if ( v8 < `SPTelemetry::ModelUpdate::Abort'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::Abort'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::Abort'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovAbort_Suppressed(
            this,
            `SPTelemetry::ModelUpdate::Abort'::`2'::numSuppressed,
            v8);
          `SPTelemetry::ModelUpdate::Abort'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::Abort'::`2'::lastFiredEventTimeInSeconds = v7 / 0x989680;
      }
      if ( !*((_BYTE *)this + 9) && !*((_BYTE *)this + 10) )
        goto LABEL_29;
      if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
      {
        Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(
          this,
          &PerformanceCount,
          "ModelUpdate_Abort",
          v7,
          (char *)this + 112);
        v12 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(
          (__int64)this,
          (__int64 *)&v12,
          (__int64)L"Reason",
          a2);
        v12 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(this, &v12);
        v9 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
        {
          PerformanceCount.QuadPart = 0;
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v9.QuadPart + 16LL))(v9);
        }
      }
      if ( *((_BYTE *)this + 10) )
        SPTelemetry::ModelUpdate::AsimovAbortLocal<char const * &>((__int64)this, v7, (__int64 *)&v10);
      else
LABEL_29:
        SPTelemetry::ModelUpdate::AsimovAbort<char const * &>((__int64)this, v7, (__int64 *)&v10);
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x140004f38  mov     [rsp-28h+arg_0], rbx
0x140004f3d  mov     [rsp-28h+arg_8], rdx
0x140004f42  push    rbp
0x140004f43  push    rsi
0x140004f44  push    rdi
0x140004f45  push    r14
0x140004f47  push    r15
0x140004f49  mov     rbp, rsp
0x140004f4c  sub     rsp, 30h
0x140004f50  mov     r15, rdx
0x140004f53  mov     rbx, rcx
0x140004f56  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140004f5b  mov     r8d, [rax]
0x140004f5e  cmp     r8d, 5
0x140004f62  jbe     loc_14000503C
0x140004f68  mov     rcx, [rax+18h]
0x140004f6c  mov     rax, [rax+10h]
0x140004f70  mov     rdx, 400000000000h
0x140004f7a  test    rdx, rax
0x140004f7d  jz      loc_14000503C
0x140004f83  mov     rax, rcx
0x140004f86  and     rax, rdx
0x140004f89  cmp     rax, rcx
0x140004f8c  jnz     loc_14000503C
0x140004f92  mov     rcx, [rbx+60h]; pti
0x140004f96  test    rcx, rcx
0x140004f99  jz      short loc_140004FAB
0x140004f9b  lea     rdx, [rbx+68h]; pftDueTime
0x140004f9f  xor     r9d, r9d; msWindowLength
0x140004fa2  xor     r8d, r8d; msPeriod
0x140004fa5  call    cs:__imp_SetThreadpoolTimer
0x140004fab  lea     rdi, [rbx+70h]
0x140004faf  mov     [rbp+var_10], rdi
0x140004fb3  test    rdi, rdi
0x140004fb6  jz      short loc_140004FC2
0x140004fb8  mov     rcx, rdi; lpCriticalSection
0x140004fbb  call    cs:__imp_EnterCriticalSection
0x140004fc1  nop
0x140004fc2  cmp     byte ptr [rbx+8], 0
0x140004fc6  jnz     short loc_140004FD8
0x140004fc8  mov     rax, [rbx]
0x140004fcb  mov     dl, 1
0x140004fcd  mov     rcx, rbx
0x140004fd0  mov     rax, [rax]
0x140004fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fd8  mov     qword ptr [rbp+PerformanceCount], 0
0x140004fe0  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140004fe4  call    cs:__imp_QueryPerformanceCounter
0x140004fea  imul    rax, qword ptr [rbp+PerformanceCount], 989680h
0x140004ff2  cqo
0x140004ff4  idiv    qword ptr [rbx+18h]
0x140004ff8  mov     r14, rax
0x140004ffb  mov     ecx, cs:?minSecondsBetweenEvents@?1??Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; uint `SPTelemetry::ModelUpdate::Abort(char const *)'::`2'::minSecondsBetweenEvents
0x140005001  test    ecx, ecx
0x140005003  jz      short loc_14000506F
0x140005005  mov     rax, 0D6BF94D5E57A42BDh
0x14000500f  mul     r14
0x140005012  mov     rsi, rdx
0x140005015  shr     rsi, 17h
0x140005019  mov     r8d, esi
0x14000501c  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; unsigned int
0x140005023  cmp     r8d, ecx
0x140005026  jnb     short loc_14000504D
0x140005028  inc     cs:?numSuppressed@?1??Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; uint `SPTelemetry::ModelUpdate::Abort(char const *)'::`2'::numSuppressed
0x14000502e  test    rdi, rdi
0x140005031  jz      short loc_14000503C
0x140005033  mov     rcx, rdi; lpCriticalSection
0x140005036  call    cs:__imp_LeaveCriticalSection
0x14000503c  mov     rbx, [rsp+30h+arg_0]
0x140005041  add     rsp, 30h
0x140005045  pop     r15
0x140005047  pop     r14
0x140005049  pop     rdi
0x14000504a  pop     rsi
0x14000504b  pop     rbp
0x14000504c  retn
0x14000504d  mov     edx, cs:?numSuppressed@?1??Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; unsigned int
0x140005053  test    edx, edx
0x140005055  jz      short loc_140005069
0x140005057  mov     rcx, rbx; this
0x14000505a  call    ?AsimovAbort_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovAbort_Suppressed(uint,uint)
0x14000505f  mov     cs:?numSuppressed@?1??Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::Abort(char const *)'::`2'::numSuppressed
0x140005069  mov     cs:?lastFiredEventTimeInSeconds@?1??Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::Abort(char const *)'::`2'::lastFiredEventTimeInSeconds
0x14000506f  cmp     byte ptr [rbx+9], 0
0x140005073  jnz     short loc_14000507F
0x140005075  cmp     byte ptr [rbx+0Ah], 0
0x140005079  jz      loc_140005121
0x14000507f  mov     rcx, rbx; this
0x140005082  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140005087  test    eax, eax
0x140005089  js      loc_14000511B
0x14000508f  mov     r9, r14
0x140005092  lea     r8, aModelupdateAbo; "ModelUpdate_Abort"
0x140005099  lea     rdx, [rbp+PerformanceCount]
0x14000509d  mov     rcx, rbx
0x1400050a0  call    ?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z; Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)
0x1400050a5  nop
0x1400050a6  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1400050aa  mov     [rbp+arg_18], rcx
0x1400050ae  test    rcx, rcx
0x1400050b1  jz      short loc_1400050C0
0x1400050b3  mov     rax, [rcx]
0x1400050b6  mov     rax, [rax+8]
0x1400050ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050bf  nop
0x1400050c0  mov     r9, r15
0x1400050c3  lea     r8, aReason; "Reason"
0x1400050ca  lea     rdx, [rbp+arg_18]
0x1400050ce  mov     rcx, rbx
0x1400050d1  call    ??$AddColumnToCoalescedEvent@PEBD@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGPEBD@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,char const *)
0x1400050d6  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1400050da  mov     [rbp+arg_18], rcx
0x1400050de  test    rcx, rcx
0x1400050e1  jz      short loc_1400050F0
0x1400050e3  mov     rax, [rcx]
0x1400050e6  mov     rax, [rax+8]
0x1400050ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050ef  nop
0x1400050f0  lea     rdx, [rbp+arg_18]
0x1400050f4  mov     rcx, rbx
0x1400050f7  call    ?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x1400050fc  nop
0x1400050fd  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140005101  test    rcx, rcx
0x140005104  jz      short loc_14000511B
0x140005106  mov     qword ptr [rbp+PerformanceCount], 0
0x14000510e  mov     rax, [rcx]
0x140005111  mov     rax, [rax+10h]
0x140005115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000511a  nop
0x14000511b  cmp     byte ptr [rbx+0Ah], 0
0x14000511f  jnz     short loc_140005135
0x140005121  lea     r8, [rbp+arg_8]
0x140005125  mov     rdx, r14
0x140005128  mov     rcx, rbx
0x14000512b  call    ??$AsimovAbort@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z; SPTelemetry::ModelUpdate::AsimovAbort<char const * &>(unsigned __int64,char const * &)
0x140005130  jmp     loc_14000502E
0x140005135  lea     r8, [rbp+arg_8]
0x140005139  mov     rdx, r14
0x14000513c  mov     rcx, rbx
0x14000513f  call    ??$AsimovAbortLocal@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z; SPTelemetry::ModelUpdate::AsimovAbortLocal<char const * &>(unsigned __int64,char const * &)
0x140005144  jmp     loc_14000502E
```

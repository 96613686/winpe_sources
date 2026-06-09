# SPTelemetry::ModelUpdate::Begin(char const *)

- ea: `0x14000c3d8`
- end: `0x14000c5ea`
- name: `?Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z`
- size: `530`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`

## callees

- `0x140003840`
- `0x140005520`
- `0x140005ea0`
- `0x14000732c`
- `0x1400077b0`
- `0x14000a5ec`
- `0x14000a688`
- `0x14000be9c`
- `0x14000c3d8`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c45b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c45b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c4d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c4d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c445`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c445`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000c484`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000c484`

## string_xrefs

- `0x14000c532`: `ModelUpdate_Begin`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::Begin(SPTelemetry::ModelUpdate *this, const char *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  struct _TP_TIMER *v6; // rcx
  unsigned __int64 v7; // r14
  unsigned int v8; // r8d
  LARGE_INTEGER v9; // rcx
  const char *v10; // [rsp+68h] [rbp+38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp+40h] BYREF
  __int64 (__fastcall ***QuadPart)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp+48h] BYREF

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
      if ( `SPTelemetry::ModelUpdate::Begin'::`2'::minSecondsBetweenEvents )
      {
        v8 = v7 / 0x989680 - `SPTelemetry::ModelUpdate::Begin'::`2'::lastFiredEventTimeInSeconds;
        if ( v8 < `SPTelemetry::ModelUpdate::Begin'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::Begin'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::Begin'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovBegin_Suppressed(
            this,
            `SPTelemetry::ModelUpdate::Begin'::`2'::numSuppressed,
            v8);
          `SPTelemetry::ModelUpdate::Begin'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::Begin'::`2'::lastFiredEventTimeInSeconds = v7 / 0x989680;
      }
      if ( !*((_BYTE *)this + 9) && !*((_BYTE *)this + 10) )
        goto LABEL_29;
      if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
      {
        Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(
          this,
          &PerformanceCount,
          "ModelUpdate_Begin",
          v7,
          (char *)this + 112);
        QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(
          (__int64)this,
          (__int64 *)&QuadPart,
          (__int64)L"Model",
          a2);
        QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(this, &QuadPart);
        v9 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
        {
          PerformanceCount.QuadPart = 0;
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v9.QuadPart + 16LL))(v9);
        }
      }
      if ( *((_BYTE *)this + 10) )
        SPTelemetry::ModelUpdate::AsimovBeginLocal<char const * &>((__int64)this, v7, (__int64 *)&v10);
      else
LABEL_29:
        SPTelemetry::ModelUpdate::AsimovBegin<char const * &>((__int64)this, v7, (__int64 *)&v10);
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x14000c3d8  mov     [rsp-28h+arg_0], rbx
0x14000c3dd  mov     [rsp-28h+arg_8], rdx
0x14000c3e2  push    rbp
0x14000c3e3  push    rsi
0x14000c3e4  push    rdi
0x14000c3e5  push    r14
0x14000c3e7  push    r15
0x14000c3e9  mov     rbp, rsp
0x14000c3ec  sub     rsp, 30h
0x14000c3f0  mov     r15, rdx
0x14000c3f3  mov     rbx, rcx
0x14000c3f6  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000c3fb  mov     r8d, [rax]
0x14000c3fe  cmp     r8d, 5
0x14000c402  jbe     loc_14000C4DC
0x14000c408  mov     rcx, [rax+18h]
0x14000c40c  mov     rax, [rax+10h]
0x14000c410  mov     rdx, 400000000000h
0x14000c41a  test    rdx, rax
0x14000c41d  jz      loc_14000C4DC
0x14000c423  mov     rax, rcx
0x14000c426  and     rax, rdx
0x14000c429  cmp     rax, rcx
0x14000c42c  jnz     loc_14000C4DC
0x14000c432  mov     rcx, [rbx+60h]; pti
0x14000c436  test    rcx, rcx
0x14000c439  jz      short loc_14000C44B
0x14000c43b  lea     rdx, [rbx+68h]; pftDueTime
0x14000c43f  xor     r9d, r9d; msWindowLength
0x14000c442  xor     r8d, r8d; msPeriod
0x14000c445  call    cs:__imp_SetThreadpoolTimer
0x14000c44b  lea     rdi, [rbx+70h]
0x14000c44f  mov     [rbp+var_10], rdi
0x14000c453  test    rdi, rdi
0x14000c456  jz      short loc_14000C462
0x14000c458  mov     rcx, rdi; lpCriticalSection
0x14000c45b  call    cs:__imp_EnterCriticalSection
0x14000c461  nop
0x14000c462  cmp     byte ptr [rbx+8], 0
0x14000c466  jnz     short loc_14000C478
0x14000c468  mov     rax, [rbx]
0x14000c46b  mov     dl, 1
0x14000c46d  mov     rcx, rbx
0x14000c470  mov     rax, [rax]
0x14000c473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c478  mov     qword ptr [rbp+PerformanceCount], 0
0x14000c480  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000c484  call    cs:__imp_QueryPerformanceCounter
0x14000c48a  imul    rax, qword ptr [rbp+PerformanceCount], 989680h
0x14000c492  cqo
0x14000c494  idiv    qword ptr [rbx+18h]
0x14000c498  mov     r14, rax
0x14000c49b  mov     ecx, cs:?minSecondsBetweenEvents@?1??Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; uint `SPTelemetry::ModelUpdate::Begin(char const *)'::`2'::minSecondsBetweenEvents
0x14000c4a1  test    ecx, ecx
0x14000c4a3  jz      short loc_14000C50F
0x14000c4a5  mov     rax, 0D6BF94D5E57A42BDh
0x14000c4af  mul     r14
0x14000c4b2  mov     rsi, rdx
0x14000c4b5  shr     rsi, 17h
0x14000c4b9  mov     r8d, esi
0x14000c4bc  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; unsigned int
0x14000c4c3  cmp     r8d, ecx
0x14000c4c6  jnb     short loc_14000C4ED
0x14000c4c8  inc     cs:?numSuppressed@?1??Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; uint `SPTelemetry::ModelUpdate::Begin(char const *)'::`2'::numSuppressed
0x14000c4ce  test    rdi, rdi
0x14000c4d1  jz      short loc_14000C4DC
0x14000c4d3  mov     rcx, rdi; lpCriticalSection
0x14000c4d6  call    cs:__imp_LeaveCriticalSection
0x14000c4dc  mov     rbx, [rsp+30h+arg_0]
0x14000c4e1  add     rsp, 30h
0x14000c4e5  pop     r15
0x14000c4e7  pop     r14
0x14000c4e9  pop     rdi
0x14000c4ea  pop     rsi
0x14000c4eb  pop     rbp
0x14000c4ec  retn
0x14000c4ed  mov     edx, cs:?numSuppressed@?1??Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA; unsigned int
0x14000c4f3  test    edx, edx
0x14000c4f5  jz      short loc_14000C509
0x14000c4f7  mov     rcx, rbx; this
0x14000c4fa  call    ?AsimovBegin_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovBegin_Suppressed(uint,uint)
0x14000c4ff  mov     cs:?numSuppressed@?1??Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::Begin(char const *)'::`2'::numSuppressed
0x14000c509  mov     cs:?lastFiredEventTimeInSeconds@?1??Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::Begin(char const *)'::`2'::lastFiredEventTimeInSeconds
0x14000c50f  cmp     byte ptr [rbx+9], 0
0x14000c513  jnz     short loc_14000C51F
0x14000c515  cmp     byte ptr [rbx+0Ah], 0
0x14000c519  jz      loc_14000C5C1
0x14000c51f  mov     rcx, rbx; this
0x14000c522  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x14000c527  test    eax, eax
0x14000c529  js      loc_14000C5BB
0x14000c52f  mov     r9, r14
0x14000c532  lea     r8, aModelupdateBeg; "ModelUpdate_Begin"
0x14000c539  lea     rdx, [rbp+PerformanceCount]
0x14000c53d  mov     rcx, rbx
0x14000c540  call    ?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z; Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)
0x14000c545  nop
0x14000c546  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000c54a  mov     [rbp+arg_18], rcx
0x14000c54e  test    rcx, rcx
0x14000c551  jz      short loc_14000C560
0x14000c553  mov     rax, [rcx]
0x14000c556  mov     rax, [rax+8]
0x14000c55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c55f  nop
0x14000c560  mov     r9, r15
0x14000c563  lea     r8, aModel; "Model"
0x14000c56a  lea     rdx, [rbp+arg_18]
0x14000c56e  mov     rcx, rbx
0x14000c571  call    ??$AddColumnToCoalescedEvent@PEBD@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGPEBD@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<char const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,char const *)
0x14000c576  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000c57a  mov     [rbp+arg_18], rcx
0x14000c57e  test    rcx, rcx
0x14000c581  jz      short loc_14000C590
0x14000c583  mov     rax, [rcx]
0x14000c586  mov     rax, [rax+8]
0x14000c58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c58f  nop
0x14000c590  lea     rdx, [rbp+arg_18]
0x14000c594  mov     rcx, rbx
0x14000c597  call    ?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x14000c59c  nop
0x14000c59d  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000c5a1  test    rcx, rcx
0x14000c5a4  jz      short loc_14000C5BB
0x14000c5a6  mov     qword ptr [rbp+PerformanceCount], 0
0x14000c5ae  mov     rax, [rcx]
0x14000c5b1  mov     rax, [rax+10h]
0x14000c5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5ba  nop
0x14000c5bb  cmp     byte ptr [rbx+0Ah], 0
0x14000c5bf  jnz     short loc_14000C5D5
0x14000c5c1  lea     r8, [rbp+arg_8]
0x14000c5c5  mov     rdx, r14
0x14000c5c8  mov     rcx, rbx
0x14000c5cb  call    ??$AsimovBegin@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z; SPTelemetry::ModelUpdate::AsimovBegin<char const * &>(unsigned __int64,char const * &)
0x14000c5d0  jmp     loc_14000C4CE
0x14000c5d5  lea     r8, [rbp+arg_8]
0x14000c5d9  mov     rdx, r14
0x14000c5dc  mov     rcx, rbx
0x14000c5df  call    ??$AsimovBeginLocal@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z; SPTelemetry::ModelUpdate::AsimovBeginLocal<char const * &>(unsigned __int64,char const * &)
0x14000c5e4  jmp     loc_14000C4CE
```

# SpeechOneSettingsTelemetry::LifeTime::MyInit(ushort const *,ushort const *,ushort const *)

- ea: `0x1400180f0`
- end: `0x140018327`
- name: `?MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z`
- size: `567`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400177a0`

## callees

- `0x140005520`
- `0x140005ea0`
- `0x14000732c`
- `0x140013e8c`
- `0x140013fcc`
- `0x140014080`
- `0x140015e08`
- `0x1400180f0`
- `0x1400189d4`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001818d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001818d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018208`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018208`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140018177`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140018177`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400181b6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400181b6`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::MyInit(
        SpeechOneSettingsTelemetry::LifeTime *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  struct _TP_TIMER *v7; // rcx
  unsigned __int64 v8; // r14
  unsigned int v9; // r8d
  __int64 v10; // r8
  LARGE_INTEGER v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-40h]
  __int64 *v13; // [rsp+30h] [rbp-30h]
  const wchar_t *v14; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v15; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 (__fastcall ***QuadPart)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp+40h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A8h] [rbp+48h] BYREF

  PerformanceCount.QuadPart = (LONGLONG)a4;
  QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))a3;
  v14 = L"SpeechModelDownload";
  v15 = L"nasp_speechmodels";
  v16[0] = L"analog";
  v5 = SpeechOneSettingsLogging::Provider();
  v6 = *(unsigned int *)v5;
  if ( (unsigned int)v6 > 5 && (*((_QWORD *)v5 + 2) & 1) != 0 && (*((_QWORD *)v5 + 3) & 1LL) == *((_QWORD *)v5 + 3) )
  {
    v7 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
    if ( v7 )
      SetThreadpoolTimer(v7, (PFILETIME)this + 13, 0, 0);
    if ( this != (SpeechOneSettingsTelemetry::LifeTime *)-112LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    if ( !*((_BYTE *)this + 8) )
    {
      LOBYTE(v6) = 1;
      (**(void (__fastcall ***)(SpeechOneSettingsTelemetry::LifeTime *, __int64))this)(this, v6);
    }
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v8 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
    if ( `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::minSecondsBetweenEvents )
    {
      v9 = v8 / 0x989680 - `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::lastFiredEventTimeInSeconds;
      if ( v9 < `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::minSecondsBetweenEvents )
      {
        ++`SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::numSuppressed;
LABEL_13:
        if ( this != (SpeechOneSettingsTelemetry::LifeTime *)-112LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
        return;
      }
      if ( `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::numSuppressed )
      {
        SpeechOneSettingsTelemetry::LifeTime::AsimovMyInit_Suppressed(
          this,
          `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::numSuppressed,
          v9);
        `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::numSuppressed = 0;
      }
      `SpeechOneSettingsTelemetry::LifeTime::MyInit'::`2'::lastFiredEventTimeInSeconds = v8 / 0x989680;
    }
    if ( *((_BYTE *)this + 9) && (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
    {
      Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(
        this,
        (__int64 *)&PerformanceCount,
        "LifeTime_MyInit");
      QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
      if ( PerformanceCount.QuadPart )
        (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
      Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *,unsigned short [8],unsigned short const *,unsigned short [6],unsigned short const *>(
        (__int64)this,
        (__int64 *)&QuadPart,
        v10,
        (__int64)L"analog",
        v12,
        (__int64 *)&v15,
        v13,
        (__int64 *)&v14);
      QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
      if ( PerformanceCount.QuadPart )
        (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
      Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(this, &QuadPart);
      v11 = PerformanceCount;
      if ( PerformanceCount.QuadPart )
      {
        PerformanceCount.QuadPart = 0;
        (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v11.QuadPart + 16LL))(v11);
      }
    }
    if ( *((_BYTE *)this + 10) )
      SpeechOneSettingsTelemetry::LifeTime::AsimovMyInitLocal<unsigned short const * &,unsigned short const * &,unsigned short const * &>(
        (_DWORD)this,
        v8,
        (unsigned int)v16,
        (unsigned int)&v15,
        (__int64)&v14);
    else
      SpeechOneSettingsTelemetry::LifeTime::AsimovMyInit<unsigned short const * &,unsigned short const * &,unsigned short const * &>(
        (_DWORD)this,
        v8,
        (unsigned int)v16,
        (unsigned int)&v15,
        (__int64)&v14);
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x1400180f0  mov     rax, rsp
0x1400180f3  mov     [rax+8], rbx
0x1400180f7  mov     [rax+20h], r9
0x1400180fb  mov     [rax+18h], r8
0x1400180ff  mov     [rax+10h], rdx
0x140018103  push    rbp
0x140018104  push    rsi
0x140018105  push    rdi
0x140018106  push    r12
0x140018108  push    r14
0x14001810a  mov     rbp, rsp
0x14001810d  sub     rsp, 60h
0x140018111  mov     rbx, rcx
0x140018114  lea     rax, aSpeechmodeldow; "SpeechModelDownload"
0x14001811b  mov     [rbp+var_20], rax
0x14001811f  lea     rax, aNaspSpeechmode; "nasp_speechmodels"
0x140018126  mov     [rbp+var_18], rax
0x14001812a  lea     r12, aAnalog; "analog"
0x140018131  mov     [rbp+var_10], r12
0x140018135  call    ?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechOneSettingsLogging::Provider(void)
0x14001813a  mov     edx, [rax]
0x14001813c  cmp     edx, 5
0x14001813f  jbe     loc_14001820E
0x140018145  mov     rcx, [rax+18h]
0x140018149  mov     rax, [rax+10h]
0x14001814d  test    al, 1
0x14001814f  jz      loc_14001820E
0x140018155  mov     rax, rcx
0x140018158  and     eax, 1
0x14001815b  cmp     rax, rcx
0x14001815e  jnz     loc_14001820E
0x140018164  mov     rcx, [rbx+60h]; pti
0x140018168  test    rcx, rcx
0x14001816b  jz      short loc_14001817D
0x14001816d  lea     rdx, [rbx+68h]; pftDueTime
0x140018171  xor     r9d, r9d; msWindowLength
0x140018174  xor     r8d, r8d; msPeriod
0x140018177  call    cs:__imp_SetThreadpoolTimer
0x14001817d  lea     rdi, [rbx+70h]
0x140018181  mov     [rbp+arg_8], rdi
0x140018185  test    rdi, rdi
0x140018188  jz      short loc_140018194
0x14001818a  mov     rcx, rdi; lpCriticalSection
0x14001818d  call    cs:__imp_EnterCriticalSection
0x140018193  nop
0x140018194  cmp     byte ptr [rbx+8], 0
0x140018198  jnz     short loc_1400181AA
0x14001819a  mov     rax, [rbx]
0x14001819d  mov     dl, 1
0x14001819f  mov     rcx, rbx
0x1400181a2  mov     rax, [rax]
0x1400181a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400181aa  mov     qword ptr [rbp+PerformanceCount], 0
0x1400181b2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400181b6  call    cs:__imp_QueryPerformanceCounter
0x1400181bc  imul    rax, qword ptr [rbp+PerformanceCount], 989680h
0x1400181c4  cqo
0x1400181c6  idiv    qword ptr [rbx+18h]
0x1400181ca  mov     r14, rax
0x1400181cd  mov     ecx, cs:?minSecondsBetweenEvents@?1??MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z@4IA; uint `SpeechOneSettingsTelemetry::LifeTime::MyInit(ushort const *,ushort const *,ushort const *)'::`2'::minSecondsBetweenEvents
0x1400181d3  test    ecx, ecx
0x1400181d5  jz      short loc_140018244
0x1400181d7  mov     rax, 0D6BF94D5E57A42BDh
0x1400181e1  mul     r14
0x1400181e4  mov     rsi, rdx
0x1400181e7  shr     rsi, 17h
0x1400181eb  mov     r8d, esi
0x1400181ee  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z@4IA; unsigned int
0x1400181f5  cmp     r8d, ecx
0x1400181f8  jnb     short loc_140018222
0x1400181fa  inc     cs:?numSuppressed@?1??MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z@4IA; uint `SpeechOneSettingsTelemetry::LifeTime::MyInit(ushort const *,ushort const *,ushort const *)'::`2'::numSuppressed
0x140018200  test    rdi, rdi
0x140018203  jz      short loc_14001820E
0x140018205  mov     rcx, rdi; lpCriticalSection
0x140018208  call    cs:__imp_LeaveCriticalSection
0x14001820e  mov     rbx, [rsp+60h+arg_0]
0x140018216  add     rsp, 60h
0x14001821a  pop     r14
0x14001821c  pop     r12
0x14001821e  pop     rdi
0x14001821f  pop     rsi
0x140018220  pop     rbp
0x140018221  retn
0x140018222  mov     edx, cs:?numSuppressed@?1??MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z@4IA; unsigned int
0x140018228  test    edx, edx
0x14001822a  jz      short loc_14001823E
0x14001822c  mov     rcx, rbx; this
0x14001822f  call    ?AsimovMyInit_Suppressed@LifeTime@SpeechOneSettingsTelemetry@@QEAAXII@Z; SpeechOneSettingsTelemetry::LifeTime::AsimovMyInit_Suppressed(uint,uint)
0x140018234  mov     cs:?numSuppressed@?1??MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z@4IA, 0; uint `SpeechOneSettingsTelemetry::LifeTime::MyInit(ushort const *,ushort const *,ushort const *)'::`2'::numSuppressed
0x14001823e  mov     cs:?lastFiredEventTimeInSeconds@?1??MyInit@LifeTime@SpeechOneSettingsTelemetry@@QEAAXPEBG00@Z@4IA, esi; uint `SpeechOneSettingsTelemetry::LifeTime::MyInit(ushort const *,ushort const *,ushort const *)'::`2'::lastFiredEventTimeInSeconds
0x140018244  cmp     byte ptr [rbx+9], 0
0x140018248  jz      loc_1400182F5
0x14001824e  mov     rcx, rbx; this
0x140018251  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140018256  test    eax, eax
0x140018258  js      loc_1400182F5
0x14001825e  mov     r9, r14
0x140018261  lea     r8, aLifetimeMyinit; "LifeTime_MyInit"
0x140018268  lea     rdx, [rbp+PerformanceCount]
0x14001826c  mov     rcx, rbx
0x14001826f  call    ?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z; Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)
0x140018274  nop
0x140018275  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140018279  mov     [rbp+arg_10], rcx
0x14001827d  test    rcx, rcx
0x140018280  jz      short loc_14001828F
0x140018282  mov     rax, [rcx]
0x140018285  mov     rax, [rax+8]
0x140018289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001828e  nop
0x14001828f  lea     rax, [rbp+var_20]
0x140018293  mov     [rsp+60h+var_28], rax
0x140018298  lea     rax, [rbp+var_18]
0x14001829c  mov     [rsp+60h+var_38], rax
0x1400182a1  mov     r9, r12
0x1400182a4  lea     rdx, [rbp+arg_10]
0x1400182a8  mov     rcx, rbx
0x1400182ab  call    ??$AddColumnToCoalescedEvent@PEBG$$BY07GPEBG$$BY05GPEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGQEBGAEAY07$$CBGAEBQEBGAEAY05$$CBG4@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *,ushort [8],ushort const *,ushort [6],ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const * const,ushort const (&)[8],ushort const * const &,ushort const (&)[6],ushort const * const &)
0x1400182b0  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1400182b4  mov     [rbp+arg_10], rcx
0x1400182b8  test    rcx, rcx
0x1400182bb  jz      short loc_1400182CA
0x1400182bd  mov     rax, [rcx]
0x1400182c0  mov     rax, [rax+8]
0x1400182c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400182c9  nop
0x1400182ca  lea     rdx, [rbp+arg_10]
0x1400182ce  mov     rcx, rbx
0x1400182d1  call    ?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x1400182d6  nop
0x1400182d7  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1400182db  test    rcx, rcx
0x1400182de  jz      short loc_1400182F5
0x1400182e0  mov     qword ptr [rbp+PerformanceCount], 0
0x1400182e8  mov     rax, [rcx]
0x1400182eb  mov     rax, [rax+10h]
0x1400182ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400182f4  nop
0x1400182f5  lea     rax, [rbp+var_20]
0x1400182f9  lea     r9, [rbp+var_18]
0x1400182fd  lea     r8, [rbp+var_10]
0x140018301  mov     rdx, r14
0x140018304  mov     rcx, rbx
0x140018307  mov     [rsp+60h+var_40], rax
0x14001830c  cmp     byte ptr [rbx+0Ah], 0
0x140018310  jnz     short loc_14001831C
0x140018312  call    ??$AsimovMyInit@AEAPEBGAEAPEBGAEAPEBG@LifeTime@SpeechOneSettingsTelemetry@@QEAAX_KAEAPEBG11@Z; SpeechOneSettingsTelemetry::LifeTime::AsimovMyInit<ushort const * &,ushort const * &,ushort const * &>(unsigned __int64,ushort const * &,ushort const * &,ushort const * &)
0x140018317  jmp     loc_140018200
0x14001831c  call    ??$AsimovMyInitLocal@AEAPEBGAEAPEBGAEAPEBG@LifeTime@SpeechOneSettingsTelemetry@@QEAAX_KAEAPEBG11@Z; SpeechOneSettingsTelemetry::LifeTime::AsimovMyInitLocal<ushort const * &,ushort const * &,ushort const * &>(unsigned __int64,ushort const * &,ushort const * &,ushort const * &)
0x140018321  jmp     loc_140018200
```

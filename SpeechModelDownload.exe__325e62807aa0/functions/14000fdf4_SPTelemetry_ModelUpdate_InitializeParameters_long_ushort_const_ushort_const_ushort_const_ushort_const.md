# SPTelemetry::ModelUpdate::InitializeParameters(long,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x14000fdf4`
- end: `0x14001007d`
- name: `?InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z`
- size: `649`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14000fafc`

## callees

- `0x140005520`
- `0x140005ea0`
- `0x14000732c`
- `0x1400077b0`
- `0x14000a26c`
- `0x14000abc4`
- `0x14000acb0`
- `0x14000c1fc`
- `0x14000fdf4`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fe8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fe8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000ff08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000ff08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fe77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fe77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000feb6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000feb6`

## string_xrefs

- `0x14000ff6a`: `ModelUpdate_InitializeParameters`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::InitializeParameters(
        SPTelemetry::ModelUpdate *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rcx
  unsigned __int64 v11; // r14
  unsigned int v12; // r8d
  __int64 v13; // r8
  LARGE_INTEGER v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-60h]
  __int64 *v16; // [rsp+30h] [rbp-50h]
  const wchar_t *v17; // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v18[3])(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+38h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+40h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp+48h] BYREF

  PerformanceCount.QuadPart = (LONGLONG)a4;
  v20 = a3;
  v19 = a2;
  v17 = L"EV100";
  v8 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    v9 = 0x400000000000LL;
    if ( (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
    {
      v10 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
      if ( v10 )
        SetThreadpoolTimer(v10, (PFILETIME)this + 13, 0, 0);
      v18[1] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))((char *)this + 112);
      if ( this != (SPTelemetry::ModelUpdate *)-112LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      if ( !*((_BYTE *)this + 8) )
      {
        LOBYTE(v9) = 1;
        (**(void (__fastcall ***)(SPTelemetry::ModelUpdate *, __int64))this)(this, v9);
      }
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v11 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
      if ( `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::minSecondsBetweenEvents )
      {
        v12 = v11 / 0x989680 - `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::lastFiredEventTimeInSeconds;
        if ( v12 < `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::InitializeParameters'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovInitializeParameters_Suppressed(
            this,
            `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::numSuppressed,
            v12);
          `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::InitializeParameters'::`2'::lastFiredEventTimeInSeconds = v11 / 0x989680;
      }
      if ( !*((_BYTE *)this + 9) && !*((_BYTE *)this + 10) )
        goto LABEL_29;
      if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
      {
        Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(
          this,
          &PerformanceCount,
          "ModelUpdate_InitializeParameters",
          v11);
        v18[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,unsigned short [11],unsigned short const *,unsigned short [14],unsigned short const *,unsigned short [11],unsigned short const *,unsigned short [9],unsigned short const *>(
          (__int64)this,
          (__int64 *)v18,
          v13,
          a2,
          v15,
          (__int64 *)&v20,
          v16,
          (__int64 *)&v17);
        v18[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(this, v18);
        v14 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
        {
          PerformanceCount.QuadPart = 0;
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v14.QuadPart + 16LL))(v14);
        }
      }
      if ( *((_BYTE *)this + 10) )
        SPTelemetry::ModelUpdate::AsimovInitializeParametersLocal<long &,unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &>(
          (__int64)this,
          v11,
          (int *)&v19,
          (__int64 *)&v20,
          (__int64 *)&v17,
          (__int64 *)&a5,
          (__int64 *)&a6);
      else
LABEL_29:
        SPTelemetry::ModelUpdate::AsimovInitializeParameters<long &,unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &>(
          (__int64)this,
          v11,
          (int *)&v19,
          (__int64 *)&v20,
          (__int64 *)&v17,
          (__int64 *)&a5,
          (__int64 *)&a6);
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x14000fdf4  mov     rax, rsp
0x14000fdf7  mov     [rax+8], rbx
0x14000fdfb  mov     [rax+20h], r9
0x14000fdff  mov     [rax+18h], r8
0x14000fe03  mov     [rax+10h], edx
0x14000fe06  push    rbp
0x14000fe07  push    rsi
0x14000fe08  push    rdi
0x14000fe09  push    r14
0x14000fe0b  push    r15
0x14000fe0d  mov     rbp, rsp
0x14000fe10  sub     rsp, 80h
0x14000fe17  mov     r15d, edx
0x14000fe1a  mov     rbx, rcx
0x14000fe1d  lea     rax, aEv100; "EV100"
0x14000fe24  mov     [rbp+var_20], rax
0x14000fe28  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000fe2d  mov     r8d, [rax]
0x14000fe30  cmp     r8d, 5
0x14000fe34  jbe     loc_14000FF0E
0x14000fe3a  mov     rcx, [rax+18h]
0x14000fe3e  mov     rax, [rax+10h]
0x14000fe42  mov     rdx, 400000000000h
0x14000fe4c  test    rdx, rax
0x14000fe4f  jz      loc_14000FF0E
0x14000fe55  mov     rax, rcx
0x14000fe58  and     rax, rdx
0x14000fe5b  cmp     rax, rcx
0x14000fe5e  jnz     loc_14000FF0E
0x14000fe64  mov     rcx, [rbx+60h]; pti
0x14000fe68  test    rcx, rcx
0x14000fe6b  jz      short loc_14000FE7D
0x14000fe6d  lea     rdx, [rbx+68h]; pftDueTime
0x14000fe71  xor     r9d, r9d; msWindowLength
0x14000fe74  xor     r8d, r8d; msPeriod
0x14000fe77  call    cs:__imp_SetThreadpoolTimer
0x14000fe7d  lea     rdi, [rbx+70h]
0x14000fe81  mov     [rbp+var_10], rdi
0x14000fe85  test    rdi, rdi
0x14000fe88  jz      short loc_14000FE94
0x14000fe8a  mov     rcx, rdi; lpCriticalSection
0x14000fe8d  call    cs:__imp_EnterCriticalSection
0x14000fe93  nop
0x14000fe94  cmp     byte ptr [rbx+8], 0
0x14000fe98  jnz     short loc_14000FEAA
0x14000fe9a  mov     rax, [rbx]
0x14000fe9d  mov     dl, 1
0x14000fe9f  mov     rcx, rbx
0x14000fea2  mov     rax, [rax]
0x14000fea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000feaa  mov     qword ptr [rbp+PerformanceCount], 0
0x14000feb2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000feb6  call    cs:__imp_QueryPerformanceCounter
0x14000febc  imul    rax, qword ptr [rbp+PerformanceCount], 989680h
0x14000fec4  cqo
0x14000fec6  idiv    qword ptr [rbx+18h]
0x14000feca  mov     r14, rax
0x14000fecd  mov     ecx, cs:?minSecondsBetweenEvents@?1??InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z@4IA; uint `SPTelemetry::ModelUpdate::InitializeParameters(long,ushort const *,ushort const *,ushort const *,ushort const *)'::`2'::minSecondsBetweenEvents
0x14000fed3  test    ecx, ecx
0x14000fed5  jz      short loc_14000FF47
0x14000fed7  mov     rax, 0D6BF94D5E57A42BDh
0x14000fee1  mul     r14
0x14000fee4  mov     rsi, rdx
0x14000fee7  shr     rsi, 17h
0x14000feeb  mov     r8d, esi
0x14000feee  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z@4IA; unsigned int
0x14000fef5  cmp     r8d, ecx
0x14000fef8  jnb     short loc_14000FF25
0x14000fefa  inc     cs:?numSuppressed@?1??InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z@4IA; uint `SPTelemetry::ModelUpdate::InitializeParameters(long,ushort const *,ushort const *,ushort const *,ushort const *)'::`2'::numSuppressed
0x14000ff00  test    rdi, rdi
0x14000ff03  jz      short loc_14000FF0E
0x14000ff05  mov     rcx, rdi; lpCriticalSection
0x14000ff08  call    cs:__imp_LeaveCriticalSection
0x14000ff0e  mov     rbx, [rsp+80h+arg_0]
0x14000ff16  add     rsp, 80h
0x14000ff1d  pop     r15
0x14000ff1f  pop     r14
0x14000ff21  pop     rdi
0x14000ff22  pop     rsi
0x14000ff23  pop     rbp
0x14000ff24  retn
0x14000ff25  mov     edx, cs:?numSuppressed@?1??InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z@4IA; unsigned int
0x14000ff2b  test    edx, edx
0x14000ff2d  jz      short loc_14000FF41
0x14000ff2f  mov     rcx, rbx; this
0x14000ff32  call    ?AsimovInitializeParameters_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovInitializeParameters_Suppressed(uint,uint)
0x14000ff37  mov     cs:?numSuppressed@?1??InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::InitializeParameters(long,ushort const *,ushort const *,ushort const *,ushort const *)'::`2'::numSuppressed
0x14000ff41  mov     cs:?lastFiredEventTimeInSeconds@?1??InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::InitializeParameters(long,ushort const *,ushort const *,ushort const *,ushort const *)'::`2'::lastFiredEventTimeInSeconds
0x14000ff47  cmp     byte ptr [rbx+9], 0
0x14000ff4b  jnz     short loc_14000FF57
0x14000ff4d  cmp     byte ptr [rbx+0Ah], 0
0x14000ff51  jz      loc_140010016
0x14000ff57  mov     rcx, rbx; this
0x14000ff5a  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x14000ff5f  test    eax, eax
0x14000ff61  js      loc_140010010
0x14000ff67  mov     r9, r14
0x14000ff6a  lea     r8, aModelupdateIni; "ModelUpdate_InitializeParameters"
0x14000ff71  lea     rdx, [rbp+PerformanceCount]
0x14000ff75  mov     rcx, rbx
0x14000ff78  call    ?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z; Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)
0x14000ff7d  nop
0x14000ff7e  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000ff82  mov     [rbp+var_18], rcx
0x14000ff86  test    rcx, rcx
0x14000ff89  jz      short loc_14000FF98
0x14000ff8b  mov     rax, [rcx]
0x14000ff8e  mov     rax, [rax+8]
0x14000ff92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff97  nop
0x14000ff98  lea     rax, [rbp+arg_28]
0x14000ff9c  mov     [rsp+80h+var_28], rax
0x14000ffa1  lea     rax, [rbp+arg_20]
0x14000ffa5  mov     [rsp+80h+var_38], rax
0x14000ffaa  lea     rax, [rbp+var_20]
0x14000ffae  mov     [rsp+80h+var_48], rax
0x14000ffb3  lea     rax, [rbp+arg_10]
0x14000ffb7  mov     [rsp+80h+var_58], rax
0x14000ffbc  mov     r9d, r15d
0x14000ffbf  lea     rdx, [rbp+var_18]
0x14000ffc3  mov     rcx, rbx
0x14000ffc6  call    ??$AddColumnToCoalescedEvent@J$$BY0L@GPEBG$$BY0O@GPEBG$$BY0L@GPEBG$$BY08GPEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJAEAY0L@$$CBGAEBQEBGAEAY0O@$$CBG323AEAY08$$CBG3@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,ushort [11],ushort const *,ushort [14],ushort const *,ushort [11],ushort const *,ushort [9],ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long,ushort const (&)[11],ushort const * const &,ushort const (&)[14],ushort const * const &,ushort const (&)[11],ushort const * const &,ushort const (&)[9],ushort const * const &)
0x14000ffcb  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000ffcf  mov     [rbp+var_18], rcx
0x14000ffd3  test    rcx, rcx
0x14000ffd6  jz      short loc_14000FFE5
0x14000ffd8  mov     rax, [rcx]
0x14000ffdb  mov     rax, [rax+8]
0x14000ffdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffe4  nop
0x14000ffe5  lea     rdx, [rbp+var_18]
0x14000ffe9  mov     rcx, rbx
0x14000ffec  call    ?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x14000fff1  nop
0x14000fff2  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000fff6  test    rcx, rcx
0x14000fff9  jz      short loc_140010010
0x14000fffb  mov     qword ptr [rbp+PerformanceCount], 0
0x140010003  mov     rax, [rcx]
0x140010006  mov     rax, [rax+10h]
0x14001000a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001000f  nop
0x140010010  cmp     byte ptr [rbx+0Ah], 0
0x140010014  jnz     short loc_140010049
0x140010016  lea     rax, [rbp+arg_28]
0x14001001a  mov     [rsp+80h+var_50], rax
0x14001001f  lea     rax, [rbp+arg_20]
0x140010023  mov     [rsp+80h+var_58], rax
0x140010028  lea     rax, [rbp+var_20]
0x14001002c  mov     [rsp+80h+var_60], rax
0x140010031  lea     r9, [rbp+arg_10]
0x140010035  lea     r8, [rbp+arg_8]
0x140010039  mov     rdx, r14
0x14001003c  mov     rcx, rbx
0x14001003f  call    ??$AsimovInitializeParameters@AEAJAEAPEBGAEAPEBGAEAPEBGAEAPEBG@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAPEBG222@Z; SPTelemetry::ModelUpdate::AsimovInitializeParameters<long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &>(unsigned __int64,long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &)
0x140010044  jmp     loc_14000FF00
0x140010049  lea     rax, [rbp+arg_28]
0x14001004d  mov     [rsp+80h+var_50], rax
0x140010052  lea     rax, [rbp+arg_20]
0x140010056  mov     [rsp+80h+var_58], rax
0x14001005b  lea     rax, [rbp+var_20]
0x14001005f  mov     [rsp+80h+var_60], rax
0x140010064  lea     r9, [rbp+arg_10]
0x140010068  lea     r8, [rbp+arg_8]
0x14001006c  mov     rdx, r14
0x14001006f  mov     rcx, rbx
0x140010072  call    ??$AsimovInitializeParametersLocal@AEAJAEAPEBGAEAPEBGAEAPEBGAEAPEBG@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAPEBG222@Z; SPTelemetry::ModelUpdate::AsimovInitializeParametersLocal<long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &>(unsigned __int64,long &,ushort const * &,ushort const * &,ushort const * &,ushort const * &)
0x140010077  jmp     loc_14000FF00
```

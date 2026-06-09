# SPTelemetry::ModelUpdate::End(long)

- ea: `0x14000e340`
- end: `0x14000e4c2`
- name: `?End@ModelUpdate@SPTelemetry@@QEAAXJ@Z`
- size: `386`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *__hidden this, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`

## callees

- `0x140003c64`
- `0x1400077b0`
- `0x14000aa08`
- `0x14000aaec`
- `0x14000c124`
- `0x14000e340`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e3b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e3b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e435`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e435`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e3a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e3a0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000e3e2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000e3e2`

## string_xrefs

- `0x14000e486`: `ModelUpdate_End`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::End(SPTelemetry::ModelUpdate *this, int a2)
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
      if ( `SPTelemetry::ModelUpdate::End'::`2'::minSecondsBetweenEvents )
      {
        v8 = v7 / 0x989680 - `SPTelemetry::ModelUpdate::End'::`2'::lastFiredEventTimeInSeconds;
        if ( v8 < `SPTelemetry::ModelUpdate::End'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::End'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::End'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovEnd_Suppressed(this, `SPTelemetry::ModelUpdate::End'::`2'::numSuppressed, v8);
          `SPTelemetry::ModelUpdate::End'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::End'::`2'::lastFiredEventTimeInSeconds = v7 / 0x989680;
      }
      v9 = (char *)this + 10;
      if ( (*((_BYTE *)this + 9) || *v9)
        && (Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<unsigned short [3],long>(
              (_DWORD)this,
              (unsigned int)"ModelUpdate_End",
              v7,
              v6,
              (__int64)&v10),
            *v9) )
      {
        SPTelemetry::ModelUpdate::AsimovEndLocal<long &>((__int64)this, v7, &v10);
      }
      else
      {
        SPTelemetry::ModelUpdate::AsimovEnd<long &>((__int64)this, v7, &v10);
      }
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x14000e340  mov     [rsp+arg_0], rbx
0x14000e345  mov     [rsp+arg_8], edx
0x14000e349  push    rbp
0x14000e34a  push    rsi
0x14000e34b  push    rdi
0x14000e34c  sub     rsp, 30h
0x14000e350  mov     rbx, rcx
0x14000e353  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000e358  mov     edx, [rax]
0x14000e35a  cmp     edx, 5
0x14000e35d  jbe     loc_14000E43B
0x14000e363  mov     rcx, [rax+18h]
0x14000e367  mov     rax, [rax+10h]
0x14000e36b  mov     rdx, 400000000000h
0x14000e375  test    rdx, rax
0x14000e378  jz      loc_14000E43B
0x14000e37e  mov     rax, rcx
0x14000e381  and     rax, rdx
0x14000e384  cmp     rax, rcx
0x14000e387  jnz     loc_14000E43B
0x14000e38d  mov     rcx, [rbx+60h]; pti
0x14000e391  test    rcx, rcx
0x14000e394  jz      short loc_14000E3A6
0x14000e396  lea     rdx, [rbx+68h]; pftDueTime
0x14000e39a  xor     r9d, r9d; msWindowLength
0x14000e39d  xor     r8d, r8d; msPeriod
0x14000e3a0  call    cs:__imp_SetThreadpoolTimer
0x14000e3a6  lea     rdi, [rbx+70h]
0x14000e3aa  mov     [rsp+48h+arg_18], rdi
0x14000e3af  test    rdi, rdi
0x14000e3b2  jz      short loc_14000E3BE
0x14000e3b4  mov     rcx, rdi; lpCriticalSection
0x14000e3b7  call    cs:__imp_EnterCriticalSection
0x14000e3bd  nop
0x14000e3be  cmp     byte ptr [rbx+8], 0
0x14000e3c2  jnz     short loc_14000E3D4
0x14000e3c4  mov     rax, [rbx]
0x14000e3c7  mov     dl, 1
0x14000e3c9  mov     rcx, rbx
0x14000e3cc  mov     rax, [rax]
0x14000e3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3d4  mov     qword ptr [rsp+48h+PerformanceCount], 0
0x14000e3dd  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x14000e3e2  call    cs:__imp_QueryPerformanceCounter
0x14000e3e8  imul    rax, qword ptr [rsp+48h+PerformanceCount], 989680h
0x14000e3f1  cqo
0x14000e3f3  idiv    qword ptr [rbx+18h]
0x14000e3f7  mov     rbp, rax
0x14000e3fa  mov     ecx, cs:?minSecondsBetweenEvents@?1??End@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; uint `SPTelemetry::ModelUpdate::End(long)'::`2'::minSecondsBetweenEvents
0x14000e400  test    ecx, ecx
0x14000e402  jz      short loc_14000E46A
0x14000e404  mov     rax, 0D6BF94D5E57A42BDh
0x14000e40e  mul     rbp
0x14000e411  mov     rsi, rdx
0x14000e414  shr     rsi, 17h
0x14000e418  mov     r8d, esi
0x14000e41b  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??End@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; unsigned int
0x14000e422  cmp     r8d, ecx
0x14000e425  jnb     short loc_14000E448
0x14000e427  inc     cs:?numSuppressed@?1??End@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; uint `SPTelemetry::ModelUpdate::End(long)'::`2'::numSuppressed
0x14000e42d  test    rdi, rdi
0x14000e430  jz      short loc_14000E43B
0x14000e432  mov     rcx, rdi; lpCriticalSection
0x14000e435  call    cs:__imp_LeaveCriticalSection
0x14000e43b  mov     rbx, [rsp+48h+arg_0]
0x14000e440  add     rsp, 30h
0x14000e444  pop     rdi
0x14000e445  pop     rsi
0x14000e446  pop     rbp
0x14000e447  retn
0x14000e448  mov     edx, cs:?numSuppressed@?1??End@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; unsigned int
0x14000e44e  test    edx, edx
0x14000e450  jz      short loc_14000E464
0x14000e452  mov     rcx, rbx; this
0x14000e455  call    ?AsimovEnd_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovEnd_Suppressed(uint,uint)
0x14000e45a  mov     cs:?numSuppressed@?1??End@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::End(long)'::`2'::numSuppressed
0x14000e464  mov     cs:?lastFiredEventTimeInSeconds@?1??End@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::End(long)'::`2'::lastFiredEventTimeInSeconds
0x14000e46a  lea     rsi, [rbx+0Ah]
0x14000e46e  cmp     byte ptr [rbx+9], 0
0x14000e472  jnz     short loc_14000E479
0x14000e474  cmp     byte ptr [rsi], 0
0x14000e477  jz      short loc_14000E49A
0x14000e479  lea     rax, [rsp+48h+arg_8]
0x14000e47e  mov     [rsp+48h+var_28], rax
0x14000e483  mov     r8, rbp
0x14000e486  lea     rdx, aModelupdateEnd; "ModelUpdate_End"
0x14000e48d  mov     rcx, rbx
0x14000e490  call    ??$AddEventToEventQueue@$$BY02GJ@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_KAEAY02$$CBGAEBJ@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<ushort [3],long>(char const *,unsigned __int64,ushort const (&)[3],long const &)
0x14000e495  cmp     byte ptr [rsi], 0
0x14000e498  jnz     short loc_14000E4AC
0x14000e49a  lea     r8, [rsp+48h+arg_8]
0x14000e49f  mov     rdx, rbp
0x14000e4a2  mov     rcx, rbx
0x14000e4a5  call    ??$AsimovEnd@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z; SPTelemetry::ModelUpdate::AsimovEnd<long &>(unsigned __int64,long &)
0x14000e4aa  jmp     short loc_14000E42D
0x14000e4ac  lea     r8, [rsp+48h+arg_8]
0x14000e4b1  mov     rdx, rbp
0x14000e4b4  mov     rcx, rbx
0x14000e4b7  call    ??$AsimovEndLocal@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z; SPTelemetry::ModelUpdate::AsimovEndLocal<long &>(unsigned __int64,long &)
0x14000e4bc  jmp     loc_14000E42D
```

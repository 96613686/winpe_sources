# SPTelemetry::ModelUpdate::DownloadMetadata(long)

- ea: `0x14000d41c`
- end: `0x14000d59e`
- name: `?DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z`
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
- `0x14000a84c`
- `0x14000a930`
- `0x14000c04c`
- `0x14000d41c`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d493`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d511`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d47c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d47c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d4be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d4be`

## string_xrefs

- `0x14000d562`: `ModelUpdate_DownloadMetadata`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::DownloadMetadata(SPTelemetry::ModelUpdate *this, int a2)
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
      if ( `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::minSecondsBetweenEvents )
      {
        v8 = v7 / 0x989680 - `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::lastFiredEventTimeInSeconds;
        if ( v8 < `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovDownloadMetadata_Suppressed(
            this,
            `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::numSuppressed,
            v8);
          `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::DownloadMetadata'::`2'::lastFiredEventTimeInSeconds = v7 / 0x989680;
      }
      v9 = (char *)this + 10;
      if ( (*((_BYTE *)this + 9) || *v9)
        && (Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<unsigned short [3],long>(
              (_DWORD)this,
              (unsigned int)"ModelUpdate_DownloadMetadata",
              v7,
              v6,
              (__int64)&v10),
            *v9) )
      {
        SPTelemetry::ModelUpdate::AsimovDownloadMetadataLocal<long &>((__int64)this, v7, &v10);
      }
      else
      {
        SPTelemetry::ModelUpdate::AsimovDownloadMetadata<long &>((__int64)this, v7, &v10);
      }
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x14000d41c  mov     [rsp+arg_0], rbx
0x14000d421  mov     [rsp+arg_8], edx
0x14000d425  push    rbp
0x14000d426  push    rsi
0x14000d427  push    rdi
0x14000d428  sub     rsp, 30h
0x14000d42c  mov     rbx, rcx
0x14000d42f  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000d434  mov     edx, [rax]
0x14000d436  cmp     edx, 5
0x14000d439  jbe     loc_14000D517
0x14000d43f  mov     rcx, [rax+18h]
0x14000d443  mov     rax, [rax+10h]
0x14000d447  mov     rdx, 400000000000h
0x14000d451  test    rdx, rax
0x14000d454  jz      loc_14000D517
0x14000d45a  mov     rax, rcx
0x14000d45d  and     rax, rdx
0x14000d460  cmp     rax, rcx
0x14000d463  jnz     loc_14000D517
0x14000d469  mov     rcx, [rbx+60h]; pti
0x14000d46d  test    rcx, rcx
0x14000d470  jz      short loc_14000D482
0x14000d472  lea     rdx, [rbx+68h]; pftDueTime
0x14000d476  xor     r9d, r9d; msWindowLength
0x14000d479  xor     r8d, r8d; msPeriod
0x14000d47c  call    cs:__imp_SetThreadpoolTimer
0x14000d482  lea     rdi, [rbx+70h]
0x14000d486  mov     [rsp+48h+arg_18], rdi
0x14000d48b  test    rdi, rdi
0x14000d48e  jz      short loc_14000D49A
0x14000d490  mov     rcx, rdi; lpCriticalSection
0x14000d493  call    cs:__imp_EnterCriticalSection
0x14000d499  nop
0x14000d49a  cmp     byte ptr [rbx+8], 0
0x14000d49e  jnz     short loc_14000D4B0
0x14000d4a0  mov     rax, [rbx]
0x14000d4a3  mov     dl, 1
0x14000d4a5  mov     rcx, rbx
0x14000d4a8  mov     rax, [rax]
0x14000d4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4b0  mov     qword ptr [rsp+48h+PerformanceCount], 0
0x14000d4b9  lea     rcx, [rsp+48h+PerformanceCount]; lpPerformanceCount
0x14000d4be  call    cs:__imp_QueryPerformanceCounter
0x14000d4c4  imul    rax, qword ptr [rsp+48h+PerformanceCount], 989680h
0x14000d4cd  cqo
0x14000d4cf  idiv    qword ptr [rbx+18h]
0x14000d4d3  mov     rbp, rax
0x14000d4d6  mov     ecx, cs:?minSecondsBetweenEvents@?1??DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; uint `SPTelemetry::ModelUpdate::DownloadMetadata(long)'::`2'::minSecondsBetweenEvents
0x14000d4dc  test    ecx, ecx
0x14000d4de  jz      short loc_14000D546
0x14000d4e0  mov     rax, 0D6BF94D5E57A42BDh
0x14000d4ea  mul     rbp
0x14000d4ed  mov     rsi, rdx
0x14000d4f0  shr     rsi, 17h
0x14000d4f4  mov     r8d, esi
0x14000d4f7  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; unsigned int
0x14000d4fe  cmp     r8d, ecx
0x14000d501  jnb     short loc_14000D524
0x14000d503  inc     cs:?numSuppressed@?1??DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; uint `SPTelemetry::ModelUpdate::DownloadMetadata(long)'::`2'::numSuppressed
0x14000d509  test    rdi, rdi
0x14000d50c  jz      short loc_14000D517
0x14000d50e  mov     rcx, rdi; lpCriticalSection
0x14000d511  call    cs:__imp_LeaveCriticalSection
0x14000d517  mov     rbx, [rsp+48h+arg_0]
0x14000d51c  add     rsp, 30h
0x14000d520  pop     rdi
0x14000d521  pop     rsi
0x14000d522  pop     rbp
0x14000d523  retn
0x14000d524  mov     edx, cs:?numSuppressed@?1??DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA; unsigned int
0x14000d52a  test    edx, edx
0x14000d52c  jz      short loc_14000D540
0x14000d52e  mov     rcx, rbx; this
0x14000d531  call    ?AsimovDownloadMetadata_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovDownloadMetadata_Suppressed(uint,uint)
0x14000d536  mov     cs:?numSuppressed@?1??DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::DownloadMetadata(long)'::`2'::numSuppressed
0x14000d540  mov     cs:?lastFiredEventTimeInSeconds@?1??DownloadMetadata@ModelUpdate@SPTelemetry@@QEAAXJ@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::DownloadMetadata(long)'::`2'::lastFiredEventTimeInSeconds
0x14000d546  lea     rsi, [rbx+0Ah]
0x14000d54a  cmp     byte ptr [rbx+9], 0
0x14000d54e  jnz     short loc_14000D555
0x14000d550  cmp     byte ptr [rsi], 0
0x14000d553  jz      short loc_14000D576
0x14000d555  lea     rax, [rsp+48h+arg_8]
0x14000d55a  mov     [rsp+48h+var_28], rax
0x14000d55f  mov     r8, rbp
0x14000d562  lea     rdx, aModelupdateDow; "ModelUpdate_DownloadMetadata"
0x14000d569  mov     rcx, rbx
0x14000d56c  call    ??$AddEventToEventQueue@$$BY02GJ@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_KAEAY02$$CBGAEBJ@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<ushort [3],long>(char const *,unsigned __int64,ushort const (&)[3],long const &)
0x14000d571  cmp     byte ptr [rsi], 0
0x14000d574  jnz     short loc_14000D588
0x14000d576  lea     r8, [rsp+48h+arg_8]
0x14000d57b  mov     rdx, rbp
0x14000d57e  mov     rcx, rbx
0x14000d581  call    ??$AsimovDownloadMetadata@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z; SPTelemetry::ModelUpdate::AsimovDownloadMetadata<long &>(unsigned __int64,long &)
0x14000d586  jmp     short loc_14000D509
0x14000d588  lea     r8, [rsp+48h+arg_8]
0x14000d58d  mov     rdx, rbp
0x14000d590  mov     rcx, rbx
0x14000d593  call    ??$AsimovDownloadMetadataLocal@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z; SPTelemetry::ModelUpdate::AsimovDownloadMetadataLocal<long &>(unsigned __int64,long &)
0x14000d598  jmp     loc_14000D509
```

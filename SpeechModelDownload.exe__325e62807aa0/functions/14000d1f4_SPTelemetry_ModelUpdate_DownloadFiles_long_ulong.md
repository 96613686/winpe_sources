# SPTelemetry::ModelUpdate::DownloadFiles(long,ulong)

- ea: `0x14000d1f4`
- end: `0x14000d414`
- name: `?DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z`
- size: `544`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, unsigned int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14000d5a4`

## callees

- `0x140005520`
- `0x140005ea0`
- `0x14000732c`
- `0x1400077b0`
- `0x14000a3b0`
- `0x14000a718`
- `0x14000a7b8`
- `0x14000bf74`
- `0x14000d1f4`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d27b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d27b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d2f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d2f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d265`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d265`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d2a4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000d2a4`

## string_xrefs

- `0x14000d352`: `ModelUpdate_DownloadFiles`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::DownloadFiles(SPTelemetry::ModelUpdate *this, unsigned int a2, int a3)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  struct _TP_TIMER *v7; // rcx
  unsigned __int64 v8; // r14
  unsigned int v9; // r8d
  __int64 v10; // r8
  LARGE_INTEGER v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-20h]
  __int64 (__fastcall ***v13[2])(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+78h] [rbp+38h] BYREF
  int v15; // [rsp+80h] [rbp+40h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp+48h] BYREF

  v15 = a3;
  v14 = a2;
  v5 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    v6 = 0x400000000000LL;
    if ( (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v5 + 3) & 0x400000000000LL) == *((_QWORD *)v5 + 3) )
    {
      v7 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
      if ( v7 )
        SetThreadpoolTimer(v7, (PFILETIME)this + 13, 0, 0);
      v13[1] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))((char *)this + 112);
      if ( this != (SPTelemetry::ModelUpdate *)-112LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      if ( !*((_BYTE *)this + 8) )
      {
        LOBYTE(v6) = 1;
        (**(void (__fastcall ***)(SPTelemetry::ModelUpdate *, __int64))this)(this, v6);
      }
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v8 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
      if ( `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::minSecondsBetweenEvents )
      {
        v9 = v8 / 0x989680 - `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::lastFiredEventTimeInSeconds;
        if ( v9 < `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::minSecondsBetweenEvents )
        {
          ++`SPTelemetry::ModelUpdate::DownloadFiles'::`2'::numSuppressed;
LABEL_13:
          if ( this != (SPTelemetry::ModelUpdate *)-112LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
          return;
        }
        if ( `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::numSuppressed )
        {
          SPTelemetry::ModelUpdate::AsimovDownloadFiles_Suppressed(
            this,
            `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::numSuppressed,
            v9);
          `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::numSuppressed = 0;
        }
        `SPTelemetry::ModelUpdate::DownloadFiles'::`2'::lastFiredEventTimeInSeconds = v8 / 0x989680;
      }
      if ( !*((_BYTE *)this + 9) && !*((_BYTE *)this + 10) )
        goto LABEL_29;
      if ( (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
      {
        Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(
          this,
          &PerformanceCount,
          "ModelUpdate_DownloadFiles",
          v8);
        v13[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,unsigned short [14],unsigned long>(
          (__int64)this,
          (__int64 *)v13,
          v10,
          a2,
          v12);
        v13[0] = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
        if ( PerformanceCount.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
        Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(this, v13);
        v11 = PerformanceCount;
        if ( PerformanceCount.QuadPart )
        {
          PerformanceCount.QuadPart = 0;
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v11.QuadPart + 16LL))(v11);
        }
      }
      if ( *((_BYTE *)this + 10) )
        SPTelemetry::ModelUpdate::AsimovDownloadFilesLocal<long &,unsigned long &>((__int64)this, v8, (int *)&v14, &v15);
      else
LABEL_29:
        SPTelemetry::ModelUpdate::AsimovDownloadFiles<long &,unsigned long &>((__int64)this, v8, (int *)&v14, &v15);
      goto LABEL_13;
    }
  }
}

```

## disassembly

```asm
0x14000d1f4  mov     [rsp-28h+arg_0], rbx
0x14000d1f9  mov     [rsp-28h+arg_10], r8d
0x14000d1fe  mov     [rsp-28h+arg_8], edx
0x14000d202  push    rbp
0x14000d203  push    rsi
0x14000d204  push    rdi
0x14000d205  push    r14
0x14000d207  push    r15
0x14000d209  mov     rbp, rsp
0x14000d20c  sub     rsp, 40h
0x14000d210  mov     r15d, edx
0x14000d213  mov     rbx, rcx
0x14000d216  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000d21b  mov     r8d, [rax]
0x14000d21e  cmp     r8d, 5
0x14000d222  jbe     loc_14000D2FC
0x14000d228  mov     rcx, [rax+18h]
0x14000d22c  mov     rax, [rax+10h]
0x14000d230  mov     rdx, 400000000000h
0x14000d23a  test    rdx, rax
0x14000d23d  jz      loc_14000D2FC
0x14000d243  mov     rax, rcx
0x14000d246  and     rax, rdx
0x14000d249  cmp     rax, rcx
0x14000d24c  jnz     loc_14000D2FC
0x14000d252  mov     rcx, [rbx+60h]; pti
0x14000d256  test    rcx, rcx
0x14000d259  jz      short loc_14000D26B
0x14000d25b  lea     rdx, [rbx+68h]; pftDueTime
0x14000d25f  xor     r9d, r9d; msWindowLength
0x14000d262  xor     r8d, r8d; msPeriod
0x14000d265  call    cs:__imp_SetThreadpoolTimer
0x14000d26b  lea     rdi, [rbx+70h]
0x14000d26f  mov     [rbp+var_8], rdi
0x14000d273  test    rdi, rdi
0x14000d276  jz      short loc_14000D282
0x14000d278  mov     rcx, rdi; lpCriticalSection
0x14000d27b  call    cs:__imp_EnterCriticalSection
0x14000d281  nop
0x14000d282  cmp     byte ptr [rbx+8], 0
0x14000d286  jnz     short loc_14000D298
0x14000d288  mov     rax, [rbx]
0x14000d28b  mov     dl, 1
0x14000d28d  mov     rcx, rbx
0x14000d290  mov     rax, [rax]
0x14000d293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d298  mov     qword ptr [rbp+PerformanceCount], 0
0x14000d2a0  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000d2a4  call    cs:__imp_QueryPerformanceCounter
0x14000d2aa  imul    rax, qword ptr [rbp+PerformanceCount], 989680h
0x14000d2b2  cqo
0x14000d2b4  idiv    qword ptr [rbx+18h]
0x14000d2b8  mov     r14, rax
0x14000d2bb  mov     ecx, cs:?minSecondsBetweenEvents@?1??DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z@4IA; uint `SPTelemetry::ModelUpdate::DownloadFiles(long,ulong)'::`2'::minSecondsBetweenEvents
0x14000d2c1  test    ecx, ecx
0x14000d2c3  jz      short loc_14000D32F
0x14000d2c5  mov     rax, 0D6BF94D5E57A42BDh
0x14000d2cf  mul     r14
0x14000d2d2  mov     rsi, rdx
0x14000d2d5  shr     rsi, 17h
0x14000d2d9  mov     r8d, esi
0x14000d2dc  sub     r8d, cs:?lastFiredEventTimeInSeconds@?1??DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z@4IA; unsigned int
0x14000d2e3  cmp     r8d, ecx
0x14000d2e6  jnb     short loc_14000D30D
0x14000d2e8  inc     cs:?numSuppressed@?1??DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z@4IA; uint `SPTelemetry::ModelUpdate::DownloadFiles(long,ulong)'::`2'::numSuppressed
0x14000d2ee  test    rdi, rdi
0x14000d2f1  jz      short loc_14000D2FC
0x14000d2f3  mov     rcx, rdi; lpCriticalSection
0x14000d2f6  call    cs:__imp_LeaveCriticalSection
0x14000d2fc  mov     rbx, [rsp+40h+arg_0]
0x14000d301  add     rsp, 40h
0x14000d305  pop     r15
0x14000d307  pop     r14
0x14000d309  pop     rdi
0x14000d30a  pop     rsi
0x14000d30b  pop     rbp
0x14000d30c  retn
0x14000d30d  mov     edx, cs:?numSuppressed@?1??DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z@4IA; unsigned int
0x14000d313  test    edx, edx
0x14000d315  jz      short loc_14000D329
0x14000d317  mov     rcx, rbx; this
0x14000d31a  call    ?AsimovDownloadFiles_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z; SPTelemetry::ModelUpdate::AsimovDownloadFiles_Suppressed(uint,uint)
0x14000d31f  mov     cs:?numSuppressed@?1??DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z@4IA, 0; uint `SPTelemetry::ModelUpdate::DownloadFiles(long,ulong)'::`2'::numSuppressed
0x14000d329  mov     cs:?lastFiredEventTimeInSeconds@?1??DownloadFiles@ModelUpdate@SPTelemetry@@QEAAXJK@Z@4IA, esi; uint `SPTelemetry::ModelUpdate::DownloadFiles(long,ulong)'::`2'::lastFiredEventTimeInSeconds
0x14000d32f  cmp     byte ptr [rbx+9], 0
0x14000d333  jnz     short loc_14000D33F
0x14000d335  cmp     byte ptr [rbx+0Ah], 0
0x14000d339  jz      loc_14000D3E3
0x14000d33f  mov     rcx, rbx; this
0x14000d342  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x14000d347  test    eax, eax
0x14000d349  js      loc_14000D3DD
0x14000d34f  mov     r9, r14
0x14000d352  lea     r8, aModelupdateDow_0; "ModelUpdate_DownloadFiles"
0x14000d359  lea     rdx, [rbp+PerformanceCount]
0x14000d35d  mov     rcx, rbx
0x14000d360  call    ?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z; Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)
0x14000d365  nop
0x14000d366  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000d36a  mov     [rbp+var_10], rcx
0x14000d36e  test    rcx, rcx
0x14000d371  jz      short loc_14000D380
0x14000d373  mov     rax, [rcx]
0x14000d376  mov     rax, [rax+8]
0x14000d37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d37f  nop
0x14000d380  lea     rax, [rbp+arg_10]
0x14000d384  mov     [rsp+40h+var_18], rax
0x14000d389  mov     r9d, r15d
0x14000d38c  lea     rdx, [rbp+var_10]
0x14000d390  mov     rcx, rbx
0x14000d393  call    ??$AddColumnToCoalescedEvent@J$$BY0O@GK@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJAEAY0O@$$CBGAEBK@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,ushort [14],ulong>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long,ushort const (&)[14],ulong const &)
0x14000d398  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000d39c  mov     [rbp+var_10], rcx
0x14000d3a0  test    rcx, rcx
0x14000d3a3  jz      short loc_14000D3B2
0x14000d3a5  mov     rax, [rcx]
0x14000d3a8  mov     rax, [rax+8]
0x14000d3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3b1  nop
0x14000d3b2  lea     rdx, [rbp+var_10]
0x14000d3b6  mov     rcx, rbx
0x14000d3b9  call    ?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x14000d3be  nop
0x14000d3bf  mov     rcx, qword ptr [rbp+PerformanceCount]
0x14000d3c3  test    rcx, rcx
0x14000d3c6  jz      short loc_14000D3DD
0x14000d3c8  mov     qword ptr [rbp+PerformanceCount], 0
0x14000d3d0  mov     rax, [rcx]
0x14000d3d3  mov     rax, [rax+10h]
0x14000d3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d3dc  nop
0x14000d3dd  cmp     byte ptr [rbx+0Ah], 0
0x14000d3e1  jnz     short loc_14000D3FB
0x14000d3e3  lea     r9, [rbp+arg_10]
0x14000d3e7  lea     r8, [rbp+arg_8]
0x14000d3eb  mov     rdx, r14
0x14000d3ee  mov     rcx, rbx
0x14000d3f1  call    ??$AsimovDownloadFiles@AEAJAEAK@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAK@Z; SPTelemetry::ModelUpdate::AsimovDownloadFiles<long &,ulong &>(unsigned __int64,long &,ulong &)
0x14000d3f6  jmp     loc_14000D2EE
0x14000d3fb  lea     r9, [rbp+arg_10]
0x14000d3ff  lea     r8, [rbp+arg_8]
0x14000d403  mov     rdx, r14
0x14000d406  mov     rcx, rbx
0x14000d409  call    ??$AsimovDownloadFilesLocal@AEAJAEAK@ModelUpdate@SPTelemetry@@QEAAX_KAEAJAEAK@Z; SPTelemetry::ModelUpdate::AsimovDownloadFilesLocal<long &,ulong &>(unsigned __int64,long &,ulong &)
0x14000d40e  jmp     loc_14000D2EE
```

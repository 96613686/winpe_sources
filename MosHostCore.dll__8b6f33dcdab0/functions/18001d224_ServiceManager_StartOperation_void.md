# ServiceManager::StartOperation(void)

- ea: `0x18001d224`
- end: `0x18001d5bd`
- name: `?StartOperation@ServiceManager@@AEAAJXZ`
- size: `921`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update`

## callers

- `0x18001b068`

## callees

- `0x180003884`
- `0x180003f64`
- `0x18000fee8`
- `0x18001217c`
- `0x18001400c`
- `0x180015ed0`
- `0x180017e00`
- `0x18001ba6c`
- `0x18001d224`
- `0x18001d5c4`
- `0x18001db8c`
- `0x18001edb0`
- `0x18001eec4`
- `0x18001f554`
- `0x18001f650`
- `0x18002110c`
- `0x180022658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d37b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d414`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d414`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001d371`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001d371`
- `MosStorage!MosStorageResetPreferredLocationIfNotPresent` at `0x18001d4f6`
- `MosStorage!MosStorageResetPreferredLocationIfNotPresent` at `0x18001d4f6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001d4c3`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001d54e`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001d4c3`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001d54e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001d512`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001d512`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d2a8`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d2a8`

## string_xrefs

- `0x18001d2a1`: `ServiceManager::StartOperation`
- `0x18001d4ba`: `ServiceManager::StartOperation`
- `0x18001d509`: `ServiceManager::StartOperation`
- `0x18001d545`: `ServiceManager::StartOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceManager::StartOperation(ServiceManager *this)
{
  char v2; // bp
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rax
  void *v7; // rax
  int v8; // r8d
  int v9; // ecx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  void *v16; // rax
  int v17; // esi
  __int64 v18; // rax
  unsigned int v19; // edi
  signed int LastError; // eax
  int v21; // ecx
  int updated; // eax
  int v23; // r8d
  int v24; // eax
  int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  void *v29; // [rsp+50h] [rbp+8h] BYREF
  void *v30; // [rsp+58h] [rbp+10h] BYREF

  v30 = 0;
  v29 = 0;
  v2 = 0;
  v3 = *((_QWORD *)this + 435);
  v4 = *((_QWORD *)this + 434);
  if ( v4 != v3 )
  {
    v5 = (v3 - v4) >> 2;
    v6 = 4 * v5;
    if ( !is_mul_ok(v5, 4u) )
      v6 = -1;
    v7 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v7;
    if ( !v7 )
    {
      v8 = 2405;
LABEL_6:
      v9 = -2147024882;
LABEL_7:
      v10 = ZTraceReportOrigination(v9, "ServiceManager::StartOperation", v8, this);
      goto LABEL_50;
    }
    memcpy_0(
      v7,
      *((const void **)this + 434),
      (*((_QWORD *)this + 435) - *((_QWORD *)this + 434)) & 0xFFFFFFFFFFFFFFFCuLL);
  }
  v12 = *((_QWORD *)this + 438);
  v13 = *((_QWORD *)this + 437);
  if ( v13 != v12 )
  {
    v14 = (v12 - v13) >> 2;
    v15 = 4 * v14;
    if ( !is_mul_ok(v14, 4u) )
      v15 = -1;
    v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v16;
    if ( !v16 )
    {
      v8 = 2412;
      goto LABEL_6;
    }
    memcpy_0(
      v16,
      *((const void **)this + 437),
      (*((_QWORD *)this + 438) - *((_QWORD *)this + 437)) & 0xFFFFFFFFFFFFFFFCuLL);
  }
  v17 = 3;
  *((_DWORD *)this + 881) = 3;
  v18 = *((_QWORD *)this + 438);
  if ( *((_QWORD *)this + 434) == *((_QWORD *)this + 435) )
  {
    if ( *((_QWORD *)this + 437) == v18 )
    {
      *((_DWORD *)this + 880) = 3;
      v19 = 5;
      goto LABEL_18;
    }
  }
  else if ( *((_QWORD *)this + 437) == v18 )
  {
    v19 = 3;
    v21 = 1;
    goto LABEL_27;
  }
  if ( *((_QWORD *)this + 437) == *((_QWORD *)this + 438) )
    __int2c();
  v19 = 4;
  v21 = 2;
LABEL_27:
  *((_DWORD *)this + 880) = v21;
  updated = PackageManager::OnOperationStarted((ServiceManager *)((char *)this + 3568));
  if ( updated < 0 )
  {
    v23 = 2440;
    goto LABEL_49;
  }
LABEL_18:
  if ( !QueryUnbiasedInterruptTime((PULONGLONG)this + 544) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v8 = 2443;
    v9 = LastError;
    goto LABEL_7;
  }
  if ( !*((_QWORD *)this + 543) )
  {
    *((_QWORD *)this + 543) = 1;
    GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 4332));
  }
  updated = ServiceManager::UpdateTransferPolicies((struct _RTL_CRITICAL_SECTION *)this);
  if ( updated >= 0 )
  {
    *((_DWORD *)this + 1090) = -1;
    updated = ServiceWatchdog::Start((char *)this + 3944, v19, *(_QWORD *)((char *)this + 4332));
    if ( updated >= 0 )
    {
      updated = TransferMonitor::Start((ServiceManager *)((char *)this + 4112));
      if ( updated >= 0 )
      {
        v2 = 1;
        updated = ServiceManager::StartUnifiedStackOperation(this);
        if ( updated >= 0 )
        {
          updated = ServiceManager::SerializeOperationState(this);
          if ( updated >= 0 )
          {
            v24 = TimerQueue::CancelAll((ServiceManager *)((char *)this + 4280));
            if ( v24 < 0 )
              ZTraceReportIgnore(v24, "ServiceManager::StartOperation", 2467, this);
            v30 = 0;
            v29 = 0;
            ServiceManager::LogOperationStartTelemetry(this);
            v25 = *((_DWORD *)this + 880);
            if ( v25 != 3 )
            {
              if ( v25 == 1 )
              {
                updated = MosStorageResetPreferredLocationIfNotPresent();
                if ( updated < 0 )
                {
                  v23 = 2483;
                  goto LABEL_49;
                }
              }
              v17 = 4;
            }
            v26 = 0;
            *((_DWORD *)this + 884) = v17;
            *((_DWORD *)this + 885) = 0;
            ServiceManager::FireOdmlStateChange(this);
            ServiceManager::CollectUserProxyTelemetryAsync(this);
            goto LABEL_57;
          }
          v23 = 2465;
        }
        else
        {
          v23 = 2463;
        }
      }
      else
      {
        v23 = 2460;
      }
    }
    else
    {
      v23 = 2459;
    }
  }
  else
  {
    v23 = 2453;
  }
LABEL_49:
  v10 = ZTraceReportPropagation(updated, "ServiceManager::StartOperation", v23, this);
LABEL_50:
  v26 = v10;
  if ( v10 < 0 )
  {
    *((_QWORD *)this + 543) = 0;
    v27 = RegUtils::SetMapsPersistedRegQword(v11, L"CurrentOperationActiveTime", 0);
    if ( v27 < 0 )
      ZTraceReportIgnore(v27, "ServiceManager::StartOperation", 2496, this);
    if ( v2 )
    {
      ServiceWatchdog::Stop((ServiceManager *)((char *)this + 3944));
      TransferMonitor::Stop((ServiceManager *)((char *)this + 4112));
    }
  }
LABEL_57:
  std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v29);
  std::unique_ptr<unsigned int [0]>::~unique_ptr<unsigned int [0]>(&v30);
  return v26;
}

```

## disassembly

```asm
0x18001d224  mov     [rsp+arg_10], rbx
0x18001d229  push    rbp
0x18001d22a  push    rsi
0x18001d22b  push    rdi
0x18001d22c  push    r13
0x18001d22e  push    r14
0x18001d230  sub     rsp, 20h
0x18001d234  mov     rbx, rcx
0x18001d237  mov     [rsp+48h+arg_8], 0
0x18001d240  mov     [rsp+48h+arg_0], 0
0x18001d249  xor     bpl, bpl
0x18001d24c  mov     rcx, [rcx+0D98h]
0x18001d253  mov     rax, [rbx+0D90h]
0x18001d25a  mov     r13d, 4
0x18001d260  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d264  cmp     rax, rcx
0x18001d267  jz      short loc_18001D2D4
0x18001d269  sub     rcx, rax
0x18001d26c  sar     rcx, 2
0x18001d270  mov     eax, r13d
0x18001d273  mul     rcx
0x18001d276  cmovb   rax, r8
0x18001d27a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d281  mov     rcx, rax; unsigned __int64
0x18001d284  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d289  mov     [rsp+48h+arg_8], rax
0x18001d28e  test    rax, rax
0x18001d291  jnz     short loc_18001D2B3
0x18001d293  mov     r8d, 965h
0x18001d299  mov     ecx, 8007000Eh
0x18001d29e  mov     r9, rbx
0x18001d2a1  lea     rdx, aServicemanager_9; "ServiceManager::StartOperation"
0x18001d2a8  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001d2ae  jmp     loc_18001D518
0x18001d2b3  mov     rdx, [rbx+0D90h]; Src
0x18001d2ba  mov     r8, [rbx+0D98h]
0x18001d2c1  sub     r8, rdx
0x18001d2c4  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18001d2c8  mov     rcx, rax; void *
0x18001d2cb  call    memcpy_0
0x18001d2d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d2d4  mov     rcx, [rbx+0DB0h]
0x18001d2db  mov     rax, [rbx+0DA8h]
0x18001d2e2  cmp     rax, rcx
0x18001d2e5  jz      short loc_18001D336
0x18001d2e7  sub     rcx, rax
0x18001d2ea  sar     rcx, 2
0x18001d2ee  mov     rax, r13
0x18001d2f1  mul     rcx
0x18001d2f4  cmovb   rax, r8
0x18001d2f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d2ff  mov     rcx, rax; unsigned __int64
0x18001d302  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d307  mov     [rsp+48h+arg_0], rax
0x18001d30c  test    rax, rax
0x18001d30f  jnz     short loc_18001D319
0x18001d311  mov     r8d, 96Ch
0x18001d317  jmp     short loc_18001D299
0x18001d319  mov     rdx, [rbx+0DA8h]; Src
0x18001d320  mov     r8, [rbx+0DB0h]
0x18001d327  sub     r8, rdx
0x18001d32a  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18001d32e  mov     rcx, rax; void *
0x18001d331  call    memcpy_0
0x18001d336  mov     esi, 3
0x18001d33b  mov     [rbx+0DC4h], esi
0x18001d341  mov     rax, [rbx+0D98h]
0x18001d348  cmp     [rbx+0D90h], rax
0x18001d34f  mov     rax, [rbx+0DB0h]
0x18001d356  jnz     short loc_18001D391
0x18001d358  cmp     [rbx+0DA8h], rax
0x18001d35f  jnz     short loc_18001D3A3
0x18001d361  mov     [rbx+0DC0h], esi
0x18001d367  lea     edi, [rsi+2]
0x18001d36a  lea     rcx, [rbx+1100h]; UnbiasedTime
0x18001d371  call    cs:__imp_QueryUnbiasedInterruptTime
0x18001d377  test    eax, eax
0x18001d379  jnz     short loc_18001D3F5
0x18001d37b  call    cs:__imp_GetLastError
0x18001d381  test    eax, eax
0x18001d383  jz      short loc_18001D3E3
0x18001d385  jle     short loc_18001D3E8
0x18001d387  movzx   eax, ax
0x18001d38a  or      eax, 80070000h
0x18001d38f  jmp     short loc_18001D3E8
0x18001d391  cmp     [rbx+0DA8h], rax
0x18001d398  jnz     short loc_18001D3A3
0x18001d39a  mov     edi, esi
0x18001d39c  mov     ecx, 1
0x18001d3a1  jmp     short loc_18001D3BD
0x18001d3a3  mov     rax, [rbx+0DB0h]
0x18001d3aa  cmp     [rbx+0DA8h], rax
0x18001d3b1  jnz     short loc_18001D3B5
0x18001d3b3  int     2Ch; Windows NT - assertion failure
0x18001d3b5  mov     edi, r13d
0x18001d3b8  mov     ecx, 2
0x18001d3bd  mov     eax, 0DC0h
0x18001d3c2  mov     rdx, rbx
0x18001d3c5  mov     [rax+rbx], ecx
0x18001d3c8  lea     rcx, [rbx+0DF0h]; this
0x18001d3cf  call    ?OnOperationStarted@PackageManager@@QEAAJXZ; PackageManager::OnOperationStarted(void)
0x18001d3d4  test    eax, eax
0x18001d3d6  jns     short loc_18001D36A
0x18001d3d8  mov     r8d, 988h
0x18001d3de  jmp     loc_18001D506
0x18001d3e3  mov     eax, 80390004h
0x18001d3e8  mov     r8d, 98Bh
0x18001d3ee  mov     ecx, eax
0x18001d3f0  jmp     loc_18001D29E
0x18001d3f5  lea     r14, [rbx+10ECh]
0x18001d3fc  cmp     qword ptr [rbx+10F8h], 0
0x18001d404  jnz     short loc_18001D41A
0x18001d406  mov     qword ptr [rbx+10F8h], 1
0x18001d411  mov     rcx, r14; lpSystemTimeAsFileTime
0x18001d414  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d41a  mov     rcx, rbx; this
0x18001d41d  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x18001d422  test    eax, eax
0x18001d424  jns     short loc_18001D431
0x18001d426  mov     r8d, 995h
0x18001d42c  jmp     loc_18001D506
0x18001d431  mov     dword ptr [rbx+1108h], 0FFFFFFFFh
0x18001d43b  lea     rcx, [rbx+0F68h]
0x18001d442  mov     r8, [r14]
0x18001d445  mov     edx, edi
0x18001d447  call    ?Start@ServiceWatchdog@@QEAAJW4StartReason@1@U_FILETIME@@@Z; ServiceWatchdog::Start(ServiceWatchdog::StartReason,_FILETIME)
0x18001d44c  test    eax, eax
0x18001d44e  jns     short loc_18001D45B
0x18001d450  mov     r8d, 99Bh
0x18001d456  jmp     loc_18001D506
0x18001d45b  lea     rcx, [rbx+1010h]; this
0x18001d462  call    ?Start@TransferMonitor@@QEAAJXZ; TransferMonitor::Start(void)
0x18001d467  test    eax, eax
0x18001d469  jns     short loc_18001D476
0x18001d46b  mov     r8d, 99Ch
0x18001d471  jmp     loc_18001D506
0x18001d476  mov     bpl, 1
0x18001d479  mov     rcx, rbx; this
0x18001d47c  call    ?StartUnifiedStackOperation@ServiceManager@@AEAAJXZ; ServiceManager::StartUnifiedStackOperation(void)
0x18001d481  test    eax, eax
0x18001d483  jns     short loc_18001D48D
0x18001d485  mov     r8d, 99Fh
0x18001d48b  jmp     short loc_18001D506
0x18001d48d  mov     rcx, rbx; this
0x18001d490  call    ?SerializeOperationState@ServiceManager@@AEAAJXZ; ServiceManager::SerializeOperationState(void)
0x18001d495  test    eax, eax
0x18001d497  jns     short loc_18001D4A1
0x18001d499  mov     r8d, 9A1h
0x18001d49f  jmp     short loc_18001D506
0x18001d4a1  lea     rcx, [rbx+10B8h]; this
0x18001d4a8  call    ?CancelAll@TimerQueue@@QEAAJXZ; TimerQueue::CancelAll(void)
0x18001d4ad  test    eax, eax
0x18001d4af  jns     short loc_18001D4C9
0x18001d4b1  mov     r9, rbx
0x18001d4b4  mov     r8d, 9A3h
0x18001d4ba  lea     rdx, aServicemanager_9; "ServiceManager::StartOperation"
0x18001d4c1  mov     ecx, eax
0x18001d4c3  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001d4c9  mov     [rsp+48h+arg_8], 0
0x18001d4d2  mov     [rsp+48h+arg_0], 0
0x18001d4db  mov     rcx, rbx; this
0x18001d4de  call    ?LogOperationStartTelemetry@ServiceManager@@AEAAXXZ; ServiceManager::LogOperationStartTelemetry(void)
0x18001d4e3  mov     eax, [rbx+0DC0h]
0x18001d4e9  cmp     eax, esi
0x18001d4eb  jz      loc_18001D576
0x18001d4f1  cmp     eax, 1
0x18001d4f4  jnz     short loc_18001D573
0x18001d4f6  call    cs:__imp_?MosStorageResetPreferredLocationIfNotPresent@@YAJXZ; MosStorageResetPreferredLocationIfNotPresent(void)
0x18001d4fc  test    eax, eax
0x18001d4fe  jns     short loc_18001D573
0x18001d500  mov     r8d, 9B3h
0x18001d506  mov     r9, rbx
0x18001d509  lea     rdx, aServicemanager_9; "ServiceManager::StartOperation"
0x18001d510  mov     ecx, eax
0x18001d512  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001d518  mov     edi, eax
0x18001d51a  test    eax, eax
0x18001d51c  jns     short loc_18001D595
0x18001d51e  mov     qword ptr [rbx+10F8h], 0
0x18001d529  xor     r8d, r8d
0x18001d52c  lea     rdx, aCurrentoperati; "CurrentOperationActiveTime"
0x18001d533  call    ?SetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_K@Z; RegUtils::SetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64)
0x18001d538  test    eax, eax
0x18001d53a  jns     short loc_18001D554
0x18001d53c  mov     r9, rbx
0x18001d53f  mov     r8d, 9C0h
0x18001d545  lea     rdx, aServicemanager_9; "ServiceManager::StartOperation"
0x18001d54c  mov     ecx, eax
0x18001d54e  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001d554  test    bpl, bpl
0x18001d557  jz      short loc_18001D595
0x18001d559  lea     rcx, [rbx+0F68h]; this
0x18001d560  call    ?Stop@ServiceWatchdog@@QEAAXXZ; ServiceWatchdog::Stop(void)
0x18001d565  lea     rcx, [rbx+1010h]; this
0x18001d56c  call    ?Stop@TransferMonitor@@QEAAXXZ; TransferMonitor::Stop(void)
0x18001d571  jmp     short loc_18001D595
0x18001d573  mov     esi, r13d
0x18001d576  xor     edi, edi
0x18001d578  mov     [rbx+0DD0h], esi
0x18001d57e  mov     [rbx+0DD4h], edi
0x18001d584  mov     rcx, rbx; this
0x18001d587  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001d58c  mov     rcx, rbx; this
0x18001d58f  call    ?CollectUserProxyTelemetryAsync@ServiceManager@@AEAAXXZ; ServiceManager::CollectUserProxyTelemetryAsync(void)
0x18001d594  nop
0x18001d595  lea     rcx, [rsp+48h+arg_0]
0x18001d59a  call    ??1?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@std@@@std@@QEAA@XZ; std::unique_ptr<uint [0]>::~unique_ptr<uint [0]>(void)
0x18001d59f  nop
0x18001d5a0  lea     rcx, [rsp+48h+arg_8]
0x18001d5a5  call    ??1?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@std@@@std@@QEAA@XZ; std::unique_ptr<uint [0]>::~unique_ptr<uint [0]>(void)
0x18001d5aa  mov     eax, edi
0x18001d5ac  mov     rbx, [rsp+48h+arg_10]
0x18001d5b1  add     rsp, 20h
0x18001d5b5  pop     r14
0x18001d5b7  pop     r13
0x18001d5b9  pop     rdi
0x18001d5ba  pop     rsi
0x18001d5bb  pop     rbp
0x18001d5bc  retn
```

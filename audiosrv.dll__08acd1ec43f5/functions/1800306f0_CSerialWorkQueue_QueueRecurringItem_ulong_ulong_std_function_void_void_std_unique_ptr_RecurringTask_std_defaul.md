# CSerialWorkQueue::QueueRecurringItem(ulong,ulong,std::function<void (void)>,std::unique_ptr<_RecurringTask,std::default_delete<_RecurringTask>> &)

- ea: `0x1800306f0`
- end: `0x180030b21`
- name: `?QueueRecurringItem@CSerialWorkQueue@@QEAAJKKV?$function@$$A6AXXZ@std@@AEAV?$unique_ptr@U_RecurringTask@@U?$default_delete@U_RecurringTask@@@std@@@3@@Z`
- size: `1073`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18002eebc`
- `0x180068870`
- `0x180079260`
- `0x1800b6cf0`
- `0x1800c5080`
- `0x1800cab08`
- `0x1800f97c0`
- `0x18011e588`

## callees

- `0x18002a1ac`
- `0x1800306f0`
- `0x180030bc4`
- `0x1800cdd70`
- `0x1800cddac`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030836`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030836`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030847`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030af9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003072f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18003072f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800309d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800309d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030776`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030776`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003074b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003074b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180030928`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180030928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030796`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030796`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030992`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800309c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030992`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800309c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800309d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800309d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 CSerialWorkQueue::QueueRecurringItem(__int64 a1, unsigned int a2, __int64 a3, ...)
{
  struct _FILETIME v3; // r15
  __int64 v4; // r13
  signed int v6; // r14d
  PTP_POOL Threadpool; // rax
  signed int v8; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_TIMER *v10; // rax
  _BYTE *v11; // rcx
  PTP_TIMER *v12; // rdi
  PTP_TIMER *v13; // rbx
  __int64 (__fastcall ***v14)(_QWORD, _BYTE *); // rcx
  HANDLE ProcessHeap; // rax
  _DWORD *v16; // rax
  _DWORD *v17; // rsi
  volatile signed __int32 *v18; // r14
  PTP_TIMER v19; // rsi
  _BYTE *v20; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v22; // rsi
  signed int LastError; // eax
  PTP_TIMER *v24; // rsi
  volatile signed __int32 *v25; // rdi
  volatile signed __int32 *v26; // rdi
  __int64 *v27; // rcx
  __int64 v28; // rdx
  signed int v30; // eax
  signed int v31; // eax
  _BYTE v32[56]; // [rsp+30h] [rbp-78h] BYREF
  _BYTE *v33; // [rsp+68h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+C8h] [rbp+20h] BYREF
  va_list pftDueTimea; // [rsp+C8h] [rbp+20h]
  PTP_TIMER **v36; // [rsp+D0h] [rbp+28h]
  va_list va1; // [rsp+D8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(pftDueTimea, a3);
  pftDueTime = va_arg(va1, struct _FILETIME);
  v36 = va_arg(va1, PTP_TIMER **);
  v3 = pftDueTime;
  v4 = a2;
  v6 = 0;
  if ( *(_BYTE *)(a1 + 80) )
    goto LABEL_45;
  if ( *(_QWORD *)a1 )
  {
LABEL_10:
    v10 = (PTP_TIMER *)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v10;
    if ( v10 )
    {
      *v10 = 0;
      v10[1] = 0;
      v10[2] = 0;
    }
    else
    {
      v12 = 0;
    }
    v13 = v12;
    if ( v12 )
    {
      v33 = 0;
      v14 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(*(_QWORD *)&v3 + 56LL);
      if ( v14 )
        v33 = (_BYTE *)(**v14)(v14, v32);
      v12[3] = (PTP_TIMER)a1;
      ProcessHeap = GetProcessHeap();
      v16 = HeapAlloc(ProcessHeap, 0, 0x50u);
      v17 = v16;
      if ( v16 )
      {
        *(_OWORD *)v16 = 0;
        v16[2] = 1;
        v16[3] = 1;
        *(_QWORD *)v16 = &std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable';
        std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(v16 + 4, v32);
      }
      else
      {
        v17 = 0;
      }
      v12[1] = (PTP_TIMER)(v17 + 4);
      v18 = (volatile signed __int32 *)v12[2];
      v12[2] = (PTP_TIMER)v17;
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      v19 = v12[1];
      v6 = -2147024882;
      if ( v19 )
        v6 = 0;
      v11 = v33;
      if ( v33 )
      {
        v20 = v32;
        LOBYTE(v20) = v33 != v32;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v33 + 32LL))(v33, v20);
      }
      if ( !v19 )
        goto LABEL_43;
      ThreadpoolTimer = CreateThreadpoolTimer(CSerialWorkQueue::TimerCallback, v12, (PTP_CALLBACK_ENVIRON)(a1 + 8));
      v22 = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        v6 = 0;
        *v12 = ThreadpoolTimer;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        *v12 = 0;
        if ( v6 < 0 )
          goto LABEL_43;
      }
      pftDueTime = (struct _FILETIME)(-10000 * v4);
      SetThreadpoolTimer(v22, (PFILETIME)pftDueTimea, 0, 0);
      v13 = 0;
      v24 = *v36;
      *v36 = v12;
      if ( v24 )
      {
        if ( *v24 )
        {
          SetThreadpoolTimer(*v24, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(*v24, 1);
          CloseThreadpoolTimer(*v24);
        }
        v24[1] = 0;
        v25 = (volatile signed __int32 *)v24[2];
        v24[2] = 0;
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        v26 = (volatile signed __int32 *)v24[2];
        if ( v26 )
        {
          if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
            if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
          }
        }
        operator delete(v24, (const struct std::nothrow_t *)0x20);
      }
    }
    else
    {
      v6 = -2147024882;
    }
LABEL_43:
    if ( v13 )
      std::default_delete<_RecurringTask>::operator()(v11, v13);
    goto LABEL_45;
  }
  Threadpool = CreateThreadpool(0);
  *(_QWORD *)a1 = Threadpool;
  if ( Threadpool )
    goto LABEL_53;
  v30 = GetLastError();
  v6 = v30;
  if ( v30 > 0 )
    v6 = (unsigned __int16)v30 | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_53:
    if ( SetThreadpoolThreadMinimum(*(PTP_POOL *)a1, 1u) )
      goto LABEL_61;
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_61:
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *(_QWORD *)(a1 + 168) = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
        goto LABEL_9;
      v31 = GetLastError();
      v6 = v31;
      if ( v31 > 0 )
        v6 = (unsigned __int16)v31 | 0x80070000;
      if ( v6 >= 0 )
      {
LABEL_9:
        SetThreadpoolThreadMaximum(*(PTP_POOL *)a1, 1u);
        *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
        *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 168);
        *(_QWORD *)(a1 + 32) = 0;
        goto LABEL_10;
      }
    }
  }
LABEL_45:
  v27 = *(__int64 **)(*(_QWORD *)&v3 + 56LL);
  if ( v27 )
  {
    v28 = *v27;
    LOBYTE(v28) = v27 != *(__int64 **)&v3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v27 + 32))(v27, v28);
    *(_QWORD *)(*(_QWORD *)&v3 + 56LL) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800306f0  mov     [rsp+arg_8], rbx
0x1800306f5  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r9
0x1800306fa  push    rbp
0x1800306fb  push    rsi
0x1800306fc  push    rdi
0x1800306fd  push    r12
0x1800306ff  push    r13
0x180030701  push    r14
0x180030703  push    r15
0x180030705  sub     rsp, 70h
0x180030709  mov     r15, r9
0x18003070c  mov     r13d, edx
0x18003070f  mov     r12, rcx
0x180030712  xor     ebp, ebp
0x180030714  mov     r14d, ebp
0x180030717  movzx   eax, byte ptr [rcx+50h]
0x18003071b  nop
0x18003071c  test    al, al
0x18003071e  jnz     loc_180030A79
0x180030724  cmp     [rcx], r14
0x180030727  jnz     loc_1800307B7
0x18003072d  xor     ecx, ecx; reserved
0x18003072f  call    cs:__imp_CreateThreadpool
0x180030735  mov     [r12], rax
0x180030739  test    rax, rax
0x18003073c  jz      loc_180030ADF
0x180030742  mov     edx, 1; cthrdMic
0x180030747  mov     rcx, [r12]; ptpp
0x18003074b  call    cs:__imp_SetThreadpoolThreadMinimum
0x180030751  test    eax, eax
0x180030753  jnz     short loc_180030776
0x180030755  call    cs:__imp_GetLastError
0x18003075b  mov     r14d, eax
0x18003075e  test    eax, eax
0x180030760  jle     short loc_18003076D
0x180030762  movzx   r14d, ax
0x180030766  or      r14d, 80070000h
0x18003076d  test    r14d, r14d
0x180030770  js      loc_180030A79
0x180030776  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003077c  mov     [r12+0A8h], rax
0x180030784  test    rax, rax
0x180030787  jz      loc_180030AF9
0x18003078d  mov     edx, 1; cthrdMost
0x180030792  mov     rcx, [r12]; ptpp
0x180030796  call    cs:__imp_SetThreadpoolThreadMaximum
0x18003079c  mov     rax, [r12]
0x1800307a0  mov     [r12+10h], rax
0x1800307a5  mov     rax, [r12+0A8h]
0x1800307ad  mov     [r12+18h], rax
0x1800307b2  mov     [r12+20h], rbp
0x1800307b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800307be  mov     ecx, 20h ; ' '; unsigned __int64
0x1800307c3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800307c8  mov     rdi, rax
0x1800307cb  mov     [rsp+0A8h+arg_0], rax
0x1800307d3  test    rax, rax
0x1800307d6  jz      loc_180030ABB
0x1800307dc  mov     [rax], rbp
0x1800307df  mov     [rax+8], rbp
0x1800307e3  mov     [rax+10h], rbp
0x1800307e7  mov     rbx, rdi
0x1800307ea  mov     [rsp+0A8h+arg_0], rbx
0x1800307f2  test    rdi, rdi
0x1800307f5  jz      loc_180030AB3
0x1800307fb  lea     rax, [rsp+0A8h+var_78]
0x180030800  mov     [rsp+0A8h+var_88], rax
0x180030805  mov     [rsp+0A8h+var_40], rbp
0x18003080a  mov     rcx, [r15+38h]
0x18003080e  test    rcx, rcx
0x180030811  jz      short loc_180030828
0x180030813  mov     rax, [rcx]
0x180030816  lea     rdx, [rsp+0A8h+var_78]
0x18003081b  mov     rax, [rax]
0x18003081e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030823  mov     [rsp+0A8h+var_40], rax
0x180030828  lea     rax, [rsp+0A8h+var_78]
0x18003082d  mov     [rsp+0A8h+var_88], rax
0x180030832  mov     [rdi+18h], r12
0x180030836  call    cs:__imp_GetProcessHeap
0x18003083c  mov     rcx, rax; hHeap
0x18003083f  xor     edx, edx; dwFlags
0x180030841  mov     r8d, 50h ; 'P'; dwBytes
0x180030847  call    cs:__imp_HeapAlloc
0x18003084d  mov     rsi, rax
0x180030850  mov     [rsp+0A8h+var_80], rax
0x180030855  test    rax, rax
0x180030858  jz      loc_180030AC3
0x18003085e  xorps   xmm0, xmm0
0x180030861  movups  xmmword ptr [rax], xmm0
0x180030864  mov     dword ptr [rax+8], 1
0x18003086b  mov     dword ptr [rax+0Ch], 1
0x180030872  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x180030879  mov     [rsi], rax
0x18003087c  lea     rcx, [rsi+10h]
0x180030880  lea     rdx, [rsp+0A8h+var_78]
0x180030885  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x18003088a  nop
0x18003088b  lea     rax, [rsi+10h]
0x18003088f  mov     [rdi+8], rax
0x180030893  mov     r14, [rdi+10h]
0x180030897  mov     [rdi+10h], rsi
0x18003089b  mov     ebp, 0FFFFFFFFh
0x1800308a0  test    r14, r14
0x1800308a3  jz      short loc_1800308DC
0x1800308a5  mov     eax, ebp
0x1800308a7  lock xadd [r14+8], eax
0x1800308ad  cmp     eax, 1
0x1800308b0  jnz     short loc_1800308DC
0x1800308b2  mov     rax, [r14]
0x1800308b5  mov     rcx, r14
0x1800308b8  mov     rax, [rax]
0x1800308bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308c0  mov     eax, ebp
0x1800308c2  lock xadd [r14+0Ch], eax
0x1800308c8  cmp     eax, 1
0x1800308cb  jnz     short loc_1800308DC
0x1800308cd  mov     rax, [r14]
0x1800308d0  mov     rcx, r14
0x1800308d3  mov     rax, [rax+8]
0x1800308d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308dc  mov     rsi, [rdi+8]
0x1800308e0  xor     eax, eax
0x1800308e2  mov     r14d, 8007000Eh
0x1800308e8  test    rsi, rsi
0x1800308eb  cmovnz  r14d, eax
0x1800308ef  mov     rcx, [rsp+0A8h+var_40]
0x1800308f4  test    rcx, rcx
0x1800308f7  jz      short loc_180030910
0x1800308f9  mov     rax, [rcx]
0x1800308fc  lea     rdx, [rsp+0A8h+var_78]
0x180030901  cmp     rcx, rdx
0x180030904  setnz   dl
0x180030907  mov     rax, [rax+20h]
0x18003090b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030910  test    rsi, rsi
0x180030913  jz      loc_180030A6E
0x180030919  lea     r8, [r12+8]; pcbe
0x18003091e  mov     rdx, rdi; pv
0x180030921  lea     rcx, ?TimerCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180030928  call    cs:__imp_CreateThreadpoolTimer
0x18003092e  mov     rsi, rax
0x180030931  test    rax, rax
0x180030934  jz      short loc_180030941
0x180030936  xor     r12d, r12d
0x180030939  mov     r14d, r12d
0x18003093c  mov     [rdi], rax
0x18003093f  jmp     short loc_180030968
0x180030941  call    cs:__imp_GetLastError
0x180030947  mov     r14d, eax
0x18003094a  test    eax, eax
0x18003094c  jle     short loc_180030959
0x18003094e  movzx   r14d, ax
0x180030952  or      r14d, 80070000h
0x180030959  mov     [rdi], rsi
0x18003095c  test    r14d, r14d
0x18003095f  js      loc_180030A6E
0x180030965  xor     r12d, r12d
0x180030968  imul    rax, r13, 0FFFFFFFFFFFFD8F0h
0x18003096f  mov     [rsp+0A8h+pftDueTime.dwLowDateTime], eax
0x180030976  shr     rax, 20h
0x18003097a  mov     [rsp+0A8h+pftDueTime.dwHighDateTime], eax
0x180030981  xor     r9d, r9d; msWindowLength
0x180030984  xor     r8d, r8d; msPeriod
0x180030987  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x18003098f  mov     rcx, rsi; pti
0x180030992  call    cs:__imp_SetThreadpoolTimer
0x180030998  mov     rbx, r12
0x18003099b  mov     rax, [rsp+0A8h+arg_20]
0x1800309a3  mov     rsi, [rax]
0x1800309a6  mov     [rax], rdi
0x1800309a9  test    rsi, rsi
0x1800309ac  jz      loc_180030A6E
0x1800309b2  mov     rcx, [rsi]; pti
0x1800309b5  test    rcx, rcx
0x1800309b8  jz      short loc_1800309DF
0x1800309ba  xor     r9d, r9d; msWindowLength
0x1800309bd  xor     r8d, r8d; msPeriod
0x1800309c0  xor     edx, edx; pftDueTime
0x1800309c2  call    cs:__imp_SetThreadpoolTimer
0x1800309c8  mov     edx, 1; fCancelPendingCallbacks
0x1800309cd  mov     rcx, [rsi]; pti
0x1800309d0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800309d6  mov     rcx, [rsi]; pti
0x1800309d9  call    cs:__imp_CloseThreadpoolTimer
0x1800309df  mov     [rsi+8], r12
0x1800309e3  mov     rdi, [rsi+10h]
0x1800309e7  mov     [rsi+10h], r12
0x1800309eb  test    rdi, rdi
0x1800309ee  jz      short loc_180030A25
0x1800309f0  mov     eax, ebp
0x1800309f2  lock xadd [rdi+8], eax
0x1800309f7  cmp     eax, 1
0x1800309fa  jnz     short loc_180030A25
0x1800309fc  mov     rax, [rdi]
0x1800309ff  mov     rcx, rdi
0x180030a02  mov     rax, [rax]
0x180030a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a0a  mov     eax, ebp
0x180030a0c  lock xadd [rdi+0Ch], eax
0x180030a11  cmp     eax, 1
0x180030a14  jnz     short loc_180030A25
0x180030a16  mov     rax, [rdi]
0x180030a19  mov     rcx, rdi
0x180030a1c  mov     rax, [rax+8]
0x180030a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a25  mov     rdi, [rsi+10h]
0x180030a29  test    rdi, rdi
0x180030a2c  jz      short loc_180030A61
0x180030a2e  mov     eax, ebp
0x180030a30  lock xadd [rdi+8], eax
0x180030a35  cmp     eax, 1
0x180030a38  jnz     short loc_180030A61
0x180030a3a  mov     rax, [rdi]
0x180030a3d  mov     rcx, rdi
0x180030a40  mov     rax, [rax]
0x180030a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a48  lock xadd [rdi+0Ch], ebp
0x180030a4d  cmp     ebp, 1
0x180030a50  jnz     short loc_180030A61
0x180030a52  mov     rax, [rdi]
0x180030a55  mov     rcx, rdi
0x180030a58  mov     rax, [rax+8]
0x180030a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a61  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180030a66  mov     rcx, rsi; void *
0x180030a69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030a6e  xor     ebp, ebp
0x180030a70  test    rbx, rbx
0x180030a73  jnz     loc_180030B13
0x180030a79  mov     rcx, [r15+38h]
0x180030a7d  test    rcx, rcx
0x180030a80  jz      short loc_180030A98
0x180030a82  mov     rdx, [rcx]
0x180030a85  mov     rax, [rdx+20h]
0x180030a89  cmp     rcx, r15
0x180030a8c  setnz   dl
0x180030a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a94  mov     [r15+38h], rbp
0x180030a98  mov     eax, r14d
0x180030a9b  mov     rbx, [rsp+0A8h+arg_8]
0x180030aa3  add     rsp, 70h
0x180030aa7  pop     r15
0x180030aa9  pop     r14
0x180030aab  pop     r13
0x180030aad  pop     r12
0x180030aaf  pop     rdi
0x180030ab0  pop     rsi
0x180030ab1  pop     rbp
0x180030ab2  retn
0x180030ab3  mov     r14d, 8007000Eh
0x180030ab9  jmp     short loc_180030A70
0x180030abb  mov     rdi, rbp
0x180030abe  jmp     loc_1800307E7
0x180030ac3  mov     rsi, rbp
0x180030ac6  jmp     loc_18003088B
0x180030acb  test    r14d, r14d
0x180030ace  js      short loc_180030A79
0x180030ad0  jmp     loc_180030742
0x180030ad5  test    r14d, r14d
0x180030ad8  js      short loc_180030A79
0x180030ada  jmp     loc_18003078D
0x180030adf  call    cs:__imp_GetLastError
0x180030ae5  mov     r14d, eax
0x180030ae8  test    eax, eax
0x180030aea  jle     short loc_180030ACB
0x180030aec  movzx   r14d, ax
0x180030af0  or      r14d, 80070000h
0x180030af7  jmp     short loc_180030ACB
0x180030af9  call    cs:__imp_GetLastError
0x180030aff  mov     r14d, eax
0x180030b02  test    eax, eax
0x180030b04  jle     short loc_180030AD5
0x180030b06  movzx   r14d, ax
0x180030b0a  or      r14d, 80070000h
0x180030b11  jmp     short loc_180030AD5
0x180030b13  mov     rdx, rbx
0x180030b16  call    ??R?$default_delete@U_RecurringTask@@@std@@QEBAXPEAU_RecurringTask@@@Z; std::default_delete<_RecurringTask>::operator()(_RecurringTask *)
0x180030b1b  jmp     loc_180030A79
```

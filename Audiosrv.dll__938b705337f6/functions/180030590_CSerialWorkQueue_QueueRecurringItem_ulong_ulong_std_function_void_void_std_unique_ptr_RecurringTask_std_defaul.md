# CSerialWorkQueue::QueueRecurringItem(ulong,ulong,std::function<void (void)>,std::unique_ptr<_RecurringTask,std::default_delete<_RecurringTask>> &)

- ea: `0x180030590`
- end: `0x1800309c1`
- name: `?QueueRecurringItem@CSerialWorkQueue@@QEAAJKKV?$function@$$A6AXXZ@std@@AEAV?$unique_ptr@U_RecurringTask@@U?$default_delete@U_RecurringTask@@@std@@@3@@Z`
- size: `1073`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18002ed5c`
- `0x180068d00`
- `0x180079760`
- `0x1800b8840`
- `0x1800c6e70`
- `0x1800ccaf8`
- `0x1800f9530`
- `0x18011e338`

## callees

- `0x18002a04c`
- `0x180030590`
- `0x180030a64`
- `0x1800cfd60`
- `0x1800cfd9c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800306d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800306d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800306e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800306e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003097f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800307e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003097f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030999`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800305cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800305cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180030870`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180030870`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030616`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030616`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800305eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800305eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800307c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800307c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030636`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030636`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030832`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030862`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030832`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180030862`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180030879`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180030879`

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
0x180030590  mov     [rsp+arg_8], rbx
0x180030595  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r9
0x18003059a  push    rbp
0x18003059b  push    rsi
0x18003059c  push    rdi
0x18003059d  push    r12
0x18003059f  push    r13
0x1800305a1  push    r14
0x1800305a3  push    r15
0x1800305a5  sub     rsp, 70h
0x1800305a9  mov     r15, r9
0x1800305ac  mov     r13d, edx
0x1800305af  mov     r12, rcx
0x1800305b2  xor     ebp, ebp
0x1800305b4  mov     r14d, ebp
0x1800305b7  movzx   eax, byte ptr [rcx+50h]
0x1800305bb  nop
0x1800305bc  test    al, al
0x1800305be  jnz     loc_180030919
0x1800305c4  cmp     [rcx], r14
0x1800305c7  jnz     loc_180030657
0x1800305cd  xor     ecx, ecx; reserved
0x1800305cf  call    cs:__imp_CreateThreadpool
0x1800305d5  mov     [r12], rax
0x1800305d9  test    rax, rax
0x1800305dc  jz      loc_18003097F
0x1800305e2  mov     edx, 1; cthrdMic
0x1800305e7  mov     rcx, [r12]; ptpp
0x1800305eb  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800305f1  test    eax, eax
0x1800305f3  jnz     short loc_180030616
0x1800305f5  call    cs:__imp_GetLastError
0x1800305fb  mov     r14d, eax
0x1800305fe  test    eax, eax
0x180030600  jle     short loc_18003060D
0x180030602  movzx   r14d, ax
0x180030606  or      r14d, 80070000h
0x18003060d  test    r14d, r14d
0x180030610  js      loc_180030919
0x180030616  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003061c  mov     [r12+0A8h], rax
0x180030624  test    rax, rax
0x180030627  jz      loc_180030999
0x18003062d  mov     edx, 1; cthrdMost
0x180030632  mov     rcx, [r12]; ptpp
0x180030636  call    cs:__imp_SetThreadpoolThreadMaximum
0x18003063c  mov     rax, [r12]
0x180030640  mov     [r12+10h], rax
0x180030645  mov     rax, [r12+0A8h]
0x18003064d  mov     [r12+18h], rax
0x180030652  mov     [r12+20h], rbp
0x180030657  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003065e  mov     ecx, 20h ; ' '; unsigned __int64
0x180030663  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180030668  mov     rdi, rax
0x18003066b  mov     [rsp+0A8h+arg_0], rax
0x180030673  test    rax, rax
0x180030676  jz      loc_18003095B
0x18003067c  mov     [rax], rbp
0x18003067f  mov     [rax+8], rbp
0x180030683  mov     [rax+10h], rbp
0x180030687  mov     rbx, rdi
0x18003068a  mov     [rsp+0A8h+arg_0], rbx
0x180030692  test    rdi, rdi
0x180030695  jz      loc_180030953
0x18003069b  lea     rax, [rsp+0A8h+var_78]
0x1800306a0  mov     [rsp+0A8h+var_88], rax
0x1800306a5  mov     [rsp+0A8h+var_40], rbp
0x1800306aa  mov     rcx, [r15+38h]
0x1800306ae  test    rcx, rcx
0x1800306b1  jz      short loc_1800306C8
0x1800306b3  mov     rax, [rcx]
0x1800306b6  lea     rdx, [rsp+0A8h+var_78]
0x1800306bb  mov     rax, [rax]
0x1800306be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306c3  mov     [rsp+0A8h+var_40], rax
0x1800306c8  lea     rax, [rsp+0A8h+var_78]
0x1800306cd  mov     [rsp+0A8h+var_88], rax
0x1800306d2  mov     [rdi+18h], r12
0x1800306d6  call    cs:__imp_GetProcessHeap
0x1800306dc  mov     rcx, rax; hHeap
0x1800306df  xor     edx, edx; dwFlags
0x1800306e1  mov     r8d, 50h ; 'P'; dwBytes
0x1800306e7  call    cs:__imp_HeapAlloc
0x1800306ed  mov     rsi, rax
0x1800306f0  mov     [rsp+0A8h+var_80], rax
0x1800306f5  test    rax, rax
0x1800306f8  jz      loc_180030963
0x1800306fe  xorps   xmm0, xmm0
0x180030701  movups  xmmword ptr [rax], xmm0
0x180030704  mov     dword ptr [rax+8], 1
0x18003070b  mov     dword ptr [rax+0Ch], 1
0x180030712  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AJPEAVSystemEffectDescriptor@@PEAVSystemEffectChainDescriptor@@@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<long (SystemEffectDescriptor *,SystemEffectChainDescriptor *)>>::`vftable'
0x180030719  mov     [rsi], rax
0x18003071c  lea     rcx, [rsi+10h]
0x180030720  lea     rdx, [rsp+0A8h+var_78]
0x180030725  call    ??0?$function@$$A6AXPEAUIAudioStreamInfo@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (IAudioStreamInfo *)>::function<void (IAudioStreamInfo *)>(std::function<void (IAudioStreamInfo *)> const &)
0x18003072a  nop
0x18003072b  lea     rax, [rsi+10h]
0x18003072f  mov     [rdi+8], rax
0x180030733  mov     r14, [rdi+10h]
0x180030737  mov     [rdi+10h], rsi
0x18003073b  mov     ebp, 0FFFFFFFFh
0x180030740  test    r14, r14
0x180030743  jz      short loc_18003077C
0x180030745  mov     eax, ebp
0x180030747  lock xadd [r14+8], eax
0x18003074d  cmp     eax, 1
0x180030750  jnz     short loc_18003077C
0x180030752  mov     rax, [r14]
0x180030755  mov     rcx, r14
0x180030758  mov     rax, [rax]
0x18003075b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030760  mov     eax, ebp
0x180030762  lock xadd [r14+0Ch], eax
0x180030768  cmp     eax, 1
0x18003076b  jnz     short loc_18003077C
0x18003076d  mov     rax, [r14]
0x180030770  mov     rcx, r14
0x180030773  mov     rax, [rax+8]
0x180030777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003077c  mov     rsi, [rdi+8]
0x180030780  xor     eax, eax
0x180030782  mov     r14d, 8007000Eh
0x180030788  test    rsi, rsi
0x18003078b  cmovnz  r14d, eax
0x18003078f  mov     rcx, [rsp+0A8h+var_40]
0x180030794  test    rcx, rcx
0x180030797  jz      short loc_1800307B0
0x180030799  mov     rax, [rcx]
0x18003079c  lea     rdx, [rsp+0A8h+var_78]
0x1800307a1  cmp     rcx, rdx
0x1800307a4  setnz   dl
0x1800307a7  mov     rax, [rax+20h]
0x1800307ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b0  test    rsi, rsi
0x1800307b3  jz      loc_18003090E
0x1800307b9  lea     r8, [r12+8]; pcbe
0x1800307be  mov     rdx, rdi; pv
0x1800307c1  lea     rcx, ?TimerCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800307c8  call    cs:__imp_CreateThreadpoolTimer
0x1800307ce  mov     rsi, rax
0x1800307d1  test    rax, rax
0x1800307d4  jz      short loc_1800307E1
0x1800307d6  xor     r12d, r12d
0x1800307d9  mov     r14d, r12d
0x1800307dc  mov     [rdi], rax
0x1800307df  jmp     short loc_180030808
0x1800307e1  call    cs:__imp_GetLastError
0x1800307e7  mov     r14d, eax
0x1800307ea  test    eax, eax
0x1800307ec  jle     short loc_1800307F9
0x1800307ee  movzx   r14d, ax
0x1800307f2  or      r14d, 80070000h
0x1800307f9  mov     [rdi], rsi
0x1800307fc  test    r14d, r14d
0x1800307ff  js      loc_18003090E
0x180030805  xor     r12d, r12d
0x180030808  imul    rax, r13, 0FFFFFFFFFFFFD8F0h
0x18003080f  mov     [rsp+0A8h+pftDueTime.dwLowDateTime], eax
0x180030816  shr     rax, 20h
0x18003081a  mov     [rsp+0A8h+pftDueTime.dwHighDateTime], eax
0x180030821  xor     r9d, r9d; msWindowLength
0x180030824  xor     r8d, r8d; msPeriod
0x180030827  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x18003082f  mov     rcx, rsi; pti
0x180030832  call    cs:__imp_SetThreadpoolTimer
0x180030838  mov     rbx, r12
0x18003083b  mov     rax, [rsp+0A8h+arg_20]
0x180030843  mov     rsi, [rax]
0x180030846  mov     [rax], rdi
0x180030849  test    rsi, rsi
0x18003084c  jz      loc_18003090E
0x180030852  mov     rcx, [rsi]; pti
0x180030855  test    rcx, rcx
0x180030858  jz      short loc_18003087F
0x18003085a  xor     r9d, r9d; msWindowLength
0x18003085d  xor     r8d, r8d; msPeriod
0x180030860  xor     edx, edx; pftDueTime
0x180030862  call    cs:__imp_SetThreadpoolTimer
0x180030868  mov     edx, 1; fCancelPendingCallbacks
0x18003086d  mov     rcx, [rsi]; pti
0x180030870  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180030876  mov     rcx, [rsi]; pti
0x180030879  call    cs:__imp_CloseThreadpoolTimer
0x18003087f  mov     [rsi+8], r12
0x180030883  mov     rdi, [rsi+10h]
0x180030887  mov     [rsi+10h], r12
0x18003088b  test    rdi, rdi
0x18003088e  jz      short loc_1800308C5
0x180030890  mov     eax, ebp
0x180030892  lock xadd [rdi+8], eax
0x180030897  cmp     eax, 1
0x18003089a  jnz     short loc_1800308C5
0x18003089c  mov     rax, [rdi]
0x18003089f  mov     rcx, rdi
0x1800308a2  mov     rax, [rax]
0x1800308a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308aa  mov     eax, ebp
0x1800308ac  lock xadd [rdi+0Ch], eax
0x1800308b1  cmp     eax, 1
0x1800308b4  jnz     short loc_1800308C5
0x1800308b6  mov     rax, [rdi]
0x1800308b9  mov     rcx, rdi
0x1800308bc  mov     rax, [rax+8]
0x1800308c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308c5  mov     rdi, [rsi+10h]
0x1800308c9  test    rdi, rdi
0x1800308cc  jz      short loc_180030901
0x1800308ce  mov     eax, ebp
0x1800308d0  lock xadd [rdi+8], eax
0x1800308d5  cmp     eax, 1
0x1800308d8  jnz     short loc_180030901
0x1800308da  mov     rax, [rdi]
0x1800308dd  mov     rcx, rdi
0x1800308e0  mov     rax, [rax]
0x1800308e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308e8  lock xadd [rdi+0Ch], ebp
0x1800308ed  cmp     ebp, 1
0x1800308f0  jnz     short loc_180030901
0x1800308f2  mov     rax, [rdi]
0x1800308f5  mov     rcx, rdi
0x1800308f8  mov     rax, [rax+8]
0x1800308fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030901  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180030906  mov     rcx, rsi; void *
0x180030909  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003090e  xor     ebp, ebp
0x180030910  test    rbx, rbx
0x180030913  jnz     loc_1800309B3
0x180030919  mov     rcx, [r15+38h]
0x18003091d  test    rcx, rcx
0x180030920  jz      short loc_180030938
0x180030922  mov     rdx, [rcx]
0x180030925  mov     rax, [rdx+20h]
0x180030929  cmp     rcx, r15
0x18003092c  setnz   dl
0x18003092f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030934  mov     [r15+38h], rbp
0x180030938  mov     eax, r14d
0x18003093b  mov     rbx, [rsp+0A8h+arg_8]
0x180030943  add     rsp, 70h
0x180030947  pop     r15
0x180030949  pop     r14
0x18003094b  pop     r13
0x18003094d  pop     r12
0x18003094f  pop     rdi
0x180030950  pop     rsi
0x180030951  pop     rbp
0x180030952  retn
0x180030953  mov     r14d, 8007000Eh
0x180030959  jmp     short loc_180030910
0x18003095b  mov     rdi, rbp
0x18003095e  jmp     loc_180030687
0x180030963  mov     rsi, rbp
0x180030966  jmp     loc_18003072B
0x18003096b  test    r14d, r14d
0x18003096e  js      short loc_180030919
0x180030970  jmp     loc_1800305E2
0x180030975  test    r14d, r14d
0x180030978  js      short loc_180030919
0x18003097a  jmp     loc_18003062D
0x18003097f  call    cs:__imp_GetLastError
0x180030985  mov     r14d, eax
0x180030988  test    eax, eax
0x18003098a  jle     short loc_18003096B
0x18003098c  movzx   r14d, ax
0x180030990  or      r14d, 80070000h
0x180030997  jmp     short loc_18003096B
0x180030999  call    cs:__imp_GetLastError
0x18003099f  mov     r14d, eax
0x1800309a2  test    eax, eax
0x1800309a4  jle     short loc_180030975
0x1800309a6  movzx   r14d, ax
0x1800309aa  or      r14d, 80070000h
0x1800309b1  jmp     short loc_180030975
0x1800309b3  mov     rdx, rbx
0x1800309b6  call    ??R?$default_delete@U_RecurringTask@@@std@@QEBAXPEAU_RecurringTask@@@Z; std::default_delete<_RecurringTask>::operator()(_RecurringTask *)
0x1800309bb  jmp     loc_180030919
```

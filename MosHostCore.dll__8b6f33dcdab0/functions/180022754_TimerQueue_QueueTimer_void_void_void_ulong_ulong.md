# TimerQueue::QueueTimer(void (*)(void *),void *,ulong,ulong)

- ea: `0x180022754`
- end: `0x18002284d`
- name: `?QueueTimer@TimerQueue@@QEAAJP6AXPEAX@Z0KK@Z`
- size: `249`
- prototype: `int(TimerQueue *__hidden this, void (*)(void *), void *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800142c4`
- `0x18001edb0`
- `0x18001f554`

## callees

- `0x180003860`
- `0x1800120b4`
- `0x180022414`
- `0x18002243c`
- `0x180022754`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227c5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800227bb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800227bb`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180022830`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180022830`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TimerQueue::QueueTimer(HANDLE *this, void (*a2)(void *), void *a3, DWORD a4, DWORD Period)
{
  _QWORD *v9; // rax
  signed int LastError; // eax
  int v11; // r8d
  int v12; // ecx
  unsigned int v13; // ebx
  __int64 *v14; // rcx
  __int64 v15; // rdx
  void *v17[7]; // [rsp+40h] [rbp-38h] BYREF

  v9 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
  {
    v17[0] = 0;
    v11 = 74;
    v12 = -2147024882;
LABEL_12:
    v13 = ZTraceReportOrigination(v12, "TimerQueue::QueueTimer", v11, this);
    goto LABEL_13;
  }
  *(_OWORD *)v9 = 0;
  v17[0] = v9;
  v9[1] = a2;
  v9[2] = a3;
  if ( !CreateTimerQueueTimer((PHANDLE)v9, *this, TimerQueue::TimerRoutine, v9, a4, Period, 0) )
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
    v11 = 86;
    v12 = LastError;
    goto LABEL_12;
  }
  v13 = 0;
  v14 = (__int64 *)(this + 1);
  v15 = (__int64)this[2];
  if ( (HANDLE)v15 == this[3] )
    std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_reallocate<std::unique_ptr<TimerQueue::TimerQueueParam>>(
      v14,
      v15,
      (__int64 *)v17);
  else
    std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_back_with_unused_capacity<std::unique_ptr<TimerQueue::TimerQueueParam>>(
      (__int64)v14,
      (__int64 *)v17);
LABEL_13:
  __1__unique_ptr_UWorkerParam__1____QueueThis_VMigrationEngine___Threadpool__QEAAXPEAVMigrationEngine__P83_EAAJXZ_Z_U__default_delete_UWorkerParam__1____QueueThis_VMigrationEngine___Threadpool__QEAAXPEAVMigrationEngine__P83_EAAJXZ_Z__std___std__QEAA_XZ(v17);
  return v13;
}

```

## disassembly

```asm
0x180022754  push    rbx
0x180022756  push    rbp
0x180022757  push    rsi
0x180022758  push    rdi
0x180022759  sub     rsp, 58h
0x18002275d  mov     ebx, r9d
0x180022760  mov     rsi, r8
0x180022763  mov     rbp, rdx
0x180022766  mov     rdi, rcx
0x180022769  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022770  mov     ecx, 18h; unsigned __int64
0x180022775  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002277a  test    rax, rax
0x18002277d  jz      loc_180022812
0x180022783  xorps   xmm0, xmm0
0x180022786  xor     ecx, ecx
0x180022788  movups  xmmword ptr [rax], xmm0
0x18002278b  mov     [rsp+78h+var_38], rax
0x180022790  mov     [rax+8], rbp
0x180022794  mov     [rax+10h], rsi
0x180022798  mov     [rsp+78h+Flags], ecx; Flags
0x18002279c  mov     ecx, [rsp+78h+arg_20]
0x1800227a3  mov     [rsp+78h+Period], ecx; Period
0x1800227a7  mov     [rsp+78h+DueTime], ebx; DueTime
0x1800227ab  mov     r9, rax; Parameter
0x1800227ae  lea     r8, ?TimerRoutine@TimerQueue@@CAXPEAXE@Z; Callback
0x1800227b5  mov     rdx, [rdi]; TimerQueue
0x1800227b8  mov     rcx, rax; phNewTimer
0x1800227bb  call    cs:__imp_CreateTimerQueueTimer
0x1800227c1  test    eax, eax
0x1800227c3  jnz     short loc_1800227EA
0x1800227c5  call    cs:__imp_GetLastError
0x1800227cb  test    eax, eax
0x1800227cd  jz      short loc_1800227DB
0x1800227cf  jle     short loc_1800227E0
0x1800227d1  movzx   eax, ax
0x1800227d4  or      eax, 80070000h
0x1800227d9  jmp     short loc_1800227E0
0x1800227db  mov     eax, 80390004h
0x1800227e0  mov     r8d, 56h ; 'V'
0x1800227e6  mov     ecx, eax
0x1800227e8  jmp     short loc_180022826
0x1800227ea  xor     ebx, ebx
0x1800227ec  lea     rcx, [rdi+8]
0x1800227f0  mov     rdx, [rcx+8]
0x1800227f4  cmp     rdx, [rcx+10h]
0x1800227f8  jz      short loc_180022806
0x1800227fa  lea     rdx, [rsp+78h+var_38]
0x1800227ff  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_back_with_unused_capacity<std::unique_ptr<TimerQueue::TimerQueueParam>>(std::unique_ptr<TimerQueue::TimerQueueParam> &&)
0x180022804  jmp     short loc_180022838
0x180022806  lea     r8, [rsp+78h+var_38]
0x18002280b  call    ??$_Emplace_reallocate@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@?$vector@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@V?$allocator@V?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UTimerQueueParam@TimerQueue@@U?$default_delete@UTimerQueueParam@TimerQueue@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<TimerQueue::TimerQueueParam>>::_Emplace_reallocate<std::unique_ptr<TimerQueue::TimerQueueParam>>(std::unique_ptr<TimerQueue::TimerQueueParam> * const,std::unique_ptr<TimerQueue::TimerQueueParam> &&)
0x180022810  jmp     short loc_180022838
0x180022812  mov     [rsp+78h+var_38], 0
0x18002281b  mov     r8d, 4Ah ; 'J'
0x180022821  mov     ecx, 8007000Eh
0x180022826  mov     r9, rdi
0x180022829  lea     rdx, aTimerqueueQueu; "TimerQueue::QueueTimer"
0x180022830  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180022836  mov     ebx, eax
0x180022838  lea     rcx, [rsp+78h+var_38]
0x18002283d  call    ??1?$unique_ptr@UWorkerParam@?1???$QueueThis@VMigrationEngine@@@Threadpool@@QEAAXPEAVMigrationEngine@@P83@EAAJXZ@Z@U?$default_delete@UWorkerParam@?1???$QueueThis@VMigrationEngine@@@Threadpool@@QEAAXPEAVMigrationEngine@@P83@EAAJXZ@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam,std::default_delete<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam>>::~unique_ptr<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam,std::default_delete<`Threadpool::QueueThis<MigrationEngine>(MigrationEngine *,long (MigrationEngine::*)(void))'::`2'::WorkerParam>>(void)
0x180022842  mov     eax, ebx
0x180022844  add     rsp, 58h
0x180022848  pop     rdi
0x180022849  pop     rsi
0x18002284a  pop     rbp
0x18002284b  pop     rbx
0x18002284c  retn
```

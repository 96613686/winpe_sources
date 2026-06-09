# Utility::PrioritizedTaskQueue::executeNextTask(void)

- ea: `0x18003afb0`
- end: `0x18003b1de`
- name: `?executeNextTask@PrioritizedTaskQueue@Utility@@AEAAXXZ`
- size: `558`
- prototype: `void __fastcall(Utility::PrioritizedTaskQueue *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000c2f8`
- `0x18000cb24`
- `0x180010f34`
- `0x180013da8`
- `0x180014cd8`
- `0x1800188f0`
- `0x18001c1cc`
- `0x180029e58`
- `0x180029ed0`
- `0x18003af24`
- `0x18003afb0`
- `0x18003bc30`
- `0x18003bce0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b137`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b002`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b14d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b14d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Utility::PrioritizedTaskQueue::executeNextTask(Utility::PrioritizedTaskQueue *this)
{
  unsigned int v2; // r15d
  _QWORD *v3; // rsi
  _QWORD *i; // rbx
  unsigned int v5; // eax
  unsigned int **v6; // rax
  unsigned int *v7; // r13
  std::_Ref_count_base *v8; // r15
  __int64 v9; // rcx
  RTL_SRWLOCK *Instance; // rax
  __int64 v11; // rcx
  RTL_SRWLOCK *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // [rsp+20h] [rbp-69h] BYREF
  std::_Ref_count_base *v15; // [rsp+28h] [rbp-61h]
  __int64 v16; // [rsp+30h] [rbp-59h]
  __int128 v17; // [rsp+38h] [rbp-51h]
  _QWORD v18[8]; // [rsp+50h] [rbp-39h] BYREF

  v17 = 0;
  if ( (unsigned __int64)Pal::TaskQueue::size((Utility::PrioritizedTaskQueue *)((char *)this + 16)) > *((_QWORD *)this + 1) )
  {
    v8 = (std::_Ref_count_base *)*((_QWORD *)&v17 + 1);
  }
  else
  {
    v14 = (__int64)this + 24;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v2 = 0;
    v3 = (_QWORD *)*((_QWORD *)this + 9);
    for ( i = (_QWORD *)*((_QWORD *)this + 8); (unsigned __int64)i < *((_QWORD *)this + 9); i += 2 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*i + 408LL) + 8LL))(*(_QWORD *)(*i + 408LL));
      if ( v5 > v2 )
      {
        v3 = i;
        if ( v5 == -1 )
          break;
        v2 = v5;
      }
    }
    if ( v3 == *((_QWORD **)this + 9) )
    {
      v8 = (std::_Ref_count_base *)*((_QWORD *)&v17 + 1);
      v7 = (unsigned int *)v17;
    }
    else
    {
      v6 = (unsigned int **)std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(
                              &v14,
                              v3);
      v7 = *v6;
      *v6 = 0;
      *(_QWORD *)&v17 = v7;
      v8 = (std::_Ref_count_base *)v6[1];
      v6[1] = 0;
      *((_QWORD *)&v17 + 1) = v8;
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      std::vector<std::shared_ptr<Utility::PrioritizableTask>>::erase((char *)this + 64, &v14, v3);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( v7 )
    {
      v16 = v7[6];
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7 + 106);
      Instance = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Utility::UtilityPerformanceTracer>::getInstance(v9);
      Pal::PerformanceTracer::traceEvent<unsigned short const * &,__int64 &>(
        Instance,
        (struct Pal::PerformanceEventId *)&dword_18007BCF0);
      Pal::Task::run((Pal::Task *)v7);
      v14 = v7[6];
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7 + 106);
      v12 = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Utility::UtilityPerformanceTracer>::getInstance(v11);
      Pal::PerformanceTracer::traceEvent<unsigned short const * &,__int64 &>(
        v12,
        (struct Pal::PerformanceEventId *)&dword_18007BCE0);
      if ( (unsigned __int64)Pal::TaskQueue::size((Utility::PrioritizedTaskQueue *)((char *)this + 16)) <= *((_QWORD *)this + 1) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        v13 = (__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 4;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        if ( v13 )
        {
          if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 88) )
          {
            v18[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Utility::PrioritizedTaskQueue::*)(void),Utility::PrioritizedTaskQueue *>,void,>::`vftable';
            v18[1] = Utility::PrioritizedTaskQueue::executeNextTask;
            v18[2] = this;
            v18[7] = v18;
            Pal::TaskQueue::addTask((char *)this + 16, &v14, v18);
            Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v14);
            std::_Func_class<void,>::_Tidy(v18);
          }
        }
      }
    }
  }
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
}

```

## disassembly

```asm
0x18003afb0  push    rbp
0x18003afb2  push    rbx
0x18003afb3  push    rsi
0x18003afb4  push    rdi
0x18003afb5  push    r12
0x18003afb7  push    r13
0x18003afb9  push    r14
0x18003afbb  push    r15
0x18003afbd  lea     rbp, [rsp-1Fh]
0x18003afc2  sub     rsp, 0A8h
0x18003afc9  mov     rax, cs:__security_cookie
0x18003afd0  xor     rax, rsp
0x18003afd3  mov     [rbp+57h+var_50], rax
0x18003afd7  mov     r14, rcx
0x18003afda  xorps   xmm0, xmm0
0x18003afdd  movdqu  [rbp+57h+var_A8], xmm0
0x18003afe2  add     rcx, 10h; this
0x18003afe6  call    ?size@TaskQueue@Pal@@QEBAIXZ; Pal::TaskQueue::size(void)
0x18003afeb  mov     eax, eax
0x18003afed  cmp     rax, [r14+8]
0x18003aff1  ja      loc_18003B1AD
0x18003aff7  lea     rdi, [r14+18h]
0x18003affb  mov     [rbp+57h+var_C0], rdi
0x18003afff  mov     rcx, rdi; lpCriticalSection
0x18003b002  call    cs:__imp_EnterCriticalSection
0x18003b008  nop
0x18003b009  xor     r15d, r15d
0x18003b00c  lea     r12, [r14+40h]
0x18003b010  mov     rsi, [r12+8]
0x18003b015  mov     rbx, [r12]
0x18003b019  cmp     rbx, [r14+48h]
0x18003b01d  jnb     short loc_18003B04B
0x18003b01f  mov     rax, [rbx]
0x18003b022  mov     rcx, [rax+198h]
0x18003b029  mov     rax, [rcx]
0x18003b02c  mov     rax, [rax+8]
0x18003b030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b035  cmp     eax, r15d
0x18003b038  jbe     short loc_18003B045
0x18003b03a  mov     rsi, rbx
0x18003b03d  cmp     eax, 0FFFFFFFFh
0x18003b040  jz      short loc_18003B04B
0x18003b042  mov     r15d, eax
0x18003b045  add     rbx, 10h
0x18003b049  jmp     short loc_18003B019
0x18003b04b  cmp     rsi, [r14+48h]
0x18003b04f  jz      short loc_18003B09A
0x18003b051  mov     rdx, rsi
0x18003b054  lea     rcx, [rbp+57h+var_C0]
0x18003b058  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18003b05d  mov     r13, [rax]
0x18003b060  mov     qword ptr [rax], 0
0x18003b067  mov     qword ptr [rbp+57h+var_A8], r13
0x18003b06b  mov     r15, [rax+8]
0x18003b06f  mov     qword ptr [rax+8], 0
0x18003b077  mov     qword ptr [rbp+57h+var_A8+8], r15
0x18003b07b  mov     rcx, [rbp+57h+var_B8]; this
0x18003b07f  test    rcx, rcx
0x18003b082  jz      short loc_18003B089
0x18003b084  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b089  mov     r8, rsi
0x18003b08c  lea     rdx, [rbp+57h+var_C0]
0x18003b090  mov     rcx, r12
0x18003b093  call    ?erase@?$vector@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@V?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<Utility::PrioritizableTask>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<Utility::PrioritizableTask>>>>)
0x18003b098  jmp     short loc_18003B0A2
0x18003b09a  mov     r15, qword ptr [rbp+57h+var_A8+8]
0x18003b09e  mov     r13, qword ptr [rbp+57h+var_A8]
0x18003b0a2  mov     rcx, rdi; lpCriticalSection
0x18003b0a5  call    cs:__imp_LeaveCriticalSection
0x18003b0ab  test    r13, r13
0x18003b0ae  jz      loc_18003B1B1
0x18003b0b4  mov     eax, [r13+18h]
0x18003b0b8  mov     [rbp+57h+var_B0], rax
0x18003b0bc  lea     rbx, [r13+1A8h]
0x18003b0c3  mov     rcx, rbx
0x18003b0c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003b0cb  mov     [rbp+57h+var_C0], rax
0x18003b0cf  call    ?getInstance@?$PerformanceTracerSingleton@VUtilityPerformanceTracer@Utility@@@Pal@@KAAEAVUtilityPerformanceTracer@Utility@@XZ; Pal::PerformanceTracerSingleton<Utility::UtilityPerformanceTracer>::getInstance(void)
0x18003b0d4  lea     r9, [rbp+57h+var_B0]
0x18003b0d8  lea     r8, [rbp+57h+var_C0]
0x18003b0dc  lea     rdx, dword_18007BCF0; struct Pal::PerformanceEventId *
0x18003b0e3  mov     rcx, rax; SRWLock
0x18003b0e6  call    ??$traceEvent@AEAPEBGAEA_J@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEA_J@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,__int64 &>(Pal::PerformanceEventId const &,ushort const * &,__int64 &)
0x18003b0eb  mov     rcx, r13; this
0x18003b0ee  call    ?run@Task@Pal@@QEAAXXZ; Pal::Task::run(void)
0x18003b0f3  mov     eax, [r13+18h]
0x18003b0f7  mov     [rbp+57h+var_C0], rax
0x18003b0fb  mov     rcx, rbx
0x18003b0fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003b103  mov     [rbp+57h+var_B0], rax
0x18003b107  call    ?getInstance@?$PerformanceTracerSingleton@VUtilityPerformanceTracer@Utility@@@Pal@@KAAEAVUtilityPerformanceTracer@Utility@@XZ; Pal::PerformanceTracerSingleton<Utility::UtilityPerformanceTracer>::getInstance(void)
0x18003b10c  lea     r9, [rbp+57h+var_C0]
0x18003b110  lea     r8, [rbp+57h+var_B0]
0x18003b114  lea     rdx, dword_18007BCE0; struct Pal::PerformanceEventId *
0x18003b11b  mov     rcx, rax; SRWLock
0x18003b11e  call    ??$traceEvent@AEAPEBGAEA_J@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEA_J@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,__int64 &>(Pal::PerformanceEventId const &,ushort const * &,__int64 &)
0x18003b123  lea     rcx, [r14+10h]; this
0x18003b127  call    ?size@TaskQueue@Pal@@QEBAIXZ; Pal::TaskQueue::size(void)
0x18003b12c  mov     eax, eax
0x18003b12e  cmp     rax, [r14+8]
0x18003b132  ja      short loc_18003B1B1
0x18003b134  mov     rcx, rdi; lpCriticalSection
0x18003b137  call    cs:__imp_EnterCriticalSection
0x18003b13d  mov     rbx, [r12+8]
0x18003b142  sub     rbx, [r12]
0x18003b146  sar     rbx, 4
0x18003b14a  mov     rcx, rdi; lpCriticalSection
0x18003b14d  call    cs:__imp_LeaveCriticalSection
0x18003b153  test    rbx, rbx
0x18003b156  jz      short loc_18003B1B1
0x18003b158  lea     rcx, [r14+58h]
0x18003b15c  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18003b161  test    al, al
0x18003b163  jnz     short loc_18003B1B1
0x18003b165  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8PrioritizedTaskQueue@Utility@@EAAXXZPEAV34@@std@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Utility::PrioritizedTaskQueue::*)(void),Utility::PrioritizedTaskQueue *>,void,>::`vftable'
0x18003b16c  mov     [rbp+57h+var_90], rax
0x18003b170  lea     rax, ?executeNextTask@PrioritizedTaskQueue@Utility@@AEAAXXZ; Utility::PrioritizedTaskQueue::executeNextTask(void)
0x18003b177  mov     [rbp+57h+var_88], rax
0x18003b17b  mov     [rbp+57h+var_80], r14
0x18003b17f  lea     rax, [rbp+57h+var_90]
0x18003b183  mov     [rbp+57h+var_58], rax
0x18003b187  lea     r8, [rbp+57h+var_90]
0x18003b18b  lea     rdx, [rbp+57h+var_C0]
0x18003b18f  lea     rcx, [r14+10h]
0x18003b193  call    ?addTask@TaskQueue@Pal@@QEAA?AV?$PresentSharedPtr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@Core@@AEBV?$function@$$A6AXXZ@std@@@Z; Pal::TaskQueue::addTask(std::function<void (void)> const &)
0x18003b198  lea     rcx, [rbp+57h+var_C0]
0x18003b19c  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18003b1a1  nop
0x18003b1a2  lea     rcx, [rbp+57h+var_90]
0x18003b1a6  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18003b1ab  jmp     short loc_18003B1B1
0x18003b1ad  mov     r15, qword ptr [rbp+57h+var_A8+8]
0x18003b1b1  test    r15, r15
0x18003b1b4  jz      short loc_18003B1BE
0x18003b1b6  mov     rcx, r15; this
0x18003b1b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b1be  mov     rcx, [rbp+57h+var_50]
0x18003b1c2  xor     rcx, rsp; StackCookie
0x18003b1c5  call    __security_check_cookie
0x18003b1ca  add     rsp, 0A8h
0x18003b1d1  pop     r15
0x18003b1d3  pop     r14
0x18003b1d5  pop     r13
0x18003b1d7  pop     r12
0x18003b1d9  pop     rdi
0x18003b1da  pop     rsi
0x18003b1db  pop     rbx
0x18003b1dc  pop     rbp
0x18003b1dd  retn
```

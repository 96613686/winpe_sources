# Utility::PrioritizedTaskQueue::add(std::shared_ptr<Utility::PrioritizableTask> const &)

- ea: `0x18003abf0`
- end: `0x18003ad5f`
- name: `?add@PrioritizedTaskQueue@Utility@@UEAA?AV?$shared_ptr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@std@@AEBV?$shared_ptr@VPrioritizableTask@Utility@@@4@@Z`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000c2f8`
- `0x18000cb24`
- `0x180010f34`
- `0x180014cd8`
- `0x1800163c4`
- `0x1800188f0`
- `0x18001e804`
- `0x180029e58`
- `0x180029ed0`
- `0x18003abf0`
- `0x18003bc30`
- `0x18003bce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003ad58`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003ad58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ac7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ac7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003accc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003accc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Utility::PrioritizedTaskQueue::add(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *Cancelled; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  RTL_SRWLOCK *Instance; // rax
  __int64 v11; // rax
  _QWORD v12[5]; // [rsp+28h] [rbp-41h] BYREF
  _QWORD v13[8]; // [rsp+50h] [rbp-19h] BYREF

  if ( !*a3 )
  {
    _o_terminate(0, a2);
    JUMPOUT(0x18003AD5ELL);
  }
  if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load(*a3 + 149LL) )
  {
    Cancelled = (_QWORD *)Pal::AsyncOperation<Core::DummyType>::createCancelled(v12);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(a2, Cancelled);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v12);
  }
  else
  {
    v12[0] = a1 + 24;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v8 = *a3;
    v12[3] = *(unsigned int *)(*a3 + 24LL);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8 + 424);
    Instance = (RTL_SRWLOCK *)Pal::PerformanceTracerSingleton<Utility::UtilityPerformanceTracer>::getInstance(v9);
    Pal::PerformanceTracer::traceEvent<unsigned short const * &,__int64 &>(
      Instance,
      (struct Pal::PerformanceEventId *)&dword_18007BCD0);
    std::vector<std::shared_ptr<Utility::PrioritizableTask>>::emplace_back<std::shared_ptr<Utility::PrioritizableTask> const &>(
      (__int64 *)(a1 + 64),
      (__int64)a3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    if ( (unsigned __int64)Pal::TaskQueue::size((Pal::TaskQueue *)(a1 + 16)) < *(_QWORD *)(a1 + 8) )
    {
      v13[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Utility::PrioritizedTaskQueue::*)(void),Utility::PrioritizedTaskQueue *>,void,>::`vftable';
      v13[1] = Utility::PrioritizedTaskQueue::executeNextTask;
      v13[2] = a1;
      v13[7] = v13;
      Pal::TaskQueue::addTask(a1 + 16, v12, v13);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v12);
      std::_Func_class<void,>::_Tidy(v13);
    }
    *a2 = 0;
    a2[1] = 0;
    v11 = a3[1];
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
    *a2 = *a3;
    a2[1] = a3[1];
  }
  return a2;
}

```

## disassembly

```asm
0x18003abf0  push    rbp
0x18003abf2  push    rbx
0x18003abf3  push    rsi
0x18003abf4  push    rdi
0x18003abf5  push    r14
0x18003abf7  lea     rbp, [rsp-37h]
0x18003abfc  sub     rsp, 0A0h
0x18003ac03  mov     rax, cs:__security_cookie
0x18003ac0a  xor     rax, rsp
0x18003ac0d  mov     [rbp+57h+var_30], rax
0x18003ac11  mov     rsi, r8
0x18003ac14  mov     rdi, rdx
0x18003ac17  mov     r14, rcx
0x18003ac1a  mov     [rbp+57h+var_A0], rdx
0x18003ac1e  mov     rcx, [r8]
0x18003ac21  test    rcx, rcx
0x18003ac24  jz      loc_18003AD58
0x18003ac2a  add     rcx, 95h
0x18003ac31  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18003ac36  test    al, al
0x18003ac38  jz      short loc_18003AC74
0x18003ac3a  lea     rcx, [rbp+57h+var_98]
0x18003ac3e  call    ?createCancelled@?$AsyncOperation@UDummyType@Core@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@Core@@XZ; Pal::AsyncOperation<Core::DummyType>::createCancelled(void)
0x18003ac43  mov     rdx, rax
0x18003ac46  mov     rcx, rdi
0x18003ac49  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18003ac4e  lea     rcx, [rbp+57h+var_98]
0x18003ac52  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18003ac57  mov     rax, rdi
0x18003ac5a  mov     rcx, [rbp+57h+var_30]
0x18003ac5e  xor     rcx, rsp; StackCookie
0x18003ac61  call    __security_check_cookie
0x18003ac66  add     rsp, 0A0h
0x18003ac6d  pop     r14
0x18003ac6f  pop     rdi
0x18003ac70  pop     rsi
0x18003ac71  pop     rbx
0x18003ac72  pop     rbp
0x18003ac73  retn
0x18003ac74  lea     rbx, [r14+18h]
0x18003ac78  mov     [rbp+57h+var_98], rbx
0x18003ac7c  mov     rcx, rbx; lpCriticalSection
0x18003ac7f  call    cs:__imp_EnterCriticalSection
0x18003ac85  nop
0x18003ac86  mov     rcx, [rsi]
0x18003ac89  mov     eax, [rcx+18h]
0x18003ac8c  mov     [rbp+57h+var_80], rax
0x18003ac90  add     rcx, 1A8h
0x18003ac97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ac9c  mov     [rbp+57h+var_A0], rax
0x18003aca0  call    ?getInstance@?$PerformanceTracerSingleton@VUtilityPerformanceTracer@Utility@@@Pal@@KAAEAVUtilityPerformanceTracer@Utility@@XZ; Pal::PerformanceTracerSingleton<Utility::UtilityPerformanceTracer>::getInstance(void)
0x18003aca5  lea     r9, [rbp+57h+var_80]
0x18003aca9  lea     r8, [rbp+57h+var_A0]
0x18003acad  lea     rdx, dword_18007BCD0; struct Pal::PerformanceEventId *
0x18003acb4  mov     rcx, rax; SRWLock
0x18003acb7  call    ??$traceEvent@AEAPEBGAEA_J@PerformanceTracer@Pal@@QEAAXAEBVPerformanceEventId@1@AEAPEBGAEA_J@Z; Pal::PerformanceTracer::traceEvent<ushort const * &,__int64 &>(Pal::PerformanceEventId const &,ushort const * &,__int64 &)
0x18003acbc  lea     rcx, [r14+40h]
0x18003acc0  mov     rdx, rsi
0x18003acc3  call    ??$emplace_back@AEBV?$shared_ptr@VPrioritizableTask@Utility@@@std@@@?$vector@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@V?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VPrioritizableTask@Utility@@@1@AEBV21@@Z; std::vector<std::shared_ptr<Utility::PrioritizableTask>>::emplace_back<std::shared_ptr<Utility::PrioritizableTask> const &>(std::shared_ptr<Utility::PrioritizableTask> const &)
0x18003acc8  nop
0x18003acc9  mov     rcx, rbx; lpCriticalSection
0x18003accc  call    cs:__imp_LeaveCriticalSection
0x18003acd2  lea     rcx, [r14+10h]; this
0x18003acd6  call    ?size@TaskQueue@Pal@@QEBAIXZ; Pal::TaskQueue::size(void)
0x18003acdb  mov     eax, eax
0x18003acdd  cmp     rax, [r14+8]
0x18003ace1  jnb     short loc_18003AD29
0x18003ace3  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8PrioritizedTaskQueue@Utility@@EAAXXZPEAV34@@std@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Utility::PrioritizedTaskQueue::*)(void),Utility::PrioritizedTaskQueue *>,void,>::`vftable'
0x18003acea  mov     [rbp+57h+var_70], rax
0x18003acee  lea     rax, ?executeNextTask@PrioritizedTaskQueue@Utility@@AEAAXXZ; Utility::PrioritizedTaskQueue::executeNextTask(void)
0x18003acf5  mov     [rbp+57h+var_68], rax
0x18003acf9  mov     [rbp+57h+var_60], r14
0x18003acfd  lea     rax, [rbp+57h+var_70]
0x18003ad01  mov     [rbp+57h+var_38], rax
0x18003ad05  lea     r8, [rbp+57h+var_70]
0x18003ad09  lea     rdx, [rbp+57h+var_98]
0x18003ad0d  lea     rcx, [r14+10h]
0x18003ad11  call    ?addTask@TaskQueue@Pal@@QEAA?AV?$PresentSharedPtr@V?$AsyncOperation@UDummyType@Core@@@Pal@@@Core@@AEBV?$function@$$A6AXXZ@std@@@Z; Pal::TaskQueue::addTask(std::function<void (void)> const &)
0x18003ad16  lea     rcx, [rbp+57h+var_98]
0x18003ad1a  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x18003ad1f  nop
0x18003ad20  lea     rcx, [rbp+57h+var_70]
0x18003ad24  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18003ad29  mov     qword ptr [rdi], 0
0x18003ad30  mov     qword ptr [rdi+8], 0
0x18003ad38  mov     rax, [rsi+8]
0x18003ad3c  test    rax, rax
0x18003ad3f  jz      short loc_18003AD45
0x18003ad41  lock inc dword ptr [rax+8]
0x18003ad45  mov     rax, [rsi]
0x18003ad48  mov     [rdi], rax
0x18003ad4b  mov     rax, [rsi+8]
0x18003ad4f  mov     [rdi+8], rax
0x18003ad53  jmp     loc_18003AC57
0x18003ad58  call    cs:__imp__o_terminate
```

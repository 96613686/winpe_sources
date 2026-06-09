# Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)

- ea: `0x18001dae4`
- end: `0x18001db87`
- name: `?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z`
- size: `163`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001c140`
- `0x18001da24`

## callees

- `0x18000288c`
- `0x18000e184`
- `0x18000f864`
- `0x18000f958`
- `0x18001bfe0`
- `0x18001cc40`
- `0x18001dae4`
- `0x18001ec74`
- `0x180025010`

## pseudocode

```c
void __fastcall Concurrency::details::_ScheduleFuncWithAutoInline(__int64 a1, int a2)
{
  void *v3; // rsi
  void (__fastcall ***v4)(_QWORD, void (__fastcall *)(void *), void *); // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v5; // [rsp+28h] [rbp-10h]
  void *v6; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x40u);
  v6 = v3;
  std::function<void (void)>::function<void (void)>(v3);
  if ( a2 == -1 )
  {
    Concurrency::details::_TaskProcThunk::_Bridge(v3);
  }
  else
  {
    std::call_once<_lambda_0e64988457575224279dcb6d61e61bdd_,>();
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      &v4,
      (_QWORD *)`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address);
    if ( v4 )
      (**v4)(v4, Concurrency::details::_TaskProcThunk::_Bridge, v3);
    else
      Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        (Concurrency::details::_DefaultPPLTaskScheduler *)&v6,
        (void (*)(void *))Concurrency::details::_TaskProcThunk::_Bridge,
        v3);
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
}

```

## disassembly

```asm
0x18001dae4  mov     [rsp+arg_0], rbx
0x18001dae9  mov     [rsp+arg_8], rsi
0x18001daee  push    rdi
0x18001daef  sub     rsp, 30h
0x18001daf3  mov     edi, edx
0x18001daf5  mov     rbx, rcx
0x18001daf8  mov     ecx, 40h ; '@'; Size
0x18001dafd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001db02  mov     rsi, rax
0x18001db05  mov     [rsp+38h+arg_10], rax
0x18001db0a  mov     rdx, rbx
0x18001db0d  mov     rcx, rax
0x18001db10  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18001db15  nop
0x18001db16  cmp     edi, 0FFFFFFFFh
0x18001db19  jnz     short loc_18001DB25
0x18001db1b  mov     rcx, rsi; void *
0x18001db1e  call    ?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z; Concurrency::details::_TaskProcThunk::_Bridge(void *)
0x18001db23  jmp     short loc_18001DB77
0x18001db25  call    ??$call_once@V_lambda_0e64988457575224279dcb6d61e61bdd_@@$$V@std@@YAXAEAUonce_flag@0@$$QEAV_lambda_0e64988457575224279dcb6d61e61bdd_@@@Z; std::call_once<_lambda_0e64988457575224279dcb6d61e61bdd_,>(std::once_flag &,_lambda_0e64988457575224279dcb6d61e61bdd_ &&)
0x18001db2a  mov     rdx, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18001db31  lea     rcx, [rsp+38h+var_18]
0x18001db36  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001db3b  nop
0x18001db3c  mov     rcx, [rsp+38h+var_18]
0x18001db41  mov     r8, rsi; void *
0x18001db44  lea     rdx, ?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z; void (*)(void *)
0x18001db4b  test    rcx, rcx
0x18001db4e  jz      short loc_18001DB5D
0x18001db50  mov     rax, [rcx]
0x18001db53  mov     rax, [rax]
0x18001db56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db5b  jmp     short loc_18001DB68
0x18001db5d  lea     rcx, [rsp+38h+arg_10]; this
0x18001db62  call    ?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z; Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)
0x18001db67  nop
0x18001db68  mov     rcx, [rsp+38h+var_10]; this
0x18001db6d  test    rcx, rcx
0x18001db70  jz      short loc_18001DB77
0x18001db72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001db77  mov     rbx, [rsp+38h+arg_0]
0x18001db7c  mov     rsi, [rsp+38h+arg_8]
0x18001db81  add     rsp, 30h
0x18001db85  pop     rdi
0x18001db86  retn
```

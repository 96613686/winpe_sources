# Concurrency::task_options::task_options(void)

- ea: `0x1800108f0`
- end: `0x180010982`
- name: `??0task_options@Concurrency@@QEAA@XZ`
- size: `146`
- prototype: `Concurrency::task_options *__fastcall(Concurrency::task_options *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001b34c`

## callees

- `0x18000e184`
- `0x18000f958`
- `0x18001030c`
- `0x1800108f0`
- `0x18001cc40`
- `0x18001ed08`

## pseudocode

```c
Concurrency::task_options *__fastcall Concurrency::task_options::task_options(Concurrency::task_options *this)
{
  _QWORD *v2; // rax
  std::_Ref_count_base *v3; // rcx
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  std::call_once<_lambda_0e64988457575224279dcb6d61e61bdd_,>();
  v2 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
         v5,
         (_QWORD *)`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = *v2;
  *((_QWORD *)this + 1) = v2[1];
  *v2 = 0;
  v2[1] = 0;
  *((_QWORD *)this + 2) = *(_QWORD *)this;
  v3 = (std::_Ref_count_base *)v2[1];
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  *((_QWORD *)this + 3) = 0;
  Concurrency::task_continuation_context::use_default((char *)this + 32);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::task_options *)((char *)this + 56));
  *((_BYTE *)this + 48) = 0;
  *((_WORD *)this + 44) = 0;
  return this;
}

```

## disassembly

```asm
0x1800108f0  mov     [rsp+arg_0], rcx
0x1800108f5  push    rbx
0x1800108f6  sub     rsp, 30h
0x1800108fa  mov     rbx, rcx
0x1800108fd  call    ??$call_once@V_lambda_0e64988457575224279dcb6d61e61bdd_@@$$V@std@@YAXAEAUonce_flag@0@$$QEAV_lambda_0e64988457575224279dcb6d61e61bdd_@@@Z; std::call_once<_lambda_0e64988457575224279dcb6d61e61bdd_,>(std::once_flag &,_lambda_0e64988457575224279dcb6d61e61bdd_ &&)
0x180010902  mov     rdx, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x180010909  lea     rcx, [rsp+38h+var_18]
0x18001090e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x180010913  mov     qword ptr [rbx], 0
0x18001091a  mov     qword ptr [rbx+8], 0
0x180010922  mov     rcx, [rax]
0x180010925  mov     [rbx], rcx
0x180010928  mov     rcx, [rax+8]
0x18001092c  mov     [rbx+8], rcx
0x180010930  mov     qword ptr [rax], 0
0x180010937  mov     qword ptr [rax+8], 0
0x18001093f  mov     rcx, [rbx]
0x180010942  mov     [rbx+10h], rcx
0x180010946  mov     rcx, [rax+8]; this
0x18001094a  test    rcx, rcx
0x18001094d  jz      short loc_180010955
0x18001094f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010954  nop
0x180010955  mov     qword ptr [rbx+18h], 0
0x18001095d  lea     rcx, [rbx+20h]
0x180010961  call    ?use_default@task_continuation_context@Concurrency@@SA?AV12@XZ; Concurrency::task_continuation_context::use_default(void)
0x180010966  lea     rcx, [rbx+38h]; this
0x18001096a  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18001096f  mov     byte ptr [rbx+30h], 0
0x180010973  mov     word ptr [rbx+58h], 0
0x180010979  mov     rax, rbx
0x18001097c  add     rsp, 30h
0x180010980  pop     rbx
0x180010981  retn
```

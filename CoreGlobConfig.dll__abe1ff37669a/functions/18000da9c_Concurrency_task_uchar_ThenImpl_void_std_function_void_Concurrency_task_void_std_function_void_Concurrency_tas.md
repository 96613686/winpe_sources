# Concurrency::task<uchar>::_ThenImpl<void,std::function<void (Concurrency::task<void>)>>(std::function<void (Concurrency::task<void>)> const &,Concurrency::details::_ThenImplOptions &)

- ea: `0x18000da9c`
- end: `0x18000dba9`
- name: `??$_ThenImpl@XV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@@?$task@E@Concurrency@@AEBA?AV?$task@X@1@AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@AEAU_ThenImplOptions@details@1@@Z`
- size: `269`
- prototype: `_QWORD *__fastcall(Concurrency::details::_Task_impl_base **, _QWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000ee28`

## callees

- `0x18000288c`
- `0x18000da9c`
- `0x18000f4d8`
- `0x18000f958`
- `0x18001c8bc`
- `0x18001cc40`
- `0x18001d904`
- `0x18001dbe8`

## pseudocode

```c
_QWORD *__fastcall Concurrency::task<unsigned char>::_ThenImpl<void,std::function<void (Concurrency::task<void>)>>(
        Concurrency::details::_Task_impl_base **a1,
        _QWORD *a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r9
  Concurrency::details::_Task_impl_base *v10; // rbx
  struct Concurrency::details::_ContinuationTaskHandleBase *v11; // rax
  _BYTE v13[8]; // [rsp+38h] [rbp-38h] BYREF
  std::_Ref_count_base *v14; // [rsp+40h] [rbp-30h]
  __int64 v15; // [rsp+48h] [rbp-28h]
  _BYTE v16[16]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  unsigned int v18; // [rsp+A0h] [rbp+30h]

  if ( !*(_QWORD *)a4 )
    *(_QWORD *)a4 = 2;
  *a2 = 0;
  a2[1] = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v13,
    a4 + 8);
  v15 = *(_QWORD *)(v8 + 16);
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v16,
    v13);
  v17 = v15;
  Concurrency::task<unsigned char>::_CreateImpl(a2, v9, v16);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  *(_BYTE *)(*a2 + 12LL) = *((_BYTE *)*a1 + 12) != 0;
  *(_BYTE *)(*a2 + 13LL) = 0;
  Concurrency::task<unsigned char>::_SetTaskCreationCallstack(a2, a4 + 32);
  v10 = *a1;
  v18 = (unsigned int)operator new(0x88u);
  v11 = (struct Concurrency::details::_ContinuationTaskHandleBase *)Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(
                                                                      v18,
                                                                      (_DWORD)a1,
                                                                      (_DWORD)a2,
                                                                      a3,
                                                                      *(_QWORD *)(a4 + 72),
                                                                      *(_DWORD *)(a4 + 64));
  Concurrency::details::_Task_impl_base::_ScheduleContinuation(v10, v11);
  return a2;
}

```

## disassembly

```asm
0x18000da9c  mov     [rsp-28h+arg_10], rbx
0x18000daa1  mov     [rsp-28h+arg_8], rdx
0x18000daa6  push    rbp
0x18000daa7  push    rsi
0x18000daa8  push    rdi
0x18000daa9  push    r14
0x18000daab  push    r15
0x18000daad  mov     rbp, rsp
0x18000dab0  sub     rsp, 70h
0x18000dab4  mov     rdi, r9
0x18000dab7  mov     r15, r8
0x18000daba  mov     rsi, rdx
0x18000dabd  mov     r14, rcx
0x18000dac0  xor     ebx, ebx
0x18000dac2  mov     [rbp+var_40], ebx
0x18000dac5  cmp     [r9], rbx
0x18000dac8  jnz     short loc_18000DAD1
0x18000daca  mov     qword ptr [r9], 2
0x18000dad1  mov     [rdx], rbx
0x18000dad4  mov     [rdx+8], rbx
0x18000dad8  mov     [rbp+var_40], 1
0x18000dadf  lea     rdx, [r9+8]
0x18000dae3  lea     rcx, [rbp+var_38]
0x18000dae7  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18000daec  mov     rcx, [rdx+10h]
0x18000daf0  mov     [rbp+var_28], rcx
0x18000daf4  lea     rax, [rbp+var_38]
0x18000daf8  mov     [rbp+arg_0], rax
0x18000dafc  mov     r9, [r9]
0x18000daff  lea     rdx, [rbp+var_38]
0x18000db03  lea     rcx, [rbp+var_20]
0x18000db07  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18000db0c  mov     rcx, [rbp+var_28]
0x18000db10  mov     [rbp+var_10], rcx
0x18000db14  lea     r8, [rbp+var_20]
0x18000db18  mov     rdx, r9
0x18000db1b  mov     rcx, rsi
0x18000db1e  call    ?_CreateImpl@?$task@E@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<uchar>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x18000db23  nop
0x18000db24  mov     rcx, [rbp+var_30]; this
0x18000db28  test    rcx, rcx
0x18000db2b  jz      short loc_18000DB32
0x18000db2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000db32  mov     rax, [r14]
0x18000db35  cmp     [rax+0Ch], bl
0x18000db38  setnz   cl
0x18000db3b  mov     rax, [rsi]
0x18000db3e  mov     [rax+0Ch], cl
0x18000db41  mov     rax, [rsi]
0x18000db44  mov     [rax+0Dh], bl
0x18000db47  lea     rdx, [rdi+20h]
0x18000db4b  mov     rcx, rsi
0x18000db4e  call    ?_SetTaskCreationCallstack@?$task@E@Concurrency@@QEAAXAEBV_TaskCreationCallstack@details@2@@Z; Concurrency::task<uchar>::_SetTaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18000db53  mov     rbx, [r14]
0x18000db56  mov     ecx, 88h; Size
0x18000db5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db60  mov     [rbp+arg_0], rax
0x18000db64  mov     edx, [rdi+40h]
0x18000db67  mov     [rsp+70h+var_48], edx
0x18000db6b  mov     rdx, [rdi+48h]
0x18000db6f  mov     [rsp+70h+var_50], rdx
0x18000db74  mov     r9, r15
0x18000db77  mov     r8, rsi
0x18000db7a  mov     rdx, r14
0x18000db7d  mov     rcx, rax
0x18000db80  call    ??0?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@0AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@4@AEBVtask_continuation_context@2@W4_TaskInliningMode@details@2@@Z; Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &,std::function<void (Concurrency::task<void>)> const &,Concurrency::task_continuation_context const &,Concurrency::details::_TaskInliningMode)
0x18000db85  nop
0x18000db86  mov     rdx, rax; struct Concurrency::details::_ContinuationTaskHandleBase *
0x18000db89  mov     rcx, rbx; this
0x18000db8c  call    ?_ScheduleContinuation@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuation(Concurrency::details::_ContinuationTaskHandleBase *)
0x18000db91  mov     rax, rsi
0x18000db94  mov     rbx, [rsp+70h+arg_10]
0x18000db9c  add     rsp, 70h
0x18000dba0  pop     r15
0x18000dba2  pop     r14
0x18000dba4  pop     rdi
0x18000dba5  pop     rsi
0x18000dba6  pop     rbp
0x18000dba7  retn
```

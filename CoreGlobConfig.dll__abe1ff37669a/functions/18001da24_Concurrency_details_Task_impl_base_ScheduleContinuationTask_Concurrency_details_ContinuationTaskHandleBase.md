# Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x18001da24`
- end: `0x18001dadc`
- name: `?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `184`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001d84c`
- `0x18001d904`

## callees

- `0x180002380`
- `0x18001da24`
- `0x18001dae4`
- `0x18001db90`
- `0x180025010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001da4c`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001da4c`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(
        Concurrency::details::_Task_impl_base *this,
        struct Concurrency::details::_ContinuationTaskHandleBase *a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  _QWORD *v6; // rdx
  _QWORD v7[7]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp-20h]

  Concurrency::details::_TaskEventLogger::_LogScheduleTask(
    (Concurrency::details::_Task_impl_base *)((char *)this + 352),
    1);
  v4 = *((unsigned int *)a2 + 9);
  if ( *((_QWORD *)a2 + 2) )
  {
    v5 = 0xFFFFFFFFLL;
    if ( (_DWORD)v4 != -1 )
    {
      v5 = 16;
      *((_DWORD *)a2 + 9) = 16;
    }
    v7[0] = &std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable';
    v7[1] = a2;
    v8 = v7;
    Concurrency::details::_ScheduleFuncWithAutoInline(v7, v5);
    if ( v8 )
    {
      v6 = v7;
      LOBYTE(v6) = v8 != v7;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v6);
    }
  }
  else
  {
    Concurrency::details::_Task_impl_base::_ScheduleTask(this, a2, v4);
  }
}

```

## disassembly

```asm
0x18001da24  mov     [rsp+arg_10], rbx
0x18001da29  push    rdi
0x18001da2a  sub     rsp, 70h
0x18001da2e  mov     rax, cs:__security_cookie
0x18001da35  xor     rax, rsp
0x18001da38  mov     [rsp+78h+var_18], rax
0x18001da3d  mov     rbx, rdx
0x18001da40  mov     rdi, rcx
0x18001da43  add     rcx, 160h
0x18001da4a  mov     dl, 1
0x18001da4c  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001da52  mov     r8d, [rbx+24h]
0x18001da56  cmp     qword ptr [rbx+10h], 0
0x18001da5b  jz      short loc_18001DAB6
0x18001da5d  or      edx, 0FFFFFFFFh
0x18001da60  cmp     r8d, edx
0x18001da63  jz      short loc_18001DA6D
0x18001da65  mov     edx, 10h
0x18001da6a  mov     [rbx+24h], edx
0x18001da6d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x18001da74  mov     [rsp+78h+var_58], rax
0x18001da79  mov     [rsp+78h+var_50], rbx
0x18001da7e  lea     rax, [rsp+78h+var_58]
0x18001da83  mov     [rsp+78h+var_20], rax
0x18001da88  lea     rcx, [rsp+78h+var_58]
0x18001da8d  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18001da92  nop
0x18001da93  mov     rcx, [rsp+78h+var_20]
0x18001da98  test    rcx, rcx
0x18001da9b  jz      short loc_18001DAC1
0x18001da9d  mov     rax, [rcx]
0x18001daa0  lea     rdx, [rsp+78h+var_58]
0x18001daa5  cmp     rcx, rdx
0x18001daa8  setnz   dl
0x18001daab  mov     rax, [rax+20h]
0x18001daaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dab4  jmp     short loc_18001DAC1
0x18001dab6  mov     rdx, rbx
0x18001dab9  mov     rcx, rdi
0x18001dabc  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18001dac1  mov     rcx, [rsp+78h+var_18]
0x18001dac6  xor     rcx, rsp; StackCookie
0x18001dac9  call    __security_check_cookie
0x18001dace  mov     rbx, [rsp+78h+arg_10]
0x18001dad6  add     rsp, 70h
0x18001dada  pop     rdi
0x18001dadb  retn
```

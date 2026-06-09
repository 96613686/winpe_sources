# Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x18004eff4`
- end: `0x18004f0ac`
- name: `?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `184`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18004ee1c`
- `0x18004eed4`

## callees

- `0x1800030e0`
- `0x18004eff4`
- `0x18004f0b4`
- `0x18004f160`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18004f01c`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18004f01c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004eff4  mov     [rsp+arg_10], rbx
0x18004eff9  push    rdi
0x18004effa  sub     rsp, 70h
0x18004effe  mov     rax, cs:__security_cookie
0x18004f005  xor     rax, rsp
0x18004f008  mov     [rsp+78h+var_18], rax
0x18004f00d  mov     rbx, rdx
0x18004f010  mov     rdi, rcx
0x18004f013  add     rcx, 160h
0x18004f01a  mov     dl, 1
0x18004f01c  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18004f022  mov     r8d, [rbx+24h]
0x18004f026  cmp     qword ptr [rbx+10h], 0
0x18004f02b  jz      short loc_18004F086
0x18004f02d  or      edx, 0FFFFFFFFh
0x18004f030  cmp     r8d, edx
0x18004f033  jz      short loc_18004F03D
0x18004f035  mov     edx, 10h
0x18004f03a  mov     [rbx+24h], edx
0x18004f03d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x18004f044  mov     [rsp+78h+var_58], rax
0x18004f049  mov     [rsp+78h+var_50], rbx
0x18004f04e  lea     rax, [rsp+78h+var_58]
0x18004f053  mov     [rsp+78h+var_20], rax
0x18004f058  lea     rcx, [rsp+78h+var_58]
0x18004f05d  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18004f062  nop
0x18004f063  mov     rcx, [rsp+78h+var_20]
0x18004f068  test    rcx, rcx
0x18004f06b  jz      short loc_18004F091
0x18004f06d  mov     rax, [rcx]
0x18004f070  lea     rdx, [rsp+78h+var_58]
0x18004f075  cmp     rcx, rdx
0x18004f078  setnz   dl
0x18004f07b  mov     rax, [rax+20h]
0x18004f07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f084  jmp     short loc_18004F091
0x18004f086  mov     rdx, rbx
0x18004f089  mov     rcx, rdi
0x18004f08c  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18004f091  mov     rcx, [rsp+78h+var_18]
0x18004f096  xor     rcx, rsp; StackCookie
0x18004f099  call    __security_check_cookie
0x18004f09e  mov     rbx, [rsp+78h+arg_10]
0x18004f0a6  add     rsp, 70h
0x18004f0aa  pop     rdi
0x18004f0ab  retn
```

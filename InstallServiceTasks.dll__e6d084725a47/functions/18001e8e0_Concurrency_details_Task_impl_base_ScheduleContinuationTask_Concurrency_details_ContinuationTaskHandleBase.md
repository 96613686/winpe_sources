# Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x18001e8e0`
- end: `0x18001e998`
- name: `?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `184`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001e77c`

## callees

- `0x180003450`
- `0x18001e8e0`
- `0x18001e9a0`
- `0x18001ea4c`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001e908`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001e908`

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
0x18001e8e0  mov     [rsp+arg_10], rbx
0x18001e8e5  push    rdi
0x18001e8e6  sub     rsp, 70h
0x18001e8ea  mov     rax, cs:__security_cookie
0x18001e8f1  xor     rax, rsp
0x18001e8f4  mov     [rsp+78h+var_18], rax
0x18001e8f9  mov     rbx, rdx
0x18001e8fc  mov     rdi, rcx
0x18001e8ff  add     rcx, 160h
0x18001e906  mov     dl, 1
0x18001e908  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001e90e  mov     r8d, [rbx+24h]
0x18001e912  cmp     qword ptr [rbx+10h], 0
0x18001e917  jz      short loc_18001E972
0x18001e919  or      edx, 0FFFFFFFFh
0x18001e91c  cmp     r8d, edx
0x18001e91f  jz      short loc_18001E929
0x18001e921  mov     edx, 10h
0x18001e926  mov     [rbx+24h], edx
0x18001e929  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x18001e930  mov     [rsp+78h+var_58], rax
0x18001e935  mov     [rsp+78h+var_50], rbx
0x18001e93a  lea     rax, [rsp+78h+var_58]
0x18001e93f  mov     [rsp+78h+var_20], rax
0x18001e944  lea     rcx, [rsp+78h+var_58]
0x18001e949  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18001e94e  nop
0x18001e94f  mov     rcx, [rsp+78h+var_20]
0x18001e954  test    rcx, rcx
0x18001e957  jz      short loc_18001E97D
0x18001e959  mov     rax, [rcx]
0x18001e95c  lea     rdx, [rsp+78h+var_58]
0x18001e961  cmp     rcx, rdx
0x18001e964  setnz   dl
0x18001e967  mov     rax, [rax+20h]
0x18001e96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e970  jmp     short loc_18001E97D
0x18001e972  mov     rdx, rbx
0x18001e975  mov     rcx, rdi
0x18001e978  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18001e97d  mov     rcx, [rsp+78h+var_18]
0x18001e982  xor     rcx, rsp; StackCookie
0x18001e985  call    __security_check_cookie
0x18001e98a  mov     rbx, [rsp+78h+arg_10]
0x18001e992  add     rsp, 70h
0x18001e996  pop     rdi
0x18001e997  retn
```

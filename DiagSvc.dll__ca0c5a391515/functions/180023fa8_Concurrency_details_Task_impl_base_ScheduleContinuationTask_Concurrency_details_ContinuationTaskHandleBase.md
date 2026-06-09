# Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x180023fa8`
- end: `0x180024060`
- name: `?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `184`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180023ebc`

## callees

- `0x180003fc0`
- `0x180023fa8`
- `0x180024068`
- `0x18002411c`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180023fd0`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180023fd0`

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
0x180023fa8  mov     [rsp+arg_10], rbx
0x180023fad  push    rdi
0x180023fae  sub     rsp, 70h
0x180023fb2  mov     rax, cs:__security_cookie
0x180023fb9  xor     rax, rsp
0x180023fbc  mov     [rsp+78h+var_18], rax
0x180023fc1  mov     rbx, rdx
0x180023fc4  mov     rdi, rcx
0x180023fc7  add     rcx, 160h
0x180023fce  mov     dl, 1
0x180023fd0  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180023fd6  mov     r8d, [rbx+24h]
0x180023fda  cmp     qword ptr [rbx+10h], 0
0x180023fdf  jz      short loc_18002403A
0x180023fe1  or      edx, 0FFFFFFFFh
0x180023fe4  cmp     r8d, edx
0x180023fe7  jz      short loc_180023FF1
0x180023fe9  mov     edx, 10h
0x180023fee  mov     [rbx+24h], edx
0x180023ff1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x180023ff8  mov     [rsp+78h+var_58], rax
0x180023ffd  mov     [rsp+78h+var_50], rbx
0x180024002  lea     rax, [rsp+78h+var_58]
0x180024007  mov     [rsp+78h+var_20], rax
0x18002400c  lea     rcx, [rsp+78h+var_58]
0x180024011  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180024016  nop
0x180024017  mov     rcx, [rsp+78h+var_20]
0x18002401c  test    rcx, rcx
0x18002401f  jz      short loc_180024045
0x180024021  mov     rax, [rcx]
0x180024024  lea     rdx, [rsp+78h+var_58]
0x180024029  cmp     rcx, rdx
0x18002402c  setnz   dl
0x18002402f  mov     rax, [rax+20h]
0x180024033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024038  jmp     short loc_180024045
0x18002403a  mov     rdx, rbx
0x18002403d  mov     rcx, rdi
0x180024040  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x180024045  mov     rcx, [rsp+78h+var_18]
0x18002404a  xor     rcx, rsp; StackCookie
0x18002404d  call    __security_check_cookie
0x180024052  mov     rbx, [rsp+78h+arg_10]
0x18002405a  add     rsp, 70h
0x18002405e  pop     rdi
0x18002405f  retn
```

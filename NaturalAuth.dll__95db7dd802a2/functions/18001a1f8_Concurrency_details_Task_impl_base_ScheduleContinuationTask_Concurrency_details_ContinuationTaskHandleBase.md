# Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x18001a1f8`
- end: `0x18001a2b0`
- name: `?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `184`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001a10c`

## callees

- `0x180004170`
- `0x18001a1f8`
- `0x18001a2b8`
- `0x18001a364`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001a220`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001a220`

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
0x18001a1f8  mov     [rsp+arg_10], rbx
0x18001a1fd  push    rdi
0x18001a1fe  sub     rsp, 70h
0x18001a202  mov     rax, cs:__security_cookie
0x18001a209  xor     rax, rsp
0x18001a20c  mov     [rsp+78h+var_18], rax
0x18001a211  mov     rbx, rdx
0x18001a214  mov     rdi, rcx
0x18001a217  add     rcx, 160h
0x18001a21e  mov     dl, 1
0x18001a220  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001a226  mov     r8d, [rbx+24h]
0x18001a22a  cmp     qword ptr [rbx+10h], 0
0x18001a22f  jz      short loc_18001A28A
0x18001a231  or      edx, 0FFFFFFFFh
0x18001a234  cmp     r8d, edx
0x18001a237  jz      short loc_18001A241
0x18001a239  mov     edx, 10h
0x18001a23e  mov     [rbx+24h], edx
0x18001a241  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x18001a248  mov     [rsp+78h+var_58], rax
0x18001a24d  mov     [rsp+78h+var_50], rbx
0x18001a252  lea     rax, [rsp+78h+var_58]
0x18001a257  mov     [rsp+78h+var_20], rax
0x18001a25c  lea     rcx, [rsp+78h+var_58]
0x18001a261  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18001a266  nop
0x18001a267  mov     rcx, [rsp+78h+var_20]
0x18001a26c  test    rcx, rcx
0x18001a26f  jz      short loc_18001A295
0x18001a271  mov     rax, [rcx]
0x18001a274  lea     rdx, [rsp+78h+var_58]
0x18001a279  cmp     rcx, rdx
0x18001a27c  setnz   dl
0x18001a27f  mov     rax, [rax+20h]
0x18001a283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a288  jmp     short loc_18001A295
0x18001a28a  mov     rdx, rbx
0x18001a28d  mov     rcx, rdi
0x18001a290  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18001a295  mov     rcx, [rsp+78h+var_18]
0x18001a29a  xor     rcx, rsp; StackCookie
0x18001a29d  call    __security_check_cookie
0x18001a2a2  mov     rbx, [rsp+78h+arg_10]
0x18001a2aa  add     rsp, 70h
0x18001a2ae  pop     rdi
0x18001a2af  retn
```

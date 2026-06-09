# Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x180011384`
- end: `0x18001143c`
- name: `?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `184`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180010964`
- `0x180021800`

## callees

- `0x180011384`
- `0x180011444`
- `0x1800243e0`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800113ac`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800113ac`

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
0x180011384  mov     [rsp+arg_10], rbx
0x180011389  push    rdi
0x18001138a  sub     rsp, 70h
0x18001138e  mov     rax, cs:__security_cookie
0x180011395  xor     rax, rsp
0x180011398  mov     [rsp+78h+var_18], rax
0x18001139d  mov     rbx, rdx
0x1800113a0  mov     rdi, rcx
0x1800113a3  add     rcx, 160h
0x1800113aa  mov     dl, 1
0x1800113ac  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x1800113b2  mov     r8d, [rbx+24h]
0x1800113b6  cmp     qword ptr [rbx+10h], 0
0x1800113bb  jz      short loc_180011416
0x1800113bd  or      edx, 0FFFFFFFFh
0x1800113c0  cmp     r8d, edx
0x1800113c3  jz      short loc_1800113CD
0x1800113c5  mov     edx, 10h
0x1800113ca  mov     [rbx+24h], edx
0x1800113cd  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x1800113d4  mov     [rsp+78h+var_58], rax
0x1800113d9  mov     [rsp+78h+var_50], rbx
0x1800113de  lea     rax, [rsp+78h+var_58]
0x1800113e3  mov     [rsp+78h+var_20], rax
0x1800113e8  lea     rcx, [rsp+78h+var_58]
0x1800113ed  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x1800113f2  nop
0x1800113f3  mov     rcx, [rsp+78h+var_20]
0x1800113f8  test    rcx, rcx
0x1800113fb  jz      short loc_180011421
0x1800113fd  mov     rax, [rcx]
0x180011400  lea     rdx, [rsp+78h+var_58]
0x180011405  cmp     rcx, rdx
0x180011408  setnz   dl
0x18001140b  mov     rax, [rax+20h]
0x18001140f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011414  jmp     short loc_180011421
0x180011416  mov     rdx, rbx
0x180011419  mov     rcx, rdi
0x18001141c  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x180011421  mov     rcx, [rsp+78h+var_18]
0x180011426  xor     rcx, rsp; StackCookie
0x180011429  call    __security_check_cookie
0x18001142e  mov     rbx, [rsp+78h+arg_10]
0x180011436  add     rsp, 70h
0x18001143a  pop     rdi
0x18001143b  retn
```

# `Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)'::`5'::_lambda_1_::operator()(void)

- ea: `0x180016e5c`
- end: `0x18001700b`
- name: `??R_lambda_1_@?4??_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@34@@Z@QEBA@XZ`
- size: `431`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800191e0`

## callees

- `0x180016e5c`
- `0x180018df0`
- `0x180019e40`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180016ec9`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180016ec9`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180016ea9`
- `msvcp_win!?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x180016ea9`
- `msvcp_win!?_CallInContext@_ContextCallback@details@Concurrency@@QEBAXV?$function@$$A6AXXZ@std@@_N@Z` at `0x180016f8d`
- `msvcp_win!?_CallInContext@_ContextCallback@details@Concurrency@@QEBAXV?$function@$$A6AXXZ@std@@_N@Z` at `0x180016f8d`

## pseudocode

```c
void __fastcall `Concurrency::details::_Task_impl_base::_ScheduleContinuationTask'::`5'::_lambda_1_::operator()(
        _QWORD *a1)
{
  bool v2; // bl
  __int64 v3; // rbx
  volatile signed __int32 *v4; // rcx
  _QWORD *v5; // rdx
  volatile signed __int32 *v6; // rbx
  Concurrency::details::_Task_impl_base *v7; // rbx
  Concurrency::details::_Task_impl_base *v8; // [rsp+20h] [rbp-B8h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-B0h]
  _BYTE v10[24]; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v11[7]; // [rsp+48h] [rbp-90h] BYREF
  _QWORD *v12; // [rsp+80h] [rbp-58h]
  _BYTE v13[56]; // [rsp+88h] [rbp-50h] BYREF
  __int64 v14; // [rsp+C0h] [rbp-18h]
  _BYTE *v15; // [rsp+E8h] [rbp+10h] BYREF

  (*(void (__fastcall **)(_QWORD, Concurrency::details::_Task_impl_base **))(*(_QWORD *)*a1 + 16LL))(*a1, &v8);
  v15 = 0;
  Concurrency::details::_ContextCallback::_Capture((Concurrency::details::_ContextCallback *)&v15);
  v2 = v15 == *(_BYTE **)(*a1 + 16LL);
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)&v15);
  if ( v2 )
  {
    Concurrency::details::_Task_impl_base::_ScheduleTask(v8, *a1, 0xFFFFFFFFLL);
  }
  else
  {
    v3 = *a1;
    *(_QWORD *)v10 = *a1;
    v4 = v9;
    if ( v9 )
    {
      _InterlockedIncrement(v9 + 2);
      v4 = v9;
    }
    try
    {
      v11[0] = std::X$$V::XZ::QEBA::Z::_Func_impl_no_alloc<``Concurrency::details::_Task_impl_base::_ScheduleContinuationTask'::`5'::_lambda_1_::operator()'::`8'::_lambda_1_,Concurrency::details::AXPEAU_ContinuationTaskHandleBase * const>::`vftable';
      v11[1] = v3;
      v11[2] = v8;
      v11[3] = v4;
      *(_OWORD *)&v10[8] = 0;
      v12 = v11;
      v15 = v13;
      v14 = 0;
      v14 = std::X$$V::XZ::QEBA::Z::_Func_impl_no_alloc<``Concurrency::details::_Task_impl_base::_ScheduleContinuationTask'::`5'::_lambda_1_::operator()'::`8'::_lambda_1_,Concurrency::details::AXPEAU_ContinuationTaskHandleBase * const>::_Copy(
              v11,
              v13);
      Concurrency::details::_ContextCallback::_CallInContext(v3 + 16, v13, 0);
      if ( v12 )
      {
        v5 = v11;
        LOBYTE(v5) = v12 != v11;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v12 + 32LL))(v12, v5);
      }
    }
    catch ( ... )
    {
      v7 = v8;
      *(_OWORD *)v10 = 0;
      __ExceptionPtrCreate(v10);
      __ExceptionPtrCurrentException(v10);
      Concurrency::details::_Task_impl_base::_CancelWithException(v7, (const struct std::exception_ptr *)v10);
      __ExceptionPtrDestroy(v10);
    }
  }
  v6 = v9;
  if ( v9 && _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
    if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  }
}

```

## disassembly

```asm
0x180016e5c  mov     rax, rsp
0x180016e5f  mov     [rax+18h], rbx
0x180016e63  push    rdi
0x180016e64  sub     rsp, 0D0h
0x180016e6b  mov     rdi, rcx
0x180016e6e  mov     dword ptr [rax+8], 0
0x180016e75  mov     rcx, [rcx]
0x180016e78  mov     rax, [rcx]
0x180016e7b  lea     rdx, [rsp+0D8h+var_B8]
0x180016e80  mov     rax, [rax+10h]
0x180016e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e89  nop
0x180016e8a  mov     [rsp+0D8h+arg_8], 0
0x180016e96  mov     dword ptr [rsp+0D8h+arg_0], 1
0x180016ea1  lea     rcx, [rsp+0D8h+arg_8]
0x180016ea9  call    cs:__imp_?_Capture@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Capture(void)
0x180016eaf  mov     rax, [rdi]
0x180016eb2  mov     rcx, [rax+10h]
0x180016eb6  cmp     [rsp+0D8h+arg_8], rcx
0x180016ebe  setz    bl
0x180016ec1  lea     rcx, [rsp+0D8h+arg_8]
0x180016ec9  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x180016ecf  nop
0x180016ed0  test    bl, bl
0x180016ed2  jz      short loc_180016EEA
0x180016ed4  or      r8d, 0FFFFFFFFh
0x180016ed8  mov     rdx, [rdi]
0x180016edb  mov     rcx, [rsp+0D8h+var_B8]
0x180016ee0  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x180016ee5  jmp     loc_180016FB9
0x180016eea  mov     rbx, [rdi]
0x180016eed  mov     [rsp+0D8h+var_A8], rbx
0x180016ef2  mov     rcx, [rsp+0D8h+var_B0]
0x180016ef7  test    rcx, rcx
0x180016efa  jz      short loc_180016F05
0x180016efc  lock inc dword ptr [rcx+8]
0x180016f00  mov     rcx, [rsp+0D8h+var_B0]
0x180016f05  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?7???R1?4??_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@45@@Z@QEBA@XZ@X$$V@std@@6B@; const std::_Func_impl_no_alloc<``Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)'::`5'::_lambda_1_::operator()(void)'::`8'::_lambda_1_,void,>::`vftable'
0x180016f0c  mov     [rsp+0D8h+var_90], rax
0x180016f11  mov     [rsp+0D8h+var_88], rbx
0x180016f16  mov     rax, [rsp+0D8h+var_B8]
0x180016f1b  mov     [rsp+0D8h+var_80], rax
0x180016f20  mov     [rsp+0D8h+var_78], rcx
0x180016f25  xorps   xmm0, xmm0
0x180016f28  movdqu  [rsp+0D8h+var_A0], xmm0
0x180016f2e  lea     rax, [rsp+0D8h+var_90]
0x180016f33  mov     [rsp+0D8h+var_58], rax
0x180016f3b  lea     rax, [rsp+0D8h+var_90]
0x180016f40  mov     [rsp+0D8h+arg_0], rax
0x180016f48  lea     rax, [rsp+0D8h+var_50]
0x180016f50  mov     [rsp+0D8h+arg_8], rax
0x180016f58  mov     [rsp+0D8h+var_18], 0
0x180016f64  lea     rdx, [rsp+0D8h+var_50]
0x180016f6c  lea     rcx, [rsp+0D8h+var_90]
0x180016f71  call    ?_Copy@?$_Func_impl_no_alloc@V_lambda_1_@?7???R1?4??_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@45@@Z@QEBA@XZ@X$$V@std@@EEBAPEAV?$_Func_base@X$$V@2@PEAX@Z; std::_Func_impl_no_alloc<``Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)'::`5'::_lambda_1_::operator()(void)'::`8'::_lambda_1_,void,>::_Copy(void *)
0x180016f76  mov     [rsp+0D8h+var_18], rax
0x180016f7e  lea     rcx, [rbx+10h]
0x180016f82  xor     r8d, r8d
0x180016f85  lea     rdx, [rsp+0D8h+var_50]
0x180016f8d  call    cs:__imp_?_CallInContext@_ContextCallback@details@Concurrency@@QEBAXV?$function@$$A6AXXZ@std@@_N@Z; Concurrency::details::_ContextCallback::_CallInContext(std::function<void (void)>,bool)
0x180016f93  nop
0x180016f94  mov     rcx, [rsp+0D8h+var_58]
0x180016f9c  test    rcx, rcx
0x180016f9f  jz      short loc_180016FB9
0x180016fa1  mov     rax, [rcx]
0x180016fa4  lea     rdx, [rsp+0D8h+var_90]
0x180016fa9  cmp     rcx, rdx
0x180016fac  setnz   dl
0x180016faf  mov     rax, [rax+20h]
0x180016fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fb8  nop
0x180016fb9  mov     rbx, [rsp+0D8h+var_B0]
0x180016fbe  test    rbx, rbx
0x180016fc1  jz      short loc_180016FFA
0x180016fc3  or      eax, 0FFFFFFFFh
0x180016fc6  lock xadd [rbx+8], eax
0x180016fcb  cmp     eax, 1
0x180016fce  jnz     short loc_180016FFA
0x180016fd0  mov     rax, [rbx]
0x180016fd3  mov     rcx, rbx
0x180016fd6  mov     rax, [rax]
0x180016fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fde  or      eax, 0FFFFFFFFh
0x180016fe1  lock xadd [rbx+0Ch], eax
0x180016fe6  cmp     eax, 1
0x180016fe9  jnz     short loc_180016FFA
0x180016feb  mov     rax, [rbx]
0x180016fee  mov     rcx, rbx
0x180016ff1  mov     rax, [rax+8]
0x180016ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ffa  mov     rbx, [rsp+0D8h+arg_10]
0x180017002  add     rsp, 0D0h
0x180017009  pop     rdi
0x18001700a  retn
```

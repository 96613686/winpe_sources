# Concurrency::details::_PPLTaskHandle_wpc::MicrosoftAccount::UserTicketResult_Concurrency::task_wpc::MicrosoftAccount::UserTicketResult_::_InitialTaskHandle_wpc::MicrosoftAccount::UserTicketResult__lambda_76df95f8bc94559cee4cf8aea0755487__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180031db0`
- end: `0x180031f3d`
- name: `Concurrency::details::_PPLTaskHandle_wpc::MicrosoftAccount::UserTicketResult_Concurrency::task_wpc::MicrosoftAccount::UserTicketResult_::_InitialTaskHandle_wpc::MicrosoftAccount::UserTicketResult__lambda_76df95f8bc94559cee4cf8aea0755487__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18002f6c0`
- `0x18002f758`
- `0x180031a4c`
- `0x180031db0`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180031e1b`
- `msvcp_win!_Mtx_unlock` at `0x180031e4d`
- `msvcp_win!_Mtx_unlock` at `0x180031e1b`
- `msvcp_win!_Mtx_unlock` at `0x180031e4d`
- `msvcp_win!_Mtx_lock` at `0x180031dd6`
- `msvcp_win!_Mtx_lock` at `0x180031dd6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031de5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031e01`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031de5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031e01`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031f21`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031f21`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Concurrency::details::_PPLTaskHandle_wpc::MicrosoftAccount::UserTicketResult_Concurrency::task_wpc::MicrosoftAccount::UserTicketResult_::_InitialTaskHandle_wpc::MicrosoftAccount::UserTicketResult__lambda_76df95f8bc94559cee4cf8aea0755487__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rbx
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  Concurrency::details::_Task_impl_base *v6; // rdi
  _BYTE *v7; // rcx
  _BYTE *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  Concurrency::details::_Task_impl_base *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int128 v14; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v15[56]; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE *v16; // [rsp+78h] [rbp-B0h]
  _BYTE v17[56]; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+B8h] [rbp-70h]
  char v19[104]; // [rsp+C0h] [rbp-68h] BYREF
  Concurrency::details::_Task_impl_base **v21; // [rsp+138h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  if ( _Mtx_lock((_Mtx_t)(v3 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v3 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v3 + 108) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v21 = v2;
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    v5 = (__int64)*v2 + 16;
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(
      *v2,
      v5,
      0,
      0,
      (__int64)*v2 + 16);
    return;
  }
  *(_DWORD *)(v3 + 8) = 1;
  _Mtx_unlock(v4);
  try
  {
    v6 = *v2;
    v7 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_76df95f8bc94559cee4cf8aea0755487__wpc::MicrosoftAccount::UserTicketResult___lambda_76df95f8bc94559cee4cf8aea0755487__const___(a1 + 24);
    v16 = v7;
    v18 = 0;
    if ( !v7 )
      goto LABEL_14;
    if ( v7 == v15 )
    {
      v18 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v7 + 8LL))(v7, v17);
      if ( !v16 )
      {
LABEL_14:
        Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync_::_LogWorkItemAndInvokeUserLambda_std::function_HttpRequest::HttpResponse___cdecl_void____(
          a1,
          (__int64)v19,
          (__int64)v17);
        Concurrency::details::_Task_impl<wpc::MicrosoftAccount::UserTicketResult>::_FinalizeAndRunContinuations(v6);
        goto LABEL_22;
      }
      v8 = v15;
      LOBYTE(v8) = v16 != v15;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v16 + 32LL))(v16, v8);
    }
    else
    {
      v18 = (__int64)v7;
    }
    v16 = 0;
    goto LABEL_14;
  }
  catch ( Concurrency::task_canceled )
  {
    v9 = *(_QWORD *)(a1 + 8);
    v10 = v9 + 16;
    LOBYTE(v10) = 1;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 8LL))(v9, v10, 0, 0, v9 + 16);
    v2 = v21;
  }
  catch ( Concurrency::details::_Interruption_exception )
  {
    v12 = *(_QWORD *)(a1 + 8);
    v13 = v12 + 16;
    LOBYTE(v13) = 1;
    guard_dispatch_icall_thunk_10345483385596137414(v12, v13, 0, 0, v12 + 16);
    v2 = v21;
  }
  catch ( ... )
  {
    v11 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
    v14 = 0;
    __ExceptionPtrCreate(&v14);
    __ExceptionPtrCurrentException(&v14);
    Concurrency::details::_Task_impl_base::_CancelWithException(v11, (const struct std::exception_ptr *)&v14);
    __ExceptionPtrDestroy(&v14);
    v2 = v21;
  }
LABEL_22:
  Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
}

```

## disassembly

```asm
0x180031db0  mov     [rsp+arg_18], rbx
0x180031db5  mov     [rsp+arg_0], rcx
0x180031dba  push    rsi
0x180031dbb  push    rdi
0x180031dbc  push    r14
0x180031dbe  sub     rsp, 110h
0x180031dc5  mov     r14, rcx
0x180031dc8  lea     rbx, [rcx+8]
0x180031dcc  mov     rsi, [rbx]
0x180031dcf  lea     rdi, [rsi+20h]
0x180031dd3  mov     rcx, rdi; _Mtx_t
0x180031dd6  call    cs:__imp__Mtx_lock
0x180031ddc  test    eax, eax
0x180031dde  jz      short loc_180031DEC
0x180031de0  mov     ecx, 5
0x180031de5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180031deb  int     3; Trap to Debugger
0x180031dec  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180031df3  jnz     short loc_180031E08
0x180031df5  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180031dfc  mov     ecx, 6
0x180031e01  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180031e07  int     3; Trap to Debugger
0x180031e08  mov     [rsp+128h+arg_8], rbx
0x180031e10  mov     eax, [rsi+8]
0x180031e13  mov     rcx, rdi; _Mtx_t
0x180031e16  cmp     eax, 2
0x180031e19  jnz     short loc_180031E46
0x180031e1b  call    cs:__imp__Mtx_unlock
0x180031e21  mov     rcx, [rbx]
0x180031e24  mov     rax, [rcx]
0x180031e27  lea     rdx, [rcx+10h]
0x180031e2b  mov     [rsp+128h+var_108], rdx
0x180031e30  xor     r9d, r9d
0x180031e33  xor     r8d, r8d
0x180031e36  mov     dl, 1
0x180031e38  mov     rax, [rax+8]
0x180031e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e41  jmp     loc_180031F27
0x180031e46  mov     dword ptr [rsi+8], 1
0x180031e4d  call    cs:__imp__Mtx_unlock
0x180031e53  nop
0x180031e54  mov     rdi, [rbx]
0x180031e57  lea     rax, [rsp+128h+var_E8]
0x180031e5c  mov     [rsp+128h+arg_10], rax
0x180031e64  mov     [rsp+128h+var_B0], 0
0x180031e6d  lea     rcx, [r14+18h]
0x180031e71  call    std___Global_new_std___Func_impl_no_alloc__lambda_76df95f8bc94559cee4cf8aea0755487__wpc__MicrosoftAccount__UserTicketResult___lambda_76df95f8bc94559cee4cf8aea0755487__const___
0x180031e76  mov     rcx, rax
0x180031e79  mov     [rsp+128h+var_B0], rax
0x180031e7e  mov     [rsp+128h+var_70], 0
0x180031e8a  test    rax, rax
0x180031e8d  jz      short loc_180031EE9
0x180031e8f  lea     rax, [rsp+128h+var_E8]
0x180031e94  cmp     rcx, rax
0x180031e97  jnz     short loc_180031ED8
0x180031e99  mov     rax, [rcx]
0x180031e9c  lea     rdx, [rsp+128h+var_A8]
0x180031ea4  mov     rax, [rax+8]
0x180031ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ead  mov     [rsp+128h+var_70], rax
0x180031eb5  mov     rcx, [rsp+128h+var_B0]
0x180031eba  test    rcx, rcx
0x180031ebd  jz      short loc_180031EE9
0x180031ebf  mov     rax, [rcx]
0x180031ec2  lea     rdx, [rsp+128h+var_E8]
0x180031ec7  cmp     rcx, rdx
0x180031eca  setnz   dl
0x180031ecd  mov     rax, [rax+20h]
0x180031ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ed6  jmp     short loc_180031EE0
0x180031ed8  mov     [rsp+128h+var_70], rcx
0x180031ee0  mov     [rsp+128h+var_B0], 0
0x180031ee9  lea     r8, [rsp+128h+var_A8]
0x180031ef1  lea     rdx, [rsp+128h+var_68]
0x180031ef9  mov     rcx, r14
0x180031efc  call    Concurrency__task_HttpRequest__HttpResponse____InitialTaskHandle_HttpRequest__HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency__details___TypeSelectorNoAsync____LogWorkItemAndInvokeUserLambda_std__function_HttpRequest__HttpResponse___cdecl_void____
0x180031f01  mov     rdx, rax
0x180031f04  mov     rcx, rdi; this
0x180031f07  call    ?_FinalizeAndRunContinuations@?$_Task_impl@UUserTicketResult@MicrosoftAccount@wpc@@@details@Concurrency@@QEAAXUUserTicketResult@MicrosoftAccount@wpc@@@Z; Concurrency::details::_Task_impl<wpc::MicrosoftAccount::UserTicketResult>::_FinalizeAndRunContinuations(wpc::MicrosoftAccount::UserTicketResult)
0x180031f0c  nop
0x180031f0d  jmp     short loc_180031F17
0x180031f0f  mov     rbx, [rsp+128h+arg_8]
0x180031f17  mov     rcx, [rbx]
0x180031f1a  add     rcx, 160h
0x180031f21  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180031f27  mov     rbx, [rsp+128h+arg_18]
0x180031f2f  add     rsp, 110h
0x180031f36  pop     r14
0x180031f38  pop     rdi
0x180031f39  pop     rsi
0x180031f3a  retn
0x180031f3b  jmp     short loc_180031F0F
```

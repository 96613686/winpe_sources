# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180048e00`
- end: `0x180048e8c`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180047790`
- `0x18004821c`
- `0x180048e00`
- `0x180048ea0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180048e34`
- `msvcp_win!_Mtx_unlock` at `0x180048e53`
- `msvcp_win!_Mtx_unlock` at `0x180048e34`
- `msvcp_win!_Mtx_unlock` at `0x180048e53`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180048e78`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180048e78`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // r14
  struct _Mtx_internal_imp_t *v4; // rcx
  Concurrency::details::_Task_impl_base *v5; // rbx
  const struct std::exception_ptr *v6; // rax
  _BYTE v7[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  std::_Mutex_base::lock((std::_Mutex_base *)(v3 + 32));
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    Concurrency::details::_Task_impl_base::_Cancel(*v2, 1);
  }
  else
  {
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    try
    {
      Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), 1);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), 1);
    }
    catch ( ... )
    {
      v5 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v6 = (const struct std::exception_ptr *)std::current_exception(v7);
      Concurrency::details::_Task_impl_base::_CancelWithException(v5, v6);
      __ExceptionPtrDestroy(v7);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
  }
}

```

## disassembly

```asm
0x180048e00  mov     [rsp+arg_10], rbx
0x180048e05  mov     [rsp+arg_0], rcx
0x180048e0a  push    rsi
0x180048e0b  push    rdi
0x180048e0c  push    r14
0x180048e0e  sub     rsp, 30h
0x180048e12  mov     rbx, rcx
0x180048e15  lea     rdi, [rcx+8]
0x180048e19  mov     r14, [rdi]
0x180048e1c  lea     rsi, [r14+20h]
0x180048e20  mov     rcx, rsi; this
0x180048e23  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180048e28  mov     eax, [r14+8]
0x180048e2c  mov     rcx, rsi; _Mtx_t
0x180048e2f  cmp     eax, 2
0x180048e32  jnz     short loc_180048E46
0x180048e34  call    cs:__imp__Mtx_unlock
0x180048e3a  mov     dl, 1; bool
0x180048e3c  mov     rcx, [rdi]; this
0x180048e3f  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180048e44  jmp     short loc_180048E7E
0x180048e46  mov     [rsp+48h+arg_8], rdi
0x180048e4b  mov     dword ptr [r14+8], 1
0x180048e53  call    cs:__imp__Mtx_unlock
0x180048e59  nop
0x180048e5a  mov     rcx, rbx
0x180048e5d  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency__details___TypeSelectorNoAsync____Init
0x180048e62  nop
0x180048e63  jmp     short loc_180048E69
0x180048e65  jmp     short loc_180048E69
0x180048e67  jmp     short $+2
0x180048e69  mov     rax, [rsp+48h+arg_8]
0x180048e6e  mov     rcx, [rax]
0x180048e71  add     rcx, 160h
0x180048e78  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180048e7e  mov     rbx, [rsp+48h+arg_10]
0x180048e83  add     rsp, 30h
0x180048e87  pop     r14
0x180048e89  pop     rdi
0x180048e8a  pop     rsi
0x180048e8b  retn
```

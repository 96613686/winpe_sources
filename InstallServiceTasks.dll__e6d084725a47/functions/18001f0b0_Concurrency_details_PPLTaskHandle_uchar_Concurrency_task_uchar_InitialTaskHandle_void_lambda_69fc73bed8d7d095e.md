# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18001f0b0`
- end: `0x18001f13c`
- name: `?invoke@?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEBAXXZ`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001d6f0`
- `0x18001e1c4`
- `0x18001f0b0`
- `0x18001f150`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001f128`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001f128`
- `msvcp_win!_Mtx_unlock` at `0x18001f0e4`
- `msvcp_win!_Mtx_unlock` at `0x18001f103`
- `msvcp_win!_Mtx_unlock` at `0x18001f0e4`
- `msvcp_win!_Mtx_unlock` at `0x18001f103`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
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
      Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
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
0x18001f0b0  mov     [rsp+arg_10], rbx
0x18001f0b5  mov     [rsp+arg_0], rcx
0x18001f0ba  push    rsi
0x18001f0bb  push    rdi
0x18001f0bc  push    r14
0x18001f0be  sub     rsp, 30h
0x18001f0c2  mov     rbx, rcx
0x18001f0c5  lea     rdi, [rcx+8]
0x18001f0c9  mov     r14, [rdi]
0x18001f0cc  lea     rsi, [r14+20h]
0x18001f0d0  mov     rcx, rsi; this
0x18001f0d3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001f0d8  mov     eax, [r14+8]
0x18001f0dc  mov     rcx, rsi; _Mtx_t
0x18001f0df  cmp     eax, 2
0x18001f0e2  jnz     short loc_18001F0F6
0x18001f0e4  call    cs:__imp__Mtx_unlock
0x18001f0ea  mov     dl, 1; bool
0x18001f0ec  mov     rcx, [rdi]; this
0x18001f0ef  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001f0f4  jmp     short loc_18001F12E
0x18001f0f6  mov     [rsp+48h+arg_8], rdi
0x18001f0fb  mov     dword ptr [r14+8], 1
0x18001f103  call    cs:__imp__Mtx_unlock
0x18001f109  nop
0x18001f10a  mov     rcx, rbx
0x18001f10d  call    ?_Init@?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18001f112  nop
0x18001f113  jmp     short loc_18001F119
0x18001f115  jmp     short loc_18001F119
0x18001f117  jmp     short $+2
0x18001f119  mov     rax, [rsp+48h+arg_8]
0x18001f11e  mov     rcx, [rax]
0x18001f121  add     rcx, 160h
0x18001f128  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001f12e  mov     rbx, [rsp+48h+arg_10]
0x18001f133  add     rsp, 30h
0x18001f137  pop     r14
0x18001f139  pop     rdi
0x18001f13a  pop     rsi
0x18001f13b  retn
```

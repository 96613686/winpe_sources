# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x1800246e0`
- end: `0x180024742`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022910`
- `0x1800235fc`
- `0x1800243a4`
- `0x1800246e0`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180024731`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180024731`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // rdx
  Concurrency::details::_Task_impl_base *v4; // rbx
  const struct std::exception_ptr *v5; // rax
  _BYTE *v6; // rdx
  _BYTE *v7; // rdx
  _BYTE v8[32]; // [rsp+0h] [rbp-38h] BYREF
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v11 = a1 + 8;
  if ( Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      v6 = v8;
      LOBYTE(v6) = 1;
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), (__int64)v6);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v7 = v8;
      LOBYTE(v7) = 1;
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), (__int64)v7);
    }
    catch ( ... )
    {
      v4 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v5 = (const struct std::exception_ptr *)std::current_exception(v9);
      Concurrency::details::_Task_impl_base::_CancelWithException(v4, v5);
      __ExceptionPtrDestroy(v9);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v11 + 352LL));
  }
  else
  {
    LOBYTE(v3) = 1;
    Concurrency::details::_Task_impl_base::_Cancel(*v2, v3);
  }
}

```

## disassembly

```asm
0x1800246e0  mov     [rsp+arg_10], rbx
0x1800246e5  mov     [rsp+arg_0], rcx
0x1800246ea  push    rdi
0x1800246eb  sub     rsp, 30h
0x1800246ef  mov     rbx, rcx
0x1800246f2  lea     rdi, [rcx+8]
0x1800246f6  mov     [rsp+38h+arg_8], rdi
0x1800246fb  mov     rcx, [rdi]
0x1800246fe  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x180024703  test    al, al
0x180024705  jnz     short loc_180024713
0x180024707  mov     dl, 1; bool
0x180024709  mov     rcx, [rdi]; this
0x18002470c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x180024711  jmp     short loc_180024737
0x180024713  mov     rcx, rbx
0x180024716  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_41663189713a77324ef99cfbd1e71423__Concurrency__details___TypeSelectorNoAsync____Init
0x18002471b  nop
0x18002471c  jmp     short loc_180024722
0x18002471e  jmp     short loc_180024722
0x180024720  jmp     short $+2
0x180024722  mov     rax, [rsp+38h+arg_8]
0x180024727  mov     rcx, [rax]
0x18002472a  add     rcx, 160h
0x180024731  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180024737  mov     rbx, [rsp+38h+arg_10]
0x18002473c  add     rsp, 30h
0x180024740  pop     rdi
0x180024741  retn
```

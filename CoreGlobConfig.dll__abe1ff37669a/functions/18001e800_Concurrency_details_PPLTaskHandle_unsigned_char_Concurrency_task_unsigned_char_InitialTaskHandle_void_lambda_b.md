# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x18001e800`
- end: `0x18001e862`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c110`
- `0x18001d26c`
- `0x18001dec4`
- `0x18001e800`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e851`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e851`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // rdx
  Concurrency::details::_Task_impl_base *v4; // rbx
  const struct std::exception_ptr *v5; // rax
  _BYTE *v6; // rdx
  _BYTE *v7; // rdx
  _BYTE v8[32]; // [rsp+0h] [rbp-38h] BYREF
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v11 = a1 + 8;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 8)) )
  {
    try
    {
      Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
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
0x18001e800  mov     [rsp+arg_10], rbx
0x18001e805  mov     [rsp+arg_0], rcx
0x18001e80a  push    rdi
0x18001e80b  sub     rsp, 30h
0x18001e80f  mov     rbx, rcx
0x18001e812  lea     rdi, [rcx+8]
0x18001e816  mov     [rsp+38h+arg_8], rdi
0x18001e81b  mov     rcx, [rdi]
0x18001e81e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18001e823  test    al, al
0x18001e825  jnz     short loc_18001E833
0x18001e827  mov     dl, 1; bool
0x18001e829  mov     rcx, [rdi]; this
0x18001e82c  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001e831  jmp     short loc_18001E857
0x18001e833  mov     rcx, rbx
0x18001e836  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_bf111cb5ee0d3807f0e3fd5a5389097f__Concurrency__details___TypeSelectorNoAsync____Init
0x18001e83b  nop
0x18001e83c  jmp     short loc_18001E842
0x18001e83e  jmp     short loc_18001E842
0x18001e840  jmp     short $+2
0x18001e842  mov     rax, [rsp+38h+arg_8]
0x18001e847  mov     rcx, [rax]
0x18001e84a  add     rcx, 160h
0x18001e851  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001e857  mov     rbx, [rsp+38h+arg_10]
0x18001e85c  add     rsp, 30h
0x18001e860  pop     rdi
0x18001e861  retn
```

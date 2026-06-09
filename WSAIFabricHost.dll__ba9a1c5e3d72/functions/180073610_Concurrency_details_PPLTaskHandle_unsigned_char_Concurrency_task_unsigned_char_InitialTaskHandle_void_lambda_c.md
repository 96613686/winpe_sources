# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180073610`
- end: `0x1800736db`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18007222c`
- `0x180073610`
- `0x180089010`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800736c3`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800736c3`
- `msvcp_win!_Mtx_unlock` at `0x180073670`
- `msvcp_win!_Mtx_unlock` at `0x1800736a4`
- `msvcp_win!_Mtx_unlock` at `0x180073670`
- `msvcp_win!_Mtx_unlock` at `0x1800736a4`
- `msvcp_win!_Mtx_lock` at `0x180073633`
- `msvcp_win!_Mtx_lock` at `0x180073633`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180073642`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007365e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180073642`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007365e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
        __int64 a1)
{
  _QWORD *v2; // r14
  __int64 v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  Concurrency::details::_Task_impl_base *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rdx
  _OWORD v11[2]; // [rsp+30h] [rbp-28h] BYREF

  v2 = (_QWORD *)(a1 + 8);
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
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    v5 = *v2 + 16LL;
    LOBYTE(v5) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v2 + 8LL))(*v2, v5, 0, 0, *v2 + 16LL);
  }
  else
  {
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    try
    {
      Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      v6 = *(_QWORD *)(a1 + 8);
      v7 = v6 + 16;
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 8LL))(v6, v7, 0, 0, v6 + 16);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      v9 = *(_QWORD *)(a1 + 8);
      v10 = v9 + 16;
      LOBYTE(v10) = 1;
      guard_dispatch_icall_thunk_10345483385596137414(v9, v10, 0, 0, v9 + 16);
    }
    catch ( ... )
    {
      v8 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v11[0] = 0;
      __ExceptionPtrCreate(v11);
      __ExceptionPtrCurrentException(v11);
      Concurrency::details::_Task_impl_base::_CancelWithException(v8, (const struct std::exception_ptr *)v11);
      __ExceptionPtrDestroy(v11);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*v2 + 352LL));
  }
}

```

## disassembly

```asm
0x180073610  mov     [rsp+arg_10], rbx
0x180073615  mov     [rsp+arg_0], rcx
0x18007361a  push    rsi
0x18007361b  push    rdi
0x18007361c  push    r14
0x18007361e  sub     rsp, 40h
0x180073622  mov     rdi, rcx
0x180073625  lea     r14, [rcx+8]
0x180073629  mov     rsi, [r14]
0x18007362c  lea     rbx, [rsi+20h]
0x180073630  mov     rcx, rbx; _Mtx_t
0x180073633  call    cs:__imp__Mtx_lock
0x180073639  test    eax, eax
0x18007363b  jz      short loc_180073649
0x18007363d  mov     ecx, 5
0x180073642  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180073648  int     3; Trap to Debugger
0x180073649  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180073650  jnz     short loc_180073665
0x180073652  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180073659  mov     ecx, 6
0x18007365e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180073664  int     3; Trap to Debugger
0x180073665  mov     eax, [rsi+8]
0x180073668  mov     rcx, rbx; _Mtx_t
0x18007366b  cmp     eax, 2
0x18007366e  jnz     short loc_180073698
0x180073670  call    cs:__imp__Mtx_unlock
0x180073676  mov     rcx, [r14]
0x180073679  mov     rax, [rcx]
0x18007367c  lea     rdx, [rcx+10h]
0x180073680  mov     [rsp+58h+var_38], rdx
0x180073685  xor     r9d, r9d
0x180073688  xor     r8d, r8d
0x18007368b  mov     dl, 1
0x18007368d  mov     rax, [rax+8]
0x180073691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073696  jmp     short loc_1800736C9
0x180073698  mov     [rsp+58h+arg_8], r14
0x18007369d  mov     dword ptr [rsi+8], 1
0x1800736a4  call    cs:__imp__Mtx_unlock
0x1800736aa  nop
0x1800736ab  mov     rcx, rdi
0x1800736ae  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency__details___TypeSelectorNoAsync____Init
0x1800736b3  nop
0x1800736b4  mov     rax, [rsp+58h+arg_8]
0x1800736b9  mov     rcx, [rax]
0x1800736bc  add     rcx, 160h
0x1800736c3  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x1800736c9  mov     rbx, [rsp+58h+arg_10]
0x1800736ce  add     rsp, 40h
0x1800736d2  pop     r14
0x1800736d4  pop     rdi
0x1800736d5  pop     rsi
0x1800736d6  retn
0x1800736d7  jmp     short loc_1800736B4
0x1800736d9  jmp     short loc_1800736B4
```

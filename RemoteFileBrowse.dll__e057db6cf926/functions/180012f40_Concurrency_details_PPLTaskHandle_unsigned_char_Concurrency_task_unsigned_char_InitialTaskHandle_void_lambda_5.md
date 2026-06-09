# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180012f40`
- end: `0x18001300b`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18001213c`
- `0x180012f40`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180012ff3`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180012ff3`
- `msvcp_win!_Mtx_unlock` at `0x180012fa0`
- `msvcp_win!_Mtx_unlock` at `0x180012fd4`
- `msvcp_win!_Mtx_unlock` at `0x180012fa0`
- `msvcp_win!_Mtx_unlock` at `0x180012fd4`
- `msvcp_win!_Mtx_lock` at `0x180012f63`
- `msvcp_win!_Mtx_lock` at `0x180012f63`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012f72`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012f8e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012f72`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012f8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
      Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
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
0x180012f40  mov     [rsp+arg_10], rbx
0x180012f45  mov     [rsp+arg_0], rcx
0x180012f4a  push    rsi
0x180012f4b  push    rdi
0x180012f4c  push    r14
0x180012f4e  sub     rsp, 40h
0x180012f52  mov     rdi, rcx
0x180012f55  lea     r14, [rcx+8]
0x180012f59  mov     rsi, [r14]
0x180012f5c  lea     rbx, [rsi+20h]
0x180012f60  mov     rcx, rbx; _Mtx_t
0x180012f63  call    cs:__imp__Mtx_lock
0x180012f69  test    eax, eax
0x180012f6b  jz      short loc_180012F79
0x180012f6d  mov     ecx, 5
0x180012f72  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012f78  int     3; Trap to Debugger
0x180012f79  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180012f80  jnz     short loc_180012F95
0x180012f82  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180012f89  mov     ecx, 6
0x180012f8e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012f94  int     3; Trap to Debugger
0x180012f95  mov     eax, [rsi+8]
0x180012f98  mov     rcx, rbx; _Mtx_t
0x180012f9b  cmp     eax, 2
0x180012f9e  jnz     short loc_180012FC8
0x180012fa0  call    cs:__imp__Mtx_unlock
0x180012fa6  mov     rcx, [r14]
0x180012fa9  mov     rax, [rcx]
0x180012fac  lea     rdx, [rcx+10h]
0x180012fb0  mov     [rsp+58h+var_38], rdx
0x180012fb5  xor     r9d, r9d
0x180012fb8  xor     r8d, r8d
0x180012fbb  mov     dl, 1
0x180012fbd  mov     rax, [rax+8]
0x180012fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fc6  jmp     short loc_180012FF9
0x180012fc8  mov     [rsp+58h+arg_8], r14
0x180012fcd  mov     dword ptr [rsi+8], 1
0x180012fd4  call    cs:__imp__Mtx_unlock
0x180012fda  nop
0x180012fdb  mov     rcx, rdi
0x180012fde  call    Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency__details___TypeSelectorNoAsync____Init
0x180012fe3  nop
0x180012fe4  mov     rax, [rsp+58h+arg_8]
0x180012fe9  mov     rcx, [rax]
0x180012fec  add     rcx, 160h
0x180012ff3  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180012ff9  mov     rbx, [rsp+58h+arg_10]
0x180012ffe  add     rsp, 40h
0x180013002  pop     r14
0x180013004  pop     rdi
0x180013005  pop     rsi
0x180013006  retn
0x180013007  jmp     short loc_180012FE4
0x180013009  jmp     short loc_180012FE4
```

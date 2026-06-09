# Concurrency::details::_PPLTaskHandle_HttpRequest::HttpResponse_Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke

- ea: `0x180060170`
- end: `0x18006023b`
- name: `Concurrency::details::_PPLTaskHandle_HttpRequest::HttpResponse_Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18005fb98`
- `0x180060170`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800601d0`
- `msvcp_win!_Mtx_unlock` at `0x180060204`
- `msvcp_win!_Mtx_unlock` at `0x1800601d0`
- `msvcp_win!_Mtx_unlock` at `0x180060204`
- `msvcp_win!_Mtx_lock` at `0x180060193`
- `msvcp_win!_Mtx_lock` at `0x180060193`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800601a2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800601be`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800601a2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800601be`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180060223`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180060223`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle_HttpRequest::HttpResponse_Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke(
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
      Concurrency::task_HttpRequest::HttpResponse_::_InitialTaskHandle_HttpRequest::HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency::details::_TypeSelectorNoAsync_::_Init(a1);
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
0x180060170  mov     [rsp+arg_10], rbx
0x180060175  mov     [rsp+arg_0], rcx
0x18006017a  push    rsi
0x18006017b  push    rdi
0x18006017c  push    r14
0x18006017e  sub     rsp, 40h
0x180060182  mov     rdi, rcx
0x180060185  lea     r14, [rcx+8]
0x180060189  mov     rsi, [r14]
0x18006018c  lea     rbx, [rsi+20h]
0x180060190  mov     rcx, rbx; _Mtx_t
0x180060193  call    cs:__imp__Mtx_lock
0x180060199  test    eax, eax
0x18006019b  jz      short loc_1800601A9
0x18006019d  mov     ecx, 5
0x1800601a2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800601a8  int     3; Trap to Debugger
0x1800601a9  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800601b0  jnz     short loc_1800601C5
0x1800601b2  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x1800601b9  mov     ecx, 6
0x1800601be  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800601c4  int     3; Trap to Debugger
0x1800601c5  mov     eax, [rsi+8]
0x1800601c8  mov     rcx, rbx; _Mtx_t
0x1800601cb  cmp     eax, 2
0x1800601ce  jnz     short loc_1800601F8
0x1800601d0  call    cs:__imp__Mtx_unlock
0x1800601d6  mov     rcx, [r14]
0x1800601d9  mov     rax, [rcx]
0x1800601dc  lea     rdx, [rcx+10h]
0x1800601e0  mov     [rsp+58h+var_38], rdx
0x1800601e5  xor     r9d, r9d
0x1800601e8  xor     r8d, r8d
0x1800601eb  mov     dl, 1
0x1800601ed  mov     rax, [rax+8]
0x1800601f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601f6  jmp     short loc_180060229
0x1800601f8  mov     [rsp+58h+arg_8], r14
0x1800601fd  mov     dword ptr [rsi+8], 1
0x180060204  call    cs:__imp__Mtx_unlock
0x18006020a  nop
0x18006020b  mov     rcx, rdi
0x18006020e  call    Concurrency__task_HttpRequest__HttpResponse____InitialTaskHandle_HttpRequest__HttpResponse__lambda_8130d6685246581cf174266372fcb501__Concurrency__details___TypeSelectorNoAsync____Init
0x180060213  nop
0x180060214  mov     rax, [rsp+58h+arg_8]
0x180060219  mov     rcx, [rax]
0x18006021c  add     rcx, 160h
0x180060223  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x180060229  mov     rbx, [rsp+58h+arg_10]
0x18006022e  add     rsp, 40h
0x180060232  pop     r14
0x180060234  pop     rdi
0x180060235  pop     rsi
0x180060236  retn
0x180060237  jmp     short loc_180060214
0x180060239  jmp     short loc_180060214
```

# Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18001e1c4`
- end: `0x18001e32c`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f0b0`

## callees

- `0x18001e1c4`
- `0x18001e344`
- `0x18001e824`
- `0x18001f150`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e27a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e27a`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e251`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e251`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001e261`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001e261`
- `msvcp_win!_Mtx_unlock` at `0x18001e2c6`
- `msvcp_win!_Mtx_unlock` at `0x18001e2d5`
- `msvcp_win!_Mtx_unlock` at `0x18001e30b`
- `msvcp_win!_Mtx_unlock` at `0x18001e2c6`
- `msvcp_win!_Mtx_unlock` at `0x18001e2d5`
- `msvcp_win!_Mtx_unlock` at `0x18001e30b`
- `msvcp_win!_Cnd_broadcast` at `0x18001e301`
- `msvcp_win!_Cnd_broadcast` at `0x18001e301`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
        __int64 a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rdx
  Concurrency::details::_TaskEventLogger *v4; // rdi
  char v5; // si
  _BYTE *v6; // rdx
  struct _Mtx_internal_imp_t *v7; // rcx
  _QWORD v8[7]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD *v9; // [rsp+58h] [rbp-1h]
  _BYTE v10[56]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v11; // [rsp+98h] [rbp+3Fh]

  v2 = *(_QWORD *)(a1 + 8);
  v8[0] = &std::_Func_impl_no_alloc<_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,void,>::`vftable';
  v8[1] = *(_QWORD *)(a1 + 24);
  v9 = v8;
  Concurrency::details::_MakeVoidToUnitFunc(v10, v8);
  if ( v9 )
  {
    v3 = v8;
    LOBYTE(v3) = v9 != v8;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v9 + 32LL))(v9, v3);
    v9 = 0;
  }
  v4 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v4);
  if ( !v11 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v5 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 16LL))(v11);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v4);
  if ( v11 )
  {
    v6 = v10;
    LOBYTE(v6) = v11 != v10;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, v6);
    v11 = 0;
  }
  *(_BYTE *)(v2 + 368) = v5;
  std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 32));
  v7 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v7);
  }
  else
  {
    *(_DWORD *)(v2 + 8) = 3;
    _Mtx_unlock(v7);
    std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 208));
    if ( *(int *)(v2 + 312) < 2 )
      *(_DWORD *)(v2 + 312) = 2;
    _Cnd_broadcast((_Cnd_t)(v2 + 136));
    _Mtx_unlock((_Mtx_t)(v2 + 208));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x18001e1c4  mov     [rsp-8+arg_18], rbx
0x18001e1c9  push    rbp
0x18001e1ca  push    rsi
0x18001e1cb  push    rdi
0x18001e1cc  lea     rbp, [rsp-47h]
0x18001e1d1  sub     rsp, 0A0h
0x18001e1d8  mov     rdi, rcx
0x18001e1db  mov     rbx, [rcx+8]
0x18001e1df  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,void,>::`vftable'
0x18001e1e6  mov     [rbp+57h+var_90], rax
0x18001e1ea  mov     rax, [rcx+18h]
0x18001e1ee  mov     [rbp+57h+var_88], rax
0x18001e1f2  lea     rax, [rbp+57h+var_90]
0x18001e1f6  mov     [rbp+57h+var_58], rax
0x18001e1fa  lea     rax, [rbp+57h+var_90]
0x18001e1fe  mov     [rbp+57h+arg_0], rax
0x18001e202  lea     rdx, [rbp+57h+var_90]
0x18001e206  lea     rcx, [rbp+57h+var_50]
0x18001e20a  call    ?_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@4@@Z; Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)
0x18001e20f  nop
0x18001e210  mov     rcx, [rbp+57h+var_58]
0x18001e214  test    rcx, rcx
0x18001e217  jz      short loc_18001E237
0x18001e219  mov     rax, [rcx]
0x18001e21c  lea     rdx, [rbp+57h+var_90]
0x18001e220  cmp     rcx, rdx
0x18001e223  setnz   dl
0x18001e226  mov     rax, [rax+20h]
0x18001e22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e22f  mov     [rbp+57h+var_58], 0
0x18001e237  lea     rax, [rbp+57h+var_50]
0x18001e23b  mov     [rbp+57h+arg_0], rax
0x18001e23f  mov     rdi, [rdi+8]
0x18001e243  add     rdi, 160h
0x18001e24a  mov     [rbp+57h+arg_10], rdi
0x18001e24e  mov     rcx, rdi
0x18001e251  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18001e257  nop
0x18001e258  mov     rcx, [rbp+57h+var_18]
0x18001e25c  test    rcx, rcx
0x18001e25f  jnz     short loc_18001E268
0x18001e261  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001e267  int     3; Trap to Debugger
0x18001e268  mov     rax, [rcx]
0x18001e26b  mov     rax, [rax+10h]
0x18001e26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e274  mov     sil, al
0x18001e277  mov     rcx, rdi
0x18001e27a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001e280  nop
0x18001e281  mov     rcx, [rbp+57h+var_18]
0x18001e285  test    rcx, rcx
0x18001e288  jz      short loc_18001E2A8
0x18001e28a  mov     rax, [rcx]
0x18001e28d  lea     rdx, [rbp+57h+var_50]
0x18001e291  cmp     rcx, rdx
0x18001e294  setnz   dl
0x18001e297  mov     rax, [rax+20h]
0x18001e29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a0  mov     [rbp+57h+var_18], 0
0x18001e2a8  mov     [rbx+170h], sil
0x18001e2af  lea     rdi, [rbx+20h]
0x18001e2b3  mov     rcx, rdi; this
0x18001e2b6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001e2bb  mov     eax, [rbx+8]
0x18001e2be  mov     rcx, rdi; _Mtx_t
0x18001e2c1  cmp     eax, 4
0x18001e2c4  jnz     short loc_18001E2CE
0x18001e2c6  call    cs:__imp__Mtx_unlock
0x18001e2cc  jmp     short loc_18001E319
0x18001e2ce  mov     dword ptr [rbx+8], 3
0x18001e2d5  call    cs:__imp__Mtx_unlock
0x18001e2db  lea     rdi, [rbx+88h]
0x18001e2e2  lea     rcx, [rdi+48h]; this
0x18001e2e6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001e2eb  cmp     dword ptr [rdi+0B0h], 2
0x18001e2f2  jge     short loc_18001E2FE
0x18001e2f4  mov     dword ptr [rdi+0B0h], 2
0x18001e2fe  mov     rcx, rdi; _Cnd_t
0x18001e301  call    cs:__imp__Cnd_broadcast
0x18001e307  lea     rcx, [rdi+48h]; _Mtx_t
0x18001e30b  call    cs:__imp__Mtx_unlock
0x18001e311  mov     rcx, rbx; this
0x18001e314  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x18001e319  mov     rbx, [rsp+0B0h+arg_18]
0x18001e321  add     rsp, 0A0h
0x18001e328  pop     rdi
0x18001e329  pop     rsi
0x18001e32a  pop     rbp
0x18001e32b  retn
```

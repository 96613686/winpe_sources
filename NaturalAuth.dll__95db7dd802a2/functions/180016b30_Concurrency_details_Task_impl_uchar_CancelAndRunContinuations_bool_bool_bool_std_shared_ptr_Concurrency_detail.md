# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180016b30`
- end: `0x180016d0c`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180004170`
- `0x180005de0`
- `0x180013558`
- `0x180016b30`
- `0x180017648`
- `0x18001a2b8`
- `0x18001b764`
- `0x180046010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180016c64`
- `msvcp_win!_Cnd_broadcast` at `0x180016c64`
- `msvcp_win!_Mtx_unlock` at `0x180016c11`
- `msvcp_win!_Mtx_unlock` at `0x180016c6e`
- `msvcp_win!_Mtx_unlock` at `0x180016ce7`
- `msvcp_win!_Mtx_unlock` at `0x180016c11`
- `msvcp_win!_Mtx_unlock` at `0x180016c6e`
- `msvcp_win!_Mtx_unlock` at `0x180016ce7`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180016c07`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180016c07`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        _QWORD *a5)
{
  struct _Mtx_internal_imp_t *v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  std::_Ref_count_base *v12; // rax
  int v13; // ebx
  int v14; // ebx
  _QWORD *v15; // rdx
  __int64 v17; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v18[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp-50h]

  v8 = (struct _Mtx_internal_imp_t *)(a1 + 32);
  v17 = a1 + 32;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  v9 = *(_DWORD *)(a1 + 8);
  if ( a3 )
  {
    if ( v9 != 4 )
    {
      v10 = a5[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v11 = a5[1];
      *(_QWORD *)(a1 + 16) = *a5;
      v12 = *(std::_Ref_count_base **)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v11;
      if ( v12 )
        std::_Ref_count_base::_Decref(v12);
      goto LABEL_11;
    }
LABEL_26:
    _Mtx_unlock(v8);
    return 0;
  }
  if ( v9 == 3 || *(_DWORD *)(a1 + 8) == 4 || *(_DWORD *)(a1 + 8) == 2 && !a2 )
    goto LABEL_26;
LABEL_11:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v13 = 1;
  }
  else
  {
    v13 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v13 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock(v8);
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      if ( *(_QWORD *)(a1 + 432) )
        std::_Func_class<void,>::operator()(a1 + 376);
    }
  }
  else
  {
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 208));
    if ( *(int *)(a1 + 312) < 2 )
      *(_DWORD *)(a1 + 312) = 2;
    _Cnd_broadcast((_Cnd_t)(a1 + 136));
    _Mtx_unlock((_Mtx_t)(a1 + 208));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v19 = 0;
      v18[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
      v18[1] = *_lambda_a7f0a2bc7a848057a70d113d8425a777_::_lambda_a7f0a2bc7a848057a70d113d8425a777_(&v17, a1);
      v19 = v18;
      Concurrency::details::_ScheduleFuncWithAutoInline(v18, 16);
      if ( v19 )
      {
        v15 = v18;
        LOBYTE(v15) = v19 != v18;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v15);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180016b30  push    rbx
0x180016b32  push    rbp
0x180016b33  push    rsi
0x180016b34  push    rdi
0x180016b35  push    r12
0x180016b37  push    r14
0x180016b39  sub     rsp, 88h
0x180016b40  mov     rax, cs:__security_cookie
0x180016b47  xor     rax, rsp
0x180016b4a  mov     [rsp+0B8h+var_48], rax
0x180016b4f  mov     bl, r8b
0x180016b52  mov     bpl, dl
0x180016b55  mov     rdi, rcx
0x180016b58  mov     r14, [rsp+0B8h+arg_20]
0x180016b60  lea     rsi, [rcx+20h]
0x180016b64  mov     [rsp+0B8h+var_98], rsi
0x180016b69  mov     rcx, rsi; this
0x180016b6c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180016b71  nop
0x180016b72  mov     r12d, 2
0x180016b78  mov     eax, [rdi+8]
0x180016b7b  test    bl, bl
0x180016b7d  jz      short loc_180016BB7
0x180016b7f  cmp     eax, 4
0x180016b82  jz      loc_180016CE4
0x180016b88  mov     rax, [r14+8]
0x180016b8c  test    rax, rax
0x180016b8f  jz      short loc_180016B95
0x180016b91  lock inc dword ptr [rax+8]
0x180016b95  mov     rcx, [r14+8]
0x180016b99  mov     rax, [r14]
0x180016b9c  mov     [rdi+10h], rax
0x180016ba0  mov     rax, [rdi+18h]
0x180016ba4  mov     [rdi+18h], rcx
0x180016ba8  test    rax, rax
0x180016bab  jz      short loc_180016BDD
0x180016bad  mov     rcx, rax; this
0x180016bb0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016bb5  jmp     short loc_180016BDD
0x180016bb7  cmp     eax, 3
0x180016bba  jz      loc_180016CE4
0x180016bc0  mov     eax, [rdi+8]
0x180016bc3  cmp     eax, 4
0x180016bc6  jz      loc_180016CE4
0x180016bcc  mov     eax, [rdi+8]
0x180016bcf  cmp     eax, r12d
0x180016bd2  jnz     short loc_180016BDD
0x180016bd4  test    bpl, bpl
0x180016bd7  jz      loc_180016CE4
0x180016bdd  test    bpl, bpl
0x180016be0  jz      short loc_180016BF0
0x180016be2  mov     dword ptr [rdi+8], 4
0x180016be9  mov     ebx, 1
0x180016bee  jmp     short loc_180016C0E
0x180016bf0  mov     eax, [rdi+8]
0x180016bf3  xor     ebx, ebx
0x180016bf5  cmp     eax, 1
0x180016bf8  cmovz   ebx, r12d
0x180016bfc  mov     [rdi+8], r12d
0x180016c00  lea     rcx, [rdi+160h]
0x180016c07  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180016c0d  nop
0x180016c0e  mov     rcx, rsi; _Mtx_t
0x180016c11  call    cs:__imp__Mtx_unlock
0x180016c17  sub     ebx, 1
0x180016c1a  jz      short loc_180016C41
0x180016c1c  cmp     ebx, 1
0x180016c1f  jnz     loc_180016CE0
0x180016c25  lea     rcx, [rdi+178h]
0x180016c2c  cmp     qword ptr [rcx+38h], 0
0x180016c31  jz      loc_180016CE0
0x180016c37  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180016c3c  jmp     loc_180016CE0
0x180016c41  lea     rbx, [rdi+88h]
0x180016c48  lea     rcx, [rbx+48h]; this
0x180016c4c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180016c51  cmp     [rbx+0B0h], r12d
0x180016c58  jge     short loc_180016C61
0x180016c5a  mov     [rbx+0B0h], r12d
0x180016c61  mov     rcx, rbx; _Cnd_t
0x180016c64  call    cs:__imp__Cnd_broadcast
0x180016c6a  lea     rcx, [rbx+48h]; _Mtx_t
0x180016c6e  call    cs:__imp__Mtx_unlock
0x180016c74  cmp     qword ptr [rdi+70h], 0
0x180016c79  jz      short loc_180016CE0
0x180016c7b  mov     [rsp+0B8h+var_50], 0
0x180016c84  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x180016c8b  mov     [rsp+0B8h+var_88], rax
0x180016c90  mov     rdx, rdi
0x180016c93  lea     rcx, [rsp+0B8h+var_98]
0x180016c98  call    ??0_lambda_a7f0a2bc7a848057a70d113d8425a777_@@QEAA@PEAV?$_Task_async_state@X@std@@@Z; _lambda_a7f0a2bc7a848057a70d113d8425a777_::_lambda_a7f0a2bc7a848057a70d113d8425a777_(std::_Task_async_state<void> *)
0x180016c9d  mov     rcx, [rax]
0x180016ca0  mov     [rsp+0B8h+var_80], rcx
0x180016ca5  lea     rax, [rsp+0B8h+var_88]
0x180016caa  mov     [rsp+0B8h+var_50], rax
0x180016caf  mov     edx, 10h
0x180016cb4  lea     rcx, [rsp+0B8h+var_88]
0x180016cb9  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180016cbe  nop
0x180016cbf  mov     rcx, [rsp+0B8h+var_50]
0x180016cc4  test    rcx, rcx
0x180016cc7  jz      short loc_180016CE0
0x180016cc9  mov     rax, [rcx]
0x180016ccc  lea     rdx, [rsp+0B8h+var_88]
0x180016cd1  cmp     rcx, rdx
0x180016cd4  setnz   dl
0x180016cd7  mov     rax, [rax+20h]
0x180016cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce0  mov     al, 1
0x180016ce2  jmp     short loc_180016CEF
0x180016ce4  mov     rcx, rsi; _Mtx_t
0x180016ce7  call    cs:__imp__Mtx_unlock
0x180016ced  xor     al, al
0x180016cef  mov     rcx, [rsp+0B8h+var_48]
0x180016cf4  xor     rcx, rsp; StackCookie
0x180016cf7  call    __security_check_cookie
0x180016cfc  add     rsp, 88h
0x180016d03  pop     r14
0x180016d05  pop     r12
0x180016d07  pop     rdi
0x180016d08  pop     rsi
0x180016d09  pop     rbp
0x180016d0a  pop     rbx
0x180016d0b  retn
```

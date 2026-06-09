# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18001d720`
- end: `0x18001d8fc`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180003450`
- `0x180004bec`
- `0x1800109dc`
- `0x18001bdcc`
- `0x18001d720`
- `0x18001e9a0`
- `0x18001f150`
- `0x180046010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001d7f7`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001d7f7`
- `msvcp_win!_Mtx_unlock` at `0x18001d801`
- `msvcp_win!_Mtx_unlock` at `0x18001d85e`
- `msvcp_win!_Mtx_unlock` at `0x18001d8d7`
- `msvcp_win!_Mtx_unlock` at `0x18001d801`
- `msvcp_win!_Mtx_unlock` at `0x18001d85e`
- `msvcp_win!_Mtx_unlock` at `0x18001d8d7`
- `msvcp_win!_Cnd_broadcast` at `0x18001d854`
- `msvcp_win!_Cnd_broadcast` at `0x18001d854`

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
      v18[1] = *wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v17, a1);
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
0x18001d720  push    rbx
0x18001d722  push    rbp
0x18001d723  push    rsi
0x18001d724  push    rdi
0x18001d725  push    r12
0x18001d727  push    r14
0x18001d729  sub     rsp, 88h
0x18001d730  mov     rax, cs:__security_cookie
0x18001d737  xor     rax, rsp
0x18001d73a  mov     [rsp+0B8h+var_48], rax
0x18001d73f  mov     bl, r8b
0x18001d742  mov     bpl, dl
0x18001d745  mov     rdi, rcx
0x18001d748  mov     r14, [rsp+0B8h+arg_20]
0x18001d750  lea     rsi, [rcx+20h]
0x18001d754  mov     [rsp+0B8h+var_98], rsi
0x18001d759  mov     rcx, rsi; this
0x18001d75c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d761  nop
0x18001d762  mov     r12d, 2
0x18001d768  mov     eax, [rdi+8]
0x18001d76b  test    bl, bl
0x18001d76d  jz      short loc_18001D7A7
0x18001d76f  cmp     eax, 4
0x18001d772  jz      loc_18001D8D4
0x18001d778  mov     rax, [r14+8]
0x18001d77c  test    rax, rax
0x18001d77f  jz      short loc_18001D785
0x18001d781  lock inc dword ptr [rax+8]
0x18001d785  mov     rcx, [r14+8]
0x18001d789  mov     rax, [r14]
0x18001d78c  mov     [rdi+10h], rax
0x18001d790  mov     rax, [rdi+18h]
0x18001d794  mov     [rdi+18h], rcx
0x18001d798  test    rax, rax
0x18001d79b  jz      short loc_18001D7CD
0x18001d79d  mov     rcx, rax; this
0x18001d7a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001d7a5  jmp     short loc_18001D7CD
0x18001d7a7  cmp     eax, 3
0x18001d7aa  jz      loc_18001D8D4
0x18001d7b0  mov     eax, [rdi+8]
0x18001d7b3  cmp     eax, 4
0x18001d7b6  jz      loc_18001D8D4
0x18001d7bc  mov     eax, [rdi+8]
0x18001d7bf  cmp     eax, r12d
0x18001d7c2  jnz     short loc_18001D7CD
0x18001d7c4  test    bpl, bpl
0x18001d7c7  jz      loc_18001D8D4
0x18001d7cd  test    bpl, bpl
0x18001d7d0  jz      short loc_18001D7E0
0x18001d7d2  mov     dword ptr [rdi+8], 4
0x18001d7d9  mov     ebx, 1
0x18001d7de  jmp     short loc_18001D7FE
0x18001d7e0  mov     eax, [rdi+8]
0x18001d7e3  xor     ebx, ebx
0x18001d7e5  cmp     eax, 1
0x18001d7e8  cmovz   ebx, r12d
0x18001d7ec  mov     [rdi+8], r12d
0x18001d7f0  lea     rcx, [rdi+160h]
0x18001d7f7  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18001d7fd  nop
0x18001d7fe  mov     rcx, rsi; _Mtx_t
0x18001d801  call    cs:__imp__Mtx_unlock
0x18001d807  sub     ebx, 1
0x18001d80a  jz      short loc_18001D831
0x18001d80c  cmp     ebx, 1
0x18001d80f  jnz     loc_18001D8D0
0x18001d815  lea     rcx, [rdi+178h]
0x18001d81c  cmp     qword ptr [rcx+38h], 0
0x18001d821  jz      loc_18001D8D0
0x18001d827  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18001d82c  jmp     loc_18001D8D0
0x18001d831  lea     rbx, [rdi+88h]
0x18001d838  lea     rcx, [rbx+48h]; this
0x18001d83c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d841  cmp     [rbx+0B0h], r12d
0x18001d848  jge     short loc_18001D851
0x18001d84a  mov     [rbx+0B0h], r12d
0x18001d851  mov     rcx, rbx; _Cnd_t
0x18001d854  call    cs:__imp__Cnd_broadcast
0x18001d85a  lea     rcx, [rbx+48h]; _Mtx_t
0x18001d85e  call    cs:__imp__Mtx_unlock
0x18001d864  cmp     qword ptr [rdi+70h], 0
0x18001d869  jz      short loc_18001D8D0
0x18001d86b  mov     [rsp+0B8h+var_50], 0
0x18001d874  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18001d87b  mov     [rsp+0B8h+var_88], rax
0x18001d880  mov     rdx, rdi
0x18001d883  lea     rcx, [rsp+0B8h+var_98]
0x18001d888  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001d88d  mov     rcx, [rax]
0x18001d890  mov     [rsp+0B8h+var_80], rcx
0x18001d895  lea     rax, [rsp+0B8h+var_88]
0x18001d89a  mov     [rsp+0B8h+var_50], rax
0x18001d89f  mov     edx, 10h
0x18001d8a4  lea     rcx, [rsp+0B8h+var_88]
0x18001d8a9  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18001d8ae  nop
0x18001d8af  mov     rcx, [rsp+0B8h+var_50]
0x18001d8b4  test    rcx, rcx
0x18001d8b7  jz      short loc_18001D8D0
0x18001d8b9  mov     rax, [rcx]
0x18001d8bc  lea     rdx, [rsp+0B8h+var_88]
0x18001d8c1  cmp     rcx, rdx
0x18001d8c4  setnz   dl
0x18001d8c7  mov     rax, [rax+20h]
0x18001d8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d0  mov     al, 1
0x18001d8d2  jmp     short loc_18001D8DF
0x18001d8d4  mov     rcx, rsi; _Mtx_t
0x18001d8d7  call    cs:__imp__Mtx_unlock
0x18001d8dd  xor     al, al
0x18001d8df  mov     rcx, [rsp+0B8h+var_48]
0x18001d8e4  xor     rcx, rsp; StackCookie
0x18001d8e7  call    __security_check_cookie
0x18001d8ec  add     rsp, 88h
0x18001d8f3  pop     r14
0x18001d8f5  pop     r12
0x18001d8f7  pop     rdi
0x18001d8f8  pop     rsi
0x18001d8f9  pop     rbp
0x18001d8fa  pop     rbx
0x18001d8fb  retn
```

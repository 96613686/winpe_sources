# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x14001e3e0`
- end: `0x14001e5bf`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x140004870`
- `0x1400194a0`
- `0x140019d2c`
- `0x14001c9e4`
- `0x14001e3e0`
- `0x14001f704`
- `0x1401b9010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001e4b4`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14001e4b4`
- `msvcp_win!_Cnd_broadcast` at `0x14001e51d`
- `msvcp_win!_Cnd_broadcast` at `0x14001e51d`
- `msvcp_win!_Mtx_unlock` at `0x14001e4c4`
- `msvcp_win!_Mtx_unlock` at `0x14001e52d`
- `msvcp_win!_Mtx_unlock` at `0x14001e593`
- `msvcp_win!_Mtx_unlock` at `0x14001e4c4`
- `msvcp_win!_Mtx_unlock` at `0x14001e52d`
- `msvcp_win!_Mtx_unlock` at `0x14001e593`

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
  __int64 v11; // rdx
  std::_Ref_count_base *v12; // rcx
  int v13; // ebx
  int v14; // ebx
  _QWORD *v15; // rdx
  _QWORD v17[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp-50h]

  v8 = (struct _Mtx_internal_imp_t *)(a1 + 32);
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
      v17[0] = ___7___Func_impl_no_alloc_V_lambda_1___CC____CancelAndRunContinuations____Task_impl_E_details_Concurrency__UEAA_N_N00AEBV__shared_ptr_U_ExceptionHolder_details_Concurrency___std___Z_X__V_std__6B_;
      v17[1] = a1;
      v18 = v17;
      Concurrency::details::_ScheduleFuncWithAutoInline(v17, 16);
      if ( v18 )
      {
        v15 = v17;
        LOBYTE(v15) = v18 != v17;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v18 + 32LL))(v18, v15);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14001e3e0  push    rbx
0x14001e3e2  push    rbp
0x14001e3e3  push    rsi
0x14001e3e4  push    rdi
0x14001e3e5  push    r14
0x14001e3e7  push    r15
0x14001e3e9  sub     rsp, 88h
0x14001e3f0  mov     rax, cs:__security_cookie
0x14001e3f7  xor     rax, rsp
0x14001e3fa  mov     [rsp+0B8h+var_48], rax
0x14001e3ff  mov     bl, r8b
0x14001e402  mov     bpl, dl
0x14001e405  mov     rdi, rcx
0x14001e408  mov     r14, [rsp+0B8h+arg_20]
0x14001e410  lea     rsi, [rcx+20h]
0x14001e414  mov     [rsp+0B8h+var_98], rsi
0x14001e419  mov     rcx, rsi; this
0x14001e41c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14001e421  nop
0x14001e422  mov     r15d, 2
0x14001e428  mov     eax, [rdi+8]
0x14001e42b  test    bl, bl
0x14001e42d  jz      short loc_14001E464
0x14001e42f  cmp     eax, 4
0x14001e432  jz      loc_14001E590
0x14001e438  mov     rax, [r14+8]
0x14001e43c  test    rax, rax
0x14001e43f  jz      short loc_14001E445
0x14001e441  lock inc dword ptr [rax+8]
0x14001e445  mov     rdx, [r14+8]
0x14001e449  mov     rax, [r14]
0x14001e44c  mov     [rdi+10h], rax
0x14001e450  mov     rcx, [rdi+18h]; this
0x14001e454  mov     [rdi+18h], rdx
0x14001e458  test    rcx, rcx
0x14001e45b  jz      short loc_14001E48A
0x14001e45d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001e462  jmp     short loc_14001E48A
0x14001e464  cmp     eax, 3
0x14001e467  jz      loc_14001E590
0x14001e46d  mov     eax, [rdi+8]
0x14001e470  cmp     eax, 4
0x14001e473  jz      loc_14001E590
0x14001e479  mov     eax, [rdi+8]
0x14001e47c  cmp     eax, r15d
0x14001e47f  jnz     short loc_14001E48A
0x14001e481  test    bpl, bpl
0x14001e484  jz      loc_14001E590
0x14001e48a  test    bpl, bpl
0x14001e48d  jz      short loc_14001E49D
0x14001e48f  mov     dword ptr [rdi+8], 4
0x14001e496  mov     ebx, 1
0x14001e49b  jmp     short loc_14001E4C1
0x14001e49d  mov     eax, [rdi+8]
0x14001e4a0  xor     ebx, ebx
0x14001e4a2  cmp     eax, 1
0x14001e4a5  cmovz   ebx, r15d
0x14001e4a9  mov     [rdi+8], r15d
0x14001e4ad  lea     rcx, [rdi+160h]
0x14001e4b4  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x14001e4bb  nop     dword ptr [rax+rax+00h]
0x14001e4c0  nop
0x14001e4c1  mov     rcx, rsi; _Mtx_t
0x14001e4c4  call    cs:__imp__Mtx_unlock
0x14001e4cb  nop     dword ptr [rax+rax+00h]
0x14001e4d0  sub     ebx, 1
0x14001e4d3  jz      short loc_14001E4FA
0x14001e4d5  cmp     ebx, 1
0x14001e4d8  jnz     loc_14001E58C
0x14001e4de  lea     rcx, [rdi+178h]
0x14001e4e5  cmp     qword ptr [rcx+38h], 0
0x14001e4ea  jz      loc_14001E58C
0x14001e4f0  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x14001e4f5  jmp     loc_14001E58C
0x14001e4fa  lea     rbx, [rdi+88h]
0x14001e501  lea     rcx, [rbx+48h]; this
0x14001e505  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14001e50a  cmp     [rbx+0B0h], r15d
0x14001e511  jge     short loc_14001E51A
0x14001e513  mov     [rbx+0B0h], r15d
0x14001e51a  mov     rcx, rbx; _Cnd_t
0x14001e51d  call    cs:__imp__Cnd_broadcast
0x14001e524  nop     dword ptr [rax+rax+00h]
0x14001e529  lea     rcx, [rbx+48h]; _Mtx_t
0x14001e52d  call    cs:__imp__Mtx_unlock
0x14001e534  nop     dword ptr [rax+rax+00h]
0x14001e539  cmp     qword ptr [rdi+70h], 0
0x14001e53e  jz      short loc_14001E58C
0x14001e540  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?CC@??_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)'::`34'::_lambda_1_,void,>::`vftable'
0x14001e547  mov     [rsp+0B8h+var_88], rax
0x14001e54c  mov     [rsp+0B8h+var_80], rdi
0x14001e551  lea     rax, [rsp+0B8h+var_88]
0x14001e556  mov     [rsp+0B8h+var_50], rax
0x14001e55b  mov     edx, 10h
0x14001e560  lea     rcx, [rsp+0B8h+var_88]
0x14001e565  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x14001e56a  nop
0x14001e56b  mov     rcx, [rsp+0B8h+var_50]
0x14001e570  test    rcx, rcx
0x14001e573  jz      short loc_14001E58C
0x14001e575  mov     rax, [rcx]
0x14001e578  lea     rdx, [rsp+0B8h+var_88]
0x14001e57d  cmp     rcx, rdx
0x14001e580  setnz   dl
0x14001e583  mov     rax, [rax+20h]
0x14001e587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e58c  mov     al, 1
0x14001e58e  jmp     short loc_14001E5A1
0x14001e590  mov     rcx, rsi; _Mtx_t
0x14001e593  call    cs:__imp__Mtx_unlock
0x14001e59a  nop     dword ptr [rax+rax+00h]
0x14001e59f  xor     al, al
0x14001e5a1  mov     rcx, [rsp+0B8h+var_48]
0x14001e5a6  xor     rcx, rsp; StackCookie
0x14001e5a9  call    __security_check_cookie
0x14001e5ae  add     rsp, 88h
0x14001e5b5  pop     r15
0x14001e5b7  pop     r14
0x14001e5b9  pop     rdi
0x14001e5ba  pop     rsi
0x14001e5bb  pop     rbp
0x14001e5bc  pop     rbx
0x14001e5bd  retn
```

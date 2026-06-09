# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1800477c0`
- end: `0x18004799c`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18000a6e0`
- `0x18000cebc`
- `0x18003330c`
- `0x180047238`
- `0x1800477c0`
- `0x180048908`
- `0x180048ea0`
- `0x18005c010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800478a1`
- `msvcp_win!_Mtx_unlock` at `0x1800478fe`
- `msvcp_win!_Mtx_unlock` at `0x180047977`
- `msvcp_win!_Mtx_unlock` at `0x1800478a1`
- `msvcp_win!_Mtx_unlock` at `0x1800478fe`
- `msvcp_win!_Mtx_unlock` at `0x180047977`
- `msvcp_win!_Cnd_broadcast` at `0x1800478f4`
- `msvcp_win!_Cnd_broadcast` at `0x1800478f4`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180047897`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180047897`

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
0x1800477c0  push    rbx
0x1800477c2  push    rbp
0x1800477c3  push    rsi
0x1800477c4  push    rdi
0x1800477c5  push    r12
0x1800477c7  push    r14
0x1800477c9  sub     rsp, 88h
0x1800477d0  mov     rax, cs:__security_cookie
0x1800477d7  xor     rax, rsp
0x1800477da  mov     [rsp+0B8h+var_48], rax
0x1800477df  mov     bl, r8b
0x1800477e2  mov     bpl, dl
0x1800477e5  mov     rdi, rcx
0x1800477e8  mov     r14, [rsp+0B8h+arg_20]
0x1800477f0  lea     rsi, [rcx+20h]
0x1800477f4  mov     [rsp+0B8h+var_98], rsi
0x1800477f9  mov     rcx, rsi; this
0x1800477fc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180047801  nop
0x180047802  mov     r12d, 2
0x180047808  mov     eax, [rdi+8]
0x18004780b  test    bl, bl
0x18004780d  jz      short loc_180047847
0x18004780f  cmp     eax, 4
0x180047812  jz      loc_180047974
0x180047818  mov     rax, [r14+8]
0x18004781c  test    rax, rax
0x18004781f  jz      short loc_180047825
0x180047821  lock inc dword ptr [rax+8]
0x180047825  mov     rcx, [r14+8]
0x180047829  mov     rax, [r14]
0x18004782c  mov     [rdi+10h], rax
0x180047830  mov     rax, [rdi+18h]
0x180047834  mov     [rdi+18h], rcx
0x180047838  test    rax, rax
0x18004783b  jz      short loc_18004786D
0x18004783d  mov     rcx, rax; this
0x180047840  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180047845  jmp     short loc_18004786D
0x180047847  cmp     eax, 3
0x18004784a  jz      loc_180047974
0x180047850  mov     eax, [rdi+8]
0x180047853  cmp     eax, 4
0x180047856  jz      loc_180047974
0x18004785c  mov     eax, [rdi+8]
0x18004785f  cmp     eax, r12d
0x180047862  jnz     short loc_18004786D
0x180047864  test    bpl, bpl
0x180047867  jz      loc_180047974
0x18004786d  test    bpl, bpl
0x180047870  jz      short loc_180047880
0x180047872  mov     dword ptr [rdi+8], 4
0x180047879  mov     ebx, 1
0x18004787e  jmp     short loc_18004789E
0x180047880  mov     eax, [rdi+8]
0x180047883  xor     ebx, ebx
0x180047885  cmp     eax, 1
0x180047888  cmovz   ebx, r12d
0x18004788c  mov     [rdi+8], r12d
0x180047890  lea     rcx, [rdi+160h]
0x180047897  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18004789d  nop
0x18004789e  mov     rcx, rsi; _Mtx_t
0x1800478a1  call    cs:__imp__Mtx_unlock
0x1800478a7  sub     ebx, 1
0x1800478aa  jz      short loc_1800478D1
0x1800478ac  cmp     ebx, 1
0x1800478af  jnz     loc_180047970
0x1800478b5  lea     rcx, [rdi+178h]
0x1800478bc  cmp     qword ptr [rcx+38h], 0
0x1800478c1  jz      loc_180047970
0x1800478c7  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1800478cc  jmp     loc_180047970
0x1800478d1  lea     rbx, [rdi+88h]
0x1800478d8  lea     rcx, [rbx+48h]; this
0x1800478dc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800478e1  cmp     [rbx+0B0h], r12d
0x1800478e8  jge     short loc_1800478F1
0x1800478ea  mov     [rbx+0B0h], r12d
0x1800478f1  mov     rcx, rbx; _Cnd_t
0x1800478f4  call    cs:__imp__Cnd_broadcast
0x1800478fa  lea     rcx, [rbx+48h]; _Mtx_t
0x1800478fe  call    cs:__imp__Mtx_unlock
0x180047904  cmp     qword ptr [rdi+70h], 0
0x180047909  jz      short loc_180047970
0x18004790b  mov     [rsp+0B8h+var_50], 0
0x180047914  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18004791b  mov     [rsp+0B8h+var_88], rax
0x180047920  mov     rdx, rdi
0x180047923  lea     rcx, [rsp+0B8h+var_98]
0x180047928  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18004792d  mov     rcx, [rax]
0x180047930  mov     [rsp+0B8h+var_80], rcx
0x180047935  lea     rax, [rsp+0B8h+var_88]
0x18004793a  mov     [rsp+0B8h+var_50], rax
0x18004793f  mov     edx, 10h
0x180047944  lea     rcx, [rsp+0B8h+var_88]
0x180047949  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18004794e  nop
0x18004794f  mov     rcx, [rsp+0B8h+var_50]
0x180047954  test    rcx, rcx
0x180047957  jz      short loc_180047970
0x180047959  mov     rax, [rcx]
0x18004795c  lea     rdx, [rsp+0B8h+var_88]
0x180047961  cmp     rcx, rdx
0x180047964  setnz   dl
0x180047967  mov     rax, [rax+20h]
0x18004796b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047970  mov     al, 1
0x180047972  jmp     short loc_18004797F
0x180047974  mov     rcx, rsi; _Mtx_t
0x180047977  call    cs:__imp__Mtx_unlock
0x18004797d  xor     al, al
0x18004797f  mov     rcx, [rsp+0B8h+var_48]
0x180047984  xor     rcx, rsp; StackCookie
0x180047987  call    __security_check_cookie
0x18004798c  add     rsp, 88h
0x180047993  pop     r14
0x180047995  pop     r12
0x180047997  pop     rdi
0x180047998  pop     rsi
0x180047999  pop     rbp
0x18004799a  pop     rbx
0x18004799b  retn
```

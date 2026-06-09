# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18001c140`
- end: `0x18001c31c`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `476`
- prototype: `char __fastcall(__int64, char, char, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180002380`
- `0x180005bfc`
- `0x180012830`
- `0x18001c140`
- `0x18001cc40`
- `0x18001dae4`
- `0x18001e88c`
- `0x180025010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001c221`
- `msvcp_win!_Mtx_unlock` at `0x18001c27e`
- `msvcp_win!_Mtx_unlock` at `0x18001c2f7`
- `msvcp_win!_Mtx_unlock` at `0x18001c221`
- `msvcp_win!_Mtx_unlock` at `0x18001c27e`
- `msvcp_win!_Mtx_unlock` at `0x18001c2f7`
- `msvcp_win!_Cnd_broadcast` at `0x18001c274`
- `msvcp_win!_Cnd_broadcast` at `0x18001c274`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c217`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c217`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18001c140  push    rbx
0x18001c142  push    rbp
0x18001c143  push    rsi
0x18001c144  push    rdi
0x18001c145  push    r12
0x18001c147  push    r14
0x18001c149  sub     rsp, 88h
0x18001c150  mov     rax, cs:__security_cookie
0x18001c157  xor     rax, rsp
0x18001c15a  mov     [rsp+0B8h+var_48], rax
0x18001c15f  mov     bl, r8b
0x18001c162  mov     bpl, dl
0x18001c165  mov     rdi, rcx
0x18001c168  mov     r14, [rsp+0B8h+arg_20]
0x18001c170  lea     rsi, [rcx+20h]
0x18001c174  mov     [rsp+0B8h+var_98], rsi
0x18001c179  mov     rcx, rsi; this
0x18001c17c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001c181  nop
0x18001c182  mov     r12d, 2
0x18001c188  mov     eax, [rdi+8]
0x18001c18b  test    bl, bl
0x18001c18d  jz      short loc_18001C1C7
0x18001c18f  cmp     eax, 4
0x18001c192  jz      loc_18001C2F4
0x18001c198  mov     rax, [r14+8]
0x18001c19c  test    rax, rax
0x18001c19f  jz      short loc_18001C1A5
0x18001c1a1  lock inc dword ptr [rax+8]
0x18001c1a5  mov     rcx, [r14+8]
0x18001c1a9  mov     rax, [r14]
0x18001c1ac  mov     [rdi+10h], rax
0x18001c1b0  mov     rax, [rdi+18h]
0x18001c1b4  mov     [rdi+18h], rcx
0x18001c1b8  test    rax, rax
0x18001c1bb  jz      short loc_18001C1ED
0x18001c1bd  mov     rcx, rax; this
0x18001c1c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c1c5  jmp     short loc_18001C1ED
0x18001c1c7  cmp     eax, 3
0x18001c1ca  jz      loc_18001C2F4
0x18001c1d0  mov     eax, [rdi+8]
0x18001c1d3  cmp     eax, 4
0x18001c1d6  jz      loc_18001C2F4
0x18001c1dc  mov     eax, [rdi+8]
0x18001c1df  cmp     eax, r12d
0x18001c1e2  jnz     short loc_18001C1ED
0x18001c1e4  test    bpl, bpl
0x18001c1e7  jz      loc_18001C2F4
0x18001c1ed  test    bpl, bpl
0x18001c1f0  jz      short loc_18001C200
0x18001c1f2  mov     dword ptr [rdi+8], 4
0x18001c1f9  mov     ebx, 1
0x18001c1fe  jmp     short loc_18001C21E
0x18001c200  mov     eax, [rdi+8]
0x18001c203  xor     ebx, ebx
0x18001c205  cmp     eax, 1
0x18001c208  cmovz   ebx, r12d
0x18001c20c  mov     [rdi+8], r12d
0x18001c210  lea     rcx, [rdi+160h]
0x18001c217  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18001c21d  nop
0x18001c21e  mov     rcx, rsi; _Mtx_t
0x18001c221  call    cs:__imp__Mtx_unlock
0x18001c227  sub     ebx, 1
0x18001c22a  jz      short loc_18001C251
0x18001c22c  cmp     ebx, 1
0x18001c22f  jnz     loc_18001C2F0
0x18001c235  lea     rcx, [rdi+178h]
0x18001c23c  cmp     qword ptr [rcx+38h], 0
0x18001c241  jz      loc_18001C2F0
0x18001c247  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18001c24c  jmp     loc_18001C2F0
0x18001c251  lea     rbx, [rdi+88h]
0x18001c258  lea     rcx, [rbx+48h]; this
0x18001c25c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001c261  cmp     [rbx+0B0h], r12d
0x18001c268  jge     short loc_18001C271
0x18001c26a  mov     [rbx+0B0h], r12d
0x18001c271  mov     rcx, rbx; _Cnd_t
0x18001c274  call    cs:__imp__Cnd_broadcast
0x18001c27a  lea     rcx, [rbx+48h]; _Mtx_t
0x18001c27e  call    cs:__imp__Mtx_unlock
0x18001c284  cmp     qword ptr [rdi+70h], 0
0x18001c289  jz      short loc_18001C2F0
0x18001c28b  mov     [rsp+0B8h+var_50], 0
0x18001c294  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18001c29b  mov     [rsp+0B8h+var_88], rax
0x18001c2a0  mov     rdx, rdi
0x18001c2a3  lea     rcx, [rsp+0B8h+var_98]
0x18001c2a8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001c2ad  mov     rcx, [rax]
0x18001c2b0  mov     [rsp+0B8h+var_80], rcx
0x18001c2b5  lea     rax, [rsp+0B8h+var_88]
0x18001c2ba  mov     [rsp+0B8h+var_50], rax
0x18001c2bf  mov     edx, 10h
0x18001c2c4  lea     rcx, [rsp+0B8h+var_88]
0x18001c2c9  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18001c2ce  nop
0x18001c2cf  mov     rcx, [rsp+0B8h+var_50]
0x18001c2d4  test    rcx, rcx
0x18001c2d7  jz      short loc_18001C2F0
0x18001c2d9  mov     rax, [rcx]
0x18001c2dc  lea     rdx, [rsp+0B8h+var_88]
0x18001c2e1  cmp     rcx, rdx
0x18001c2e4  setnz   dl
0x18001c2e7  mov     rax, [rax+20h]
0x18001c2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2f0  mov     al, 1
0x18001c2f2  jmp     short loc_18001C2FF
0x18001c2f4  mov     rcx, rsi; _Mtx_t
0x18001c2f7  call    cs:__imp__Mtx_unlock
0x18001c2fd  xor     al, al
0x18001c2ff  mov     rcx, [rsp+0B8h+var_48]
0x18001c304  xor     rcx, rsp; StackCookie
0x18001c307  call    __security_check_cookie
0x18001c30c  add     rsp, 88h
0x18001c313  pop     r14
0x18001c315  pop     r12
0x18001c317  pop     rdi
0x18001c318  pop     rsi
0x18001c319  pop     rbp
0x18001c31a  pop     rbx
0x18001c31b  retn
```

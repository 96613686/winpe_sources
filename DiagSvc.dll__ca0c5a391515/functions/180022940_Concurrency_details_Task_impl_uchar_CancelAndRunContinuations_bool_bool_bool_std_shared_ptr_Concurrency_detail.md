# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180022940`
- end: `0x180022b1c`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `476`
- prototype: `char __fastcall(__int64, char, char, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180003fc0`
- `0x1800083cc`
- `0x18001e760`
- `0x180022940`
- `0x180022f00`
- `0x180024068`
- `0x180024834`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180022a17`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180022a17`
- `msvcp_win!_Mtx_unlock` at `0x180022a21`
- `msvcp_win!_Mtx_unlock` at `0x180022a7e`
- `msvcp_win!_Mtx_unlock` at `0x180022af7`
- `msvcp_win!_Mtx_unlock` at `0x180022a21`
- `msvcp_win!_Mtx_unlock` at `0x180022a7e`
- `msvcp_win!_Mtx_unlock` at `0x180022af7`
- `msvcp_win!_Cnd_broadcast` at `0x180022a74`
- `msvcp_win!_Cnd_broadcast` at `0x180022a74`

## pseudocode

```c
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
0x180022940  push    rbx
0x180022942  push    rbp
0x180022943  push    rsi
0x180022944  push    rdi
0x180022945  push    r12
0x180022947  push    r14
0x180022949  sub     rsp, 88h
0x180022950  mov     rax, cs:__security_cookie
0x180022957  xor     rax, rsp
0x18002295a  mov     [rsp+0B8h+var_48], rax
0x18002295f  mov     bl, r8b
0x180022962  mov     bpl, dl
0x180022965  mov     rdi, rcx
0x180022968  mov     r14, [rsp+0B8h+arg_20]
0x180022970  lea     rsi, [rcx+20h]
0x180022974  mov     [rsp+0B8h+var_98], rsi
0x180022979  mov     rcx, rsi; this
0x18002297c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180022981  nop
0x180022982  mov     r12d, 2
0x180022988  mov     eax, [rdi+8]
0x18002298b  test    bl, bl
0x18002298d  jz      short loc_1800229C7
0x18002298f  cmp     eax, 4
0x180022992  jz      loc_180022AF4
0x180022998  mov     rax, [r14+8]
0x18002299c  test    rax, rax
0x18002299f  jz      short loc_1800229A5
0x1800229a1  lock inc dword ptr [rax+8]
0x1800229a5  mov     rcx, [r14+8]
0x1800229a9  mov     rax, [r14]
0x1800229ac  mov     [rdi+10h], rax
0x1800229b0  mov     rax, [rdi+18h]
0x1800229b4  mov     [rdi+18h], rcx
0x1800229b8  test    rax, rax
0x1800229bb  jz      short loc_1800229ED
0x1800229bd  mov     rcx, rax; this
0x1800229c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800229c5  jmp     short loc_1800229ED
0x1800229c7  cmp     eax, 3
0x1800229ca  jz      loc_180022AF4
0x1800229d0  mov     eax, [rdi+8]
0x1800229d3  cmp     eax, 4
0x1800229d6  jz      loc_180022AF4
0x1800229dc  mov     eax, [rdi+8]
0x1800229df  cmp     eax, r12d
0x1800229e2  jnz     short loc_1800229ED
0x1800229e4  test    bpl, bpl
0x1800229e7  jz      loc_180022AF4
0x1800229ed  test    bpl, bpl
0x1800229f0  jz      short loc_180022A00
0x1800229f2  mov     dword ptr [rdi+8], 4
0x1800229f9  mov     ebx, 1
0x1800229fe  jmp     short loc_180022A1E
0x180022a00  mov     eax, [rdi+8]
0x180022a03  xor     ebx, ebx
0x180022a05  cmp     eax, 1
0x180022a08  cmovz   ebx, r12d
0x180022a0c  mov     [rdi+8], r12d
0x180022a10  lea     rcx, [rdi+160h]
0x180022a17  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x180022a1d  nop
0x180022a1e  mov     rcx, rsi; _Mtx_t
0x180022a21  call    cs:__imp__Mtx_unlock
0x180022a27  sub     ebx, 1
0x180022a2a  jz      short loc_180022A51
0x180022a2c  cmp     ebx, 1
0x180022a2f  jnz     loc_180022AF0
0x180022a35  lea     rcx, [rdi+178h]
0x180022a3c  cmp     qword ptr [rcx+38h], 0
0x180022a41  jz      loc_180022AF0
0x180022a47  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180022a4c  jmp     loc_180022AF0
0x180022a51  lea     rbx, [rdi+88h]
0x180022a58  lea     rcx, [rbx+48h]; this
0x180022a5c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180022a61  cmp     [rbx+0B0h], r12d
0x180022a68  jge     short loc_180022A71
0x180022a6a  mov     [rbx+0B0h], r12d
0x180022a71  mov     rcx, rbx; _Cnd_t
0x180022a74  call    cs:__imp__Cnd_broadcast
0x180022a7a  lea     rcx, [rbx+48h]; _Mtx_t
0x180022a7e  call    cs:__imp__Mtx_unlock
0x180022a84  cmp     qword ptr [rdi+70h], 0
0x180022a89  jz      short loc_180022AF0
0x180022a8b  mov     [rsp+0B8h+var_50], 0
0x180022a94  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x180022a9b  mov     [rsp+0B8h+var_88], rax
0x180022aa0  mov     rdx, rdi
0x180022aa3  lea     rcx, [rsp+0B8h+var_98]
0x180022aa8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180022aad  mov     rcx, [rax]
0x180022ab0  mov     [rsp+0B8h+var_80], rcx
0x180022ab5  lea     rax, [rsp+0B8h+var_88]
0x180022aba  mov     [rsp+0B8h+var_50], rax
0x180022abf  mov     edx, 10h
0x180022ac4  lea     rcx, [rsp+0B8h+var_88]
0x180022ac9  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180022ace  nop
0x180022acf  mov     rcx, [rsp+0B8h+var_50]
0x180022ad4  test    rcx, rcx
0x180022ad7  jz      short loc_180022AF0
0x180022ad9  mov     rax, [rcx]
0x180022adc  lea     rdx, [rsp+0B8h+var_88]
0x180022ae1  cmp     rcx, rdx
0x180022ae4  setnz   dl
0x180022ae7  mov     rax, [rax+20h]
0x180022aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022af0  mov     al, 1
0x180022af2  jmp     short loc_180022AFF
0x180022af4  mov     rcx, rsi; _Mtx_t
0x180022af7  call    cs:__imp__Mtx_unlock
0x180022afd  xor     al, al
0x180022aff  mov     rcx, [rsp+0B8h+var_48]
0x180022b04  xor     rcx, rsp; StackCookie
0x180022b07  call    __security_check_cookie
0x180022b0c  add     rsp, 88h
0x180022b13  pop     r14
0x180022b15  pop     r12
0x180022b17  pop     rdi
0x180022b18  pop     rsi
0x180022b19  pop     rbp
0x180022b1a  pop     rbx
0x180022b1b  retn
```

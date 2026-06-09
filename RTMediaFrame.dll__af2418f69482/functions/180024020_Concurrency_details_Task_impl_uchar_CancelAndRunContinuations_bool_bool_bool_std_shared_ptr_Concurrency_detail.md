# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x180024020`
- end: `0x1800241db`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18001df10`
- `0x180024020`
- `0x1800243b4`
- `0x1800243e0`
- `0x18002448c`
- `0x180026920`
- `0x180032350`
- `0x180052010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180024133`
- `msvcp_win!_Cnd_broadcast` at `0x180024133`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800240d6`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800240d6`
- `msvcp_win!_Mtx_unlock` at `0x1800240e0`
- `msvcp_win!_Mtx_unlock` at `0x18002413d`
- `msvcp_win!_Mtx_unlock` at `0x1800241b6`
- `msvcp_win!_Mtx_unlock` at `0x1800240e0`
- `msvcp_win!_Mtx_unlock` at `0x18002413d`
- `msvcp_win!_Mtx_unlock` at `0x1800241b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  struct _Mtx_internal_imp_t *v8; // rsi
  int v9; // eax
  int v10; // ebx
  int v11; // ebx
  _QWORD *v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v15[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-50h]

  v8 = (struct _Mtx_internal_imp_t *)(a1 + 32);
  v14 = a1 + 32;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  v9 = *(_DWORD *)(a1 + 8);
  if ( !a3 )
  {
    if ( v9 != 3 && *(_DWORD *)(a1 + 8) != 4 && (*(_DWORD *)(a1 + 8) != 2 || a2) )
      goto LABEL_8;
LABEL_23:
    _Mtx_unlock(v8);
    return 0;
  }
  if ( v9 == 4 )
    goto LABEL_23;
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(a1 + 16, a5);
LABEL_8:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v10 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock(v8);
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
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
      v16 = 0;
      v15[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
      v15[1] = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                            &v14,
                            a1);
      v16 = v15;
      Concurrency::details::_ScheduleFuncWithAutoInline(v15, 16);
      if ( v16 )
      {
        v12 = v15;
        LOBYTE(v12) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v12);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180024020  push    rbx
0x180024022  push    rbp
0x180024023  push    rsi
0x180024024  push    rdi
0x180024025  push    r12
0x180024027  push    r14
0x180024029  sub     rsp, 88h
0x180024030  mov     rax, cs:__security_cookie
0x180024037  xor     rax, rsp
0x18002403a  mov     [rsp+0B8h+var_48], rax
0x18002403f  mov     bl, r8b
0x180024042  mov     bpl, dl
0x180024045  mov     rdi, rcx
0x180024048  mov     r14, [rsp+0B8h+arg_20]
0x180024050  lea     rsi, [rcx+20h]
0x180024054  mov     [rsp+0B8h+var_98], rsi
0x180024059  mov     rcx, rsi; this
0x18002405c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180024061  nop
0x180024062  mov     r12d, 2
0x180024068  mov     eax, [rdi+8]
0x18002406b  test    bl, bl
0x18002406d  jz      short loc_180024086
0x18002406f  cmp     eax, 4
0x180024072  jz      loc_1800241B3
0x180024078  lea     rcx, [rdi+10h]
0x18002407c  mov     rdx, r14
0x18002407f  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x180024084  jmp     short loc_1800240AC
0x180024086  cmp     eax, 3
0x180024089  jz      loc_1800241B3
0x18002408f  mov     eax, [rdi+8]
0x180024092  cmp     eax, 4
0x180024095  jz      loc_1800241B3
0x18002409b  mov     eax, [rdi+8]
0x18002409e  cmp     eax, r12d
0x1800240a1  jnz     short loc_1800240AC
0x1800240a3  test    bpl, bpl
0x1800240a6  jz      loc_1800241B3
0x1800240ac  test    bpl, bpl
0x1800240af  jz      short loc_1800240BF
0x1800240b1  mov     dword ptr [rdi+8], 4
0x1800240b8  mov     ebx, 1
0x1800240bd  jmp     short loc_1800240DD
0x1800240bf  mov     eax, [rdi+8]
0x1800240c2  xor     ebx, ebx
0x1800240c4  cmp     eax, 1
0x1800240c7  cmovz   ebx, r12d
0x1800240cb  mov     [rdi+8], r12d
0x1800240cf  lea     rcx, [rdi+160h]
0x1800240d6  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x1800240dc  nop
0x1800240dd  mov     rcx, rsi; _Mtx_t
0x1800240e0  call    cs:__imp__Mtx_unlock
0x1800240e6  sub     ebx, 1
0x1800240e9  jz      short loc_180024110
0x1800240eb  cmp     ebx, 1
0x1800240ee  jnz     loc_1800241AF
0x1800240f4  lea     rcx, [rdi+178h]
0x1800240fb  cmp     qword ptr [rcx+38h], 0
0x180024100  jz      loc_1800241AF
0x180024106  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002410b  jmp     loc_1800241AF
0x180024110  lea     rbx, [rdi+88h]
0x180024117  lea     rcx, [rbx+48h]; this
0x18002411b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180024120  cmp     [rbx+0B0h], r12d
0x180024127  jge     short loc_180024130
0x180024129  mov     [rbx+0B0h], r12d
0x180024130  mov     rcx, rbx; _Cnd_t
0x180024133  call    cs:__imp__Cnd_broadcast
0x180024139  lea     rcx, [rbx+48h]; _Mtx_t
0x18002413d  call    cs:__imp__Mtx_unlock
0x180024143  cmp     qword ptr [rdi+70h], 0
0x180024148  jz      short loc_1800241AF
0x18002414a  mov     [rsp+0B8h+var_50], 0
0x180024153  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18002415a  mov     [rsp+0B8h+var_88], rax
0x18002415f  mov     rdx, rdi
0x180024162  lea     rcx, [rsp+0B8h+var_98]
0x180024167  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002416c  mov     rcx, [rax]
0x18002416f  mov     [rsp+0B8h+var_80], rcx
0x180024174  lea     rax, [rsp+0B8h+var_88]
0x180024179  mov     [rsp+0B8h+var_50], rax
0x18002417e  mov     edx, 10h
0x180024183  lea     rcx, [rsp+0B8h+var_88]
0x180024188  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18002418d  nop
0x18002418e  mov     rcx, [rsp+0B8h+var_50]
0x180024193  test    rcx, rcx
0x180024196  jz      short loc_1800241AF
0x180024198  mov     rax, [rcx]
0x18002419b  lea     rdx, [rsp+0B8h+var_88]
0x1800241a0  cmp     rcx, rdx
0x1800241a3  setnz   dl
0x1800241a6  mov     rax, [rax+20h]
0x1800241aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241af  mov     al, 1
0x1800241b1  jmp     short loc_1800241BE
0x1800241b3  mov     rcx, rsi; _Mtx_t
0x1800241b6  call    cs:__imp__Mtx_unlock
0x1800241bc  xor     al, al
0x1800241be  mov     rcx, [rsp+0B8h+var_48]
0x1800241c3  xor     rcx, rsp; StackCookie
0x1800241c6  call    __security_check_cookie
0x1800241cb  add     rsp, 88h
0x1800241d2  pop     r14
0x1800241d4  pop     r12
0x1800241d6  pop     rdi
0x1800241d7  pop     rsi
0x1800241d8  pop     rbp
0x1800241d9  pop     rbx
0x1800241da  retn
```

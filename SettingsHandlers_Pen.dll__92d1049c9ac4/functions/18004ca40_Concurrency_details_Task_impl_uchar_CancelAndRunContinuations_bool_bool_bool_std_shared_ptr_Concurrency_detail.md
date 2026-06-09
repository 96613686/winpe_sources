# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18004ca40`
- end: `0x18004cbfb`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800030e0`
- `0x1800047ec`
- `0x180049a60`
- `0x18004aba0`
- `0x18004ca40`
- `0x18004f0b4`
- `0x18004fac4`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004caf6`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004caf6`
- `msvcp_win!_Mtx_unlock` at `0x18004cb00`
- `msvcp_win!_Mtx_unlock` at `0x18004cb5d`
- `msvcp_win!_Mtx_unlock` at `0x18004cbd6`
- `msvcp_win!_Mtx_unlock` at `0x18004cb00`
- `msvcp_win!_Mtx_unlock` at `0x18004cb5d`
- `msvcp_win!_Mtx_unlock` at `0x18004cbd6`
- `msvcp_win!_Cnd_broadcast` at `0x18004cb53`
- `msvcp_win!_Cnd_broadcast` at `0x18004cb53`

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
      v15[1] = *(_QWORD *)_lambda_e284b0dc2b4a3a31de4a6cc01957982e_::_lambda_e284b0dc2b4a3a31de4a6cc01957982e_(&v14, a1);
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
0x18004ca40  push    rbx
0x18004ca42  push    rbp
0x18004ca43  push    rsi
0x18004ca44  push    rdi
0x18004ca45  push    r12
0x18004ca47  push    r14
0x18004ca49  sub     rsp, 88h
0x18004ca50  mov     rax, cs:__security_cookie
0x18004ca57  xor     rax, rsp
0x18004ca5a  mov     [rsp+0B8h+var_48], rax
0x18004ca5f  mov     bl, r8b
0x18004ca62  mov     bpl, dl
0x18004ca65  mov     rdi, rcx
0x18004ca68  mov     r14, [rsp+0B8h+arg_20]
0x18004ca70  lea     rsi, [rcx+20h]
0x18004ca74  mov     [rsp+0B8h+var_98], rsi
0x18004ca79  mov     rcx, rsi; this
0x18004ca7c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004ca81  nop
0x18004ca82  mov     r12d, 2
0x18004ca88  mov     eax, [rdi+8]
0x18004ca8b  test    bl, bl
0x18004ca8d  jz      short loc_18004CAA6
0x18004ca8f  cmp     eax, 4
0x18004ca92  jz      loc_18004CBD3
0x18004ca98  lea     rcx, [rdi+10h]
0x18004ca9c  mov     rdx, r14
0x18004ca9f  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x18004caa4  jmp     short loc_18004CACC
0x18004caa6  cmp     eax, 3
0x18004caa9  jz      loc_18004CBD3
0x18004caaf  mov     eax, [rdi+8]
0x18004cab2  cmp     eax, 4
0x18004cab5  jz      loc_18004CBD3
0x18004cabb  mov     eax, [rdi+8]
0x18004cabe  cmp     eax, r12d
0x18004cac1  jnz     short loc_18004CACC
0x18004cac3  test    bpl, bpl
0x18004cac6  jz      loc_18004CBD3
0x18004cacc  test    bpl, bpl
0x18004cacf  jz      short loc_18004CADF
0x18004cad1  mov     dword ptr [rdi+8], 4
0x18004cad8  mov     ebx, 1
0x18004cadd  jmp     short loc_18004CAFD
0x18004cadf  mov     eax, [rdi+8]
0x18004cae2  xor     ebx, ebx
0x18004cae4  cmp     eax, 1
0x18004cae7  cmovz   ebx, r12d
0x18004caeb  mov     [rdi+8], r12d
0x18004caef  lea     rcx, [rdi+160h]
0x18004caf6  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18004cafc  nop
0x18004cafd  mov     rcx, rsi; _Mtx_t
0x18004cb00  call    cs:__imp__Mtx_unlock
0x18004cb06  sub     ebx, 1
0x18004cb09  jz      short loc_18004CB30
0x18004cb0b  cmp     ebx, 1
0x18004cb0e  jnz     loc_18004CBCF
0x18004cb14  lea     rcx, [rdi+178h]
0x18004cb1b  cmp     qword ptr [rcx+38h], 0
0x18004cb20  jz      loc_18004CBCF
0x18004cb26  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18004cb2b  jmp     loc_18004CBCF
0x18004cb30  lea     rbx, [rdi+88h]
0x18004cb37  lea     rcx, [rbx+48h]; this
0x18004cb3b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004cb40  cmp     [rbx+0B0h], r12d
0x18004cb47  jge     short loc_18004CB50
0x18004cb49  mov     [rbx+0B0h], r12d
0x18004cb50  mov     rcx, rbx; _Cnd_t
0x18004cb53  call    cs:__imp__Cnd_broadcast
0x18004cb59  lea     rcx, [rbx+48h]; _Mtx_t
0x18004cb5d  call    cs:__imp__Mtx_unlock
0x18004cb63  cmp     qword ptr [rdi+70h], 0
0x18004cb68  jz      short loc_18004CBCF
0x18004cb6a  mov     [rsp+0B8h+var_50], 0
0x18004cb73  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18004cb7a  mov     [rsp+0B8h+var_88], rax
0x18004cb7f  mov     rdx, rdi
0x18004cb82  lea     rcx, [rsp+0B8h+var_98]
0x18004cb87  call    ??0_lambda_e284b0dc2b4a3a31de4a6cc01957982e_@@QEAA@PEAU?$_Task_impl@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@@Z; _lambda_e284b0dc2b4a3a31de4a6cc01957982e_::_lambda_e284b0dc2b4a3a31de4a6cc01957982e_(Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>> *)
0x18004cb8c  mov     rcx, [rax]
0x18004cb8f  mov     [rsp+0B8h+var_80], rcx
0x18004cb94  lea     rax, [rsp+0B8h+var_88]
0x18004cb99  mov     [rsp+0B8h+var_50], rax
0x18004cb9e  mov     edx, 10h
0x18004cba3  lea     rcx, [rsp+0B8h+var_88]
0x18004cba8  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18004cbad  nop
0x18004cbae  mov     rcx, [rsp+0B8h+var_50]
0x18004cbb3  test    rcx, rcx
0x18004cbb6  jz      short loc_18004CBCF
0x18004cbb8  mov     rax, [rcx]
0x18004cbbb  lea     rdx, [rsp+0B8h+var_88]
0x18004cbc0  cmp     rcx, rdx
0x18004cbc3  setnz   dl
0x18004cbc6  mov     rax, [rax+20h]
0x18004cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbcf  mov     al, 1
0x18004cbd1  jmp     short loc_18004CBDE
0x18004cbd3  mov     rcx, rsi; _Mtx_t
0x18004cbd6  call    cs:__imp__Mtx_unlock
0x18004cbdc  xor     al, al
0x18004cbde  mov     rcx, [rsp+0B8h+var_48]
0x18004cbe3  xor     rcx, rsp; StackCookie
0x18004cbe6  call    __security_check_cookie
0x18004cbeb  add     rsp, 88h
0x18004cbf2  pop     r14
0x18004cbf4  pop     r12
0x18004cbf6  pop     rdi
0x18004cbf7  pop     rsi
0x18004cbf8  pop     rbp
0x18004cbf9  pop     rbx
0x18004cbfa  retn
```

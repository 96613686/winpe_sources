# Concurrency::details::_Task_impl<wil::cloud_store_save_result>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18004cfb0`
- end: `0x18004d16b`
- name: `?_CancelAndRunContinuations@?$_Task_impl@Vcloud_store_save_result@wil@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
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
- `0x18004cfb0`
- `0x18004f0b4`
- `0x18004fac4`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d066`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d066`
- `msvcp_win!_Mtx_unlock` at `0x18004d070`
- `msvcp_win!_Mtx_unlock` at `0x18004d0cd`
- `msvcp_win!_Mtx_unlock` at `0x18004d146`
- `msvcp_win!_Mtx_unlock` at `0x18004d070`
- `msvcp_win!_Mtx_unlock` at `0x18004d0cd`
- `msvcp_win!_Mtx_unlock` at `0x18004d146`
- `msvcp_win!_Cnd_broadcast` at `0x18004d0c3`
- `msvcp_win!_Cnd_broadcast` at `0x18004d0c3`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<wil::cloud_store_save_result>::_CancelAndRunContinuations(
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
      if ( *(_QWORD *)(a1 + 440) )
        std::_Func_class<void,>::operator()(a1 + 384);
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
      v15[0] = &std::_Func_impl_no_alloc<_lambda_db1e06f0fa5be6b0af8d780c8ceb30d6_,void,>::`vftable';
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
0x18004cfb0  push    rbx
0x18004cfb2  push    rbp
0x18004cfb3  push    rsi
0x18004cfb4  push    rdi
0x18004cfb5  push    r12
0x18004cfb7  push    r14
0x18004cfb9  sub     rsp, 88h
0x18004cfc0  mov     rax, cs:__security_cookie
0x18004cfc7  xor     rax, rsp
0x18004cfca  mov     [rsp+0B8h+var_48], rax
0x18004cfcf  mov     bl, r8b
0x18004cfd2  mov     bpl, dl
0x18004cfd5  mov     rdi, rcx
0x18004cfd8  mov     r14, [rsp+0B8h+arg_20]
0x18004cfe0  lea     rsi, [rcx+20h]
0x18004cfe4  mov     [rsp+0B8h+var_98], rsi
0x18004cfe9  mov     rcx, rsi; this
0x18004cfec  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004cff1  nop
0x18004cff2  mov     r12d, 2
0x18004cff8  mov     eax, [rdi+8]
0x18004cffb  test    bl, bl
0x18004cffd  jz      short loc_18004D016
0x18004cfff  cmp     eax, 4
0x18004d002  jz      loc_18004D143
0x18004d008  lea     rcx, [rdi+10h]
0x18004d00c  mov     rdx, r14
0x18004d00f  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x18004d014  jmp     short loc_18004D03C
0x18004d016  cmp     eax, 3
0x18004d019  jz      loc_18004D143
0x18004d01f  mov     eax, [rdi+8]
0x18004d022  cmp     eax, 4
0x18004d025  jz      loc_18004D143
0x18004d02b  mov     eax, [rdi+8]
0x18004d02e  cmp     eax, r12d
0x18004d031  jnz     short loc_18004D03C
0x18004d033  test    bpl, bpl
0x18004d036  jz      loc_18004D143
0x18004d03c  test    bpl, bpl
0x18004d03f  jz      short loc_18004D04F
0x18004d041  mov     dword ptr [rdi+8], 4
0x18004d048  mov     ebx, 1
0x18004d04d  jmp     short loc_18004D06D
0x18004d04f  mov     eax, [rdi+8]
0x18004d052  xor     ebx, ebx
0x18004d054  cmp     eax, 1
0x18004d057  cmovz   ebx, r12d
0x18004d05b  mov     [rdi+8], r12d
0x18004d05f  lea     rcx, [rdi+160h]
0x18004d066  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18004d06c  nop
0x18004d06d  mov     rcx, rsi; _Mtx_t
0x18004d070  call    cs:__imp__Mtx_unlock
0x18004d076  sub     ebx, 1
0x18004d079  jz      short loc_18004D0A0
0x18004d07b  cmp     ebx, 1
0x18004d07e  jnz     loc_18004D13F
0x18004d084  lea     rcx, [rdi+180h]
0x18004d08b  cmp     qword ptr [rcx+38h], 0
0x18004d090  jz      loc_18004D13F
0x18004d096  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18004d09b  jmp     loc_18004D13F
0x18004d0a0  lea     rbx, [rdi+88h]
0x18004d0a7  lea     rcx, [rbx+48h]; this
0x18004d0ab  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004d0b0  cmp     [rbx+0B0h], r12d
0x18004d0b7  jge     short loc_18004D0C0
0x18004d0b9  mov     [rbx+0B0h], r12d
0x18004d0c0  mov     rcx, rbx; _Cnd_t
0x18004d0c3  call    cs:__imp__Cnd_broadcast
0x18004d0c9  lea     rcx, [rbx+48h]; _Mtx_t
0x18004d0cd  call    cs:__imp__Mtx_unlock
0x18004d0d3  cmp     qword ptr [rdi+70h], 0
0x18004d0d8  jz      short loc_18004D13F
0x18004d0da  mov     [rsp+0B8h+var_50], 0
0x18004d0e3  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_db1e06f0fa5be6b0af8d780c8ceb30d6_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_db1e06f0fa5be6b0af8d780c8ceb30d6_,void,>::`vftable'
0x18004d0ea  mov     [rsp+0B8h+var_88], rax
0x18004d0ef  mov     rdx, rdi
0x18004d0f2  lea     rcx, [rsp+0B8h+var_98]
0x18004d0f7  call    ??0_lambda_e284b0dc2b4a3a31de4a6cc01957982e_@@QEAA@PEAU?$_Task_impl@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@@Z; _lambda_e284b0dc2b4a3a31de4a6cc01957982e_::_lambda_e284b0dc2b4a3a31de4a6cc01957982e_(Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>> *)
0x18004d0fc  mov     rcx, [rax]
0x18004d0ff  mov     [rsp+0B8h+var_80], rcx
0x18004d104  lea     rax, [rsp+0B8h+var_88]
0x18004d109  mov     [rsp+0B8h+var_50], rax
0x18004d10e  mov     edx, 10h
0x18004d113  lea     rcx, [rsp+0B8h+var_88]
0x18004d118  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18004d11d  nop
0x18004d11e  mov     rcx, [rsp+0B8h+var_50]
0x18004d123  test    rcx, rcx
0x18004d126  jz      short loc_18004D13F
0x18004d128  mov     rax, [rcx]
0x18004d12b  lea     rdx, [rsp+0B8h+var_88]
0x18004d130  cmp     rcx, rdx
0x18004d133  setnz   dl
0x18004d136  mov     rax, [rax+20h]
0x18004d13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d13f  mov     al, 1
0x18004d141  jmp     short loc_18004D14E
0x18004d143  mov     rcx, rsi; _Mtx_t
0x18004d146  call    cs:__imp__Mtx_unlock
0x18004d14c  xor     al, al
0x18004d14e  mov     rcx, [rsp+0B8h+var_48]
0x18004d153  xor     rcx, rsp; StackCookie
0x18004d156  call    __security_check_cookie
0x18004d15b  add     rsp, 88h
0x18004d162  pop     r14
0x18004d164  pop     r12
0x18004d166  pop     rdi
0x18004d167  pop     rsi
0x18004d168  pop     rbp
0x18004d169  pop     rbx
0x18004d16a  retn
```

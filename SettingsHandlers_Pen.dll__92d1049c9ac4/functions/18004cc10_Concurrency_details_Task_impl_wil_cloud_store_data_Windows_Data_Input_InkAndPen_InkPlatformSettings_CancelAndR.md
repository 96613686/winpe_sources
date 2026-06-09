# Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18004cc10`
- end: `0x18004cdcb`
- name: `?_CancelAndRunContinuations@?$_Task_impl@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x1800030e0`
- `0x1800047ec`
- `0x180049a60`
- `0x18004aba0`
- `0x18004cc10`
- `0x18004f0b4`
- `0x18004fac4`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004ccc6`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004ccc6`
- `msvcp_win!_Mtx_unlock` at `0x18004ccd0`
- `msvcp_win!_Mtx_unlock` at `0x18004cd2d`
- `msvcp_win!_Mtx_unlock` at `0x18004cda6`
- `msvcp_win!_Mtx_unlock` at `0x18004ccd0`
- `msvcp_win!_Mtx_unlock` at `0x18004cd2d`
- `msvcp_win!_Mtx_unlock` at `0x18004cda6`
- `msvcp_win!_Cnd_broadcast` at `0x18004cd23`
- `msvcp_win!_Cnd_broadcast` at `0x18004cd23`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_CancelAndRunContinuations(
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
      if ( *(_QWORD *)(a1 + 528) )
        std::_Func_class<void,>::operator()(a1 + 472);
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
      v15[0] = &std::_Func_impl_no_alloc<_lambda_e284b0dc2b4a3a31de4a6cc01957982e_,void,>::`vftable';
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
0x18004cc10  push    rbx
0x18004cc12  push    rbp
0x18004cc13  push    rsi
0x18004cc14  push    rdi
0x18004cc15  push    r12
0x18004cc17  push    r14
0x18004cc19  sub     rsp, 88h
0x18004cc20  mov     rax, cs:__security_cookie
0x18004cc27  xor     rax, rsp
0x18004cc2a  mov     [rsp+0B8h+var_48], rax
0x18004cc2f  mov     bl, r8b
0x18004cc32  mov     bpl, dl
0x18004cc35  mov     rdi, rcx
0x18004cc38  mov     r14, [rsp+0B8h+arg_20]
0x18004cc40  lea     rsi, [rcx+20h]
0x18004cc44  mov     [rsp+0B8h+var_98], rsi
0x18004cc49  mov     rcx, rsi; this
0x18004cc4c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004cc51  nop
0x18004cc52  mov     r12d, 2
0x18004cc58  mov     eax, [rdi+8]
0x18004cc5b  test    bl, bl
0x18004cc5d  jz      short loc_18004CC76
0x18004cc5f  cmp     eax, 4
0x18004cc62  jz      loc_18004CDA3
0x18004cc68  lea     rcx, [rdi+10h]
0x18004cc6c  mov     rdx, r14
0x18004cc6f  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x18004cc74  jmp     short loc_18004CC9C
0x18004cc76  cmp     eax, 3
0x18004cc79  jz      loc_18004CDA3
0x18004cc7f  mov     eax, [rdi+8]
0x18004cc82  cmp     eax, 4
0x18004cc85  jz      loc_18004CDA3
0x18004cc8b  mov     eax, [rdi+8]
0x18004cc8e  cmp     eax, r12d
0x18004cc91  jnz     short loc_18004CC9C
0x18004cc93  test    bpl, bpl
0x18004cc96  jz      loc_18004CDA3
0x18004cc9c  test    bpl, bpl
0x18004cc9f  jz      short loc_18004CCAF
0x18004cca1  mov     dword ptr [rdi+8], 4
0x18004cca8  mov     ebx, 1
0x18004ccad  jmp     short loc_18004CCCD
0x18004ccaf  mov     eax, [rdi+8]
0x18004ccb2  xor     ebx, ebx
0x18004ccb4  cmp     eax, 1
0x18004ccb7  cmovz   ebx, r12d
0x18004ccbb  mov     [rdi+8], r12d
0x18004ccbf  lea     rcx, [rdi+160h]
0x18004ccc6  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18004cccc  nop
0x18004cccd  mov     rcx, rsi; _Mtx_t
0x18004ccd0  call    cs:__imp__Mtx_unlock
0x18004ccd6  sub     ebx, 1
0x18004ccd9  jz      short loc_18004CD00
0x18004ccdb  cmp     ebx, 1
0x18004ccde  jnz     loc_18004CD9F
0x18004cce4  lea     rcx, [rdi+1D8h]
0x18004cceb  cmp     qword ptr [rcx+38h], 0
0x18004ccf0  jz      loc_18004CD9F
0x18004ccf6  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18004ccfb  jmp     loc_18004CD9F
0x18004cd00  lea     rbx, [rdi+88h]
0x18004cd07  lea     rcx, [rbx+48h]; this
0x18004cd0b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004cd10  cmp     [rbx+0B0h], r12d
0x18004cd17  jge     short loc_18004CD20
0x18004cd19  mov     [rbx+0B0h], r12d
0x18004cd20  mov     rcx, rbx; _Cnd_t
0x18004cd23  call    cs:__imp__Cnd_broadcast
0x18004cd29  lea     rcx, [rbx+48h]; _Mtx_t
0x18004cd2d  call    cs:__imp__Mtx_unlock
0x18004cd33  cmp     qword ptr [rdi+70h], 0
0x18004cd38  jz      short loc_18004CD9F
0x18004cd3a  mov     [rsp+0B8h+var_50], 0
0x18004cd43  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e284b0dc2b4a3a31de4a6cc01957982e_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e284b0dc2b4a3a31de4a6cc01957982e_,void,>::`vftable'
0x18004cd4a  mov     [rsp+0B8h+var_88], rax
0x18004cd4f  mov     rdx, rdi
0x18004cd52  lea     rcx, [rsp+0B8h+var_98]
0x18004cd57  call    ??0_lambda_e284b0dc2b4a3a31de4a6cc01957982e_@@QEAA@PEAU?$_Task_impl@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@@Z; _lambda_e284b0dc2b4a3a31de4a6cc01957982e_::_lambda_e284b0dc2b4a3a31de4a6cc01957982e_(Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>> *)
0x18004cd5c  mov     rcx, [rax]
0x18004cd5f  mov     [rsp+0B8h+var_80], rcx
0x18004cd64  lea     rax, [rsp+0B8h+var_88]
0x18004cd69  mov     [rsp+0B8h+var_50], rax
0x18004cd6e  mov     edx, 10h
0x18004cd73  lea     rcx, [rsp+0B8h+var_88]
0x18004cd78  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18004cd7d  nop
0x18004cd7e  mov     rcx, [rsp+0B8h+var_50]
0x18004cd83  test    rcx, rcx
0x18004cd86  jz      short loc_18004CD9F
0x18004cd88  mov     rax, [rcx]
0x18004cd8b  lea     rdx, [rsp+0B8h+var_88]
0x18004cd90  cmp     rcx, rdx
0x18004cd93  setnz   dl
0x18004cd96  mov     rax, [rax+20h]
0x18004cd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd9f  mov     al, 1
0x18004cda1  jmp     short loc_18004CDAE
0x18004cda3  mov     rcx, rsi; _Mtx_t
0x18004cda6  call    cs:__imp__Mtx_unlock
0x18004cdac  xor     al, al
0x18004cdae  mov     rcx, [rsp+0B8h+var_48]
0x18004cdb3  xor     rcx, rsp; StackCookie
0x18004cdb6  call    __security_check_cookie
0x18004cdbb  add     rsp, 88h
0x18004cdc2  pop     r14
0x18004cdc4  pop     r12
0x18004cdc6  pop     rdi
0x18004cdc7  pop     rsi
0x18004cdc8  pop     rbp
0x18004cdc9  pop     rbx
0x18004cdca  retn
```

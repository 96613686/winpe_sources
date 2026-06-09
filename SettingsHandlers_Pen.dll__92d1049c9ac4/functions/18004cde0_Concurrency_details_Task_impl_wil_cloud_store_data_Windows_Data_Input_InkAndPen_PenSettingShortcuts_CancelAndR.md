# Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18004cde0`
- end: `0x18004cf9b`
- name: `?_CancelAndRunContinuations@?$_Task_impl@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
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
- `0x18004cde0`
- `0x18004f0b4`
- `0x18004fac4`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004ce96`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004ce96`
- `msvcp_win!_Mtx_unlock` at `0x18004cea0`
- `msvcp_win!_Mtx_unlock` at `0x18004cefd`
- `msvcp_win!_Mtx_unlock` at `0x18004cf76`
- `msvcp_win!_Mtx_unlock` at `0x18004cea0`
- `msvcp_win!_Mtx_unlock` at `0x18004cefd`
- `msvcp_win!_Mtx_unlock` at `0x18004cf76`
- `msvcp_win!_Cnd_broadcast` at `0x18004cef3`
- `msvcp_win!_Cnd_broadcast` at `0x18004cef3`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_CancelAndRunContinuations(
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
      if ( *(_QWORD *)(a1 + 648) )
        std::_Func_class<void,>::operator()(a1 + 592);
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
      v15[0] = &std::_Func_impl_no_alloc<_lambda_4793ec9528f7f90d183b68d98353cb7b_,void,>::`vftable';
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
0x18004cde0  push    rbx
0x18004cde2  push    rbp
0x18004cde3  push    rsi
0x18004cde4  push    rdi
0x18004cde5  push    r12
0x18004cde7  push    r14
0x18004cde9  sub     rsp, 88h
0x18004cdf0  mov     rax, cs:__security_cookie
0x18004cdf7  xor     rax, rsp
0x18004cdfa  mov     [rsp+0B8h+var_48], rax
0x18004cdff  mov     bl, r8b
0x18004ce02  mov     bpl, dl
0x18004ce05  mov     rdi, rcx
0x18004ce08  mov     r14, [rsp+0B8h+arg_20]
0x18004ce10  lea     rsi, [rcx+20h]
0x18004ce14  mov     [rsp+0B8h+var_98], rsi
0x18004ce19  mov     rcx, rsi; this
0x18004ce1c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004ce21  nop
0x18004ce22  mov     r12d, 2
0x18004ce28  mov     eax, [rdi+8]
0x18004ce2b  test    bl, bl
0x18004ce2d  jz      short loc_18004CE46
0x18004ce2f  cmp     eax, 4
0x18004ce32  jz      loc_18004CF73
0x18004ce38  lea     rcx, [rdi+10h]
0x18004ce3c  mov     rdx, r14
0x18004ce3f  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x18004ce44  jmp     short loc_18004CE6C
0x18004ce46  cmp     eax, 3
0x18004ce49  jz      loc_18004CF73
0x18004ce4f  mov     eax, [rdi+8]
0x18004ce52  cmp     eax, 4
0x18004ce55  jz      loc_18004CF73
0x18004ce5b  mov     eax, [rdi+8]
0x18004ce5e  cmp     eax, r12d
0x18004ce61  jnz     short loc_18004CE6C
0x18004ce63  test    bpl, bpl
0x18004ce66  jz      loc_18004CF73
0x18004ce6c  test    bpl, bpl
0x18004ce6f  jz      short loc_18004CE7F
0x18004ce71  mov     dword ptr [rdi+8], 4
0x18004ce78  mov     ebx, 1
0x18004ce7d  jmp     short loc_18004CE9D
0x18004ce7f  mov     eax, [rdi+8]
0x18004ce82  xor     ebx, ebx
0x18004ce84  cmp     eax, 1
0x18004ce87  cmovz   ebx, r12d
0x18004ce8b  mov     [rdi+8], r12d
0x18004ce8f  lea     rcx, [rdi+160h]
0x18004ce96  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18004ce9c  nop
0x18004ce9d  mov     rcx, rsi; _Mtx_t
0x18004cea0  call    cs:__imp__Mtx_unlock
0x18004cea6  sub     ebx, 1
0x18004cea9  jz      short loc_18004CED0
0x18004ceab  cmp     ebx, 1
0x18004ceae  jnz     loc_18004CF6F
0x18004ceb4  lea     rcx, [rdi+250h]
0x18004cebb  cmp     qword ptr [rcx+38h], 0
0x18004cec0  jz      loc_18004CF6F
0x18004cec6  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18004cecb  jmp     loc_18004CF6F
0x18004ced0  lea     rbx, [rdi+88h]
0x18004ced7  lea     rcx, [rbx+48h]; this
0x18004cedb  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004cee0  cmp     [rbx+0B0h], r12d
0x18004cee7  jge     short loc_18004CEF0
0x18004cee9  mov     [rbx+0B0h], r12d
0x18004cef0  mov     rcx, rbx; _Cnd_t
0x18004cef3  call    cs:__imp__Cnd_broadcast
0x18004cef9  lea     rcx, [rbx+48h]; _Mtx_t
0x18004cefd  call    cs:__imp__Mtx_unlock
0x18004cf03  cmp     qword ptr [rdi+70h], 0
0x18004cf08  jz      short loc_18004CF6F
0x18004cf0a  mov     [rsp+0B8h+var_50], 0
0x18004cf13  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4793ec9528f7f90d183b68d98353cb7b_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4793ec9528f7f90d183b68d98353cb7b_,void,>::`vftable'
0x18004cf1a  mov     [rsp+0B8h+var_88], rax
0x18004cf1f  mov     rdx, rdi
0x18004cf22  lea     rcx, [rsp+0B8h+var_98]
0x18004cf27  call    ??0_lambda_e284b0dc2b4a3a31de4a6cc01957982e_@@QEAA@PEAU?$_Task_impl@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@@Z; _lambda_e284b0dc2b4a3a31de4a6cc01957982e_::_lambda_e284b0dc2b4a3a31de4a6cc01957982e_(Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>> *)
0x18004cf2c  mov     rcx, [rax]
0x18004cf2f  mov     [rsp+0B8h+var_80], rcx
0x18004cf34  lea     rax, [rsp+0B8h+var_88]
0x18004cf39  mov     [rsp+0B8h+var_50], rax
0x18004cf3e  mov     edx, 10h
0x18004cf43  lea     rcx, [rsp+0B8h+var_88]
0x18004cf48  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18004cf4d  nop
0x18004cf4e  mov     rcx, [rsp+0B8h+var_50]
0x18004cf53  test    rcx, rcx
0x18004cf56  jz      short loc_18004CF6F
0x18004cf58  mov     rax, [rcx]
0x18004cf5b  lea     rdx, [rsp+0B8h+var_88]
0x18004cf60  cmp     rcx, rdx
0x18004cf63  setnz   dl
0x18004cf66  mov     rax, [rax+20h]
0x18004cf6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf6f  mov     al, 1
0x18004cf71  jmp     short loc_18004CF7E
0x18004cf73  mov     rcx, rsi; _Mtx_t
0x18004cf76  call    cs:__imp__Mtx_unlock
0x18004cf7c  xor     al, al
0x18004cf7e  mov     rcx, [rsp+0B8h+var_48]
0x18004cf83  xor     rcx, rsp; StackCookie
0x18004cf86  call    __security_check_cookie
0x18004cf8b  add     rsp, 88h
0x18004cf92  pop     r14
0x18004cf94  pop     r12
0x18004cf96  pop     rdi
0x18004cf97  pop     rsi
0x18004cf98  pop     rbp
0x18004cf99  pop     rbx
0x18004cf9a  retn
```

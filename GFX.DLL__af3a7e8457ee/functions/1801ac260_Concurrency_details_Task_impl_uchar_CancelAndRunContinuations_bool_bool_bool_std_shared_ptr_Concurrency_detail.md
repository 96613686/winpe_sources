# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1801ac260`
- end: `0x1801ac42d`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180056ee0`
- `0x1800795a0`
- `0x1800d7dd0`
- `0x1800f4cd4`
- `0x1800fc238`
- `0x1801ac260`
- `0x1801ada98`

## import_xrefs

- `MSVCP140!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801ac347`
- `MSVCP140!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801ac347`
- `MSVCP140!_Cnd_broadcast` at `0x1801ac3a5`
- `MSVCP140!_Cnd_broadcast` at `0x1801ac3a5`
- `MSVCP140!_Mtx_unlock` at `0x1801ac359`
- `MSVCP140!_Mtx_unlock` at `0x1801ac3af`
- `MSVCP140!_Mtx_unlock` at `0x1801ac3f8`
- `MSVCP140!_Mtx_unlock` at `0x1801ac359`
- `MSVCP140!_Mtx_unlock` at `0x1801ac3af`
- `MSVCP140!_Mtx_unlock` at `0x1801ac3f8`

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
  struct _Mtx_internal_imp_t *v8; // rbx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // ebp
  int v13; // edi
  int v14; // ebp
  _QWORD v16[4]; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v17[8]; // [rsp+40h] [rbp-68h] BYREF

  v8 = (struct _Mtx_internal_imp_t *)(a1 + 32);
  v16[2] = a1 + 32;
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
      v16[0] = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 16) = *a5;
      v16[1] = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v11;
      std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(v16);
      goto LABEL_10;
    }
LABEL_23:
    _Mtx_unlock(v8);
    return 0;
  }
  if ( v9 == 3 || *(_DWORD *)(a1 + 8) == 4 || *(_DWORD *)(a1 + 8) == 2 && !a2 )
    goto LABEL_23;
LABEL_10:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v12 = 1;
  }
  else
  {
    v13 = *(_DWORD *)(a1 + 8);
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
    v12 = 0;
    if ( v13 == 1 )
      v12 = 2;
  }
  _Mtx_unlock(v8);
  v14 = v12 - 1;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      if ( *(_QWORD *)(a1 + 432) )
        std::_Func_class<void,>::operator()();
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
      v17[7] = v17;
      Concurrency::details::_ScheduleFuncWithAutoInline(v17, 16);
      std::_Func_class<void,>::_Tidy(v17);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1801ac260  mov     [rsp+arg_8], rbx
0x1801ac265  mov     [rsp+arg_10], rbp
0x1801ac26a  mov     [rsp+arg_18], rsi
0x1801ac26f  push    rdi
0x1801ac270  push    r14
0x1801ac272  push    r15
0x1801ac274  sub     rsp, 90h
0x1801ac27b  mov     rax, cs:__security_cookie
0x1801ac282  xor     rax, rsp
0x1801ac285  mov     [rsp+0A8h+var_28], rax
0x1801ac28d  mov     dil, r8b
0x1801ac290  mov     bpl, dl
0x1801ac293  mov     rsi, rcx
0x1801ac296  mov     r14, [rsp+0A8h+arg_20]
0x1801ac29e  lea     rbx, [rcx+20h]
0x1801ac2a2  mov     [rsp+0A8h+var_78], rbx
0x1801ac2a7  mov     rcx, rbx; this
0x1801ac2aa  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801ac2af  mov     r15d, 2
0x1801ac2b5  mov     eax, [rsi+8]
0x1801ac2b8  test    dil, dil
0x1801ac2bb  jz      short loc_1801AC300
0x1801ac2bd  cmp     eax, 4
0x1801ac2c0  jz      loc_1801AC3F5
0x1801ac2c6  mov     rax, [r14+8]
0x1801ac2ca  test    rax, rax
0x1801ac2cd  jz      short loc_1801AC2D3
0x1801ac2cf  lock inc dword ptr [rax+8]
0x1801ac2d3  mov     rcx, [r14+8]
0x1801ac2d7  mov     rax, [rsi+10h]
0x1801ac2db  mov     [rsp+0A8h+var_88], rax
0x1801ac2e0  mov     rax, [r14]
0x1801ac2e3  mov     [rsi+10h], rax
0x1801ac2e7  mov     rax, [rsi+18h]
0x1801ac2eb  mov     [rsp+0A8h+var_80], rax
0x1801ac2f0  mov     [rsi+18h], rcx
0x1801ac2f4  lea     rcx, [rsp+0A8h+var_88]
0x1801ac2f9  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801ac2fe  jmp     short loc_1801AC326
0x1801ac300  cmp     eax, 3
0x1801ac303  jz      loc_1801AC3F5
0x1801ac309  mov     eax, [rsi+8]
0x1801ac30c  cmp     eax, 4
0x1801ac30f  jz      loc_1801AC3F5
0x1801ac315  mov     eax, [rsi+8]
0x1801ac318  cmp     eax, r15d
0x1801ac31b  jnz     short loc_1801AC326
0x1801ac31d  test    bpl, bpl
0x1801ac320  jz      loc_1801AC3F5
0x1801ac326  test    bpl, bpl
0x1801ac329  jz      short loc_1801AC339
0x1801ac32b  mov     dword ptr [rsi+8], 4
0x1801ac332  mov     ebp, 1
0x1801ac337  jmp     short loc_1801AC356
0x1801ac339  mov     edi, [rsi+8]
0x1801ac33c  mov     [rsi+8], r15d
0x1801ac340  lea     rcx, [rsi+160h]
0x1801ac347  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x1801ac34d  xor     ebp, ebp
0x1801ac34f  cmp     edi, 1
0x1801ac352  cmovz   ebp, r15d
0x1801ac356  mov     rcx, rbx; _Mtx_t
0x1801ac359  call    cs:__imp__Mtx_unlock
0x1801ac35f  sub     ebp, 1
0x1801ac362  jz      short loc_1801AC382
0x1801ac364  cmp     ebp, 1
0x1801ac367  jnz     loc_1801AC3F1
0x1801ac36d  lea     rcx, [rsi+178h]
0x1801ac374  cmp     qword ptr [rcx+38h], 0
0x1801ac379  jz      short loc_1801AC3F1
0x1801ac37b  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1801ac380  jmp     short loc_1801AC3F1
0x1801ac382  lea     rdi, [rsi+88h]
0x1801ac389  lea     rcx, [rdi+48h]; this
0x1801ac38d  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801ac392  cmp     [rdi+0B0h], r15d
0x1801ac399  jge     short loc_1801AC3A2
0x1801ac39b  mov     [rdi+0B0h], r15d
0x1801ac3a2  mov     rcx, rdi; _Cnd_t
0x1801ac3a5  call    cs:__imp__Cnd_broadcast
0x1801ac3ab  lea     rcx, [rdi+48h]; _Mtx_t
0x1801ac3af  call    cs:__imp__Mtx_unlock
0x1801ac3b5  cmp     qword ptr [rsi+70h], 0
0x1801ac3ba  jz      short loc_1801AC3F1
0x1801ac3bc  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?CC@??_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)'::`34'::_lambda_1_,void,>::`vftable'
0x1801ac3c3  mov     [rsp+0A8h+var_68], rcx
0x1801ac3c8  mov     [rsp+0A8h+var_60], rsi
0x1801ac3cd  lea     rcx, [rsp+0A8h+var_68]
0x1801ac3d2  mov     [rsp+0A8h+var_30], rcx
0x1801ac3d7  mov     edx, 10h
0x1801ac3dc  lea     rcx, [rsp+0A8h+var_68]
0x1801ac3e1  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x1801ac3e6  nop
0x1801ac3e7  lea     rcx, [rsp+0A8h+var_68]
0x1801ac3ec  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1801ac3f1  mov     al, 1
0x1801ac3f3  jmp     short loc_1801AC400
0x1801ac3f5  mov     rcx, rbx; _Mtx_t
0x1801ac3f8  call    cs:__imp__Mtx_unlock
0x1801ac3fe  xor     al, al
0x1801ac400  mov     rcx, [rsp+0A8h+var_28]
0x1801ac408  xor     rcx, rsp; StackCookie
0x1801ac40b  call    __security_check_cookie
0x1801ac410  lea     r11, [rsp+0A8h+var_18]
0x1801ac418  mov     rbx, [r11+28h]
0x1801ac41c  mov     rbp, [r11+30h]
0x1801ac420  mov     rsi, [r11+38h]
0x1801ac424  mov     rsp, r11
0x1801ac427  pop     r15
0x1801ac429  pop     r14
0x1801ac42b  pop     rdi
0x1801ac42c  retn
```

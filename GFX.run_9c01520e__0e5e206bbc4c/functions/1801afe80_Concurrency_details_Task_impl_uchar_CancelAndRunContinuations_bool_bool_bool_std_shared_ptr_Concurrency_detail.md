# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1801afe80`
- end: `0x1801b004d`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800578b0`
- `0x18005a2d8`
- `0x18005b714`
- `0x180076df0`
- `0x180096050`
- `0x1801afe80`
- `0x1801b16b8`

## import_xrefs

- `MSVCP140!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801aff67`
- `MSVCP140!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801aff67`
- `MSVCP140!_Cnd_broadcast` at `0x1801affc5`
- `MSVCP140!_Cnd_broadcast` at `0x1801affc5`
- `MSVCP140!_Mtx_unlock` at `0x1801aff79`
- `MSVCP140!_Mtx_unlock` at `0x1801affcf`
- `MSVCP140!_Mtx_unlock` at `0x1801b0018`
- `MSVCP140!_Mtx_unlock` at `0x1801aff79`
- `MSVCP140!_Mtx_unlock` at `0x1801affcf`
- `MSVCP140!_Mtx_unlock` at `0x1801b0018`

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
0x1801afe80  mov     [rsp+arg_8], rbx
0x1801afe85  mov     [rsp+arg_10], rbp
0x1801afe8a  mov     [rsp+arg_18], rsi
0x1801afe8f  push    rdi
0x1801afe90  push    r14
0x1801afe92  push    r15
0x1801afe94  sub     rsp, 90h
0x1801afe9b  mov     rax, cs:__security_cookie
0x1801afea2  xor     rax, rsp
0x1801afea5  mov     [rsp+0A8h+var_28], rax
0x1801afead  mov     dil, r8b
0x1801afeb0  mov     bpl, dl
0x1801afeb3  mov     rsi, rcx
0x1801afeb6  mov     r14, [rsp+0A8h+arg_20]
0x1801afebe  lea     rbx, [rcx+20h]
0x1801afec2  mov     [rsp+0A8h+var_78], rbx
0x1801afec7  mov     rcx, rbx; this
0x1801afeca  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801afecf  mov     r15d, 2
0x1801afed5  mov     eax, [rsi+8]
0x1801afed8  test    dil, dil
0x1801afedb  jz      short loc_1801AFF20
0x1801afedd  cmp     eax, 4
0x1801afee0  jz      loc_1801B0015
0x1801afee6  mov     rax, [r14+8]
0x1801afeea  test    rax, rax
0x1801afeed  jz      short loc_1801AFEF3
0x1801afeef  lock inc dword ptr [rax+8]
0x1801afef3  mov     rcx, [r14+8]
0x1801afef7  mov     rax, [rsi+10h]
0x1801afefb  mov     [rsp+0A8h+var_88], rax
0x1801aff00  mov     rax, [r14]
0x1801aff03  mov     [rsi+10h], rax
0x1801aff07  mov     rax, [rsi+18h]
0x1801aff0b  mov     [rsp+0A8h+var_80], rax
0x1801aff10  mov     [rsi+18h], rcx
0x1801aff14  lea     rcx, [rsp+0A8h+var_88]
0x1801aff19  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801aff1e  jmp     short loc_1801AFF46
0x1801aff20  cmp     eax, 3
0x1801aff23  jz      loc_1801B0015
0x1801aff29  mov     eax, [rsi+8]
0x1801aff2c  cmp     eax, 4
0x1801aff2f  jz      loc_1801B0015
0x1801aff35  mov     eax, [rsi+8]
0x1801aff38  cmp     eax, r15d
0x1801aff3b  jnz     short loc_1801AFF46
0x1801aff3d  test    bpl, bpl
0x1801aff40  jz      loc_1801B0015
0x1801aff46  test    bpl, bpl
0x1801aff49  jz      short loc_1801AFF59
0x1801aff4b  mov     dword ptr [rsi+8], 4
0x1801aff52  mov     ebp, 1
0x1801aff57  jmp     short loc_1801AFF76
0x1801aff59  mov     edi, [rsi+8]
0x1801aff5c  mov     [rsi+8], r15d
0x1801aff60  lea     rcx, [rsi+160h]
0x1801aff67  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x1801aff6d  xor     ebp, ebp
0x1801aff6f  cmp     edi, 1
0x1801aff72  cmovz   ebp, r15d
0x1801aff76  mov     rcx, rbx; _Mtx_t
0x1801aff79  call    cs:__imp__Mtx_unlock
0x1801aff7f  sub     ebp, 1
0x1801aff82  jz      short loc_1801AFFA2
0x1801aff84  cmp     ebp, 1
0x1801aff87  jnz     loc_1801B0011
0x1801aff8d  lea     rcx, [rsi+178h]
0x1801aff94  cmp     qword ptr [rcx+38h], 0
0x1801aff99  jz      short loc_1801B0011
0x1801aff9b  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1801affa0  jmp     short loc_1801B0011
0x1801affa2  lea     rdi, [rsi+88h]
0x1801affa9  lea     rcx, [rdi+48h]; this
0x1801affad  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801affb2  cmp     [rdi+0B0h], r15d
0x1801affb9  jge     short loc_1801AFFC2
0x1801affbb  mov     [rdi+0B0h], r15d
0x1801affc2  mov     rcx, rdi; _Cnd_t
0x1801affc5  call    cs:__imp__Cnd_broadcast
0x1801affcb  lea     rcx, [rdi+48h]; _Mtx_t
0x1801affcf  call    cs:__imp__Mtx_unlock
0x1801affd5  cmp     qword ptr [rsi+70h], 0
0x1801affda  jz      short loc_1801B0011
0x1801affdc  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?CC@??_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)'::`34'::_lambda_1_,void,>::`vftable'
0x1801affe3  mov     [rsp+0A8h+var_68], rcx
0x1801affe8  mov     [rsp+0A8h+var_60], rsi
0x1801affed  lea     rcx, [rsp+0A8h+var_68]
0x1801afff2  mov     [rsp+0A8h+var_30], rcx
0x1801afff7  mov     edx, 10h
0x1801afffc  lea     rcx, [rsp+0A8h+var_68]
0x1801b0001  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x1801b0006  nop
0x1801b0007  lea     rcx, [rsp+0A8h+var_68]
0x1801b000c  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1801b0011  mov     al, 1
0x1801b0013  jmp     short loc_1801B0020
0x1801b0015  mov     rcx, rbx; _Mtx_t
0x1801b0018  call    cs:__imp__Mtx_unlock
0x1801b001e  xor     al, al
0x1801b0020  mov     rcx, [rsp+0A8h+var_28]
0x1801b0028  xor     rcx, rsp; StackCookie
0x1801b002b  call    __security_check_cookie
0x1801b0030  lea     r11, [rsp+0A8h+var_18]
0x1801b0038  mov     rbx, [r11+28h]
0x1801b003c  mov     rbp, [r11+30h]
0x1801b0040  mov     rsi, [r11+38h]
0x1801b0044  mov     rsp, r11
0x1801b0047  pop     r15
0x1801b0049  pop     r14
0x1801b004b  pop     rdi
0x1801b004c  retn
```

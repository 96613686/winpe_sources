# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x18002e8c0`
- end: `0x18002ea9c`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800028d0`
- `0x180004e4c`
- `0x18002be78`
- `0x18002e8c0`
- `0x18002edf4`
- `0x180030178`
- `0x180031474`
- `0x18005a010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x18002e9f4`
- `msvcp_win!_Cnd_broadcast` at `0x18002e9f4`
- `msvcp_win!_Mtx_unlock` at `0x18002e9a1`
- `msvcp_win!_Mtx_unlock` at `0x18002e9fe`
- `msvcp_win!_Mtx_unlock` at `0x18002ea77`
- `msvcp_win!_Mtx_unlock` at `0x18002e9a1`
- `msvcp_win!_Mtx_unlock` at `0x18002e9fe`
- `msvcp_win!_Mtx_unlock` at `0x18002ea77`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002e997`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002e997`

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
      v18[1] = *(_QWORD *)_lambda_43d504f6f759b10c442bf5ae561285b2_::_lambda_43d504f6f759b10c442bf5ae561285b2_(&v17, a1);
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
0x18002e8c0  push    rbx
0x18002e8c2  push    rbp
0x18002e8c3  push    rsi
0x18002e8c4  push    rdi
0x18002e8c5  push    r12
0x18002e8c7  push    r14
0x18002e8c9  sub     rsp, 88h
0x18002e8d0  mov     rax, cs:__security_cookie
0x18002e8d7  xor     rax, rsp
0x18002e8da  mov     [rsp+0B8h+var_48], rax
0x18002e8df  mov     bl, r8b
0x18002e8e2  mov     bpl, dl
0x18002e8e5  mov     rdi, rcx
0x18002e8e8  mov     r14, [rsp+0B8h+arg_20]
0x18002e8f0  lea     rsi, [rcx+20h]
0x18002e8f4  mov     [rsp+0B8h+var_98], rsi
0x18002e8f9  mov     rcx, rsi; this
0x18002e8fc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002e901  nop
0x18002e902  mov     r12d, 2
0x18002e908  mov     eax, [rdi+8]
0x18002e90b  test    bl, bl
0x18002e90d  jz      short loc_18002E947
0x18002e90f  cmp     eax, 4
0x18002e912  jz      loc_18002EA74
0x18002e918  mov     rax, [r14+8]
0x18002e91c  test    rax, rax
0x18002e91f  jz      short loc_18002E925
0x18002e921  lock inc dword ptr [rax+8]
0x18002e925  mov     rcx, [r14+8]
0x18002e929  mov     rax, [r14]
0x18002e92c  mov     [rdi+10h], rax
0x18002e930  mov     rax, [rdi+18h]
0x18002e934  mov     [rdi+18h], rcx
0x18002e938  test    rax, rax
0x18002e93b  jz      short loc_18002E96D
0x18002e93d  mov     rcx, rax; this
0x18002e940  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e945  jmp     short loc_18002E96D
0x18002e947  cmp     eax, 3
0x18002e94a  jz      loc_18002EA74
0x18002e950  mov     eax, [rdi+8]
0x18002e953  cmp     eax, 4
0x18002e956  jz      loc_18002EA74
0x18002e95c  mov     eax, [rdi+8]
0x18002e95f  cmp     eax, r12d
0x18002e962  jnz     short loc_18002E96D
0x18002e964  test    bpl, bpl
0x18002e967  jz      loc_18002EA74
0x18002e96d  test    bpl, bpl
0x18002e970  jz      short loc_18002E980
0x18002e972  mov     dword ptr [rdi+8], 4
0x18002e979  mov     ebx, 1
0x18002e97e  jmp     short loc_18002E99E
0x18002e980  mov     eax, [rdi+8]
0x18002e983  xor     ebx, ebx
0x18002e985  cmp     eax, 1
0x18002e988  cmovz   ebx, r12d
0x18002e98c  mov     [rdi+8], r12d
0x18002e990  lea     rcx, [rdi+160h]
0x18002e997  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18002e99d  nop
0x18002e99e  mov     rcx, rsi; _Mtx_t
0x18002e9a1  call    cs:__imp__Mtx_unlock
0x18002e9a7  sub     ebx, 1
0x18002e9aa  jz      short loc_18002E9D1
0x18002e9ac  cmp     ebx, 1
0x18002e9af  jnz     loc_18002EA70
0x18002e9b5  lea     rcx, [rdi+178h]
0x18002e9bc  cmp     qword ptr [rcx+38h], 0
0x18002e9c1  jz      loc_18002EA70
0x18002e9c7  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002e9cc  jmp     loc_18002EA70
0x18002e9d1  lea     rbx, [rdi+88h]
0x18002e9d8  lea     rcx, [rbx+48h]; this
0x18002e9dc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002e9e1  cmp     [rbx+0B0h], r12d
0x18002e9e8  jge     short loc_18002E9F1
0x18002e9ea  mov     [rbx+0B0h], r12d
0x18002e9f1  mov     rcx, rbx; _Cnd_t
0x18002e9f4  call    cs:__imp__Cnd_broadcast
0x18002e9fa  lea     rcx, [rbx+48h]; _Mtx_t
0x18002e9fe  call    cs:__imp__Mtx_unlock
0x18002ea04  cmp     qword ptr [rdi+70h], 0
0x18002ea09  jz      short loc_18002EA70
0x18002ea0b  mov     [rsp+0B8h+var_50], 0
0x18002ea14  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x18002ea1b  mov     [rsp+0B8h+var_88], rax
0x18002ea20  mov     rdx, rdi
0x18002ea23  lea     rcx, [rsp+0B8h+var_98]
0x18002ea28  call    ??0_lambda_43d504f6f759b10c442bf5ae561285b2_@@QEAA@PEAV?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@@Z; _lambda_43d504f6f759b10c442bf5ae561285b2_::_lambda_43d504f6f759b10c442bf5ae561285b2_(SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)> *)
0x18002ea2d  mov     rcx, [rax]
0x18002ea30  mov     [rsp+0B8h+var_80], rcx
0x18002ea35  lea     rax, [rsp+0B8h+var_88]
0x18002ea3a  mov     [rsp+0B8h+var_50], rax
0x18002ea3f  mov     edx, 10h
0x18002ea44  lea     rcx, [rsp+0B8h+var_88]
0x18002ea49  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18002ea4e  nop
0x18002ea4f  mov     rcx, [rsp+0B8h+var_50]
0x18002ea54  test    rcx, rcx
0x18002ea57  jz      short loc_18002EA70
0x18002ea59  mov     rax, [rcx]
0x18002ea5c  lea     rdx, [rsp+0B8h+var_88]
0x18002ea61  cmp     rcx, rdx
0x18002ea64  setnz   dl
0x18002ea67  mov     rax, [rax+20h]
0x18002ea6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea70  mov     al, 1
0x18002ea72  jmp     short loc_18002EA7F
0x18002ea74  mov     rcx, rsi; _Mtx_t
0x18002ea77  call    cs:__imp__Mtx_unlock
0x18002ea7d  xor     al, al
0x18002ea7f  mov     rcx, [rsp+0B8h+var_48]
0x18002ea84  xor     rcx, rsp; StackCookie
0x18002ea87  call    __security_check_cookie
0x18002ea8c  add     rsp, 88h
0x18002ea93  pop     r14
0x18002ea95  pop     r12
0x18002ea97  pop     rdi
0x18002ea98  pop     rsi
0x18002ea99  pop     rbp
0x18002ea9a  pop     rbx
0x18002ea9b  retn
```

# Concurrency::task_void_::then__lambda_ff9fab94e839700dcda8ee6d193e4200___

- ea: `0x18000ee28`
- end: `0x18000ef96`
- name: `Concurrency::task_void_::then__lambda_ff9fab94e839700dcda8ee6d193e4200___`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18001b34c`

## callees

- `0x180002380`
- `0x18000c4f4`
- `0x18000da9c`
- `0x18000ee28`
- `0x18000f958`
- `0x18001030c`
- `0x180011fa4`
- `0x1800120a4`
- `0x18001c9bc`
- `0x18001cc40`
- `0x18001d584`
- `0x18001dd48`
- `0x18001e61c`
- `0x180025010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18000ef6a`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18000ef6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Concurrency::task_void_::then__lambda_ff9fab94e839700dcda8ee6d193e4200___(
        Concurrency::details::_Task_impl_base **a1,
        _QWORD *a2,
        _QWORD *a3,
        Concurrency::task_options *a4)
{
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rdx
  _QWORD *v11; // rdx
  _BYTE v13[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v15[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  _BYTE v19[80]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v20[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v21; // [rsp+108h] [rbp+8h]

  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v14);
  v14 = v9;
  *(_BYTE *)(v8 + 48) = 1;
  *(_QWORD *)(v8 + 56) = v9;
  if ( (_QWORD *)(v8 + 64) != v15 )
    std::vector<void *>::_Assign_counted_range<void * *>(v8 + 64, v15[0], (__int64)(v15[1] - v15[0]) >> 3);
  std::vector<void *>::_Tidy(v15);
  Concurrency::task_options::get_continuation_context(a4, v13);
  if ( !*a1 )
    Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v16,
    (_QWORD *)*a1 + 36);
  v18 = *(_QWORD *)(v10 + 16);
  Concurrency::details::_ThenImplOptions::_CreateOptions(
    (__int64)v19,
    (__int64)a4,
    (Concurrency::details::_RefCounter *)v13,
    &v16);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  v20[0] = off_1800264A8;
  v20[1] = *a3;
  v21 = v20;
  Concurrency::task<unsigned char>::_ThenImpl<void,std::function<void (Concurrency::task<void>)>>(
    a1,
    a2,
    (int)v20,
    (__int64)v19);
  if ( v21 )
  {
    v11 = v20;
    LOBYTE(v11) = v21 != v20;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v11);
    v21 = 0;
  }
  Concurrency::details::_ThenImplOptions::~_ThenImplOptions((Concurrency::details::_ThenImplOptions *)v19);
  Concurrency::details::_ContextCallback::_Reset((Concurrency::details::_ContextCallback *)v13);
  Concurrency::task_options::~task_options(a4);
  return a2;
}

```

## disassembly

```asm
0x18000ee28  push    rbp
0x18000ee2a  push    rbx
0x18000ee2b  push    rsi
0x18000ee2c  push    rdi
0x18000ee2d  push    r14
0x18000ee2f  lea     rbp, [rsp-20h]
0x18000ee34  sub     rsp, 120h
0x18000ee3b  mov     rax, cs:__security_cookie
0x18000ee42  xor     rax, rsp
0x18000ee45  mov     [rbp+40h+var_30], rax
0x18000ee49  mov     rbx, r9
0x18000ee4c  mov     r14, r8
0x18000ee4f  mov     rdi, rdx
0x18000ee52  mov     rsi, rcx
0x18000ee55  mov     [rsp+140h+var_118], rdx
0x18000ee5a  mov     [rsp+140h+var_118], rbx
0x18000ee5f  mov     r8, [rbp+48h]
0x18000ee63  lea     rcx, [rsp+140h+var_100]; this
0x18000ee68  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18000ee6d  mov     [rsp+140h+var_100], r8
0x18000ee72  mov     byte ptr [r9+30h], 1
0x18000ee77  mov     [r9+38h], r8
0x18000ee7b  lea     rcx, [r9+40h]
0x18000ee7f  lea     rax, [rsp+140h+var_F8]
0x18000ee84  cmp     rcx, rax
0x18000ee87  jz      short loc_18000EEA0
0x18000ee89  mov     rdx, [rsp+140h+var_F8]
0x18000ee8e  mov     r8, [rsp+140h+var_F0]
0x18000ee93  sub     r8, rdx
0x18000ee96  sar     r8, 3
0x18000ee9a  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x18000ee9f  nop
0x18000eea0  lea     rcx, [rsp+140h+var_F8]
0x18000eea5  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18000eeaa  lea     rdx, [rsp+140h+var_110]
0x18000eeaf  mov     rcx, rbx
0x18000eeb2  call    ?get_continuation_context@task_options@Concurrency@@QEBA?AVtask_continuation_context@2@XZ; Concurrency::task_options::get_continuation_context(void)
0x18000eeb7  nop
0x18000eeb8  mov     rdx, [rsi]
0x18000eebb  test    rdx, rdx
0x18000eebe  jnz     short loc_18000EEC6
0x18000eec0  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
0x18000eec6  add     rdx, 120h
0x18000eecd  lea     rcx, [rsp+140h+var_E0]
0x18000eed2  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18000eed7  mov     rcx, [rdx+10h]
0x18000eedb  mov     [rsp+140h+var_D0], rcx
0x18000eee0  lea     r9, [rsp+140h+var_E0]
0x18000eee5  lea     r8, [rsp+140h+var_110]
0x18000eeea  mov     rdx, rbx
0x18000eeed  lea     rcx, [rbp+40h+var_C0]
0x18000eef1  call    ?_CreateOptions@_ThenImplOptions@details@Concurrency@@SA?AU123@AEBVtask_options@3@AEBVtask_continuation_context@3@AEBUscheduler_ptr@3@@Z; Concurrency::details::_ThenImplOptions::_CreateOptions(Concurrency::task_options const &,Concurrency::task_continuation_context const &,Concurrency::scheduler_ptr const &)
0x18000eef6  nop
0x18000eef7  mov     rcx, [rsp+140h+var_D8]; this
0x18000eefc  test    rcx, rcx
0x18000eeff  jz      short loc_18000EF06
0x18000ef01  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ef06  lea     rax, off_1800264A8
0x18000ef0d  mov     [rbp+40h+var_70], rax
0x18000ef11  mov     rax, [r14]
0x18000ef14  mov     [rbp+40h+var_68], rax
0x18000ef18  lea     rax, [rbp+40h+var_70]
0x18000ef1c  mov     [rbp+40h+var_38], rax
0x18000ef20  lea     r9, [rbp+40h+var_C0]
0x18000ef24  lea     r8, [rbp+40h+var_70]
0x18000ef28  mov     rdx, rdi
0x18000ef2b  mov     rcx, rsi
0x18000ef2e  call    ??$_ThenImpl@XV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@@?$task@E@Concurrency@@AEBA?AV?$task@X@1@AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@AEAU_ThenImplOptions@details@1@@Z; Concurrency::task<uchar>::_ThenImpl<void,std::function<void (Concurrency::task<void>)>>(std::function<void (Concurrency::task<void>)> const &,Concurrency::details::_ThenImplOptions &)
0x18000ef33  nop
0x18000ef34  mov     rcx, [rbp+40h+var_38]
0x18000ef38  test    rcx, rcx
0x18000ef3b  jz      short loc_18000EF5B
0x18000ef3d  mov     rax, [rcx]
0x18000ef40  lea     rdx, [rbp+40h+var_70]
0x18000ef44  cmp     rcx, rdx
0x18000ef47  setnz   dl
0x18000ef4a  mov     rax, [rax+20h]
0x18000ef4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef53  mov     [rbp+40h+var_38], 0
0x18000ef5b  lea     rcx, [rbp+40h+var_C0]; this
0x18000ef5f  call    ??1_ThenImplOptions@details@Concurrency@@QEAA@XZ; Concurrency::details::_ThenImplOptions::~_ThenImplOptions(void)
0x18000ef64  nop
0x18000ef65  lea     rcx, [rsp+140h+var_110]
0x18000ef6a  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18000ef70  nop
0x18000ef71  mov     rcx, rbx; this
0x18000ef74  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x18000ef79  mov     rax, rdi
0x18000ef7c  mov     rcx, [rbp+40h+var_30]
0x18000ef80  xor     rcx, rsp; StackCookie
0x18000ef83  call    __security_check_cookie
0x18000ef88  add     rsp, 120h
0x18000ef8f  pop     r14
0x18000ef91  pop     rdi
0x18000ef92  pop     rsi
0x18000ef93  pop     rbx
0x18000ef94  pop     rbp
0x18000ef95  retn
```

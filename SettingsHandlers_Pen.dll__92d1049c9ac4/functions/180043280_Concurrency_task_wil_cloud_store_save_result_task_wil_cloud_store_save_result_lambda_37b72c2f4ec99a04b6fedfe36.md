# Concurrency::task<wil::cloud_store_save_result>::task<wil::cloud_store_save_result>(_lambda_37b72c2f4ec99a04b6fedfe365ac8865_)

- ea: `0x180043280`
- end: `0x1800433e5`
- name: `??$?0V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEAA@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004a1fc`

## callees

- `0x1800030e0`
- `0x1800037c0`
- `0x180010fc0`
- `0x18004324c`
- `0x180043280`
- `0x180047e70`
- `0x1800488c8`
- `0x180048c60`
- `0x180048e68`
- `0x180049980`
- `0x18004dadc`
- `0x18004ed78`
- `0x18004f160`
- `0x18004f1b8`
- `0x18004f6c8`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180043355`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180043355`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Concurrency::task<wil::cloud_store_save_result>::task<wil::cloud_store_save_result>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 scheduler; // rax
  Concurrency::details::_RefCounter *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 i; // rcx
  __int64 v9; // rdi
  _QWORD *v11; // [rsp+20h] [rbp-69h]
  __int64 v12; // [rsp+28h] [rbp-61h] BYREF
  _BYTE v13[24]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD *v14; // [rsp+48h] [rbp-41h]
  _BYTE v15[24]; // [rsp+50h] [rbp-39h] BYREF
  Concurrency::details::_RefCounter *v16; // [rsp+68h] [rbp-21h]
  __int64 v17; // [rsp+B0h] [rbp+27h]

  v14 = a1;
  v17 = a2;
  *a1 = 0;
  a1[1] = 0;
  Concurrency::task_options::task_options((Concurrency::task_options *)v15);
  scheduler = Concurrency::task_options::get_scheduler(v15, &v12);
  v5 = v16;
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)v16 + 2);
  v6 = (__int64)v5;
  if ( !v5 )
    v6 = 2;
  Concurrency::task<wil::cloud_store_save_result>::_CreateImpl(a1, v6, scheduler);
  if ( v5 )
    Concurrency::details::_RefCounter::_Release(v5);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v12);
  v12 = v7;
  Concurrency::task<wil::cloud_store_save_result>::_SetTaskCreationCallstack(a1, &v12);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>(v13);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*a1 + i + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352LL), 0);
  v9 = *a1;
  v11 = operator new(0x1D8u);
  *v11 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v11 + 1,
    a1);
  *v11 = &Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  _lambda_37b72c2f4ec99a04b6fedfe365ac8865_::_lambda_37b72c2f4ec99a04b6fedfe365ac8865_(
    (_lambda_37b72c2f4ec99a04b6fedfe365ac8865_ *)(v11 + 3),
    (const struct _lambda_37b72c2f4ec99a04b6fedfe365ac8865_ *)a2);
  Concurrency::details::_Task_impl_base::_ScheduleTask(v9, v11, 0);
  Concurrency::task_options::~task_options((Concurrency::task_options *)v15);
  _lambda_8757527ad8577d579be782cce1093164_::~_lambda_8757527ad8577d579be782cce1093164_((_lambda_8757527ad8577d579be782cce1093164_ *)(a2 + 40));
  return a1;
}

```

## disassembly

```asm
0x180043280  mov     [rsp-8+arg_10], rbx
0x180043285  push    rbp
0x180043286  push    rsi
0x180043287  push    rdi
0x180043288  push    r14
0x18004328a  push    r15
0x18004328c  lea     rbp, [rsp-37h]
0x180043291  sub     rsp, 0C0h
0x180043298  mov     rax, cs:__security_cookie
0x18004329f  xor     rax, rsp
0x1800432a2  mov     [rbp+57h+var_28], rax
0x1800432a6  mov     r14, rdx
0x1800432a9  mov     rsi, rcx
0x1800432ac  mov     [rbp+57h+var_98], rcx
0x1800432b0  mov     [rbp+57h+var_30], rdx
0x1800432b4  xor     edi, edi
0x1800432b6  mov     [rcx], rdi
0x1800432b9  mov     [rcx+8], rdi
0x1800432bd  lea     rcx, [rbp+57h+var_90]; this
0x1800432c1  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1800432c6  nop
0x1800432c7  lea     rdx, [rbp+57h+var_B8]
0x1800432cb  lea     rcx, [rbp+57h+var_90]
0x1800432cf  call    ?get_scheduler@task_options@Concurrency@@QEBA?AUscheduler_ptr@2@XZ; Concurrency::task_options::get_scheduler(void)
0x1800432d4  mov     rbx, [rbp+57h+var_78]
0x1800432d8  test    rbx, rbx
0x1800432db  jz      short loc_1800432E1
0x1800432dd  lock inc dword ptr [rbx+8]
0x1800432e1  mov     [rbp+57h+var_C0], rbx
0x1800432e5  mov     rdx, rbx
0x1800432e8  mov     r15d, 2
0x1800432ee  test    rbx, rbx
0x1800432f1  cmovz   rdx, r15
0x1800432f5  mov     r8, rax
0x1800432f8  mov     rcx, rsi
0x1800432fb  call    ?_CreateImpl@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<wil::cloud_store_save_result>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x180043300  nop
0x180043301  test    rbx, rbx
0x180043304  jz      short loc_18004330F
0x180043306  mov     rcx, rbx; this
0x180043309  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18004330e  nop
0x18004330f  mov     r8, [rbp+5Fh]
0x180043313  lea     rcx, [rbp+57h+var_B8]; this
0x180043317  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18004331c  mov     [rbp+57h+var_B8], r8
0x180043320  lea     rdx, [rbp+57h+var_B8]
0x180043324  mov     rcx, rsi
0x180043327  call    ?_SetTaskCreationCallstack@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEAAXAEBV_TaskCreationCallstack@details@2@@Z; Concurrency::task<wil::cloud_store_save_result>::_SetTaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x18004332c  nop
0x18004332d  lea     rcx, [rbp+57h+var_B0]
0x180043331  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>(void)
0x180043336  mov     rcx, rdi
0x180043339  mov     rax, [rsi]
0x18004333c  mov     [rax+rcx+0Ch], dil
0x180043341  inc     rcx
0x180043344  cmp     rcx, r15
0x180043347  jnz     short loc_180043339
0x180043349  mov     rcx, [rsi]
0x18004334c  add     rcx, 160h
0x180043353  xor     edx, edx
0x180043355  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18004335b  mov     rdi, [rsi]
0x18004335e  mov     ecx, 1D8h; Size
0x180043363  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043368  mov     rbx, rax
0x18004336b  mov     [rbp+57h+var_C0], rax
0x18004336f  lea     rax, ??_7?$_PPLTaskHandle@Vcloud_store_save_result@wil@@U?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180043376  mov     [rbx], rax
0x180043379  lea     rcx, [rbx+8]
0x18004337d  mov     rdx, rsi
0x180043380  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x180043385  nop
0x180043386  lea     rax, ??_7?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@6B@; const Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_37b72c2f4ec99a04b6fedfe365ac8865_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18004338d  mov     [rbx], rax
0x180043390  lea     rcx, [rbx+18h]; this
0x180043394  mov     rdx, r14; struct _lambda_37b72c2f4ec99a04b6fedfe365ac8865_ *
0x180043397  call    ??0_lambda_37b72c2f4ec99a04b6fedfe365ac8865_@@QEAA@AEBV0@@Z; _lambda_37b72c2f4ec99a04b6fedfe365ac8865_::_lambda_37b72c2f4ec99a04b6fedfe365ac8865_(_lambda_37b72c2f4ec99a04b6fedfe365ac8865_ const &)
0x18004339c  nop
0x18004339d  xor     r8d, r8d
0x1800433a0  mov     rdx, rbx
0x1800433a3  mov     rcx, rdi
0x1800433a6  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x1800433ab  nop
0x1800433ac  lea     rcx, [rbp+57h+var_90]; this
0x1800433b0  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x1800433b5  nop
0x1800433b6  lea     rcx, [r14+28h]; this
0x1800433ba  call    ??1_lambda_8757527ad8577d579be782cce1093164_@@QEAA@XZ; _lambda_8757527ad8577d579be782cce1093164_::~_lambda_8757527ad8577d579be782cce1093164_(void)
0x1800433bf  mov     rax, rsi
0x1800433c2  mov     rcx, [rbp+57h+var_28]
0x1800433c6  xor     rcx, rsp; StackCookie
0x1800433c9  call    __security_check_cookie
0x1800433ce  mov     rbx, [rsp+0E0h+arg_10]
0x1800433d6  add     rsp, 0C0h
0x1800433dd  pop     r15
0x1800433df  pop     r14
0x1800433e1  pop     rdi
0x1800433e2  pop     rsi
0x1800433e3  pop     rbp
0x1800433e4  retn
```

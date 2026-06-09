# Concurrency::task<wil::cloud_store_save_result>::task<wil::cloud_store_save_result>(_lambda_5841bb6124e075856403c279d110f614_)

- ea: `0x180043714`
- end: `0x180043877`
- name: `??$?0V_lambda_5841bb6124e075856403c279d110f614_@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEAA@V_lambda_5841bb6124e075856403c279d110f614_@@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004a690`

## callees

- `0x1800030e0`
- `0x1800037c0`
- `0x180010fc0`
- `0x18004324c`
- `0x180043714`
- `0x180047f54`
- `0x1800488c8`
- `0x180048c60`
- `0x180048e1c`
- `0x180049980`
- `0x18004dadc`
- `0x18004ed78`
- `0x18004f160`
- `0x18004f1b8`
- `0x18004f6c8`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800437ea`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800437ea`

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
  v11 = operator new(0x160u);
  *v11 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v11 + 1,
    a1);
  *v11 = &Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  _lambda_5841bb6124e075856403c279d110f614_::_lambda_5841bb6124e075856403c279d110f614_(
    (_lambda_5841bb6124e075856403c279d110f614_ *)(v11 + 3),
    (const struct _lambda_5841bb6124e075856403c279d110f614_ *)a2);
  Concurrency::details::_Task_impl_base::_ScheduleTask(v9, v11, 0);
  Concurrency::task_options::~task_options((Concurrency::task_options *)v15);
  _lambda_73cf33be731be4801e459318391e3fda_::~_lambda_73cf33be731be4801e459318391e3fda_((_lambda_73cf33be731be4801e459318391e3fda_ *)(a2 + 40));
  return a1;
}

```

## disassembly

```asm
0x180043714  mov     [rsp-8+arg_10], rbx
0x180043719  push    rbp
0x18004371a  push    rsi
0x18004371b  push    rdi
0x18004371c  push    r14
0x18004371e  push    r15
0x180043720  lea     rbp, [rsp-37h]
0x180043725  sub     rsp, 0C0h
0x18004372c  mov     rax, cs:__security_cookie
0x180043733  xor     rax, rsp
0x180043736  mov     [rbp+57h+var_28], rax
0x18004373a  mov     r14, rdx
0x18004373d  mov     rsi, rcx
0x180043740  mov     [rbp+57h+var_98], rcx
0x180043744  mov     [rbp+57h+var_30], rdx
0x180043748  xor     edi, edi
0x18004374a  mov     [rcx], rdi
0x18004374d  mov     [rcx+8], rdi
0x180043751  lea     rcx, [rbp+57h+var_90]; this
0x180043755  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x18004375a  nop
0x18004375b  lea     rdx, [rbp+57h+var_B8]
0x18004375f  lea     rcx, [rbp+57h+var_90]
0x180043763  call    ?get_scheduler@task_options@Concurrency@@QEBA?AUscheduler_ptr@2@XZ; Concurrency::task_options::get_scheduler(void)
0x180043768  mov     rbx, [rbp+57h+var_78]
0x18004376c  test    rbx, rbx
0x18004376f  jz      short loc_180043775
0x180043771  lock inc dword ptr [rbx+8]
0x180043775  mov     [rbp+57h+var_C0], rbx
0x180043779  mov     rdx, rbx
0x18004377c  mov     r15d, 2
0x180043782  test    rbx, rbx
0x180043785  cmovz   rdx, r15
0x180043789  mov     r8, rax
0x18004378c  mov     rcx, rsi
0x18004378f  call    ?_CreateImpl@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<wil::cloud_store_save_result>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x180043794  nop
0x180043795  test    rbx, rbx
0x180043798  jz      short loc_1800437A3
0x18004379a  mov     rcx, rbx; this
0x18004379d  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1800437a2  nop
0x1800437a3  mov     r8, [rbp+5Fh]
0x1800437a7  lea     rcx, [rbp+57h+var_B8]; this
0x1800437ab  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x1800437b0  mov     [rbp+57h+var_B8], r8
0x1800437b4  lea     rdx, [rbp+57h+var_B8]
0x1800437b8  mov     rcx, rsi
0x1800437bb  call    ?_SetTaskCreationCallstack@?$task@Vcloud_store_save_result@wil@@@Concurrency@@QEAAXAEBV_TaskCreationCallstack@details@2@@Z; Concurrency::task<wil::cloud_store_save_result>::_SetTaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x1800437c0  nop
0x1800437c1  lea     rcx, [rbp+57h+var_B0]
0x1800437c5  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>(void)
0x1800437ca  mov     rcx, rdi
0x1800437cd  mov     rax, [rsi]
0x1800437d0  mov     [rax+rcx+0Ch], dil
0x1800437d5  inc     rcx
0x1800437d8  cmp     rcx, r15
0x1800437db  jnz     short loc_1800437CD
0x1800437dd  mov     rcx, [rsi]
0x1800437e0  mov     ebx, 160h
0x1800437e5  add     rcx, rbx
0x1800437e8  xor     edx, edx
0x1800437ea  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x1800437f0  mov     rdi, [rsi]
0x1800437f3  mov     ecx, ebx; Size
0x1800437f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800437fa  mov     rbx, rax
0x1800437fd  mov     [rbp+57h+var_C0], rax
0x180043801  lea     rax, ??_7?$_PPLTaskHandle@Vcloud_store_save_result@wil@@U?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_5841bb6124e075856403c279d110f614_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_save_result,Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180043808  mov     [rbx], rax
0x18004380b  lea     rcx, [rbx+8]
0x18004380f  mov     rdx, rsi
0x180043812  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x180043817  nop
0x180043818  lea     rax, ??_7?$_InitialTaskHandle@Vcloud_store_save_result@wil@@V_lambda_5841bb6124e075856403c279d110f614_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@Vcloud_store_save_result@wil@@@Concurrency@@6B@; const Concurrency::task<wil::cloud_store_save_result>::_InitialTaskHandle<wil::cloud_store_save_result,_lambda_5841bb6124e075856403c279d110f614_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18004381f  mov     [rbx], rax
0x180043822  lea     rcx, [rbx+18h]; this
0x180043826  mov     rdx, r14; struct _lambda_5841bb6124e075856403c279d110f614_ *
0x180043829  call    ??0_lambda_5841bb6124e075856403c279d110f614_@@QEAA@AEBV0@@Z; _lambda_5841bb6124e075856403c279d110f614_::_lambda_5841bb6124e075856403c279d110f614_(_lambda_5841bb6124e075856403c279d110f614_ const &)
0x18004382e  nop
0x18004382f  xor     r8d, r8d
0x180043832  mov     rdx, rbx
0x180043835  mov     rcx, rdi
0x180043838  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18004383d  nop
0x18004383e  lea     rcx, [rbp+57h+var_90]; this
0x180043842  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x180043847  nop
0x180043848  lea     rcx, [r14+28h]; this
0x18004384c  call    ??1_lambda_73cf33be731be4801e459318391e3fda_@@QEAA@XZ; _lambda_73cf33be731be4801e459318391e3fda_::~_lambda_73cf33be731be4801e459318391e3fda_(void)
0x180043851  mov     rax, rsi
0x180043854  mov     rcx, [rbp+57h+var_28]
0x180043858  xor     rcx, rsp; StackCookie
0x18004385b  call    __security_check_cookie
0x180043860  mov     rbx, [rsp+0E0h+arg_10]
0x180043868  add     rsp, 0C0h
0x18004386f  pop     r15
0x180043871  pop     r14
0x180043873  pop     rdi
0x180043874  pop     rsi
0x180043875  pop     rbp
0x180043876  retn
```

# Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>(_lambda_488856adf621c6ff95a38da0d629ff6c_)

- ea: `0x180043580`
- end: `0x18004370b`
- name: `??$?0V_lambda_488856adf621c6ff95a38da0d629ff6c_@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEAA@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004aa04`

## callees

- `0x1800030e0`
- `0x1800037c0`
- `0x180010fc0`
- `0x18004324c`
- `0x180043580`
- `0x180045d9c`
- `0x180047eac`
- `0x1800488c8`
- `0x180048c60`
- `0x180048db0`
- `0x180049980`
- `0x18004d9d0`
- `0x18004ed78`
- `0x18004f160`
- `0x18004f6c8`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18004367a`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18004367a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 scheduler; // rax
  Concurrency::details::_RefCounter *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 i; // rcx
  __int64 v10; // rdi
  _QWORD *v12; // [rsp+20h] [rbp-89h]
  __int64 v13; // [rsp+28h] [rbp-81h] BYREF
  _QWORD v14[4]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v16[24]; // [rsp+70h] [rbp-39h] BYREF
  Concurrency::details::_RefCounter *v17; // [rsp+88h] [rbp-21h]
  __int64 v18; // [rsp+D0h] [rbp+27h]

  v14[3] = a1;
  v18 = a2;
  *a1 = 0;
  a1[1] = 0;
  Concurrency::task_options::task_options((Concurrency::task_options *)v16);
  scheduler = Concurrency::task_options::get_scheduler(v16, v15);
  v5 = v17;
  if ( v17 )
    _InterlockedIncrement((volatile signed __int32 *)v17 + 2);
  v6 = (__int64)v5;
  if ( !v5 )
    v6 = 2;
  Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_CreateImpl(
    a1,
    v6,
    scheduler);
  if ( v5 )
    Concurrency::details::_RefCounter::_Release(v5);
  Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack((Concurrency::details::_TaskCreationCallstack *)&v13);
  v13 = v7;
  v8 = *a1;
  *(_QWORD *)(v8 + 320) = v7;
  if ( (_QWORD *)(v8 + 328) != v14 )
    std::vector<void *>::_Assign_counted_range<void * *>(v8 + 328, v14[0], (__int64)(v14[1] - v14[0]) >> 3);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>(v14);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*a1 + i + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352LL), 0);
  v10 = *a1;
  v12 = operator new(0xF0u);
  *v12 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v12 + 1,
    a1);
  *v12 = &Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  _lambda_45f745786ef9029c1ad2740a163b37bf_::_lambda_45f745786ef9029c1ad2740a163b37bf_(
    (_lambda_45f745786ef9029c1ad2740a163b37bf_ *)(v12 + 3),
    (const struct _lambda_45f745786ef9029c1ad2740a163b37bf_ *)a2);
  Concurrency::details::_Task_impl_base::_ScheduleTask(v10, v12, 0);
  Concurrency::task_options::~task_options((Concurrency::task_options *)v16);
  _lambda_6097690ecdf9c863edd60def523b580d_::~_lambda_6097690ecdf9c863edd60def523b580d_((_lambda_6097690ecdf9c863edd60def523b580d_ *)(a2 + 40));
  return a1;
}

```

## disassembly

```asm
0x180043580  mov     [rsp-8+arg_10], rbx
0x180043585  push    rbp
0x180043586  push    rsi
0x180043587  push    rdi
0x180043588  push    r14
0x18004358a  push    r15
0x18004358c  lea     rbp, [rsp-37h]
0x180043591  sub     rsp, 0E0h
0x180043598  mov     rax, cs:__security_cookie
0x18004359f  xor     rax, rsp
0x1800435a2  mov     [rbp+57h+var_28], rax
0x1800435a6  mov     r14, rdx
0x1800435a9  mov     rsi, rcx
0x1800435ac  mov     [rbp+57h+var_B8], rcx
0x1800435b0  mov     [rbp+57h+var_30], rdx
0x1800435b4  xor     edi, edi
0x1800435b6  mov     [rcx], rdi
0x1800435b9  mov     [rcx+8], rdi
0x1800435bd  lea     rcx, [rbp+57h+var_90]; this
0x1800435c1  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x1800435c6  nop
0x1800435c7  lea     rdx, [rbp+57h+var_B0]
0x1800435cb  lea     rcx, [rbp+57h+var_90]
0x1800435cf  call    ?get_scheduler@task_options@Concurrency@@QEBA?AUscheduler_ptr@2@XZ; Concurrency::task_options::get_scheduler(void)
0x1800435d4  mov     rbx, [rbp+57h+var_78]
0x1800435d8  test    rbx, rbx
0x1800435db  jz      short loc_1800435E1
0x1800435dd  lock inc dword ptr [rbx+8]
0x1800435e1  mov     [rsp+100h+var_E0], rbx
0x1800435e6  mov     rdx, rbx
0x1800435e9  mov     r15d, 2
0x1800435ef  test    rbx, rbx
0x1800435f2  cmovz   rdx, r15
0x1800435f6  mov     r8, rax
0x1800435f9  mov     rcx, rsi
0x1800435fc  call    ?_CreateImpl@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x180043601  nop
0x180043602  test    rbx, rbx
0x180043605  jz      short loc_180043610
0x180043607  mov     rcx, rbx; this
0x18004360a  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18004360f  nop
0x180043610  mov     r8, [rbp+5Fh]
0x180043614  lea     rcx, [rsp+100h+var_D8]; this
0x180043619  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18004361e  mov     [rsp+100h+var_D8], r8
0x180043623  mov     rax, [rsi]
0x180043626  mov     [rax+140h], r8
0x18004362d  lea     rcx, [rax+148h]
0x180043634  lea     rax, [rbp+57h+var_D0]
0x180043638  cmp     rcx, rax
0x18004363b  jz      short loc_180043652
0x18004363d  mov     r8, [rbp+57h+var_C8]
0x180043641  mov     rdx, [rbp+57h+var_D0]
0x180043645  sub     r8, rdx
0x180043648  sar     r8, 3
0x18004364c  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x180043651  nop
0x180043652  lea     rcx, [rbp+57h+var_D0]
0x180043656  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>(void)
0x18004365b  mov     rcx, rdi
0x18004365e  mov     rax, [rsi]
0x180043661  mov     [rax+rcx+0Ch], dil
0x180043666  inc     rcx
0x180043669  cmp     rcx, r15
0x18004366c  jnz     short loc_18004365E
0x18004366e  mov     rcx, [rsi]
0x180043671  add     rcx, 160h
0x180043678  xor     edx, edx
0x18004367a  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180043680  mov     rdi, [rsi]
0x180043683  mov     ecx, 0F0h; Size
0x180043688  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004368d  mov     rbx, rax
0x180043690  mov     [rsp+100h+var_E0], rax
0x180043695  lea     rax, ??_7?$_PPLTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x18004369c  mov     [rbx], rax
0x18004369f  lea     rcx, [rbx+8]
0x1800436a3  mov     rdx, rsi
0x1800436a6  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1800436ab  nop
0x1800436ac  lea     rax, ??_7?$_InitialTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@6B@; const Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x1800436b3  mov     [rbx], rax
0x1800436b6  lea     rcx, [rbx+18h]; this
0x1800436ba  mov     rdx, r14; struct _lambda_45f745786ef9029c1ad2740a163b37bf_ *
0x1800436bd  call    ??0_lambda_45f745786ef9029c1ad2740a163b37bf_@@QEAA@AEBV0@@Z; _lambda_45f745786ef9029c1ad2740a163b37bf_::_lambda_45f745786ef9029c1ad2740a163b37bf_(_lambda_45f745786ef9029c1ad2740a163b37bf_ const &)
0x1800436c2  nop
0x1800436c3  xor     r8d, r8d
0x1800436c6  mov     rdx, rbx
0x1800436c9  mov     rcx, rdi
0x1800436cc  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x1800436d1  nop
0x1800436d2  lea     rcx, [rbp+57h+var_90]; this
0x1800436d6  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x1800436db  nop
0x1800436dc  lea     rcx, [r14+28h]; this
0x1800436e0  call    ??1_lambda_6097690ecdf9c863edd60def523b580d_@@QEAA@XZ; _lambda_6097690ecdf9c863edd60def523b580d_::~_lambda_6097690ecdf9c863edd60def523b580d_(void)
0x1800436e5  mov     rax, rsi
0x1800436e8  mov     rcx, [rbp+57h+var_28]
0x1800436ec  xor     rcx, rsp; StackCookie
0x1800436ef  call    __security_check_cookie
0x1800436f4  mov     rbx, [rsp+100h+arg_10]
0x1800436fc  add     rsp, 0E0h
0x180043703  pop     r15
0x180043705  pop     r14
0x180043707  pop     rdi
0x180043708  pop     rsi
0x180043709  pop     rbp
0x18004370a  retn
```

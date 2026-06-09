# Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>(_lambda_45f745786ef9029c1ad2740a163b37bf_)

- ea: `0x1800433ec`
- end: `0x180043577`
- name: `??$?0V_lambda_45f745786ef9029c1ad2740a163b37bf_@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEAA@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@@Z`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004a41c`

## callees

- `0x1800030e0`
- `0x1800037c0`
- `0x180010fc0`
- `0x18004324c`
- `0x1800433ec`
- `0x180045d9c`
- `0x180047eac`
- `0x1800488c8`
- `0x180048c60`
- `0x180048db0`
- `0x180049980`
- `0x18004d8c4`
- `0x18004ed78`
- `0x18004f160`
- `0x18004f6c8`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800434e6`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x1800434e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>(
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
  Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_CreateImpl(
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
  *v12 = &Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v12 + 1,
    a1);
  *v12 = &Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
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
0x1800433ec  mov     [rsp-8+arg_10], rbx
0x1800433f1  push    rbp
0x1800433f2  push    rsi
0x1800433f3  push    rdi
0x1800433f4  push    r14
0x1800433f6  push    r15
0x1800433f8  lea     rbp, [rsp-37h]
0x1800433fd  sub     rsp, 0E0h
0x180043404  mov     rax, cs:__security_cookie
0x18004340b  xor     rax, rsp
0x18004340e  mov     [rbp+57h+var_28], rax
0x180043412  mov     r14, rdx
0x180043415  mov     rsi, rcx
0x180043418  mov     [rbp+57h+var_B8], rcx
0x18004341c  mov     [rbp+57h+var_30], rdx
0x180043420  xor     edi, edi
0x180043422  mov     [rcx], rdi
0x180043425  mov     [rcx+8], rdi
0x180043429  lea     rcx, [rbp+57h+var_90]; this
0x18004342d  call    ??0task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::task_options(void)
0x180043432  nop
0x180043433  lea     rdx, [rbp+57h+var_B0]
0x180043437  lea     rcx, [rbp+57h+var_90]
0x18004343b  call    ?get_scheduler@task_options@Concurrency@@QEBA?AUscheduler_ptr@2@XZ; Concurrency::task_options::get_scheduler(void)
0x180043440  mov     rbx, [rbp+57h+var_78]
0x180043444  test    rbx, rbx
0x180043447  jz      short loc_18004344D
0x180043449  lock inc dword ptr [rbx+8]
0x18004344d  mov     [rsp+100h+var_E0], rbx
0x180043452  mov     rdx, rbx
0x180043455  mov     r15d, 2
0x18004345b  test    rbx, rbx
0x18004345e  cmovz   rdx, r15
0x180043462  mov     r8, rax
0x180043465  mov     rcx, rsi
0x180043468  call    ?_CreateImpl@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x18004346d  nop
0x18004346e  test    rbx, rbx
0x180043471  jz      short loc_18004347C
0x180043473  mov     rcx, rbx; this
0x180043476  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18004347b  nop
0x18004347c  mov     r8, [rbp+5Fh]
0x180043480  lea     rcx, [rsp+100h+var_D8]; this
0x180043485  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18004348a  mov     [rsp+100h+var_D8], r8
0x18004348f  mov     rax, [rsi]
0x180043492  mov     [rax+140h], r8
0x180043499  lea     rcx, [rax+148h]
0x1800434a0  lea     rax, [rbp+57h+var_D0]
0x1800434a4  cmp     rcx, rax
0x1800434a7  jz      short loc_1800434BE
0x1800434a9  mov     r8, [rbp+57h+var_C8]
0x1800434ad  mov     rdx, [rbp+57h+var_D0]
0x1800434b1  sub     r8, rdx
0x1800434b4  sar     r8, 3
0x1800434b8  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x1800434bd  nop
0x1800434be  lea     rcx, [rbp+57h+var_D0]
0x1800434c2  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::_Iterator_base0>>>(void)
0x1800434c7  mov     rcx, rdi
0x1800434ca  mov     rax, [rsi]
0x1800434cd  mov     [rax+rcx+0Ch], dil
0x1800434d2  inc     rcx
0x1800434d5  cmp     rcx, r15
0x1800434d8  jnz     short loc_1800434CA
0x1800434da  mov     rcx, [rsi]
0x1800434dd  add     rcx, 160h
0x1800434e4  xor     edx, edx
0x1800434e6  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x1800434ec  mov     rdi, [rsi]
0x1800434ef  mov     ecx, 0F0h; Size
0x1800434f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800434f9  mov     rbx, rax
0x1800434fc  mov     [rsp+100h+var_E0], rax
0x180043501  lea     rax, ??_7?$_PPLTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180043508  mov     [rbx], rax
0x18004350b  lea     rcx, [rbx+8]
0x18004350f  mov     rdx, rsi
0x180043512  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x180043517  nop
0x180043518  lea     rax, ??_7?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@6B@; const Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18004351f  mov     [rbx], rax
0x180043522  lea     rcx, [rbx+18h]; this
0x180043526  mov     rdx, r14; struct _lambda_45f745786ef9029c1ad2740a163b37bf_ *
0x180043529  call    ??0_lambda_45f745786ef9029c1ad2740a163b37bf_@@QEAA@AEBV0@@Z; _lambda_45f745786ef9029c1ad2740a163b37bf_::_lambda_45f745786ef9029c1ad2740a163b37bf_(_lambda_45f745786ef9029c1ad2740a163b37bf_ const &)
0x18004352e  nop
0x18004352f  xor     r8d, r8d
0x180043532  mov     rdx, rbx
0x180043535  mov     rcx, rdi
0x180043538  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18004353d  nop
0x18004353e  lea     rcx, [rbp+57h+var_90]; this
0x180043542  call    ??1task_options@Concurrency@@QEAA@XZ; Concurrency::task_options::~task_options(void)
0x180043547  nop
0x180043548  lea     rcx, [r14+28h]; this
0x18004354c  call    ??1_lambda_6097690ecdf9c863edd60def523b580d_@@QEAA@XZ; _lambda_6097690ecdf9c863edd60def523b580d_::~_lambda_6097690ecdf9c863edd60def523b580d_(void)
0x180043551  mov     rax, rsi
0x180043554  mov     rcx, [rbp+57h+var_28]
0x180043558  xor     rcx, rsp; StackCookie
0x18004355b  call    __security_check_cookie
0x180043560  mov     rbx, [rsp+100h+arg_10]
0x180043568  add     rsp, 0E0h
0x18004356f  pop     r15
0x180043571  pop     r14
0x180043573  pop     rdi
0x180043574  pop     rsi
0x180043575  pop     rbp
0x180043576  retn
```

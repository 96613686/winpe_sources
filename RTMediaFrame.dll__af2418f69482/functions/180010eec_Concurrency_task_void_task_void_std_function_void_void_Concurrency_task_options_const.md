# Concurrency::task<void>::task<void>(std::function<void (void)>,Concurrency::task_options const &)

- ea: `0x180010eec`
- end: `0x1800110a6`
- name: `??$?0V?$function@$$A6AXXZ@std@@@?$task@X@Concurrency@@QEAA@V?$function@$$A6AXXZ@std@@AEBVtask_options@1@@Z`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e64c`

## callees

- `0x180010d48`
- `0x180010eec`
- `0x180011444`
- `0x180011578`
- `0x180011590`
- `0x1800115c4`
- `0x18001ec7c`
- `0x18001ee34`
- `0x18001f5e0`
- `0x180021dc8`
- `0x1800272a0`
- `0x180033f30`
- `0x180052010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180011015`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180011015`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Concurrency::task<void>::task<void>(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 scheduler; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rdx
  char v11; // bl
  __int64 v12; // rdx
  __int64 i; // rcx
  __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  __int128 v19; // [rsp+28h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h]
  __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v22[24]; // [rsp+48h] [rbp-18h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]
  _QWORD *v24; // [rsp+A0h] [rbp+40h]

  *a1 = 0;
  a1[1] = 0;
  scheduler = Concurrency::task_options::get_scheduler(a3, &v18);
  v7 = *(volatile signed __int32 **)(a3 + 24);
  if ( v7 )
    _InterlockedIncrement(v7 + 2);
  v8 = (__int64)v7;
  if ( !v7 )
    v8 = 2;
  Concurrency::task<unsigned char>::_CreateImpl(a1, v8, scheduler);
  if ( v7 )
    Concurrency::details::_RefCounter::_Release((Concurrency::details::_RefCounter *)v7);
  if ( *(_BYTE *)(a3 + 48) )
  {
    v18 = *(_QWORD *)(a3 + 56);
    v19 = 0;
    v20 = 0;
    std::vector<void *>::_Construct_n<void * * const &,void * * const &>(
      &v19,
      (__int64)(*(_QWORD *)(a3 + 72) - *(_QWORD *)(a3 + 64)) >> 3);
    v10 = &v18;
    v11 = 1;
  }
  else
  {
    std::vector<void *>::vector<void *>(v22, retaddr, v9);
    v21 = v12;
    v10 = &v21;
    v11 = 2;
  }
  Concurrency::task<unsigned char>::_SetTaskCreationCallstack(a1, v10);
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    std::vector<void *>::_Tidy(v22);
  }
  if ( (v11 & 1) != 0 )
    std::vector<void *>::_Tidy(&v19);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + *a1 + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352LL), 0);
  v14 = *a1;
  v24 = operator new(0x58u);
  *v24 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>(
    v24 + 1,
    a1);
  *v24 = &Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>(
    v24 + 3,
    a2);
  Concurrency::details::_Task_impl_base::_ScheduleTask(v14, v24, 0);
  v16 = *(_QWORD *)(a2 + 56);
  if ( v16 )
  {
    LOBYTE(v15) = v16 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, v15);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180010eec  mov     [rsp-28h+arg_18], rbx
0x180010ef1  mov     [rsp-28h+arg_8], rdx
0x180010ef6  mov     [rsp-28h+arg_0], rcx
0x180010efb  push    rbp
0x180010efc  push    rsi
0x180010efd  push    rdi
0x180010efe  push    r12
0x180010f00  push    r14
0x180010f02  mov     rbp, rsp
0x180010f05  sub     rsp, 60h
0x180010f09  mov     rdi, r8
0x180010f0c  mov     r14, rdx
0x180010f0f  mov     rsi, rcx
0x180010f12  mov     dword ptr [rbp+arg_10], 0
0x180010f19  mov     qword ptr [rcx], 0
0x180010f20  mov     qword ptr [rcx+8], 0
0x180010f28  lea     rdx, [rbp+var_40]
0x180010f2c  mov     rcx, r8
0x180010f2f  call    ?get_scheduler@task_options@Concurrency@@QEBA?AUscheduler_ptr@2@XZ; Concurrency::task_options::get_scheduler(void)
0x180010f34  mov     rbx, [rdi+18h]
0x180010f38  test    rbx, rbx
0x180010f3b  jz      short loc_180010F41
0x180010f3d  lock inc dword ptr [rbx+8]
0x180010f41  mov     [rbp+arg_10], rbx
0x180010f45  mov     rdx, rbx
0x180010f48  mov     r12d, 2
0x180010f4e  test    rbx, rbx
0x180010f51  cmovz   rdx, r12
0x180010f55  mov     r8, rax
0x180010f58  mov     rcx, rsi
0x180010f5b  call    ?_CreateImpl@?$task@E@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<uchar>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x180010f60  nop
0x180010f61  test    rbx, rbx
0x180010f64  jz      short loc_180010F6F
0x180010f66  mov     rcx, rbx; this
0x180010f69  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x180010f6e  nop
0x180010f6f  cmp     byte ptr [rdi+30h], 0
0x180010f73  jz      short loc_180010FB3
0x180010f75  mov     rax, [rdi+38h]
0x180010f79  mov     [rbp+var_40], rax
0x180010f7d  xorps   xmm0, xmm0
0x180010f80  movdqu  [rbp+var_38], xmm0
0x180010f85  mov     [rbp+var_28], 0
0x180010f8d  lea     r8, [rdi+40h]
0x180010f91  lea     r9, [r8+8]
0x180010f95  mov     rdx, [r9]
0x180010f98  sub     rdx, [r8]
0x180010f9b  sar     rdx, 3
0x180010f9f  lea     rcx, [rbp+var_38]
0x180010fa3  call    ??$_Construct_n@AEBQEAPEAXAEBQEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAX_KAEBQEAPEAX1@Z; std::vector<void *>::_Construct_n<void * * const &,void * * const &>(unsigned __int64,void * * const &,void * * const &)
0x180010fa8  lea     rdx, [rbp+var_40]
0x180010fac  mov     ebx, 1
0x180010fb1  jmp     short loc_180010FCB
0x180010fb3  mov     rdx, [rbp+28h]
0x180010fb7  lea     rcx, [rbp+var_18]
0x180010fbb  call    ??0?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::vector<void *>(void)
0x180010fc0  mov     [rbp+var_20], rdx
0x180010fc4  lea     rdx, [rbp+var_20]
0x180010fc8  mov     ebx, r12d
0x180010fcb  mov     dword ptr [rbp+arg_10], ebx
0x180010fce  mov     rcx, rsi
0x180010fd1  call    ?_SetTaskCreationCallstack@?$task@E@Concurrency@@QEAAXAEBV_TaskCreationCallstack@details@2@@Z; Concurrency::task<uchar>::_SetTaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180010fd6  nop
0x180010fd7  test    r12b, bl
0x180010fda  jz      short loc_180010FE9
0x180010fdc  and     ebx, 0FFFFFFFDh
0x180010fdf  lea     rcx, [rbp+var_18]
0x180010fe3  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180010fe8  nop
0x180010fe9  test    bl, 1
0x180010fec  jz      short loc_180010FF7
0x180010fee  lea     rcx, [rbp+var_38]
0x180010ff2  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180010ff7  xor     ecx, ecx
0x180010ff9  mov     rax, [rsi]
0x180010ffc  mov     byte ptr [rcx+rax+0Ch], 0
0x180011001  inc     rcx
0x180011004  cmp     rcx, r12
0x180011007  jnz     short loc_180010FF9
0x180011009  mov     rcx, [rsi]
0x18001100c  add     rcx, 160h
0x180011013  xor     edx, edx
0x180011015  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001101b  mov     rdi, [rsi]
0x18001101e  mov     ecx, 58h ; 'X'; Size
0x180011023  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011028  mov     rbx, rax
0x18001102b  mov     [rbp+arg_10], rax
0x18001102f  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x180011036  mov     [rbx], rax
0x180011039  lea     rcx, [rbx+8]
0x18001103d  mov     rdx, rsi
0x180011040  call    ??0?$shared_ptr@U?$_Task_impl@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>(std::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>> const &)
0x180011045  nop
0x180011046  lea     rax, ??_7?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18001104d  mov     [rbx], rax
0x180011050  lea     rcx, [rbx+18h]
0x180011054  mov     rdx, r14
0x180011057  call    ??0?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>(std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)> const &)
0x18001105c  nop
0x18001105d  xor     r8d, r8d
0x180011060  mov     rdx, rbx
0x180011063  mov     rcx, rdi
0x180011066  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18001106b  nop
0x18001106c  mov     rcx, [r14+38h]
0x180011070  test    rcx, rcx
0x180011073  jz      short loc_18001108F
0x180011075  mov     rax, [rcx]
0x180011078  cmp     rcx, r14
0x18001107b  setnz   dl
0x18001107e  mov     rax, [rax+20h]
0x180011082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011087  mov     qword ptr [r14+38h], 0
0x18001108f  mov     rax, rsi
0x180011092  mov     rbx, [rsp+60h+arg_18]
0x18001109a  add     rsp, 60h
0x18001109e  pop     r14
0x1800110a0  pop     r12
0x1800110a2  pop     rdi
0x1800110a3  pop     rsi
0x1800110a4  pop     rbp
0x1800110a5  retn
```

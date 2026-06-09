# Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>(std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::task_options const &)

- ea: `0x18001e8cc`
- end: `0x18001ea97`
- name: `??$?0V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@QEAA@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@AEBVtask_options@1@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e4a0`

## callees

- `0x180010d48`
- `0x180011444`
- `0x180011578`
- `0x180011590`
- `0x180011604`
- `0x1800117cc`
- `0x18001e8cc`
- `0x18001eaf8`
- `0x18001ec7c`
- `0x18001ee34`
- `0x1800272a0`
- `0x180031a7c`
- `0x180033f30`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001ea1e`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001ea1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 scheduler; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdx
  char v10; // bl
  __int64 v11; // r8
  __int128 *v12; // rdx
  __int64 v13; // rax
  __int64 i; // rcx
  __int64 v15; // rdi
  _BYTE v17[24]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h]
  __int128 v19; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+50h] [rbp-30h]
  __int64 v21; // [rsp+58h] [rbp-28h]
  _BYTE v22[32]; // [rsp+60h] [rbp-20h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+28h]
  _QWORD *v24; // [rsp+C0h] [rbp+40h]

  *a1 = 0;
  a1[1] = 0;
  scheduler = Concurrency::task_options::get_scheduler(a3, v17);
  v7 = *(volatile signed __int32 **)(a3 + 24);
  if ( v7 )
    _InterlockedIncrement(v7 + 2);
  v8 = (__int64)v7;
  if ( !v7 )
    v8 = 2;
  Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_CreateImpl(a1, v8, scheduler);
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
    v10 = 1;
    v11 = v18;
    v12 = &v19;
  }
  else
  {
    std::vector<void *>::vector<void *>(v22, v9, retaddr);
    v21 = v11;
    v10 = 2;
    v12 = (__int128 *)v22;
  }
  v13 = *a1;
  *(_QWORD *)(v13 + 320) = v11;
  if ( (__int128 *)(v13 + 328) != v12 )
    std::vector<void *>::_Assign_counted_range<void * *>(
      v13 + 328,
      *(_QWORD *)v12,
      (__int64)(*((_QWORD *)v12 + 1) - *(_QWORD *)v12) >> 3);
  if ( (v10 & 2) != 0 )
  {
    v10 &= ~2u;
    std::vector<void *>::_Tidy(v22);
  }
  if ( (v10 & 1) != 0 )
    std::vector<void *>::_Tidy(&v19);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + *a1 + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352LL), 0);
  v15 = *a1;
  v24 = operator new(0x58u);
  *v24 = &Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  std::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>(
    v24 + 1,
    a1);
  *v24 = &Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>(
    v24 + 3,
    a2);
  Concurrency::details::_Task_impl_base::_ScheduleTask(v15, v24, 0);
  std::_Func_class<void,>::~_Func_class<void,>(a2);
  return a1;
}

```

## disassembly

```asm
0x18001e8cc  mov     [rsp-28h+arg_18], rbx
0x18001e8d1  mov     [rsp-28h+arg_8], rdx
0x18001e8d6  mov     [rsp-28h+arg_0], rcx
0x18001e8db  push    rbp
0x18001e8dc  push    rsi
0x18001e8dd  push    rdi
0x18001e8de  push    r12
0x18001e8e0  push    r14
0x18001e8e2  mov     rbp, rsp
0x18001e8e5  sub     rsp, 80h
0x18001e8ec  mov     rdi, r8
0x18001e8ef  mov     r14, rdx
0x18001e8f2  mov     rsi, rcx
0x18001e8f5  mov     dword ptr [rbp+arg_10], 0
0x18001e8fc  mov     qword ptr [rcx], 0
0x18001e903  mov     qword ptr [rcx+8], 0
0x18001e90b  lea     rdx, [rbp+var_60]
0x18001e90f  mov     rcx, r8
0x18001e912  call    ?get_scheduler@task_options@Concurrency@@QEBA?AUscheduler_ptr@2@XZ; Concurrency::task_options::get_scheduler(void)
0x18001e917  mov     rbx, [rdi+18h]
0x18001e91b  test    rbx, rbx
0x18001e91e  jz      short loc_18001E924
0x18001e920  lock inc dword ptr [rbx+8]
0x18001e924  mov     [rbp+arg_10], rbx
0x18001e928  mov     rdx, rbx
0x18001e92b  mov     r12d, 2
0x18001e931  test    rbx, rbx
0x18001e934  cmovz   rdx, r12
0x18001e938  mov     r8, rax
0x18001e93b  mov     rcx, rsi
0x18001e93e  call    ?_CreateImpl@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@QEAAXPEAV_CancellationTokenState@details@2@Uscheduler_ptr@2@@Z; Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_CreateImpl(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)
0x18001e943  nop
0x18001e944  test    rbx, rbx
0x18001e947  jz      short loc_18001E952
0x18001e949  mov     rcx, rbx; this
0x18001e94c  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001e951  nop
0x18001e952  cmp     byte ptr [rdi+30h], 0
0x18001e956  jz      short loc_18001E99B
0x18001e958  mov     rax, [rdi+38h]
0x18001e95c  mov     [rbp+var_48], rax
0x18001e960  xorps   xmm0, xmm0
0x18001e963  movdqu  [rbp+var_40], xmm0
0x18001e968  mov     [rbp+var_30], 0
0x18001e970  lea     r8, [rdi+40h]
0x18001e974  lea     r9, [r8+8]
0x18001e978  mov     rdx, [r9]
0x18001e97b  sub     rdx, [r8]
0x18001e97e  sar     rdx, 3
0x18001e982  lea     rcx, [rbp+var_40]
0x18001e986  call    ??$_Construct_n@AEBQEAPEAXAEBQEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAX_KAEBQEAPEAX1@Z; std::vector<void *>::_Construct_n<void * * const &,void * * const &>(unsigned __int64,void * * const &,void * * const &)
0x18001e98b  nop
0x18001e98c  mov     ebx, 1
0x18001e991  mov     r8, [rbp+var_48]
0x18001e995  lea     rdx, [rbp+var_40]
0x18001e999  jmp     short loc_18001E9B3
0x18001e99b  mov     r8, [rbp+28h]
0x18001e99f  lea     rcx, [rbp+var_20]
0x18001e9a3  call    ??0?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::vector<void *>(void)
0x18001e9a8  mov     [rbp+var_28], r8
0x18001e9ac  mov     ebx, r12d
0x18001e9af  lea     rdx, [rbp+var_20]
0x18001e9b3  mov     dword ptr [rbp+arg_10], ebx
0x18001e9b6  mov     rax, [rsi]
0x18001e9b9  mov     [rax+140h], r8
0x18001e9c0  lea     rcx, [rax+148h]
0x18001e9c7  cmp     rcx, rdx
0x18001e9ca  jz      short loc_18001E9E0
0x18001e9cc  mov     r8, [rdx+8]
0x18001e9d0  sub     r8, [rdx]
0x18001e9d3  sar     r8, 3
0x18001e9d7  mov     rdx, [rdx]
0x18001e9da  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x18001e9df  nop
0x18001e9e0  test    r12b, bl
0x18001e9e3  jz      short loc_18001E9F2
0x18001e9e5  and     ebx, 0FFFFFFFDh
0x18001e9e8  lea     rcx, [rbp+var_20]
0x18001e9ec  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001e9f1  nop
0x18001e9f2  test    bl, 1
0x18001e9f5  jz      short loc_18001EA00
0x18001e9f7  lea     rcx, [rbp+var_40]
0x18001e9fb  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001ea00  xor     ecx, ecx
0x18001ea02  mov     rax, [rsi]
0x18001ea05  mov     byte ptr [rcx+rax+0Ch], 0
0x18001ea0a  inc     rcx
0x18001ea0d  cmp     rcx, r12
0x18001ea10  jnz     short loc_18001EA02
0x18001ea12  mov     rcx, [rsi]
0x18001ea15  add     rcx, 160h
0x18001ea1c  xor     edx, edx
0x18001ea1e  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001ea24  mov     rdi, [rsi]
0x18001ea27  mov     ecx, 58h ; 'X'; Size
0x18001ea2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea31  mov     rbx, rax
0x18001ea34  mov     [rbp+arg_10], rax
0x18001ea38  lea     rax, ??_7?$_PPLTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@U?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_TaskProcHandle@details@6@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x18001ea3f  mov     [rbx], rax
0x18001ea42  lea     rcx, [rbx+8]
0x18001ea46  mov     rdx, rsi
0x18001ea49  call    ??0?$shared_ptr@U?$_Task_impl@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>(std::shared_ptr<Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>> const &)
0x18001ea4e  nop
0x18001ea4f  lea     rax, ??_7?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@6B@; const Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18001ea56  mov     [rbx], rax
0x18001ea59  lea     rcx, [rbx+18h]
0x18001ea5d  mov     rdx, r14
0x18001ea60  call    ??0?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@QEAA@AEBV01@@Z; std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>(std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)> const &)
0x18001ea65  nop
0x18001ea66  xor     r8d, r8d
0x18001ea69  mov     rdx, rbx
0x18001ea6c  mov     rcx, rdi
0x18001ea6f  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x18001ea74  nop
0x18001ea75  mov     rcx, r14
0x18001ea78  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001ea7d  mov     rax, rsi
0x18001ea80  mov     rbx, [rsp+80h+arg_18]
0x18001ea88  add     rsp, 80h
0x18001ea8f  pop     r14
0x18001ea91  pop     r12
0x18001ea93  pop     rdi
0x18001ea94  pop     rsi
0x18001ea95  pop     rbp
0x18001ea96  retn
```

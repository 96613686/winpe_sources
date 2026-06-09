# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(void)

- ea: `0x18004f820`
- end: `0x18004f897`
- name: `?invoke@?$_PPLTaskHandle@EU?$_ContinuationTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_ContinuationTaskHandleBase@details@3@@details@Concurrency@@UEBAXXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18004ca10`
- `0x18004d250`
- `0x18004d458`
- `0x18004f2e0`
- `0x18004f820`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f886`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f886`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_ContinuationTaskHandleBase>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  Concurrency::details::_Task_impl_base *v3; // rcx
  __int64 v4; // [rsp+48h] [rbp+10h]

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 40);
  v4 = a1 + 40;
  if ( (unsigned __int8)Concurrency::details::_Task_impl<unsigned char>::_TransitionedToStarted(*(_QWORD *)(a1 + 40)) )
  {
    Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(a1);
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_TaskEventLogger *)(*(_QWORD *)v4 + 352LL));
  }
  else
  {
    v3 = *v2;
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 56) + 16LL) )
      Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(v3);
    else
      Concurrency::details::_Task_impl_base::_Cancel(v3, 1);
  }
}

```

## disassembly

```asm
0x18004f820  mov     [rsp+arg_10], rbx
0x18004f825  mov     [rsp+arg_0], rcx
0x18004f82a  push    rdi
0x18004f82b  sub     rsp, 30h
0x18004f82f  mov     rbx, rcx
0x18004f832  lea     rdi, [rcx+28h]
0x18004f836  mov     [rsp+38h+arg_8], rdi
0x18004f83b  mov     rcx, [rdi]
0x18004f83e  call    ?_TransitionedToStarted@?$_Task_impl@E@details@Concurrency@@QEAA_NXZ; Concurrency::details::_Task_impl<uchar>::_TransitionedToStarted(void)
0x18004f843  test    al, al
0x18004f845  jnz     short loc_18004F868
0x18004f847  mov     rdx, [rbx+38h]
0x18004f84b  add     rdx, 10h
0x18004f84f  mov     rcx, [rdi]; this
0x18004f852  cmp     qword ptr [rdx], 0
0x18004f856  jz      short loc_18004F85F
0x18004f858  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18004f85d  jmp     short loc_18004F88C
0x18004f85f  mov     dl, 1; bool
0x18004f861  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18004f866  jmp     short loc_18004F88C
0x18004f868  mov     rcx, rbx
0x18004f86b  call    ?_Continue@?$_ContinuationTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)
0x18004f870  nop
0x18004f871  jmp     short loc_18004F877
0x18004f873  jmp     short loc_18004F877
0x18004f875  jmp     short $+2
0x18004f877  mov     rax, [rsp+38h+arg_8]
0x18004f87c  mov     rcx, [rax]
0x18004f87f  add     rcx, 160h
0x18004f886  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18004f88c  mov     rbx, [rsp+38h+arg_10]
0x18004f891  add     rsp, 30h
0x18004f895  pop     rdi
0x18004f896  retn
```

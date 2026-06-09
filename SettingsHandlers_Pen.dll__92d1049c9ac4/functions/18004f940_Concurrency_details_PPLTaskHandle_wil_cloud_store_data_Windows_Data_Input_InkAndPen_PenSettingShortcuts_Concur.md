# Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18004f940`
- end: `0x18004f9cc`
- name: `?invoke@?$_PPLTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEBAXXZ`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18004ca10`
- `0x18004e870`
- `0x18004f940`
- `0x18004fac4`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f9b8`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f9b8`
- `msvcp_win!_Mtx_unlock` at `0x18004f974`
- `msvcp_win!_Mtx_unlock` at `0x18004f993`
- `msvcp_win!_Mtx_unlock` at `0x18004f974`
- `msvcp_win!_Mtx_unlock` at `0x18004f993`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // r14
  struct _Mtx_internal_imp_t *v4; // rcx

  v2 = (Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 8);
  std::_Mutex_base::lock((std::_Mutex_base *)(v3 + 32));
  v4 = (struct _Mtx_internal_imp_t *)(v3 + 32);
  if ( *(_DWORD *)(v3 + 8) == 2 )
  {
    _Mtx_unlock(v4);
    Concurrency::details::_Task_impl_base::_Cancel(*v2, 1);
  }
  else
  {
    *(_DWORD *)(v3 + 8) = 1;
    _Mtx_unlock(v4);
    Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
  }
}

```

## disassembly

```asm
0x18004f940  mov     [rsp+arg_10], rbx
0x18004f945  mov     [rsp+arg_0], rcx
0x18004f94a  push    rsi
0x18004f94b  push    rdi
0x18004f94c  push    r14
0x18004f94e  sub     rsp, 30h
0x18004f952  mov     rbx, rcx
0x18004f955  lea     rdi, [rcx+8]
0x18004f959  mov     r14, [rdi]
0x18004f95c  lea     rsi, [r14+20h]
0x18004f960  mov     rcx, rsi; this
0x18004f963  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004f968  mov     eax, [r14+8]
0x18004f96c  mov     rcx, rsi; _Mtx_t
0x18004f96f  cmp     eax, 2
0x18004f972  jnz     short loc_18004F986
0x18004f974  call    cs:__imp__Mtx_unlock
0x18004f97a  mov     dl, 1; bool
0x18004f97c  mov     rcx, [rdi]; this
0x18004f97f  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18004f984  jmp     short loc_18004F9BE
0x18004f986  mov     [rsp+48h+arg_8], rdi
0x18004f98b  mov     dword ptr [r14+8], 1
0x18004f993  call    cs:__imp__Mtx_unlock
0x18004f999  nop
0x18004f99a  mov     rcx, rbx
0x18004f99d  call    ?_Init@?$_InitialTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_488856adf621c6ff95a38da0d629ff6c_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,_lambda_488856adf621c6ff95a38da0d629ff6c_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18004f9a2  nop
0x18004f9a3  jmp     short loc_18004F9A9
0x18004f9a5  jmp     short loc_18004F9A9
0x18004f9a7  jmp     short $+2
0x18004f9a9  mov     rax, [rsp+48h+arg_8]
0x18004f9ae  mov     rcx, [rax]
0x18004f9b1  add     rcx, 160h
0x18004f9b8  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18004f9be  mov     rbx, [rsp+48h+arg_10]
0x18004f9c3  add     rsp, 30h
0x18004f9c7  pop     r14
0x18004f9c9  pop     rdi
0x18004f9ca  pop     rsi
0x18004f9cb  retn
```

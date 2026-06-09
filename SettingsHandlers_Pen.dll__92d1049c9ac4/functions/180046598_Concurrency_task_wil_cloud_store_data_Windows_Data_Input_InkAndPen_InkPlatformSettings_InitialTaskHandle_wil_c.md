# Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings> (void)>>(std::function<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings> (void)>)

- ea: `0x180046598`
- end: `0x180046600`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6A?AV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XZ@std@@@?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBA?AV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V?$function@$$A6A?AV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XZ@std@@@Z`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e7a4`
- `0x18004e870`

## callees

- `0x180048de4`
- `0x18004ab38`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800465c8`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800465c8`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800465de`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800465de`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings> (void)>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rbx

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  std::_Func_class<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,>::operator()(a3, a2);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  std::_Func_class<void,>::~_Func_class<void,>(a3);
  return a2;
}

```

## disassembly

```asm
0x180046598  mov     rax, rsp
0x18004659b  mov     [rax+8], rbx
0x18004659f  mov     [rax+20h], rsi
0x1800465a3  mov     [rax+18h], r8
0x1800465a7  mov     [rax+10h], rdx
0x1800465ab  push    rdi
0x1800465ac  sub     rsp, 30h
0x1800465b0  mov     rdi, r8
0x1800465b3  mov     rsi, rdx
0x1800465b6  mov     rbx, [rcx+8]
0x1800465ba  add     rbx, 160h
0x1800465c1  mov     [rax+10h], rbx
0x1800465c5  mov     rcx, rbx
0x1800465c8  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800465ce  nop
0x1800465cf  mov     rdx, rsi
0x1800465d2  mov     rcx, rdi
0x1800465d5  call    ??R?$_Func_class@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@$$V@std@@QEBA?AV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@XZ; std::_Func_class<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,>::operator()(void)
0x1800465da  nop
0x1800465db  mov     rcx, rbx
0x1800465de  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800465e4  nop
0x1800465e5  mov     rcx, rdi
0x1800465e8  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800465ed  mov     rax, rsi
0x1800465f0  mov     rbx, [rsp+38h+arg_0]
0x1800465f5  mov     rsi, [rsp+38h+arg_18]
0x1800465fa  add     rsp, 30h
0x1800465fe  pop     rdi
0x1800465ff  retn
```

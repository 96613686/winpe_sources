# Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>>(std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>)

- ea: `0x18001e00c`
- end: `0x18001e074`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@@?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@QEBA?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001daa8`

## callees

- `0x1800117cc`
- `0x18001c914`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e052`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e052`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e03c`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001e03c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rbx

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  std::_Func_class<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,>::operator()(a3, a2);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  std::_Func_class<void,>::~_Func_class<void,>(a3);
  return a2;
}

```

## disassembly

```asm
0x18001e00c  mov     rax, rsp
0x18001e00f  mov     [rax+8], rbx
0x18001e013  mov     [rax+20h], rsi
0x18001e017  mov     [rax+18h], r8
0x18001e01b  mov     [rax+10h], rdx
0x18001e01f  push    rdi
0x18001e020  sub     rsp, 30h
0x18001e024  mov     rdi, r8
0x18001e027  mov     rsi, rdx
0x18001e02a  mov     rbx, [rcx+8]
0x18001e02e  add     rbx, 160h
0x18001e035  mov     [rax+10h], rbx
0x18001e039  mov     rcx, rbx
0x18001e03c  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18001e042  nop
0x18001e043  mov     rdx, rsi
0x18001e046  mov     rcx, rdi
0x18001e049  call    ??R?$_Func_class@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@$$V@std@@QEBA?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ; std::_Func_class<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,>::operator()(void)
0x18001e04e  nop
0x18001e04f  mov     rcx, rbx
0x18001e052  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001e058  nop
0x18001e059  mov     rcx, rdi
0x18001e05c  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e061  mov     rax, rsi
0x18001e064  mov     rbx, [rsp+38h+arg_0]
0x18001e069  mov     rsi, [rsp+38h+arg_18]
0x18001e06e  add     rsp, 30h
0x18001e072  pop     rdi
0x18001e073  retn
```

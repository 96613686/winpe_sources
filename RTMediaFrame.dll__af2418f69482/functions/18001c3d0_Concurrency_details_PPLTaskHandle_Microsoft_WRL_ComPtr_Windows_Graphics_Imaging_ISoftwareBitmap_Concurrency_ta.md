# Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18001c3d0`
- end: `0x18001c45c`
- name: `?invoke@?$_PPLTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@U?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@U_TaskProcHandle@details@6@@details@Concurrency@@UEBAXXZ`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c3d0`
- `0x18001daa8`
- `0x18001df10`
- `0x1800218b8`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c448`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c448`
- `msvcp_win!_Mtx_unlock` at `0x18001c404`
- `msvcp_win!_Mtx_unlock` at `0x18001c423`
- `msvcp_win!_Mtx_unlock` at `0x18001c404`
- `msvcp_win!_Mtx_unlock` at `0x18001c423`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Concurrency::details::_PPLTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base **v2; // rdi
  __int64 v3; // r14
  struct _Mtx_internal_imp_t *v4; // rcx
  Concurrency::details::_Task_impl_base *v5; // rbx
  const struct std::exception_ptr *v6; // rax
  _BYTE v7[40]; // [rsp+20h] [rbp-28h] BYREF

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
    try
    {
      Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
    }
    catch ( Concurrency::task_canceled )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), 1);
    }
    catch ( Concurrency::details::_Interruption_exception )
    {
      Concurrency::details::_Task_impl_base::_Cancel(*(Concurrency::details::_Task_impl_base **)(a1 + 8), 1);
    }
    catch ( ... )
    {
      v5 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
      v6 = (const struct std::exception_ptr *)std::current_exception(v7);
      Concurrency::details::_Task_impl_base::_CancelWithException(v5, v6);
      __ExceptionPtrDestroy(v7);
    }
    Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted((Concurrency::details::_Task_impl_base *)((char *)*v2 + 352));
  }
}

```

## disassembly

```asm
0x18001c3d0  mov     [rsp+arg_10], rbx
0x18001c3d5  mov     [rsp+arg_0], rcx
0x18001c3da  push    rsi
0x18001c3db  push    rdi
0x18001c3dc  push    r14
0x18001c3de  sub     rsp, 30h
0x18001c3e2  mov     rbx, rcx
0x18001c3e5  lea     rdi, [rcx+8]
0x18001c3e9  mov     r14, [rdi]
0x18001c3ec  lea     rsi, [r14+20h]
0x18001c3f0  mov     rcx, rsi; this
0x18001c3f3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001c3f8  mov     eax, [r14+8]
0x18001c3fc  mov     rcx, rsi; _Mtx_t
0x18001c3ff  cmp     eax, 2
0x18001c402  jnz     short loc_18001C416
0x18001c404  call    cs:__imp__Mtx_unlock
0x18001c40a  mov     dl, 1; bool
0x18001c40c  mov     rcx, [rdi]; this
0x18001c40f  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001c414  jmp     short loc_18001C44E
0x18001c416  mov     [rsp+48h+arg_8], rdi
0x18001c41b  mov     dword ptr [r14+8], 1
0x18001c423  call    cs:__imp__Mtx_unlock
0x18001c429  nop
0x18001c42a  mov     rcx, rbx
0x18001c42d  call    ?_Init@?$_InitialTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@V?$function@$$A6A?AV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_InitialTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,std::function<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18001c432  nop
0x18001c433  jmp     short loc_18001C439
0x18001c435  jmp     short loc_18001C439
0x18001c437  jmp     short $+2
0x18001c439  mov     rax, [rsp+48h+arg_8]
0x18001c43e  mov     rcx, [rax]
0x18001c441  add     rcx, 160h
0x18001c448  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18001c44e  mov     rbx, [rsp+48h+arg_10]
0x18001c453  add     rsp, 30h
0x18001c457  pop     r14
0x18001c459  pop     rdi
0x18001c45a  pop     rsi
0x18001c45b  retn
```

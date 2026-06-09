# Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(void)

- ea: `0x18004f8a0`
- end: `0x18004f92c`
- name: `?invoke@?$_PPLTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@U?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@U_TaskProcHandle@details@5@@details@Concurrency@@UEBAXXZ`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18004ca10`
- `0x18004e7a4`
- `0x18004f8a0`
- `0x18004fac4`

## import_xrefs

- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f918`
- `msvcp_win!?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004f918`
- `msvcp_win!_Mtx_unlock` at `0x18004f8d4`
- `msvcp_win!_Mtx_unlock` at `0x18004f8f3`
- `msvcp_win!_Mtx_unlock` at `0x18004f8d4`
- `msvcp_win!_Mtx_unlock` at `0x18004f8f3`

## pseudocode

```c
void __fastcall Concurrency::details::_PPLTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::invoke(
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
      Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>::_Init(a1);
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
0x18004f8a0  mov     [rsp+arg_10], rbx
0x18004f8a5  mov     [rsp+arg_0], rcx
0x18004f8aa  push    rsi
0x18004f8ab  push    rdi
0x18004f8ac  push    r14
0x18004f8ae  sub     rsp, 30h
0x18004f8b2  mov     rbx, rcx
0x18004f8b5  lea     rdi, [rcx+8]
0x18004f8b9  mov     r14, [rdi]
0x18004f8bc  lea     rsi, [r14+20h]
0x18004f8c0  mov     rcx, rsi; this
0x18004f8c3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004f8c8  mov     eax, [r14+8]
0x18004f8cc  mov     rcx, rsi; _Mtx_t
0x18004f8cf  cmp     eax, 2
0x18004f8d2  jnz     short loc_18004F8E6
0x18004f8d4  call    cs:__imp__Mtx_unlock
0x18004f8da  mov     dl, 1; bool
0x18004f8dc  mov     rcx, [rdi]; this
0x18004f8df  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18004f8e4  jmp     short loc_18004F91E
0x18004f8e6  mov     [rsp+48h+arg_8], rdi
0x18004f8eb  mov     dword ptr [r14+8], 1
0x18004f8f3  call    cs:__imp__Mtx_unlock
0x18004f8f9  nop
0x18004f8fa  mov     rcx, rbx
0x18004f8fd  call    ?_Init@?$_InitialTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@V_lambda_45f745786ef9029c1ad2740a163b37bf_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z; Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_InitialTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,_lambda_45f745786ef9029c1ad2740a163b37bf_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)
0x18004f902  nop
0x18004f903  jmp     short loc_18004F909
0x18004f905  jmp     short loc_18004F909
0x18004f907  jmp     short $+2
0x18004f909  mov     rax, [rsp+48h+arg_8]
0x18004f90e  mov     rcx, [rax]
0x18004f911  add     rcx, 160h
0x18004f918  call    cs:__imp_?_LogTaskExecutionCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskExecutionCompleted(void)
0x18004f91e  mov     rbx, [rsp+48h+arg_10]
0x18004f923  add     rsp, 30h
0x18004f927  pop     r14
0x18004f929  pop     rdi
0x18004f92a  pop     rsi
0x18004f92b  retn
```

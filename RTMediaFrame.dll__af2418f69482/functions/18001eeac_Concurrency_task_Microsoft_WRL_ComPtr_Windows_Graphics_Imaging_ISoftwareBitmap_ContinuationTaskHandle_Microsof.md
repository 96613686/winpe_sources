# Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>(std::function<uchar (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)> &&,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>> &&)

- ea: `0x18001eeac`
- end: `0x18001ef54`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@V?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@?$_ContinuationTaskHandle@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@XV?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@$$QEAV12@@Z`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d9b4`

## callees

- `0x18001134c`
- `0x18001eeac`
- `0x180052010`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ef3b`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ef3b`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001eed4`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001eed4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001ef0e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001ef0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_ContinuationTaskHandle<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>,void,std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<unsigned char (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>,Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  char v7; // bl
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-10h]

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v9 = *a3;
  v10 = (std::_Ref_count_base *)a3[1];
  *a3 = 0;
  a3[1] = 0;
  v6 = *(_QWORD *)(a2 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, &v9);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  return v7;
}

```

## disassembly

```asm
0x18001eeac  mov     [rsp+arg_10], rbx
0x18001eeb1  mov     [rsp+arg_18], rsi
0x18001eeb6  push    rdi
0x18001eeb7  sub     rsp, 30h
0x18001eebb  mov     rbx, r8
0x18001eebe  mov     rdi, rdx
0x18001eec1  mov     rsi, [rcx+28h]
0x18001eec5  add     rsi, 160h
0x18001eecc  mov     [rsp+38h+arg_0], rsi
0x18001eed1  mov     rcx, rsi
0x18001eed4  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18001eeda  nop
0x18001eedb  mov     rax, [rbx]
0x18001eede  mov     [rsp+38h+var_18], rax
0x18001eee3  mov     rax, [rbx+8]
0x18001eee7  mov     [rsp+38h+var_10], rax
0x18001eeec  mov     qword ptr [rbx], 0
0x18001eef3  mov     qword ptr [rbx+8], 0
0x18001eefb  lea     rax, [rsp+38h+var_18]
0x18001ef00  mov     [rsp+38h+arg_8], rax
0x18001ef05  mov     rcx, [rdi+38h]
0x18001ef09  test    rcx, rcx
0x18001ef0c  jnz     short loc_18001EF15
0x18001ef0e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001ef14  int     3; Trap to Debugger
0x18001ef15  mov     rax, [rcx]
0x18001ef18  lea     rdx, [rsp+38h+var_18]
0x18001ef1d  mov     rax, [rax+10h]
0x18001ef21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef26  mov     bl, al
0x18001ef28  mov     rcx, [rsp+38h+var_10]; this
0x18001ef2d  test    rcx, rcx
0x18001ef30  jz      short loc_18001EF38
0x18001ef32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ef37  nop
0x18001ef38  mov     rcx, rsi
0x18001ef3b  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001ef41  nop
0x18001ef42  mov     al, bl
0x18001ef44  mov     rbx, [rsp+38h+arg_10]
0x18001ef49  mov     rsi, [rsp+38h+arg_18]
0x18001ef4e  add     rsp, 30h
0x18001ef52  pop     rdi
0x18001ef53  retn
```

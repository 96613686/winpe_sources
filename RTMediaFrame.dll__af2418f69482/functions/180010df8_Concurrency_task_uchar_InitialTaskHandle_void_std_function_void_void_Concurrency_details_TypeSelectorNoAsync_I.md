# Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180010df8`
- end: `0x180010ee6`
- name: `?_Init@?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010d90`

## callees

- `0x180010df8`
- `0x1800115c4`
- `0x18001dc68`
- `0x18001ff68`
- `0x180052010`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010e9a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010e9a`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010e71`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180010e71`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180010e81`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180010e81`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Init(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  __int64 v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdx
  Concurrency::details::_TaskEventLogger *v6; // rbx
  _BYTE *v7; // rdx
  _BYTE v9[56]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE *v10; // [rsp+58h] [rbp-1h]
  _BYTE v11[80]; // [rsp+60h] [rbp+7h] BYREF

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v3 = std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>(
         v11,
         a1 + 24);
  Concurrency::details::_MakeVoidToUnitFunc(v9, v3);
  v4 = *(__int64 **)(v3 + 56);
  if ( v4 )
  {
    v5 = *v4;
    LOBYTE(v5) = v4 != (__int64 *)v3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v4 + 32))(v4, v5);
    *(_QWORD *)(v3 + 56) = 0;
  }
  v6 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v6);
  if ( !v10 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v10 + 16LL))(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v6);
  if ( v10 )
  {
    v7 = v9;
    LOBYTE(v7) = v10 != v9;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v10 + 32LL))(v10, v7);
    v10 = 0;
  }
  return Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
}

```

## disassembly

```asm
0x180010df8  mov     [rsp-8+arg_18], rbx
0x180010dfd  push    rbp
0x180010dfe  push    rsi
0x180010dff  push    rdi
0x180010e00  lea     rbp, [rsp-47h]
0x180010e05  sub     rsp, 0A0h
0x180010e0c  mov     rdi, rcx
0x180010e0f  mov     rsi, [rcx+8]
0x180010e13  lea     rdx, [rcx+18h]
0x180010e17  lea     rcx, [rbp+57h+var_50]
0x180010e1b  call    ??0?$function@$$A6AXV?$task@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@Concurrency@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)>(std::function<void (Concurrency::task<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>)> const &)
0x180010e20  mov     rbx, rax
0x180010e23  mov     [rbp+57h+arg_0], rax
0x180010e27  mov     rdx, rax
0x180010e2a  lea     rcx, [rbp+57h+var_90]
0x180010e2e  call    ?_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@4@@Z; Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)
0x180010e33  nop
0x180010e34  mov     rcx, [rbx+38h]
0x180010e38  test    rcx, rcx
0x180010e3b  jz      short loc_180010E57
0x180010e3d  mov     rdx, [rcx]
0x180010e40  mov     rax, [rdx+20h]
0x180010e44  cmp     rcx, rbx
0x180010e47  setnz   dl
0x180010e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e4f  mov     qword ptr [rbx+38h], 0
0x180010e57  lea     rax, [rbp+57h+var_90]
0x180010e5b  mov     [rbp+57h+arg_0], rax
0x180010e5f  mov     rbx, [rdi+8]
0x180010e63  add     rbx, 160h
0x180010e6a  mov     [rbp+57h+arg_10], rbx
0x180010e6e  mov     rcx, rbx
0x180010e71  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180010e77  nop
0x180010e78  mov     rcx, [rbp+57h+var_58]
0x180010e7c  test    rcx, rcx
0x180010e7f  jnz     short loc_180010E88
0x180010e81  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180010e87  int     3; Trap to Debugger
0x180010e88  mov     rax, [rcx]
0x180010e8b  mov     rax, [rax+10h]
0x180010e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e94  mov     dil, al
0x180010e97  mov     rcx, rbx
0x180010e9a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180010ea0  nop
0x180010ea1  mov     rcx, [rbp+57h+var_58]
0x180010ea5  test    rcx, rcx
0x180010ea8  jz      short loc_180010EC8
0x180010eaa  mov     rax, [rcx]
0x180010ead  lea     rdx, [rbp+57h+var_90]
0x180010eb1  cmp     rcx, rdx
0x180010eb4  setnz   dl
0x180010eb7  mov     rax, [rax+20h]
0x180010ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ec0  mov     [rbp+57h+var_58], 0
0x180010ec8  mov     dl, dil
0x180010ecb  mov     rcx, rsi; this
0x180010ece  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x180010ed3  mov     rbx, [rsp+0B0h+arg_18]
0x180010edb  add     rsp, 0A0h
0x180010ee2  pop     rdi
0x180010ee3  pop     rsi
0x180010ee4  pop     rbp
0x180010ee5  retn
```

# std::thread::_Start__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1___

- ea: `0x140038404`
- end: `0x1400384ad`
- name: `std::thread::_Start__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1___`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140038870`

## callees

- `0x140004c1c`
- `0x14001b1c8`
- `0x140038404`
- `0x1400384c4`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1400384a0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1400384a0`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140038463`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140038463`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1___(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // rax
  _QWORD *v7; // [rsp+60h] [rbp+8h] BYREF

  v4 = operator new(0x158u);
  *v4 = *a2;
  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v4 + 1,
    a2 + 1);
  v4[1] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::TraceListenerAsync::`vftable';
  v7 = v4;
  v5 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    __debugbreak();
    JUMPOUT(0x1400384ADLL);
  }
  v7 = 0;
  return std::unique_ptr_std::tuple__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1____std::default_delete_std::tuple__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1_______::_unique_ptr_std::tuple__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1____std::default_delete_std::tuple__Microsoft::Win32::EventTracing::RealTimeTraceListener::StartAsync_::_2_::_lambda_1_______(&v7);
}

```

## disassembly

```asm
0x140038404  push    rbx
0x140038406  push    rsi
0x140038407  push    rdi
0x140038408  push    r14
0x14003840a  sub     rsp, 38h
0x14003840e  mov     rdi, rdx
0x140038411  mov     r14, rcx
0x140038414  mov     ecx, 158h; Size
0x140038419  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003841e  mov     rsi, rax
0x140038421  mov     r8, [rdi]
0x140038424  mov     [rax], r8
0x140038427  lea     rdx, [rdi+8]
0x14003842b  lea     rcx, [rax+8]
0x14003842f  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x140038434  lea     rax, ??_7TraceListenerAsync@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::TraceListenerAsync::`vftable'
0x14003843b  mov     [rsi+8], rax
0x14003843f  mov     [rsp+58h+arg_0], rsi
0x140038444  lea     rbx, [r14+8]
0x140038448  mov     [rsp+58h+var_30], rbx
0x14003844d  mov     [rsp+58h+var_38], 0
0x140038455  mov     r9, rsi
0x140038458  lea     r8, std__thread___Invoke_std__tuple__Microsoft__Win32__EventTracing__RealTimeTraceListener__StartAsync____2____lambda_1____0_
0x14003845f  xor     edx, edx
0x140038461  xor     ecx, ecx
0x140038463  call    cs:__imp__o__beginthreadex
0x14003846a  nop     dword ptr [rax+rax+00h]
0x14003846f  mov     [r14], rax
0x140038472  test    rax, rax
0x140038475  jz      short loc_140038495
0x140038477  mov     [rsp+58h+arg_0], 0
0x140038480  lea     rcx, [rsp+58h+arg_0]
0x140038485  call    std__unique_ptr_std__tuple__Microsoft__Win32__EventTracing__RealTimeTraceListener__StartAsync____2____lambda_1____std__default_delete_std__tuple__Microsoft__Win32__EventTracing__RealTimeTraceListener__StartAsync____2____lambda_1__________unique_ptr_std__tuple__Microsoft__Win32__EventTracing__RealTimeTraceListener__StartAsync____2____lambda_1____std__default_delete_std__tuple__Microsoft__Win32__EventTracing__RealTimeTraceListener__StartAsync____2____lambda_1_______
0x14003848a  add     rsp, 38h
0x14003848e  pop     r14
0x140038490  pop     rdi
0x140038491  pop     rsi
0x140038492  pop     rbx
0x140038493  retn
0x140038495  mov     dword ptr [rbx], 0
0x14003849b  mov     ecx, 6
0x1400384a0  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1400384a7  nop     dword ptr [rax+rax+00h]
0x1400384ac  int     3; Trap to Debugger
```

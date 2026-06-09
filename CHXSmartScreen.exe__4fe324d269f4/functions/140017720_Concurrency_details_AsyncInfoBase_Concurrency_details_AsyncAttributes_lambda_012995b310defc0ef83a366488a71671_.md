# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_GetOnProgress

- ea: `0x140017720`
- end: `0x140017753`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_GetOnProgress`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140017760`

## callees

- `0x140003330`
- `0x1400088b4`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140017729`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140017729`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_GetOnProgress()
{
  __int64 pExceptionObject; // [rsp+38h] [rbp+10h] BYREF
  __int64 Exception; // [rsp+40h] [rbp+18h]

  Exception = Platform::Exception::CreateException(2147549183LL);
  pExceptionObject = __abi_winrt_ptr_ctor(Exception);
  throw (Platform::Exception **)&pExceptionObject;
}

```

## disassembly

```asm
0x140017720  sub     rsp, 28h
0x140017724  mov     ecx, 8000FFFFh
0x140017729  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x14001772f  mov     [rsp+28h+arg_10], rax
0x140017734  mov     rcx, rax
0x140017737  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14001773c  mov     [rsp+28h+pExceptionObject], rax
0x140017741  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140017748  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001774d  call    _CxxThrowException_0
```

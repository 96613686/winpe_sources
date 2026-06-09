# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_PutOnProgress

- ea: `0x14001cac0`
- end: `0x14001caf3`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_PutOnProgress`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140003330`
- `0x1400088b4`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001cac9`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001cac9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_PutOnProgress()
{
  __int64 pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  __int64 Exception; // [rsp+48h] [rbp+20h]

  Exception = Platform::Exception::CreateException(2147549183LL);
  pExceptionObject = __abi_winrt_ptr_ctor(Exception);
  throw (Platform::Exception **)&pExceptionObject;
}

```

## disassembly

```asm
0x14001cac0  sub     rsp, 28h
0x14001cac4  mov     ecx, 8000FFFFh
0x14001cac9  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x14001cacf  mov     [rsp+28h+arg_18], rax
0x14001cad4  mov     rcx, rax
0x14001cad7  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14001cadc  mov     [rsp+28h+pExceptionObject], rax
0x14001cae1  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x14001cae8  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001caed  call    _CxxThrowException_0
```

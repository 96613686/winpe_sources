# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_CheckValidStateForAsyncInfoCall

- ea: `0x14001ac0c`
- end: `0x14001ac80`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_CheckValidStateForAsyncInfoCall`
- size: `116`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140021e50`
- `0x140021e90`
- `0x140021ec0`
- `0x140023200`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14001ac0c`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001ac27`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001ac56`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001ac27`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x14001ac56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_CheckValidStateForAsyncInfoCall(
        __int64 a1)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  result = *(unsigned int *)(a1 + 48);
  if ( (_DWORD)result == 5 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  if ( (_DWORD)result == -1 )
  {
    Exception = Platform::Exception::CreateException(2147483673LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x14001ac0c  sub     rsp, 28h
0x14001ac10  mov     eax, [rcx+30h]
0x14001ac13  cmp     eax, 5
0x14001ac16  jz      short loc_14001AC51
0x14001ac18  cmp     eax, 0FFFFFFFFh
0x14001ac1b  jz      short loc_14001AC22
0x14001ac1d  add     rsp, 28h
0x14001ac21  retn
0x14001ac22  mov     ecx, 80000019h
0x14001ac27  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x14001ac2d  mov     [rsp+28h+arg_8], rax
0x14001ac32  mov     rcx, rax
0x14001ac35  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14001ac3a  mov     [rsp+28h+pExceptionObject], rax
0x14001ac3f  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x14001ac46  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001ac4b  call    _CxxThrowException_0
0x14001ac51  mov     ecx, 8000000Eh
0x14001ac56  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x14001ac5c  mov     [rsp+28h+arg_8], rax
0x14001ac61  mov     rcx, rax
0x14001ac64  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14001ac69  mov     [rsp+28h+pExceptionObject], rax
0x14001ac6e  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x14001ac75  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001ac7a  call    _CxxThrowException_0
```

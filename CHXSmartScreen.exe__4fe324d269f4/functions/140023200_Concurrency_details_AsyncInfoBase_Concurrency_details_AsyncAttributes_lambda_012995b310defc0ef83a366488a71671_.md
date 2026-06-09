# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Id::set

- ea: `0x140023200`
- end: `0x14002328c`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Id::set`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14001ac0c`
- `0x140023200`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140023233`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140023262`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140023233`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140023262`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Id::set(
        __int64 a1,
        int a2)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  __int64 Exception; // [rsp+48h] [rbp+20h]

  Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_CheckValidStateForAsyncInfoCall(a1);
  if ( !a2 )
  {
    Exception = Platform::Exception::CreateException(2147942487LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  result = *(unsigned int *)(a1 + 48);
  if ( (_DWORD)result != -1 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  *(_DWORD *)(a1 + 56) = a2;
  return result;
}

```

## disassembly

```asm
0x140023200  mov     [rsp+arg_0], rbx
0x140023205  push    rdi
0x140023206  sub     rsp, 20h
0x14002320a  mov     edi, edx
0x14002320c  mov     rbx, rcx
0x14002320f  call    Concurrency__details___AsyncInfoBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__1____CheckValidStateForAsyncInfoCall
0x140023214  test    edi, edi
0x140023216  jz      short loc_14002325D
0x140023218  mov     eax, [rbx+30h]
0x14002321b  cmp     eax, 0FFFFFFFFh
0x14002321e  jnz     short loc_14002322E
0x140023220  mov     [rbx+38h], edi
0x140023223  mov     rbx, [rsp+28h+arg_0]
0x140023228  add     rsp, 20h
0x14002322c  pop     rdi
0x14002322d  retn
0x14002322e  mov     ecx, 8000000Eh
0x140023233  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x140023239  mov     [rsp+28h+arg_18], rax
0x14002323e  mov     rcx, rax
0x140023241  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140023246  mov     [rsp+28h+pExceptionObject], rax
0x14002324b  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140023252  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140023257  call    _CxxThrowException_0
0x14002325d  mov     ecx, 80070057h
0x140023262  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x140023268  mov     [rsp+28h+arg_18], rax
0x14002326d  mov     rcx, rax
0x140023270  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140023275  mov     [rsp+28h+pExceptionObject], rax
0x14002327a  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140023281  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140023286  call    _CxxThrowException_0
```

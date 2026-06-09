# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___::[Windows::Foundation::IAsyncOperation_Platform::String___]::GetResults

- ea: `0x1800ced70`
- end: `0x1800cee15`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___::[Windows::Foundation::IAsyncOperation_Platform::String___]::GetResults`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800cee20`

## callees

- `0x180005e50`
- `0x18000617a`
- `0x18003feb4`
- `0x18003ff8c`
- `0x1800cae2c`
- `0x1800ced70`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800cedbe`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800cedeb`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800cedbe`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1800cedeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_8d16998f3a7765ec946ee0f4259e66ba___::_Windows::Foundation::IAsyncOperation_Platform::String____::GetResults(
        __int64 a1)
{
  int v1; // eax
  HSTRING v2; // rdi
  __int64 v3; // rbx
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  v1 = *(_DWORD *)(a1 + 56);
  if ( v1 == 3 )
  {
    Exception = Platform::Exception::CreateException(*(unsigned int *)(a1 + 60));
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  if ( v1 != 1 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  v2 = (HSTRING)Concurrency::task<Platform::String __gc *>::get(a1 + 104);
  pExceptionObject = (__int64)v2;
  v3 = __abi_winrt_ptrto_string_ctor(v2);
  WindowsDeleteString_0(v2);
  return v3;
}

```

## disassembly

```asm
0x1800ced70  mov     [rsp+arg_10], rbx
0x1800ced75  push    rdi
0x1800ced76  sub     rsp, 20h
0x1800ced7a  mov     eax, [rcx+38h]
0x1800ced7d  cmp     eax, 3
0x1800ced80  jz      short loc_1800CEDE8
0x1800ced82  cmp     eax, 1
0x1800ced85  jnz     short loc_1800CEDB9
0x1800ced87  add     rcx, 68h ; 'h'
0x1800ced8b  call    ?get@?$task@PE$AAVString@Platform@@@Concurrency@@QEBAPE$AAVString@Platform@@XZ; Concurrency::task<Platform::String *>::get(void)
0x1800ced90  mov     rdi, rax
0x1800ced93  mov     [rsp+28h+pExceptionObject], rax
0x1800ced98  mov     rcx, rax
0x1800ced9b  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800ceda0  mov     rbx, rax
0x1800ceda3  mov     rcx, rdi; string
0x1800ceda6  call    WindowsDeleteString_0
0x1800cedab  mov     rax, rbx
0x1800cedae  mov     rbx, [rsp+28h+arg_10]
0x1800cedb3  add     rsp, 20h
0x1800cedb7  pop     rdi
0x1800cedb8  retn
0x1800cedb9  mov     ecx, 8000000Eh
0x1800cedbe  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800cedc4  mov     [rsp+28h+arg_8], rax
0x1800cedc9  mov     rcx, rax
0x1800cedcc  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cedd1  mov     [rsp+28h+pExceptionObject], rax
0x1800cedd6  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800ceddd  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800cede2  call    _CxxThrowException_0
0x1800cede8  mov     ecx, [rcx+3Ch]
0x1800cedeb  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1800cedf1  mov     [rsp+28h+arg_8], rax
0x1800cedf6  mov     rcx, rax
0x1800cedf9  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cedfe  mov     [rsp+28h+pExceptionObject], rax
0x1800cee03  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1800cee0a  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800cee0f  call    _CxxThrowException_0
```

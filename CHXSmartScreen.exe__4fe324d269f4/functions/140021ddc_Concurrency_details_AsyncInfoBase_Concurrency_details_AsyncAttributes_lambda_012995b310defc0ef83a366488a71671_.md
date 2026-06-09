# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Completed::[Windows::Foundation::IAsyncAction]::get

- ea: `0x140021ddc`
- end: `0x140021e3a`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Completed::[Windows::Foundation::IAsyncAction]::get`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140021e40`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x140021ddc`
- `0x140035010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140021e10`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140021e10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Completed::_Windows::Foundation::IAsyncAction_::get(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  if ( *(_DWORD *)(a1 + 48) == 5 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  v1 = *(_QWORD *)(a1 + 40);
  if ( v1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 8LL))(*(_QWORD *)(a1 + 40));
  return v1;
}

```

## disassembly

```asm
0x140021ddc  push    rbx
0x140021dde  sub     rsp, 20h
0x140021de2  mov     eax, [rcx+30h]
0x140021de5  cmp     eax, 5
0x140021de8  jz      short loc_140021E0B
0x140021dea  mov     rbx, [rcx+28h]
0x140021dee  test    rbx, rbx
0x140021df1  jz      short loc_140021E02
0x140021df3  mov     rcx, [rbx]
0x140021df6  mov     rax, [rcx+8]
0x140021dfa  mov     rcx, rbx
0x140021dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021e02  mov     rax, rbx
0x140021e05  add     rsp, 20h
0x140021e09  pop     rbx
0x140021e0a  retn
0x140021e0b  mov     ecx, 8000000Eh
0x140021e10  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x140021e16  mov     [rsp+28h+arg_8], rax
0x140021e1b  mov     rcx, rax
0x140021e1e  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140021e23  mov     [rsp+28h+pExceptionObject], rax
0x140021e28  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140021e2f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140021e34  call    _CxxThrowException_0
```

# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::[Windows::Foundation::IAsyncInfo]::__abi_Windows_Foundation_IAsyncInfo____abi_get_ErrorCode

- ea: `0x140021a80`
- end: `0x140021b08`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::[Windows::Foundation::IAsyncInfo]::__abi_Windows_Foundation_IAsyncInfo____abi_get_ErrorCode`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140021b10`

## callees

- `0x14000342d`
- `0x140021a80`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140021aab`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140021aab`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_Windows::Foundation::IAsyncInfo_::__abi_Windows_Foundation_IAsyncInfo____abi_get_ErrorCode(
        __int64 a1,
        _DWORD *a2)
{
  int v5; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_BYTE *)(a1 + 68) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  memset_0(&v5, 0, sizeof(v5));
  try
  {
    *a2 = v5;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)(a1 + 16) + 88LL))(a1 + 16, &v5);
    *a2 = v5;
  }
  catch ( ... )
  {
    __abi_translateCurrentException(0);
  }
  return 0;
}

```

## disassembly

```asm
0x140021a80  mov     [rsp+arg_10], rbx
0x140021a85  mov     [rsp+arg_18], rsi
0x140021a8a  push    rdi
0x140021a8b  sub     rsp, 30h
0x140021a8f  mov     rax, cs:__security_cookie
0x140021a96  xor     rax, rsp
0x140021a99  mov     [rsp+38h+var_10], rax
0x140021a9e  mov     rdi, rdx
0x140021aa1  mov     rsi, rcx
0x140021aa4  xor     ebx, ebx
0x140021aa6  cmp     [rcx+44h], bl
0x140021aa9  jz      short loc_140021AB2
0x140021aab  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140021ab1  int     3; Trap to Debugger
0x140021ab2  xor     edx, edx; Val
0x140021ab4  lea     r8d, [rdx+4]; Size
0x140021ab8  lea     rcx, [rsp+38h+var_18]; void *
0x140021abd  call    memset_0
0x140021ac2  mov     eax, [rsp+38h+var_18]
0x140021ac6  mov     [rdi], eax
0x140021ac8  lea     rcx, [rsi+10h]
0x140021acc  mov     rax, [rcx]
0x140021acf  lea     rdx, [rsp+38h+var_18]
0x140021ad4  mov     rax, [rax+58h]
0x140021ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021add  mov     eax, [rsp+38h+var_18]
0x140021ae1  mov     [rdi], eax
0x140021ae3  jmp     short loc_140021AE9
0x140021ae5  mov     ebx, [rsp+38h+var_18]
0x140021ae9  mov     eax, ebx
0x140021aeb  mov     rcx, [rsp+38h+var_10]
0x140021af0  xor     rcx, rsp; StackCookie
0x140021af3  call    __security_check_cookie
0x140021af8  mov     rbx, [rsp+38h+arg_10]
0x140021afd  mov     rsi, [rsp+38h+arg_18]
0x140021b02  add     rsp, 30h
0x140021b06  pop     rdi
0x140021b07  retn
```

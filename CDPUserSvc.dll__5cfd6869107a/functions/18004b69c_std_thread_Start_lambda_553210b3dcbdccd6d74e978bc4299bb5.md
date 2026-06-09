# std::thread::_Start__lambda_553210b3dcbdccd6d74e978bc4299bb5___

- ea: `0x18004b69c`
- end: `0x18004b730`
- name: `std::thread::_Start__lambda_553210b3dcbdccd6d74e978bc4299bb5___`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026400`

## callees

- `0x18002c5a0`
- `0x18004b69c`
- `0x18004b9a0`
- `0x18004bb24`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004b729`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004b729`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004b6ed`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004b6ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start__lambda_553210b3dcbdccd6d74e978bc4299bb5___(__int64 a1, __int64 a2)
{
  void *v4; // rdi
  __int64 v5; // rax
  void *v7; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(0xB8u);
  lambda_553210b3dcbdccd6d74e978bc4299bb5_::_lambda_553210b3dcbdccd6d74e978bc4299bb5_(v4, a2);
  v7 = v4;
  v5 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18004B72FLL);
  }
  v7 = 0;
  return std::unique_ptr_std::tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5____std::default_delete_std::tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5_______::_unique_ptr_std::tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5____std::default_delete_std::tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5_______(&v7);
}

```

## disassembly

```asm
0x18004b69c  mov     [rsp+arg_8], rbx
0x18004b6a1  mov     [rsp+arg_10], rsi
0x18004b6a6  push    rdi
0x18004b6a7  sub     rsp, 30h
0x18004b6ab  mov     rbx, rdx
0x18004b6ae  mov     rsi, rcx
0x18004b6b1  mov     ecx, 0B8h; Size
0x18004b6b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b6bb  mov     rdi, rax
0x18004b6be  mov     rdx, rbx
0x18004b6c1  mov     rcx, rax
0x18004b6c4  call    _lambda_553210b3dcbdccd6d74e978bc4299bb5____lambda_553210b3dcbdccd6d74e978bc4299bb5_
0x18004b6c9  mov     [rsp+38h+arg_0], rdi
0x18004b6ce  lea     rbx, [rsi+8]
0x18004b6d2  mov     [rsp+38h+var_10], rbx
0x18004b6d7  mov     [rsp+38h+var_18], 0
0x18004b6df  mov     r9, rdi
0x18004b6e2  lea     r8, std__thread___Invoke_std__tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5____0_
0x18004b6e9  xor     edx, edx
0x18004b6eb  xor     ecx, ecx
0x18004b6ed  call    cs:__imp__o__beginthreadex
0x18004b6f3  mov     [rsi], rax
0x18004b6f6  test    rax, rax
0x18004b6f9  jz      short loc_18004B71E
0x18004b6fb  mov     [rsp+38h+arg_0], 0
0x18004b704  lea     rcx, [rsp+38h+arg_0]
0x18004b709  call    std__unique_ptr_std__tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5____std__default_delete_std__tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5__________unique_ptr_std__tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5____std__default_delete_std__tuple__lambda_553210b3dcbdccd6d74e978bc4299bb5_______
0x18004b70e  mov     rbx, [rsp+38h+arg_8]
0x18004b713  mov     rsi, [rsp+38h+arg_10]
0x18004b718  add     rsp, 30h
0x18004b71c  pop     rdi
0x18004b71d  retn
0x18004b71e  mov     dword ptr [rbx], 0
0x18004b724  mov     ecx, 6
0x18004b729  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

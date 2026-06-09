# std::thread::thread__lambda_23ce11eb9ed0d697c6a40868e54c794d__0_

- ea: `0x180047504`
- end: `0x180047589`
- name: `std::thread::thread__lambda_23ce11eb9ed0d697c6a40868e54c794d__0_`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180049100`

## callees

- `0x180007d4c`
- `0x180047504`
- `0x180048260`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180047582`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180047582`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180047548`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180047548`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::thread__lambda_23ce11eb9ed0d697c6a40868e54c794d__0_(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rax
  _QWORD *v7; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(8u);
  *v4 = *a2;
  v7 = v4;
  v5 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180047588LL);
  }
  v7 = 0;
  std::unique_ptr_std::tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d____std::default_delete_std::tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d_______::_unique_ptr_std::tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d____std::default_delete_std::tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d_______(&v7);
  return a1;
}

```

## disassembly

```asm
0x180047504  mov     [rsp+arg_8], rbx
0x180047509  push    rdi
0x18004750a  sub     rsp, 30h
0x18004750e  mov     rbx, rdx
0x180047511  mov     rdi, rcx
0x180047514  mov     ecx, 8; Size
0x180047519  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004751e  mov     rdx, [rbx]
0x180047521  mov     [rax], rdx
0x180047524  mov     [rsp+38h+arg_0], rax
0x180047529  lea     rbx, [rdi+8]
0x18004752d  mov     [rsp+38h+var_10], rbx
0x180047532  mov     [rsp+38h+var_18], 0
0x18004753a  mov     r9, rax
0x18004753d  lea     r8, std__thread___Invoke_std__tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d____0_
0x180047544  xor     edx, edx
0x180047546  xor     ecx, ecx
0x180047548  call    cs:__imp__o__beginthreadex
0x18004754e  mov     [rdi], rax
0x180047551  test    rax, rax
0x180047554  jz      short loc_180047577
0x180047556  mov     [rsp+38h+arg_0], 0
0x18004755f  lea     rcx, [rsp+38h+arg_0]
0x180047564  call    std__unique_ptr_std__tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d____std__default_delete_std__tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d__________unique_ptr_std__tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d____std__default_delete_std__tuple__lambda_23ce11eb9ed0d697c6a40868e54c794d_______
0x180047569  mov     rax, rdi
0x18004756c  mov     rbx, [rsp+38h+arg_8]
0x180047571  add     rsp, 30h
0x180047575  pop     rdi
0x180047576  retn
0x180047577  mov     dword ptr [rbx], 0
0x18004757d  mov     ecx, 6
0x180047582  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

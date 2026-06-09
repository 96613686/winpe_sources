# std::thread::thread__lambda_f3d8809f5612c984a5365a493d0aaa66__0_

- ea: `0x1800545a4`
- end: `0x180054629`
- name: `std::thread::thread__lambda_f3d8809f5612c984a5365a493d0aaa66__0_`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c3a8`

## callees

- `0x180026268`
- `0x18002c5a0`
- `0x1800545a4`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180054622`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180054622`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800545e8`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800545e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::thread__lambda_f3d8809f5612c984a5365a493d0aaa66__0_(__int64 a1, _QWORD *a2)
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
         std::thread::_Invoke_std::tuple__lambda_f3d8809f5612c984a5365a493d0aaa66____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180054628LL);
  }
  v7 = 0;
  std::unique_ptr_std::tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c____std::default_delete_std::tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c_______::_unique_ptr_std::tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c____std::default_delete_std::tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c_______(&v7);
  return a1;
}

```

## disassembly

```asm
0x1800545a4  mov     [rsp+arg_8], rbx
0x1800545a9  push    rdi
0x1800545aa  sub     rsp, 30h
0x1800545ae  mov     rbx, rdx
0x1800545b1  mov     rdi, rcx
0x1800545b4  mov     ecx, 8; Size
0x1800545b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800545be  mov     rdx, [rbx]
0x1800545c1  mov     [rax], rdx
0x1800545c4  mov     [rsp+38h+arg_0], rax
0x1800545c9  lea     rbx, [rdi+8]
0x1800545cd  mov     [rsp+38h+var_10], rbx
0x1800545d2  mov     [rsp+38h+var_18], 0
0x1800545da  mov     r9, rax
0x1800545dd  lea     r8, std__thread___Invoke_std__tuple__lambda_f3d8809f5612c984a5365a493d0aaa66____0_
0x1800545e4  xor     edx, edx
0x1800545e6  xor     ecx, ecx
0x1800545e8  call    cs:__imp__o__beginthreadex
0x1800545ee  mov     [rdi], rax
0x1800545f1  test    rax, rax
0x1800545f4  jz      short loc_180054617
0x1800545f6  mov     [rsp+38h+arg_0], 0
0x1800545ff  lea     rcx, [rsp+38h+arg_0]
0x180054604  call    std__unique_ptr_std__tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c____std__default_delete_std__tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c__________unique_ptr_std__tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c____std__default_delete_std__tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c_______
0x180054609  mov     rax, rdi
0x18005460c  mov     rbx, [rsp+38h+arg_8]
0x180054611  add     rsp, 30h
0x180054615  pop     rdi
0x180054616  retn
0x180054617  mov     dword ptr [rbx], 0
0x18005461d  mov     ecx, 6
0x180054622  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

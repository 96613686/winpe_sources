# std::thread::_Start__lambda_cd44e955c89ad0a4f8ada30fcefeb60e___

- ea: `0x18005b58c`
- end: `0x18005b64a`
- name: `std::thread::_Start__lambda_cd44e955c89ad0a4f8ada30fcefeb60e___`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005cfc0`

## callees

- `0x1800225d0`
- `0x18005b58c`
- `0x18005b9ec`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005b643`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005b643`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18005b60c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18005b60c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start__lambda_cd44e955c89ad0a4f8ada30fcefeb60e___(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rax
  _QWORD *v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(0x18u);
  *v4 = 0;
  if ( v4 != a2 )
  {
    *v4 = *a2;
    *a2 = 0;
  }
  v4[1] = a2[1];
  v5 = a2 + 2;
  v4[2] = 0;
  if ( v4 + 2 != v5 )
  {
    v4[2] = *v5;
    *v5 = 0;
  }
  v8 = v4;
  v6 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18005B649LL);
  }
  v8 = 0;
  return std::unique_ptr_std::tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e____std::default_delete_std::tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e_______::_unique_ptr_std::tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e____std::default_delete_std::tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e_______(&v8);
}

```

## disassembly

```asm
0x18005b58c  mov     [rsp+arg_8], rbx
0x18005b591  push    rdi
0x18005b592  sub     rsp, 30h
0x18005b596  mov     rbx, rdx
0x18005b599  mov     rdi, rcx
0x18005b59c  mov     ecx, 18h; Size
0x18005b5a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b5a6  mov     r9, rax
0x18005b5a9  mov     qword ptr [rax], 0
0x18005b5b0  cmp     rax, rbx
0x18005b5b3  jz      short loc_18005B5C2
0x18005b5b5  mov     r8, [rbx]
0x18005b5b8  mov     [rax], r8
0x18005b5bb  mov     qword ptr [rbx], 0
0x18005b5c2  mov     rcx, [rbx+8]
0x18005b5c6  mov     [rax+8], rcx
0x18005b5ca  lea     rcx, [rax+10h]
0x18005b5ce  add     rbx, 10h
0x18005b5d2  mov     qword ptr [rcx], 0
0x18005b5d9  cmp     rcx, rbx
0x18005b5dc  jz      short loc_18005B5EB
0x18005b5de  mov     rax, [rbx]
0x18005b5e1  mov     [rcx], rax
0x18005b5e4  mov     qword ptr [rbx], 0
0x18005b5eb  mov     [rsp+38h+arg_0], r9
0x18005b5f0  lea     rbx, [rdi+8]
0x18005b5f4  mov     [rsp+38h+var_10], rbx
0x18005b5f9  mov     [rsp+38h+var_18], 0
0x18005b601  lea     r8, std__thread___Invoke_std__tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e____0_
0x18005b608  xor     edx, edx
0x18005b60a  xor     ecx, ecx
0x18005b60c  call    cs:__imp__o__beginthreadex
0x18005b612  mov     [rdi], rax
0x18005b615  test    rax, rax
0x18005b618  jz      short loc_18005B638
0x18005b61a  mov     [rsp+38h+arg_0], 0
0x18005b623  lea     rcx, [rsp+38h+arg_0]
0x18005b628  call    std__unique_ptr_std__tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e____std__default_delete_std__tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e__________unique_ptr_std__tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e____std__default_delete_std__tuple__lambda_cd44e955c89ad0a4f8ada30fcefeb60e_______
0x18005b62d  mov     rbx, [rsp+38h+arg_8]
0x18005b632  add     rsp, 30h
0x18005b636  pop     rdi
0x18005b637  retn
0x18005b638  mov     dword ptr [rbx], 0
0x18005b63e  mov     ecx, 6
0x18005b643  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

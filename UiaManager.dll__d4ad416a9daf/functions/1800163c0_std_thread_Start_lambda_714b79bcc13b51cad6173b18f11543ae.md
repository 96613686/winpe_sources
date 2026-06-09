# std::thread::_Start__lambda_714b79bcc13b51cad6173b18f11543ae___

- ea: `0x1800163c0`
- end: `0x180016454`
- name: `std::thread::_Start__lambda_714b79bcc13b51cad6173b18f11543ae___`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015e54`

## callees

- `0x1800163c0`
- `0x180043a8c`
- `0x1800782c4`
- `0x1800784c4`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001644d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001644d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180016411`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180016411`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start__lambda_714b79bcc13b51cad6173b18f11543ae___(__int64 a1, __int64 a2)
{
  void *v4; // rdi
  __int64 v5; // rax
  void *v7; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(0x78u);
  lambda_714b79bcc13b51cad6173b18f11543ae_::_lambda_714b79bcc13b51cad6173b18f11543ae__0(v4, a2);
  v7 = v4;
  v5 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_714b79bcc13b51cad6173b18f11543ae____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180016453LL);
  }
  v7 = 0;
  return std::unique_ptr_std::tuple__lambda_714b79bcc13b51cad6173b18f11543ae____std::default_delete_std::tuple__lambda_714b79bcc13b51cad6173b18f11543ae_______::_unique_ptr_std::tuple__lambda_714b79bcc13b51cad6173b18f11543ae____std::default_delete_std::tuple__lambda_714b79bcc13b51cad6173b18f11543ae_______(&v7);
}

```

## disassembly

```asm
0x1800163c0  mov     [rsp+arg_8], rbx
0x1800163c5  mov     [rsp+arg_10], rsi
0x1800163ca  push    rdi
0x1800163cb  sub     rsp, 30h
0x1800163cf  mov     rbx, rdx
0x1800163d2  mov     rsi, rcx
0x1800163d5  mov     ecx, 78h ; 'x'; Size
0x1800163da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800163df  mov     rdi, rax
0x1800163e2  mov     rdx, rbx
0x1800163e5  mov     rcx, rax
0x1800163e8  call    _lambda_714b79bcc13b51cad6173b18f11543ae____lambda_714b79bcc13b51cad6173b18f11543ae__0
0x1800163ed  mov     [rsp+38h+arg_0], rdi
0x1800163f2  lea     rbx, [rsi+8]
0x1800163f6  mov     [rsp+38h+var_10], rbx
0x1800163fb  mov     [rsp+38h+var_18], 0
0x180016403  mov     r9, rdi
0x180016406  lea     r8, std__thread___Invoke_std__tuple__lambda_714b79bcc13b51cad6173b18f11543ae____0_
0x18001640d  xor     edx, edx
0x18001640f  xor     ecx, ecx
0x180016411  call    cs:__imp__o__beginthreadex
0x180016417  mov     [rsi], rax
0x18001641a  test    rax, rax
0x18001641d  jz      short loc_180016442
0x18001641f  mov     [rsp+38h+arg_0], 0
0x180016428  lea     rcx, [rsp+38h+arg_0]
0x18001642d  call    std__unique_ptr_std__tuple__lambda_714b79bcc13b51cad6173b18f11543ae____std__default_delete_std__tuple__lambda_714b79bcc13b51cad6173b18f11543ae__________unique_ptr_std__tuple__lambda_714b79bcc13b51cad6173b18f11543ae____std__default_delete_std__tuple__lambda_714b79bcc13b51cad6173b18f11543ae_______
0x180016432  mov     rbx, [rsp+38h+arg_8]
0x180016437  mov     rsi, [rsp+38h+arg_10]
0x18001643c  add     rsp, 30h
0x180016440  pop     rdi
0x180016441  retn
0x180016442  mov     dword ptr [rbx], 0
0x180016448  mov     ecx, 6
0x18001644d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

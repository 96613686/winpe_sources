# std::thread::thread__lambda_8adb629ae038cbc525f1291e566af1ba__0_

- ea: `0x18001b3ac`
- end: `0x18001b42d`
- name: `std::thread::thread__lambda_8adb629ae038cbc525f1291e566af1ba__0_`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a358`

## callees

- `0x1800037c0`
- `0x18001b3ac`
- `0x1800206b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001b3ec`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001b3ec`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b426`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001b426`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::thread__lambda_8adb629ae038cbc525f1291e566af1ba__0_(__int64 a1, void *a2)
{
  __int64 v3; // rax
  void *v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  v5 = operator new(1u);
  v3 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____0_,
         v5,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v3;
  if ( !v3 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18001B42CLL);
  }
  v5 = 0;
  std::unique_ptr_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std::default_delete_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba_______::_unique_ptr_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std::default_delete_std::tuple__lambda_8adb629ae038cbc525f1291e566af1ba_______(&v5);
  return a1;
}

```

## disassembly

```asm
0x18001b3ac  mov     [rsp+arg_0], rbx
0x18001b3b1  mov     [rsp+arg_8], rdx
0x18001b3b6  push    rdi
0x18001b3b7  sub     rsp, 30h
0x18001b3bb  mov     rbx, rcx
0x18001b3be  mov     ecx, 1; Size
0x18001b3c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b3c8  mov     [rsp+38h+arg_8], rax
0x18001b3cd  lea     rdi, [rbx+8]
0x18001b3d1  mov     [rsp+38h+var_10], rdi
0x18001b3d6  mov     [rsp+38h+var_18], 0
0x18001b3de  mov     r9, rax
0x18001b3e1  lea     r8, std__thread___Invoke_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba____0_
0x18001b3e8  xor     edx, edx
0x18001b3ea  xor     ecx, ecx
0x18001b3ec  call    cs:__imp__o__beginthreadex
0x18001b3f2  mov     [rbx], rax
0x18001b3f5  test    rax, rax
0x18001b3f8  jz      short loc_18001B41B
0x18001b3fa  mov     [rsp+38h+arg_8], 0
0x18001b403  lea     rcx, [rsp+38h+arg_8]
0x18001b408  call    std__unique_ptr_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std__default_delete_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba__________unique_ptr_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba____std__default_delete_std__tuple__lambda_8adb629ae038cbc525f1291e566af1ba_______
0x18001b40d  mov     rax, rbx
0x18001b410  mov     rbx, [rsp+38h+arg_0]
0x18001b415  add     rsp, 30h
0x18001b419  pop     rdi
0x18001b41a  retn
0x18001b41b  mov     dword ptr [rdi], 0
0x18001b421  mov     ecx, 6
0x18001b426  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

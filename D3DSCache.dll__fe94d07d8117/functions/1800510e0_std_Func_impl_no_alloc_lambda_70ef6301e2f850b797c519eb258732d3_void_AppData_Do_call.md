# std::_Func_impl_no_alloc__lambda_70ef6301e2f850b797c519eb258732d3__void_AppData_&_::_Do_call

- ea: `0x1800510e0`
- end: `0x18005114e`
- name: `std::_Func_impl_no_alloc__lambda_70ef6301e2f850b797c519eb258732d3__void_AppData_&_::_Do_call`
- size: `110`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003710`
- `0x1800510e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005112d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005112d`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_70ef6301e2f850b797c519eb258732d3__void_AppData___::_Do_call(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rbx
  __int64 j; // rdi
  _QWORD *v6; // r9

  v2 = *(_QWORD **)(a2 + 72);
  for ( i = *(_QWORD **)(a2 + 64); i != v2; i += 6 )
  {
    for ( j = 0; j != 3; ++j )
    {
      if ( i[3] <= 7u )
        v6 = i;
      else
        v6 = (_QWORD *)*i;
      StringCchPrintfW(*(unsigned __int16 **)(a1 + 16), 0x104u, L"%s%s", v6, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * j));
      DeleteFileW(*(LPCWSTR *)(a1 + 16));
    }
  }
}

```

## disassembly

```asm
0x1800510e0  push    rbx
0x1800510e2  push    rbp
0x1800510e3  push    rsi
0x1800510e4  push    rdi
0x1800510e5  sub     rsp, 38h
0x1800510e9  mov     rsi, [rdx+48h]
0x1800510ed  mov     rbp, rcx
0x1800510f0  mov     rbx, [rdx+40h]
0x1800510f4  jmp     short loc_180051140
0x1800510f6  xor     edi, edi
0x1800510f8  cmp     qword ptr [rbx+18h], 7
0x1800510fd  mov     rax, [rbp+8]
0x180051101  mov     rcx, [rax+rdi*8]
0x180051105  jbe     short loc_18005110C
0x180051107  mov     r9, [rbx]
0x18005110a  jmp     short loc_18005110F
0x18005110c  mov     r9, rbx
0x18005110f  mov     [rsp+58h+var_38], rcx
0x180051114  lea     r8, aSS_2; "%s%s"
0x18005111b  mov     rcx, [rbp+10h]; unsigned __int16 *
0x18005111f  mov     edx, 104h; unsigned __int64
0x180051124  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051129  mov     rcx, [rbp+10h]; lpFileName
0x18005112d  call    cs:__imp_DeleteFileW
0x180051133  inc     rdi
0x180051136  cmp     rdi, 3
0x18005113a  jnz     short loc_1800510F8
0x18005113c  add     rbx, 30h ; '0'
0x180051140  cmp     rbx, rsi
0x180051143  jnz     short loc_1800510F6
0x180051145  add     rsp, 38h
0x180051149  pop     rdi
0x18005114a  pop     rsi
0x18005114b  pop     rbp
0x18005114c  pop     rbx
0x18005114d  retn
```

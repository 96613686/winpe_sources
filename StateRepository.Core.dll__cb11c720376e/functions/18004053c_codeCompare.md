# codeCompare

- ea: `0x18004053c`
- end: `0x1800405ec`
- name: `codeCompare`
- size: `176`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, int, int, char, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800355c0`
- `0x18003e5c0`
- `0x18005c310`
- `0x18005f420`

## callees

- `0x180005c54`
- `0x180011d80`
- `0x180012c7c`
- `0x180012d50`
- `0x18003a958`
- `0x18004053c`

## pseudocode

```c
__int64 __fastcall codeCompare(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6, int a7, char a8, int a9)
{
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rdx
  unsigned __int16 v18; // bx
  unsigned int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // r9d

  if ( *(_DWORD *)(a1 + 52) )
    return 0;
  v14 = a2;
  v15 = a3;
  if ( !a9 )
  {
    v14 = a3;
    v15 = a2;
  }
  v16 = sqlite3BinaryCompareCollSeq(a1, v15, v14);
  LOBYTE(v17) = sqlite3ExprAffinity(a3);
  v18 = (unsigned __int8)(a8 | sqlite3CompareAffinity(a2, v17));
  v19 = sqlite3VdbeAddOp4(*(_QWORD *)(a1 + 16), a4, a6, a7, a5, v16, -2);
  sqlite3VdbeChangeP5(*(_QWORD *)(a1 + 16), v18, v20, v19);
  return v21;
}

```

## disassembly

```asm
0x18004053c  push    rbx
0x18004053e  push    rbp
0x18004053f  push    rsi
0x180040540  push    rdi
0x180040541  push    r14
0x180040543  sub     rsp, 40h
0x180040547  cmp     dword ptr [rcx+34h], 0
0x18004054b  mov     r14d, r9d
0x18004054e  mov     rbx, r8
0x180040551  mov     rbp, rdx
0x180040554  mov     rsi, rcx
0x180040557  jz      short loc_180040560
0x180040559  xor     eax, eax
0x18004055b  jmp     loc_1800405E1
0x180040560  mov     eax, [rsp+68h+arg_40]
0x180040567  mov     r8, rbp
0x18004056a  test    eax, eax
0x18004056c  mov     rdx, rbx
0x18004056f  cmovz   r8, rbx
0x180040573  cmovz   rdx, rbp
0x180040577  call    sqlite3BinaryCompareCollSeq
0x18004057c  mov     rcx, rbx
0x18004057f  mov     rdi, rax
0x180040582  call    sqlite3ExprAffinity
0x180040587  mov     dl, al
0x180040589  mov     rcx, rbp
0x18004058c  call    sqlite3CompareAffinity
0x180040591  or      al, [rsp+68h+arg_38]
0x180040598  mov     edx, r14d
0x18004059b  mov     r9d, [rsp+68h+arg_30]
0x1800405a3  mov     r8d, [rsp+68h+arg_28]
0x1800405ab  mov     rcx, [rsi+10h]
0x1800405af  movzx   ebx, al
0x1800405b2  mov     eax, [rsp+68h+arg_20]
0x1800405b9  mov     [rsp+68h+var_38], 0FFFFFFFEh
0x1800405c1  mov     [rsp+68h+var_40], rdi
0x1800405c6  mov     [rsp+68h+var_48], eax
0x1800405ca  call    sqlite3VdbeAddOp4
0x1800405cf  mov     rcx, [rsi+10h]
0x1800405d3  movzx   edx, bx
0x1800405d6  mov     r9d, eax
0x1800405d9  call    sqlite3VdbeChangeP5
0x1800405de  mov     eax, r9d
0x1800405e1  add     rsp, 40h
0x1800405e5  pop     r14
0x1800405e7  pop     rdi
0x1800405e8  pop     rsi
0x1800405e9  pop     rbp
0x1800405ea  pop     rbx
0x1800405eb  retn
```

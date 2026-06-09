# codeVectorCompare

- ea: `0x18005f420`
- end: `0x18005f70e`
- name: `codeVectorCompare`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800355c0`

## callees

- `0x1800119e0`
- `0x1800134a0`
- `0x180036688`
- `0x1800370c0`
- `0x18003ff00`
- `0x18004053c`
- `0x18005f420`
- `0x180060ce8`
- `0x18006e604`
- `0x18006ec88`

## pseudocode

```c
__int64 __fastcall codeVectorCompare(__int64 a1, __int64 a2, int a3, char a4, char a5)
{
  __int64 v5; // r13
  int v9; // eax
  __int64 v10; // rdx
  int v11; // r12d
  __int64 result; // rax
  int v13; // eax
  __int64 v14; // r9
  int v15; // r8d
  __int64 v16; // rbx
  char v17; // cl
  unsigned __int8 v18; // si
  int v19; // r13d
  int v20; // r9d
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // [rsp+50h] [rbp-31h] BYREF
  int v27; // [rsp+54h] [rbp-2Dh] BYREF
  int v28; // [rsp+58h] [rbp-29h]
  int v29; // [rsp+5Ch] [rbp-25h]
  int v30; // [rsp+60h] [rbp-21h]
  int v31; // [rsp+64h] [rbp-1Dh]
  int v32; // [rsp+68h] [rbp-19h]
  int v33; // [rsp+6Ch] [rbp-15h]
  int v34; // [rsp+70h] [rbp-11h]
  __int64 v35; // [rsp+78h] [rbp-9h] BYREF
  __int64 v36; // [rsp+80h] [rbp-1h] BYREF
  __int64 v37; // [rsp+88h] [rbp+7h]
  __int64 v38; // [rsp+90h] [rbp+Fh]
  unsigned int v39; // [rsp+E0h] [rbp+5Fh]
  int v40; // [rsp+E8h] [rbp+67h]
  unsigned int v41; // [rsp+F8h] [rbp+77h]

  v5 = *(_QWORD *)(a2 + 24);
  v37 = *(_QWORD *)(a2 + 16);
  v38 = v5;
  v9 = sqlite3ExprVectorSize(v37);
  --*(_DWORD *)(a1 + 72);
  v11 = (*(_DWORD *)(v10 + 4) >> 10) & 1;
  v30 = v9;
  result = *(unsigned int *)(a1 + 72);
  v39 = *(_DWORD *)(a1 + 72);
  if ( *(_DWORD *)(a1 + 52) )
    return result;
  v13 = sqlite3ExprVectorSize(v5);
  if ( v15 != v13 )
    return sqlite3ErrorMsg(a1, "row value misused");
  v16 = *(_QWORD *)(a1 + 16);
  v41 = 0;
  v17 = 57;
  if ( a4 != 56 )
    v17 = a4;
  if ( a4 == 58 )
  {
    v18 = 55;
  }
  else
  {
    v18 = v17;
    if ( a4 == 53 )
      v18 = 54;
  }
  v31 = exprCodeSubselect(a1, v14);
  v32 = exprCodeSubselect(a1, v5);
  sqlite3VdbeAddOp3(v16, 71, 1, a3, 0);
  v19 = 0;
  v20 = v30 - 1;
  v40 = v30 - 1;
  v21 = 71;
  if ( a5 != (char)0x80 )
    v21 = 92;
  v34 = v21;
  while ( 1 )
  {
    v26 = 0;
    v27 = 0;
    v36 = 0;
    v35 = 0;
    if ( v41 )
      *(_DWORD *)(sqlite3VdbeGetOp(v16, v41) + 8) = *(_DWORD *)(v16 + 144);
    v28 = v20;
    v29 = exprVectorRegister(a1, v37, v19, v31, (__int64)&v36, (__int64)&v26);
    v33 = exprVectorRegister(a1, v38, v19, v32, (__int64)&v35, (__int64)&v27);
    v41 = *(_DWORD *)(v16 + 144);
    codeCompare(a1, v36, v35, v18, v29, v33, v39, a5, v11);
    sqlite3ReleaseTempReg(a1, v26);
    sqlite3ReleaseTempReg(v22, v27);
    if ( v18 == 57 )
    {
      v23 = v28;
    }
    else
    {
      if ( v18 != 55 )
        goto LABEL_21;
      v23 = v40;
    }
    if ( v19 < v23 )
      v41 = sqlite3VdbeAddOp3(v16, 59, 0, 0, 0);
LABEL_21:
    if ( a5 == (char)0x80 )
    {
      v24 = 0;
      v25 = 0;
    }
    else
    {
      v24 = v29;
      v25 = v33;
    }
    sqlite3VdbeAddOp3(v16, v34, v24, a3, v25);
    if ( v19 == v40 )
      break;
    if ( v18 == 54 )
    {
      sqlite3VdbeAddOp3(v16, 52, a3, v39, 0);
    }
    else
    {
      sqlite3VdbeAddOp3(v16, 9, 0, v39, 0);
      if ( v19 == v30 - 2 )
        v18 = a4;
    }
    v20 = v40;
    ++v19;
  }
  *(_DWORD *)(sqlite3VdbeGetOp(v16, v41) + 8) = *(_DWORD *)(v16 + 144);
  result = sqlite3VdbeResolveLabel(v16, v39);
  if ( a4 == 53 )
    return sqlite3VdbeAddOp3(v16, 19, a3, a3, 0);
  return result;
}

```

## disassembly

```asm
0x18005f420  mov     [rsp-8+arg_10], rbx
0x18005f425  push    rbp
0x18005f426  push    rsi
0x18005f427  push    rdi
0x18005f428  push    r12
0x18005f42a  push    r13
0x18005f42c  push    r14
0x18005f42e  push    r15
0x18005f430  lea     rbp, [rsp-1Fh]
0x18005f435  sub     rsp, 0A0h
0x18005f43c  mov     r13, [rdx+18h]
0x18005f440  mov     rdi, rcx
0x18005f443  movzx   r14d, r9b
0x18005f447  mov     r15d, r8d
0x18005f44a  mov     r9, [rdx+10h]
0x18005f44e  mov     rcx, r9
0x18005f451  mov     [rbp+4Fh+var_48], r9
0x18005f455  mov     [rbp+4Fh+var_40], r13
0x18005f459  call    sqlite3ExprVectorSize
0x18005f45e  dec     dword ptr [rdi+48h]
0x18005f461  mov     r8d, eax
0x18005f464  mov     r12d, [rdx+4]
0x18005f468  shr     r12d, 0Ah
0x18005f46c  and     r12d, 1
0x18005f470  mov     [rbp+4Fh+var_70], eax
0x18005f473  cmp     dword ptr [rdi+34h], 0
0x18005f477  mov     eax, [rdi+48h]
0x18005f47a  mov     [rbp+4Fh+arg_0], eax
0x18005f47d  jnz     loc_18005F6F3
0x18005f483  mov     rcx, r13
0x18005f486  call    sqlite3ExprVectorSize
0x18005f48b  cmp     r8d, eax
0x18005f48e  jz      short loc_18005F4A4
0x18005f490  lea     rdx, aRowValueMisuse; "row value misused"
0x18005f497  mov     rcx, rdi
0x18005f49a  call    sqlite3ErrorMsg
0x18005f49f  jmp     loc_18005F6F3
0x18005f4a4  mov     rbx, [rdi+10h]
0x18005f4a8  xor     edx, edx
0x18005f4aa  cmp     r14b, 38h ; '8'
0x18005f4ae  mov     [rbp+4Fh+arg_18], edx
0x18005f4b1  lea     ecx, [rdx+39h]
0x18005f4b4  cmovnz  ecx, r14d
0x18005f4b8  lea     eax, [rdx+36h]
0x18005f4bb  cmp     r14b, 3Ah ; ':'
0x18005f4bf  jnz     short loc_18005F4C6
0x18005f4c1  mov     sil, 37h ; '7'
0x18005f4c4  jmp     short loc_18005F4D0
0x18005f4c6  cmp     r14b, 35h ; '5'
0x18005f4ca  movzx   esi, cl
0x18005f4cd  cmovz   esi, eax
0x18005f4d0  mov     rdx, r9
0x18005f4d3  mov     rcx, rdi
0x18005f4d6  call    exprCodeSubselect
0x18005f4db  mov     rdx, r13
0x18005f4de  mov     [rbp+4Fh+var_6C], eax
0x18005f4e1  mov     rcx, rdi
0x18005f4e4  call    exprCodeSubselect
0x18005f4e9  mov     edx, 47h ; 'G'
0x18005f4ee  mov     [rbp+4Fh+var_68], eax
0x18005f4f1  mov     r9d, r15d
0x18005f4f4  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18005f4fc  mov     rcx, rbx
0x18005f4ff  lea     r8d, [rdx-46h]
0x18005f503  call    sqlite3VdbeAddOp3
0x18005f508  mov     r9d, [rbp+4Fh+var_70]
0x18005f50c  xor     r13d, r13d
0x18005f50f  dec     r9d
0x18005f512  cmp     [rbp+4Fh+arg_20], 80h
0x18005f516  mov     [rbp+4Fh+arg_8], r9d
0x18005f51a  lea     ecx, [r13+5Ch]
0x18005f51e  lea     eax, [rcx-15h]
0x18005f521  cmovnz  eax, ecx
0x18005f524  mov     [rbp+4Fh+var_60], eax
0x18005f527  mov     eax, [rbp+4Fh+arg_18]
0x18005f52a  mov     [rbp+4Fh+var_80], 0
0x18005f531  mov     [rbp+4Fh+var_7C], 0
0x18005f538  mov     [rbp+4Fh+var_50], 0
0x18005f540  mov     [rbp+4Fh+var_58], 0
0x18005f548  test    eax, eax
0x18005f54a  jz      short loc_18005F55F
0x18005f54c  mov     edx, eax
0x18005f54e  mov     rcx, rbx
0x18005f551  call    sqlite3VdbeGetOp
0x18005f556  mov     ecx, [rbx+90h]
0x18005f55c  mov     [rax+8], ecx
0x18005f55f  mov     rdx, [rbp+4Fh+var_48]
0x18005f563  lea     rax, [rbp+4Fh+var_80]
0x18005f567  mov     [rsp+0D0h+var_A8], rax
0x18005f56c  mov     r8d, r13d
0x18005f56f  lea     rax, [rbp+4Fh+var_50]
0x18005f573  mov     [rbp+4Fh+var_78], r9d
0x18005f577  mov     r9d, [rbp+4Fh+var_6C]
0x18005f57b  mov     rcx, rdi
0x18005f57e  mov     [rsp+0D0h+var_B0], rax
0x18005f583  call    exprVectorRegister
0x18005f588  mov     r9d, [rbp+4Fh+var_68]
0x18005f58c  mov     r8d, r13d
0x18005f58f  mov     rdx, [rbp+4Fh+var_40]
0x18005f593  mov     rcx, rdi
0x18005f596  mov     [rbp+4Fh+var_74], eax
0x18005f599  lea     rax, [rbp+4Fh+var_7C]
0x18005f59d  mov     [rsp+0D0h+var_A8], rax
0x18005f5a2  lea     rax, [rbp+4Fh+var_58]
0x18005f5a6  mov     [rsp+0D0h+var_B0], rax
0x18005f5ab  call    exprVectorRegister
0x18005f5b0  mov     ecx, [rbp+4Fh+arg_0]
0x18005f5b3  mov     edx, eax
0x18005f5b5  mov     r8, [rbp+4Fh+var_58]
0x18005f5b9  mov     [rsp+0D0h+var_90], r12d
0x18005f5be  mov     [rbp+4Fh+var_64], eax
0x18005f5c1  mov     eax, [rbx+90h]
0x18005f5c7  mov     [rbp+4Fh+arg_18], eax
0x18005f5ca  movzx   eax, [rbp+4Fh+arg_20]
0x18005f5ce  mov     [rsp+0D0h+var_98], eax
0x18005f5d2  mov     [rsp+0D0h+var_A0], ecx
0x18005f5d6  mov     ecx, [rbp+4Fh+var_74]
0x18005f5d9  mov     dword ptr [rsp+0D0h+var_A8], edx
0x18005f5dd  mov     rdx, [rbp+4Fh+var_50]
0x18005f5e1  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x18005f5e5  mov     rcx, rdi
0x18005f5e8  movzx   r9d, sil
0x18005f5ec  call    codeCompare
0x18005f5f1  mov     edx, [rbp+4Fh+var_80]
0x18005f5f4  mov     rcx, rdi
0x18005f5f7  call    sqlite3ReleaseTempReg
0x18005f5fc  mov     edx, [rbp+4Fh+var_7C]
0x18005f5ff  call    sqlite3ReleaseTempReg
0x18005f604  cmp     sil, 39h ; '9'
0x18005f608  jz      short loc_18005F615
0x18005f60a  cmp     sil, 37h ; '7'
0x18005f60e  jnz     short loc_18005F63A
0x18005f610  mov     eax, [rbp+4Fh+arg_8]
0x18005f613  jmp     short loc_18005F618
0x18005f615  mov     eax, [rbp+4Fh+var_78]
0x18005f618  cmp     r13d, eax
0x18005f61b  jge     short loc_18005F63A
0x18005f61d  xor     r9d, r9d
0x18005f620  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18005f628  xor     r8d, r8d
0x18005f62b  mov     rcx, rbx
0x18005f62e  lea     edx, [r9+3Bh]
0x18005f632  call    sqlite3VdbeAddOp3
0x18005f637  mov     [rbp+4Fh+arg_18], eax
0x18005f63a  cmp     [rbp+4Fh+arg_20], 80h
0x18005f63e  jnz     short loc_18005F646
0x18005f640  xor     eax, eax
0x18005f642  xor     ecx, ecx
0x18005f644  jmp     short loc_18005F64C
0x18005f646  mov     eax, [rbp+4Fh+var_74]
0x18005f649  mov     ecx, [rbp+4Fh+var_64]
0x18005f64c  mov     edx, [rbp+4Fh+var_60]
0x18005f64f  mov     r9d, r15d
0x18005f652  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x18005f656  mov     r8d, eax
0x18005f659  mov     rcx, rbx
0x18005f65c  call    sqlite3VdbeAddOp3
0x18005f661  mov     rcx, rbx
0x18005f664  cmp     r13d, [rbp+4Fh+arg_8]
0x18005f668  jz      short loc_18005F6B4
0x18005f66a  mov     r9d, [rbp+4Fh+arg_0]
0x18005f66e  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18005f676  cmp     sil, 36h ; '6'
0x18005f67a  jnz     short loc_18005F68B
0x18005f67c  mov     r8d, r15d
0x18005f67f  mov     edx, 34h ; '4'
0x18005f684  call    sqlite3VdbeAddOp3
0x18005f689  jmp     short loc_18005F6A8
0x18005f68b  xor     r8d, r8d
0x18005f68e  lea     edx, [r8+9]
0x18005f692  call    sqlite3VdbeAddOp3
0x18005f697  mov     ecx, [rbp+4Fh+var_70]
0x18005f69a  add     ecx, 0FFFFFFFEh
0x18005f69d  movzx   esi, sil
0x18005f6a1  cmp     r13d, ecx
0x18005f6a4  cmovz   esi, r14d
0x18005f6a8  mov     r9d, [rbp+4Fh+arg_8]
0x18005f6ac  inc     r13d
0x18005f6af  jmp     loc_18005F527
0x18005f6b4  mov     edx, [rbp+4Fh+arg_18]
0x18005f6b7  call    sqlite3VdbeGetOp
0x18005f6bc  mov     r8d, [rbx+90h]
0x18005f6c3  mov     rcx, rbx
0x18005f6c6  mov     edx, [rbp+4Fh+arg_0]
0x18005f6c9  mov     [rax+8], r8d
0x18005f6cd  call    sqlite3VdbeResolveLabel
0x18005f6d2  cmp     r14b, 35h ; '5'
0x18005f6d6  jnz     short loc_18005F6F3
0x18005f6d8  mov     r9d, r15d
0x18005f6db  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18005f6e3  mov     r8d, r15d
0x18005f6e6  mov     edx, 13h
0x18005f6eb  mov     rcx, rbx
0x18005f6ee  call    sqlite3VdbeAddOp3
0x18005f6f3  mov     rbx, [rsp+0D0h+arg_10]
0x18005f6fb  add     rsp, 0A0h
0x18005f702  pop     r15
0x18005f704  pop     r14
0x18005f706  pop     r13
0x18005f708  pop     r12
0x18005f70a  pop     rdi
0x18005f70b  pop     rsi
0x18005f70c  pop     rbp
0x18005f70d  retn
```

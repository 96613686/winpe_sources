# sqlite3ComputeGeneratedColumns

- ea: `0x180070c9c`
- end: `0x180070e87`
- name: `sqlite3ComputeGeneratedColumns`
- size: `491`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a954`
- `0x180019470`
- `0x1800504a8`

## callees

- `0x18000506c`
- `0x180011bcc`
- `0x1800191d0`
- `0x180051e60`
- `0x180051fd0`
- `0x1800595c4`
- `0x180070c9c`
- `0x180091c30`

## pseudocode

```c
__int64 __fastcall sqlite3ComputeGeneratedColumns(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rcx
  _BYTE *v7; // r8
  __int64 v8; // r9
  __int64 Op; // rax
  int v10; // edx
  int v11; // r9d
  __int64 v12; // rax
  int i; // ecx
  __int16 v14; // ax
  int v15; // r15d
  const char **v16; // r14
  int v17; // edi
  __int64 result; // rax
  __int64 v19; // rbp
  __int16 v20; // ax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int16 v23; // ax
  __int128 v24; // [rsp+20h] [rbp-68h] BYREF
  __int128 v25; // [rsp+30h] [rbp-58h]
  __int128 v26; // [rsp+40h] [rbp-48h]

  v6 = *(_QWORD *)(a1 + 16);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  sqlite3TableAffinity(v6, a3, a2);
  if ( (*(_BYTE *)(a3 + 48) & 0x40) != 0 )
  {
    Op = sqlite3VdbeGetOp(*(_QWORD *)(a1 + 16), (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 144LL) - 1), v7, v8);
    if ( *(_BYTE *)Op == 96 )
    {
      v7 = *(_BYTE **)(Op + 16);
      v10 = 0;
      v11 = 0;
      if ( *v7 )
      {
        do
        {
          v12 = *(_QWORD *)(a3 + 8);
          if ( (*(_BYTE *)(v12 + 24LL * v11 + 18) & 0x20) == 0 )
          {
            if ( (*(_BYTE *)(v12 + 24LL * v11 + 18) & 0x40) != 0 )
              v7[v10] = 64;
            ++v10;
          }
          ++v11;
        }
        while ( v7[v10] );
      }
    }
    else if ( *(_BYTE *)Op == 95 )
    {
      *(_DWORD *)(Op + 12) = 1;
    }
  }
  for ( i = 0; i < *(__int16 *)(a3 + 54); ++i )
  {
    v7 = *(_BYTE **)(a3 + 8);
    v14 = *(_WORD *)&v7[24 * i + 18];
    if ( (v14 & 0x60) != 0 )
      *(_WORD *)&v7[24 * i + 18] = v14 | 0x80;
  }
  *((_QWORD *)&v26 + 1) = a3;
  *((_QWORD *)&v24 + 1) = exprColumnFlagUnion;
  *(_QWORD *)&v25 = 0;
  *(_DWORD *)(a1 + 64) = -a2;
  *((_QWORD *)&v25 + 1) = 0;
  while ( 1 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    result = 0;
    if ( *(__int16 *)(a3 + 54) <= 0 )
      break;
    do
    {
      v19 = *(_QWORD *)(a3 + 8) + 24LL * v17;
      v20 = *(_WORD *)(v19 + 18);
      if ( (v20 & 0x80) != 0 )
      {
        v21 = *(_QWORD *)(a3 + 8) + 24LL * v17;
        *(_WORD *)(v19 + 18) = v20 | 0x100;
        WORD2(v26) = 0;
        v22 = sqlite3ColumnExpr(a3, v21, v7, 128);
        sqlite3WalkExpr(&v24, v22);
        *(_WORD *)(v19 + 18) &= ~0x100u;
        if ( (SBYTE4(v26) & 0x80u) == 0 )
        {
          v15 = 1;
          v23 = sqlite3TableColumnToStorage(a3, (unsigned __int16)v17, v7, 128);
          sqlite3ExprCodeGeneratedColumn(a1, a3, v19, a2 + v23);
          *(_WORD *)(v19 + 18) &= ~0x80u;
        }
        else
        {
          v16 = (const char **)v19;
        }
      }
      result = (unsigned int)*(__int16 *)(a3 + 54);
      ++v17;
    }
    while ( v17 < (int)result );
    if ( !v16 )
      break;
    if ( !v15 )
    {
      result = sqlite3ErrorMsg(a1, "generated column loop on \"%s\"", *v16);
      break;
    }
  }
  *(_DWORD *)(a1 + 64) = 0;
  return result;
}

```

## disassembly

```asm
0x180070c9c  push    rbx
0x180070c9e  push    rbp
0x180070c9f  push    rsi
0x180070ca0  push    rdi
0x180070ca1  push    r12
0x180070ca3  push    r14
0x180070ca5  push    r15
0x180070ca7  sub     rsp, 50h
0x180070cab  xorps   xmm0, xmm0
0x180070cae  mov     rbx, r8
0x180070cb1  mov     r8d, edx
0x180070cb4  mov     r12d, edx
0x180070cb7  mov     rsi, rcx
0x180070cba  mov     rdx, rbx
0x180070cbd  mov     rcx, [rcx+10h]
0x180070cc1  movups  [rsp+88h+var_68], xmm0
0x180070cc6  movups  [rsp+88h+var_58], xmm0
0x180070ccb  movups  [rsp+88h+var_48], xmm0
0x180070cd0  call    sqlite3TableAffinity
0x180070cd5  test    byte ptr [rbx+30h], 40h
0x180070cd9  mov     edi, 1
0x180070cde  jz      short loc_180070D3E
0x180070ce0  mov     rcx, [rsi+10h]
0x180070ce4  mov     edx, [rcx+90h]
0x180070cea  sub     edx, edi
0x180070cec  call    sqlite3VdbeGetOp
0x180070cf1  cmp     byte ptr [rax], 60h ; '`'
0x180070cf4  jnz     short loc_180070D36
0x180070cf6  mov     r8, [rax+10h]
0x180070cfa  xor     edx, edx
0x180070cfc  xor     r9d, r9d
0x180070cff  cmp     [r8], dl
0x180070d02  jz      short loc_180070D3E
0x180070d04  movsxd  rax, r9d
0x180070d07  lea     rcx, [rax+rax*2]
0x180070d0b  mov     rax, [rbx+8]
0x180070d0f  test    byte ptr [rax+rcx*8+12h], 20h
0x180070d14  jnz     short loc_180070D27
0x180070d16  test    byte ptr [rax+rcx*8+12h], 40h
0x180070d1b  jz      short loc_180070D25
0x180070d1d  movsxd  rax, edx
0x180070d20  mov     byte ptr [rax+r8], 40h ; '@'
0x180070d25  add     edx, edi
0x180070d27  movsxd  rax, edx
0x180070d2a  add     r9d, edi
0x180070d2d  cmp     byte ptr [rax+r8], 0
0x180070d32  jnz     short loc_180070D04
0x180070d34  jmp     short loc_180070D3E
0x180070d36  cmp     byte ptr [rax], 5Fh ; '_'
0x180070d39  jnz     short loc_180070D3E
0x180070d3b  mov     [rax+0Ch], edi
0x180070d3e  xor     ecx, ecx
0x180070d40  xor     eax, eax
0x180070d42  mov     r9d, 80h
0x180070d48  cmp     ax, [rbx+36h]
0x180070d4c  jge     short loc_180070D77
0x180070d4e  mov     r8, [rbx+8]
0x180070d52  movsxd  rax, ecx
0x180070d55  lea     rdx, [rax+rax*2]
0x180070d59  movzx   eax, word ptr [r8+rdx*8+12h]
0x180070d5f  test    al, 60h
0x180070d61  jz      short loc_180070D6D
0x180070d63  or      ax, r9w
0x180070d67  mov     [r8+rdx*8+12h], ax
0x180070d6d  movsx   eax, word ptr [rbx+36h]
0x180070d71  add     ecx, edi
0x180070d73  cmp     ecx, eax
0x180070d75  jl      short loc_180070D4E
0x180070d77  lea     rax, exprColumnFlagUnion
0x180070d7e  mov     qword ptr [rsp+88h+var_48+8], rbx
0x180070d83  mov     qword ptr [rsp+88h+var_68+8], rax
0x180070d88  mov     eax, r12d
0x180070d8b  neg     eax
0x180070d8d  mov     qword ptr [rsp+88h+var_58], 0
0x180070d96  mov     [rsi+40h], eax
0x180070d99  mov     qword ptr [rsp+88h+var_58+8], 0
0x180070da2  xor     r15d, r15d
0x180070da5  xor     r14d, r14d
0x180070da8  xor     edi, edi
0x180070daa  xor     eax, eax
0x180070dac  cmp     ax, [rbx+36h]
0x180070db0  jge     loc_180070E71
0x180070db6  movsxd  rax, edi
0x180070db9  lea     rcx, [rax+rax*2]
0x180070dbd  mov     rax, [rbx+8]
0x180070dc1  lea     rbp, [rax+rcx*8]
0x180070dc5  movzx   eax, word ptr [rbp+12h]
0x180070dc9  test    r9b, al
0x180070dcc  jz      short loc_180070E43
0x180070dce  or      ax, 100h
0x180070dd2  mov     rdx, rbp
0x180070dd5  mov     [rbp+12h], ax
0x180070dd9  mov     rcx, rbx
0x180070ddc  xor     eax, eax
0x180070dde  mov     word ptr [rsp+88h+var_48+4], ax
0x180070de3  call    sqlite3ColumnExpr
0x180070de8  mov     rdx, rax
0x180070deb  lea     rcx, [rsp+88h+var_68]
0x180070df0  call    sqlite3WalkExpr
0x180070df5  mov     eax, 0FEFFh
0x180070dfa  mov     r9d, 80h
0x180070e00  and     [rbp+12h], ax
0x180070e04  test    byte ptr [rsp+88h+var_48+4], r9b
0x180070e09  jz      short loc_180070E10
0x180070e0b  mov     r14, rbp
0x180070e0e  jmp     short loc_180070E43
0x180070e10  movzx   edx, di
0x180070e13  mov     rcx, rbx
0x180070e16  mov     r15d, 1
0x180070e1c  call    sqlite3TableColumnToStorage
0x180070e21  movsx   r9d, ax
0x180070e25  mov     r8, rbp
0x180070e28  add     r9d, r12d
0x180070e2b  mov     rdx, rbx
0x180070e2e  mov     rcx, rsi
0x180070e31  call    sqlite3ExprCodeGeneratedColumn
0x180070e36  mov     eax, 0FF7Fh
0x180070e3b  lea     r9d, [r15+7Fh]
0x180070e3f  and     [rbp+12h], ax
0x180070e43  movsx   eax, word ptr [rbx+36h]
0x180070e47  inc     edi
0x180070e49  cmp     edi, eax
0x180070e4b  jl      loc_180070DB6
0x180070e51  test    r14, r14
0x180070e54  jz      short loc_180070E71
0x180070e56  test    r15d, r15d
0x180070e59  jnz     loc_180070DA2
0x180070e5f  mov     r8, [r14]
0x180070e62  lea     rdx, aGeneratedColum_0; "generated column loop on \"%s\""
0x180070e69  mov     rcx, rsi
0x180070e6c  call    sqlite3ErrorMsg
0x180070e71  mov     dword ptr [rsi+40h], 0
0x180070e78  add     rsp, 50h
0x180070e7c  pop     r15
0x180070e7e  pop     r14
0x180070e80  pop     r12
0x180070e82  pop     rdi
0x180070e83  pop     rsi
0x180070e84  pop     rbp
0x180070e85  pop     rbx
0x180070e86  retn
```

# updateVirtualTable

- ea: `0x18005e35c`
- end: `0x18005e8e4`
- name: `updateVirtualTable`
- size: `1416`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1800167c0`

## callees

- `0x180005c54`
- `0x180008894`
- `0x18000c930`
- `0x180010950`
- `0x1800119e0`
- `0x180011d80`
- `0x18003465c`
- `0x180036688`
- `0x180036730`
- `0x18003e1e0`
- `0x18003e944`
- `0x1800573d8`
- `0x18005e35c`
- `0x180060e90`
- `0x1800671d4`
- `0x180067de4`
- `0x18006eb80`
- `0x180092f78`

## pseudocode

```c
__int64 __fastcall updateVirtualTable(
        _QWORD *a1,
        int *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8)
{
  __int64 v8; // rdi
  _QWORD *v9; // rsi
  __int64 v10; // r12
  int v12; // r15d
  __int64 v14; // r8
  unsigned int v15; // r13d
  int v16; // eax
  int v17; // ecx
  int v18; // ebp
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // r13
  __int64 v22; // rcx
  __int64 v23; // rbx
  unsigned int i; // ebp
  __int64 v25; // rax
  int v26; // r8d
  int v27; // r15d
  int *v28; // r13
  int v29; // ebp
  __int64 v30; // r12
  __int64 result; // rax
  int v32; // ebx
  int v33; // ebp
  unsigned int v34; // ecx
  __int64 v35; // r8
  __int64 v36; // r9
  unsigned int v37; // ebp
  int v38; // ebx
  int v39; // ebx
  _QWORD *v40; // rcx
  int v41; // ebx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  int v45; // [rsp+40h] [rbp-78h]
  int v46; // [rsp+44h] [rbp-74h]
  int v47; // [rsp+50h] [rbp-68h]
  __int64 VTable; // [rsp+58h] [rbp-60h]
  __int64 v49; // [rsp+60h] [rbp-58h]
  int v50; // [rsp+C0h] [rbp+8h]

  v8 = a1[2];
  v9 = a1;
  v10 = *a1;
  v12 = a2[10];
  VTable = sqlite3GetVTable(*a1, a3);
  v45 = *(__int16 *)(v14 + 54) + 2;
  v46 = *((_DWORD *)v9 + 14);
  *((_DWORD *)v9 + 14) = v46 + 1;
  v15 = sqlite3VdbeAddOp3(v8, 117, v46, v45, 0);
  v16 = *((_DWORD *)v9 + 15);
  v17 = v16 + v45;
  *((_DWORD *)v9 + 15) = v16 + v45;
  v18 = v16 + 1;
  v50 = v16 + 1;
  if ( *a2 > 1 )
  {
    v49 = 0;
    if ( *(char *)(a3 + 48) < 0 )
    {
      v21 = a6;
      v19 = sqlite3PrimaryKeyIndex(a3);
      v22 = **(__int16 **)(v19 + 8);
      if ( *(int *)(a6 + 4 * v22) < 0 )
        v20 = exprRowColumn(v9, (unsigned int)v22);
      else
        v20 = sqlite3ExprDup(v10, *(_QWORD *)(32LL * *(int *)(a6 + 4 * v22) + a4 + 8), 0);
    }
    else
    {
      LODWORD(v19) = 0;
      if ( a5 )
        v20 = sqlite3ExprDup(v10, a5, 0);
      else
        v20 = sqlite3PExpr(v9, 76, 0);
      v21 = a6;
    }
    v23 = sqlite3ExprListAppend(v9, 0, v20);
    for ( i = 0; (int)i < *(__int16 *)(a3 + 54); ++i )
    {
      if ( *(int *)(v21 + 4LL * (int)i) < 0 )
      {
        v25 = exprRowColumn(v9, i);
        if ( v25 )
          *(_BYTE *)(v25 + 2) = 1;
      }
      else
      {
        v25 = sqlite3ExprDup(v10, *(_QWORD *)(32LL * *(int *)(v21 + 4LL * (int)i) + a4 + 8), 0);
      }
      v23 = sqlite3ExprListAppend(v9, v23, v25);
    }
    v26 = v19;
    v27 = v46;
    v28 = a2;
    updateFromSelect((_DWORD)v9, v46, v26, v23, (__int64)a2, a7);
    sqlite3ExprListDeleteGeneric(v10, v23);
    v29 = 0;
    v30 = 0;
LABEL_35:
    if ( *v28 == 1 )
      sqlite3WhereEnd(v30);
    v41 = 0;
    v15 = sqlite3VdbeAddOp3(v8, 36, v27, 0, 0);
    if ( v45 > 0 )
    {
      do
      {
        sqlite3VdbeAddOp3(v8, 94, v27, v41, v50 + v41);
        ++v41;
      }
      while ( v41 < v45 );
      v30 = v49;
    }
    goto LABEL_40;
  }
  v47 = v17 + 1;
  *((_DWORD *)v9 + 15) = v17 + 2;
  result = sqlite3WhereBegin((_DWORD)v9, (_DWORD)a2, a7, 0, 0, 0, 4, 0);
  v49 = result;
  v30 = result;
  if ( !result )
    return result;
  v32 = 0;
  if ( *(__int16 *)(a3 + 54) > 0 )
  {
    v33 = v18 + 2;
    do
    {
      v34 = v32 + v33;
      if ( *(int *)(a6 + 4LL * v32) < 0 )
      {
        sqlite3VdbeAddOp3(v8, 176, v12, v32, v34);
        sqlite3VdbeChangeP5(v8, 1, v35, v36);
      }
      else
      {
        sqlite3ExprCode(v9, *(_QWORD *)(32LL * *(int *)(a6 + 4LL * v32) + a4 + 8), v34);
      }
      ++v32;
    }
    while ( v32 < *(__int16 *)(a3 + 54) );
    v30 = v49;
    v18 = v50;
  }
  v37 = v18 + 1;
  if ( *(char *)(a3 + 48) < 0 )
  {
    v39 = **(__int16 **)(sqlite3PrimaryKeyIndex(a3) + 8);
    sqlite3VdbeAddOp3(v8, 176, v12, v39, v50);
    sqlite3VdbeAddOp3(v8, 81, v39 + v50 + 2, v37, 0);
    v38 = v50;
  }
  else
  {
    v38 = v50;
    sqlite3VdbeAddOp3(v8, 135, v12, v50, 0);
    if ( a5 )
      sqlite3ExprCode(v9, a5, v37);
    else
      sqlite3VdbeAddOp3(v8, 135, v12, v37, 0);
  }
  v29 = *(unsigned __int8 *)(v30 + 66);
  if ( !*(_BYTE *)(v30 + 66) )
  {
    v40 = v9;
    if ( v9[22] )
      v40 = (_QWORD *)v9[22];
    *((_BYTE *)v40 + 32) = 1;
    sqlite3VdbeAddOp3(v8, 97, v38, v45, v47);
    v27 = v46;
    sqlite3VdbeAddOp3(v8, 127, v46, v47 + 1, 0);
    sqlite3VdbeAddOp3(v8, 128, v46, v47, v47 + 1);
    v28 = a2;
    goto LABEL_35;
  }
  sqlite3VdbeChangeToNoop(v8, v15);
  sqlite3VdbeAddOp3(v8, 122, v12, 0, 0);
  v27 = v46;
LABEL_40:
  sqlite3VtabMakeWritable(v9);
  sqlite3VdbeAddOp4(v8, 7, 0, v45, v50, VTable, -11);
  v44 = 2;
  if ( a8 != 11 )
    LOWORD(v44) = a8;
  sqlite3VdbeChangeP5(v8, v44, v42, v43);
  if ( v9[22] )
    v9 = (_QWORD *)v9[22];
  *((_BYTE *)v9 + 33) = 1;
  if ( v29 )
    return sqlite3WhereEnd(v30);
  sqlite3VdbeAddOp3(v8, 39, v27, v15 + 1, 0);
  *(_DWORD *)(sqlite3VdbeGetOp(v8, v15) + 8) = *(_DWORD *)(v8 + 144);
  return sqlite3VdbeAddOp3(v8, 122, v27, 0, 0);
}

```

## disassembly

```asm
0x18005e35c  mov     [rsp+arg_18], r9
0x18005e361  mov     [rsp+arg_10], r8
0x18005e366  mov     [rsp+arg_8], rdx
0x18005e36b  push    rbx
0x18005e36c  push    rbp
0x18005e36d  push    rsi
0x18005e36e  push    rdi
0x18005e36f  push    r12
0x18005e371  push    r13
0x18005e373  push    r14
0x18005e375  push    r15
0x18005e377  sub     rsp, 78h
0x18005e37b  mov     rdi, [rcx+10h]
0x18005e37f  mov     rsi, rcx
0x18005e382  mov     r12, [rcx]
0x18005e385  mov     rbx, r9
0x18005e388  mov     r15d, [rdx+28h]
0x18005e38c  mov     rcx, r12
0x18005e38f  mov     rdx, r8
0x18005e392  mov     [rsp+0B8h+var_68], rdi
0x18005e397  mov     r14, r8
0x18005e39a  call    sqlite3GetVTable
0x18005e39f  movsx   ecx, word ptr [r8+36h]
0x18005e3a4  mov     edx, 75h ; 'u'
0x18005e3a9  mov     r8d, [rsi+38h]
0x18005e3ad  add     ecx, 2
0x18005e3b0  mov     [rsp+0B8h+var_60], rax
0x18005e3b5  mov     r9d, ecx
0x18005e3b8  mov     [rsp+0B8h+var_78], ecx
0x18005e3bc  mov     rcx, rdi
0x18005e3bf  mov     [rsp+0B8h+var_74], r8d
0x18005e3c4  lea     eax, [r8+1]
0x18005e3c8  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e3d0  mov     [rsi+38h], eax
0x18005e3d3  call    sqlite3VdbeAddOp3
0x18005e3d8  mov     ecx, [rsp+0B8h+var_78]
0x18005e3dc  mov     r13d, eax
0x18005e3df  mov     rdx, [rsp+0B8h+arg_8]
0x18005e3e7  mov     [rsp+0B8h+var_6C], eax
0x18005e3eb  mov     eax, [rsi+3Ch]
0x18005e3ee  add     ecx, eax
0x18005e3f0  mov     [rsi+3Ch], ecx
0x18005e3f3  cmp     dword ptr [rdx], 1
0x18005e3f6  lea     ebp, [rax+1]
0x18005e3f9  mov     [rsp+0B8h+arg_0], ebp
0x18005e400  jle     loc_18005E559
0x18005e406  test    byte ptr [r14+30h], 80h
0x18005e40b  mov     [rsp+0B8h+var_58], 0
0x18005e414  jnz     short loc_18005E44F
0x18005e416  mov     rdx, [rsp+0B8h+arg_20]
0x18005e41e  xor     r15d, r15d
0x18005e421  test    rdx, rdx
0x18005e424  jz      short loc_18005E433
0x18005e426  xor     r8d, r8d
0x18005e429  mov     rcx, r12
0x18005e42c  call    sqlite3ExprDup
0x18005e431  jmp     short loc_18005E445
0x18005e433  xor     r9d, r9d
0x18005e436  xor     r8d, r8d
0x18005e439  mov     rcx, rsi
0x18005e43c  lea     edx, [r9+4Ch]
0x18005e440  call    sqlite3PExpr
0x18005e445  mov     r13, [rsp+0B8h+arg_28]
0x18005e44d  jmp     short loc_18005E497
0x18005e44f  mov     rcx, r14
0x18005e452  call    sqlite3PrimaryKeyIndex
0x18005e457  mov     r13, [rsp+0B8h+arg_28]
0x18005e45f  mov     r15, rax
0x18005e462  mov     rax, [rax+8]
0x18005e466  movsx   rcx, word ptr [rax]
0x18005e46a  cmp     dword ptr [r13+rcx*4+0], 0
0x18005e470  jl      short loc_18005E48D
0x18005e472  movsxd  rdx, dword ptr [r13+rcx*4+0]
0x18005e477  xor     r8d, r8d
0x18005e47a  shl     rdx, 5
0x18005e47e  mov     rcx, r12
0x18005e481  mov     rdx, [rdx+rbx+8]
0x18005e486  call    sqlite3ExprDup
0x18005e48b  jmp     short loc_18005E497
0x18005e48d  mov     edx, ecx
0x18005e48f  mov     rcx, rsi
0x18005e492  call    exprRowColumn
0x18005e497  mov     r8, rax
0x18005e49a  xor     edx, edx
0x18005e49c  mov     rcx, rsi
0x18005e49f  call    sqlite3ExprListAppend
0x18005e4a4  mov     rbx, rax
0x18005e4a7  xor     ebp, ebp
0x18005e4a9  xor     eax, eax
0x18005e4ab  cmp     ax, [r14+36h]
0x18005e4b0  jge     short loc_18005E514
0x18005e4b2  mov     rdi, [rsp+0B8h+arg_18]
0x18005e4ba  movsxd  rax, ebp
0x18005e4bd  cmp     dword ptr [r13+rax*4+0], 0
0x18005e4c3  jl      short loc_18005E4E0
0x18005e4c5  movsxd  rdx, dword ptr [r13+rax*4+0]
0x18005e4ca  xor     r8d, r8d
0x18005e4cd  shl     rdx, 5
0x18005e4d1  mov     rcx, r12
0x18005e4d4  mov     rdx, [rdx+rdi+8]
0x18005e4d9  call    sqlite3ExprDup
0x18005e4de  jmp     short loc_18005E4F3
0x18005e4e0  mov     edx, ebp
0x18005e4e2  mov     rcx, rsi
0x18005e4e5  call    exprRowColumn
0x18005e4ea  test    rax, rax
0x18005e4ed  jz      short loc_18005E4F3
0x18005e4ef  mov     byte ptr [rax+2], 1
0x18005e4f3  mov     r8, rax
0x18005e4f6  mov     rdx, rbx
0x18005e4f9  mov     rcx, rsi
0x18005e4fc  call    sqlite3ExprListAppend
0x18005e501  mov     rbx, rax
0x18005e504  inc     ebp
0x18005e506  movsx   eax, word ptr [r14+36h]
0x18005e50b  cmp     ebp, eax
0x18005e50d  jl      short loc_18005E4BA
0x18005e50f  mov     rdi, [rsp+0B8h+var_68]
0x18005e514  mov     rax, [rsp+0B8h+arg_30]
0x18005e51c  mov     r8, r15
0x18005e51f  mov     r15d, [rsp+0B8h+var_74]
0x18005e524  mov     r9, rbx
0x18005e527  mov     r13, [rsp+0B8h+arg_8]
0x18005e52f  mov     edx, r15d
0x18005e532  mov     [rsp+0B8h+var_90], rax
0x18005e537  mov     rcx, rsi
0x18005e53a  mov     [rsp+0B8h+var_98], r13
0x18005e53f  call    updateFromSelect
0x18005e544  mov     rdx, rbx
0x18005e547  mov     rcx, r12
0x18005e54a  call    sqlite3ExprListDeleteGeneric
0x18005e54f  xor     ebp, ebp
0x18005e551  mov     r12d, ebp
0x18005e554  jmp     loc_18005E7A8
0x18005e559  mov     r8, [rsp+0B8h+arg_30]
0x18005e561  lea     eax, [rcx+1]
0x18005e564  xor     ecx, ecx
0x18005e566  mov     dword ptr [rsp+0B8h+var_68], eax
0x18005e56a  mov     [rsp+0B8h+var_80], ecx
0x18005e56e  inc     eax
0x18005e570  mov     word ptr [rsp+0B8h+var_88], 4
0x18005e577  xor     r9d, r9d
0x18005e57a  mov     [rsp+0B8h+var_90], rcx
0x18005e57f  mov     [rsp+0B8h+var_98], rcx
0x18005e584  mov     rcx, rsi
0x18005e587  mov     [rsi+3Ch], eax
0x18005e58a  call    sqlite3WhereBegin
0x18005e58f  mov     [rsp+0B8h+var_58], rax
0x18005e594  mov     r12, rax
0x18005e597  test    rax, rax
0x18005e59a  jz      loc_18005E8D3
0x18005e5a0  xor     ebx, ebx
0x18005e5a2  xor     ecx, ecx
0x18005e5a4  cmp     cx, [r14+36h]
0x18005e5a9  jge     short loc_18005E627
0x18005e5ab  mov     r13, [rsp+0B8h+arg_28]
0x18005e5b3  add     ebp, 2
0x18005e5b6  mov     r12, [rsp+0B8h+arg_18]
0x18005e5be  movsxd  rax, ebx
0x18005e5c1  lea     ecx, [rbx+rbp]
0x18005e5c4  cmp     dword ptr [r13+rax*4+0], 0
0x18005e5ca  jl      short loc_18005E5E7
0x18005e5cc  movsxd  rdx, dword ptr [r13+rax*4+0]
0x18005e5d1  mov     r8d, ecx
0x18005e5d4  shl     rdx, 5
0x18005e5d8  mov     rcx, rsi
0x18005e5db  mov     rdx, [rdx+r12+8]
0x18005e5e0  call    sqlite3ExprCode
0x18005e5e5  jmp     short loc_18005E60B
0x18005e5e7  mov     dword ptr [rsp+0B8h+var_98], ecx
0x18005e5eb  mov     r9d, ebx
0x18005e5ee  mov     rcx, rdi
0x18005e5f1  mov     r8d, r15d
0x18005e5f4  mov     edx, 0B0h
0x18005e5f9  call    sqlite3VdbeAddOp3
0x18005e5fe  mov     edx, 1
0x18005e603  mov     rcx, rdi
0x18005e606  call    sqlite3VdbeChangeP5
0x18005e60b  movsx   eax, word ptr [r14+36h]
0x18005e610  inc     ebx
0x18005e612  cmp     ebx, eax
0x18005e614  jl      short loc_18005E5BE
0x18005e616  mov     r13d, [rsp+0B8h+var_6C]
0x18005e61b  mov     r12, [rsp+0B8h+var_58]
0x18005e620  mov     ebp, [rsp+0B8h+arg_0]
0x18005e627  inc     ebp
0x18005e629  test    byte ptr [r14+30h], 80h
0x18005e62e  jnz     short loc_18005E689
0x18005e630  mov     ebx, [rsp+0B8h+arg_0]
0x18005e637  mov     r8d, r15d
0x18005e63a  mov     r9d, ebx
0x18005e63d  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e645  mov     edx, 87h
0x18005e64a  mov     rcx, rdi
0x18005e64d  call    sqlite3VdbeAddOp3
0x18005e652  mov     rdx, [rsp+0B8h+arg_20]
0x18005e65a  test    rdx, rdx
0x18005e65d  jz      short loc_18005E66C
0x18005e65f  mov     r8d, ebp
0x18005e662  mov     rcx, rsi
0x18005e665  call    sqlite3ExprCode
0x18005e66a  jmp     short loc_18005E6E4
0x18005e66c  mov     r9d, ebp
0x18005e66f  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e677  mov     r8d, r15d
0x18005e67a  mov     edx, 87h
0x18005e67f  mov     rcx, rdi
0x18005e682  call    sqlite3VdbeAddOp3
0x18005e687  jmp     short loc_18005E6E4
0x18005e689  mov     rcx, r14
0x18005e68c  call    sqlite3PrimaryKeyIndex
0x18005e691  mov     r8d, r15d
0x18005e694  mov     edx, 0B0h
0x18005e699  mov     rcx, [rax+8]
0x18005e69d  mov     eax, [rsp+0B8h+arg_0]
0x18005e6a4  mov     dword ptr [rsp+0B8h+var_98], eax
0x18005e6a8  movsx   ebx, word ptr [rcx]
0x18005e6ab  mov     rcx, rdi
0x18005e6ae  mov     r9d, ebx
0x18005e6b1  call    sqlite3VdbeAddOp3
0x18005e6b6  mov     r8d, [rsp+0B8h+arg_0]
0x18005e6be  mov     r9d, ebp
0x18005e6c1  add     r8d, 2
0x18005e6c5  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e6cd  add     r8d, ebx
0x18005e6d0  mov     edx, 51h ; 'Q'
0x18005e6d5  mov     rcx, rdi
0x18005e6d8  call    sqlite3VdbeAddOp3
0x18005e6dd  mov     ebx, [rsp+0B8h+arg_0]
0x18005e6e4  movzx   ebp, byte ptr [r12+42h]
0x18005e6ea  test    ebp, ebp
0x18005e6ec  jz      short loc_18005E727
0x18005e6ee  mov     edx, r13d
0x18005e6f1  mov     rcx, rdi
0x18005e6f4  call    sqlite3VdbeChangeToNoop
0x18005e6f9  xor     r9d, r9d
0x18005e6fc  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e704  mov     r8d, r15d
0x18005e707  mov     rcx, rdi
0x18005e70a  lea     edx, [r9+7Ah]
0x18005e70e  call    sqlite3VdbeAddOp3
0x18005e713  mov     rax, [rsp+0B8h+var_60]
0x18005e718  mov     r15d, [rsp+0B8h+var_74]
0x18005e71d  mov     [rsp+0B8h+var_60], rax
0x18005e722  jmp     loc_18005E818
0x18005e727  mov     rax, [rsi+0B0h]
0x18005e72e  mov     rcx, rsi
0x18005e731  mov     r13d, dword ptr [rsp+0B8h+var_68]
0x18005e736  test    rax, rax
0x18005e739  mov     r9d, [rsp+0B8h+var_78]
0x18005e73e  mov     r8d, ebx
0x18005e741  cmovnz  rcx, rax
0x18005e745  mov     dword ptr [rsp+0B8h+var_98], r13d
0x18005e74a  mov     edx, 61h ; 'a'
0x18005e74f  mov     byte ptr [rcx+20h], 1
0x18005e753  mov     rcx, rdi
0x18005e756  call    sqlite3VdbeAddOp3
0x18005e75b  mov     r15d, [rsp+0B8h+var_74]
0x18005e760  lea     ebx, [r13+1]
0x18005e764  mov     r9d, ebx
0x18005e767  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e76f  mov     r8d, r15d
0x18005e772  mov     edx, 7Fh
0x18005e777  mov     rcx, rdi
0x18005e77a  call    sqlite3VdbeAddOp3
0x18005e77f  mov     r9d, r13d
0x18005e782  mov     dword ptr [rsp+0B8h+var_98], ebx
0x18005e786  mov     r8d, r15d
0x18005e789  mov     edx, 80h
0x18005e78e  mov     rcx, rdi
0x18005e791  call    sqlite3VdbeAddOp3
0x18005e796  mov     rax, [rsp+0B8h+var_60]
0x18005e79b  mov     r13, [rsp+0B8h+arg_8]
0x18005e7a3  mov     [rsp+0B8h+var_60], rax
0x18005e7a8  cmp     dword ptr [r13+0], 1
0x18005e7ad  jnz     short loc_18005E7B7
0x18005e7af  mov     rcx, r12
0x18005e7b2  call    sqlite3WhereEnd
0x18005e7b7  xor     r9d, r9d
0x18005e7ba  mov     dword ptr [rsp+0B8h+var_98], 0
0x18005e7c2  mov     r8d, r15d
0x18005e7c5  mov     rcx, rdi
0x18005e7c8  lea     edx, [r9+24h]
0x18005e7cc  call    sqlite3VdbeAddOp3
0x18005e7d1  xor     ebx, ebx
0x18005e7d3  mov     r13d, eax
0x18005e7d6  cmp     [rsp+0B8h+var_78], ebx
0x18005e7da  jle     short loc_18005E818
0x18005e7dc  mov     r14d, [rsp+0B8h+arg_0]
0x18005e7e4  mov     r12d, [rsp+0B8h+var_78]
0x18005e7e9  lea     ecx, [r14+rbx]
0x18005e7ed  mov     r9d, ebx
0x18005e7f0  mov     dword ptr [rsp+0B8h+var_98], ecx
0x18005e7f4  mov     r8d, r15d
0x18005e7f7  mov     rcx, rdi
0x18005e7fa  mov     edx, 5Eh ; '^'
0x18005e7ff  call    sqlite3VdbeAddOp3
0x18005e804  inc     ebx
0x18005e806  cmp     ebx, r12d
0x18005e809  jl      short loc_18005E7E9
  ... truncated ...
```

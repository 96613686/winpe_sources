# updateVirtualTable

- ea: `0x18009c038`
- end: `0x18009c5c0`
- name: `updateVirtualTable`
- size: `1416`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x18002f9a4`

## callees

- `0x180006ac0`
- `0x18000b4bc`
- `0x18000db18`
- `0x18001ece0`
- `0x18003713c`
- `0x18003b8a0`
- `0x18003be78`
- `0x18003e5b4`
- `0x180041574`
- `0x180042260`
- `0x180042cd4`
- `0x18005e9bc`
- `0x18007f6bc`
- `0x180086d48`
- `0x18008cd90`
- `0x18008ff40`
- `0x18009bd98`
- `0x18009c038`

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
  unsigned int v35; // ebp
  int v36; // ebx
  int v37; // ebx
  _QWORD *v38; // rcx
  int v39; // ebx
  __int64 v40; // rdx
  int v41; // [rsp+40h] [rbp-78h]
  int v42; // [rsp+44h] [rbp-74h]
  int v43; // [rsp+50h] [rbp-68h]
  __int64 VTable; // [rsp+58h] [rbp-60h]
  __int64 v45; // [rsp+60h] [rbp-58h]
  int v46; // [rsp+C0h] [rbp+8h]

  v8 = a1[2];
  v9 = a1;
  v10 = *a1;
  v12 = a2[19];
  VTable = sqlite3GetVTable(*a1, a3);
  v41 = *(__int16 *)(v14 + 54) + 2;
  v42 = *((_DWORD *)v9 + 13);
  *((_DWORD *)v9 + 13) = v42 + 1;
  v15 = sqlite3VdbeAddOp3(v8, 118, v42, v41, 0);
  v16 = *((_DWORD *)v9 + 14);
  v17 = v16 + v41;
  *((_DWORD *)v9 + 14) = v16 + v41;
  v18 = v16 + 1;
  v46 = v16 + 1;
  if ( *a2 > 1 )
  {
    v45 = 0;
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
        v20 = sqlite3PExpr(v9, 75, 0, 0);
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
    v27 = v42;
    v28 = a2;
    updateFromSelect((_DWORD)v9, v42, v26, v23, (__int64)a2, a7);
    sqlite3ExprListDeleteGeneric(v10, v23);
    v29 = 0;
    v30 = 0;
LABEL_35:
    if ( *v28 == 1 )
      sqlite3WhereEnd(v30);
    v39 = 0;
    v15 = sqlite3VdbeAddOp3(v8, 36, v27, 0, 0);
    if ( v41 > 0 )
    {
      do
      {
        sqlite3VdbeAddOp3(v8, 94, v27, v39, v46 + v39);
        ++v39;
      }
      while ( v39 < v41 );
      v30 = v45;
    }
    goto LABEL_40;
  }
  v43 = v17 + 1;
  *((_DWORD *)v9 + 14) = v17 + 2;
  result = sqlite3WhereBegin((_DWORD)v9, (_DWORD)a2, a7, 0, 0, 0, 4, 0);
  v45 = result;
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
        sqlite3VdbeChangeP5(v8, 1);
      }
      else
      {
        sqlite3ExprCode(v9, *(_QWORD *)(32LL * *(int *)(a6 + 4LL * v32) + a4 + 8), v34);
      }
      ++v32;
    }
    while ( v32 < *(__int16 *)(a3 + 54) );
    v30 = v45;
    v18 = v46;
  }
  v35 = v18 + 1;
  if ( *(char *)(a3 + 48) < 0 )
  {
    v37 = **(__int16 **)(sqlite3PrimaryKeyIndex(a3) + 8);
    sqlite3VdbeAddOp3(v8, 176, v12, v37, v46);
    sqlite3VdbeAddOp3(v8, 81, v37 + v46 + 2, v35, 0);
    v36 = v46;
  }
  else
  {
    v36 = v46;
    sqlite3VdbeAddOp3(v8, 135, v12, v46, 0);
    if ( a5 )
      sqlite3ExprCode(v9, a5, v35);
    else
      sqlite3VdbeAddOp3(v8, 135, v12, v35, 0);
  }
  v29 = *(unsigned __int8 *)(v30 + 66);
  if ( !*(_BYTE *)(v30 + 66) )
  {
    v38 = v9;
    if ( v9[22] )
      v38 = (_QWORD *)v9[22];
    *((_BYTE *)v38 + 32) = 1;
    sqlite3VdbeAddOp3(v8, 97, v36, v41, v43);
    v27 = v42;
    sqlite3VdbeAddOp3(v8, 127, v42, v43 + 1, 0);
    sqlite3VdbeAddOp3(v8, 128, v42, v43, v43 + 1);
    v28 = a2;
    goto LABEL_35;
  }
  sqlite3VdbeChangeToNoop(v8, v15);
  sqlite3VdbeAddOp3(v8, 122, v12, 0, 0);
  v27 = v42;
LABEL_40:
  sqlite3VtabMakeWritable(v9);
  sqlite3VdbeAddOp4(v8, 7, 0, v41, v46, VTable, -11);
  v40 = 2;
  if ( a8 != 11 )
    LOWORD(v40) = a8;
  sqlite3VdbeChangeP5(v8, v40);
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
0x18009c038  mov     [rsp+arg_18], r9
0x18009c03d  mov     [rsp+arg_10], r8
0x18009c042  mov     [rsp+arg_8], rdx
0x18009c047  push    rbx
0x18009c048  push    rbp
0x18009c049  push    rsi
0x18009c04a  push    rdi
0x18009c04b  push    r12
0x18009c04d  push    r13
0x18009c04f  push    r14
0x18009c051  push    r15
0x18009c053  sub     rsp, 78h
0x18009c057  mov     rdi, [rcx+10h]
0x18009c05b  mov     rsi, rcx
0x18009c05e  mov     r12, [rcx]
0x18009c061  mov     rbx, r9
0x18009c064  mov     r15d, [rdx+4Ch]
0x18009c068  mov     rcx, r12
0x18009c06b  mov     rdx, r8
0x18009c06e  mov     [rsp+0B8h+var_68], rdi
0x18009c073  mov     r14, r8
0x18009c076  call    sqlite3GetVTable
0x18009c07b  movsx   ecx, word ptr [r8+36h]
0x18009c080  mov     edx, 76h ; 'v'
0x18009c085  mov     r8d, [rsi+34h]
0x18009c089  add     ecx, 2
0x18009c08c  mov     [rsp+0B8h+var_60], rax
0x18009c091  mov     r9d, ecx
0x18009c094  mov     [rsp+0B8h+var_78], ecx
0x18009c098  mov     rcx, rdi
0x18009c09b  mov     [rsp+0B8h+var_74], r8d
0x18009c0a0  lea     eax, [r8+1]
0x18009c0a4  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c0ac  mov     [rsi+34h], eax
0x18009c0af  call    sqlite3VdbeAddOp3
0x18009c0b4  mov     ecx, [rsp+0B8h+var_78]
0x18009c0b8  mov     r13d, eax
0x18009c0bb  mov     rdx, [rsp+0B8h+arg_8]
0x18009c0c3  mov     [rsp+0B8h+var_6C], eax
0x18009c0c7  mov     eax, [rsi+38h]
0x18009c0ca  add     ecx, eax
0x18009c0cc  mov     [rsi+38h], ecx
0x18009c0cf  cmp     dword ptr [rdx], 1
0x18009c0d2  lea     ebp, [rax+1]
0x18009c0d5  mov     [rsp+0B8h+arg_0], ebp
0x18009c0dc  jle     loc_18009C235
0x18009c0e2  test    byte ptr [r14+30h], 80h
0x18009c0e7  mov     [rsp+0B8h+var_58], 0
0x18009c0f0  jnz     short loc_18009C12B
0x18009c0f2  mov     rdx, [rsp+0B8h+arg_20]
0x18009c0fa  xor     r15d, r15d
0x18009c0fd  test    rdx, rdx
0x18009c100  jz      short loc_18009C10F
0x18009c102  xor     r8d, r8d
0x18009c105  mov     rcx, r12
0x18009c108  call    sqlite3ExprDup
0x18009c10d  jmp     short loc_18009C121
0x18009c10f  xor     r9d, r9d
0x18009c112  xor     r8d, r8d
0x18009c115  mov     rcx, rsi
0x18009c118  lea     edx, [r9+4Bh]
0x18009c11c  call    sqlite3PExpr
0x18009c121  mov     r13, [rsp+0B8h+arg_28]
0x18009c129  jmp     short loc_18009C173
0x18009c12b  mov     rcx, r14
0x18009c12e  call    sqlite3PrimaryKeyIndex
0x18009c133  mov     r13, [rsp+0B8h+arg_28]
0x18009c13b  mov     r15, rax
0x18009c13e  mov     rax, [rax+8]
0x18009c142  movsx   rcx, word ptr [rax]
0x18009c146  cmp     dword ptr [r13+rcx*4+0], 0
0x18009c14c  jl      short loc_18009C169
0x18009c14e  movsxd  rdx, dword ptr [r13+rcx*4+0]
0x18009c153  xor     r8d, r8d
0x18009c156  shl     rdx, 5
0x18009c15a  mov     rcx, r12
0x18009c15d  mov     rdx, [rdx+rbx+8]
0x18009c162  call    sqlite3ExprDup
0x18009c167  jmp     short loc_18009C173
0x18009c169  mov     edx, ecx
0x18009c16b  mov     rcx, rsi
0x18009c16e  call    exprRowColumn
0x18009c173  mov     r8, rax
0x18009c176  xor     edx, edx
0x18009c178  mov     rcx, rsi
0x18009c17b  call    sqlite3ExprListAppend
0x18009c180  mov     rbx, rax
0x18009c183  xor     ebp, ebp
0x18009c185  xor     eax, eax
0x18009c187  cmp     ax, [r14+36h]
0x18009c18c  jge     short loc_18009C1F0
0x18009c18e  mov     rdi, [rsp+0B8h+arg_18]
0x18009c196  movsxd  rax, ebp
0x18009c199  cmp     dword ptr [r13+rax*4+0], 0
0x18009c19f  jl      short loc_18009C1BC
0x18009c1a1  movsxd  rdx, dword ptr [r13+rax*4+0]
0x18009c1a6  xor     r8d, r8d
0x18009c1a9  shl     rdx, 5
0x18009c1ad  mov     rcx, r12
0x18009c1b0  mov     rdx, [rdx+rdi+8]
0x18009c1b5  call    sqlite3ExprDup
0x18009c1ba  jmp     short loc_18009C1CF
0x18009c1bc  mov     edx, ebp
0x18009c1be  mov     rcx, rsi
0x18009c1c1  call    exprRowColumn
0x18009c1c6  test    rax, rax
0x18009c1c9  jz      short loc_18009C1CF
0x18009c1cb  mov     byte ptr [rax+2], 1
0x18009c1cf  mov     r8, rax
0x18009c1d2  mov     rdx, rbx
0x18009c1d5  mov     rcx, rsi
0x18009c1d8  call    sqlite3ExprListAppend
0x18009c1dd  mov     rbx, rax
0x18009c1e0  inc     ebp
0x18009c1e2  movsx   eax, word ptr [r14+36h]
0x18009c1e7  cmp     ebp, eax
0x18009c1e9  jl      short loc_18009C196
0x18009c1eb  mov     rdi, [rsp+0B8h+var_68]
0x18009c1f0  mov     rax, [rsp+0B8h+arg_30]
0x18009c1f8  mov     r8, r15
0x18009c1fb  mov     r15d, [rsp+0B8h+var_74]
0x18009c200  mov     r9, rbx
0x18009c203  mov     r13, [rsp+0B8h+arg_8]
0x18009c20b  mov     edx, r15d
0x18009c20e  mov     [rsp+0B8h+var_90], rax
0x18009c213  mov     rcx, rsi
0x18009c216  mov     [rsp+0B8h+var_98], r13
0x18009c21b  call    updateFromSelect
0x18009c220  mov     rdx, rbx
0x18009c223  mov     rcx, r12
0x18009c226  call    sqlite3ExprListDeleteGeneric
0x18009c22b  xor     ebp, ebp
0x18009c22d  mov     r12d, ebp
0x18009c230  jmp     loc_18009C484
0x18009c235  mov     r8, [rsp+0B8h+arg_30]
0x18009c23d  lea     eax, [rcx+1]
0x18009c240  xor     ecx, ecx
0x18009c242  mov     dword ptr [rsp+0B8h+var_68], eax
0x18009c246  mov     [rsp+0B8h+var_80], ecx
0x18009c24a  inc     eax
0x18009c24c  mov     word ptr [rsp+0B8h+var_88], 4
0x18009c253  xor     r9d, r9d
0x18009c256  mov     [rsp+0B8h+var_90], rcx
0x18009c25b  mov     [rsp+0B8h+var_98], rcx
0x18009c260  mov     rcx, rsi
0x18009c263  mov     [rsi+38h], eax
0x18009c266  call    sqlite3WhereBegin
0x18009c26b  mov     [rsp+0B8h+var_58], rax
0x18009c270  mov     r12, rax
0x18009c273  test    rax, rax
0x18009c276  jz      loc_18009C5AF
0x18009c27c  xor     ebx, ebx
0x18009c27e  xor     ecx, ecx
0x18009c280  cmp     cx, [r14+36h]
0x18009c285  jge     short loc_18009C303
0x18009c287  mov     r13, [rsp+0B8h+arg_28]
0x18009c28f  add     ebp, 2
0x18009c292  mov     r12, [rsp+0B8h+arg_18]
0x18009c29a  movsxd  rax, ebx
0x18009c29d  lea     ecx, [rbx+rbp]
0x18009c2a0  cmp     dword ptr [r13+rax*4+0], 0
0x18009c2a6  jl      short loc_18009C2C3
0x18009c2a8  movsxd  rdx, dword ptr [r13+rax*4+0]
0x18009c2ad  mov     r8d, ecx
0x18009c2b0  shl     rdx, 5
0x18009c2b4  mov     rcx, rsi
0x18009c2b7  mov     rdx, [rdx+r12+8]
0x18009c2bc  call    sqlite3ExprCode
0x18009c2c1  jmp     short loc_18009C2E7
0x18009c2c3  mov     dword ptr [rsp+0B8h+var_98], ecx
0x18009c2c7  mov     r9d, ebx
0x18009c2ca  mov     rcx, rdi
0x18009c2cd  mov     r8d, r15d
0x18009c2d0  mov     edx, 0B0h
0x18009c2d5  call    sqlite3VdbeAddOp3
0x18009c2da  mov     edx, 1
0x18009c2df  mov     rcx, rdi
0x18009c2e2  call    sqlite3VdbeChangeP5
0x18009c2e7  movsx   eax, word ptr [r14+36h]
0x18009c2ec  inc     ebx
0x18009c2ee  cmp     ebx, eax
0x18009c2f0  jl      short loc_18009C29A
0x18009c2f2  mov     r13d, [rsp+0B8h+var_6C]
0x18009c2f7  mov     r12, [rsp+0B8h+var_58]
0x18009c2fc  mov     ebp, [rsp+0B8h+arg_0]
0x18009c303  inc     ebp
0x18009c305  test    byte ptr [r14+30h], 80h
0x18009c30a  jnz     short loc_18009C365
0x18009c30c  mov     ebx, [rsp+0B8h+arg_0]
0x18009c313  mov     r8d, r15d
0x18009c316  mov     r9d, ebx
0x18009c319  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c321  mov     edx, 87h
0x18009c326  mov     rcx, rdi
0x18009c329  call    sqlite3VdbeAddOp3
0x18009c32e  mov     rdx, [rsp+0B8h+arg_20]
0x18009c336  test    rdx, rdx
0x18009c339  jz      short loc_18009C348
0x18009c33b  mov     r8d, ebp
0x18009c33e  mov     rcx, rsi
0x18009c341  call    sqlite3ExprCode
0x18009c346  jmp     short loc_18009C3C0
0x18009c348  mov     r9d, ebp
0x18009c34b  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c353  mov     r8d, r15d
0x18009c356  mov     edx, 87h
0x18009c35b  mov     rcx, rdi
0x18009c35e  call    sqlite3VdbeAddOp3
0x18009c363  jmp     short loc_18009C3C0
0x18009c365  mov     rcx, r14
0x18009c368  call    sqlite3PrimaryKeyIndex
0x18009c36d  mov     r8d, r15d
0x18009c370  mov     edx, 0B0h
0x18009c375  mov     rcx, [rax+8]
0x18009c379  mov     eax, [rsp+0B8h+arg_0]
0x18009c380  mov     dword ptr [rsp+0B8h+var_98], eax
0x18009c384  movsx   ebx, word ptr [rcx]
0x18009c387  mov     rcx, rdi
0x18009c38a  mov     r9d, ebx
0x18009c38d  call    sqlite3VdbeAddOp3
0x18009c392  mov     r8d, [rsp+0B8h+arg_0]
0x18009c39a  mov     r9d, ebp
0x18009c39d  add     r8d, 2
0x18009c3a1  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c3a9  add     r8d, ebx
0x18009c3ac  mov     edx, 51h ; 'Q'
0x18009c3b1  mov     rcx, rdi
0x18009c3b4  call    sqlite3VdbeAddOp3
0x18009c3b9  mov     ebx, [rsp+0B8h+arg_0]
0x18009c3c0  movzx   ebp, byte ptr [r12+42h]
0x18009c3c6  test    ebp, ebp
0x18009c3c8  jz      short loc_18009C403
0x18009c3ca  mov     edx, r13d
0x18009c3cd  mov     rcx, rdi
0x18009c3d0  call    sqlite3VdbeChangeToNoop
0x18009c3d5  xor     r9d, r9d
0x18009c3d8  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c3e0  mov     r8d, r15d
0x18009c3e3  mov     rcx, rdi
0x18009c3e6  lea     edx, [r9+7Ah]
0x18009c3ea  call    sqlite3VdbeAddOp3
0x18009c3ef  mov     rax, [rsp+0B8h+var_60]
0x18009c3f4  mov     r15d, [rsp+0B8h+var_74]
0x18009c3f9  mov     [rsp+0B8h+var_60], rax
0x18009c3fe  jmp     loc_18009C4F4
0x18009c403  mov     rax, [rsi+0B0h]
0x18009c40a  mov     rcx, rsi
0x18009c40d  mov     r13d, dword ptr [rsp+0B8h+var_68]
0x18009c412  test    rax, rax
0x18009c415  mov     r9d, [rsp+0B8h+var_78]
0x18009c41a  mov     r8d, ebx
0x18009c41d  cmovnz  rcx, rax
0x18009c421  mov     dword ptr [rsp+0B8h+var_98], r13d
0x18009c426  mov     edx, 61h ; 'a'
0x18009c42b  mov     byte ptr [rcx+20h], 1
0x18009c42f  mov     rcx, rdi
0x18009c432  call    sqlite3VdbeAddOp3
0x18009c437  mov     r15d, [rsp+0B8h+var_74]
0x18009c43c  lea     ebx, [r13+1]
0x18009c440  mov     r9d, ebx
0x18009c443  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c44b  mov     r8d, r15d
0x18009c44e  mov     edx, 7Fh
0x18009c453  mov     rcx, rdi
0x18009c456  call    sqlite3VdbeAddOp3
0x18009c45b  mov     r9d, r13d
0x18009c45e  mov     dword ptr [rsp+0B8h+var_98], ebx
0x18009c462  mov     r8d, r15d
0x18009c465  mov     edx, 80h
0x18009c46a  mov     rcx, rdi
0x18009c46d  call    sqlite3VdbeAddOp3
0x18009c472  mov     rax, [rsp+0B8h+var_60]
0x18009c477  mov     r13, [rsp+0B8h+arg_8]
0x18009c47f  mov     [rsp+0B8h+var_60], rax
0x18009c484  cmp     dword ptr [r13+0], 1
0x18009c489  jnz     short loc_18009C493
0x18009c48b  mov     rcx, r12
0x18009c48e  call    sqlite3WhereEnd
0x18009c493  xor     r9d, r9d
0x18009c496  mov     dword ptr [rsp+0B8h+var_98], 0
0x18009c49e  mov     r8d, r15d
0x18009c4a1  mov     rcx, rdi
0x18009c4a4  lea     edx, [r9+24h]
0x18009c4a8  call    sqlite3VdbeAddOp3
0x18009c4ad  xor     ebx, ebx
0x18009c4af  mov     r13d, eax
0x18009c4b2  cmp     [rsp+0B8h+var_78], ebx
0x18009c4b6  jle     short loc_18009C4F4
0x18009c4b8  mov     r14d, [rsp+0B8h+arg_0]
0x18009c4c0  mov     r12d, [rsp+0B8h+var_78]
0x18009c4c5  lea     ecx, [r14+rbx]
0x18009c4c9  mov     r9d, ebx
0x18009c4cc  mov     dword ptr [rsp+0B8h+var_98], ecx
0x18009c4d0  mov     r8d, r15d
0x18009c4d3  mov     rcx, rdi
0x18009c4d6  mov     edx, 5Eh ; '^'
0x18009c4db  call    sqlite3VdbeAddOp3
0x18009c4e0  inc     ebx
0x18009c4e2  cmp     ebx, r12d
0x18009c4e5  jl      short loc_18009C4C5
  ... truncated ...
```

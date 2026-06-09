# updateVirtualTable

- ea: `0x1800a14d0`
- end: `0x1800a1a58`
- name: `updateVirtualTable`
- size: `1416`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x18000a954`

## callees

- `0x18000506c`
- `0x1800071dc`
- `0x180007ac0`
- `0x180008be8`
- `0x18000d04c`
- `0x180014270`
- `0x180015540`
- `0x180015700`
- `0x1800168c0`
- `0x18001b16c`
- `0x18001bc40`
- `0x18001cb40`
- `0x18002319c`
- `0x1800619e8`
- `0x18006a580`
- `0x180072a38`
- `0x18007e6dc`
- `0x1800a14d0`

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
  __int64 v41; // r8
  __int64 v42; // r9
  int v43; // [rsp+40h] [rbp-78h]
  int v44; // [rsp+44h] [rbp-74h]
  int v45; // [rsp+50h] [rbp-68h]
  __int64 VTable; // [rsp+58h] [rbp-60h]
  __int64 v47; // [rsp+60h] [rbp-58h]
  int v48; // [rsp+C0h] [rbp+8h]

  v8 = a1[2];
  v9 = a1;
  v10 = *a1;
  v12 = a2[19];
  VTable = sqlite3GetVTable(*a1, a3);
  v43 = *(__int16 *)(v14 + 54) + 2;
  v44 = *((_DWORD *)v9 + 13);
  *((_DWORD *)v9 + 13) = v44 + 1;
  v15 = sqlite3VdbeAddOp3(v8, 118, v44, v43, 0);
  v16 = *((_DWORD *)v9 + 14);
  v17 = v16 + v43;
  *((_DWORD *)v9 + 14) = v16 + v43;
  v18 = v16 + 1;
  v48 = v16 + 1;
  if ( *a2 > 1 )
  {
    v47 = 0;
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
    v27 = v44;
    v28 = a2;
    updateFromSelect((_DWORD)v9, v44, v26, v23, (__int64)a2, a7);
    sqlite3ExprListDeleteGeneric(v10, v23);
    v29 = 0;
    v30 = 0;
LABEL_35:
    if ( *v28 == 1 )
      sqlite3WhereEnd(v30);
    v39 = 0;
    v15 = sqlite3VdbeAddOp3(v8, 36, v27, 0, 0);
    if ( v43 > 0 )
    {
      do
      {
        sqlite3VdbeAddOp3(v8, 94, v27, v39, v48 + v39);
        ++v39;
      }
      while ( v39 < v43 );
      v30 = v47;
    }
    goto LABEL_40;
  }
  v45 = v17 + 1;
  *((_DWORD *)v9 + 14) = v17 + 2;
  result = sqlite3WhereBegin((_DWORD)v9, (_DWORD)a2, a7, 0, 0, 0, 4, 0);
  v47 = result;
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
    v30 = v47;
    v18 = v48;
  }
  v35 = v18 + 1;
  if ( *(char *)(a3 + 48) < 0 )
  {
    v37 = **(__int16 **)(sqlite3PrimaryKeyIndex(a3) + 8);
    sqlite3VdbeAddOp3(v8, 176, v12, v37, v48);
    sqlite3VdbeAddOp3(v8, 81, v37 + v48 + 2, v35, 0);
    v36 = v48;
  }
  else
  {
    v36 = v48;
    sqlite3VdbeAddOp3(v8, 135, v12, v48, 0);
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
    sqlite3VdbeAddOp3(v8, 97, v36, v43, v45);
    v27 = v44;
    sqlite3VdbeAddOp3(v8, 127, v44, v45 + 1, 0);
    sqlite3VdbeAddOp3(v8, 128, v44, v45, v45 + 1);
    v28 = a2;
    goto LABEL_35;
  }
  sqlite3VdbeChangeToNoop(v8, v15);
  sqlite3VdbeAddOp3(v8, 122, v12, 0, 0);
  v27 = v44;
LABEL_40:
  sqlite3VtabMakeWritable(v9);
  sqlite3VdbeAddOp4(v8, 7, 0, v43, v48, VTable, -11);
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
  *(_DWORD *)(sqlite3VdbeGetOp(v8, v15, v41, v42) + 8) = *(_DWORD *)(v8 + 144);
  return sqlite3VdbeAddOp3(v8, 122, v27, 0, 0);
}

```

## disassembly

```asm
0x1800a14d0  mov     [rsp+arg_18], r9
0x1800a14d5  mov     [rsp+arg_10], r8
0x1800a14da  mov     [rsp+arg_8], rdx
0x1800a14df  push    rbx
0x1800a14e0  push    rbp
0x1800a14e1  push    rsi
0x1800a14e2  push    rdi
0x1800a14e3  push    r12
0x1800a14e5  push    r13
0x1800a14e7  push    r14
0x1800a14e9  push    r15
0x1800a14eb  sub     rsp, 78h
0x1800a14ef  mov     rdi, [rcx+10h]
0x1800a14f3  mov     rsi, rcx
0x1800a14f6  mov     r12, [rcx]
0x1800a14f9  mov     rbx, r9
0x1800a14fc  mov     r15d, [rdx+4Ch]
0x1800a1500  mov     rcx, r12
0x1800a1503  mov     rdx, r8
0x1800a1506  mov     [rsp+0B8h+var_68], rdi
0x1800a150b  mov     r14, r8
0x1800a150e  call    sqlite3GetVTable
0x1800a1513  movsx   ecx, word ptr [r8+36h]
0x1800a1518  mov     edx, 76h ; 'v'
0x1800a151d  mov     r8d, [rsi+34h]
0x1800a1521  add     ecx, 2
0x1800a1524  mov     [rsp+0B8h+var_60], rax
0x1800a1529  mov     r9d, ecx
0x1800a152c  mov     [rsp+0B8h+var_78], ecx
0x1800a1530  mov     rcx, rdi
0x1800a1533  mov     [rsp+0B8h+var_74], r8d
0x1800a1538  lea     eax, [r8+1]
0x1800a153c  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a1544  mov     [rsi+34h], eax
0x1800a1547  call    sqlite3VdbeAddOp3
0x1800a154c  mov     ecx, [rsp+0B8h+var_78]
0x1800a1550  mov     r13d, eax
0x1800a1553  mov     rdx, [rsp+0B8h+arg_8]
0x1800a155b  mov     [rsp+0B8h+var_6C], eax
0x1800a155f  mov     eax, [rsi+38h]
0x1800a1562  add     ecx, eax
0x1800a1564  mov     [rsi+38h], ecx
0x1800a1567  cmp     dword ptr [rdx], 1
0x1800a156a  lea     ebp, [rax+1]
0x1800a156d  mov     [rsp+0B8h+arg_0], ebp
0x1800a1574  jle     loc_1800A16CD
0x1800a157a  test    byte ptr [r14+30h], 80h
0x1800a157f  mov     [rsp+0B8h+var_58], 0
0x1800a1588  jnz     short loc_1800A15C3
0x1800a158a  mov     rdx, [rsp+0B8h+arg_20]
0x1800a1592  xor     r15d, r15d
0x1800a1595  test    rdx, rdx
0x1800a1598  jz      short loc_1800A15A7
0x1800a159a  xor     r8d, r8d
0x1800a159d  mov     rcx, r12
0x1800a15a0  call    sqlite3ExprDup
0x1800a15a5  jmp     short loc_1800A15B9
0x1800a15a7  xor     r9d, r9d
0x1800a15aa  xor     r8d, r8d
0x1800a15ad  mov     rcx, rsi
0x1800a15b0  lea     edx, [r9+4Bh]
0x1800a15b4  call    sqlite3PExpr
0x1800a15b9  mov     r13, [rsp+0B8h+arg_28]
0x1800a15c1  jmp     short loc_1800A160B
0x1800a15c3  mov     rcx, r14
0x1800a15c6  call    sqlite3PrimaryKeyIndex
0x1800a15cb  mov     r13, [rsp+0B8h+arg_28]
0x1800a15d3  mov     r15, rax
0x1800a15d6  mov     rax, [rax+8]
0x1800a15da  movsx   rcx, word ptr [rax]
0x1800a15de  cmp     dword ptr [r13+rcx*4+0], 0
0x1800a15e4  jl      short loc_1800A1601
0x1800a15e6  movsxd  rdx, dword ptr [r13+rcx*4+0]
0x1800a15eb  xor     r8d, r8d
0x1800a15ee  shl     rdx, 5
0x1800a15f2  mov     rcx, r12
0x1800a15f5  mov     rdx, [rdx+rbx+8]
0x1800a15fa  call    sqlite3ExprDup
0x1800a15ff  jmp     short loc_1800A160B
0x1800a1601  mov     edx, ecx
0x1800a1603  mov     rcx, rsi
0x1800a1606  call    exprRowColumn
0x1800a160b  mov     r8, rax
0x1800a160e  xor     edx, edx
0x1800a1610  mov     rcx, rsi
0x1800a1613  call    sqlite3ExprListAppend
0x1800a1618  mov     rbx, rax
0x1800a161b  xor     ebp, ebp
0x1800a161d  xor     eax, eax
0x1800a161f  cmp     ax, [r14+36h]
0x1800a1624  jge     short loc_1800A1688
0x1800a1626  mov     rdi, [rsp+0B8h+arg_18]
0x1800a162e  movsxd  rax, ebp
0x1800a1631  cmp     dword ptr [r13+rax*4+0], 0
0x1800a1637  jl      short loc_1800A1654
0x1800a1639  movsxd  rdx, dword ptr [r13+rax*4+0]
0x1800a163e  xor     r8d, r8d
0x1800a1641  shl     rdx, 5
0x1800a1645  mov     rcx, r12
0x1800a1648  mov     rdx, [rdx+rdi+8]
0x1800a164d  call    sqlite3ExprDup
0x1800a1652  jmp     short loc_1800A1667
0x1800a1654  mov     edx, ebp
0x1800a1656  mov     rcx, rsi
0x1800a1659  call    exprRowColumn
0x1800a165e  test    rax, rax
0x1800a1661  jz      short loc_1800A1667
0x1800a1663  mov     byte ptr [rax+2], 1
0x1800a1667  mov     r8, rax
0x1800a166a  mov     rdx, rbx
0x1800a166d  mov     rcx, rsi
0x1800a1670  call    sqlite3ExprListAppend
0x1800a1675  mov     rbx, rax
0x1800a1678  inc     ebp
0x1800a167a  movsx   eax, word ptr [r14+36h]
0x1800a167f  cmp     ebp, eax
0x1800a1681  jl      short loc_1800A162E
0x1800a1683  mov     rdi, [rsp+0B8h+var_68]
0x1800a1688  mov     rax, [rsp+0B8h+arg_30]
0x1800a1690  mov     r8, r15
0x1800a1693  mov     r15d, [rsp+0B8h+var_74]
0x1800a1698  mov     r9, rbx
0x1800a169b  mov     r13, [rsp+0B8h+arg_8]
0x1800a16a3  mov     edx, r15d
0x1800a16a6  mov     [rsp+0B8h+var_90], rax
0x1800a16ab  mov     rcx, rsi
0x1800a16ae  mov     [rsp+0B8h+var_98], r13
0x1800a16b3  call    updateFromSelect
0x1800a16b8  mov     rdx, rbx
0x1800a16bb  mov     rcx, r12
0x1800a16be  call    sqlite3ExprListDeleteGeneric
0x1800a16c3  xor     ebp, ebp
0x1800a16c5  mov     r12d, ebp
0x1800a16c8  jmp     loc_1800A191C
0x1800a16cd  mov     r8, [rsp+0B8h+arg_30]
0x1800a16d5  lea     eax, [rcx+1]
0x1800a16d8  xor     ecx, ecx
0x1800a16da  mov     dword ptr [rsp+0B8h+var_68], eax
0x1800a16de  mov     [rsp+0B8h+var_80], ecx
0x1800a16e2  inc     eax
0x1800a16e4  mov     word ptr [rsp+0B8h+var_88], 4
0x1800a16eb  xor     r9d, r9d
0x1800a16ee  mov     [rsp+0B8h+var_90], rcx
0x1800a16f3  mov     [rsp+0B8h+var_98], rcx
0x1800a16f8  mov     rcx, rsi
0x1800a16fb  mov     [rsi+38h], eax
0x1800a16fe  call    sqlite3WhereBegin
0x1800a1703  mov     [rsp+0B8h+var_58], rax
0x1800a1708  mov     r12, rax
0x1800a170b  test    rax, rax
0x1800a170e  jz      loc_1800A1A47
0x1800a1714  xor     ebx, ebx
0x1800a1716  xor     ecx, ecx
0x1800a1718  cmp     cx, [r14+36h]
0x1800a171d  jge     short loc_1800A179B
0x1800a171f  mov     r13, [rsp+0B8h+arg_28]
0x1800a1727  add     ebp, 2
0x1800a172a  mov     r12, [rsp+0B8h+arg_18]
0x1800a1732  movsxd  rax, ebx
0x1800a1735  lea     ecx, [rbx+rbp]
0x1800a1738  cmp     dword ptr [r13+rax*4+0], 0
0x1800a173e  jl      short loc_1800A175B
0x1800a1740  movsxd  rdx, dword ptr [r13+rax*4+0]
0x1800a1745  mov     r8d, ecx
0x1800a1748  shl     rdx, 5
0x1800a174c  mov     rcx, rsi
0x1800a174f  mov     rdx, [rdx+r12+8]
0x1800a1754  call    sqlite3ExprCode
0x1800a1759  jmp     short loc_1800A177F
0x1800a175b  mov     dword ptr [rsp+0B8h+var_98], ecx
0x1800a175f  mov     r9d, ebx
0x1800a1762  mov     rcx, rdi
0x1800a1765  mov     r8d, r15d
0x1800a1768  mov     edx, 0B0h
0x1800a176d  call    sqlite3VdbeAddOp3
0x1800a1772  mov     edx, 1
0x1800a1777  mov     rcx, rdi
0x1800a177a  call    sqlite3VdbeChangeP5
0x1800a177f  movsx   eax, word ptr [r14+36h]
0x1800a1784  inc     ebx
0x1800a1786  cmp     ebx, eax
0x1800a1788  jl      short loc_1800A1732
0x1800a178a  mov     r13d, [rsp+0B8h+var_6C]
0x1800a178f  mov     r12, [rsp+0B8h+var_58]
0x1800a1794  mov     ebp, [rsp+0B8h+arg_0]
0x1800a179b  inc     ebp
0x1800a179d  test    byte ptr [r14+30h], 80h
0x1800a17a2  jnz     short loc_1800A17FD
0x1800a17a4  mov     ebx, [rsp+0B8h+arg_0]
0x1800a17ab  mov     r8d, r15d
0x1800a17ae  mov     r9d, ebx
0x1800a17b1  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a17b9  mov     edx, 87h
0x1800a17be  mov     rcx, rdi
0x1800a17c1  call    sqlite3VdbeAddOp3
0x1800a17c6  mov     rdx, [rsp+0B8h+arg_20]
0x1800a17ce  test    rdx, rdx
0x1800a17d1  jz      short loc_1800A17E0
0x1800a17d3  mov     r8d, ebp
0x1800a17d6  mov     rcx, rsi
0x1800a17d9  call    sqlite3ExprCode
0x1800a17de  jmp     short loc_1800A1858
0x1800a17e0  mov     r9d, ebp
0x1800a17e3  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a17eb  mov     r8d, r15d
0x1800a17ee  mov     edx, 87h
0x1800a17f3  mov     rcx, rdi
0x1800a17f6  call    sqlite3VdbeAddOp3
0x1800a17fb  jmp     short loc_1800A1858
0x1800a17fd  mov     rcx, r14
0x1800a1800  call    sqlite3PrimaryKeyIndex
0x1800a1805  mov     r8d, r15d
0x1800a1808  mov     edx, 0B0h
0x1800a180d  mov     rcx, [rax+8]
0x1800a1811  mov     eax, [rsp+0B8h+arg_0]
0x1800a1818  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800a181c  movsx   ebx, word ptr [rcx]
0x1800a181f  mov     rcx, rdi
0x1800a1822  mov     r9d, ebx
0x1800a1825  call    sqlite3VdbeAddOp3
0x1800a182a  mov     r8d, [rsp+0B8h+arg_0]
0x1800a1832  mov     r9d, ebp
0x1800a1835  add     r8d, 2
0x1800a1839  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a1841  add     r8d, ebx
0x1800a1844  mov     edx, 51h ; 'Q'
0x1800a1849  mov     rcx, rdi
0x1800a184c  call    sqlite3VdbeAddOp3
0x1800a1851  mov     ebx, [rsp+0B8h+arg_0]
0x1800a1858  movzx   ebp, byte ptr [r12+42h]
0x1800a185e  test    ebp, ebp
0x1800a1860  jz      short loc_1800A189B
0x1800a1862  mov     edx, r13d
0x1800a1865  mov     rcx, rdi
0x1800a1868  call    sqlite3VdbeChangeToNoop
0x1800a186d  xor     r9d, r9d
0x1800a1870  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a1878  mov     r8d, r15d
0x1800a187b  mov     rcx, rdi
0x1800a187e  lea     edx, [r9+7Ah]
0x1800a1882  call    sqlite3VdbeAddOp3
0x1800a1887  mov     rax, [rsp+0B8h+var_60]
0x1800a188c  mov     r15d, [rsp+0B8h+var_74]
0x1800a1891  mov     [rsp+0B8h+var_60], rax
0x1800a1896  jmp     loc_1800A198C
0x1800a189b  mov     rax, [rsi+0B0h]
0x1800a18a2  mov     rcx, rsi
0x1800a18a5  mov     r13d, dword ptr [rsp+0B8h+var_68]
0x1800a18aa  test    rax, rax
0x1800a18ad  mov     r9d, [rsp+0B8h+var_78]
0x1800a18b2  mov     r8d, ebx
0x1800a18b5  cmovnz  rcx, rax
0x1800a18b9  mov     dword ptr [rsp+0B8h+var_98], r13d
0x1800a18be  mov     edx, 61h ; 'a'
0x1800a18c3  mov     byte ptr [rcx+20h], 1
0x1800a18c7  mov     rcx, rdi
0x1800a18ca  call    sqlite3VdbeAddOp3
0x1800a18cf  mov     r15d, [rsp+0B8h+var_74]
0x1800a18d4  lea     ebx, [r13+1]
0x1800a18d8  mov     r9d, ebx
0x1800a18db  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a18e3  mov     r8d, r15d
0x1800a18e6  mov     edx, 7Fh
0x1800a18eb  mov     rcx, rdi
0x1800a18ee  call    sqlite3VdbeAddOp3
0x1800a18f3  mov     r9d, r13d
0x1800a18f6  mov     dword ptr [rsp+0B8h+var_98], ebx
0x1800a18fa  mov     r8d, r15d
0x1800a18fd  mov     edx, 80h
0x1800a1902  mov     rcx, rdi
0x1800a1905  call    sqlite3VdbeAddOp3
0x1800a190a  mov     rax, [rsp+0B8h+var_60]
0x1800a190f  mov     r13, [rsp+0B8h+arg_8]
0x1800a1917  mov     [rsp+0B8h+var_60], rax
0x1800a191c  cmp     dword ptr [r13+0], 1
0x1800a1921  jnz     short loc_1800A192B
0x1800a1923  mov     rcx, r12
0x1800a1926  call    sqlite3WhereEnd
0x1800a192b  xor     r9d, r9d
0x1800a192e  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800a1936  mov     r8d, r15d
0x1800a1939  mov     rcx, rdi
0x1800a193c  lea     edx, [r9+24h]
0x1800a1940  call    sqlite3VdbeAddOp3
0x1800a1945  xor     ebx, ebx
0x1800a1947  mov     r13d, eax
0x1800a194a  cmp     [rsp+0B8h+var_78], ebx
0x1800a194e  jle     short loc_1800A198C
0x1800a1950  mov     r14d, [rsp+0B8h+arg_0]
0x1800a1958  mov     r12d, [rsp+0B8h+var_78]
0x1800a195d  lea     ecx, [r14+rbx]
0x1800a1961  mov     r9d, ebx
0x1800a1964  mov     dword ptr [rsp+0B8h+var_98], ecx
0x1800a1968  mov     r8d, r15d
0x1800a196b  mov     rcx, rdi
0x1800a196e  mov     edx, 5Eh ; '^'
0x1800a1973  call    sqlite3VdbeAddOp3
0x1800a1978  inc     ebx
0x1800a197a  cmp     ebx, r12d
0x1800a197d  jl      short loc_1800A195D
  ... truncated ...
```

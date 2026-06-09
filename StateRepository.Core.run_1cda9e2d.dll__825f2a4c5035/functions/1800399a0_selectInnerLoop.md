# selectInnerLoop

- ea: `0x1800399a0`
- end: `0x18003a310`
- name: `selectInnerLoop`
- size: `2416`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: ``

## callers

- `0x180037194`
- `0x180043968`
- `0x180070c50`
- `0x18007a5a8`

## callees

- `0x180005c54`
- `0x1800119e0`
- `0x180011d80`
- `0x18001c1c4`
- `0x18001c220`
- `0x1800352fc`
- `0x180036688`
- `0x1800399a0`
- `0x18003a318`
- `0x18003abcc`
- `0x18003ff00`
- `0x1800443c8`
- `0x18004cfa0`
- `0x18005599c`
- `0x18005d030`
- `0x1800652f8`

## string_xrefs

- `0x18003a2e9`: `CREATE BLOOM FILTER`

## pseudocode

```c
__int64 __fastcall selectInnerLoop(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        unsigned int a7,
        int a8)
{
  _DWORD *v8; // r13
  int v9; // r11d
  __int64 v10; // rdi
  __int64 v12; // rbx
  __int64 v13; // rsi
  int v14; // r9d
  int v15; // r12d
  int v16; // eax
  char v17; // r10
  int v18; // ebp
  int v19; // eax
  int v20; // ecx
  __int64 result; // rax
  int v22; // r15d
  int v23; // edx
  int v24; // r9d
  int v25; // r8d
  int v26; // edx
  int v27; // r8d
  int i; // r13d
  unsigned int v29; // ebx
  unsigned int v30; // eax
  unsigned int TempReg; // ebx
  unsigned int v32; // ebx
  int v33; // r8d
  int *v34; // rcx
  int v35; // r8d
  __int64 v36; // rax
  __int16 v37; // cx
  int v38; // eax
  int v39; // eax
  unsigned int TempRange; // r13d
  int v41; // ebx
  __int64 v42; // rcx
  __int64 v43; // r8
  unsigned int v44; // r13d
  unsigned int v45; // eax
  bool v46; // zf
  int v47; // r12d
  int v48; // ebp
  int v49; // r15d
  __int64 v50; // rcx
  int v51; // r14d
  int v52; // ebx
  int v53; // r11d
  unsigned int v54; // ebx
  int v55; // edx
  int v56; // [rsp+40h] [rbp-68h]
  int v57; // [rsp+44h] [rbp-64h]
  int v58; // [rsp+48h] [rbp-60h]
  _QWORD v59[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v62; // [rsp+C0h] [rbp+18h]
  unsigned int v63; // [rsp+C0h] [rbp+18h]
  int v64; // [rsp+C8h] [rbp+20h]
  int *v65; // [rsp+D0h] [rbp+28h]
  unsigned int v66; // [rsp+D8h] [rbp+30h]

  v62 = a3;
  v8 = a6;
  v9 = 0;
  v10 = *(_QWORD *)(a1 + 16);
  v12 = a2;
  v56 = 0;
  v13 = a1;
  v59[0] = 0;
  v14 = 0;
  v15 = *(unsigned __int8 *)a6;
  v64 = a6[1];
  if ( a5 )
    v16 = *(unsigned __int8 *)(a5 + 1);
  else
    v16 = 0;
  v58 = v16;
  if ( a4 )
  {
    if ( *(_QWORD *)a4 )
      goto LABEL_6;
    a4 = 0;
  }
  if ( !v16 )
  {
    codeOffset(v10, *(unsigned int *)(a2 + 12), a7);
    v14 = 0;
    v9 = 0;
    a3 = v62;
  }
LABEL_6:
  v17 = 1;
  v18 = **(_DWORD **)(v12 + 32);
  v19 = a6[3];
  if ( v19 )
  {
    v20 = *(_DWORD *)(v13 + 60);
    result = (unsigned int)(v18 + v19);
    if ( (int)result > v20 )
    {
      result = (unsigned int)(v20 + v18);
      *(_DWORD *)(v13 + 60) = result;
    }
  }
  else
  {
    if ( a4 )
    {
      v14 = **(_DWORD **)a4 + 1;
      if ( (*(_BYTE *)(a4 + 36) & 1) != 0 )
        v14 = **(_DWORD **)a4;
      *(_DWORD *)(v13 + 60) += v14;
      v56 = v14;
    }
    result = (unsigned int)(*(_DWORD *)(v13 + 60) + 1);
    a6[3] = result;
    *(_DWORD *)(v13 + 60) += v18;
  }
  v22 = a6[3];
  v23 = v22;
  v57 = v22;
  a6[4] = v18;
  if ( (a3 & 0x80000000) == 0LL )
  {
    if ( v18 <= 0 )
      goto LABEL_11;
    for ( i = 0; i < v18; ++i )
      result = sqlite3VdbeAddOp3(v10, 94, v62, i, v22 + i);
    v13 = a1;
    v8 = a6;
    LODWORD(v12) = a2;
    goto LABEL_23;
  }
  if ( (_BYTE)v15 != 3 )
  {
    if ( (((_BYTE)v15 - 9) & 0xFA) != 0 || (_BYTE)v15 == 14 )
      v17 = 0;
    if ( a4 && !v58 && (((_BYTE)v15 - 12) & 0xFD) != 0 )
    {
      v34 = *(int **)a4;
      v17 |= 0xCu;
      v35 = *(_DWORD *)(a4 + 8);
      if ( v35 < **(_DWORD **)a4 )
      {
        do
        {
          v36 = 8 * (v35 + 1LL);
          if ( LOWORD(v34[v36]) )
            *(_WORD *)(32LL * LOWORD(v34[v36]) + *(_QWORD *)(v12 + 32)) = v35 - *(_WORD *)(a4 + 8) + 1;
          v34 = *(int **)a4;
          ++v35;
        }
        while ( v35 < **(_DWORD **)a4 );
        v14 = v56;
        v23 = v22;
      }
      a3 = *(_QWORD *)(v12 + 32);
      if ( *(int *)a3 > 0 )
      {
        do
        {
          v37 = *(_WORD *)(32 * ((unsigned int)v9 + 1LL) + a3);
          v38 = 0;
          if ( !v37 )
            v38 = v23;
          v23 = v38;
          v39 = v18 - 1;
          if ( !v37 )
            v39 = v18;
          ++v9;
          v18 = v39;
        }
        while ( v9 < *(_DWORD *)a3 );
        v13 = a1;
        v8 = a6;
        v57 = v23;
      }
      v9 = 0;
    }
    LODWORD(v59[0]) = v22;
    BYTE4(v59[0]) = v17;
    if ( *(_DWORD *)(v12 + 8) && (v17 & 8) != 0 && v14 > 0 )
    {
      result = (__int64)v59;
      v57 = 0;
      *(_QWORD *)(a4 + 40) = v59;
      goto LABEL_11;
    }
    result = sqlite3ExprCodeExprList(v13, *(_QWORD *)(v12 + 32), v22, 0, v17);
LABEL_23:
    v9 = 0;
  }
LABEL_11:
  if ( v58 )
  {
    v29 = *(unsigned __int8 *)(a5 + 1);
    v30 = codeDistinct(v13, v29, *(_DWORD *)(a5 + 4), a7, *(_QWORD *)(a2 + 32), v22);
    result = fixDistinctOpenEph(v13, v29, v30, *(unsigned int *)(a5 + 8));
    LODWORD(v12) = a2;
    v9 = 0;
    if ( !a4 )
    {
      result = codeOffset(v10, *(unsigned int *)(a2 + 12), a7);
      v9 = 0;
    }
  }
  if ( (unsigned __int8)v15 <= 9u )
  {
    if ( (_BYTE)v15 == 9 )
    {
LABEL_14:
      if ( a4 )
        return pushOntoSorter(v13, a4, v12, v22, v57, v18, v56);
      if ( (_BYTE)v15 == 13 )
      {
        v25 = v8[1];
        v24 = 0;
        v26 = 12;
      }
      else
      {
        v24 = v18;
        v25 = v22;
        v26 = 84;
      }
      sqlite3VdbeAddOp3(v10, v26, v25, v24, 0);
      goto LABEL_27;
    }
    switch ( v15 )
    {
      case 1:
        TempReg = sqlite3GetTempReg(v13);
        sqlite3VdbeAddOp3(v10, 97, v22, v18, TempReg);
        sqlite3VdbeAddOp4Int(v10, 138, v64, TempReg, v22, v18);
        result = sqlite3ReleaseTempReg(v13, TempReg);
        goto LABEL_41;
      case 2:
        result = sqlite3VdbeAddOp3(v10, 140, v64, v22, v18);
        goto LABEL_41;
      case 3:
        result = sqlite3VdbeAddOp3(v10, 71, 1, v64, 0);
LABEL_41:
        v9 = 0;
        break;
      case 5:
LABEL_81:
        TempRange = sqlite3GetTempRange(v13, (unsigned int)(v56 + 1), a3);
        sqlite3VdbeAddOp3(v10, 97, v22, v18, v56 + TempRange);
        if ( (_BYTE)v15 == 5 )
        {
          sqlite3VdbeAddOp4Int(v10, 29, v64 + 1, *(_DWORD *)(v10 + 144) + 4, TempRange, 0);
          sqlite3VdbeAddOp4Int(v10, 138, v64 + 1, TempRange, v22, v18);
        }
        if ( a4 )
        {
          pushOntoSorter(v13, a4, a2, v56 + TempRange, v57, 1, v56);
        }
        else
        {
          v54 = sqlite3GetTempReg(v13);
          sqlite3VdbeAddOp3(v10, 127, v64, v54, v55);
          sqlite3VdbeAddOp3(v10, 128, v64, TempRange, v54);
          sqlite3VdbeChangeP5(v10, 8);
          sqlite3ReleaseTempReg(v13, v54);
        }
        result = sqlite3ReleaseTempRange(v13, TempRange, (unsigned int)(v56 + 1));
        goto LABEL_41;
      case 6:
      case 7:
        v63 = 0;
        v65 = (int *)*((_QWORD *)v8 + 4);
        v41 = *v65;
        v66 = sqlite3GetTempReg(v13);
        v44 = sqlite3GetTempRange(v42, (unsigned int)(v41 + 2), v43);
        v45 = v44 + v41 + 1;
        if ( (_BYTE)v15 == 6 )
        {
          v63 = sqlite3VdbeAddOp4Int(v10, 29, v64 + 1, 0, v22, v18);
          v45 = v44 + v41 + 1;
        }
        sqlite3VdbeAddOp3(v10, 97, v22, v18, v45);
        v46 = (_BYTE)v15 == 6;
        v47 = v64;
        if ( v46 )
        {
          sqlite3VdbeAddOp3(v10, 138, v64 + 1, v44 + v41 + 1, 0);
          sqlite3VdbeChangeP5(v10, 16);
        }
        v48 = 0;
        if ( v41 > 0 )
        {
          v49 = v22 - 1;
          do
          {
            sqlite3VdbeAddOp3(v10, 81, v49 + LOWORD(v65[8 * v48 + 8]), v48 + v44, 0);
            ++v48;
          }
          while ( v48 < v41 );
          v13 = a1;
          v47 = v64;
        }
        sqlite3VdbeAddOp3(v10, 126, v47, v41 + v44, 0);
        sqlite3VdbeAddOp3(v10, 97, v44, v41 + 2, v66);
        sqlite3VdbeAddOp4Int(v10, 138, v47, v66, v44, v41 + 2);
        if ( v63 )
          *(_DWORD *)(sqlite3VdbeGetOp(v10, v63) + 8) = *(_DWORD *)(v10 + 144);
        sqlite3ReleaseTempReg(v13, v66);
        result = sqlite3ReleaseTempRange(v50, v44, (unsigned int)(v41 + 2));
        break;
      case 8:
        goto LABEL_81;
    }
LABEL_42:
    if ( a4 )
      return result;
    goto LABEL_28;
  }
  switch ( v15 )
  {
    case 10:
      if ( a4 )
        return pushOntoSorter(v13, a4, v12, v22, v57, v18, v56);
      goto LABEL_28;
    case 11:
      if ( a4 )
      {
        result = pushOntoSorter(v13, a4, v12, v22, v57, v18, v56);
        v8[2] = 0;
        return result;
      }
      v32 = sqlite3GetTempReg(v13);
      sqlite3VdbeAddOp4(v10, 97, v22, v18, v32, *((_QWORD *)v8 + 3), v18);
      sqlite3VdbeAddOp4Int(v10, 138, v64, v32, v22, v18);
      v33 = v8[2];
      if ( v33 )
      {
        sqlite3VdbeAddOp4Int(v10, 183, v33, 0, v22, v18);
        sqlite3VdbeExplain(v13, 0, "CREATE BLOOM FILTER");
      }
      sqlite3ReleaseTempReg(v13, v32);
      goto LABEL_28;
    case 12:
      goto LABEL_81;
    case 13:
      goto LABEL_14;
    case 14:
      goto LABEL_81;
  }
  if ( v15 != 15 )
    goto LABEL_42;
  if ( a4 )
    return pushOntoSorter(v13, a4, v12, v22, v57, v18, v56);
  v51 = v8[2];
  v52 = sqlite3GetTempReg(v13);
  sqlite3VdbeAddOp3(v10, 51, v22, a8, v53);
  sqlite3VdbeAddOp3(v10, 97, ((unsigned int)v51 >> 31) + v22, v18 - ((unsigned int)v51 >> 31), v52);
  if ( v51 >= 0 )
    sqlite3VdbeAddOp4Int(v10, 138, v64, v52, v22, v51);
  else
    sqlite3VdbeAddOp3(v10, 128, v64, v52, v22);
LABEL_27:
  v9 = 0;
LABEL_28:
  result = a2;
  v27 = *(_DWORD *)(a2 + 8);
  if ( v27 )
    return sqlite3VdbeAddOp3(v10, 61, v27, a8, v9);
  return result;
}

```

## disassembly

```asm
0x1800399a0  mov     [rsp+arg_10], r8d
0x1800399a5  mov     [rsp+arg_8], rdx
0x1800399aa  mov     [rsp+arg_0], rcx
0x1800399af  push    rbx
0x1800399b0  push    rbp
0x1800399b1  push    rsi
0x1800399b2  push    rdi
0x1800399b3  push    r12
0x1800399b5  push    r13
0x1800399b7  push    r14
0x1800399b9  push    r15
0x1800399bb  sub     rsp, 68h
0x1800399bf  mov     r13, [rsp+0A8h+arg_28]
0x1800399c7  xor     r11d, r11d
0x1800399ca  mov     rdi, [rcx+10h]
0x1800399ce  mov     r14, r9
0x1800399d1  mov     rbx, rdx
0x1800399d4  mov     [rsp+0A8h+var_68], r11d
0x1800399d9  mov     rsi, rcx
0x1800399dc  mov     [rsp+0A8h+var_58], r11
0x1800399e1  mov     eax, [r13+4]
0x1800399e5  mov     r9d, r11d
0x1800399e8  movzx   r12d, byte ptr [r13+0]
0x1800399ed  mov     [rsp+0A8h+arg_18], eax
0x1800399f4  mov     rax, [rsp+0A8h+arg_20]
0x1800399fc  test    rax, rax
0x1800399ff  jz      loc_180039ADA
0x180039a05  movzx   eax, byte ptr [rax+1]
0x180039a09  mov     [rsp+0A8h+var_60], eax
0x180039a0d  test    r14, r14
0x180039a10  jnz     loc_180039DB2
0x180039a16  test    eax, eax
0x180039a18  jnz     short loc_180039A3D
0x180039a1a  mov     r8d, [rsp+0A8h+arg_30]
0x180039a22  mov     rcx, rdi
0x180039a25  mov     edx, [rdx+0Ch]
0x180039a28  call    codeOffset
0x180039a2d  mov     r9d, [rsp+0A8h+var_68]
0x180039a32  xor     r11d, r11d
0x180039a35  mov     r8d, [rsp+0A8h+arg_10]
0x180039a3d  mov     rax, [rbx+20h]
0x180039a41  mov     r10d, 1
0x180039a47  mov     ebp, [rax]
0x180039a49  mov     eax, [r13+0Ch]
0x180039a4d  test    eax, eax
0x180039a4f  jz      loc_180039B8E
0x180039a55  mov     ecx, [rsi+3Ch]
0x180039a58  add     eax, ebp
0x180039a5a  cmp     eax, ecx
0x180039a5c  jg      loc_180039DE2
0x180039a62  mov     r15d, [r13+0Ch]
0x180039a66  mov     edx, r15d
0x180039a69  mov     [rsp+0A8h+var_64], edx
0x180039a6d  mov     [r13+10h], ebp
0x180039a71  test    r8d, r8d
0x180039a74  jns     loc_180039BA9
0x180039a7a  cmp     r12b, 3
0x180039a7e  jnz     short loc_180039AE2
0x180039a80  cmp     [rsp+0A8h+var_60], r11d
0x180039a85  jnz     loc_180039C56
0x180039a8b  cmp     r12b, 9
0x180039a8f  ja      loc_180039D27
0x180039a95  jnz     loc_180039C0B
0x180039a9b  test    r14, r14
0x180039a9e  jz      loc_180039B35
0x180039aa4  mov     eax, [rsp+0A8h+var_68]
0x180039aa8  mov     r9d, r15d
0x180039aab  mov     [rsp+0A8h+var_78], eax
0x180039aaf  mov     r8, rbx
0x180039ab2  mov     eax, [rsp+0A8h+var_64]
0x180039ab6  mov     rdx, r14
0x180039ab9  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180039abd  mov     rcx, rsi
0x180039ac0  mov     dword ptr [rsp+0A8h+var_88], eax
0x180039ac4  call    pushOntoSorter
0x180039ac9  add     rsp, 68h
0x180039acd  pop     r15
0x180039acf  pop     r14
0x180039ad1  pop     r13
0x180039ad3  pop     r12
0x180039ad5  pop     rdi
0x180039ad6  pop     rsi
0x180039ad7  pop     rbp
0x180039ad8  pop     rbx
0x180039ad9  retn
0x180039ada  mov     eax, r11d
0x180039add  jmp     loc_180039A09
0x180039ae2  lea     eax, [r12-9]
0x180039ae7  test    al, 0FAh
0x180039ae9  jnz     loc_180039DED
0x180039aef  cmp     r12b, 0Eh
0x180039af3  jz      loc_180039DED
0x180039af9  test    r14, r14
0x180039afc  jnz     loc_180039DF5
0x180039b02  mov     dword ptr [rsp+0A8h+var_58], r15d
0x180039b07  mov     byte ptr [rsp+0A8h+var_58+4], r10b
0x180039b0c  cmp     [rbx+8], r11d
0x180039b10  jnz     loc_180039EBB
0x180039b16  mov     rdx, [rbx+20h]
0x180039b1a  xor     r9d, r9d
0x180039b1d  mov     r8d, r15d
0x180039b20  mov     byte ptr [rsp+0A8h+var_88], r10b
0x180039b25  mov     rcx, rsi
0x180039b28  call    sqlite3ExprCodeExprList
0x180039b2d  xor     r11d, r11d
0x180039b30  jmp     loc_180039A80
0x180039b35  mov     dword ptr [rsp+0A8h+var_88], r11d
0x180039b3a  mov     rcx, rdi
0x180039b3d  cmp     r12b, 0Dh
0x180039b41  jz      loc_180039BFB
0x180039b47  mov     r9d, ebp
0x180039b4a  mov     r8d, r15d
0x180039b4d  mov     edx, 54h ; 'T'
0x180039b52  call    sqlite3VdbeAddOp3
0x180039b57  xor     r11d, r11d
0x180039b5a  mov     rax, [rsp+0A8h+arg_8]
0x180039b62  mov     r8d, [rax+8]
0x180039b66  test    r8d, r8d
0x180039b69  jz      loc_180039AC9
0x180039b6f  mov     r9d, [rsp+0A8h+arg_38]
0x180039b77  mov     edx, 3Dh ; '='
0x180039b7c  mov     rcx, rdi
0x180039b7f  mov     dword ptr [rsp+0A8h+var_88], r11d
0x180039b84  call    sqlite3VdbeAddOp3
0x180039b89  jmp     loc_180039AC9
0x180039b8e  test    r14, r14
0x180039b91  jnz     loc_180039DC3
0x180039b97  mov     eax, [rsi+3Ch]
0x180039b9a  add     eax, r10d
0x180039b9d  mov     [r13+0Ch], eax
0x180039ba1  add     [rsi+3Ch], ebp
0x180039ba4  jmp     loc_180039A62
0x180039ba9  test    ebp, ebp
0x180039bab  jle     loc_180039A80
0x180039bb1  mov     ebx, [rsp+0A8h+arg_10]
0x180039bb8  mov     r13d, r11d
0x180039bbb  lea     eax, [r15+r13]
0x180039bbf  mov     r9d, r13d
0x180039bc2  mov     r8d, ebx
0x180039bc5  mov     dword ptr [rsp+0A8h+var_88], eax
0x180039bc9  mov     edx, 5Eh ; '^'
0x180039bce  mov     rcx, rdi
0x180039bd1  call    sqlite3VdbeAddOp3
0x180039bd6  inc     r13d
0x180039bd9  cmp     r13d, ebp
0x180039bdc  jl      short loc_180039BBB
0x180039bde  mov     rsi, [rsp+0A8h+arg_0]
0x180039be6  mov     r13, [rsp+0A8h+arg_28]
0x180039bee  mov     rbx, [rsp+0A8h+arg_8]
0x180039bf6  jmp     loc_180039B2D
0x180039bfb  mov     r8d, [r13+4]
0x180039bff  xor     r9d, r9d
0x180039c02  lea     edx, [r9+0Ch]
0x180039c06  jmp     loc_180039B52
0x180039c0b  mov     ecx, r12d
0x180039c0e  sub     ecx, 1
0x180039c11  jz      loc_180039CD6
0x180039c17  sub     ecx, 1
0x180039c1a  jz      loc_18003A171
0x180039c20  sub     ecx, 1
0x180039c23  jnz     loc_180039EE1
0x180039c29  mov     r9d, [rsp+0A8h+arg_18]
0x180039c31  lea     edx, [rcx+47h]
0x180039c34  mov     dword ptr [rsp+0A8h+var_88], r11d
0x180039c39  lea     r8d, [rcx+1]
0x180039c3d  mov     rcx, rdi
0x180039c40  call    sqlite3VdbeAddOp3
0x180039c45  xor     r11d, r11d
0x180039c48  test    r14, r14
0x180039c4b  jnz     loc_180039AC9
0x180039c51  jmp     loc_180039B5A
0x180039c56  mov     rcx, [rsp+0A8h+arg_20]
0x180039c5e  mov     r8, [rsp+0A8h+arg_8]
0x180039c66  mov     r9d, [rsp+0A8h+arg_30]
0x180039c6e  mov     dword ptr [rsp+0A8h+var_80], r15d
0x180039c73  movzx   ebx, byte ptr [rcx+1]
0x180039c77  mov     rax, [r8+20h]
0x180039c7b  mov     edx, ebx
0x180039c7d  mov     r8d, [rcx+4]
0x180039c81  mov     rcx, rsi
0x180039c84  mov     [rsp+0A8h+var_88], rax
0x180039c89  call    codeDistinct
0x180039c8e  mov     r9, [rsp+0A8h+arg_20]
0x180039c96  mov     r8d, eax
0x180039c99  mov     edx, ebx
0x180039c9b  mov     rcx, rsi
0x180039c9e  mov     r9d, [r9+8]
0x180039ca2  call    fixDistinctOpenEph
0x180039ca7  mov     rbx, [rsp+0A8h+arg_8]
0x180039caf  xor     r11d, r11d
0x180039cb2  test    r14, r14
0x180039cb5  jnz     loc_180039A8B
0x180039cbb  mov     r8d, [rsp+0A8h+arg_30]
0x180039cc3  mov     rcx, rdi
0x180039cc6  mov     edx, [rbx+0Ch]
0x180039cc9  call    codeOffset
0x180039cce  xor     r11d, r11d
0x180039cd1  jmp     loc_180039A8B
0x180039cd6  mov     rcx, rsi
0x180039cd9  call    sqlite3GetTempReg
0x180039cde  mov     r9d, ebp
0x180039ce1  mov     dword ptr [rsp+0A8h+var_88], eax
0x180039ce5  mov     r8d, r15d
0x180039ce8  mov     edx, 61h ; 'a'
0x180039ced  mov     rcx, rdi
0x180039cf0  mov     ebx, eax
0x180039cf2  call    sqlite3VdbeAddOp3
0x180039cf7  mov     r8d, [rsp+0A8h+arg_18]
0x180039cff  mov     r9d, ebx
0x180039d02  mov     edx, 8Ah
0x180039d07  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180039d0b  mov     rcx, rdi
0x180039d0e  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180039d13  call    sqlite3VdbeAddOp4Int
0x180039d18  mov     edx, ebx
0x180039d1a  mov     rcx, rsi
0x180039d1d  call    sqlite3ReleaseTempReg
0x180039d22  jmp     loc_180039C45
0x180039d27  mov     ecx, r12d
0x180039d2a  sub     ecx, 0Ah
0x180039d2d  jz      loc_18003A302
0x180039d33  sub     ecx, 1
0x180039d36  jnz     loc_18003A18A
0x180039d3c  mov     rcx, rsi
0x180039d3f  test    r14, r14
0x180039d42  jnz     loc_18003A2A1
0x180039d48  call    sqlite3GetTempReg
0x180039d4d  mov     rcx, [r13+18h]
0x180039d51  lea     edx, [r14+61h]
0x180039d55  mov     [rsp+0A8h+var_78], ebp
0x180039d59  mov     r9d, ebp
0x180039d5c  mov     [rsp+0A8h+var_80], rcx
0x180039d61  mov     r8d, r15d
0x180039d64  mov     rcx, rdi
0x180039d67  mov     dword ptr [rsp+0A8h+var_88], eax
0x180039d6b  mov     ebx, eax
0x180039d6d  call    sqlite3VdbeAddOp4
0x180039d72  mov     r8d, [rsp+0A8h+arg_18]
0x180039d7a  mov     r9d, ebx
0x180039d7d  mov     edx, 8Ah
0x180039d82  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180039d86  mov     rcx, rdi
0x180039d89  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180039d8e  call    sqlite3VdbeAddOp4Int
0x180039d93  mov     r8d, [r13+8]
0x180039d97  xor     r11d, r11d
0x180039d9a  test    r8d, r8d
0x180039d9d  jnz     loc_18003A2D0
0x180039da3  mov     edx, ebx
0x180039da5  mov     rcx, rsi
0x180039da8  call    sqlite3ReleaseTempReg
0x180039dad  jmp     loc_180039B5A
0x180039db2  cmp     [r14], r11
0x180039db5  jnz     loc_180039A3D
0x180039dbb  mov     r14, r11
0x180039dbe  jmp     loc_180039A16
0x180039dc3  mov     rax, [r14]
0x180039dc6  test    [r14+24h], r10b
0x180039dca  mov     ecx, [rax]
0x180039dcc  lea     r9d, [rcx+1]
0x180039dd0  cmovnz  r9d, ecx
0x180039dd4  add     [rsi+3Ch], r9d
0x180039dd8  mov     [rsp+0A8h+var_68], r9d
0x180039ddd  jmp     loc_180039B97
0x180039de2  lea     eax, [rcx+rbp]
0x180039de5  mov     [rsi+3Ch], eax
0x180039de8  jmp     loc_180039A62
0x180039ded  mov     r10b, r11b
0x180039df0  jmp     loc_180039AF9
0x180039df5  cmp     [rsp+0A8h+var_60], r11d
0x180039dfa  jnz     loc_180039B02
0x180039e00  lea     eax, [r12-0Ch]
0x180039e05  test    al, 0FDh
0x180039e07  jz      loc_180039B02
0x180039e0d  mov     rcx, [r14]
0x180039e10  or      r10b, 0Ch
0x180039e14  mov     r8d, [r14+8]
0x180039e18  cmp     r8d, [rcx]
0x180039e1b  jge     short loc_180039E64
0x180039e1d  mov     r9d, 1
0x180039e23  movsxd  rax, r8d
0x180039e26  add     rax, r9
0x180039e29  shl     rax, 5
0x180039e2d  cmp     [rax+rcx], r11w
0x180039e32  jbe     short loc_180039E51
0x180039e34  movzx   ecx, word ptr [rax+rcx]
0x180039e38  movzx   edx, r8w
0x180039e3c  sub     dx, [r14+8]
0x180039e41  mov     rax, [rbx+20h]
0x180039e45  add     dx, r9w
0x180039e49  shl     rcx, 5
0x180039e4d  mov     [rcx+rax], dx
0x180039e51  mov     rcx, [r14]
0x180039e54  add     r8d, r9d
0x180039e57  cmp     r8d, [rcx]
0x180039e5a  jl      short loc_180039E23
0x180039e5c  mov     r9d, [rsp+0A8h+var_68]
0x180039e61  mov     edx, r15d
0x180039e64  mov     r8, [rbx+20h]
0x180039e68  cmp     dword ptr [r8], 0
  ... truncated ...
```

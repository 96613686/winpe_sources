# sqlite3DeleteFrom

- ea: `0x180008c0c`
- end: `0x180009686`
- name: `sqlite3DeleteFrom`
- size: `2682`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: ``

## callers

- `0x18000213c`
- `0x18004aec8`
- `0x18007be68`

## callees

- `0x18000506c`
- `0x1800071bc`
- `0x1800071dc`
- `0x180007ac0`
- `0x1800087d0`
- `0x1800087ec`
- `0x180008be8`
- `0x180008c0c`
- `0x180009ac0`
- `0x180009c54`
- `0x180009ccc`
- `0x180009e04`
- `0x180009ef0`
- `0x18000a754`
- `0x1800151f0`
- `0x180015460`
- `0x180015700`
- `0x180015750`
- `0x180015eb0`
- `0x1800168c0`
- `0x180018d00`
- `0x18001bb70`
- `0x18001cb40`
- `0x18001e090`
- `0x18001f0f0`
- `0x18001f418`
- `0x18002319c`
- `0x180025770`
- `0x180051998`
- `0x180052008`
- `0x1800588ac`
- `0x18005db24`
- `0x1800619e8`
- `0x180062418`
- `0x1800707f8`
- `0x180072a38`
- `0x180078968`
- `0x180090af4`

## string_xrefs

- `0x180009672`: `rows deleted`

## pseudocode

```c
__int64 __fastcall sqlite3DeleteFrom(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r15
  void *v6; // rbx
  _QWORD *v8; // rsi
  __int64 v9; // rax
  _QWORD *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rdi
  int v14; // r12d
  int v15; // edx
  __int64 v16; // rax
  int v17; // ecx
  __int64 Vdbe; // rax
  __int64 v19; // r9
  __int64 v20; // r15
  __int64 v21; // r13
  __int64 v22; // r9
  int v23; // r13d
  __int16 v24; // bx
  __int64 v25; // rdi
  int v26; // r8d
  int v27; // edx
  int v28; // eax
  int v29; // r8d
  __int64 v30; // rax
  char v31; // di
  __int64 v32; // rbx
  int v33; // r13d
  __int64 v34; // rdi
  int v35; // r12d
  void *v36; // rax
  _BYTE *v37; // r13
  int v38; // r9d
  int v39; // ecx
  unsigned int v40; // ebx
  int v41; // r13d
  int v42; // edx
  unsigned int v43; // ebx
  __int64 result; // rax
  __int64 i; // rbx
  int v46; // eax
  int v47; // r9d
  __int64 v48; // rax
  __int64 v49; // r9
  int v50; // ecx
  _QWORD *v51; // rcx
  int v52; // r9d
  int v53; // eax
  int v54; // edx
  __int64 VTable; // rdi
  _QWORD *v56; // rdx
  int v57; // r8d
  unsigned int v58; // r9d
  int v59; // edx
  __int64 v60; // r8
  __int64 v61; // r9
  int v62; // [rsp+28h] [rbp-E0h]
  __int64 v63; // [rsp+30h] [rbp-D8h]
  char v64; // [rsp+68h] [rbp-A0h]
  char v65; // [rsp+69h] [rbp-9Fh]
  int v66; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v67; // [rsp+70h] [rbp-98h]
  int v68; // [rsp+74h] [rbp-94h]
  int v69; // [rsp+78h] [rbp-90h]
  int v70; // [rsp+7Ch] [rbp-8Ch]
  unsigned int v71; // [rsp+80h] [rbp-88h]
  void *v72; // [rsp+88h] [rbp-80h]
  int v73; // [rsp+90h] [rbp-78h]
  int v74; // [rsp+94h] [rbp-74h] BYREF
  __int64 v75; // [rsp+98h] [rbp-70h]
  int v76; // [rsp+A0h] [rbp-68h]
  unsigned int v77; // [rsp+A4h] [rbp-64h]
  __int64 v78; // [rsp+A8h] [rbp-60h]
  __int64 v79; // [rsp+B0h] [rbp-58h]
  __int64 v80; // [rsp+B8h] [rbp-50h]
  __int64 v81; // [rsp+C0h] [rbp-48h]
  _QWORD *v82; // [rsp+C8h] [rbp-40h]
  __int64 v83; // [rsp+D0h] [rbp-38h]
  __int64 v84; // [rsp+D8h] [rbp-30h]
  __int128 v85; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v86; // [rsp+F0h] [rbp-18h]
  __int128 v87; // [rsp+100h] [rbp-8h]
  __int64 v88; // [rsp+110h] [rbp+8h]
  unsigned int v90; // [rsp+158h] [rbp+50h]

  v5 = *a1;
  v66 = 0;
  v6 = 0;
  v74 = 0;
  v8 = a1;
  v85 = 0;
  v88 = 0;
  v86 = 0;
  v72 = 0;
  v87 = 0;
  v78 = v5;
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_67;
  v9 = sqlite3SrcListLookup(a1, a2);
  v10 = (_QWORD *)v9;
  if ( !v9 )
    goto LABEL_67;
  if ( (*(_QWORD *)(v9 + 88) || (v11 = *(_QWORD *)(*(_QWORD *)(*v8 + 32LL) + 56LL)) != 0 && *(_QWORD *)(v11 + 64))
    && !*((_BYTE *)v8 + 229) )
  {
    v12 = triggersReallyExist((_DWORD)v8, (_DWORD)v10, 128, 0, 0);
  }
  else
  {
    v12 = 0;
  }
  v65 = *((_BYTE *)v10 + 63);
  v81 = v12;
  if ( v12 || (unsigned int)sqlite3FkRequired(v8, v10, 0, 0) )
    LODWORD(v6) = 1;
  if ( (unsigned int)sqlite3ViewGetColumnNames(v8, v10)
    || (unsigned int)sqlite3IsReadOnly(v8, v10, v12)
    || (v13 = (int)sqlite3SchemaToIndex(v5, v10[12]),
        v71 = sqlite3AuthCheck((_DWORD)v8, 9, *v10, 0, *(_QWORD *)(32 * v13 + *(_QWORD *)(v5 + 32))),
        v71 == 1) )
  {
    v6 = v72;
    goto LABEL_67;
  }
  v14 = *((_DWORD *)v8 + 13);
  v82 = 0;
  v15 = 0;
  v83 = 0;
  v68 = v14;
  v76 = 0;
  *(_DWORD *)(a2 + 76) = v14;
  ++*((_DWORD *)v8 + 13);
  v16 = v10[2];
  v17 = *((_DWORD *)v8 + 13);
  if ( v16 )
  {
    do
    {
      ++v17;
      ++v15;
      *((_DWORD *)v8 + 13) = v17;
      v16 = *(_QWORD *)(v16 + 40);
    }
    while ( v16 );
    v76 = v15;
  }
  if ( v65 == 2 )
  {
    v83 = v8[47];
    v8[47] = *v10;
    v82 = v8;
  }
  Vdbe = sqlite3GetVdbe(v8);
  v20 = Vdbe;
  if ( Vdbe )
  {
    if ( !*((_BYTE *)v8 + 30) )
      *(_DWORD *)(Vdbe + 200) |= 0x10u;
    sqlite3BeginWriteOperation(v8, (unsigned int)v6, (unsigned int)v13, v19);
    if ( v65 == 2 )
    {
      v49 = a4;
      v21 = a3;
      sqlite3MaterializeView(v8, v10, a3, v49, a5, v14);
      v74 = v14;
      v66 = v14;
    }
    else
    {
      v21 = a3;
    }
    v88 = 0;
    *((_QWORD *)&v85 + 1) = a2;
    v86 = 0;
    *(_QWORD *)&v85 = v8;
    v87 = 0;
    if ( !(unsigned int)sqlite3ResolveExprNames(&v85, v21) )
    {
      v23 = 0;
      v77 = 0;
      if ( (*(_QWORD *)(v78 + 48) & 0x100000000LL) != 0 && !*((_BYTE *)v8 + 30) && !v8[23] && !*((_BYTE *)v8 + 227) )
      {
        v23 = ++*((_DWORD *)v8 + 14);
        v77 = v23;
        sqlite3VdbeAddOp3(v20, 71, 0, v23, 0);
      }
      if ( !a3 && !v71 && !(_DWORD)v6 && *((_BYTE *)v10 + 63) != 1 )
      {
        LOBYTE(v22) = 1;
        sqlite3TableLock(v8, (unsigned int)v13, *((unsigned int *)v10 + 10), v22, *v10);
        if ( *((char *)v10 + 48) >= 0 )
        {
          v50 = -1;
          if ( v23 )
            v50 = v23;
          sqlite3VdbeAddOp4(v20, 145, *((_DWORD *)v10 + 10), v13, v50, *v10, -1);
        }
        for ( i = v10[2]; i; i = *(_QWORD *)(i + 40) )
        {
          if ( (*(_DWORD *)(i + 100) & 3) == 2 && *((char *)v10 + 48) < 0 )
          {
            v46 = -1;
            if ( v23 )
              v46 = v23;
          }
          else
          {
            v46 = 0;
          }
          sqlite3VdbeAddOp3(v20, 145, *(_DWORD *)(i + 88), v13, v46);
        }
        goto LABEL_60;
      }
      if ( (BYTE8(v87) & 0x40) != 0 )
        LOWORD(v6) = 1;
      v24 = (8 * ((unsigned __int16)v6 ^ 1)) | 0x14;
      if ( *((char *)v10 + 48) >= 0 )
      {
        v47 = ++*((_DWORD *)v8 + 14);
        v70 = 0;
        v69 = 0;
        v71 = 0;
        v75 = 0;
        LOWORD(v67) = 1;
        v73 = v47;
        sqlite3VdbeAddOp3(v20, 75, 0, v47, 0);
      }
      else
      {
        v73 = 0;
        v25 = sqlite3PrimaryKeyIndex(v10);
        v75 = v25;
        v62 = v26;
        v27 = *(unsigned __int16 *)(v25 + 94);
        v28 = *((_DWORD *)v8 + 14);
        v67 = v27;
        v70 = v28 + 1;
        v29 = *((_DWORD *)v8 + 13);
        *((_DWORD *)v8 + 14) = (__int16)v27 + v28;
        v69 = v29;
        *((_DWORD *)v8 + 13) = v29 + 1;
        v71 = sqlite3VdbeAddOp3(v20, 118, v29, (__int16)v27, v62);
        sqlite3VdbeSetP4KeyInfo(v8, v25);
      }
      v30 = sqlite3WhereBegin((_DWORD)v8, a2, a3, 0, 0, 0, v24, v14 + 1);
      v79 = v30;
      if ( !v30 )
        goto LABEL_65;
      v31 = *(_BYTE *)(v30 + 66);
      v32 = *(_QWORD *)(v30 + 40);
      v84 = v32;
      v80 = v32;
      v64 = v31;
      if ( v31 != 1 )
      {
        v51 = v8;
        if ( v8[22] )
          v51 = (_QWORD *)v8[22];
        *((_BYTE *)v51 + 32) = 1;
      }
      if ( (*(_BYTE *)(v30 + 68) & 1) != 0 )
        sqlite3VdbeAddOp3(v20, 143, v14, 0, 0);
      if ( v23 )
        sqlite3VdbeAddOp3(v20, 86, v23, 1, 0);
      v33 = (__int16)v67;
      if ( v75 )
      {
        v34 = 0;
        if ( (__int16)v67 > 0 )
        {
          do
          {
            sqlite3ExprCodeGetColumnOfTable(
              v20,
              (_DWORD)v10,
              v14,
              *(__int16 *)(*(_QWORD *)(v75 + 8) + 2 * v34),
              v70 + v34);
            v34 = (unsigned int)(v34 + 1);
          }
          while ( (int)v34 < (__int16)v67 );
          LODWORD(v32) = v84;
          v8 = a1;
        }
        v35 = v70;
        v31 = v64;
      }
      else
      {
        v35 = ++*((_DWORD *)v8 + 14);
        sqlite3VdbeAddOp3(v20, 135, v68, v35, 0);
      }
      if ( !v31 )
      {
        v90 = 0;
        if ( v75 )
        {
          v35 = ++*((_DWORD *)v8 + 14);
          v67 = 0;
          v48 = sqlite3IndexAffinityStr(*v8);
          sqlite3VdbeAddOp4(v20, 97, v70, v33, v35, v48, v33);
          sqlite3VdbeAddOp4Int(v20, 138, v69, v35, v70, v33);
        }
        else
        {
          LOWORD(v67) = 1;
          sqlite3VdbeAddOp3(v20, 156, v73, v35, 0);
        }
        sqlite3WhereEnd(v79);
        v37 = v72;
        goto LABEL_49;
      }
      v36 = (void *)sqlite3DbMallocRawNN(v78, v76 + 2);
      v72 = v36;
      v37 = v36;
      if ( v36 )
      {
        memset_0(v36, 1, v76 + 1LL);
        v39 = v68;
        v37[v76 + 1] = 0;
        if ( (int)v32 >= 0 )
          v37[(int)v32 - v39] = 0;
        if ( v80 >= 0 )
          v37[HIDWORD(v80) - v39] = 0;
        if ( v71 )
          sqlite3VdbeChangeToNoop(v20, v71);
        --*((_DWORD *)v8 + 17);
        v31 = v64;
        v90 = *((_DWORD *)v8 + 17);
LABEL_49:
        if ( v65 == 2 )
        {
          v41 = v68;
        }
        else
        {
          v40 = 0;
          if ( v31 == 2 )
            v40 = sqlite3VdbeAddOp3(v20, 15, 0, 0, 0);
          LOBYTE(v38) = 8;
          v63 = (__int64)v37;
          v41 = v68;
          sqlite3OpenTableAndIndices((_DWORD)v8, (_DWORD)v10, 113, v38, v68, v63, (__int64)&v66, (__int64)&v74);
          if ( v31 == 2 )
          {
            sqlite3VdbeJumpHereOrPopInst(v20, v40);
            goto LABEL_54;
          }
        }
        if ( !v31 )
        {
          if ( v75 )
          {
            v43 = sqlite3VdbeAddOp3(v20, 36, v69, 0, 0);
            if ( *((_BYTE *)v10 + 63) == 1 )
            {
              v52 = 0;
              v53 = v35;
            }
            else
            {
              v52 = v35;
              v53 = 0;
            }
            v54 = 94;
            if ( *((_BYTE *)v10 + 63) != 1 )
              v54 = 134;
            sqlite3VdbeAddOp3(v20, v54, v69, v52, v53);
          }
          else
          {
            v43 = sqlite3VdbeAddOp3(v20, 46, v73, 0, v35);
          }
          goto LABEL_110;
        }
LABEL_54:
        v42 = v66;
        v43 = 0;
        if ( *((_BYTE *)v10 + 63) == 1 )
          goto LABEL_119;
        if ( !*((_BYTE *)v72 + v66 - v41) )
        {
LABEL_56:
          if ( *((_BYTE *)v10 + 63) != 1 )
          {
            sqlite3GenerateRowDelete(
              (_DWORD)v8,
              (_DWORD)v10,
              v81,
              v42,
              v74,
              v35,
              v67,
              *((_BYTE *)v8 + 30) == 0,
              11,
              v31,
              HIDWORD(v80));
LABEL_58:
            if ( v31 )
            {
              sqlite3VdbeResolveLabel(v20, v90);
              sqlite3WhereEnd(v79);
            }
            else
            {
              if ( v75 )
              {
                v57 = v69;
                v58 = v43 + 1;
                v59 = 39;
              }
              else
              {
                v57 = 0;
                v58 = v43;
                v59 = 9;
              }
              sqlite3VdbeAddOp3(v20, v59, v57, v58, 0);
              *(_DWORD *)(sqlite3VdbeGetOp(v20, v43, v60, v61) + 8) = *(_DWORD *)(v20 + 144);
            }
LABEL_60:
            if ( !*((_BYTE *)v8 + 30) && !v8[23] )
              sqlite3AutoincrementEnd(v8);
            if ( v77 )
              sqlite3CodeChangeCount(v20, v77, "rows deleted");
            goto LABEL_65;
          }
LABEL_119:
          VTable = sqlite3GetVTable(v78, v10);
          sqlite3VtabMakeWritable(v8);
          v56 = v8;
          if ( v8[22] )
            v56 = (_QWORD *)v8[22];
          *((_BYTE *)v56 + 33) = 1;
          if ( v64 == 1 )
          {
            sqlite3VdbeAddOp3(v20, 122, v41, 0, 0);
            if ( !v8[22] )
              *((_BYTE *)v8 + 32) = 0;
          }
          sqlite3VdbeAddOp4(v20, 7, 0, 1, v35, VTable, -11);
          sqlite3VdbeChangeP5(v20, 2);
          v31 = v64;
          goto LABEL_58;
        }
        sqlite3VdbeAddOp4Int(v20, 28, v66, v90, v35, (__int16)v67);
LABEL_110:
        v42 = v66;
        goto LABEL_56;
      }
      sqlite3WhereEnd(v79);
    }
  }
LABEL_65:
  v6 = v72;
  v5 = v78;
  if ( v82 )
    v82[47] = v83;
LABEL_67:
  sqlite3SrcListDelete(v5, a2);
  result = a3;
  if ( a3 )
    result = sqlite3ExprDeleteNN(v5);
  if ( v6 )
    return sqlite3DbNNFreeNN(v5, v6);
  return result;
}

```

## disassembly

```asm
0x180008c0c  mov     rax, rsp
0x180008c0f  mov     [rax+20h], rbx
0x180008c13  mov     [rax+18h], r8
0x180008c17  mov     [rax+10h], rdx
0x180008c1b  mov     [rax+8], rcx
0x180008c1f  push    rbp
0x180008c20  push    rsi
0x180008c21  push    rdi
0x180008c22  push    r12
0x180008c24  push    r13
0x180008c26  push    r14
0x180008c28  push    r15
0x180008c2a  lea     rbp, [rax-48h]
0x180008c2e  sub     rsp, 110h
0x180008c35  mov     r15, [rcx]
0x180008c38  xorps   xmm0, xmm0
0x180008c3b  xor     eax, eax
0x180008c3d  mov     [rsp+140h+var_DC], 0
0x180008c45  xor     ebx, ebx
0x180008c47  mov     [rbp+40h+var_B4], 0
0x180008c4e  mov     r13, r9
0x180008c51  mov     rsi, rcx
0x180008c54  movups  [rbp+40h+var_68], xmm0
0x180008c58  mov     [rbp+40h+var_38], rax
0x180008c5c  movups  [rbp+40h+var_58], xmm0
0x180008c60  mov     [rbp+40h+var_C0], rbx
0x180008c64  movups  [rbp+40h+var_48], xmm0
0x180008c68  mov     [rbp+40h+var_A0], r15
0x180008c6c  cmp     [rcx+30h], eax
0x180008c6f  jnz     loc_180009149
0x180008c75  mov     rdx, [rbp+40h+arg_8]
0x180008c79  call    sqlite3SrcListLookup
0x180008c7e  mov     r14, rax
0x180008c81  test    rax, rax
0x180008c84  jz      loc_180009149
0x180008c8a  cmp     [rax+58h], rbx
0x180008c8e  jnz     loc_180009194
0x180008c94  mov     rax, [rsi]
0x180008c97  mov     rcx, [rax+20h]
0x180008c9b  mov     rax, [rcx+38h]
0x180008c9f  test    rax, rax
0x180008ca2  jz      short loc_180008CAE
0x180008ca4  cmp     [rax+40h], rbx
0x180008ca8  jnz     loc_180009194
0x180008cae  xor     edi, edi
0x180008cb0  mov     al, [r14+3Fh]
0x180008cb4  mov     r12d, 1
0x180008cba  mov     byte ptr [rsp+140h+var_E0+1], al
0x180008cbe  mov     [rbp+40h+var_88], rdi
0x180008cc2  test    rdi, rdi
0x180008cc5  jnz     loc_18000923F
0x180008ccb  xor     r9d, r9d
0x180008cce  xor     r8d, r8d
0x180008cd1  mov     rdx, r14
0x180008cd4  mov     rcx, rsi
0x180008cd7  call    sqlite3FkRequired
0x180008cdc  test    eax, eax
0x180008cde  jnz     loc_18000923F
0x180008ce4  mov     rdx, r14
0x180008ce7  mov     rcx, rsi
0x180008cea  call    sqlite3ViewGetColumnNames
0x180008cef  test    eax, eax
0x180008cf1  jnz     loc_180009270
0x180008cf7  mov     r8, rdi
0x180008cfa  mov     rdx, r14
0x180008cfd  mov     rcx, rsi
0x180008d00  call    sqlite3IsReadOnly
0x180008d05  test    eax, eax
0x180008d07  jnz     loc_180009270
0x180008d0d  mov     rdx, [r14+60h]
0x180008d11  mov     rcx, r15
0x180008d14  call    sqlite3SchemaToIndex
0x180008d19  mov     r8, [r14]
0x180008d1c  xor     r9d, r9d
0x180008d1f  movsxd  rdi, eax
0x180008d22  mov     rax, [r15+20h]
0x180008d26  mov     rcx, rdi
0x180008d29  shl     rcx, 5
0x180008d2d  lea     edx, [r9+9]
0x180008d31  mov     rcx, [rcx+rax]
0x180008d35  mov     [rsp+140h+var_120], rcx
0x180008d3a  mov     rcx, rsi
0x180008d3d  call    sqlite3AuthCheck
0x180008d42  mov     [rsp+140h+var_C8], eax
0x180008d46  cmp     eax, r12d
0x180008d49  jz      loc_180009270
0x180008d4f  mov     r12d, [rsi+34h]
0x180008d53  xor     eax, eax
0x180008d55  mov     [rbp+40h+var_80], rax
0x180008d59  xor     edx, edx
0x180008d5b  mov     rax, [rbp+40h+arg_8]
0x180008d5f  mov     r8d, 1
0x180008d65  mov     [rbp+40h+var_78], 0
0x180008d6d  mov     [rsp+140h+var_D4], r12d
0x180008d72  mov     [rbp+40h+var_A8], edx
0x180008d75  mov     [rax+4Ch], r12d
0x180008d79  add     [rsi+34h], r8d
0x180008d7d  mov     rax, [r14+10h]
0x180008d81  mov     ecx, [rsi+34h]
0x180008d84  test    rax, rax
0x180008d87  jz      short loc_180008D9D
0x180008d89  inc     ecx
0x180008d8b  add     edx, r8d
0x180008d8e  mov     [rsi+34h], ecx
0x180008d91  mov     rax, [rax+28h]
0x180008d95  test    rax, rax
0x180008d98  jnz     short loc_180008D89
0x180008d9a  mov     [rbp+40h+var_A8], edx
0x180008d9d  cmp     byte ptr [rsp+140h+var_E0+1], 2
0x180008da2  jz      loc_18000935C
0x180008da8  mov     rcx, rsi
0x180008dab  call    sqlite3GetVdbe
0x180008db0  mov     r15, rax
0x180008db3  test    rax, rax
0x180008db6  jz      loc_18000912D
0x180008dbc  cmp     byte ptr [rsi+1Eh], 0
0x180008dc0  jnz     short loc_180008DC9
0x180008dc2  or      dword ptr [rax+0C8h], 10h
0x180008dc9  mov     r8d, edi
0x180008dcc  mov     edx, ebx
0x180008dce  mov     rcx, rsi
0x180008dd1  call    sqlite3BeginWriteOperation
0x180008dd6  cmp     byte ptr [rsp+140h+var_E0+1], 2
0x180008ddb  jz      loc_18000937A
0x180008de1  mov     r13, [rbp+40h+arg_10]
0x180008de5  xorps   xmm0, xmm0
0x180008de8  lea     rcx, [rbp+40h+var_68]
0x180008dec  xor     eax, eax
0x180008dee  mov     rdx, r13
0x180008df1  movups  [rbp+40h+var_68], xmm0
0x180008df5  mov     [rbp+40h+var_38], rax
0x180008df9  mov     rax, [rbp+40h+arg_8]
0x180008dfd  mov     qword ptr [rbp+40h+var_68+8], rax
0x180008e01  movups  [rbp+40h+var_58], xmm0
0x180008e05  mov     qword ptr [rbp+40h+var_68], rsi
0x180008e09  movups  [rbp+40h+var_48], xmm0
0x180008e0d  call    sqlite3ResolveExprNames
0x180008e12  xor     r8d, r8d
0x180008e15  test    eax, eax
0x180008e17  jnz     loc_18000912D
0x180008e1d  mov     rax, [rbp+40h+var_A0]
0x180008e21  mov     rcx, 100000000h
0x180008e2b  mov     r13d, r8d
0x180008e2e  mov     [rbp+40h+var_A4], r8d
0x180008e32  test    [rax+30h], rcx
0x180008e36  jnz     loc_1800093AB
0x180008e3c  cmp     [rbp+40h+arg_10], r8
0x180008e40  jz      loc_1800091C1
0x180008e46  test    byte ptr [rbp+40h+var_48+8], 40h
0x180008e4a  mov     edi, 1
0x180008e4f  cmovnz  ebx, edi
0x180008e52  xor     bx, di
0x180008e55  shl     bx, 3
0x180008e59  or      bx, 14h
0x180008e5d  test    byte ptr [r14+30h], 80h
0x180008e62  jz      loc_180009283
0x180008e68  mov     rcx, r14
0x180008e6b  mov     [rbp+40h+var_B8], r8d
0x180008e6f  call    sqlite3PrimaryKeyIndex
0x180008e74  mov     rdi, rax
0x180008e77  mov     [rbp+40h+var_B0], rax
0x180008e7b  mov     dword ptr [rsp+140h+var_120], r8d
0x180008e80  movzx   edx, word ptr [rax+5Eh]
0x180008e84  mov     eax, [rsi+38h]
0x180008e87  movsx   r9d, dx
0x180008e8b  mov     [rsp+140h+var_D8], edx
0x180008e8f  mov     edx, 76h ; 'v'
0x180008e94  lea     ecx, [rax+1]
0x180008e97  add     eax, r9d
0x180008e9a  mov     [rsp+140h+var_CC], ecx
0x180008e9e  mov     ecx, [rsi+34h]
0x180008ea1  mov     r8d, ecx
0x180008ea4  mov     [rsi+38h], eax
0x180008ea7  mov     [rsp+140h+var_D0], ecx
0x180008eab  lea     eax, [rcx+1]
0x180008eae  mov     rcx, r15
0x180008eb1  mov     [rsi+34h], eax
0x180008eb4  call    sqlite3VdbeAddOp3
0x180008eb9  mov     rdx, rdi
0x180008ebc  mov     [rsp+140h+var_C8], eax
0x180008ec0  mov     rcx, rsi
0x180008ec3  call    sqlite3VdbeSetP4KeyInfo
0x180008ec8  mov     r8, [rbp+40h+arg_10]
0x180008ecc  lea     eax, [r12+1]
0x180008ed1  mov     rdx, [rbp+40h+arg_8]
0x180008ed5  xor     r9d, r9d
0x180008ed8  mov     dword ptr [rsp+140h+var_108], eax
0x180008edc  mov     rcx, rsi
0x180008edf  mov     word ptr [rsp+140h+var_110], bx
0x180008ee4  mov     [rsp+140h+var_118], 0
0x180008eed  mov     [rsp+140h+var_120], 0
0x180008ef6  call    sqlite3WhereBegin
0x180008efb  mov     [rbp+40h+var_98], rax
0x180008eff  mov     rdx, rax
0x180008f02  test    rax, rax
0x180008f05  jz      loc_18000912D
0x180008f0b  mov     dil, [rax+42h]
0x180008f0f  mov     r8d, 1
0x180008f15  mov     rbx, [rax+28h]
0x180008f19  mov     [rbp+40h+var_70], rbx
0x180008f1d  mov     [rbp+40h+var_90], rbx
0x180008f21  mov     byte ptr [rsp+140h+var_E0], dil
0x180008f26  cmp     dil, r8b
0x180008f29  jnz     loc_18000944D
0x180008f2f  test    [rdx+44h], r8b
0x180008f33  jnz     loc_180009467
0x180008f39  test    r13d, r13d
0x180008f3c  jnz     loc_18000948D
0x180008f42  cmp     [rbp+40h+var_B0], 0
0x180008f47  movsx   r13d, word ptr [rsp+140h+var_D8]
0x180008f4d  jz      loc_180009247
0x180008f53  xor     edi, edi
0x180008f55  test    r13d, r13d
0x180008f58  jle     short loc_180008F8F
0x180008f5a  mov     ebx, [rsp+140h+var_CC]
0x180008f5e  mov     rsi, [rbp+40h+var_B0]
0x180008f62  mov     rax, [rsi+8]
0x180008f66  lea     edx, [rbx+rdi]
0x180008f69  mov     dword ptr [rsp+140h+var_120], edx
0x180008f6d  mov     r8d, r12d
0x180008f70  mov     rdx, r14
0x180008f73  mov     rcx, r15
0x180008f76  movsx   r9d, word ptr [rax+rdi*2]
0x180008f7b  call    sqlite3ExprCodeGetColumnOfTable
0x180008f80  inc     edi
0x180008f82  cmp     edi, r13d
0x180008f85  jl      short loc_180008F62
0x180008f87  mov     rbx, [rbp+40h+var_70]
0x180008f8b  mov     rsi, [rbp+40h+arg_0]
0x180008f8f  mov     r12d, [rsp+140h+var_CC]
0x180008f94  mov     dil, byte ptr [rsp+140h+var_E0]
0x180008f99  xor     ecx, ecx
0x180008f9b  test    dil, dil
0x180008f9e  jz      loc_1800092C0
0x180008fa4  movsxd  rdi, [rbp+40h+var_A8]
0x180008fa8  mov     rcx, [rbp+40h+var_A0]
0x180008fac  lea     eax, [rdi+2]
0x180008faf  movsxd  rdx, eax
0x180008fb2  call    sqlite3DbMallocRawNN
0x180008fb7  mov     [rbp+40h+var_C0], rax
0x180008fbb  mov     r13, rax
0x180008fbe  test    rax, rax
0x180008fc1  jz      loc_1800094AD
0x180008fc7  lea     r8, [rdi+1]; Size
0x180008fcb  mov     edx, 1; Val
0x180008fd0  mov     rcx, rax; void *
0x180008fd3  call    memset_0
0x180008fd8  mov     ecx, [rsp+140h+var_D4]
0x180008fdc  xor     edx, edx
0x180008fde  mov     [rdi+r13+1], dl
0x180008fe3  test    ebx, ebx
0x180008fe5  jns     loc_1800094BB
0x180008feb  mov     eax, dword ptr [rbp+40h+var_90+4]
0x180008fee  test    eax, eax
0x180008ff0  js      short loc_180008FFA
0x180008ff2  sub     eax, ecx
0x180008ff4  cdqe
0x180008ff6  mov     [rax+r13], dl
0x180008ffa  mov     eax, [rsp+140h+var_C8]
0x180008ffe  test    eax, eax
0x180009000  jz      short loc_18000900C
0x180009002  mov     edx, eax
0x180009004  mov     rcx, r15
0x180009007  call    sqlite3VdbeChangeToNoop
0x18000900c  dec     dword ptr [rsi+44h]
0x18000900f  mov     ebx, [rsi+44h]
0x180009012  mov     dil, byte ptr [rsp+140h+var_E0]
0x180009017  mov     dword ptr [rbp+40h+arg_0], ebx
0x18000901a  cmp     byte ptr [rsp+140h+var_E0+1], 2
0x18000901f  jz      loc_180009279
0x180009025  xor     ebx, ebx
0x180009027  cmp     dil, 2
0x18000902b  jz      loc_1800094C9
0x180009031  lea     rax, [rbp+40h+var_B4]
0x180009035  mov     r9b, 8
0x180009038  mov     qword ptr [rsp+140h+var_108], rax
0x18000903d  mov     r8d, 71h ; 'q'
0x180009043  lea     rax, [rsp+140h+var_DC]
0x180009048  mov     rdx, r14
0x18000904b  mov     [rsp+140h+var_110], rax
0x180009050  mov     rcx, rsi
0x180009053  mov     [rsp+140h+var_118], r13
0x180009058  mov     r13d, [rsp+140h+var_D4]
0x18000905d  mov     dword ptr [rsp+140h+var_120], r13d
0x180009062  call    sqlite3OpenTableAndIndices
0x180009067  cmp     dil, 2
0x18000906b  jz      loc_1800094E6
0x180009071  test    dil, dil
0x180009074  jz      loc_180009520
0x18000907a  mov     edx, [rsp+140h+var_DC]
0x18000907e  xor     ebx, ebx
0x180009080  cmp     byte ptr [r14+3Fh], 1
0x180009085  jz      loc_180009593
0x18000908b  mov     rcx, [rbp+40h+var_C0]
0x18000908f  mov     eax, edx
0x180009091  sub     eax, r13d
0x180009094  cdqe
0x180009096  cmp     [rax+rcx], bl
0x180009099  jnz     loc_1800094F5
0x18000909f  cmp     byte ptr [r14+3Fh], 1
  ... truncated ...
```

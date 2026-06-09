# sqlite3DeleteFrom

- ea: `0x180019e50`
- end: `0x18001a809`
- name: `sqlite3DeleteFrom`
- size: `2489`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: ``

## callers

- `0x180018754`
- `0x180031b38`
- `0x180083f28`

## callees

- `0x180002ed0`
- `0x180005c54`
- `0x180008894`
- `0x18000c960`
- `0x18000ca30`
- `0x18000fa9c`
- `0x180010390`
- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x1800157d4`
- `0x1800184cc`
- `0x180018600`
- `0x18001861c`
- `0x180019e50`
- `0x18001c254`
- `0x1800351c8`
- `0x180036688`
- `0x180036730`
- `0x1800370c0`
- `0x1800398f0`
- `0x18003a8dc`
- `0x18003abcc`
- `0x18003e944`
- `0x18003f6dc`
- `0x18004036c`
- `0x180053ecc`
- `0x18005a2c4`
- `0x18005fbb8`
- `0x18006074c`
- `0x180060e90`
- `0x180063dc8`
- `0x180065204`
- `0x1800671d4`
- `0x180067de4`
- `0x18006910e`
- `0x180082690`
- `0x18008513c`

## string_xrefs

- `0x18001a790`: `rows deleted`

## pseudocode

```c
__int64 __fastcall sqlite3DeleteFrom(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  void *v4; // rbx
  __int64 *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // edi
  int v11; // r12d
  int v12; // r13d
  int v13; // edx
  __int64 v14; // rax
  int v15; // ecx
  __int64 Vdbe; // rax
  __int64 v17; // r15
  __int64 v18; // r9
  int v19; // ecx
  __int64 i; // rbx
  int v21; // eax
  __int16 v22; // bx
  int v23; // edi
  int v24; // eax
  __int64 v25; // r12
  int v26; // eax
  int v27; // r8d
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rbx
  char v32; // al
  __int64 *v33; // rcx
  __int64 v34; // rdi
  int v35; // r12d
  int v36; // r9d
  _BYTE *v37; // rdx
  int v38; // ecx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  char v42; // di
  unsigned int v43; // ebx
  int v44; // r13d
  int v45; // edx
  unsigned int v46; // ebx
  int v47; // r9d
  int v48; // eax
  int v49; // edx
  __int64 VTable; // rdi
  __int64 *v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // r8d
  unsigned int v55; // r9d
  int v56; // edx
  __int64 result; // rax
  int v58; // [rsp+68h] [rbp-A0h] BYREF
  int v59; // [rsp+6Ch] [rbp-9Ch]
  int v60; // [rsp+70h] [rbp-98h]
  int v61; // [rsp+74h] [rbp-94h]
  unsigned int v62; // [rsp+78h] [rbp-90h]
  int v63; // [rsp+7Ch] [rbp-8Ch]
  void *v64; // [rsp+80h] [rbp-88h]
  int v65; // [rsp+88h] [rbp-80h]
  int v66; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v67; // [rsp+90h] [rbp-78h]
  int v68; // [rsp+94h] [rbp-74h]
  unsigned int v69; // [rsp+98h] [rbp-70h]
  __int64 v70; // [rsp+A0h] [rbp-68h]
  __int64 v71; // [rsp+A8h] [rbp-60h]
  __int64 v72; // [rsp+B0h] [rbp-58h]
  __int64 v73; // [rsp+B8h] [rbp-50h]
  __int64 v74; // [rsp+C0h] [rbp-48h]
  __int64 *v75; // [rsp+C8h] [rbp-40h]
  __int64 v76; // [rsp+D0h] [rbp-38h]
  __int64 v77; // [rsp+D8h] [rbp-30h]
  __int128 v78; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v79; // [rsp+F0h] [rbp-18h]
  __int128 v80; // [rsp+100h] [rbp-8h]
  __int64 v81; // [rsp+110h] [rbp+8h]
  unsigned int v83; // [rsp+168h] [rbp+60h]
  char v86; // [rsp+180h] [rbp+78h]
  char v88; // [rsp+188h] [rbp+80h]

  v3 = *a1;
  v58 = 0;
  v4 = 0;
  v66 = 0;
  v5 = a1;
  v81 = 0;
  v78 = 0;
  v64 = 0;
  v79 = 0;
  v71 = v3;
  v80 = 0;
  if ( *((_DWORD *)a1 + 13) )
    goto LABEL_124;
  v6 = sqlite3SrcListLookup(a1, a2);
  v7 = v6;
  if ( !v6 )
    goto LABEL_124;
  if ( (*(_QWORD *)(v6 + 88) || (v8 = *(_QWORD *)(*(_QWORD *)(*v5 + 32) + 56LL)) != 0 && *(_QWORD *)(v8 + 64))
    && !*((_BYTE *)v5 + 229) )
  {
    v9 = triggersReallyExist((_DWORD)v5, v7, 129, 0, 0);
  }
  else
  {
    v9 = 0;
  }
  v88 = *(_BYTE *)(v7 + 63);
  v74 = v9;
  if ( v9 || (unsigned int)sqlite3FkRequired(v5, v7, 0, 0) )
    LODWORD(v4) = 1;
  if ( (unsigned int)sqlite3ViewGetColumnNames(v5, v7)
    || (unsigned int)sqlite3IsReadOnly(v5, v7, v9)
    || (v10 = sqlite3SchemaToIndex(v3, *(_QWORD *)(v7 + 96)),
        v11 = sqlite3AuthCheck((_DWORD)v5, 9, *(_QWORD *)v7, 0, *(_QWORD *)(32LL * (int)v10 + *(_QWORD *)(v3 + 32))),
        v11 == 1) )
  {
    v4 = v64;
    goto LABEL_124;
  }
  v12 = *((_DWORD *)v5 + 14);
  v75 = 0;
  v13 = 0;
  v76 = 0;
  v59 = v12;
  v68 = 0;
  *(_DWORD *)(a2 + 40) = v12;
  ++*((_DWORD *)v5 + 14);
  v14 = *(_QWORD *)(v7 + 16);
  v15 = *((_DWORD *)v5 + 14);
  if ( v14 )
  {
    do
    {
      ++v15;
      ++v13;
      *((_DWORD *)v5 + 14) = v15;
      v14 = *(_QWORD *)(v14 + 40);
    }
    while ( v14 );
    v68 = v13;
  }
  if ( v88 == 2 )
  {
    v76 = v5[47];
    v5[47] = *(_QWORD *)v7;
    v75 = v5;
  }
  Vdbe = sqlite3GetVdbe(v5);
  v17 = Vdbe;
  if ( Vdbe )
  {
    if ( !*((_BYTE *)v5 + 30) )
      *(_DWORD *)(Vdbe + 200) |= 0x10u;
    sqlite3BeginWriteOperation(v5, (unsigned int)v4, v10);
    if ( v88 == 2 )
    {
      sqlite3MaterializeView((_DWORD)v5, v7, a3, 0, 0, v12);
      v66 = v12;
      v58 = v12;
    }
    v81 = 0;
    *((_QWORD *)&v78 + 1) = a2;
    v79 = 0;
    *(_QWORD *)&v78 = v5;
    v80 = 0;
    if ( !(unsigned int)sqlite3ResolveExprNames(&v78, a3) )
    {
      v62 = 0;
      if ( (*(_QWORD *)(v71 + 48) & 0x100000000LL) != 0 && !*((_BYTE *)v5 + 30) && !v5[23] && !*((_BYTE *)v5 + 227) )
      {
        v62 = ++*((_DWORD *)v5 + 15);
        sqlite3VdbeAddOp3(v17, 71, 0, v62, 0);
      }
      if ( !v11 && !a3 && !(_DWORD)v4 && *(_BYTE *)(v7 + 63) != 1 )
      {
        LOBYTE(v18) = 1;
        sqlite3TableLock(v5, v10, *(unsigned int *)(v7 + 40), v18, *(_QWORD *)v7);
        if ( *(char *)(v7 + 48) >= 0 )
        {
          v19 = -1;
          if ( v62 )
            v19 = v62;
          sqlite3VdbeAddOp4(v17, 145, *(_DWORD *)(v7 + 40), v10, v19, *(_QWORD *)v7, -1);
        }
        for ( i = *(_QWORD *)(v7 + 16); i; i = *(_QWORD *)(i + 40) )
        {
          if ( (*(_DWORD *)(i + 100) & 3) == 2 && *(char *)(v7 + 48) < 0 )
          {
            v21 = -1;
            if ( v62 )
              v21 = v62;
          }
          else
          {
            v21 = 0;
          }
          sqlite3VdbeAddOp3(v17, 145, *(_DWORD *)(i + 88), v10, v21);
        }
        goto LABEL_116;
      }
      if ( (BYTE8(v80) & 0x40) != 0 )
        LOWORD(v4) = 1;
      v22 = (8 * ((unsigned __int16)v4 ^ 1)) | 0x14;
      if ( *(char *)(v7 + 48) < 0 )
      {
        v65 = 0;
        v25 = sqlite3PrimaryKeyIndex(v7);
        v70 = v25;
        v23 = *(unsigned __int16 *)(v25 + 94);
        v26 = *((_DWORD *)v5 + 15);
        v60 = v23;
        v63 = v26 + 1;
        v27 = *((_DWORD *)v5 + 14);
        *((_DWORD *)v5 + 15) = (__int16)v23 + v26;
        v61 = v27;
        *((_DWORD *)v5 + 14) = v27 + 1;
        v69 = sqlite3VdbeAddOp3(v17, 117, v27, (__int16)v23, v28);
        sqlite3VdbeSetP4KeyInfo(v5, v25);
      }
      else
      {
        ++*((_DWORD *)v5 + 15);
        LOWORD(v23) = 1;
        v24 = *((_DWORD *)v5 + 15);
        v63 = 0;
        v25 = 0;
        v61 = 0;
        v69 = 0;
        v70 = 0;
        v60 = 1;
        v65 = v24;
        sqlite3VdbeAddOp3(v17, 75, 0, v24, 0);
      }
      v29 = sqlite3WhereBegin((_DWORD)v5, a2, a3, 0, 0, 0, v22, v12 + 1);
      v72 = v29;
      v30 = v29;
      if ( !v29 )
        goto LABEL_121;
      v31 = *(_QWORD *)(v29 + 40);
      v32 = *(_BYTE *)(v29 + 66);
      v77 = v31;
      v73 = v31;
      v86 = v32;
      if ( v32 != 1 )
      {
        v33 = v5;
        if ( v5[22] )
          v33 = (__int64 *)v5[22];
        *((_BYTE *)v33 + 32) = 1;
      }
      if ( (*(_BYTE *)(v30 + 68) & 1) != 0 )
        sqlite3VdbeAddOp3(v17, 143, v12, 0, 0);
      if ( v62 )
        sqlite3VdbeAddOp3(v17, 86, v62, 1, 0);
      v23 = (__int16)v23;
      v67 = (__int16)v23;
      if ( v25 )
      {
        v34 = 0;
        if ( v67 > 0 )
        {
          do
          {
            sqlite3ExprCodeGetColumnOfTable(v17, v7, v59, *(__int16 *)(*(_QWORD *)(v70 + 8) + 2 * v34), v63 + v34);
            v34 = (unsigned int)(v34 + 1);
          }
          while ( (int)v34 < v67 );
          LODWORD(v31) = v77;
          v5 = a1;
        }
        v35 = v63;
        v23 = v67;
      }
      else
      {
        v35 = ++*((_DWORD *)v5 + 15);
        sqlite3ExprCodeGetColumnOfTable(v17, v7, v59, -1, v35);
      }
      if ( v86 )
      {
        v64 = (void *)sqlite3DbMallocRawNN(v71, v68 + 2);
        if ( !v64 )
        {
          sqlite3WhereEnd(v72);
          goto LABEL_121;
        }
        memset_0(v64, 1, v68 + 1LL);
        v37 = v64;
        v38 = v59;
        *((_BYTE *)v64 + v68 + 1) = 0;
        if ( (int)v31 >= 0 )
          v37[(int)v31 - v38] = 0;
        if ( v73 >= 0 )
          v37[HIDWORD(v73) - v38] = 0;
        if ( v69 )
          sqlite3VdbeChangeToNoop(v17, v69);
        v83 = --*((_DWORD *)v5 + 18);
      }
      else
      {
        v39 = v70;
        v83 = 0;
        if ( v70 )
        {
          ++*((_DWORD *)v5 + 15);
          v40 = *v5;
          v35 = *((_DWORD *)v5 + 15);
          v60 = 0;
          v41 = sqlite3IndexAffinityStr(v40, v39);
          sqlite3VdbeAddOp4(v17, 97, v63, v23, v35, v41, v23);
          sqlite3VdbeAddOp4Int(v17, 138, v61, v35, v63, v23);
        }
        else
        {
          LOWORD(v60) = 1;
          sqlite3VdbeAddOp3(v17, 156, v65, v35, 0);
        }
        sqlite3WhereEnd(v72);
      }
      v42 = v86;
      if ( v88 == 2 )
      {
        v44 = v59;
      }
      else
      {
        v43 = 0;
        if ( v86 == 2 )
          v43 = sqlite3VdbeAddOp3(v17, 15, 0, 0, 0);
        v44 = v59;
        LOBYTE(v36) = 8;
        sqlite3OpenTableAndIndices((_DWORD)v5, v7, 113, v36, v59, (__int64)v64, (__int64)&v58, (__int64)&v66);
        if ( v86 == 2 )
        {
          sqlite3VdbeJumpHereOrPopInst(v17, v43);
          goto LABEL_90;
        }
      }
      if ( !v86 )
      {
        if ( v70 )
        {
          v46 = sqlite3VdbeAddOp3(v17, 36, v61, 0, 0);
          if ( *(_BYTE *)(v7 + 63) == 1 )
          {
            v47 = 0;
            v48 = v35;
          }
          else
          {
            v47 = v35;
            v48 = 0;
          }
          v49 = 94;
          if ( *(_BYTE *)(v7 + 63) != 1 )
            v49 = 134;
          sqlite3VdbeAddOp3(v17, v49, v61, v47, v48);
        }
        else
        {
          v46 = sqlite3VdbeAddOp3(v17, 46, v65, 0, v35);
        }
        goto LABEL_101;
      }
LABEL_90:
      v45 = v58;
      v46 = 0;
      if ( *(_BYTE *)(v7 + 63) == 1 )
        goto LABEL_103;
      if ( !*((_BYTE *)v64 + v58 - v44) )
      {
LABEL_102:
        if ( *(_BYTE *)(v7 + 63) != 1 )
        {
          sqlite3GenerateRowDelete(
            (_DWORD)v5,
            v7,
            v74,
            v45,
            v66,
            v35,
            v60,
            *((_BYTE *)v5 + 30) == 0,
            11,
            v86,
            HIDWORD(v73));
LABEL_110:
          if ( v42 )
          {
            sqlite3VdbeResolveLabel(v17, v83);
            sqlite3WhereEnd(v72);
          }
          else
          {
            if ( v70 )
            {
              v54 = v61;
              v55 = v46 + 1;
              v56 = 39;
            }
            else
            {
              v54 = 0;
              v55 = v46;
              v56 = 9;
            }
            sqlite3VdbeAddOp3(v17, v56, v54, v55, 0);
            *(_DWORD *)(sqlite3VdbeGetOp(v17, v46) + 8) = *(_DWORD *)(v17 + 144);
          }
LABEL_116:
          if ( !*((_BYTE *)v5 + 30) && !v5[23] )
            sqlite3AutoincrementEnd(v5);
          if ( v62 )
            sqlite3CodeChangeCount(v17, v62, "rows deleted");
          goto LABEL_121;
        }
LABEL_103:
        VTable = sqlite3GetVTable(v71, v7);
        sqlite3VtabMakeWritable(v5);
        v51 = v5;
        if ( v5[22] )
          v51 = (__int64 *)v5[22];
        *((_BYTE *)v51 + 33) = 1;
        if ( v86 == 1 )
        {
          sqlite3VdbeAddOp3(v17, 122, v44, 0, 0);
          if ( !v5[22] )
            *((_BYTE *)v5 + 32) = 0;
        }
        sqlite3VdbeAddOp4(v17, 7, 0, 1, v35, VTable, -11);
        sqlite3VdbeChangeP5(v17, 2, v52, v53);
        v42 = v86;
        goto LABEL_110;
      }
      sqlite3VdbeAddOp4Int(v17, 28, v58, v83, v35, (__int16)v60);
LABEL_101:
      v45 = v58;
      goto LABEL_102;
    }
  }
LABEL_121:
  v3 = v71;
  v4 = v64;
  if ( v75 )
    v75[47] = v76;
LABEL_124:
  sqlite3SrcListDelete(v3, a2);
  result = a3;
  if ( a3 )
    result = sqlite3ExprDeleteNN(v3);
  if ( v4 )
    return sqlite3DbNNFreeNN(v3);
  return result;
}

```

## disassembly

```asm
0x180019e50  mov     rax, rsp
0x180019e53  mov     [rax+20h], r9
0x180019e57  mov     [rax+18h], r8
0x180019e5b  mov     [rax+10h], rdx
0x180019e5f  mov     [rax+8], rcx
0x180019e63  push    rbp
0x180019e64  push    rbx
0x180019e65  push    rsi
0x180019e66  push    rdi
0x180019e67  push    r12
0x180019e69  push    r13
0x180019e6b  push    r14
0x180019e6d  push    r15
0x180019e6f  lea     rbp, [rax-58h]
0x180019e73  sub     rsp, 118h
0x180019e7a  mov     r15, [rcx]
0x180019e7d  xorps   xmm0, xmm0
0x180019e80  xor     eax, eax
0x180019e82  mov     [rsp+150h+var_F0], 0
0x180019e8a  xor     ebx, ebx
0x180019e8c  mov     [rbp+50h+var_CC], 0
0x180019e93  mov     rsi, rcx
0x180019e96  mov     [rbp+50h+var_48], rax
0x180019e9a  movups  [rbp+50h+var_78], xmm0
0x180019e9e  mov     [rsp+150h+var_D8], rbx
0x180019ea3  movups  [rbp+50h+var_68], xmm0
0x180019ea7  mov     [rbp+50h+var_B0], r15
0x180019eab  movups  [rbp+50h+var_58], xmm0
0x180019eaf  cmp     [rcx+34h], eax
0x180019eb2  jnz     loc_18001A7C5
0x180019eb8  mov     rdx, [rbp+50h+arg_8]
0x180019ebc  call    sqlite3SrcListLookup
0x180019ec1  mov     r14, rax
0x180019ec4  test    rax, rax
0x180019ec7  jz      loc_18001A7C5
0x180019ecd  cmp     [rax+58h], rbx
0x180019ed1  jnz     short loc_180019EE9
0x180019ed3  mov     rax, [rsi]
0x180019ed6  mov     rcx, [rax+20h]
0x180019eda  mov     rax, [rcx+38h]
0x180019ede  test    rax, rax
0x180019ee1  jz      short loc_180019EF1
0x180019ee3  cmp     [rax+40h], rbx
0x180019ee7  jz      short loc_180019EF1
0x180019ee9  cmp     [rsi+0E5h], bl
0x180019eef  jz      short loc_180019EF5
0x180019ef1  xor     edi, edi
0x180019ef3  jmp     short loc_180019F11
0x180019ef5  xor     r9d, r9d
0x180019ef8  mov     [rsp+150h+var_130], rbx
0x180019efd  mov     r8d, 81h
0x180019f03  mov     rdx, r14
0x180019f06  mov     rcx, rsi
0x180019f09  call    triggersReallyExist
0x180019f0e  mov     rdi, rax
0x180019f11  mov     al, [r14+3Fh]
0x180019f15  mov     r13d, 1
0x180019f1b  mov     [rbp+50h+arg_20], al
0x180019f21  mov     [rbp+50h+var_98], rdi
0x180019f25  test    rdi, rdi
0x180019f28  jnz     short loc_180019F3F
0x180019f2a  xor     r9d, r9d
0x180019f2d  xor     r8d, r8d
0x180019f30  mov     rdx, r14
0x180019f33  mov     rcx, rsi
0x180019f36  call    sqlite3FkRequired
0x180019f3b  test    eax, eax
0x180019f3d  jz      short loc_180019F42
0x180019f3f  mov     ebx, r13d
0x180019f42  mov     rdx, r14
0x180019f45  mov     rcx, rsi
0x180019f48  call    sqlite3ViewGetColumnNames
0x180019f4d  test    eax, eax
0x180019f4f  jnz     loc_18001A7C0
0x180019f55  mov     r8, rdi
0x180019f58  mov     rdx, r14
0x180019f5b  mov     rcx, rsi
0x180019f5e  call    sqlite3IsReadOnly
0x180019f63  test    eax, eax
0x180019f65  jnz     loc_18001A7C0
0x180019f6b  mov     rdx, [r14+60h]
0x180019f6f  mov     rcx, r15
0x180019f72  call    sqlite3SchemaToIndex
0x180019f77  mov     r8, [r14]
0x180019f7a  xor     r9d, r9d
0x180019f7d  movsxd  rdi, eax
0x180019f80  mov     rax, [r15+20h]
0x180019f84  mov     rcx, rdi
0x180019f87  shl     rcx, 5
0x180019f8b  lea     edx, [r9+9]
0x180019f8f  mov     rcx, [rcx+rax]
0x180019f93  mov     [rsp+150h+var_130], rcx
0x180019f98  mov     rcx, rsi
0x180019f9b  call    sqlite3AuthCheck
0x180019fa0  mov     r12d, eax
0x180019fa3  cmp     eax, r13d
0x180019fa6  jz      loc_18001A7C0
0x180019fac  mov     r13d, [rsi+38h]
0x180019fb0  xor     eax, eax
0x180019fb2  mov     [rbp+50h+var_90], rax
0x180019fb6  xor     edx, edx
0x180019fb8  mov     rax, [rbp+50h+arg_8]
0x180019fbc  mov     r8d, 1
0x180019fc2  mov     [rbp+50h+var_88], 0
0x180019fca  mov     [rsp+150h+var_EC], r13d
0x180019fcf  mov     [rbp+50h+var_C4], edx
0x180019fd2  mov     [rax+28h], r13d
0x180019fd6  add     [rsi+38h], r8d
0x180019fda  mov     rax, [r14+10h]
0x180019fde  mov     ecx, [rsi+38h]
0x180019fe1  test    rax, rax
0x180019fe4  jz      short loc_180019FFA
0x180019fe6  inc     ecx
0x180019fe8  add     edx, r8d
0x180019feb  mov     [rsi+38h], ecx
0x180019fee  mov     rax, [rax+28h]
0x180019ff2  test    rax, rax
0x180019ff5  jnz     short loc_180019FE6
0x180019ff7  mov     [rbp+50h+var_C4], edx
0x180019ffa  cmp     [rbp+50h+arg_20], 2
0x18001a001  jnz     short loc_18001A01C
0x18001a003  mov     rax, [rsi+178h]
0x18001a00a  mov     [rbp+50h+var_88], rax
0x18001a00e  mov     rax, [r14]
0x18001a011  mov     [rsi+178h], rax
0x18001a018  mov     [rbp+50h+var_90], rsi
0x18001a01c  mov     rcx, rsi
0x18001a01f  call    sqlite3GetVdbe
0x18001a024  mov     r15, rax
0x18001a027  test    rax, rax
0x18001a02a  jz      loc_18001A7A1
0x18001a030  cmp     byte ptr [rsi+1Eh], 0
0x18001a034  jnz     short loc_18001A03D
0x18001a036  or      dword ptr [rax+0C8h], 10h
0x18001a03d  mov     r8d, edi
0x18001a040  mov     edx, ebx
0x18001a042  mov     rcx, rsi
0x18001a045  call    sqlite3BeginWriteOperation
0x18001a04a  cmp     [rbp+50h+arg_20], 2
0x18001a051  jnz     short loc_18001A07C
0x18001a053  mov     r8, [rbp+50h+arg_10]
0x18001a057  xor     r9d, r9d
0x18001a05a  mov     dword ptr [rsp+150h+var_128], r13d
0x18001a05f  mov     rdx, r14
0x18001a062  mov     rcx, rsi
0x18001a065  mov     [rsp+150h+var_130], 0
0x18001a06e  call    sqlite3MaterializeView
0x18001a073  mov     [rbp+50h+var_CC], r13d
0x18001a077  mov     [rsp+150h+var_F0], r13d
0x18001a07c  mov     rdx, [rbp+50h+arg_10]
0x18001a080  lea     rcx, [rbp+50h+var_78]
0x18001a084  xorps   xmm0, xmm0
0x18001a087  xor     eax, eax
0x18001a089  movups  [rbp+50h+var_78], xmm0
0x18001a08d  mov     [rbp+50h+var_48], rax
0x18001a091  mov     rax, [rbp+50h+arg_8]
0x18001a095  mov     qword ptr [rbp+50h+var_78+8], rax
0x18001a099  movups  [rbp+50h+var_68], xmm0
0x18001a09d  mov     qword ptr [rbp+50h+var_78], rsi
0x18001a0a1  movups  [rbp+50h+var_58], xmm0
0x18001a0a5  call    sqlite3ResolveExprNames
0x18001a0aa  xor     edx, edx
0x18001a0ac  test    eax, eax
0x18001a0ae  jnz     loc_18001A7A1
0x18001a0b4  mov     rax, [rbp+50h+var_B0]
0x18001a0b8  mov     rcx, 100000000h
0x18001a0c2  mov     dword ptr [rsp+150h+var_E0], edx
0x18001a0c6  test    [rax+30h], rcx
0x18001a0ca  jz      short loc_18001A104
0x18001a0cc  cmp     [rsi+1Eh], dl
0x18001a0cf  jnz     short loc_18001A104
0x18001a0d1  cmp     [rsi+0B8h], rdx
0x18001a0d8  jnz     short loc_18001A104
0x18001a0da  cmp     [rsi+0E3h], dl
0x18001a0e0  jnz     short loc_18001A104
0x18001a0e2  inc     dword ptr [rsi+3Ch]
0x18001a0e5  xor     r8d, r8d
0x18001a0e8  mov     eax, [rsi+3Ch]
0x18001a0eb  mov     rcx, r15
0x18001a0ee  mov     dword ptr [rsp+150h+var_130], edx
0x18001a0f2  mov     r9d, eax
0x18001a0f5  mov     dword ptr [rsp+150h+var_E0], eax
0x18001a0f9  lea     edx, [r8+47h]
0x18001a0fd  call    sqlite3VdbeAddOp3
0x18001a102  xor     edx, edx
0x18001a104  mov     ecx, 1
0x18001a109  test    r12d, r12d
0x18001a10c  jnz     loc_18001A1D0
0x18001a112  cmp     [rbp+50h+arg_10], rdx
0x18001a116  jnz     loc_18001A1D0
0x18001a11c  test    ebx, ebx
0x18001a11e  jnz     loc_18001A1D0
0x18001a124  cmp     [r14+3Fh], cl
0x18001a128  jz      loc_18001A1D0
0x18001a12e  mov     rax, [r14]
0x18001a131  mov     r9b, cl
0x18001a134  mov     r8d, [r14+28h]
0x18001a138  mov     rcx, rsi
0x18001a13b  mov     edx, edi
0x18001a13d  mov     [rsp+150h+var_130], rax
0x18001a142  call    sqlite3TableLock
0x18001a147  mov     r12d, dword ptr [rsp+150h+var_E0]
0x18001a14c  or      r13d, 0FFFFFFFFh
0x18001a150  test    byte ptr [r14+30h], 80h
0x18001a155  jnz     short loc_18001A186
0x18001a157  mov     rax, [r14]
0x18001a15a  test    r12d, r12d
0x18001a15d  mov     r8d, [r14+28h]
0x18001a161  mov     ecx, r13d
0x18001a164  cmovnz  ecx, r12d
0x18001a168  mov     dword ptr [rsp+150h+var_120], r13d
0x18001a16d  mov     [rsp+150h+var_128], rax
0x18001a172  mov     r9d, edi
0x18001a175  mov     dword ptr [rsp+150h+var_130], ecx
0x18001a179  mov     edx, 91h
0x18001a17e  mov     rcx, r15
0x18001a181  call    sqlite3VdbeAddOp4
0x18001a186  mov     rbx, [r14+10h]
0x18001a18a  jmp     short loc_18001A1C6
0x18001a18c  mov     eax, [rbx+64h]
0x18001a18f  and     al, 3
0x18001a191  cmp     al, 2
0x18001a193  jnz     short loc_18001A1A8
0x18001a195  test    byte ptr [r14+30h], 80h
0x18001a19a  jz      short loc_18001A1A8
0x18001a19c  test    r12d, r12d
0x18001a19f  mov     eax, r13d
0x18001a1a2  cmovnz  eax, r12d
0x18001a1a6  jmp     short loc_18001A1AA
0x18001a1a8  xor     eax, eax
0x18001a1aa  mov     r8d, [rbx+58h]
0x18001a1ae  mov     r9d, edi
0x18001a1b1  mov     edx, 91h
0x18001a1b6  mov     dword ptr [rsp+150h+var_130], eax
0x18001a1ba  mov     rcx, r15
0x18001a1bd  call    sqlite3VdbeAddOp3
0x18001a1c2  mov     rbx, [rbx+28h]
0x18001a1c6  test    rbx, rbx
0x18001a1c9  jnz     short loc_18001A18C
0x18001a1cb  jmp     loc_18001A770
0x18001a1d0  test    byte ptr [rbp+50h+var_58+8], 40h
0x18001a1d4  cmovnz  ebx, ecx
0x18001a1d7  xor     bx, cx
0x18001a1da  shl     bx, 3
0x18001a1de  or      bx, 14h
0x18001a1e2  test    byte ptr [r14+30h], 80h
0x18001a1e7  jnz     short loc_18001A223
0x18001a1e9  add     [rsi+3Ch], ecx
0x18001a1ec  movzx   edi, cx
0x18001a1ef  mov     eax, [rsi+3Ch]
0x18001a1f2  xor     r8d, r8d
0x18001a1f5  mov     dword ptr [rsp+150h+var_E0+4], edx
0x18001a1f9  mov     r12, rdx
0x18001a1fc  mov     [rsp+150h+var_E4], edx
0x18001a200  mov     r9d, eax
0x18001a203  mov     [rbp+50h+var_C0], edx
0x18001a206  mov     rcx, r15
0x18001a209  mov     [rbp+50h+var_B8], rdx
0x18001a20d  mov     dword ptr [rsp+150h+var_130], edx
0x18001a211  lea     edx, [r8+4Bh]
0x18001a215  mov     [rsp+150h+var_E8], edi
0x18001a219  mov     [rbp+50h+var_D0], eax
0x18001a21c  call    sqlite3VdbeAddOp3
0x18001a221  jmp     short loc_18001A280
0x18001a223  mov     rcx, r14
0x18001a226  mov     [rbp+50h+var_D0], edx
0x18001a229  call    sqlite3PrimaryKeyIndex
0x18001a22e  mov     r12, rax
0x18001a231  mov     [rbp+50h+var_B8], rax
0x18001a235  mov     dword ptr [rsp+150h+var_130], edx
0x18001a239  mov     edx, 75h ; 'u'
0x18001a23e  movzx   edi, word ptr [rax+5Eh]
0x18001a242  mov     eax, [rsi+3Ch]
0x18001a245  movsx   r9d, di
0x18001a249  mov     [rsp+150h+var_E8], edi
0x18001a24d  lea     ecx, [rax+1]
0x18001a250  add     eax, r9d
0x18001a253  mov     dword ptr [rsp+150h+var_E0+4], ecx
0x18001a257  mov     ecx, [rsi+38h]
0x18001a25a  mov     r8d, ecx
0x18001a25d  mov     [rsi+3Ch], eax
0x18001a260  mov     [rsp+150h+var_E4], ecx
0x18001a264  lea     eax, [rcx+1]
0x18001a267  mov     rcx, r15
0x18001a26a  mov     [rsi+38h], eax
0x18001a26d  call    sqlite3VdbeAddOp3
0x18001a272  mov     rdx, r12
0x18001a275  mov     [rbp+50h+var_C0], eax
0x18001a278  mov     rcx, rsi
0x18001a27b  call    sqlite3VdbeSetP4KeyInfo
0x18001a280  mov     r8, [rbp+50h+arg_10]
0x18001a284  lea     eax, [r13+1]
0x18001a288  mov     rdx, [rbp+50h+arg_8]
0x18001a28c  xor     r9d, r9d
0x18001a28f  mov     dword ptr [rsp+150h+var_118], eax
0x18001a293  mov     rcx, rsi
0x18001a296  mov     word ptr [rsp+150h+var_120], bx
0x18001a29b  mov     [rsp+150h+var_128], 0
0x18001a2a4  mov     [rsp+150h+var_130], 0
0x18001a2ad  call    sqlite3WhereBegin
  ... truncated ...
```

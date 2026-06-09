# sqlite3DeleteFrom

- ea: `0x180071d34`
- end: `0x180072781`
- name: `sqlite3DeleteFrom`
- size: `2637`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x18003e7e0`
- `0x180079dfc`
- `0x1800c3bd8`

## callees

- `0x180002cf8`
- `0x180037d8c`
- `0x18003f2e8`
- `0x1800693b0`
- `0x180069d64`
- `0x18006e018`
- `0x1800717b0`
- `0x1800718f8`
- `0x180071d34`
- `0x180074ab0`
- `0x180076d6c`
- `0x18007a280`
- `0x18007c30c`
- `0x18007d478`
- `0x18007f7fc`
- `0x180080f0c`
- `0x180081b90`
- `0x18008a258`
- `0x18008e124`
- `0x18008e588`
- `0x18008f3d8`
- `0x1800923d8`
- `0x1800924d4`
- `0x1800927e0`
- `0x180092870`
- `0x18009a3b4`
- `0x18009a3f0`
- `0x18009c8f4`
- `0x18009cc20`
- `0x18009e1e4`
- `0x18009f1c8`
- `0x1800a2050`
- `0x1800b1a74`
- `0x1800b6a40`

## string_xrefs

- `0x1800726fe`: `rows deleted`

## pseudocode

```c
__int64 __fastcall sqlite3DeleteFrom(__int64 *a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // r15
  void *v6; // rbx
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rdx
  int v16; // r12d
  int v17; // edx
  __int64 v18; // rax
  int v19; // ecx
  __int64 Vdbe; // rax
  __int64 v21; // r15
  int v22; // r9d
  __int64 v23; // r13
  int v24; // r9d
  int v25; // r13d
  int v26; // eax
  __int64 v27; // rbx
  unsigned int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  __int16 v31; // bx
  int v32; // eax
  __int64 v33; // r13
  __int16 v34; // r12
  int v35; // eax
  int v36; // r8d
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rbx
  char v40; // al
  _QWORD *v41; // rcx
  unsigned int v42; // edi
  __int64 v43; // rdi
  int v44; // r12d
  int v45; // r9d
  _BYTE *v46; // rdx
  int v47; // edi
  __int64 v48; // rbx
  unsigned int v49; // eax
  unsigned int v50; // ebx
  char v51; // r10
  int v52; // edx
  unsigned int v53; // edi
  __int16 v54; // bx
  int v55; // ebx
  int v56; // r9d
  int v57; // eax
  int v58; // edx
  _QWORD *i; // rbx
  _QWORD *v60; // rcx
  unsigned int v61; // eax
  __int64 v62; // rax
  int v63; // r8d
  unsigned int v64; // r9d
  int v65; // edx
  __int64 result; // rax
  char v67; // [rsp+68h] [rbp-A0h]
  char v68; // [rsp+69h] [rbp-9Fh]
  int v69; // [rsp+6Ch] [rbp-9Ch]
  __int16 v70; // [rsp+70h] [rbp-98h]
  int v71; // [rsp+74h] [rbp-94h] BYREF
  int v72; // [rsp+78h] [rbp-90h]
  int v73; // [rsp+7Ch] [rbp-8Ch]
  int v74; // [rsp+80h] [rbp-88h]
  void *v75; // [rsp+88h] [rbp-80h]
  int v76; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v77; // [rsp+94h] [rbp-74h]
  int v78; // [rsp+98h] [rbp-70h]
  int v79; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v80; // [rsp+A0h] [rbp-68h]
  __int64 v81; // [rsp+A8h] [rbp-60h]
  __int64 v82; // [rsp+B0h] [rbp-58h]
  __int64 v83; // [rsp+B8h] [rbp-50h]
  __int64 v84; // [rsp+C0h] [rbp-48h]
  _QWORD *v85; // [rsp+C8h] [rbp-40h]
  __int64 v86; // [rsp+D0h] [rbp-38h]
  __int64 v87; // [rsp+D8h] [rbp-30h]
  __int128 v88; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v89; // [rsp+F0h] [rbp-18h]
  __int128 v90; // [rsp+100h] [rbp-8h]
  __int64 v91; // [rsp+110h] [rbp+8h]
  unsigned int v93; // [rsp+158h] [rbp+50h]

  v5 = *a1;
  v71 = 0;
  v76 = 0;
  v6 = 0;
  v8 = a1;
  v75 = 0;
  v88 = 0;
  v91 = 0;
  v89 = 0;
  v81 = v5;
  v90 = 0;
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_143;
  v9 = sqlite3SrcListLookup(a1, a2);
  v10 = v9;
  if ( !v9 )
    goto LABEL_143;
  if ( (*(_QWORD *)(v9 + 88) || (v11 = *(_QWORD *)(*(_QWORD *)(*v8 + 32LL) + 56LL)) != 0 && *(_QWORD *)(v11 + 64))
    && !*((_BYTE *)v8 + 229) )
  {
    v12 = triggersReallyExist((_DWORD)v8, v10, 128, 0, 0);
  }
  else
  {
    v12 = 0;
  }
  v68 = *(_BYTE *)(v10 + 63);
  v84 = v12;
  if ( v12 || (unsigned int)sqlite3FkRequired(v8, v10, 0, 0) )
    LODWORD(v6) = 1;
  if ( (*(_BYTE *)(v10 + 63) == 1 || *(__int16 *)(v10 + 54) <= 0) && (unsigned int)viewGetColumnNames(v8, v10)
    || (unsigned int)sqlite3IsReadOnly(v8, v10, v12) )
  {
    v6 = 0;
    goto LABEL_143;
  }
  v13 = *(_QWORD *)(v10 + 96);
  v14 = -32768;
  if ( v13 )
  {
    v15 = *(_QWORD *)(v5 + 32);
    v14 = 0;
    if ( *(_QWORD *)(v15 + 24) != v13 )
    {
      do
        ++v14;
      while ( *(_QWORD *)(32LL * v14 + v15 + 24) != v13 );
      v8 = a1;
    }
  }
  v16 = sqlite3AuthCheck((_DWORD)v8, 9, *(_QWORD *)v10, 0, *(_QWORD *)(32LL * v14 + *(_QWORD *)(v5 + 32)));
  if ( v16 == 1 )
  {
    v6 = v75;
    goto LABEL_143;
  }
  v85 = 0;
  v17 = 0;
  v69 = *((_DWORD *)v8 + 13);
  *(_DWORD *)(a2 + 76) = v69;
  ++*((_DWORD *)v8 + 13);
  v18 = *(_QWORD *)(v10 + 16);
  v19 = *((_DWORD *)v8 + 13);
  v86 = 0;
  v79 = 0;
  if ( v18 )
  {
    do
    {
      ++v19;
      ++v17;
      *((_DWORD *)v8 + 13) = v19;
      v18 = *(_QWORD *)(v18 + 40);
    }
    while ( v18 );
    v79 = v17;
  }
  if ( v68 == 2 )
  {
    v86 = v8[47];
    v8[47] = *(_QWORD *)v10;
    v85 = v8;
  }
  Vdbe = sqlite3GetVdbe(v8);
  v21 = Vdbe;
  if ( Vdbe )
  {
    if ( !*((_BYTE *)v8 + 30) )
      *(_DWORD *)(Vdbe + 200) |= 0x10u;
    sqlite3BeginWriteOperation(v8, (unsigned int)v6, (unsigned int)v14);
    if ( v68 == 2 )
    {
      v22 = a4;
      v23 = a3;
      sqlite3MaterializeView((_DWORD)v8, v10, a3, v22, a5, v69);
      v76 = v69;
      v71 = v69;
    }
    else
    {
      v23 = a3;
    }
    v91 = 0;
    *((_QWORD *)&v88 + 1) = a2;
    v89 = 0;
    *(_QWORD *)&v88 = v8;
    v90 = 0;
    if ( !(unsigned int)sqlite3ResolveExprNames(&v88, v23) )
    {
      v25 = 0;
      v77 = 0;
      if ( (*(_QWORD *)(v81 + 48) & 0x100000000LL) != 0 && !*((_BYTE *)v8 + 30) && !v8[23] && !*((_BYTE *)v8 + 227) )
      {
        v25 = ++*((_DWORD *)v8 + 14);
        v77 = v25;
        sqlite3VdbeAddOp3(v21, 71, 0, v25, 0);
      }
      if ( !v16 && !a3 && !(_DWORD)v6 && *(_BYTE *)(v10 + 63) != 1 )
      {
        LOBYTE(v24) = 1;
        sqlite3TableLock((_DWORD)v8, v14, *(_DWORD *)(v10 + 40), v24, *(_QWORD *)v10);
        if ( *(char *)(v10 + 48) >= 0 )
        {
          v26 = -1;
          v27 = *(_QWORD *)v10;
          if ( v25 )
            v26 = v25;
          v28 = sqlite3VdbeAddOp3(v21, 145, *(_DWORD *)(v10 + 40), v14, v26);
          sqlite3VdbeChangeP4(v21, v28, v27, 0xFFFFFFFFLL);
        }
        v29 = *(_QWORD *)(v10 + 16);
        if ( v29 )
        {
          do
          {
            if ( (*(_DWORD *)(v29 + 100) & 3) == 2 && *(char *)(v10 + 48) < 0 )
            {
              v30 = -1;
              if ( v25 )
                v30 = v25;
            }
            else
            {
              v30 = 0;
            }
            sqlite3VdbeAddOp3(v21, 145, *(_DWORD *)(v29 + 88), v14, v30);
            v29 = *(_QWORD *)(v29 + 40);
          }
          while ( v29 );
          v8 = a1;
        }
        goto LABEL_133;
      }
      if ( (BYTE8(v90) & 0x40) != 0 )
        LOWORD(v6) = 1;
      v31 = (8 * ((unsigned __int16)v6 ^ 1)) | 0x14;
      if ( *(char *)(v10 + 48) < 0 )
      {
        v33 = *(_QWORD *)(v10 + 16);
        v73 = 0;
        while ( v33 && (*(_DWORD *)(v33 + 100) & 3) != 2 )
          v33 = *(_QWORD *)(v33 + 40);
        v34 = *(_WORD *)(v33 + 94);
        v35 = *((_DWORD *)v8 + 14);
        v70 = v34;
        v72 = v35 + 1;
        v36 = *((_DWORD *)v8 + 13);
        *((_DWORD *)v8 + 14) = v34 + v35;
        v74 = v36;
        *((_DWORD *)v8 + 13) = v36 + 1;
        v80 = sqlite3VdbeAddOp3(v21, 118, v36, v34, 0);
        sqlite3VdbeSetP4KeyInfo(v8, v33);
      }
      else
      {
        v32 = ++*((_DWORD *)v8 + 14);
        v74 = 0;
        v33 = 0;
        v80 = 0;
        v72 = 0;
        v34 = 1;
        v73 = v32;
        v70 = 1;
        sqlite3VdbeAddOp3(v21, 75, 0, v32, 0);
      }
      v37 = sqlite3WhereBegin((_DWORD)v8, a2, a3, 0, 0, 0, v31, v69 + 1);
      v82 = v37;
      v38 = v37;
      if ( !v37 )
        goto LABEL_139;
      v39 = *(_QWORD *)(v37 + 40);
      v40 = *(_BYTE *)(v37 + 66);
      v87 = v39;
      v83 = v39;
      v67 = v40;
      if ( v40 != 1 )
      {
        v41 = v8;
        if ( v8[22] )
          v41 = (_QWORD *)v8[22];
        *((_BYTE *)v41 + 32) = 1;
      }
      if ( (*(_BYTE *)(v38 + 68) & 1) != 0 )
        sqlite3VdbeAddOp3(v21, 143, v69, 0, 0);
      if ( v77 )
        sqlite3VdbeAddOp3(v21, 86, v77, 1, 0);
      v42 = v34;
      v78 = v34;
      if ( v33 )
      {
        v43 = 0;
        if ( v78 > 0 )
        {
          do
          {
            sqlite3ExprCodeGetColumnOfTable(v21, v10, v69, *(__int16 *)(*(_QWORD *)(v33 + 8) + 2 * v43), v72 + v43);
            v43 = (unsigned int)(v43 + 1);
          }
          while ( (int)v43 < v78 );
          LODWORD(v39) = v87;
          v8 = a1;
        }
        v44 = v72;
        v42 = v78;
      }
      else
      {
        v44 = ++*((_DWORD *)v8 + 14);
        sqlite3VdbeAddOp3(v21, 135, v69, v44, 0);
      }
      if ( v67 )
      {
        v75 = (void *)sqlite3DbMallocRawNN(v81, v79 + 2);
        if ( !v75 )
        {
          sqlite3WhereEnd(v82);
          goto LABEL_139;
        }
        memset_0(v75, 1, v79 + 1LL);
        v46 = v75;
        *((_BYTE *)v75 + v79 + 1) = 0;
        if ( (int)v39 >= 0 )
          v46[(int)v39 - v69] = 0;
        if ( v83 >= 0 )
          v46[HIDWORD(v83) - v69] = 0;
        if ( v80 )
          sqlite3VdbeChangeToNoop(v21, v80);
        --*((_DWORD *)v8 + 17);
        v47 = v73;
        v93 = *((_DWORD *)v8 + 17);
      }
      else
      {
        v93 = 0;
        if ( v33 )
        {
          ++*((_DWORD *)v8 + 14);
          v48 = *(_QWORD *)(v33 + 32);
          v44 = *((_DWORD *)v8 + 14);
          v70 = 0;
          if ( !v48 )
            v48 = computeIndexAffStr(*v8, v33);
          v49 = sqlite3VdbeAddOp3(v21, 97, v72, v42, v44);
          sqlite3VdbeChangeP4(v21, v49, v48, v42);
          sqlite3VdbeAddOp4Int(v21, 138, v74, v44, v72, v42);
          v47 = v73;
        }
        else
        {
          v47 = v73;
          v70 = 1;
          sqlite3VdbeAddOp3(v21, 156, v73, v44, 0);
        }
        sqlite3WhereEnd(v82);
      }
      if ( v68 == 2 )
      {
        v51 = v67;
      }
      else
      {
        v50 = 0;
        if ( v67 == 2 )
          v50 = sqlite3VdbeAddOp3(v21, 15, 0, 0, 0);
        LOBYTE(v45) = 8;
        sqlite3OpenTableAndIndices((_DWORD)v8, v10, 113, v45, v69, (__int64)v75, (__int64)&v71, (__int64)&v76);
        v51 = v67;
        if ( v67 == 2 )
        {
          sqlite3VdbeJumpHereOrPopInst(v21, v50);
          goto LABEL_102;
        }
      }
      if ( !v51 )
      {
        if ( v33 )
        {
          v55 = v74;
          v53 = sqlite3VdbeAddOp3(v21, 36, v74, 0, 0);
          if ( *(_BYTE *)(v10 + 63) == 1 )
          {
            v56 = 0;
            v57 = v44;
          }
          else
          {
            v56 = v44;
            v57 = 0;
          }
          v58 = 94;
          if ( *(_BYTE *)(v10 + 63) != 1 )
            v58 = 134;
          sqlite3VdbeAddOp3(v21, v58, v55, v56, v57);
        }
        else
        {
          v53 = sqlite3VdbeAddOp3(v21, 46, v47, 0, v44);
        }
        v54 = v70;
        goto LABEL_114;
      }
LABEL_102:
      v52 = v71;
      v53 = 0;
      v54 = v70;
      if ( *(_BYTE *)(v10 + 63) == 1 )
        goto LABEL_116;
      if ( !*((_BYTE *)v75 + v71 - v69) )
      {
LABEL_115:
        if ( *(_BYTE *)(v10 + 63) != 1 )
        {
          sqlite3GenerateRowDelete(
            (_DWORD)v8,
            v10,
            v84,
            v52,
            v76,
            v44,
            v54,
            *((_BYTE *)v8 + 30) == 0,
            11,
            v51,
            HIDWORD(v83));
LABEL_127:
          if ( v67 )
          {
            sqlite3VdbeResolveLabel(v21, v93);
            sqlite3WhereEnd(v82);
          }
          else
          {
            if ( v33 )
            {
              v63 = v74;
              v64 = v53 + 1;
              v65 = 39;
            }
            else
            {
              v63 = 0;
              v64 = v53;
              v65 = 9;
            }
            sqlite3VdbeAddOp3(v21, v65, v63, v64, 0);
            sqlite3VdbeJumpHere(v21, v53);
          }
LABEL_133:
          if ( !*((_BYTE *)v8 + 30) && !v8[23] && v8[21] )
            autoIncrementEnd(v8);
          if ( v77 )
            sqlite3CodeChangeCount(v21, v77, "rows deleted");
          goto LABEL_139;
        }
LABEL_116:
        for ( i = *(_QWORD **)(v10 + 80); i; i = (_QWORD *)i[5] )
        {
          if ( *i == v81 )
            break;
        }
        sqlite3VtabMakeWritable(v8, v10);
        v60 = v8;
        if ( v8[22] )
          v60 = (_QWORD *)v8[22];
        *((_BYTE *)v60 + 33) = 1;
        if ( v67 == 1 )
        {
          sqlite3VdbeAddOp3(v21, 122, v69, 0, 0);
          if ( !v8[22] )
            *((_BYTE *)v8 + 32) = 0;
        }
        v61 = sqlite3VdbeAddOp3(v21, 7, 0, 1, v44);
        sqlite3VdbeChangeP4(v21, v61, i, 4294967285LL);
        v62 = *(int *)(v21 + 144);
        if ( (int)v62 > 0 )
          *(_WORD *)(*(_QWORD *)(v21 + 136) + 24 * v62 - 22) = 2;
        goto LABEL_127;
      }
      sqlite3VdbeAddOp4Int(v21, 28, v71, v93, v44, v70);
LABEL_114:
      v52 = v71;
      v51 = v67;
      goto LABEL_115;
    }
  }
LABEL_139:
  v5 = v81;
  v6 = v75;
  if ( v85 )
    v85[47] = v86;
LABEL_143:
  sqlite3SrcListDelete(v5, a2);
  result = a3;
  if ( a3 )
    result = sqlite3ExprDeleteNN(v5, a3);
  if ( v6 )
    return sqlite3DbNNFreeNN(v5, v6);
  return result;
}

```

## disassembly

```asm
0x180071d34  mov     rax, rsp
0x180071d37  mov     [rax+20h], rbx
0x180071d3b  mov     [rax+18h], r8
0x180071d3f  mov     [rax+10h], rdx
0x180071d43  mov     [rax+8], rcx
0x180071d47  push    rbp
0x180071d48  push    rsi
0x180071d49  push    rdi
0x180071d4a  push    r12
0x180071d4c  push    r13
0x180071d4e  push    r14
0x180071d50  push    r15
0x180071d52  lea     rbp, [rax-48h]
0x180071d56  sub     rsp, 110h
0x180071d5d  mov     r15, [rcx]
0x180071d60  xor     r12d, r12d
0x180071d63  xorps   xmm0, xmm0
0x180071d66  mov     [rsp+140h+var_D4], r12d
0x180071d6b  xor     eax, eax
0x180071d6d  mov     [rbp+40h+var_B8], r12d
0x180071d71  mov     ebx, r12d
0x180071d74  mov     r13, r9
0x180071d77  mov     rsi, rcx
0x180071d7a  mov     [rbp+40h+var_C0], rbx
0x180071d7e  movups  [rbp+40h+var_68], xmm0
0x180071d82  mov     [rbp+40h+var_38], rax
0x180071d86  movups  [rbp+40h+var_58], xmm0
0x180071d8a  mov     [rbp+40h+var_A0], r15
0x180071d8e  movups  [rbp+40h+var_48], xmm0
0x180071d92  cmp     [rcx+30h], r12d
0x180071d96  jnz     loc_180072736
0x180071d9c  mov     rdx, [rbp+40h+arg_8]
0x180071da0  call    sqlite3SrcListLookup
0x180071da5  mov     r14, rax
0x180071da8  test    rax, rax
0x180071dab  jz      loc_180072736
0x180071db1  cmp     [rax+58h], r12
0x180071db5  jnz     short loc_180071DCD
0x180071db7  mov     rax, [rsi]
0x180071dba  mov     rcx, [rax+20h]
0x180071dbe  mov     rax, [rcx+38h]
0x180071dc2  test    rax, rax
0x180071dc5  jz      short loc_180071DD6
0x180071dc7  cmp     [rax+40h], r12
0x180071dcb  jz      short loc_180071DD6
0x180071dcd  cmp     [rsi+0E5h], r12b
0x180071dd4  jz      short loc_180071DDB
0x180071dd6  mov     rdi, r12
0x180071dd9  jmp     short loc_180071DF7
0x180071ddb  xor     r9d, r9d
0x180071dde  mov     [rsp+140h+var_120], r12
0x180071de3  mov     r8d, 80h
0x180071de9  mov     rdx, r14
0x180071dec  mov     rcx, rsi
0x180071def  call    triggersReallyExist
0x180071df4  mov     rdi, rax
0x180071df7  mov     al, [r14+3Fh]
0x180071dfb  mov     byte ptr [rsp+140h+var_E0+1], al
0x180071dff  mov     [rbp+40h+var_88], rdi
0x180071e03  test    rdi, rdi
0x180071e06  jnz     short loc_180071E1D
0x180071e08  xor     r9d, r9d
0x180071e0b  xor     r8d, r8d
0x180071e0e  mov     rdx, r14
0x180071e11  mov     rcx, rsi
0x180071e14  call    sqlite3FkRequired
0x180071e19  test    eax, eax
0x180071e1b  jz      short loc_180071E22
0x180071e1d  mov     ebx, 1
0x180071e22  cmp     byte ptr [r14+3Fh], 1
0x180071e27  jz      short loc_180071E30
0x180071e29  cmp     [r14+36h], r12w
0x180071e2e  jg      short loc_180071E43
0x180071e30  mov     rdx, r14
0x180071e33  mov     rcx, rsi
0x180071e36  call    viewGetColumnNames
0x180071e3b  test    eax, eax
0x180071e3d  jnz     loc_180072733
0x180071e43  mov     r8, rdi
0x180071e46  mov     rdx, r14
0x180071e49  mov     rcx, rsi
0x180071e4c  call    sqlite3IsReadOnly
0x180071e51  test    eax, eax
0x180071e53  jnz     loc_180072733
0x180071e59  mov     rcx, [r14+60h]
0x180071e5d  mov     edi, 0FFFF8000h
0x180071e62  test    rcx, rcx
0x180071e65  jz      short loc_180071E88
0x180071e67  mov     rdx, [r15+20h]
0x180071e6b  mov     edi, r12d
0x180071e6e  cmp     [rdx+18h], rcx
0x180071e72  jz      short loc_180071E88
0x180071e74  inc     edi
0x180071e76  movsxd  rax, edi
0x180071e79  shl     rax, 5
0x180071e7d  cmp     [rax+rdx+18h], rcx
0x180071e82  jnz     short loc_180071E74
0x180071e84  mov     rsi, [rbp+40h+arg_0]
0x180071e88  mov     rax, [r15+20h]
0x180071e8c  xor     r9d, r9d
0x180071e8f  mov     r8, [r14]
0x180071e92  movsxd  rcx, edi
0x180071e95  shl     rcx, 5
0x180071e99  lea     edx, [r9+9]
0x180071e9d  mov     rcx, [rcx+rax]
0x180071ea1  mov     [rsp+140h+var_120], rcx
0x180071ea6  mov     rcx, rsi
0x180071ea9  call    sqlite3AuthCheck
0x180071eae  mov     r8d, 1
0x180071eb4  mov     r12d, eax
0x180071eb7  cmp     eax, r8d
0x180071eba  jz      loc_18007272D
0x180071ec0  mov     rcx, [rbp+40h+arg_8]
0x180071ec4  xor     eax, eax
0x180071ec6  mov     [rbp+40h+var_80], rax
0x180071eca  xor     edx, edx
0x180071ecc  mov     eax, [rsi+34h]
0x180071ecf  mov     [rsp+140h+var_DC], eax
0x180071ed3  mov     [rcx+4Ch], eax
0x180071ed6  add     [rsi+34h], r8d
0x180071eda  mov     rax, [r14+10h]
0x180071ede  mov     ecx, [rsi+34h]
0x180071ee1  mov     [rbp+40h+var_78], 0
0x180071ee9  mov     [rbp+40h+var_AC], edx
0x180071eec  test    rax, rax
0x180071eef  jz      short loc_180071F05
0x180071ef1  inc     ecx
0x180071ef3  add     edx, r8d
0x180071ef6  mov     [rsi+34h], ecx
0x180071ef9  mov     rax, [rax+28h]
0x180071efd  test    rax, rax
0x180071f00  jnz     short loc_180071EF1
0x180071f02  mov     [rbp+40h+var_AC], edx
0x180071f05  cmp     byte ptr [rsp+140h+var_E0+1], 2
0x180071f0a  jnz     short loc_180071F25
0x180071f0c  mov     rax, [rsi+178h]
0x180071f13  mov     [rbp+40h+var_78], rax
0x180071f17  mov     rax, [r14]
0x180071f1a  mov     [rsi+178h], rax
0x180071f21  mov     [rbp+40h+var_80], rsi
0x180071f25  mov     rcx, rsi
0x180071f28  call    sqlite3GetVdbe
0x180071f2d  mov     r15, rax
0x180071f30  test    rax, rax
0x180071f33  jz      loc_18007270F
0x180071f39  cmp     byte ptr [rsi+1Eh], 0
0x180071f3d  jnz     short loc_180071F46
0x180071f3f  or      dword ptr [rax+0C8h], 10h
0x180071f46  mov     r8d, edi
0x180071f49  mov     edx, ebx
0x180071f4b  mov     rcx, rsi
0x180071f4e  call    sqlite3BeginWriteOperation
0x180071f53  cmp     byte ptr [rsp+140h+var_E0+1], 2
0x180071f58  jnz     short loc_180071F8D
0x180071f5a  mov     ecx, [rsp+140h+var_DC]
0x180071f5e  mov     r9, r13
0x180071f61  mov     rax, [rbp+40h+arg_20]
0x180071f65  mov     rdx, r14
0x180071f68  mov     r13, [rbp+40h+arg_10]
0x180071f6c  mov     dword ptr [rsp+140h+var_118], ecx
0x180071f70  mov     r8, r13
0x180071f73  mov     rcx, rsi
0x180071f76  mov     [rsp+140h+var_120], rax
0x180071f7b  call    sqlite3MaterializeView
0x180071f80  mov     eax, [rsp+140h+var_DC]
0x180071f84  mov     [rbp+40h+var_B8], eax
0x180071f87  mov     [rsp+140h+var_D4], eax
0x180071f8b  jmp     short loc_180071F91
0x180071f8d  mov     r13, [rbp+40h+arg_10]
0x180071f91  xorps   xmm0, xmm0
0x180071f94  lea     rcx, [rbp+40h+var_68]
0x180071f98  xor     eax, eax
0x180071f9a  mov     rdx, r13
0x180071f9d  movups  [rbp+40h+var_68], xmm0
0x180071fa1  mov     [rbp+40h+var_38], rax
0x180071fa5  mov     rax, [rbp+40h+arg_8]
0x180071fa9  mov     qword ptr [rbp+40h+var_68+8], rax
0x180071fad  movups  [rbp+40h+var_58], xmm0
0x180071fb1  mov     qword ptr [rbp+40h+var_68], rsi
0x180071fb5  movups  [rbp+40h+var_48], xmm0
0x180071fb9  call    sqlite3ResolveExprNames
0x180071fbe  test    eax, eax
0x180071fc0  jnz     loc_18007270F
0x180071fc6  mov     rax, [rbp+40h+var_A0]
0x180071fca  xor     r13d, r13d
0x180071fcd  mov     rcx, 100000000h
0x180071fd7  mov     [rbp+40h+var_B4], r13d
0x180071fdb  test    [rax+30h], rcx
0x180071fdf  jz      short loc_18007201E
0x180071fe1  cmp     [rsi+1Eh], r13b
0x180071fe5  jnz     short loc_18007201E
0x180071fe7  cmp     [rsi+0B8h], r13
0x180071fee  jnz     short loc_18007201E
0x180071ff0  cmp     [rsi+0E3h], r13b
0x180071ff7  jnz     short loc_18007201E
0x180071ff9  inc     dword ptr [rsi+38h]
0x180071ffc  xor     r8d, r8d
0x180071fff  mov     r13d, [rsi+38h]
0x180072003  mov     rcx, r15
0x180072006  mov     r9d, r13d
0x180072009  mov     [rbp+40h+var_B4], r13d
0x18007200d  mov     dword ptr [rsp+140h+var_120], 0
0x180072015  lea     edx, [r8+47h]
0x180072019  call    sqlite3VdbeAddOp3
0x18007201e  test    r12d, r12d
0x180072021  jnz     loc_1800720F5
0x180072027  xor     r12d, r12d
0x18007202a  cmp     [rbp+40h+arg_10], r12
0x18007202e  jnz     loc_1800720F8
0x180072034  test    ebx, ebx
0x180072036  jnz     loc_1800720F8
0x18007203c  lea     ecx, [rbx+1]
0x18007203f  cmp     [r14+3Fh], cl
0x180072043  jz      loc_1800720F8
0x180072049  mov     rax, [r14]
0x18007204c  mov     r9b, cl
0x18007204f  mov     r8d, [r14+28h]
0x180072053  mov     rcx, rsi
0x180072056  mov     edx, edi
0x180072058  mov     [rsp+140h+var_120], rax
0x18007205d  call    sqlite3TableLock
0x180072062  test    byte ptr [r14+30h], 80h
0x180072067  jnz     short loc_18007209F
0x180072069  mov     r8d, [r14+28h]
0x18007206d  or      eax, 0FFFFFFFFh
0x180072070  mov     rbx, [r14]
0x180072073  test    r13d, r13d
0x180072076  mov     r9d, edi
0x180072079  mov     edx, 91h
0x18007207e  cmovnz  eax, r13d
0x180072082  mov     rcx, r15
0x180072085  mov     dword ptr [rsp+140h+var_120], eax
0x180072089  call    sqlite3VdbeAddOp3
0x18007208e  or      r9d, 0FFFFFFFFh
0x180072092  mov     r8, rbx
0x180072095  mov     edx, eax
0x180072097  mov     rcx, r15
0x18007209a  call    sqlite3VdbeChangeP4
0x18007209f  mov     rbx, [r14+10h]
0x1800720a3  test    rbx, rbx
0x1800720a6  jz      loc_1800726D7
0x1800720ac  mov     eax, [rbx+64h]
0x1800720af  and     al, 3
0x1800720b1  cmp     al, 2
0x1800720b3  jnz     short loc_1800720C8
0x1800720b5  test    byte ptr [r14+30h], 80h
0x1800720ba  jz      short loc_1800720C8
0x1800720bc  or      eax, 0FFFFFFFFh
0x1800720bf  test    r13d, r13d
0x1800720c2  cmovnz  eax, r13d
0x1800720c6  jmp     short loc_1800720CB
0x1800720c8  mov     eax, r12d
0x1800720cb  mov     r8d, [rbx+58h]
0x1800720cf  mov     r9d, edi
0x1800720d2  mov     edx, 91h
0x1800720d7  mov     dword ptr [rsp+140h+var_120], eax
0x1800720db  mov     rcx, r15
0x1800720de  call    sqlite3VdbeAddOp3
0x1800720e3  mov     rbx, [rbx+28h]
0x1800720e7  test    rbx, rbx
0x1800720ea  jnz     short loc_1800720AC
0x1800720ec  mov     rsi, [rbp+40h+arg_0]
0x1800720f0  jmp     loc_1800726D7
0x1800720f5  xor     r12d, r12d
0x1800720f8  test    byte ptr [rbp+40h+var_48+8], 40h
0x1800720fc  mov     edi, 1
0x180072101  cmovnz  ebx, edi
0x180072104  xor     bx, di
0x180072107  shl     bx, 3
0x18007210b  or      bx, 14h
0x18007210f  test    byte ptr [r14+30h], 80h
0x180072114  jnz     short loc_180072151
0x180072116  add     [rsi+38h], edi
0x180072119  lea     edx, [rdi+4Ah]
0x18007211c  mov     eax, [rsi+38h]
0x18007211f  xor     ecx, ecx
0x180072121  mov     [rsp+140h+var_C8], ecx
0x180072125  mov     r13d, ecx
0x180072128  mov     [rbp+40h+var_A8], ecx
0x18007212b  mov     r9d, eax
0x18007212e  mov     dword ptr [rsp+140h+var_120], ecx
0x180072132  xor     r8d, r8d
0x180072135  mov     [rsp+140h+var_D0], r12d
0x18007213a  mov     rcx, r15
0x18007213d  movzx   r12d, di
0x180072141  mov     [rsp+140h+var_CC], eax
0x180072145  mov     [rsp+140h+var_D8], r12d
0x18007214a  call    sqlite3VdbeAddOp3
0x18007214f  jmp     short loc_1800721C0
0x180072151  mov     r13, [r14+10h]
0x180072155  mov     [rsp+140h+var_CC], r12d
0x18007215a  jmp     short loc_18007216A
0x18007215c  mov     eax, [r13+64h]
0x180072160  and     al, 3
0x180072162  cmp     al, 2
0x180072164  jz      short loc_18007216F
0x180072166  mov     r13, [r13+28h]
0x18007216a  test    r13, r13
0x18007216d  jnz     short loc_18007215C
0x18007216f  movzx   r12d, word ptr [r13+5Eh]
  ... truncated ...
```

# sqlite3DeleteFrom

- ea: `0x140054474`
- end: `0x140054eb5`
- name: `sqlite3DeleteFrom`
- size: `2625`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x140024174`
- `0x14005bfe8`
- `0x1400a40bc`

## callees

- `0x1400026c0`
- `0x14001d720`
- `0x140024bec`
- `0x14004bdbc`
- `0x14004c754`
- `0x1400509b8`
- `0x140053ef0`
- `0x140054038`
- `0x140054474`
- `0x140056d98`
- `0x14005904c`
- `0x14005c46c`
- `0x14005e4b4`
- `0x14005f5fc`
- `0x14006189c`
- `0x140062f5c`
- `0x140063830`
- `0x14006b920`
- `0x14006f6b0`
- `0x14006fb14`
- `0x140070918`
- `0x1400738a0`
- `0x14007399c`
- `0x140073ca8`
- `0x140073d38`
- `0x14007b574`
- `0x14007b5b0`
- `0x14007da70`
- `0x14007dd9c`
- `0x14007f328`
- `0x1400802f0`
- `0x1400830e4`
- `0x140092694`
- `0x140097310`

## string_xrefs

- `0x140054e37`: `rows deleted`

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
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rdx
  int v13; // r12d
  int v14; // r13d
  int v15; // edx
  __int64 v16; // rax
  int v17; // ecx
  __int64 Vdbe; // rax
  __int64 v19; // r15
  int v20; // r9d
  int v21; // r13d
  int v22; // eax
  __int64 v23; // rbx
  unsigned int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  __int16 v27; // bx
  unsigned int v28; // eax
  __int64 v29; // r13
  __int16 v30; // r12
  int v31; // eax
  int v32; // r8d
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rbx
  char v36; // al
  __int64 *v37; // rcx
  unsigned int v38; // edi
  __int64 v39; // rdi
  int v40; // r12d
  int v41; // r9d
  _BYTE *v42; // rdx
  int v43; // edi
  __int64 v44; // rbx
  unsigned int v45; // eax
  unsigned int v46; // ebx
  char v47; // r10
  int v48; // edx
  unsigned int v49; // edi
  __int16 v50; // bx
  int v51; // ebx
  int v52; // r9d
  int v53; // eax
  int v54; // edx
  _QWORD *i; // rbx
  __int64 *v56; // rcx
  unsigned int v57; // eax
  __int64 v58; // rax
  int v59; // r8d
  unsigned int v60; // r9d
  int v61; // edx
  __int64 result; // rax
  __int16 v63; // [rsp+68h] [rbp-A0h]
  int v64; // [rsp+6Ch] [rbp-9Ch]
  int v65; // [rsp+70h] [rbp-98h] BYREF
  int v66; // [rsp+74h] [rbp-94h]
  __int64 v67; // [rsp+78h] [rbp-90h]
  void *v68; // [rsp+80h] [rbp-88h]
  int v69; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v70; // [rsp+8Ch] [rbp-7Ch]
  int v71; // [rsp+90h] [rbp-78h]
  int v72; // [rsp+94h] [rbp-74h]
  unsigned int v73; // [rsp+98h] [rbp-70h]
  __int64 v74; // [rsp+A0h] [rbp-68h]
  __int64 v75; // [rsp+A8h] [rbp-60h]
  __int64 v76; // [rsp+B0h] [rbp-58h]
  __int64 v77; // [rsp+B8h] [rbp-50h]
  __int64 *v78; // [rsp+C0h] [rbp-48h]
  __int64 v79; // [rsp+C8h] [rbp-40h]
  __int64 v80; // [rsp+D0h] [rbp-38h]
  __int128 v81; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v82; // [rsp+E8h] [rbp-20h]
  __int128 v83; // [rsp+F8h] [rbp-10h]
  __int64 v84; // [rsp+108h] [rbp+0h]
  unsigned int v86; // [rsp+168h] [rbp+60h]
  char v89; // [rsp+180h] [rbp+78h]
  char v91; // [rsp+188h] [rbp+80h]

  v3 = *a1;
  v65 = 0;
  v69 = 0;
  v4 = 0;
  v5 = a1;
  v68 = 0;
  v81 = 0;
  v84 = 0;
  v82 = 0;
  v74 = v3;
  v83 = 0;
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_141;
  v6 = sqlite3SrcListLookup(a1, a2);
  v7 = v6;
  if ( !v6 )
    goto LABEL_141;
  if ( (*(_QWORD *)(v6 + 88) || (v8 = *(_QWORD *)(*(_QWORD *)(*v5 + 32) + 56LL)) != 0 && *(_QWORD *)(v8 + 64))
    && !*((_BYTE *)v5 + 221) )
  {
    v9 = triggersReallyExist((_DWORD)v5, v7, 128, 0, 0);
  }
  else
  {
    v9 = 0;
  }
  v91 = *(_BYTE *)(v7 + 63);
  v77 = v9;
  if ( v9 || (unsigned int)sqlite3FkRequired(v5, v7, 0, 0) )
    LODWORD(v4) = 1;
  if ( (*(_BYTE *)(v7 + 63) == 1 || *(__int16 *)(v7 + 54) <= 0) && (unsigned int)viewGetColumnNames(v5, v7)
    || (unsigned int)sqlite3IsReadOnly(v5, v7, v9) )
  {
    v4 = 0;
    goto LABEL_141;
  }
  v10 = *(_QWORD *)(v7 + 96);
  v11 = -32768;
  if ( v10 )
  {
    v12 = *(_QWORD *)(v3 + 32);
    v11 = 0;
    if ( *(_QWORD *)(v12 + 24) != v10 )
    {
      do
        ++v11;
      while ( *(_QWORD *)(32LL * v11 + v12 + 24) != v10 );
    }
  }
  v13 = sqlite3AuthCheck((_DWORD)v5, 9, *(_QWORD *)v7, 0, *(_QWORD *)(32LL * v11 + *(_QWORD *)(v3 + 32)));
  if ( v13 == 1 )
  {
    v4 = v68;
    goto LABEL_141;
  }
  v14 = *((_DWORD *)v5 + 13);
  v78 = 0;
  v15 = 0;
  v79 = 0;
  v64 = v14;
  v72 = 0;
  *(_DWORD *)(a2 + 76) = v14;
  ++*((_DWORD *)v5 + 13);
  v16 = *(_QWORD *)(v7 + 16);
  v17 = *((_DWORD *)v5 + 13);
  if ( v16 )
  {
    do
    {
      ++v17;
      ++v15;
      *((_DWORD *)v5 + 13) = v17;
      v16 = *(_QWORD *)(v16 + 40);
    }
    while ( v16 );
    v72 = v15;
  }
  if ( v91 == 2 )
  {
    v79 = v5[46];
    v5[46] = *(_QWORD *)v7;
    v78 = v5;
  }
  Vdbe = sqlite3GetVdbe(v5);
  v19 = Vdbe;
  if ( Vdbe )
  {
    if ( !*((_BYTE *)v5 + 30) )
      *(_DWORD *)(Vdbe + 200) |= 0x10u;
    sqlite3BeginWriteOperation(v5, (unsigned int)v4, (unsigned int)v11);
    if ( v91 == 2 )
    {
      sqlite3MaterializeView((_DWORD)v5, v7, a3, 0, 0, v14);
      v69 = v14;
      v65 = v14;
    }
    v84 = 0;
    *((_QWORD *)&v81 + 1) = a2;
    v82 = 0;
    *(_QWORD *)&v81 = v5;
    v83 = 0;
    if ( !(unsigned int)sqlite3ResolveExprNames(&v81, a3) )
    {
      v21 = 0;
      v70 = 0;
      if ( (*(_QWORD *)(v74 + 48) & 0x100000000LL) != 0 && !*((_BYTE *)v5 + 30) && !v5[22] && !*((_BYTE *)v5 + 219) )
      {
        v21 = ++*((_DWORD *)v5 + 14);
        v70 = v21;
        sqlite3VdbeAddOp3(v19, 71, 0, v21, 0);
      }
      if ( !v13 && !a3 && !(_DWORD)v4 && *(_BYTE *)(v7 + 63) != 1 )
      {
        LOBYTE(v20) = 1;
        sqlite3TableLock((_DWORD)v5, v11, *(_DWORD *)(v7 + 40), v20, *(_QWORD *)v7);
        if ( *(char *)(v7 + 48) >= 0 )
        {
          v22 = -1;
          v23 = *(_QWORD *)v7;
          if ( v21 )
            v22 = v21;
          v24 = sqlite3VdbeAddOp3(v19, 145, *(_DWORD *)(v7 + 40), v11, v22);
          sqlite3VdbeChangeP4(v19, v24, v23, 0xFFFFFFFFLL);
        }
        v25 = *(_QWORD *)(v7 + 16);
        if ( v25 )
        {
          do
          {
            if ( (*(_DWORD *)(v25 + 100) & 3) == 2 && *(char *)(v7 + 48) < 0 )
            {
              v26 = -1;
              if ( v21 )
                v26 = v21;
            }
            else
            {
              v26 = 0;
            }
            sqlite3VdbeAddOp3(v19, 145, *(_DWORD *)(v25 + 88), v11, v26);
            v25 = *(_QWORD *)(v25 + 40);
          }
          while ( v25 );
          v5 = a1;
        }
        goto LABEL_131;
      }
      if ( (BYTE8(v83) & 0x40) != 0 )
        LOWORD(v4) = 1;
      v27 = (8 * ((unsigned __int16)v4 ^ 1)) | 0x14;
      if ( *(char *)(v7 + 48) < 0 )
      {
        v29 = *(_QWORD *)(v7 + 16);
        LODWORD(v67) = 0;
        while ( v29 && (*(_DWORD *)(v29 + 100) & 3) != 2 )
          v29 = *(_QWORD *)(v29 + 40);
        v30 = *(_WORD *)(v29 + 94);
        v31 = *((_DWORD *)v5 + 14);
        v63 = v30;
        v66 = v31 + 1;
        v32 = *((_DWORD *)v5 + 13);
        *((_DWORD *)v5 + 14) = v30 + v31;
        HIDWORD(v67) = v32;
        *((_DWORD *)v5 + 13) = v32 + 1;
        v73 = sqlite3VdbeAddOp3(v19, 118, v32, v30, 0);
        sqlite3VdbeSetP4KeyInfo(v5, v29);
      }
      else
      {
        v28 = ++*((_DWORD *)v5 + 14);
        v29 = 0;
        v73 = 0;
        v66 = 0;
        v30 = 1;
        v67 = v28;
        v63 = 1;
        sqlite3VdbeAddOp3(v19, 75, 0, v28, 0);
      }
      v33 = sqlite3WhereBegin((_DWORD)v5, a2, a3, 0, 0, 0, v27, v64 + 1);
      v75 = v33;
      v34 = v33;
      if ( !v33 )
        goto LABEL_137;
      v35 = *(_QWORD *)(v33 + 40);
      v36 = *(_BYTE *)(v33 + 66);
      v80 = v35;
      v76 = v35;
      v89 = v36;
      if ( v36 != 1 )
      {
        v37 = v5;
        if ( v5[21] )
          v37 = (__int64 *)v5[21];
        *((_BYTE *)v37 + 32) = 1;
      }
      if ( (*(_BYTE *)(v34 + 68) & 1) != 0 )
        sqlite3VdbeAddOp3(v19, 143, v64, 0, 0);
      if ( v70 )
        sqlite3VdbeAddOp3(v19, 86, v70, 1, 0);
      v38 = v30;
      v71 = v30;
      if ( v29 )
      {
        v39 = 0;
        if ( v71 > 0 )
        {
          do
          {
            sqlite3ExprCodeGetColumnOfTable(v19, v7, v64, *(__int16 *)(*(_QWORD *)(v29 + 8) + 2 * v39), v66 + v39);
            v39 = (unsigned int)(v39 + 1);
          }
          while ( (int)v39 < v71 );
          LODWORD(v35) = v80;
          v5 = a1;
        }
        v40 = v66;
        v38 = v71;
      }
      else
      {
        v40 = ++*((_DWORD *)v5 + 14);
        sqlite3VdbeAddOp3(v19, 135, v64, v40, 0);
      }
      if ( v89 )
      {
        v68 = (void *)sqlite3DbMallocRawNN(v74, v72 + 2);
        if ( !v68 )
        {
          sqlite3WhereEnd(v75);
          goto LABEL_137;
        }
        memset_0(v68, 1, v72 + 1LL);
        v42 = v68;
        *((_BYTE *)v68 + v72 + 1) = 0;
        if ( (int)v35 >= 0 )
          v42[(int)v35 - v64] = 0;
        if ( v76 >= 0 )
          v42[HIDWORD(v76) - v64] = 0;
        if ( v73 )
          sqlite3VdbeChangeToNoop(v19, v73);
        --*((_DWORD *)v5 + 17);
        v43 = v67;
        v86 = *((_DWORD *)v5 + 17);
      }
      else
      {
        v86 = 0;
        if ( v29 )
        {
          ++*((_DWORD *)v5 + 14);
          v44 = *(_QWORD *)(v29 + 32);
          v40 = *((_DWORD *)v5 + 14);
          v63 = 0;
          if ( !v44 )
            v44 = computeIndexAffStr(*v5, v29);
          v45 = sqlite3VdbeAddOp3(v19, 97, v66, v38, v40);
          sqlite3VdbeChangeP4(v19, v45, v44, v38);
          sqlite3VdbeAddOp4Int(v19, 138, HIDWORD(v67), v40, v66, v38);
          v43 = v67;
        }
        else
        {
          v43 = v67;
          v63 = 1;
          sqlite3VdbeAddOp3(v19, 156, v67, v40, 0);
        }
        sqlite3WhereEnd(v75);
      }
      if ( v91 == 2 )
      {
        v47 = v89;
      }
      else
      {
        v46 = 0;
        if ( v89 == 2 )
          v46 = sqlite3VdbeAddOp3(v19, 15, 0, 0, 0);
        LOBYTE(v41) = 8;
        sqlite3OpenTableAndIndices((_DWORD)v5, v7, 113, v41, v64, (__int64)v68, (__int64)&v65, (__int64)&v69);
        v47 = v89;
        if ( v89 == 2 )
        {
          sqlite3VdbeJumpHereOrPopInst(v19, v46);
          goto LABEL_100;
        }
      }
      if ( !v47 )
      {
        if ( v29 )
        {
          v51 = HIDWORD(v67);
          v49 = sqlite3VdbeAddOp3(v19, 36, HIDWORD(v67), 0, 0);
          if ( *(_BYTE *)(v7 + 63) == 1 )
          {
            v52 = 0;
            v53 = v40;
          }
          else
          {
            v52 = v40;
            v53 = 0;
          }
          v54 = 94;
          if ( *(_BYTE *)(v7 + 63) != 1 )
            v54 = 134;
          sqlite3VdbeAddOp3(v19, v54, v51, v52, v53);
        }
        else
        {
          v49 = sqlite3VdbeAddOp3(v19, 46, v43, 0, v40);
        }
        v50 = v63;
        goto LABEL_112;
      }
LABEL_100:
      v48 = v65;
      v49 = 0;
      v50 = v63;
      if ( *(_BYTE *)(v7 + 63) == 1 )
        goto LABEL_114;
      if ( !*((_BYTE *)v68 + v65 - v64) )
      {
LABEL_113:
        if ( *(_BYTE *)(v7 + 63) != 1 )
        {
          sqlite3GenerateRowDelete(
            (_DWORD)v5,
            v7,
            v77,
            v48,
            v69,
            v40,
            v50,
            *((_BYTE *)v5 + 30) == 0,
            11,
            v47,
            HIDWORD(v76));
LABEL_125:
          if ( v89 )
          {
            sqlite3VdbeResolveLabel(v19, v86);
            sqlite3WhereEnd(v75);
          }
          else
          {
            if ( v29 )
            {
              v59 = HIDWORD(v67);
              v60 = v49 + 1;
              v61 = 39;
            }
            else
            {
              v59 = 0;
              v60 = v49;
              v61 = 9;
            }
            sqlite3VdbeAddOp3(v19, v61, v59, v60, 0);
            sqlite3VdbeJumpHere(v19, v49);
          }
LABEL_131:
          if ( !*((_BYTE *)v5 + 30) && !v5[22] && v5[20] )
            autoIncrementEnd(v5);
          if ( v70 )
            sqlite3CodeChangeCount(v19, v70, "rows deleted");
          goto LABEL_137;
        }
LABEL_114:
        for ( i = *(_QWORD **)(v7 + 80); i; i = (_QWORD *)i[5] )
        {
          if ( *i == v74 )
            break;
        }
        sqlite3VtabMakeWritable(v5, v7);
        v56 = v5;
        if ( v5[21] )
          v56 = (__int64 *)v5[21];
        *((_BYTE *)v56 + 33) = 1;
        if ( v89 == 1 )
        {
          sqlite3VdbeAddOp3(v19, 122, v64, 0, 0);
          if ( !v5[21] )
            *((_BYTE *)v5 + 32) = 0;
        }
        v57 = sqlite3VdbeAddOp3(v19, 7, 0, 1, v40);
        sqlite3VdbeChangeP4(v19, v57, i, 4294967285LL);
        v58 = *(int *)(v19 + 144);
        if ( (int)v58 > 0 )
          *(_WORD *)(*(_QWORD *)(v19 + 136) + 24 * v58 - 22) = 2;
        goto LABEL_125;
      }
      sqlite3VdbeAddOp4Int(v19, 28, v65, v86, v40, v63);
LABEL_112:
      v48 = v65;
      v47 = v89;
      goto LABEL_113;
    }
  }
LABEL_137:
  v3 = v74;
  v4 = v68;
  if ( v78 )
    v78[46] = v79;
LABEL_141:
  sqlite3SrcListDelete(v3, a2);
  result = a3;
  if ( a3 )
    result = sqlite3ExprDeleteNN(v3);
  if ( v4 )
    return sqlite3DbNNFreeNN(v3, v4);
  return result;
}

```

## disassembly

```asm
0x140054474  mov     rax, rsp
0x140054477  mov     [rax+20h], r9
0x14005447b  mov     [rax+18h], r8
0x14005447f  mov     [rax+10h], rdx
0x140054483  mov     [rax+8], rcx
0x140054487  push    rbp
0x140054488  push    rbx
0x140054489  push    rsi
0x14005448a  push    rdi
0x14005448b  push    r12
0x14005448d  push    r13
0x14005448f  push    r14
0x140054491  push    r15
0x140054493  lea     rbp, [rax-58h]
0x140054497  sub     rsp, 118h
0x14005449e  mov     r15, [rcx]
0x1400544a1  xor     r12d, r12d
0x1400544a4  xorps   xmm0, xmm0
0x1400544a7  mov     [rsp+150h+var_E8], r12d
0x1400544ac  xor     eax, eax
0x1400544ae  mov     [rbp+50h+var_D0], r12d
0x1400544b2  mov     ebx, r12d
0x1400544b5  mov     rsi, rcx
0x1400544b8  mov     [rsp+150h+var_D8], rbx
0x1400544bd  movups  [rbp+50h+var_80], xmm0
0x1400544c1  mov     [rbp+50h+var_50], rax
0x1400544c5  movups  [rbp+50h+var_70], xmm0
0x1400544c9  mov     [rbp+50h+var_B8], r15
0x1400544cd  movups  [rbp+50h+var_60], xmm0
0x1400544d1  cmp     [rcx+30h], r12d
0x1400544d5  jnz     loc_140054E71
0x1400544db  mov     rdx, [rbp+50h+arg_8]
0x1400544df  call    sqlite3SrcListLookup
0x1400544e4  mov     r14, rax
0x1400544e7  test    rax, rax
0x1400544ea  jz      loc_140054E71
0x1400544f0  cmp     [rax+58h], r12
0x1400544f4  jnz     short loc_14005450C
0x1400544f6  mov     rax, [rsi]
0x1400544f9  mov     rcx, [rax+20h]
0x1400544fd  mov     rax, [rcx+38h]
0x140054501  test    rax, rax
0x140054504  jz      short loc_140054515
0x140054506  cmp     [rax+40h], r12
0x14005450a  jz      short loc_140054515
0x14005450c  cmp     [rsi+0DDh], r12b
0x140054513  jz      short loc_14005451A
0x140054515  mov     rdi, r12
0x140054518  jmp     short loc_140054536
0x14005451a  xor     r9d, r9d
0x14005451d  mov     [rsp+150h+var_130], r12
0x140054522  mov     r8d, 80h
0x140054528  mov     rdx, r14
0x14005452b  mov     rcx, rsi
0x14005452e  call    triggersReallyExist
0x140054533  mov     rdi, rax
0x140054536  mov     al, [r14+3Fh]
0x14005453a  mov     r13d, 1
0x140054540  mov     [rbp+50h+arg_20], al
0x140054546  mov     [rbp+50h+var_A0], rdi
0x14005454a  test    rdi, rdi
0x14005454d  jnz     short loc_140054564
0x14005454f  xor     r9d, r9d
0x140054552  xor     r8d, r8d
0x140054555  mov     rdx, r14
0x140054558  mov     rcx, rsi
0x14005455b  call    sqlite3FkRequired
0x140054560  test    eax, eax
0x140054562  jz      short loc_140054567
0x140054564  mov     ebx, r13d
0x140054567  cmp     [r14+3Fh], r13b
0x14005456b  jz      short loc_140054574
0x14005456d  cmp     [r14+36h], r12w
0x140054572  jg      short loc_140054587
0x140054574  mov     rdx, r14
0x140054577  mov     rcx, rsi
0x14005457a  call    viewGetColumnNames
0x14005457f  test    eax, eax
0x140054581  jnz     loc_140054E6E
0x140054587  mov     r8, rdi
0x14005458a  mov     rdx, r14
0x14005458d  mov     rcx, rsi
0x140054590  call    sqlite3IsReadOnly
0x140054595  test    eax, eax
0x140054597  jnz     loc_140054E6E
0x14005459d  mov     rcx, [r14+60h]
0x1400545a1  mov     edi, 0FFFF8000h
0x1400545a6  test    rcx, rcx
0x1400545a9  jz      short loc_1400545C9
0x1400545ab  mov     rdx, [r15+20h]
0x1400545af  mov     edi, r12d
0x1400545b2  cmp     [rdx+18h], rcx
0x1400545b6  jz      short loc_1400545C9
0x1400545b8  add     edi, r13d
0x1400545bb  movsxd  rax, edi
0x1400545be  shl     rax, 5
0x1400545c2  cmp     [rax+rdx+18h], rcx
0x1400545c7  jnz     short loc_1400545B8
0x1400545c9  mov     rax, [r15+20h]
0x1400545cd  xor     r9d, r9d
0x1400545d0  mov     r8, [r14]
0x1400545d3  movsxd  rcx, edi
0x1400545d6  shl     rcx, 5
0x1400545da  lea     edx, [r9+9]
0x1400545de  mov     rcx, [rcx+rax]
0x1400545e2  mov     [rsp+150h+var_130], rcx
0x1400545e7  mov     rcx, rsi
0x1400545ea  call    sqlite3AuthCheck
0x1400545ef  mov     r12d, eax
0x1400545f2  cmp     eax, r13d
0x1400545f5  jz      loc_140054E67
0x1400545fb  mov     r13d, [rsi+34h]
0x1400545ff  xor     eax, eax
0x140054601  mov     [rbp+50h+var_98], rax
0x140054605  xor     edx, edx
0x140054607  mov     rax, [rbp+50h+arg_8]
0x14005460b  mov     r8d, 1
0x140054611  mov     [rbp+50h+var_90], 0
0x140054619  mov     [rsp+150h+var_EC], r13d
0x14005461e  mov     [rbp+50h+var_C4], edx
0x140054621  mov     [rax+4Ch], r13d
0x140054625  add     [rsi+34h], r8d
0x140054629  mov     rax, [r14+10h]
0x14005462d  mov     ecx, [rsi+34h]
0x140054630  test    rax, rax
0x140054633  jz      short loc_140054649
0x140054635  inc     ecx
0x140054637  add     edx, r8d
0x14005463a  mov     [rsi+34h], ecx
0x14005463d  mov     rax, [rax+28h]
0x140054641  test    rax, rax
0x140054644  jnz     short loc_140054635
0x140054646  mov     [rbp+50h+var_C4], edx
0x140054649  cmp     [rbp+50h+arg_20], 2
0x140054650  jnz     short loc_14005466B
0x140054652  mov     rax, [rsi+170h]
0x140054659  mov     [rbp+50h+var_90], rax
0x14005465d  mov     rax, [r14]
0x140054660  mov     [rsi+170h], rax
0x140054667  mov     [rbp+50h+var_98], rsi
0x14005466b  mov     rcx, rsi
0x14005466e  call    sqlite3GetVdbe
0x140054673  mov     r15, rax
0x140054676  test    rax, rax
0x140054679  jz      loc_140054E48
0x14005467f  cmp     byte ptr [rsi+1Eh], 0
0x140054683  jnz     short loc_14005468C
0x140054685  or      dword ptr [rax+0C8h], 10h
0x14005468c  mov     r8d, edi
0x14005468f  mov     edx, ebx
0x140054691  mov     rcx, rsi
0x140054694  call    sqlite3BeginWriteOperation
0x140054699  cmp     [rbp+50h+arg_20], 2
0x1400546a0  jnz     short loc_1400546CB
0x1400546a2  mov     r8, [rbp+50h+arg_10]
0x1400546a6  xor     r9d, r9d
0x1400546a9  mov     dword ptr [rsp+150h+var_128], r13d
0x1400546ae  mov     rdx, r14
0x1400546b1  mov     rcx, rsi
0x1400546b4  mov     [rsp+150h+var_130], 0
0x1400546bd  call    sqlite3MaterializeView
0x1400546c2  mov     [rbp+50h+var_D0], r13d
0x1400546c6  mov     [rsp+150h+var_E8], r13d
0x1400546cb  mov     rdx, [rbp+50h+arg_10]
0x1400546cf  lea     rcx, [rbp+50h+var_80]
0x1400546d3  xorps   xmm0, xmm0
0x1400546d6  xor     eax, eax
0x1400546d8  movups  [rbp+50h+var_80], xmm0
0x1400546dc  mov     [rbp+50h+var_50], rax
0x1400546e0  mov     rax, [rbp+50h+arg_8]
0x1400546e4  mov     qword ptr [rbp+50h+var_80+8], rax
0x1400546e8  movups  [rbp+50h+var_70], xmm0
0x1400546ec  mov     qword ptr [rbp+50h+var_80], rsi
0x1400546f0  movups  [rbp+50h+var_60], xmm0
0x1400546f4  call    sqlite3ResolveExprNames
0x1400546f9  test    eax, eax
0x1400546fb  jnz     loc_140054E48
0x140054701  mov     rax, [rbp+50h+var_B8]
0x140054705  xor     r13d, r13d
0x140054708  mov     rcx, 100000000h
0x140054712  mov     [rbp+50h+var_CC], r13d
0x140054716  test    [rax+30h], rcx
0x14005471a  jz      short loc_140054759
0x14005471c  cmp     [rsi+1Eh], r13b
0x140054720  jnz     short loc_140054759
0x140054722  cmp     [rsi+0B0h], r13
0x140054729  jnz     short loc_140054759
0x14005472b  cmp     [rsi+0DBh], r13b
0x140054732  jnz     short loc_140054759
0x140054734  inc     dword ptr [rsi+38h]
0x140054737  xor     r8d, r8d
0x14005473a  mov     r13d, [rsi+38h]
0x14005473e  mov     rcx, r15
0x140054741  mov     r9d, r13d
0x140054744  mov     [rbp+50h+var_CC], r13d
0x140054748  mov     dword ptr [rsp+150h+var_130], 0
0x140054750  lea     edx, [r8+47h]
0x140054754  call    sqlite3VdbeAddOp3
0x140054759  test    r12d, r12d
0x14005475c  jnz     loc_140054830
0x140054762  xor     r12d, r12d
0x140054765  cmp     [rbp+50h+arg_10], r12
0x140054769  jnz     loc_140054833
0x14005476f  test    ebx, ebx
0x140054771  jnz     loc_140054833
0x140054777  lea     ecx, [rbx+1]
0x14005477a  cmp     [r14+3Fh], cl
0x14005477e  jz      loc_140054833
0x140054784  mov     rax, [r14]
0x140054787  mov     r9b, cl
0x14005478a  mov     r8d, [r14+28h]
0x14005478e  mov     rcx, rsi
0x140054791  mov     edx, edi
0x140054793  mov     [rsp+150h+var_130], rax
0x140054798  call    sqlite3TableLock
0x14005479d  test    byte ptr [r14+30h], 80h
0x1400547a2  jnz     short loc_1400547DA
0x1400547a4  mov     r8d, [r14+28h]
0x1400547a8  or      eax, 0FFFFFFFFh
0x1400547ab  mov     rbx, [r14]
0x1400547ae  test    r13d, r13d
0x1400547b1  mov     r9d, edi
0x1400547b4  mov     edx, 91h
0x1400547b9  cmovnz  eax, r13d
0x1400547bd  mov     rcx, r15
0x1400547c0  mov     dword ptr [rsp+150h+var_130], eax
0x1400547c4  call    sqlite3VdbeAddOp3
0x1400547c9  or      r9d, 0FFFFFFFFh
0x1400547cd  mov     r8, rbx
0x1400547d0  mov     edx, eax
0x1400547d2  mov     rcx, r15
0x1400547d5  call    sqlite3VdbeChangeP4
0x1400547da  mov     rbx, [r14+10h]
0x1400547de  test    rbx, rbx
0x1400547e1  jz      loc_140054E10
0x1400547e7  mov     eax, [rbx+64h]
0x1400547ea  and     al, 3
0x1400547ec  cmp     al, 2
0x1400547ee  jnz     short loc_140054803
0x1400547f0  test    byte ptr [r14+30h], 80h
0x1400547f5  jz      short loc_140054803
0x1400547f7  or      eax, 0FFFFFFFFh
0x1400547fa  test    r13d, r13d
0x1400547fd  cmovnz  eax, r13d
0x140054801  jmp     short loc_140054806
0x140054803  mov     eax, r12d
0x140054806  mov     r8d, [rbx+58h]
0x14005480a  mov     r9d, edi
0x14005480d  mov     edx, 91h
0x140054812  mov     dword ptr [rsp+150h+var_130], eax
0x140054816  mov     rcx, r15
0x140054819  call    sqlite3VdbeAddOp3
0x14005481e  mov     rbx, [rbx+28h]
0x140054822  test    rbx, rbx
0x140054825  jnz     short loc_1400547E7
0x140054827  mov     rsi, [rbp+50h+arg_0]
0x14005482b  jmp     loc_140054E10
0x140054830  xor     r12d, r12d
0x140054833  test    byte ptr [rbp+50h+var_60+8], 40h
0x140054837  mov     edi, 1
0x14005483c  cmovnz  ebx, edi
0x14005483f  xor     bx, di
0x140054842  shl     bx, 3
0x140054846  or      bx, 14h
0x14005484a  test    byte ptr [r14+30h], 80h
0x14005484f  jnz     short loc_14005488C
0x140054851  add     [rsi+38h], edi
0x140054854  lea     edx, [rdi+4Ah]
0x140054857  mov     eax, [rsi+38h]
0x14005485a  xor     ecx, ecx
0x14005485c  mov     dword ptr [rsp+150h+var_E0+4], ecx
0x140054860  mov     r13d, ecx
0x140054863  mov     [rbp+50h+var_C0], ecx
0x140054866  mov     r9d, eax
0x140054869  mov     dword ptr [rsp+150h+var_130], ecx
0x14005486d  xor     r8d, r8d
0x140054870  mov     [rsp+150h+var_E4], r12d
0x140054875  mov     rcx, r15
0x140054878  movzx   r12d, di
0x14005487c  mov     dword ptr [rsp+150h+var_E0], eax
0x140054880  mov     [rsp+150h+var_F0], r12d
0x140054885  call    sqlite3VdbeAddOp3
0x14005488a  jmp     short loc_1400548FB
0x14005488c  mov     r13, [r14+10h]
0x140054890  mov     dword ptr [rsp+150h+var_E0], r12d
0x140054895  jmp     short loc_1400548A5
0x140054897  mov     eax, [r13+64h]
0x14005489b  and     al, 3
0x14005489d  cmp     al, 2
0x14005489f  jz      short loc_1400548AA
0x1400548a1  mov     r13, [r13+28h]
0x1400548a5  test    r13, r13
0x1400548a8  jnz     short loc_140054897
0x1400548aa  movzx   r12d, word ptr [r13+5Eh]
0x1400548af  mov     edx, 76h ; 'v'
0x1400548b4  mov     eax, [rsi+38h]
0x1400548b7  movsx   r9d, r12w
0x1400548bb  mov     [rsp+150h+var_F0], r12d
0x1400548c0  mov     dword ptr [rsp+150h+var_130], 0
0x1400548c8  lea     ecx, [rax+1]
  ... truncated ...
```

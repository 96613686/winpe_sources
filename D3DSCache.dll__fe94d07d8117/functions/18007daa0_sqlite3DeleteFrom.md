# sqlite3DeleteFrom

- ea: `0x18007daa0`
- end: `0x18007e416`
- name: `sqlite3DeleteFrom`
- size: `2422`
- prototype: ``
- caller_count: `3`
- callee_count: `39`
- tags: ``

## callers

- `0x18001bc30`
- `0x1800595f8`
- `0x180082408`

## callees

- `0x180006ac0`
- `0x180007a00`
- `0x18000b4bc`
- `0x18000db18`
- `0x180015e80`
- `0x18002d570`
- `0x1800369e4`
- `0x18003713c`
- `0x180037774`
- `0x180038974`
- `0x18003be78`
- `0x18003bff4`
- `0x18003c4c4`
- `0x18003c5f4`
- `0x18003ceec`
- `0x18003d480`
- `0x18003e68c`
- `0x18003f960`
- `0x18004002c`
- `0x180041574`
- `0x180041c54`
- `0x180041fd0`
- `0x1800421bc`
- `0x180042260`
- `0x18004242c`
- `0x180042c38`
- `0x180042cb0`
- `0x180042cd4`
- `0x180045374`
- `0x180078a68`
- `0x18007b620`
- `0x18007daa0`
- `0x1800828a0`
- `0x180083240`
- `0x18008608c`
- `0x180086890`
- `0x18008cd90`
- `0x18008daa8`
- `0x18008ff40`

## string_xrefs

- `0x18007e3ba`: `rows deleted`

## pseudocode

```c
void *__fastcall sqlite3DeleteFrom(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 *v3; // rsi
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // r15
  __int64 v7; // rax
  char v8; // r12
  __int64 v9; // rdi
  BOOL v10; // ebx
  __int64 v11; // rdi
  int v12; // r13d
  int v13; // edx
  __int64 v14; // rax
  int v15; // ecx
  __int64 Vdbe; // rax
  __int64 v17; // r14
  int v18; // r9d
  int v19; // r12d
  int v20; // ecx
  __int64 i; // rbx
  int v22; // eax
  __int16 v23; // bx
  __int64 v24; // rdi
  int v25; // eax
  int v26; // r8d
  int v27; // edx
  int v28; // eax
  int v29; // r8d
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rbx
  char v33; // al
  __int64 *v34; // rcx
  __int64 v35; // rdi
  int v36; // r12d
  int v37; // r9d
  _BYTE *v38; // rdx
  int v39; // ecx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  char v43; // di
  unsigned int v44; // ebx
  int v45; // r13d
  int v46; // edx
  unsigned int v47; // ebx
  int v48; // r9d
  int v49; // eax
  int v50; // edx
  __int64 VTable; // rdi
  __int64 *v52; // rdx
  int v53; // r8d
  unsigned int v54; // r9d
  int v55; // edx
  __int64 v56; // rsi
  void *result; // rax
  int v58; // [rsp+28h] [rbp-E0h]
  int v59; // [rsp+68h] [rbp-A0h] BYREF
  int v60; // [rsp+6Ch] [rbp-9Ch]
  int v61; // [rsp+70h] [rbp-98h]
  int v62; // [rsp+74h] [rbp-94h]
  int v63; // [rsp+78h] [rbp-90h]
  int v64; // [rsp+7Ch] [rbp-8Ch]
  int v65; // [rsp+80h] [rbp-88h] BYREF
  __int64 v66; // [rsp+88h] [rbp-80h]
  int v67; // [rsp+90h] [rbp-78h]
  int v68; // [rsp+94h] [rbp-74h]
  unsigned int v69; // [rsp+98h] [rbp-70h]
  unsigned int v70; // [rsp+9Ch] [rbp-6Ch]
  void *v71; // [rsp+A0h] [rbp-68h]
  __int64 v72; // [rsp+A8h] [rbp-60h]
  __int64 v73; // [rsp+B0h] [rbp-58h]
  __int64 v74; // [rsp+B8h] [rbp-50h]
  __int64 v75; // [rsp+C0h] [rbp-48h]
  __int64 v76; // [rsp+C8h] [rbp-40h]
  __int128 v77; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v78; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v79; // [rsp+F0h] [rbp-18h]
  __int128 v80; // [rsp+100h] [rbp-8h]
  __int64 v81; // [rsp+110h] [rbp+8h]
  unsigned int v83; // [rsp+168h] [rbp+60h]
  int v86; // [rsp+180h] [rbp+78h]
  char v87; // [rsp+180h] [rbp+78h]
  char v89; // [rsp+188h] [rbp+80h]

  v59 = 0;
  v3 = a1;
  v65 = 0;
  v78 = 0;
  v81 = 0;
  v4 = *a1;
  v72 = *a1;
  v79 = 0;
  v71 = 0;
  v80 = 0;
  v77 = 0;
  if ( !*((_DWORD *)a1 + 12) )
  {
    v5 = sqlite3SrcListLookup(a1, a2);
    v6 = v5;
    if ( v5 )
    {
      v7 = sqlite3TriggersExist((_DWORD)v3, v5, 128, 0, 0);
      v8 = *(_BYTE *)(v6 + 63);
      v9 = v7;
      v89 = v8;
      v76 = v7;
      v10 = v7 || (unsigned int)sqlite3FkRequired(v3, v6, 0, 0);
      if ( !(unsigned int)sqlite3ViewGetColumnNames(v3, v6) && !(unsigned int)sqlite3IsReadOnly(v3, v6, v9) )
      {
        v11 = (int)sqlite3SchemaToIndex(v4, *(_QWORD *)(v6 + 96));
        v86 = sqlite3AuthCheck((_DWORD)v3, 9, *(_QWORD *)v6, 0, *(_QWORD *)(32 * v11 + *(_QWORD *)(v4 + 32)));
        if ( v86 != 1 )
        {
          v12 = *((_DWORD *)v3 + 13);
          v13 = 0;
          v60 = v12;
          v68 = 0;
          *(_DWORD *)(a2 + 76) = v12;
          ++*((_DWORD *)v3 + 13);
          v14 = *(_QWORD *)(v6 + 16);
          v15 = *((_DWORD *)v3 + 13);
          if ( v14 )
          {
            do
            {
              ++v15;
              ++v13;
              *((_DWORD *)v3 + 13) = v15;
              v14 = *(_QWORD *)(v14 + 40);
            }
            while ( v14 );
            v68 = v13;
          }
          if ( v8 == 2 )
          {
            *(_QWORD *)&v77 = v3[47];
            v3[47] = *(_QWORD *)v6;
            *((_QWORD *)&v77 + 1) = v3;
          }
          Vdbe = sqlite3GetVdbe(v3);
          v17 = Vdbe;
          if ( Vdbe )
          {
            if ( !*((_BYTE *)v3 + 30) )
              *(_DWORD *)(Vdbe + 200) |= 0x10u;
            sqlite3BeginWriteOperation(v3, v10, (unsigned int)v11);
            if ( v8 == 2 )
            {
              sqlite3MaterializeView((_DWORD)v3, v6, a3, 0, 0, v12);
              v65 = v12;
              v59 = v12;
            }
            v81 = 0;
            *((_QWORD *)&v78 + 1) = a2;
            v79 = 0;
            *(_QWORD *)&v78 = v3;
            v80 = 0;
            if ( !(unsigned int)sqlite3ResolveExprNames(&v78, a3) )
            {
              v19 = 0;
              v70 = 0;
              if ( (*(_QWORD *)(v72 + 48) & 0x100000000LL) != 0
                && !*((_BYTE *)v3 + 30)
                && !v3[23]
                && !*((_BYTE *)v3 + 227) )
              {
                v19 = ++*((_DWORD *)v3 + 14);
                v70 = v19;
                sqlite3VdbeAddOp3(v17, 71, 0, v19, 0);
              }
              if ( !v86 && !a3 && !v10 && *(_BYTE *)(v6 + 63) != 1 )
              {
                LOBYTE(v18) = 1;
                sqlite3TableLock((_DWORD)v3, v11, *(_DWORD *)(v6 + 40), v18, *(_QWORD *)v6);
                if ( *(char *)(v6 + 48) >= 0 )
                {
                  v20 = -1;
                  if ( v19 )
                    v20 = v19;
                  sqlite3VdbeAddOp4(v17, 145, *(_DWORD *)(v6 + 40), v11, v20, *(_QWORD *)v6, -1);
                }
                for ( i = *(_QWORD *)(v6 + 16); i; i = *(_QWORD *)(i + 40) )
                {
                  if ( (*(_DWORD *)(i + 100) & 3) == 2 && *(char *)(v6 + 48) < 0 )
                  {
                    v22 = -1;
                    if ( v19 )
                      v22 = v19;
                  }
                  else
                  {
                    v22 = 0;
                  }
                  sqlite3VdbeAddOp3(v17, 145, *(_DWORD *)(i + 88), v11, v22);
                }
                goto LABEL_111;
              }
              if ( (BYTE8(v80) & 0x40) != 0 )
                LOWORD(v10) = 1;
              v23 = (8 * !v10) | 0x14;
              if ( *(char *)(v6 + 48) < 0 )
              {
                v64 = 0;
                v24 = sqlite3PrimaryKeyIndex(v6);
                v66 = v24;
                v58 = v26;
                v27 = *(unsigned __int16 *)(v24 + 94);
                v28 = *((_DWORD *)v3 + 14);
                v61 = v27;
                v63 = v28 + 1;
                v29 = *((_DWORD *)v3 + 13);
                *((_DWORD *)v3 + 14) = (__int16)v27 + v28;
                v62 = v29;
                *((_DWORD *)v3 + 13) = v29 + 1;
                v69 = sqlite3VdbeAddOp3(v17, 118, v29, (__int16)v27, v58);
                sqlite3VdbeSetP4KeyInfo(v3, v24);
                LOWORD(v24) = v61;
              }
              else
              {
                ++*((_DWORD *)v3 + 14);
                LOWORD(v24) = 1;
                v25 = *((_DWORD *)v3 + 14);
                v63 = 0;
                v62 = 0;
                v69 = 0;
                v66 = 0;
                v61 = 1;
                v64 = v25;
                sqlite3VdbeAddOp3(v17, 75, 0, v25, 0);
              }
              v30 = sqlite3WhereBegin((_DWORD)v3, a2, a3, 0, 0, 0, v23, v12 + 1);
              v73 = v30;
              v31 = v30;
              if ( v30 )
              {
                v32 = *(_QWORD *)(v30 + 40);
                v33 = *(_BYTE *)(v30 + 66);
                v75 = v32;
                v74 = v32;
                v87 = v33;
                if ( v33 != 1 )
                {
                  v34 = v3;
                  if ( v3[22] )
                    v34 = (__int64 *)v3[22];
                  *((_BYTE *)v34 + 32) = 1;
                }
                if ( (*(_BYTE *)(v31 + 68) & 1) != 0 )
                  sqlite3VdbeAddOp3(v17, 143, v12, 0, 0);
                if ( v19 )
                  sqlite3VdbeAddOp3(v17, 86, v19, 1, 0);
                LODWORD(v24) = (__int16)v24;
                v67 = (__int16)v24;
                if ( v66 )
                {
                  v35 = 0;
                  if ( v67 > 0 )
                  {
                    do
                    {
                      sqlite3ExprCodeGetColumnOfTable(
                        v17,
                        v6,
                        v60,
                        *(__int16 *)(*(_QWORD *)(v66 + 8) + 2 * v35),
                        v63 + v35);
                      v35 = (unsigned int)(v35 + 1);
                    }
                    while ( (int)v35 < v67 );
                    LODWORD(v32) = v75;
                    v3 = a1;
                  }
                  v36 = v63;
                  LODWORD(v24) = v67;
                }
                else
                {
                  v36 = ++*((_DWORD *)v3 + 14);
                  sqlite3ExprCodeGetColumnOfTable(v17, v6, v60, -1, v36);
                }
                if ( v87 )
                {
                  v71 = (void *)sqlite3DbMallocRawNN(v72, v68 + 2);
                  if ( !v71 )
                  {
                    sqlite3WhereEnd(v73);
                    goto LABEL_116;
                  }
                  memset_0(v71, 1, v68 + 1LL);
                  v38 = v71;
                  v39 = v60;
                  *((_BYTE *)v71 + v68 + 1) = 0;
                  if ( (int)v32 >= 0 )
                    v38[(int)v32 - v39] = 0;
                  if ( v74 >= 0 )
                    v38[HIDWORD(v74) - v39] = 0;
                  if ( v69 )
                    sqlite3VdbeChangeToNoop(v17, v69);
                  v83 = --*((_DWORD *)v3 + 17);
                }
                else
                {
                  v40 = v66;
                  v83 = 0;
                  if ( v66 )
                  {
                    ++*((_DWORD *)v3 + 14);
                    v41 = *v3;
                    v36 = *((_DWORD *)v3 + 14);
                    v61 = 0;
                    v42 = sqlite3IndexAffinityStr(v41, v40);
                    sqlite3VdbeAddOp4(v17, 97, v63, v24, v36, v42, v24);
                    sqlite3VdbeAddOp4Int(v17, 138, v62, v36, v63, v24);
                  }
                  else
                  {
                    LOWORD(v61) = 1;
                    sqlite3VdbeAddOp3(v17, 156, v64, v36, 0);
                  }
                  sqlite3WhereEnd(v73);
                }
                v43 = v87;
                if ( v89 == 2 )
                {
                  v45 = v60;
                }
                else
                {
                  v44 = 0;
                  if ( v87 == 2 )
                    v44 = sqlite3VdbeAddOp3(v17, 15, 0, 0, 0);
                  v45 = v60;
                  LOBYTE(v37) = 8;
                  sqlite3OpenTableAndIndices((_DWORD)v3, v6, 113, v37, v60, (__int64)v71, (__int64)&v59, (__int64)&v65);
                  if ( v87 == 2 )
                  {
                    sqlite3VdbeJumpHereOrPopInst(v17, v44);
                    goto LABEL_85;
                  }
                }
                if ( !v87 )
                {
                  if ( v66 )
                  {
                    v47 = sqlite3VdbeAddOp3(v17, 36, v62, 0, 0);
                    if ( *(_BYTE *)(v6 + 63) == 1 )
                    {
                      v48 = 0;
                      v49 = v36;
                    }
                    else
                    {
                      v48 = v36;
                      v49 = 0;
                    }
                    v50 = 94;
                    if ( *(_BYTE *)(v6 + 63) != 1 )
                      v50 = 134;
                    sqlite3VdbeAddOp3(v17, v50, v62, v48, v49);
                  }
                  else
                  {
                    v47 = sqlite3VdbeAddOp3(v17, 46, v64, 0, v36);
                  }
                  goto LABEL_96;
                }
LABEL_85:
                v46 = v59;
                v47 = 0;
                if ( *(_BYTE *)(v6 + 63) == 1 )
                  goto LABEL_98;
                if ( !*((_BYTE *)v71 + v59 - v45) )
                {
LABEL_97:
                  if ( *(_BYTE *)(v6 + 63) != 1 )
                  {
                    sqlite3GenerateRowDelete(
                      (_DWORD)v3,
                      v6,
                      v76,
                      v46,
                      v65,
                      v36,
                      v61,
                      *((_BYTE *)v3 + 30) == 0,
                      11,
                      v87,
                      HIDWORD(v74));
LABEL_105:
                    if ( v43 )
                    {
                      sqlite3VdbeResolveLabel(v17, v83);
                      sqlite3WhereEnd(v73);
                    }
                    else
                    {
                      if ( v66 )
                      {
                        v53 = v62;
                        v54 = v47 + 1;
                        v55 = 39;
                      }
                      else
                      {
                        v53 = 0;
                        v54 = v47;
                        v55 = 9;
                      }
                      sqlite3VdbeAddOp3(v17, v55, v53, v54, 0);
                      *(_DWORD *)(sqlite3VdbeGetOp(v17, v47) + 8) = *(_DWORD *)(v17 + 144);
                    }
LABEL_111:
                    if ( !*((_BYTE *)v3 + 30) && !v3[23] )
                      sqlite3AutoincrementEnd(v3);
                    if ( v70 )
                      sqlite3CodeChangeCount(v17, v70, "rows deleted");
                    goto LABEL_116;
                  }
LABEL_98:
                  VTable = sqlite3GetVTable(v72, v6);
                  sqlite3VtabMakeWritable(v3);
                  v52 = v3;
                  if ( v3[22] )
                    v52 = (__int64 *)v3[22];
                  *((_BYTE *)v52 + 33) = 1;
                  if ( v87 == 1 )
                  {
                    sqlite3VdbeAddOp3(v17, 122, v45, 0, 0);
                    if ( !v3[22] )
                      *((_BYTE *)v3 + 32) = 0;
                  }
                  sqlite3VdbeAddOp4(v17, 7, 0, 1, v36, VTable, -11);
                  sqlite3VdbeChangeP5(v17, 2);
                  v43 = v87;
                  goto LABEL_105;
                }
                sqlite3VdbeAddOp4Int(v17, 28, v59, v83, v36, (__int16)v61);
LABEL_96:
                v46 = v59;
                goto LABEL_97;
              }
            }
          }
        }
      }
    }
  }
LABEL_116:
  sqlite3AuthContextPop(&v77);
  v56 = v72;
  sqlite3SrcListDelete(v72, a2);
  sqlite3ExprDeleteGeneric(v56, a3);
  result = v71;
  if ( v71 )
    return (void *)sqlite3DbNNFreeNN(v56);
  return result;
}

```

## disassembly

```asm
0x18007daa0  mov     rax, rsp
0x18007daa3  mov     [rax+20h], r9
0x18007daa7  mov     [rax+18h], r8
0x18007daab  mov     [rax+10h], rdx
0x18007daaf  mov     [rax+8], rcx
0x18007dab3  push    rbp
0x18007dab4  push    rbx
0x18007dab5  push    rsi
0x18007dab6  push    rdi
0x18007dab7  push    r12
0x18007dab9  push    r13
0x18007dabb  push    r14
0x18007dabd  push    r15
0x18007dabf  lea     rbp, [rax-58h]
0x18007dac3  sub     rsp, 118h
0x18007daca  xorps   xmm0, xmm0
0x18007dacd  mov     [rsp+150h+var_F0], 0
0x18007dad5  mov     rsi, rcx
0x18007dad8  mov     [rsp+150h+var_D8], 0
0x18007dae0  xor     ecx, ecx
0x18007dae2  movups  [rbp+50h+var_78], xmm0
0x18007dae6  mov     [rbp+50h+var_48], rcx
0x18007daea  mov     r14, [rsi]
0x18007daed  mov     [rbp+50h+var_B0], r14
0x18007daf1  movups  [rbp+50h+var_68], xmm0
0x18007daf5  mov     [rbp+50h+var_B8], rcx
0x18007daf9  movups  [rbp+50h+var_58], xmm0
0x18007dafd  movups  [rbp+50h+var_88], xmm0
0x18007db01  cmp     [rsi+30h], ecx
0x18007db04  jnz     loc_18007E3C9
0x18007db0a  mov     rcx, rsi
0x18007db0d  call    sqlite3SrcListLookup
0x18007db12  mov     r15, rax
0x18007db15  test    rax, rax
0x18007db18  jz      loc_18007E3C9
0x18007db1e  xor     r9d, r9d
0x18007db21  mov     [rsp+150h+var_130], 0
0x18007db2a  mov     r8d, 80h
0x18007db30  mov     rdx, rax
0x18007db33  mov     rcx, rsi
0x18007db36  call    sqlite3TriggersExist
0x18007db3b  mov     r12b, [r15+3Fh]
0x18007db3f  mov     rdi, rax
0x18007db42  mov     [rbp+50h+arg_20], r12b
0x18007db49  mov     r13d, 1
0x18007db4f  mov     [rbp+50h+var_90], rax
0x18007db53  test    rax, rax
0x18007db56  jnz     short loc_18007DB71
0x18007db58  xor     r9d, r9d
0x18007db5b  xor     r8d, r8d
0x18007db5e  mov     rdx, r15
0x18007db61  mov     rcx, rsi
0x18007db64  call    sqlite3FkRequired
0x18007db69  test    eax, eax
0x18007db6b  jnz     short loc_18007DB71
0x18007db6d  xor     ebx, ebx
0x18007db6f  jmp     short loc_18007DB74
0x18007db71  mov     ebx, r13d
0x18007db74  mov     rdx, r15
0x18007db77  mov     rcx, rsi
0x18007db7a  call    sqlite3ViewGetColumnNames
0x18007db7f  test    eax, eax
0x18007db81  jnz     loc_18007E3C9
0x18007db87  mov     r8, rdi
0x18007db8a  mov     rdx, r15
0x18007db8d  mov     rcx, rsi
0x18007db90  call    sqlite3IsReadOnly
0x18007db95  test    eax, eax
0x18007db97  jnz     loc_18007E3C9
0x18007db9d  mov     rdx, [r15+60h]
0x18007dba1  mov     rcx, r14
0x18007dba4  call    sqlite3SchemaToIndex
0x18007dba9  mov     r8, [r15]
0x18007dbac  xor     r9d, r9d
0x18007dbaf  movsxd  rdi, eax
0x18007dbb2  mov     rax, [r14+20h]
0x18007dbb6  mov     rcx, rdi
0x18007dbb9  shl     rcx, 5
0x18007dbbd  lea     edx, [r9+9]
0x18007dbc1  mov     rcx, [rcx+rax]
0x18007dbc5  mov     [rsp+150h+var_130], rcx
0x18007dbca  mov     rcx, rsi
0x18007dbcd  call    sqlite3AuthCheck
0x18007dbd2  mov     [rbp+50h+arg_18], eax
0x18007dbd5  cmp     eax, r13d
0x18007dbd8  jz      loc_18007E3C9
0x18007dbde  mov     r13d, [rsi+34h]
0x18007dbe2  xor     edx, edx
0x18007dbe4  mov     rax, [rbp+50h+arg_8]
0x18007dbe8  mov     r8d, 1
0x18007dbee  mov     [rsp+150h+var_EC], r13d
0x18007dbf3  mov     [rbp+50h+var_C4], edx
0x18007dbf6  mov     [rax+4Ch], r13d
0x18007dbfa  add     [rsi+34h], r8d
0x18007dbfe  mov     rax, [r15+10h]
0x18007dc02  mov     ecx, [rsi+34h]
0x18007dc05  test    rax, rax
0x18007dc08  jz      short loc_18007DC1E
0x18007dc0a  inc     ecx
0x18007dc0c  add     edx, r8d
0x18007dc0f  mov     [rsi+34h], ecx
0x18007dc12  mov     rax, [rax+28h]
0x18007dc16  test    rax, rax
0x18007dc19  jnz     short loc_18007DC0A
0x18007dc1b  mov     [rbp+50h+var_C4], edx
0x18007dc1e  cmp     r12b, 2
0x18007dc22  jnz     short loc_18007DC3D
0x18007dc24  mov     rax, [rsi+178h]
0x18007dc2b  mov     qword ptr [rbp+50h+var_88], rax
0x18007dc2f  mov     rax, [r15]
0x18007dc32  mov     [rsi+178h], rax
0x18007dc39  mov     qword ptr [rbp+50h+var_88+8], rsi
0x18007dc3d  mov     rcx, rsi
0x18007dc40  call    sqlite3GetVdbe
0x18007dc45  mov     r14, rax
0x18007dc48  test    rax, rax
0x18007dc4b  jz      loc_18007E3C9
0x18007dc51  cmp     byte ptr [rsi+1Eh], 0
0x18007dc55  jnz     short loc_18007DC5E
0x18007dc57  or      dword ptr [rax+0C8h], 10h
0x18007dc5e  mov     r8d, edi
0x18007dc61  mov     edx, ebx
0x18007dc63  mov     rcx, rsi
0x18007dc66  call    sqlite3BeginWriteOperation
0x18007dc6b  cmp     r12b, 2
0x18007dc6f  mov     r12, [rbp+50h+arg_10]
0x18007dc73  jnz     short loc_18007DC9E
0x18007dc75  mov     dword ptr [rsp+150h+var_128], r13d
0x18007dc7a  xor     r9d, r9d
0x18007dc7d  mov     r8, r12
0x18007dc80  mov     [rsp+150h+var_130], 0
0x18007dc89  mov     rdx, r15
0x18007dc8c  mov     rcx, rsi
0x18007dc8f  call    sqlite3MaterializeView
0x18007dc94  mov     [rsp+150h+var_D8], r13d
0x18007dc99  mov     [rsp+150h+var_F0], r13d
0x18007dc9e  xorps   xmm0, xmm0
0x18007dca1  lea     rcx, [rbp+50h+var_78]
0x18007dca5  xor     eax, eax
0x18007dca7  mov     rdx, r12
0x18007dcaa  movups  [rbp+50h+var_78], xmm0
0x18007dcae  mov     [rbp+50h+var_48], rax
0x18007dcb2  mov     rax, [rbp+50h+arg_8]
0x18007dcb6  mov     qword ptr [rbp+50h+var_78+8], rax
0x18007dcba  movups  [rbp+50h+var_68], xmm0
0x18007dcbe  mov     qword ptr [rbp+50h+var_78], rsi
0x18007dcc2  movups  [rbp+50h+var_58], xmm0
0x18007dcc6  call    sqlite3ResolveExprNames
0x18007dccb  xor     r8d, r8d
0x18007dcce  test    eax, eax
0x18007dcd0  jnz     loc_18007E3C9
0x18007dcd6  mov     rax, [rbp+50h+var_B0]
0x18007dcda  mov     rcx, 100000000h
0x18007dce4  mov     r12d, r8d
0x18007dce7  mov     [rbp+50h+var_BC], r8d
0x18007dceb  test    [rax+30h], rcx
0x18007dcef  jz      short loc_18007DD2B
0x18007dcf1  cmp     [rsi+1Eh], r8b
0x18007dcf5  jnz     short loc_18007DD2B
0x18007dcf7  cmp     [rsi+0B8h], r8
0x18007dcfe  jnz     short loc_18007DD2B
0x18007dd00  cmp     [rsi+0E3h], r8b
0x18007dd07  jnz     short loc_18007DD2B
0x18007dd09  inc     dword ptr [rsi+38h]
0x18007dd0c  lea     edx, [r8+47h]
0x18007dd10  mov     r12d, [rsi+38h]
0x18007dd14  mov     rcx, r14
0x18007dd17  mov     r9d, r12d
0x18007dd1a  mov     [rbp+50h+var_BC], r12d
0x18007dd1e  mov     dword ptr [rsp+150h+var_130], r8d
0x18007dd23  call    sqlite3VdbeAddOp3
0x18007dd28  xor     r8d, r8d
0x18007dd2b  mov     ecx, 1
0x18007dd30  cmp     [rbp+50h+arg_18], r8d
0x18007dd34  jnz     loc_18007DDF3
0x18007dd3a  cmp     [rbp+50h+arg_10], r8
0x18007dd3e  jnz     loc_18007DDF3
0x18007dd44  test    ebx, ebx
0x18007dd46  jnz     loc_18007DDF3
0x18007dd4c  cmp     [r15+3Fh], cl
0x18007dd50  jz      loc_18007DDF3
0x18007dd56  mov     rax, [r15]
0x18007dd59  mov     r9b, cl
0x18007dd5c  mov     r8d, [r15+28h]
0x18007dd60  mov     rcx, rsi
0x18007dd63  mov     edx, edi
0x18007dd65  mov     [rsp+150h+var_130], rax
0x18007dd6a  call    sqlite3TableLock
0x18007dd6f  or      r13d, 0FFFFFFFFh
0x18007dd73  test    byte ptr [r15+30h], 80h
0x18007dd78  jnz     short loc_18007DDA9
0x18007dd7a  mov     rax, [r15]
0x18007dd7d  test    r12d, r12d
0x18007dd80  mov     r8d, [r15+28h]
0x18007dd84  mov     ecx, r13d
0x18007dd87  cmovnz  ecx, r12d
0x18007dd8b  mov     dword ptr [rsp+150h+var_120], r13d
0x18007dd90  mov     [rsp+150h+var_128], rax
0x18007dd95  mov     r9d, edi
0x18007dd98  mov     dword ptr [rsp+150h+var_130], ecx
0x18007dd9c  mov     edx, 91h
0x18007dda1  mov     rcx, r14
0x18007dda4  call    sqlite3VdbeAddOp4
0x18007dda9  mov     rbx, [r15+10h]
0x18007ddad  jmp     short loc_18007DDE9
0x18007ddaf  mov     eax, [rbx+64h]
0x18007ddb2  and     al, 3
0x18007ddb4  cmp     al, 2
0x18007ddb6  jnz     short loc_18007DDCB
0x18007ddb8  test    byte ptr [r15+30h], 80h
0x18007ddbd  jz      short loc_18007DDCB
0x18007ddbf  test    r12d, r12d
0x18007ddc2  mov     eax, r13d
0x18007ddc5  cmovnz  eax, r12d
0x18007ddc9  jmp     short loc_18007DDCD
0x18007ddcb  xor     eax, eax
0x18007ddcd  mov     r8d, [rbx+58h]
0x18007ddd1  mov     r9d, edi
0x18007ddd4  mov     edx, 91h
0x18007ddd9  mov     dword ptr [rsp+150h+var_130], eax
0x18007dddd  mov     rcx, r14
0x18007dde0  call    sqlite3VdbeAddOp3
0x18007dde5  mov     rbx, [rbx+28h]
0x18007dde9  test    rbx, rbx
0x18007ddec  jnz     short loc_18007DDAF
0x18007ddee  jmp     loc_18007E39B
0x18007ddf3  test    byte ptr [rbp+50h+var_58+8], 40h
0x18007ddf7  cmovnz  ebx, ecx
0x18007ddfa  xor     bx, cx
0x18007ddfd  shl     bx, 3
0x18007de01  or      bx, 14h
0x18007de05  test    byte ptr [r15+30h], 80h
0x18007de0a  jnz     short loc_18007DE48
0x18007de0c  add     [rsi+38h], ecx
0x18007de0f  movzx   edi, cx
0x18007de12  mov     eax, [rsi+38h]
0x18007de15  mov     rcx, r14
0x18007de18  mov     [rsp+150h+var_E0], r8d
0x18007de1d  mov     r9d, eax
0x18007de20  mov     [rsp+150h+var_E4], r8d
0x18007de25  mov     [rbp+50h+var_C0], r8d
0x18007de29  mov     [rbp+50h+var_D0], r8
0x18007de2d  mov     dword ptr [rsp+150h+var_130], r8d
0x18007de32  xor     r8d, r8d
0x18007de35  mov     [rsp+150h+var_E8], edi
0x18007de39  mov     [rsp+150h+var_DC], eax
0x18007de3d  lea     edx, [r8+4Bh]
0x18007de41  call    sqlite3VdbeAddOp3
0x18007de46  jmp     short loc_18007DEAC
0x18007de48  mov     rcx, r15
0x18007de4b  mov     [rsp+150h+var_DC], r8d
0x18007de50  call    sqlite3PrimaryKeyIndex
0x18007de55  mov     rdi, rax
0x18007de58  mov     [rbp+50h+var_D0], rax
0x18007de5c  mov     dword ptr [rsp+150h+var_130], r8d
0x18007de61  movzx   edx, word ptr [rax+5Eh]
0x18007de65  mov     eax, [rsi+38h]
0x18007de68  movsx   r9d, dx
0x18007de6c  mov     [rsp+150h+var_E8], edx
0x18007de70  mov     edx, 76h ; 'v'
0x18007de75  lea     ecx, [rax+1]
0x18007de78  add     eax, r9d
0x18007de7b  mov     [rsp+150h+var_E0], ecx
0x18007de7f  mov     ecx, [rsi+34h]
0x18007de82  mov     r8d, ecx
0x18007de85  mov     [rsi+38h], eax
0x18007de88  mov     [rsp+150h+var_E4], ecx
0x18007de8c  lea     eax, [rcx+1]
0x18007de8f  mov     rcx, r14
0x18007de92  mov     [rsi+34h], eax
0x18007de95  call    sqlite3VdbeAddOp3
0x18007de9a  mov     rdx, rdi
0x18007de9d  mov     [rbp+50h+var_C0], eax
0x18007dea0  mov     rcx, rsi
0x18007dea3  call    sqlite3VdbeSetP4KeyInfo
0x18007dea8  mov     edi, [rsp+150h+var_E8]
0x18007deac  mov     r8, [rbp+50h+arg_10]
0x18007deb0  lea     eax, [r13+1]
0x18007deb4  mov     rdx, [rbp+50h+arg_8]
0x18007deb8  xor     r9d, r9d
0x18007debb  mov     dword ptr [rsp+150h+var_118], eax
0x18007debf  mov     rcx, rsi
0x18007dec2  mov     word ptr [rsp+150h+var_120], bx
0x18007dec7  mov     [rsp+150h+var_128], 0
0x18007ded0  mov     [rsp+150h+var_130], 0
0x18007ded9  call    sqlite3WhereBegin
0x18007dede  mov     [rbp+50h+var_A8], rax
0x18007dee2  mov     rdx, rax
0x18007dee5  test    rax, rax
0x18007dee8  jz      loc_18007E3C9
0x18007deee  mov     rbx, [rax+28h]
0x18007def2  mov     r8d, 1
0x18007def8  mov     al, [rax+42h]
0x18007defb  mov     [rbp+50h+var_98], rbx
0x18007deff  mov     [rbp+50h+var_A0], rbx
0x18007df03  mov     byte ptr [rbp+50h+arg_18], al
0x18007df06  cmp     al, r8b
0x18007df09  jz      short loc_18007DF20
0x18007df0b  mov     rax, [rsi+0B0h]
0x18007df12  mov     rcx, rsi
  ... truncated ...
```

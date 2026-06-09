# multiSelect

- ea: `0x14003a3c4`
- end: `0x14003abc5`
- name: `multiSelect`
- size: `2049`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x14006cd0c`

## callees

- `0x140024e2c`
- `0x14002f17c`
- `0x14003a3c4`
- `0x14003abcc`
- `0x14003ac30`
- `0x14003b5e0`
- `0x1400480a0`
- `0x140054038`
- `0x14005904c`
- `0x140059b7c`
- `0x14005f5fc`
- `0x140061cc8`
- `0x14006299c`
- `0x140062a00`
- `0x140065e48`
- `0x14006cd0c`
- `0x14006efb4`
- `0x1400738a0`
- `0x14007399c`
- `0x140073ca8`
- `0x14007aa84`
- `0x14007ab20`
- `0x14007b574`
- `0x14007da70`

## string_xrefs

- `0x14003a4cb`: `COMPOUND QUERY`
- `0x14003a5d6`: `%s USING TEMP B-TREE`
- `0x14003a93c`: `%s USING TEMP B-TREE`

## pseudocode

```c
__int64 __fastcall multiSelect(__int64 *a1, unsigned __int8 *a2, __int128 *a3)
{
  __int64 v3; // rsi
  int v4; // r12d
  __int128 v5; // xmm1
  __int64 v6; // rbx
  unsigned __int8 *v8; // r14
  __int64 v9; // r15
  __int64 Vdbe; // rax
  __int64 v11; // r13
  unsigned __int8 *v12; // rax
  int v14; // edi
  unsigned __int8 *i; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rsi
  const char *v19; // rax
  __int16 v20; // ax
  unsigned int v21; // esi
  char v22; // al
  int v23; // ebx
  unsigned __int8 v24; // al
  int v25; // eax
  unsigned int v26; // edi
  int v27; // r8d
  int v28; // eax
  int v29; // eax
  __int64 v30; // r11
  __int64 v31; // rcx
  __int16 v32; // ax
  __int64 v33; // rcx
  __int16 v34; // ax
  __int16 v35; // r10
  int v36; // edi
  unsigned __int8 *j; // rax
  char v38; // cl
  __int64 v39; // rdi
  const char *v40; // rax
  int v41; // eax
  bool v42; // zf
  unsigned int v43; // esi
  unsigned int v44; // edi
  int v45; // ebx
  __int64 v46; // rax
  __int64 v47; // rbx
  int v48; // esi
  __int64 *v49; // rdi
  int v50; // ebx
  __int64 v51; // r13
  __int64 v52; // rax
  int v53; // r15d
  __int64 v54; // rdi
  __int64 v55; // rdx
  __int64 *v56; // rax
  __int128 *v57; // rcx
  __int64 v58; // [rsp+40h] [rbp-79h]
  __int128 v59; // [rsp+48h] [rbp-71h] BYREF
  __int128 v60; // [rsp+58h] [rbp-61h]
  __int64 v61; // [rsp+68h] [rbp-51h]
  _QWORD v62[5]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v63[37]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v64; // [rsp+C0h] [rbp+7h]
  __int64 v65; // [rsp+C8h] [rbp+Fh]
  int v67; // [rsp+128h] [rbp+6Fh] BYREF
  __int128 *v68; // [rsp+130h] [rbp+77h]
  __int64 v69; // [rsp+138h] [rbp+7Fh]

  v68 = a3;
  v3 = *a1;
  v4 = 0;
  v5 = a3[1];
  v6 = *((_QWORD *)a2 + 10);
  v59 = *a3;
  v8 = a2;
  v9 = (__int64)a1;
  v61 = *((_QWORD *)a3 + 4);
  v58 = 0;
  v69 = v3;
  v60 = v5;
  Vdbe = sqlite3GetVdbe(a1);
  v11 = Vdbe;
  v65 = Vdbe;
  if ( (_BYTE)v59 == 12 )
  {
    sqlite3VdbeAddOp3(Vdbe, 118, DWORD1(v59), **((_DWORD **)v8 + 4), 0);
    LOBYTE(v59) = 14;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x400) != 0 )
  {
    v4 = multiSelectValues(v9, v8, &v59);
    if ( v4 >= 0 )
      goto LABEL_81;
    v4 = 0;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x2000) != 0 )
  {
    v12 = v8;
    do
    {
      if ( (*((_DWORD *)v12 + 1) & 0x2000) == 0 )
        break;
      v12 = (unsigned __int8 *)*((_QWORD *)v12 + 10);
    }
    while ( v12 );
    if ( v12 )
    {
      generateWithRecursiveQuery(v9, v8, &v59);
LABEL_61:
      if ( !*(_DWORD *)(v9 + 48) && (v8[4] & 0x20) != 0 )
      {
        v67 = **((_DWORD **)v8 + 4);
        v46 = sqlite3KeyInfoAlloc(v3, (unsigned int)v67, 1);
        v64 = v46;
        v47 = v46;
        if ( v46 )
        {
          v48 = 0;
          v49 = (__int64 *)(v46 + 32);
          if ( v67 > 0 )
          {
            v50 = v67;
            v51 = v69;
            do
            {
              v52 = multiSelectCollSeq(v9, v8, (unsigned int)v48);
              *v49 = v52;
              if ( !v52 )
                *v49 = *(_QWORD *)(v51 + 16);
              ++v48;
              ++v49;
            }
            while ( v48 < v50 );
            v47 = v64;
            v11 = v65;
          }
          v53 = v67;
          do
          {
            v54 = 0;
            do
            {
              v55 = *(int *)&v8[4 * v54 + 20];
              if ( (int)v55 < 0 )
                break;
              v56 = *(_BYTE *)(*(_QWORD *)v11 + 103LL)
                  ? qword_1400C8EC0
                  : (__int64 *)(*(_QWORD *)(v11 + 136) + 24 * v55);
              *((_DWORD *)v56 + 2) = v53;
              ++*(_DWORD *)v47;
              sqlite3VdbeChangeP4(v11, v55, v47, 4294967288LL);
              *(_DWORD *)&v8[4 * v54 + 20] = -1;
              v54 = (unsigned int)(v54 + 1);
            }
            while ( (int)v54 < 2 );
            v8 = (unsigned __int8 *)*((_QWORD *)v8 + 10);
          }
          while ( v8 );
          v42 = (*(_DWORD *)v47)-- == 1;
          v9 = (__int64)a1;
          if ( v42 )
            sqlite3DbNNFreeNN(*(_QWORD *)(v47 + 16), v47);
        }
        else
        {
          v4 = 7;
        }
      }
      goto LABEL_81;
    }
  }
  if ( *((_QWORD *)v8 + 9) )
    return multiSelectOrderBy(v9, v8, a3);
  if ( !*(_QWORD *)(v6 + 80) )
  {
    sqlite3VdbeExplain(v9, 1, "COMPOUND QUERY");
    sqlite3VdbeExplain(v9, 1, "LEFT-MOST SUBQUERY");
  }
  if ( *v8 == 134 )
    goto LABEL_45;
  if ( *v8 != 135 )
  {
    if ( *v8 != 136 )
    {
      v14 = *(_DWORD *)(v9 + 52);
      memset(&v62[2], 0, 21);
      *(_DWORD *)(v9 + 52) = v14 + 2;
      *(_OWORD *)v62 = 0;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v14, 0, 0);
      for ( i = v8; *((_QWORD *)i + 11); i = (unsigned __int8 *)*((_QWORD *)i + 11) )
        ;
      *((_DWORD *)i + 1) |= 0x20u;
      LOBYTE(v62[0]) = 1;
      HIDWORD(v62[0]) = v14;
      v62[1] = 0;
      v62[3] = 0;
      LODWORD(v62[2]) = 0;
      v4 = sqlite3Select(v9, v6, v62);
      if ( v4 )
        goto LABEL_81;
      v16 = sqlite3VdbeAddOp3(v11, 118, v14 + 1, 0, 0);
      v17 = *v8;
      *((_DWORD *)v8 + 6) = v16;
      v18 = *((_QWORD *)v8 + 12);
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 10) = 0;
      HIDWORD(v62[0]) = v14 + 1;
      v19 = (const char *)sqlite3SelectOpName(v17);
      sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v19);
      v4 = sqlite3Select(v9, v8, v62);
      v58 = *((_QWORD *)v8 + 10);
      *((_QWORD *)v8 + 10) = v6;
      v20 = *(_WORD *)(v6 + 2);
      if ( *((__int16 *)v8 + 1) > v20 )
        *((_WORD *)v8 + 1) = v20;
      if ( *((_QWORD *)v8 + 12) )
        sqlite3ExprDeleteNN(v69);
      *((_QWORD *)v8 + 12) = v18;
      if ( !v4 )
      {
        v21 = *(_DWORD *)(v9 + 68) - 1;
        *(_DWORD *)(v9 + 68) -= 2;
        computeLimitRegisters(v9, (__int64)v8, v21);
        sqlite3VdbeAddOp3(v11, 36, v14, v21, 0);
        v22 = *(_BYTE *)(v9 + 31);
        if ( v22 )
        {
          v24 = v22 - 1;
          *(_BYTE *)(v9 + 31) = v24;
          v23 = *(_DWORD *)(v9 + 4LL * v24 + 224);
        }
        else
        {
          v23 = ++*(_DWORD *)(v9 + 56);
        }
        v67 = sqlite3VdbeAddOp3(v11, 134, v14, v23, 0);
        sqlite3VdbeAddOp4Int(v11, 28, v14 + 1, v21 - 1, v23, 0);
        if ( v23 && *(_BYTE *)(v9 + 31) < 8u )
          *(_DWORD *)(v9 + 4LL * (unsigned __int8)(*(_BYTE *)(v9 + 31))++ + 224) = v23;
        selectInnerLoop(v9, (_DWORD)v8, v14, 0, 0, (__int64)&v59, v21 - 1, v21);
        sqlite3VdbeResolveLabel(v11, v21 - 1);
        sqlite3VdbeAddOp3(v11, 39, v14, v67, 0);
        sqlite3VdbeResolveLabel(v11, v21);
        sqlite3VdbeAddOp3(v11, 122, v14 + 1, 0, 0);
        sqlite3VdbeAddOp3(v11, 122, v14, 0, 0);
      }
LABEL_58:
      v3 = v69;
LABEL_59:
      if ( !*((_QWORD *)v8 + 11) )
        sqlite3VdbeExplainPop(v9);
      goto LABEL_61;
    }
LABEL_45:
    memset(v63, 0, sizeof(v63));
    if ( (_BYTE)v59 == 1 )
    {
      v36 = DWORD1(v59);
      v67 = DWORD1(v59);
    }
    else
    {
      v67 = *(_DWORD *)(v9 + 52);
      v36 = v67;
      *(_DWORD *)(v9 + 52) = v67 + 1;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v36, 0, 0);
      for ( j = v8; *((_QWORD *)j + 11); j = (unsigned __int8 *)*((_QWORD *)j + 11) )
        ;
      *((_DWORD *)j + 1) |= 0x20u;
    }
    v63[0] = 1;
    *(_DWORD *)&v63[4] = v36;
    *(_QWORD *)&v63[8] = 0;
    *(_QWORD *)&v63[24] = 0;
    *(_DWORD *)&v63[16] = 0;
    v4 = sqlite3Select(v9, v6, v63);
    if ( v4 )
      goto LABEL_81;
    v38 = *v8;
    v39 = *((_QWORD *)v8 + 12);
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 12) = 0;
    v63[0] = (v38 == -120) + 1;
    v40 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
    sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v40);
    v41 = sqlite3Select(v9, v8, v63);
    v42 = *v8 == 0x86;
    v4 = v41;
    v58 = *((_QWORD *)v8 + 10);
    *((_QWORD *)v8 + 10) = v6;
    *((_QWORD *)v8 + 9) = 0;
    if ( v42 )
      *((_WORD *)v8 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v8 + 1), *(unsigned __int16 *)(v6 + 2));
    if ( *((_QWORD *)v8 + 12) )
      sqlite3ExprDeleteNN(v3);
    v42 = (_BYTE)v59 == 1;
    *((_QWORD *)v8 + 12) = v39;
    *((_QWORD *)v8 + 1) = 0;
    if ( v42 || *(_BYTE *)(v3 + 103) )
      goto LABEL_59;
    v43 = *(_DWORD *)(v9 + 68) - 1;
    v44 = *(_DWORD *)(v9 + 68) - 2;
    *(_DWORD *)(v9 + 68) = v44;
    computeLimitRegisters(v9, (__int64)v8, v43);
    sqlite3VdbeAddOp3(v11, 36, v67, v43, 0);
    v45 = *(_DWORD *)(v11 + 144);
    selectInnerLoop(v9, (_DWORD)v8, v67, 0, 0, (__int64)&v59, v43 - 1, v43);
    sqlite3VdbeResolveLabel(v11, v44);
    sqlite3VdbeAddOp3(v11, 39, v67, v45, 0);
    sqlite3VdbeResolveLabel(v11, v43);
    sqlite3VdbeAddOp3(v11, 122, v67, 0, 0);
    goto LABEL_58;
  }
  *(_DWORD *)(v6 + 8) = *((_DWORD *)v8 + 2);
  *(_DWORD *)(v6 + 12) = *((_DWORD *)v8 + 3);
  *(_QWORD *)(v6 + 96) = *((_QWORD *)v8 + 12);
  v67 = 0;
  v25 = sqlite3Select(v9, v6, &v59);
  *(_QWORD *)(v6 + 96) = 0;
  v4 = v25;
  if ( !v25 )
  {
    v26 = 0;
    *((_QWORD *)v8 + 10) = 0;
    v27 = *(_DWORD *)(v6 + 8);
    *((_DWORD *)v8 + 2) = v27;
    *((_DWORD *)v8 + 3) = *(_DWORD *)(v6 + 12);
    if ( v27 )
    {
      v26 = sqlite3VdbeAddOp3(v11, 17, v27, 0, 0);
      v28 = *((_DWORD *)v8 + 3);
      if ( v28 )
        sqlite3VdbeAddOp3(v11, 160, *((_DWORD *)v8 + 2), v28 + 1, *((_DWORD *)v8 + 3));
    }
    sqlite3VdbeExplain(v9, 1, "UNION ALL");
    v29 = sqlite3Select(v9, v8, &v59);
    v30 = *((_QWORD *)v8 + 10);
    v4 = v29;
    v31 = *((unsigned __int16 *)v8 + 1);
    *((_QWORD *)v8 + 10) = v6;
    v58 = v30;
    v32 = sqlite3LogEstAdd(v31, *(unsigned __int16 *)(v6 + 2));
    v33 = *((_QWORD *)v8 + 12);
    *((_WORD *)v8 + 1) = v32;
    if ( v33 )
    {
      if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v33 + 16), &v67) )
      {
        if ( v67 > 0 )
        {
          v34 = sqlite3LogEst(v67);
          if ( v35 > v34 )
            *((_WORD *)v8 + 1) = v34;
        }
      }
    }
    if ( v26 )
      sqlite3VdbeJumpHere(v11, v26);
    goto LABEL_59;
  }
LABEL_81:
  v57 = v68;
  *((_DWORD *)v68 + 3) = HIDWORD(v59);
  *((_DWORD *)v57 + 4) = v60;
  if ( v58 )
    sqlite3ParserAddCleanup(v9, sqlite3SelectDelete, v58);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14003a3c4  mov     [rsp-8+arg_10], r8
0x14003a3c9  mov     [rsp-8+arg_0], rcx
0x14003a3ce  push    rbp
0x14003a3cf  push    rbx
0x14003a3d0  push    rsi
0x14003a3d1  push    rdi
0x14003a3d2  push    r12
0x14003a3d4  push    r13
0x14003a3d6  push    r14
0x14003a3d8  push    r15
0x14003a3da  lea     rbp, [rsp-1Fh]
0x14003a3df  sub     rsp, 0D8h
0x14003a3e6  movups  xmm0, xmmword ptr [r8]
0x14003a3ea  mov     rsi, [rcx]
0x14003a3ed  xor     r12d, r12d
0x14003a3f0  movups  xmm1, xmmword ptr [r8+10h]
0x14003a3f5  mov     rbx, [rdx+50h]
0x14003a3f9  mov     rdi, r8
0x14003a3fc  movups  [rbp+57h+var_C8], xmm0
0x14003a400  mov     r14, rdx
0x14003a403  mov     r15, rcx
0x14003a406  movsd   xmm0, qword ptr [r8+20h]
0x14003a40c  movsd   [rbp+57h+var_A8], xmm0
0x14003a411  mov     [rbp+57h+var_D0], r12
0x14003a415  mov     [rbp+57h+arg_18], rsi
0x14003a419  movups  [rbp+57h+var_B8], xmm1
0x14003a41d  call    sqlite3GetVdbe
0x14003a422  cmp     byte ptr [rbp+57h+var_C8], 0Ch
0x14003a426  mov     r13, rax
0x14003a429  mov     [rbp+57h+var_48], rax
0x14003a42d  jnz     short loc_14003A450
0x14003a42f  mov     r9, [r14+20h]
0x14003a433  lea     edx, [r12+76h]
0x14003a438  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x14003a43c  mov     rcx, rax
0x14003a43f  mov     dword ptr [rsp+110h+var_F0], r12d
0x14003a444  mov     r9d, [r9]
0x14003a447  call    sqlite3VdbeAddOp3
0x14003a44c  mov     byte ptr [rbp+57h+var_C8], 0Eh
0x14003a450  test    dword ptr [r14+4], 400h
0x14003a458  jz      short loc_14003A477
0x14003a45a  lea     r8, [rbp+57h+var_C8]
0x14003a45e  mov     rdx, r14
0x14003a461  mov     rcx, r15
0x14003a464  call    multiSelectValues
0x14003a469  mov     r12d, eax
0x14003a46c  test    eax, eax
0x14003a46e  jns     loc_14003AB83
0x14003a474  xor     r12d, r12d
0x14003a477  mov     ecx, 2000h
0x14003a47c  test    [r14+4], ecx
0x14003a480  jz      short loc_14003A4AC
0x14003a482  mov     rax, r14
0x14003a485  test    [rax+4], ecx
0x14003a488  jz      short loc_14003A493
0x14003a48a  mov     rax, [rax+50h]
0x14003a48e  test    rax, rax
0x14003a491  jnz     short loc_14003A485
0x14003a493  test    rax, rax
0x14003a496  jz      short loc_14003A4AC
0x14003a498  lea     r8, [rbp+57h+var_C8]
0x14003a49c  mov     rdx, r14
0x14003a49f  mov     rcx, r15
0x14003a4a2  call    generateWithRecursiveQuery
0x14003a4a7  jmp     loc_14003AA88
0x14003a4ac  cmp     [r14+48h], r12
0x14003a4b0  jz      short loc_14003A4C5
0x14003a4b2  mov     r8, rdi
0x14003a4b5  mov     rdx, r14
0x14003a4b8  mov     rcx, r15
0x14003a4bb  call    multiSelectOrderBy
0x14003a4c0  jmp     loc_14003ABB1
0x14003a4c5  cmp     [rbx+50h], r12
0x14003a4c9  jnz     short loc_14003A4F3
0x14003a4cb  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x14003a4d2  mov     edx, 1
0x14003a4d7  mov     rcx, r15
0x14003a4da  call    sqlite3VdbeExplain
0x14003a4df  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x14003a4e6  mov     edx, 1
0x14003a4eb  mov     rcx, r15
0x14003a4ee  call    sqlite3VdbeExplain
0x14003a4f3  movzx   ecx, byte ptr [r14]
0x14003a4f7  sub     ecx, 86h
0x14003a4fd  jz      loc_14003A881
0x14003a503  sub     ecx, 1
0x14003a506  jz      loc_14003A764
0x14003a50c  cmp     ecx, 1
0x14003a50f  jz      loc_14003A881
0x14003a515  mov     edi, [r15+34h]
0x14003a519  xorps   xmm0, xmm0
0x14003a51c  xor     eax, eax
0x14003a51e  mov     dword ptr [rsp+110h+var_F0], r12d
0x14003a523  xor     r9d, r9d
0x14003a526  mov     r8d, edi
0x14003a529  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14003a52d  mov     qword ptr [rbp+57h+var_90+0Dh], rax
0x14003a531  mov     rcx, r13
0x14003a534  lea     eax, [rdi+2]
0x14003a537  lea     esi, [r9+76h]
0x14003a53b  mov     [r15+34h], eax
0x14003a53f  mov     edx, esi
0x14003a541  movups  [rbp+57h+var_A0], xmm0
0x14003a545  call    sqlite3VdbeAddOp3
0x14003a54a  mov     [r14+14h], eax
0x14003a54e  mov     rax, r14
0x14003a551  cmp     [r14+58h], r12
0x14003a555  jz      short loc_14003A561
0x14003a557  mov     rax, [rax+58h]
0x14003a55b  cmp     [rax+58h], r12
0x14003a55f  jnz     short loc_14003A557
0x14003a561  or      dword ptr [rax+4], 20h
0x14003a565  lea     r8, [rbp+57h+var_A0]
0x14003a569  mov     rdx, rbx
0x14003a56c  mov     byte ptr [rbp+57h+var_A0], 1
0x14003a570  mov     rcx, r15
0x14003a573  mov     dword ptr [rbp+57h+var_A0+4], edi
0x14003a576  mov     qword ptr [rbp+57h+var_A0+8], 0
0x14003a57e  mov     qword ptr [rbp+57h+var_90+8], r12
0x14003a582  mov     dword ptr [rbp+57h+var_90], r12d
0x14003a586  call    sqlite3Select
0x14003a58b  mov     r12d, eax
0x14003a58e  test    eax, eax
0x14003a590  jnz     loc_14003AB83
0x14003a596  lea     r12d, [rdi+1]
0x14003a59a  mov     dword ptr [rsp+110h+var_F0], eax
0x14003a59e  mov     r8d, r12d
0x14003a5a1  xor     r9d, r9d
0x14003a5a4  mov     edx, esi
0x14003a5a6  mov     rcx, r13
0x14003a5a9  call    sqlite3VdbeAddOp3
0x14003a5ae  movzx   ecx, byte ptr [r14]
0x14003a5b2  mov     [r14+18h], eax
0x14003a5b6  mov     rsi, [r14+60h]
0x14003a5ba  mov     qword ptr [r14+60h], 0
0x14003a5c2  mov     qword ptr [r14+50h], 0
0x14003a5ca  mov     dword ptr [rbp+57h+var_A0+4], r12d
0x14003a5ce  call    sqlite3SelectOpName
0x14003a5d3  mov     r9, rax
0x14003a5d6  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x14003a5dd  mov     rcx, r15
0x14003a5e0  mov     edx, 1
0x14003a5e5  call    sqlite3VdbeExplain
0x14003a5ea  lea     r8, [rbp+57h+var_A0]
0x14003a5ee  mov     rdx, r14
0x14003a5f1  mov     rcx, r15
0x14003a5f4  call    sqlite3Select
0x14003a5f9  mov     r12d, eax
0x14003a5fc  mov     rax, [r14+50h]
0x14003a600  mov     [rbp+57h+var_D0], rax
0x14003a604  mov     [r14+50h], rbx
0x14003a608  movzx   eax, word ptr [rbx+2]
0x14003a60c  cmp     [r14+2], ax
0x14003a611  jle     short loc_14003A618
0x14003a613  mov     [r14+2], ax
0x14003a618  mov     rdx, [r14+60h]
0x14003a61c  test    rdx, rdx
0x14003a61f  jz      short loc_14003A62A
0x14003a621  mov     rcx, [rbp+57h+arg_18]
0x14003a625  call    sqlite3ExprDeleteNN
0x14003a62a  mov     [r14+60h], rsi
0x14003a62e  test    r12d, r12d
0x14003a631  jnz     loc_14003AA75
0x14003a637  mov     esi, [r15+44h]
0x14003a63b  mov     rdx, r14
0x14003a63e  dec     esi
0x14003a640  mov     rcx, r15
0x14003a643  mov     r8d, esi
0x14003a646  lea     eax, [rsi-1]
0x14003a649  mov     [r15+44h], eax
0x14003a64d  call    computeLimitRegisters
0x14003a652  mov     r9d, esi
0x14003a655  mov     dword ptr [rsp+110h+var_F0], r12d
0x14003a65a  mov     r8d, edi
0x14003a65d  lea     edx, [r12+24h]
0x14003a662  mov     rcx, r13
0x14003a665  call    sqlite3VdbeAddOp3
0x14003a66a  mov     al, [r15+1Fh]
0x14003a66e  test    al, al
0x14003a670  jnz     short loc_14003A67C
0x14003a672  inc     dword ptr [r15+38h]
0x14003a676  mov     ebx, [r15+38h]
0x14003a67a  jmp     short loc_14003A68D
0x14003a67c  dec     al
0x14003a67e  movzx   eax, al
0x14003a681  mov     [r15+1Fh], al
0x14003a685  mov     ebx, [r15+rax*4+0E0h]
0x14003a68d  mov     r9d, ebx
0x14003a690  mov     dword ptr [rsp+110h+var_F0], 0
0x14003a698  mov     r8d, edi
0x14003a69b  mov     edx, 86h
0x14003a6a0  mov     rcx, r13
0x14003a6a3  call    sqlite3VdbeAddOp3
0x14003a6a8  lea     r9d, [rsi-1]
0x14003a6ac  mov     dword ptr [rsp+110h+var_E8], 0
0x14003a6b4  lea     r8d, [rdi+1]
0x14003a6b8  mov     [rbp+57h+arg_8], eax
0x14003a6bb  mov     edx, 1Ch
0x14003a6c0  mov     dword ptr [rsp+110h+var_F0], ebx
0x14003a6c4  mov     rcx, r13
0x14003a6c7  call    sqlite3VdbeAddOp4Int
0x14003a6cc  test    ebx, ebx
0x14003a6ce  jz      short loc_14003A6E8
0x14003a6d0  cmp     byte ptr [r15+1Fh], 8
0x14003a6d5  jnb     short loc_14003A6E8
0x14003a6d7  movzx   eax, byte ptr [r15+1Fh]
0x14003a6dc  mov     [r15+rax*4+0E0h], ebx
0x14003a6e4  inc     byte ptr [r15+1Fh]
0x14003a6e8  mov     [rsp+110h+var_D8], esi
0x14003a6ec  lea     rax, [rbp+57h+var_C8]
0x14003a6f0  lea     ebx, [rsi-1]
0x14003a6f3  xor     r9d, r9d
0x14003a6f6  mov     [rsp+110h+var_E0], ebx
0x14003a6fa  mov     r8d, edi
0x14003a6fd  mov     [rsp+110h+var_E8], rax
0x14003a702  mov     rdx, r14
0x14003a705  mov     rcx, r15
0x14003a708  mov     [rsp+110h+var_F0], 0
0x14003a711  call    selectInnerLoop
0x14003a716  mov     edx, ebx
0x14003a718  mov     rcx, r13
0x14003a71b  call    sqlite3VdbeResolveLabel
0x14003a720  mov     r9d, [rbp+57h+arg_8]
0x14003a724  xor     ebx, ebx
0x14003a726  mov     r8d, edi
0x14003a729  mov     dword ptr [rsp+110h+var_F0], ebx
0x14003a72d  mov     rcx, r13
0x14003a730  lea     edx, [rbx+27h]
0x14003a733  call    sqlite3VdbeAddOp3
0x14003a738  mov     edx, esi
0x14003a73a  mov     rcx, r13
0x14003a73d  call    sqlite3VdbeResolveLabel
0x14003a742  xor     r9d, r9d
0x14003a745  mov     dword ptr [rsp+110h+var_F0], ebx
0x14003a749  lea     r8d, [rdi+1]
0x14003a74d  mov     rcx, r13
0x14003a750  lea     edx, [rbx+7Ah]
0x14003a753  call    sqlite3VdbeAddOp3
0x14003a758  mov     r8d, edi
0x14003a75b  mov     dword ptr [rsp+110h+var_F0], ebx
0x14003a75f  jmp     loc_14003AA66
0x14003a764  mov     eax, [r14+8]
0x14003a768  lea     r8, [rbp+57h+var_C8]
0x14003a76c  mov     [rbx+8], eax
0x14003a76f  mov     rdx, rbx
0x14003a772  mov     eax, [r14+0Ch]
0x14003a776  mov     rcx, r15
0x14003a779  mov     [rbx+0Ch], eax
0x14003a77c  mov     rax, [r14+60h]
0x14003a780  mov     [rbx+60h], rax
0x14003a784  mov     [rbp+57h+arg_8], r12d
0x14003a788  call    sqlite3Select
0x14003a78d  mov     qword ptr [rbx+60h], 0
0x14003a795  mov     r12d, eax
0x14003a798  test    eax, eax
0x14003a79a  jnz     loc_14003AB83
0x14003a7a0  xor     edi, edi
0x14003a7a2  mov     [r14+50h], rdi
0x14003a7a6  mov     r8d, [rbx+8]
0x14003a7aa  mov     [r14+8], r8d
0x14003a7ae  mov     eax, [rbx+0Ch]
0x14003a7b1  mov     [r14+0Ch], eax
0x14003a7b5  test    r8d, r8d
0x14003a7b8  jz      short loc_14003A7EF
0x14003a7ba  xor     r9d, r9d
0x14003a7bd  mov     dword ptr [rsp+110h+var_F0], edi
0x14003a7c1  lea     edx, [rdi+11h]
0x14003a7c4  mov     rcx, r13
0x14003a7c7  call    sqlite3VdbeAddOp3
0x14003a7cc  mov     edi, eax
0x14003a7ce  mov     eax, [r14+0Ch]
0x14003a7d2  test    eax, eax
0x14003a7d4  jz      short loc_14003A7EF
0x14003a7d6  mov     r8d, [r14+8]
0x14003a7da  lea     r9d, [rax+1]
0x14003a7de  mov     edx, 0A0h
0x14003a7e3  mov     dword ptr [rsp+110h+var_F0], eax
0x14003a7e7  mov     rcx, r13
0x14003a7ea  call    sqlite3VdbeAddOp3
0x14003a7ef  lea     r8, aUnionAll; "UNION ALL"
0x14003a7f6  mov     edx, 1
0x14003a7fb  mov     rcx, r15
0x14003a7fe  call    sqlite3VdbeExplain
0x14003a803  lea     r8, [rbp+57h+var_C8]
0x14003a807  mov     rdx, r14
0x14003a80a  mov     rcx, r15
0x14003a80d  call    sqlite3Select
0x14003a812  mov     r11, [r14+50h]
0x14003a816  mov     r12d, eax
0x14003a819  movzx   ecx, word ptr [r14+2]
0x14003a81e  mov     [r14+50h], rbx
0x14003a822  movzx   edx, word ptr [rbx+2]
0x14003a826  mov     [rbp+57h+var_D0], r11
0x14003a82a  call    sqlite3LogEstAdd
0x14003a82f  mov     rcx, [r14+60h]
0x14003a833  movzx   r10d, ax
0x14003a837  mov     [r14+2], ax
0x14003a83c  test    rcx, rcx
0x14003a83f  jz      short loc_14003A86A
0x14003a841  mov     rcx, [rcx+10h]
  ... truncated ...
```

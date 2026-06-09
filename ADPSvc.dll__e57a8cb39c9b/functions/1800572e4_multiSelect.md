# multiSelect

- ea: `0x1800572e4`
- end: `0x180057ae5`
- name: `multiSelect`
- size: `2049`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18008b73c`

## callees

- `0x18003f548`
- `0x18004a08c`
- `0x1800572e4`
- `0x180057aec`
- `0x180057b50`
- `0x180058500`
- `0x18006554c`
- `0x1800718f8`
- `0x180076d6c`
- `0x1800778dc`
- `0x18007d478`
- `0x18007fc30`
- `0x180080904`
- `0x180080968`
- `0x180084298`
- `0x18008b73c`
- `0x18008da14`
- `0x1800923d8`
- `0x1800924d4`
- `0x1800927e0`
- `0x1800998c0`
- `0x18009995c`
- `0x18009a3b4`
- `0x18009c8f4`

## string_xrefs

- `0x1800573eb`: `COMPOUND QUERY`
- `0x1800574f6`: `%s USING TEMP B-TREE`
- `0x18005785c`: `%s USING TEMP B-TREE`

## pseudocode

```c
__int64 __fastcall multiSelect(_QWORD *a1, unsigned __int8 *a2, __int128 *a3)
{
  __int64 v3; // rsi
  int v4; // r12d
  __int128 v5; // xmm1
  __int64 v6; // rbx
  unsigned __int8 *v8; // r14
  _QWORD *v9; // r15
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
  __int64 v21; // rdx
  unsigned int v22; // esi
  char v23; // al
  int v24; // ebx
  unsigned __int8 v25; // al
  int v26; // eax
  unsigned int v27; // edi
  int v28; // r8d
  int v29; // eax
  int v30; // eax
  __int64 v31; // r11
  __int64 v32; // rcx
  __int16 v33; // ax
  __int64 v34; // rcx
  __int16 v35; // ax
  __int16 v36; // r10
  int v37; // edi
  unsigned __int8 *j; // rax
  char v39; // cl
  __int64 v40; // rdi
  const char *v41; // rax
  int v42; // eax
  bool v43; // zf
  __int64 v44; // rdx
  unsigned int v45; // esi
  unsigned int v46; // edi
  int v47; // ebx
  __int64 v48; // rax
  __int64 v49; // rbx
  int v50; // esi
  __int64 *v51; // rdi
  int v52; // ebx
  __int64 v53; // r13
  __int64 v54; // rax
  int v55; // r15d
  __int64 v56; // rdi
  __int64 v57; // rdx
  __int64 *v58; // rax
  __int128 *v59; // rcx
  __int64 v60; // [rsp+40h] [rbp-79h]
  __int128 v61; // [rsp+48h] [rbp-71h] BYREF
  __int128 v62; // [rsp+58h] [rbp-61h]
  __int64 v63; // [rsp+68h] [rbp-51h]
  _QWORD v64[5]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v65[37]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v66; // [rsp+C0h] [rbp+7h]
  __int64 v67; // [rsp+C8h] [rbp+Fh]
  int v69; // [rsp+128h] [rbp+6Fh] BYREF
  __int128 *v70; // [rsp+130h] [rbp+77h]
  __int64 v71; // [rsp+138h] [rbp+7Fh]

  v70 = a3;
  v3 = *a1;
  v4 = 0;
  v5 = a3[1];
  v6 = *((_QWORD *)a2 + 10);
  v61 = *a3;
  v8 = a2;
  v9 = a1;
  v63 = *((_QWORD *)a3 + 4);
  v60 = 0;
  v71 = v3;
  v62 = v5;
  Vdbe = sqlite3GetVdbe(a1);
  v11 = Vdbe;
  v67 = Vdbe;
  if ( (_BYTE)v61 == 12 )
  {
    sqlite3VdbeAddOp3(Vdbe, 118, DWORD1(v61), **((_DWORD **)v8 + 4), 0);
    LOBYTE(v61) = 14;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x400) != 0 )
  {
    v4 = multiSelectValues(v9, v8, &v61);
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
      generateWithRecursiveQuery(v9, v8, &v61);
LABEL_61:
      if ( !*((_DWORD *)v9 + 12) && (v8[4] & 0x20) != 0 )
      {
        v69 = **((_DWORD **)v8 + 4);
        v48 = sqlite3KeyInfoAlloc(v3, (unsigned int)v69, 1);
        v66 = v48;
        v49 = v48;
        if ( v48 )
        {
          v50 = 0;
          v51 = (__int64 *)(v48 + 32);
          if ( v69 > 0 )
          {
            v52 = v69;
            v53 = v71;
            do
            {
              v54 = multiSelectCollSeq(v9, v8, (unsigned int)v50);
              *v51 = v54;
              if ( !v54 )
                *v51 = *(_QWORD *)(v53 + 16);
              ++v50;
              ++v51;
            }
            while ( v50 < v52 );
            v49 = v66;
            v11 = v67;
          }
          v55 = v69;
          do
          {
            v56 = 0;
            do
            {
              v57 = *(int *)&v8[4 * v56 + 20];
              if ( (int)v57 < 0 )
                break;
              v58 = *(_BYTE *)(*(_QWORD *)v11 + 103LL)
                  ? qword_18010FAB0
                  : (__int64 *)(*(_QWORD *)(v11 + 136) + 24 * v57);
              *((_DWORD *)v58 + 2) = v55;
              ++*(_DWORD *)v49;
              sqlite3VdbeChangeP4(v11, v57, v49, 4294967288LL);
              *(_DWORD *)&v8[4 * v56 + 20] = -1;
              v56 = (unsigned int)(v56 + 1);
            }
            while ( (int)v56 < 2 );
            v8 = (unsigned __int8 *)*((_QWORD *)v8 + 10);
          }
          while ( v8 );
          v43 = (*(_DWORD *)v49)-- == 1;
          v9 = a1;
          if ( v43 )
            sqlite3DbNNFreeNN(*(_QWORD *)(v49 + 16), v49);
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
      v14 = *((_DWORD *)v9 + 13);
      memset(&v64[2], 0, 21);
      *((_DWORD *)v9 + 13) = v14 + 2;
      *(_OWORD *)v64 = 0;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v14, 0, 0);
      for ( i = v8; *((_QWORD *)i + 11); i = (unsigned __int8 *)*((_QWORD *)i + 11) )
        ;
      *((_DWORD *)i + 1) |= 0x20u;
      LOBYTE(v64[0]) = 1;
      HIDWORD(v64[0]) = v14;
      v64[1] = 0;
      v64[3] = 0;
      LODWORD(v64[2]) = 0;
      v4 = sqlite3Select(v9, v6, v64);
      if ( v4 )
        goto LABEL_81;
      v16 = sqlite3VdbeAddOp3(v11, 118, v14 + 1, 0, 0);
      v17 = *v8;
      *((_DWORD *)v8 + 6) = v16;
      v18 = *((_QWORD *)v8 + 12);
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 10) = 0;
      HIDWORD(v64[0]) = v14 + 1;
      v19 = (const char *)sqlite3SelectOpName(v17);
      sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v19);
      v4 = sqlite3Select(v9, v8, v64);
      v60 = *((_QWORD *)v8 + 10);
      *((_QWORD *)v8 + 10) = v6;
      v20 = *(_WORD *)(v6 + 2);
      if ( *((__int16 *)v8 + 1) > v20 )
        *((_WORD *)v8 + 1) = v20;
      v21 = *((_QWORD *)v8 + 12);
      if ( v21 )
        sqlite3ExprDeleteNN(v71, v21);
      *((_QWORD *)v8 + 12) = v18;
      if ( !v4 )
      {
        v22 = *((_DWORD *)v9 + 17) - 1;
        *((_DWORD *)v9 + 17) -= 2;
        computeLimitRegisters(v9, v8, v22);
        sqlite3VdbeAddOp3(v11, 36, v14, v22, 0);
        v23 = *((_BYTE *)v9 + 31);
        if ( v23 )
        {
          v25 = v23 - 1;
          *((_BYTE *)v9 + 31) = v25;
          v24 = *((_DWORD *)v9 + v25 + 58);
        }
        else
        {
          v24 = ++*((_DWORD *)v9 + 14);
        }
        v69 = sqlite3VdbeAddOp3(v11, 134, v14, v24, 0);
        sqlite3VdbeAddOp4Int(v11, 28, v14 + 1, v22 - 1, v24, 0);
        if ( v24 && *((_BYTE *)v9 + 31) < 8u )
          *((_DWORD *)v9 + (unsigned __int8)(*((_BYTE *)v9 + 31))++ + 58) = v24;
        selectInnerLoop((_DWORD)v9, (_DWORD)v8, v14, 0, 0, (__int64)&v61, v22 - 1, v22);
        sqlite3VdbeResolveLabel(v11, v22 - 1);
        sqlite3VdbeAddOp3(v11, 39, v14, v69, 0);
        sqlite3VdbeResolveLabel(v11, v22);
        sqlite3VdbeAddOp3(v11, 122, v14 + 1, 0, 0);
        sqlite3VdbeAddOp3(v11, 122, v14, 0, 0);
      }
LABEL_58:
      v3 = v71;
LABEL_59:
      if ( !*((_QWORD *)v8 + 11) )
        sqlite3VdbeExplainPop(v9);
      goto LABEL_61;
    }
LABEL_45:
    memset(v65, 0, sizeof(v65));
    if ( (_BYTE)v61 == 1 )
    {
      v37 = DWORD1(v61);
      v69 = DWORD1(v61);
    }
    else
    {
      v69 = *((_DWORD *)v9 + 13);
      v37 = v69;
      *((_DWORD *)v9 + 13) = v69 + 1;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v37, 0, 0);
      for ( j = v8; *((_QWORD *)j + 11); j = (unsigned __int8 *)*((_QWORD *)j + 11) )
        ;
      *((_DWORD *)j + 1) |= 0x20u;
    }
    v65[0] = 1;
    *(_DWORD *)&v65[4] = v37;
    *(_QWORD *)&v65[8] = 0;
    *(_QWORD *)&v65[24] = 0;
    *(_DWORD *)&v65[16] = 0;
    v4 = sqlite3Select(v9, v6, v65);
    if ( v4 )
      goto LABEL_81;
    v39 = *v8;
    v40 = *((_QWORD *)v8 + 12);
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 12) = 0;
    v65[0] = (v39 == -120) + 1;
    v41 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
    sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v41);
    v42 = sqlite3Select(v9, v8, v65);
    v43 = *v8 == 0x86;
    v4 = v42;
    v60 = *((_QWORD *)v8 + 10);
    *((_QWORD *)v8 + 10) = v6;
    *((_QWORD *)v8 + 9) = 0;
    if ( v43 )
      *((_WORD *)v8 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v8 + 1), *(unsigned __int16 *)(v6 + 2));
    v44 = *((_QWORD *)v8 + 12);
    if ( v44 )
      sqlite3ExprDeleteNN(v3, v44);
    v43 = (_BYTE)v61 == 1;
    *((_QWORD *)v8 + 12) = v40;
    *((_QWORD *)v8 + 1) = 0;
    if ( v43 || *(_BYTE *)(v3 + 103) )
      goto LABEL_59;
    v45 = *((_DWORD *)v9 + 17) - 1;
    v46 = *((_DWORD *)v9 + 17) - 2;
    *((_DWORD *)v9 + 17) = v46;
    computeLimitRegisters(v9, v8, v45);
    sqlite3VdbeAddOp3(v11, 36, v69, v45, 0);
    v47 = *(_DWORD *)(v11 + 144);
    selectInnerLoop((_DWORD)v9, (_DWORD)v8, v69, 0, 0, (__int64)&v61, v45 - 1, v45);
    sqlite3VdbeResolveLabel(v11, v46);
    sqlite3VdbeAddOp3(v11, 39, v69, v47, 0);
    sqlite3VdbeResolveLabel(v11, v45);
    sqlite3VdbeAddOp3(v11, 122, v69, 0, 0);
    goto LABEL_58;
  }
  *(_DWORD *)(v6 + 8) = *((_DWORD *)v8 + 2);
  *(_DWORD *)(v6 + 12) = *((_DWORD *)v8 + 3);
  *(_QWORD *)(v6 + 96) = *((_QWORD *)v8 + 12);
  v69 = 0;
  v26 = sqlite3Select(v9, v6, &v61);
  *(_QWORD *)(v6 + 96) = 0;
  v4 = v26;
  if ( !v26 )
  {
    v27 = 0;
    *((_QWORD *)v8 + 10) = 0;
    v28 = *(_DWORD *)(v6 + 8);
    *((_DWORD *)v8 + 2) = v28;
    *((_DWORD *)v8 + 3) = *(_DWORD *)(v6 + 12);
    if ( v28 )
    {
      v27 = sqlite3VdbeAddOp3(v11, 17, v28, 0, 0);
      v29 = *((_DWORD *)v8 + 3);
      if ( v29 )
        sqlite3VdbeAddOp3(v11, 160, *((_DWORD *)v8 + 2), v29 + 1, *((_DWORD *)v8 + 3));
    }
    sqlite3VdbeExplain(v9, 1, "UNION ALL");
    v30 = sqlite3Select(v9, v8, &v61);
    v31 = *((_QWORD *)v8 + 10);
    v4 = v30;
    v32 = *((unsigned __int16 *)v8 + 1);
    *((_QWORD *)v8 + 10) = v6;
    v60 = v31;
    v33 = sqlite3LogEstAdd(v32, *(unsigned __int16 *)(v6 + 2));
    v34 = *((_QWORD *)v8 + 12);
    *((_WORD *)v8 + 1) = v33;
    if ( v34 )
    {
      if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v34 + 16), &v69) )
      {
        if ( v69 > 0 )
        {
          v35 = sqlite3LogEst(v69);
          if ( v36 > v35 )
            *((_WORD *)v8 + 1) = v35;
        }
      }
    }
    if ( v27 )
      sqlite3VdbeJumpHere(v11, v27);
    goto LABEL_59;
  }
LABEL_81:
  v59 = v70;
  *((_DWORD *)v70 + 3) = HIDWORD(v61);
  *((_DWORD *)v59 + 4) = v62;
  if ( v60 )
    sqlite3ParserAddCleanup(v9, sqlite3SelectDeleteGeneric, v60);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800572e4  mov     [rsp-8+arg_10], r8
0x1800572e9  mov     [rsp-8+arg_0], rcx
0x1800572ee  push    rbp
0x1800572ef  push    rbx
0x1800572f0  push    rsi
0x1800572f1  push    rdi
0x1800572f2  push    r12
0x1800572f4  push    r13
0x1800572f6  push    r14
0x1800572f8  push    r15
0x1800572fa  lea     rbp, [rsp-1Fh]
0x1800572ff  sub     rsp, 0D8h
0x180057306  movups  xmm0, xmmword ptr [r8]
0x18005730a  mov     rsi, [rcx]
0x18005730d  xor     r12d, r12d
0x180057310  movups  xmm1, xmmword ptr [r8+10h]
0x180057315  mov     rbx, [rdx+50h]
0x180057319  mov     rdi, r8
0x18005731c  movups  [rbp+57h+var_C8], xmm0
0x180057320  mov     r14, rdx
0x180057323  mov     r15, rcx
0x180057326  movsd   xmm0, qword ptr [r8+20h]
0x18005732c  movsd   [rbp+57h+var_A8], xmm0
0x180057331  mov     [rbp+57h+var_D0], r12
0x180057335  mov     [rbp+57h+arg_18], rsi
0x180057339  movups  [rbp+57h+var_B8], xmm1
0x18005733d  call    sqlite3GetVdbe
0x180057342  cmp     byte ptr [rbp+57h+var_C8], 0Ch
0x180057346  mov     r13, rax
0x180057349  mov     [rbp+57h+var_48], rax
0x18005734d  jnz     short loc_180057370
0x18005734f  mov     r9, [r14+20h]
0x180057353  lea     edx, [r12+76h]
0x180057358  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x18005735c  mov     rcx, rax
0x18005735f  mov     dword ptr [rsp+110h+var_F0], r12d
0x180057364  mov     r9d, [r9]
0x180057367  call    sqlite3VdbeAddOp3
0x18005736c  mov     byte ptr [rbp+57h+var_C8], 0Eh
0x180057370  test    dword ptr [r14+4], 400h
0x180057378  jz      short loc_180057397
0x18005737a  lea     r8, [rbp+57h+var_C8]
0x18005737e  mov     rdx, r14
0x180057381  mov     rcx, r15
0x180057384  call    multiSelectValues
0x180057389  mov     r12d, eax
0x18005738c  test    eax, eax
0x18005738e  jns     loc_180057AA3
0x180057394  xor     r12d, r12d
0x180057397  mov     ecx, 2000h
0x18005739c  test    [r14+4], ecx
0x1800573a0  jz      short loc_1800573CC
0x1800573a2  mov     rax, r14
0x1800573a5  test    [rax+4], ecx
0x1800573a8  jz      short loc_1800573B3
0x1800573aa  mov     rax, [rax+50h]
0x1800573ae  test    rax, rax
0x1800573b1  jnz     short loc_1800573A5
0x1800573b3  test    rax, rax
0x1800573b6  jz      short loc_1800573CC
0x1800573b8  lea     r8, [rbp+57h+var_C8]
0x1800573bc  mov     rdx, r14
0x1800573bf  mov     rcx, r15
0x1800573c2  call    generateWithRecursiveQuery
0x1800573c7  jmp     loc_1800579A8
0x1800573cc  cmp     [r14+48h], r12
0x1800573d0  jz      short loc_1800573E5
0x1800573d2  mov     r8, rdi
0x1800573d5  mov     rdx, r14
0x1800573d8  mov     rcx, r15
0x1800573db  call    multiSelectOrderBy
0x1800573e0  jmp     loc_180057AD1
0x1800573e5  cmp     [rbx+50h], r12
0x1800573e9  jnz     short loc_180057413
0x1800573eb  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x1800573f2  mov     edx, 1
0x1800573f7  mov     rcx, r15
0x1800573fa  call    sqlite3VdbeExplain
0x1800573ff  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x180057406  mov     edx, 1
0x18005740b  mov     rcx, r15
0x18005740e  call    sqlite3VdbeExplain
0x180057413  movzx   ecx, byte ptr [r14]
0x180057417  sub     ecx, 86h
0x18005741d  jz      loc_1800577A1
0x180057423  sub     ecx, 1
0x180057426  jz      loc_180057684
0x18005742c  cmp     ecx, 1
0x18005742f  jz      loc_1800577A1
0x180057435  mov     edi, [r15+34h]
0x180057439  xorps   xmm0, xmm0
0x18005743c  xor     eax, eax
0x18005743e  mov     dword ptr [rsp+110h+var_F0], r12d
0x180057443  xor     r9d, r9d
0x180057446  mov     r8d, edi
0x180057449  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005744d  mov     qword ptr [rbp+57h+var_90+0Dh], rax
0x180057451  mov     rcx, r13
0x180057454  lea     eax, [rdi+2]
0x180057457  lea     esi, [r9+76h]
0x18005745b  mov     [r15+34h], eax
0x18005745f  mov     edx, esi
0x180057461  movups  [rbp+57h+var_A0], xmm0
0x180057465  call    sqlite3VdbeAddOp3
0x18005746a  mov     [r14+14h], eax
0x18005746e  mov     rax, r14
0x180057471  cmp     [r14+58h], r12
0x180057475  jz      short loc_180057481
0x180057477  mov     rax, [rax+58h]
0x18005747b  cmp     [rax+58h], r12
0x18005747f  jnz     short loc_180057477
0x180057481  or      dword ptr [rax+4], 20h
0x180057485  lea     r8, [rbp+57h+var_A0]
0x180057489  mov     rdx, rbx
0x18005748c  mov     byte ptr [rbp+57h+var_A0], 1
0x180057490  mov     rcx, r15
0x180057493  mov     dword ptr [rbp+57h+var_A0+4], edi
0x180057496  mov     qword ptr [rbp+57h+var_A0+8], 0
0x18005749e  mov     qword ptr [rbp+57h+var_90+8], r12
0x1800574a2  mov     dword ptr [rbp+57h+var_90], r12d
0x1800574a6  call    sqlite3Select
0x1800574ab  mov     r12d, eax
0x1800574ae  test    eax, eax
0x1800574b0  jnz     loc_180057AA3
0x1800574b6  lea     r12d, [rdi+1]
0x1800574ba  mov     dword ptr [rsp+110h+var_F0], eax
0x1800574be  mov     r8d, r12d
0x1800574c1  xor     r9d, r9d
0x1800574c4  mov     edx, esi
0x1800574c6  mov     rcx, r13
0x1800574c9  call    sqlite3VdbeAddOp3
0x1800574ce  movzx   ecx, byte ptr [r14]
0x1800574d2  mov     [r14+18h], eax
0x1800574d6  mov     rsi, [r14+60h]
0x1800574da  mov     qword ptr [r14+60h], 0
0x1800574e2  mov     qword ptr [r14+50h], 0
0x1800574ea  mov     dword ptr [rbp+57h+var_A0+4], r12d
0x1800574ee  call    sqlite3SelectOpName
0x1800574f3  mov     r9, rax
0x1800574f6  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x1800574fd  mov     rcx, r15
0x180057500  mov     edx, 1
0x180057505  call    sqlite3VdbeExplain
0x18005750a  lea     r8, [rbp+57h+var_A0]
0x18005750e  mov     rdx, r14
0x180057511  mov     rcx, r15
0x180057514  call    sqlite3Select
0x180057519  mov     r12d, eax
0x18005751c  mov     rax, [r14+50h]
0x180057520  mov     [rbp+57h+var_D0], rax
0x180057524  mov     [r14+50h], rbx
0x180057528  movzx   eax, word ptr [rbx+2]
0x18005752c  cmp     [r14+2], ax
0x180057531  jle     short loc_180057538
0x180057533  mov     [r14+2], ax
0x180057538  mov     rdx, [r14+60h]
0x18005753c  test    rdx, rdx
0x18005753f  jz      short loc_18005754A
0x180057541  mov     rcx, [rbp+57h+arg_18]
0x180057545  call    sqlite3ExprDeleteNN
0x18005754a  mov     [r14+60h], rsi
0x18005754e  test    r12d, r12d
0x180057551  jnz     loc_180057995
0x180057557  mov     esi, [r15+44h]
0x18005755b  mov     rdx, r14
0x18005755e  dec     esi
0x180057560  mov     rcx, r15
0x180057563  mov     r8d, esi
0x180057566  lea     eax, [rsi-1]
0x180057569  mov     [r15+44h], eax
0x18005756d  call    computeLimitRegisters
0x180057572  mov     r9d, esi
0x180057575  mov     dword ptr [rsp+110h+var_F0], r12d
0x18005757a  mov     r8d, edi
0x18005757d  lea     edx, [r12+24h]
0x180057582  mov     rcx, r13
0x180057585  call    sqlite3VdbeAddOp3
0x18005758a  mov     al, [r15+1Fh]
0x18005758e  test    al, al
0x180057590  jnz     short loc_18005759C
0x180057592  inc     dword ptr [r15+38h]
0x180057596  mov     ebx, [r15+38h]
0x18005759a  jmp     short loc_1800575AD
0x18005759c  dec     al
0x18005759e  movzx   eax, al
0x1800575a1  mov     [r15+1Fh], al
0x1800575a5  mov     ebx, [r15+rax*4+0E8h]
0x1800575ad  mov     r9d, ebx
0x1800575b0  mov     dword ptr [rsp+110h+var_F0], 0
0x1800575b8  mov     r8d, edi
0x1800575bb  mov     edx, 86h
0x1800575c0  mov     rcx, r13
0x1800575c3  call    sqlite3VdbeAddOp3
0x1800575c8  lea     r9d, [rsi-1]
0x1800575cc  mov     dword ptr [rsp+110h+var_E8], 0
0x1800575d4  lea     r8d, [rdi+1]
0x1800575d8  mov     [rbp+57h+arg_8], eax
0x1800575db  mov     edx, 1Ch
0x1800575e0  mov     dword ptr [rsp+110h+var_F0], ebx
0x1800575e4  mov     rcx, r13
0x1800575e7  call    sqlite3VdbeAddOp4Int
0x1800575ec  test    ebx, ebx
0x1800575ee  jz      short loc_180057608
0x1800575f0  cmp     byte ptr [r15+1Fh], 8
0x1800575f5  jnb     short loc_180057608
0x1800575f7  movzx   eax, byte ptr [r15+1Fh]
0x1800575fc  mov     [r15+rax*4+0E8h], ebx
0x180057604  inc     byte ptr [r15+1Fh]
0x180057608  mov     [rsp+110h+var_D8], esi
0x18005760c  lea     rax, [rbp+57h+var_C8]
0x180057610  lea     ebx, [rsi-1]
0x180057613  xor     r9d, r9d
0x180057616  mov     [rsp+110h+var_E0], ebx
0x18005761a  mov     r8d, edi
0x18005761d  mov     [rsp+110h+var_E8], rax
0x180057622  mov     rdx, r14
0x180057625  mov     rcx, r15
0x180057628  mov     [rsp+110h+var_F0], 0
0x180057631  call    selectInnerLoop
0x180057636  mov     edx, ebx
0x180057638  mov     rcx, r13
0x18005763b  call    sqlite3VdbeResolveLabel
0x180057640  mov     r9d, [rbp+57h+arg_8]
0x180057644  xor     ebx, ebx
0x180057646  mov     r8d, edi
0x180057649  mov     dword ptr [rsp+110h+var_F0], ebx
0x18005764d  mov     rcx, r13
0x180057650  lea     edx, [rbx+27h]
0x180057653  call    sqlite3VdbeAddOp3
0x180057658  mov     edx, esi
0x18005765a  mov     rcx, r13
0x18005765d  call    sqlite3VdbeResolveLabel
0x180057662  xor     r9d, r9d
0x180057665  mov     dword ptr [rsp+110h+var_F0], ebx
0x180057669  lea     r8d, [rdi+1]
0x18005766d  mov     rcx, r13
0x180057670  lea     edx, [rbx+7Ah]
0x180057673  call    sqlite3VdbeAddOp3
0x180057678  mov     r8d, edi
0x18005767b  mov     dword ptr [rsp+110h+var_F0], ebx
0x18005767f  jmp     loc_180057986
0x180057684  mov     eax, [r14+8]
0x180057688  lea     r8, [rbp+57h+var_C8]
0x18005768c  mov     [rbx+8], eax
0x18005768f  mov     rdx, rbx
0x180057692  mov     eax, [r14+0Ch]
0x180057696  mov     rcx, r15
0x180057699  mov     [rbx+0Ch], eax
0x18005769c  mov     rax, [r14+60h]
0x1800576a0  mov     [rbx+60h], rax
0x1800576a4  mov     [rbp+57h+arg_8], r12d
0x1800576a8  call    sqlite3Select
0x1800576ad  mov     qword ptr [rbx+60h], 0
0x1800576b5  mov     r12d, eax
0x1800576b8  test    eax, eax
0x1800576ba  jnz     loc_180057AA3
0x1800576c0  xor     edi, edi
0x1800576c2  mov     [r14+50h], rdi
0x1800576c6  mov     r8d, [rbx+8]
0x1800576ca  mov     [r14+8], r8d
0x1800576ce  mov     eax, [rbx+0Ch]
0x1800576d1  mov     [r14+0Ch], eax
0x1800576d5  test    r8d, r8d
0x1800576d8  jz      short loc_18005770F
0x1800576da  xor     r9d, r9d
0x1800576dd  mov     dword ptr [rsp+110h+var_F0], edi
0x1800576e1  lea     edx, [rdi+11h]
0x1800576e4  mov     rcx, r13
0x1800576e7  call    sqlite3VdbeAddOp3
0x1800576ec  mov     edi, eax
0x1800576ee  mov     eax, [r14+0Ch]
0x1800576f2  test    eax, eax
0x1800576f4  jz      short loc_18005770F
0x1800576f6  mov     r8d, [r14+8]
0x1800576fa  lea     r9d, [rax+1]
0x1800576fe  mov     edx, 0A0h
0x180057703  mov     dword ptr [rsp+110h+var_F0], eax
0x180057707  mov     rcx, r13
0x18005770a  call    sqlite3VdbeAddOp3
0x18005770f  lea     r8, aUnionAll; "UNION ALL"
0x180057716  mov     edx, 1
0x18005771b  mov     rcx, r15
0x18005771e  call    sqlite3VdbeExplain
0x180057723  lea     r8, [rbp+57h+var_C8]
0x180057727  mov     rdx, r14
0x18005772a  mov     rcx, r15
0x18005772d  call    sqlite3Select
0x180057732  mov     r11, [r14+50h]
0x180057736  mov     r12d, eax
0x180057739  movzx   ecx, word ptr [r14+2]
0x18005773e  mov     [r14+50h], rbx
0x180057742  movzx   edx, word ptr [rbx+2]
0x180057746  mov     [rbp+57h+var_D0], r11
0x18005774a  call    sqlite3LogEstAdd
0x18005774f  mov     rcx, [r14+60h]
0x180057753  movzx   r10d, ax
0x180057757  mov     [r14+2], ax
0x18005775c  test    rcx, rcx
0x18005775f  jz      short loc_18005778A
0x180057761  mov     rcx, [rcx+10h]
  ... truncated ...
```

# multiSelect

- ea: `0x180043968`
- end: `0x180044145`
- name: `multiSelect`
- size: `2013`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180037194`

## callees

- `0x18000a530`
- `0x18000c960`
- `0x180010810`
- `0x180011950`
- `0x1800119e0`
- `0x1800128ec`
- `0x180013570`
- `0x1800136e4`
- `0x180014360`
- `0x180036688`
- `0x1800370c0`
- `0x180037194`
- `0x1800399a0`
- `0x18003abcc`
- `0x18003ff00`
- `0x180042230`
- `0x180043968`
- `0x1800443c8`
- `0x18004444c`
- `0x180044460`
- `0x1800444a4`
- `0x180044538`
- `0x18004cfa0`
- `0x180063a58`
- `0x18006536c`
- `0x180070c50`
- `0x18007a5a8`

## string_xrefs

- `0x180043b74`: `%s USING TEMP B-TREE`
- `0x180043eb0`: `%s USING TEMP B-TREE`
- `0x180043a70`: `COMPOUND QUERY`

## pseudocode

```c
__int64 __fastcall multiSelect(_QWORD *a1, unsigned __int8 *a2, __int128 *a3)
{
  __int64 v3; // r14
  int v4; // r13d
  __int128 v5; // xmm1
  __int64 v6; // rbx
  unsigned __int8 *v8; // r15
  _QWORD *v9; // r12
  __int64 Vdbe; // rax
  __int64 v11; // rdi
  unsigned __int8 *v12; // rax
  int v14; // esi
  __int64 v15; // rax
  int v16; // esi
  int v17; // eax
  __int64 v18; // rcx
  const char *v19; // rax
  int v20; // eax
  __int64 v21; // rsi
  __int16 v22; // ax
  unsigned int v23; // r14d
  unsigned int v24; // esi
  unsigned int TempReg; // ebx
  int v26; // edi
  int v27; // ebx
  int v28; // ecx
  int v29; // r9d
  int v30; // r8d
  unsigned int v31; // esi
  int v32; // r8d
  unsigned int v33; // eax
  int v34; // ecx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int16 v38; // ax
  __int64 v39; // rcx
  __int16 v40; // ax
  int v41; // r14d
  __int64 Rightmost; // rax
  char v43; // cl
  __int64 v44; // rsi
  const char *v45; // rax
  int v46; // eax
  bool v47; // zf
  unsigned int v48; // esi
  unsigned int v49; // edi
  int v50; // ebx
  __int64 v51; // rdx
  __int64 v52; // rdx
  int v53; // eax
  __int64 v54; // rax
  __int64 v55; // r14
  int v56; // esi
  __int64 *v57; // rbx
  int v58; // edi
  __int64 v59; // rax
  int v60; // r12d
  __int64 v61; // rbx
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rdx
  __int128 *v65; // rcx
  __int64 v66; // [rsp+40h] [rbp-89h]
  __int64 v67; // [rsp+48h] [rbp-81h]
  __int64 v68; // [rsp+50h] [rbp-79h]
  __int128 v69; // [rsp+58h] [rbp-71h] BYREF
  __int128 v70; // [rsp+68h] [rbp-61h]
  __int64 v71; // [rsp+78h] [rbp-51h]
  _QWORD v72[5]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v73[37]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v74; // [rsp+D0h] [rbp+7h]
  int v76; // [rsp+138h] [rbp+6Fh] BYREF
  __int128 *v77; // [rsp+140h] [rbp+77h]
  __int64 v78; // [rsp+148h] [rbp+7Fh]

  v77 = a3;
  v3 = *a1;
  v4 = 0;
  v5 = a3[1];
  v6 = *((_QWORD *)a2 + 10);
  v69 = *a3;
  v8 = a2;
  v9 = a1;
  v71 = *((_QWORD *)a3 + 4);
  v68 = 0;
  v66 = v3;
  v70 = v5;
  Vdbe = sqlite3GetVdbe(a1);
  v11 = Vdbe;
  v67 = Vdbe;
  if ( (_BYTE)v69 == 12 )
  {
    sqlite3VdbeAddOp3(Vdbe, 117, DWORD1(v69), **((_DWORD **)v8 + 4), 0);
    LOBYTE(v69) = 14;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x400) != 0 )
  {
    v4 = multiSelectValues(v9, v8, &v69);
    if ( v4 >= 0 )
      goto LABEL_71;
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
      generateWithRecursiveQuery(v9, v8, &v69);
LABEL_55:
      if ( !*((_DWORD *)v9 + 13) && (v8[4] & 0x20) != 0 )
      {
        v76 = **((_DWORD **)v8 + 4);
        v54 = sqlite3KeyInfoAlloc(v3, (unsigned int)v76, 1);
        v78 = v54;
        v55 = v54;
        if ( v54 )
        {
          v56 = 0;
          v57 = (__int64 *)(v54 + 32);
          if ( v76 > 0 )
          {
            v58 = v76;
            do
            {
              v59 = multiSelectCollSeq(v9, v8, (unsigned int)v56);
              *v57 = v59;
              if ( !v59 )
                *v57 = *(_QWORD *)(v66 + 16);
              ++v56;
              ++v57;
            }
            while ( v56 < v58 );
            v11 = v67;
            v55 = v78;
          }
          v60 = v76;
          do
          {
            v61 = 0;
            do
            {
              v62 = *(unsigned int *)&v8[4 * v61 + 20];
              if ( (int)v62 < 0 )
                break;
              *(_DWORD *)(sqlite3VdbeGetOp(v11, v62) + 8) = v60;
              v63 = sqlite3KeyInfoRef(v55);
              sqlite3VdbeChangeP4(v11, v64, v63);
              *(_DWORD *)&v8[4 * v61 + 20] = -1;
              v61 = (unsigned int)(v61 + 1);
            }
            while ( (int)v61 < 2 );
            v8 = (unsigned __int8 *)*((_QWORD *)v8 + 10);
          }
          while ( v8 );
          sqlite3KeyInfoUnref(v55);
          v9 = a1;
        }
        else
        {
          v4 = 7;
        }
      }
      goto LABEL_71;
    }
  }
  if ( *((_QWORD *)v8 + 9) )
    return multiSelectOrderBy(v9, v8, a3);
  if ( !*(_QWORD *)(v6 + 80) )
  {
    sqlite3VdbeExplain(v9, 1, "COMPOUND QUERY");
    sqlite3VdbeExplain(v9, 1, "LEFT-MOST SUBQUERY");
  }
  switch ( *v8 )
  {
    case 0x87u:
      goto LABEL_37;
    case 0x88u:
      *(_DWORD *)(v6 + 8) = *((_DWORD *)v8 + 2);
      *(_DWORD *)(v6 + 12) = *((_DWORD *)v8 + 3);
      *(_QWORD *)(v6 + 96) = *((_QWORD *)v8 + 12);
      v76 = 0;
      v4 = sqlite3Select(v9, v6, &v69);
      *(_QWORD *)(v6 + 96) = 0;
      if ( !v4 )
      {
        *((_QWORD *)v8 + 10) = 0;
        v31 = 0;
        v32 = *(_DWORD *)(v6 + 8);
        *((_DWORD *)v8 + 2) = v32;
        *((_DWORD *)v8 + 3) = *(_DWORD *)(v6 + 12);
        if ( v32 )
        {
          v33 = sqlite3VdbeAddOp3(v11, 17, v32, 0, 0);
          v34 = *((_DWORD *)v8 + 3);
          v31 = v33;
          if ( v34 )
            sqlite3VdbeAddOp3(v11, 160, *((_DWORD *)v8 + 2), v34 + 1, v34);
        }
        sqlite3VdbeExplain(v9, 1, "UNION ALL");
        v35 = sqlite3Select(v9, v8, &v69);
        v36 = *((unsigned __int16 *)v8 + 1);
        v4 = v35;
        v37 = *((_QWORD *)v8 + 10);
        *((_QWORD *)v8 + 10) = v6;
        v68 = v37;
        v38 = sqlite3LogEstAdd(v36, *(unsigned __int16 *)(v6 + 2));
        v39 = *((_QWORD *)v8 + 12);
        *((_WORD *)v8 + 1) = v38;
        if ( v39 )
        {
          if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v39 + 16), &v76, v9) )
          {
            if ( v76 > 0 )
            {
              v40 = sqlite3LogEst(v76);
              if ( *((__int16 *)v8 + 1) > v40 )
                *((_WORD *)v8 + 1) = v40;
            }
          }
        }
        if ( v31 )
          *(_DWORD *)(sqlite3VdbeGetOp(v11, v31) + 8) = *(_DWORD *)(v11 + 144);
        goto LABEL_50;
      }
      break;
    case 0x89u:
LABEL_37:
      memset(v73, 0, sizeof(v73));
      if ( (_BYTE)v69 == 1 )
      {
        v41 = DWORD1(v69);
      }
      else
      {
        v41 = *((_DWORD *)v9 + 14);
        *((_DWORD *)v9 + 14) = v41 + 1;
        *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 117, v41, 0, 0);
        Rightmost = findRightmost(v8);
        *(_DWORD *)(Rightmost + 4) |= 0x20u;
      }
      v73[0] = 1;
      *(_DWORD *)&v73[4] = v41;
      *(_QWORD *)&v73[8] = 0;
      *(_QWORD *)&v73[24] = 0;
      *(_DWORD *)&v73[16] = 0;
      v4 = sqlite3Select(v9, v6, v73);
      if ( !v4 )
      {
        v43 = *v8;
        v44 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 10) = 0;
        *((_QWORD *)v8 + 12) = 0;
        v73[0] = (v43 == -119) + 1;
        v45 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v45);
        v46 = sqlite3Select(v9, v8, v73);
        v47 = *v8 == 0x87;
        v4 = v46;
        v68 = *((_QWORD *)v8 + 10);
        *((_QWORD *)v8 + 10) = v6;
        *((_QWORD *)v8 + 9) = 0;
        if ( v47 )
          *((_WORD *)v8 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v8 + 1), *(unsigned __int16 *)(v6 + 2));
        if ( *((_QWORD *)v8 + 12) )
          sqlite3ExprDeleteNN(v66);
        *((_QWORD *)v8 + 12) = v44;
        v47 = (_BYTE)v69 == 1;
        *((_QWORD *)v8 + 1) = 0;
        if ( v47 || *(_BYTE *)(v66 + 103) )
          goto LABEL_49;
        v48 = *((_DWORD *)v9 + 18) - 1;
        v49 = *((_DWORD *)v9 + 18) - 2;
        *((_DWORD *)v9 + 18) = v49;
        computeLimitRegisters(v9, v8, v48);
        sqlite3VdbeAddOp3(v67, 36, v41, v48, 0);
        v50 = *(_DWORD *)(v67 + 144);
        selectInnerLoop((_DWORD)v9, (_DWORD)v8, v41, 0, 0, (__int64)&v69, v48 - 1, v48);
        v51 = v49;
        v11 = v67;
        sqlite3VdbeResolveLabel(v67, v51);
        sqlite3VdbeAddOp3(v67, 39, v41, v50, 0);
        sqlite3VdbeResolveLabel(v67, v48);
        v30 = v41;
LABEL_48:
        sqlite3VdbeAddOp3(v11, 122, v30, 0, 0);
LABEL_49:
        v3 = v66;
LABEL_50:
        if ( !*((_QWORD *)v8 + 11) )
        {
          v52 = *((unsigned int *)v9 + 80);
          if ( (_DWORD)v52 )
            v53 = *(_DWORD *)(sqlite3VdbeGetOp(v9[2], v52) + 8);
          else
            v53 = 0;
          *((_DWORD *)v9 + 80) = v53;
        }
        goto LABEL_55;
      }
      break;
    default:
      v14 = *((_DWORD *)v9 + 14);
      v76 = v14;
      memset(&v72[2], 0, 21);
      *((_DWORD *)v9 + 14) = v14 + 2;
      *(_OWORD *)v72 = 0;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 117, v14, 0, 0);
      v15 = findRightmost(v8);
      *(_DWORD *)(v15 + 4) |= 0x20u;
      LOBYTE(v72[0]) = 1;
      HIDWORD(v72[0]) = v14;
      v72[1] = 0;
      v72[3] = 0;
      LODWORD(v72[2]) = 0;
      v4 = sqlite3Select(v9, v6, v72);
      if ( !v4 )
      {
        v16 = v14 + 1;
        LODWORD(v78) = v16;
        v17 = sqlite3VdbeAddOp3(v11, 117, v16, 0, 0);
        v18 = *v8;
        *((_DWORD *)v8 + 6) = v17;
        v74 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 10) = 0;
        *((_QWORD *)v8 + 12) = 0;
        HIDWORD(v72[0]) = v16;
        v19 = (const char *)sqlite3SelectOpName(v18);
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v19);
        v20 = sqlite3Select(v9, v8, v72);
        v21 = *((_QWORD *)v8 + 10);
        v4 = v20;
        *((_QWORD *)v8 + 10) = v6;
        v22 = *(_WORD *)(v6 + 2);
        v68 = v21;
        if ( *((__int16 *)v8 + 1) > v22 )
          *((_WORD *)v8 + 1) = v22;
        if ( *((_QWORD *)v8 + 12) )
          sqlite3ExprDeleteNN(v3);
        *((_QWORD *)v8 + 12) = v74;
        if ( v4 )
          goto LABEL_50;
        v23 = *((_DWORD *)v9 + 18) - 1;
        v24 = *((_DWORD *)v9 + 18) - 2;
        *((_DWORD *)v9 + 18) = v24;
        computeLimitRegisters(v9, v8, v23);
        sqlite3VdbeAddOp3(v11, 36, v76, v23, 0);
        TempReg = sqlite3GetTempReg(v9);
        v26 = sqlite3VdbeAddOp3(v11, 134, v76, TempReg, 0);
        sqlite3VdbeAddOp4Int(v67, 28, v78, v24, TempReg, 0);
        sqlite3ReleaseTempReg(v9, TempReg);
        v27 = v76;
        selectInnerLoop(v28, (_DWORD)v8, v76, 0, 0, (__int64)&v69, v23 - 1, v23);
        sqlite3VdbeResolveLabel(v67, v24);
        v29 = v26;
        v11 = v67;
        sqlite3VdbeAddOp3(v67, 39, v27, v29, 0);
        sqlite3VdbeResolveLabel(v67, v23);
        sqlite3VdbeAddOp3(v67, 122, v27 + 1, 0, 0);
        v30 = v27;
        goto LABEL_48;
      }
      break;
  }
LABEL_71:
  v65 = v77;
  *((_DWORD *)v77 + 3) = HIDWORD(v69);
  *((_DWORD *)v65 + 4) = v70;
  if ( v68 )
    sqlite3ParserAddCleanup(v9, sqlite3SelectDeleteGeneric, v68);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180043968  mov     [rsp-8+arg_10], r8
0x18004396d  mov     [rsp-8+arg_0], rcx
0x180043972  push    rbp
0x180043973  push    rbx
0x180043974  push    rsi
0x180043975  push    rdi
0x180043976  push    r12
0x180043978  push    r13
0x18004397a  push    r14
0x18004397c  push    r15
0x18004397e  lea     rbp, [rsp-1Fh]
0x180043983  sub     rsp, 0E8h
0x18004398a  movups  xmm0, xmmword ptr [r8]
0x18004398e  mov     r14, [rcx]
0x180043991  xor     r13d, r13d
0x180043994  movups  xmm1, xmmword ptr [r8+10h]
0x180043999  mov     rbx, [rdx+50h]
0x18004399d  mov     rsi, r8
0x1800439a0  movups  [rbp+57h+var_C8], xmm0
0x1800439a4  mov     r15, rdx
0x1800439a7  mov     r12, rcx
0x1800439aa  movsd   xmm0, qword ptr [r8+20h]
0x1800439b0  movsd   [rbp+57h+var_A8], xmm0
0x1800439b5  mov     [rbp+57h+var_D0], r13
0x1800439b9  mov     [rsp+120h+var_E0], r14
0x1800439be  movups  [rbp+57h+var_B8], xmm1
0x1800439c2  call    sqlite3GetVdbe
0x1800439c7  cmp     byte ptr [rbp+57h+var_C8], 0Ch
0x1800439cb  mov     rdi, rax
0x1800439ce  mov     [rsp+120h+var_D8], rax
0x1800439d3  jnz     short loc_1800439F5
0x1800439d5  mov     r9, [r15+20h]
0x1800439d9  lea     edx, [r13+75h]
0x1800439dd  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x1800439e1  mov     rcx, rax
0x1800439e4  mov     dword ptr [rsp+120h+var_100], r13d
0x1800439e9  mov     r9d, [r9]
0x1800439ec  call    sqlite3VdbeAddOp3
0x1800439f1  mov     byte ptr [rbp+57h+var_C8], 0Eh
0x1800439f5  test    dword ptr [r15+4], 400h
0x1800439fd  jz      short loc_180043A1C
0x1800439ff  lea     r8, [rbp+57h+var_C8]
0x180043a03  mov     rdx, r15
0x180043a06  mov     rcx, r12
0x180043a09  call    multiSelectValues
0x180043a0e  mov     r13d, eax
0x180043a11  test    eax, eax
0x180043a13  jns     loc_180044103
0x180043a19  xor     r13d, r13d
0x180043a1c  mov     ecx, 2000h
0x180043a21  test    [r15+4], ecx
0x180043a25  jz      short loc_180043A51
0x180043a27  mov     rax, r15
0x180043a2a  test    [rax+4], ecx
0x180043a2d  jz      short loc_180043A38
0x180043a2f  mov     rax, [rax+50h]
0x180043a33  test    rax, rax
0x180043a36  jnz     short loc_180043A2A
0x180043a38  test    rax, rax
0x180043a3b  jz      short loc_180043A51
0x180043a3d  lea     r8, [rbp+57h+var_C8]
0x180043a41  mov     rdx, r15
0x180043a44  mov     rcx, r12
0x180043a47  call    generateWithRecursiveQuery
0x180043a4c  jmp     loc_180044022
0x180043a51  cmp     [r15+48h], r13
0x180043a55  jz      short loc_180043A6A
0x180043a57  mov     r8, rsi
0x180043a5a  mov     rdx, r15
0x180043a5d  mov     rcx, r12
0x180043a60  call    multiSelectOrderBy
0x180043a65  jmp     loc_180044131
0x180043a6a  cmp     [rbx+50h], r13
0x180043a6e  jnz     short loc_180043A98
0x180043a70  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x180043a77  mov     edx, 1
0x180043a7c  mov     rcx, r12
0x180043a7f  call    sqlite3VdbeExplain
0x180043a84  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x180043a8b  mov     edx, 1
0x180043a90  mov     rcx, r12
0x180043a93  call    sqlite3VdbeExplain
0x180043a98  movzx   ecx, byte ptr [r15]
0x180043a9c  sub     ecx, 87h
0x180043aa2  jz      loc_180043E01
0x180043aa8  sub     ecx, 1
0x180043aab  jz      loc_180043CDA
0x180043ab1  cmp     ecx, 1
0x180043ab4  jz      loc_180043E01
0x180043aba  mov     esi, [r12+38h]
0x180043abf  xorps   xmm0, xmm0
0x180043ac2  xor     eax, eax
0x180043ac4  mov     [rbp+57h+arg_8], esi
0x180043ac7  xor     r9d, r9d
0x180043aca  mov     dword ptr [rsp+120h+var_100], r13d
0x180043acf  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180043ad3  mov     qword ptr [rbp+57h+var_90+0Dh], rax
0x180043ad7  mov     r8d, esi
0x180043ada  lea     eax, [rsi+2]
0x180043add  mov     rcx, rdi
0x180043ae0  lea     edx, [r9+75h]
0x180043ae4  mov     [r12+38h], eax
0x180043ae9  movups  [rbp+57h+var_A0], xmm0
0x180043aed  call    sqlite3VdbeAddOp3
0x180043af2  mov     rcx, r15
0x180043af5  mov     [r15+14h], eax
0x180043af9  call    findRightmost
0x180043afe  lea     r8, [rbp+57h+var_A0]
0x180043b02  mov     rdx, rbx
0x180043b05  mov     rcx, r12
0x180043b08  or      dword ptr [rax+4], 20h
0x180043b0c  mov     byte ptr [rbp+57h+var_A0], 1
0x180043b10  mov     dword ptr [rbp+57h+var_A0+4], esi
0x180043b13  mov     qword ptr [rbp+57h+var_A0+8], 0
0x180043b1b  mov     qword ptr [rbp+57h+var_90+8], r13
0x180043b1f  mov     dword ptr [rbp+57h+var_90], r13d
0x180043b23  call    sqlite3Select
0x180043b28  mov     r13d, eax
0x180043b2b  test    eax, eax
0x180043b2d  jnz     loc_180044103
0x180043b33  inc     esi
0x180043b35  lea     edx, [rax+75h]
0x180043b38  xor     r13d, r13d
0x180043b3b  mov     dword ptr [rbp+57h+arg_18], esi
0x180043b3e  mov     r8d, esi
0x180043b41  mov     dword ptr [rsp+120h+var_100], r13d
0x180043b46  xor     r9d, r9d
0x180043b49  mov     rcx, rdi
0x180043b4c  call    sqlite3VdbeAddOp3
0x180043b51  movzx   ecx, byte ptr [r15]
0x180043b55  mov     [r15+18h], eax
0x180043b59  mov     rax, [r15+60h]
0x180043b5d  mov     [rbp+57h+var_50], rax
0x180043b61  mov     [r15+50h], r13
0x180043b65  mov     [r15+60h], r13
0x180043b69  mov     dword ptr [rbp+57h+var_A0+4], esi
0x180043b6c  call    sqlite3SelectOpName
0x180043b71  mov     r9, rax
0x180043b74  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x180043b7b  mov     rcx, r12
0x180043b7e  lea     edx, [r13+1]
0x180043b82  call    sqlite3VdbeExplain
0x180043b87  lea     r8, [rbp+57h+var_A0]
0x180043b8b  mov     rdx, r15
0x180043b8e  mov     rcx, r12
0x180043b91  call    sqlite3Select
0x180043b96  mov     rsi, [r15+50h]
0x180043b9a  mov     r13d, eax
0x180043b9d  mov     [r15+50h], rbx
0x180043ba1  movzx   eax, word ptr [rbx+2]
0x180043ba5  mov     [rbp+57h+var_D0], rsi
0x180043ba9  cmp     [r15+2], ax
0x180043bae  jle     short loc_180043BB5
0x180043bb0  mov     [r15+2], ax
0x180043bb5  mov     rdx, [r15+60h]
0x180043bb9  test    rdx, rdx
0x180043bbc  jz      short loc_180043BC6
0x180043bbe  mov     rcx, r14
0x180043bc1  call    sqlite3ExprDeleteNN
0x180043bc6  mov     rax, [rbp+57h+var_50]
0x180043bca  mov     [r15+60h], rax
0x180043bce  test    r13d, r13d
0x180043bd1  jnz     loc_180043FF6
0x180043bd7  mov     r14d, [r12+48h]
0x180043bdc  mov     rdx, r15
0x180043bdf  dec     r14d
0x180043be2  mov     rcx, r12
0x180043be5  mov     r8d, r14d
0x180043be8  lea     esi, [r14-1]
0x180043bec  mov     [r12+48h], esi
0x180043bf1  call    computeLimitRegisters
0x180043bf6  mov     r8d, [rbp+57h+arg_8]
0x180043bfa  lea     edx, [r13+24h]
0x180043bfe  mov     r9d, r14d
0x180043c01  mov     dword ptr [rsp+120h+var_100], r13d
0x180043c06  mov     rcx, rdi
0x180043c09  call    sqlite3VdbeAddOp3
0x180043c0e  mov     rcx, r12
0x180043c11  call    sqlite3GetTempReg
0x180043c16  mov     r8d, [rbp+57h+arg_8]
0x180043c1a  mov     r9d, eax
0x180043c1d  mov     edx, 86h
0x180043c22  mov     dword ptr [rsp+120h+var_100], r13d
0x180043c27  mov     rcx, rdi
0x180043c2a  mov     ebx, eax
0x180043c2c  call    sqlite3VdbeAddOp3
0x180043c31  mov     r8d, dword ptr [rbp+57h+arg_18]
0x180043c35  lea     edx, [r13+1Ch]
0x180043c39  mov     rcx, [rsp+120h+var_D8]
0x180043c3e  mov     r9d, esi
0x180043c41  mov     dword ptr [rsp+120h+var_F8], r13d
0x180043c46  mov     edi, eax
0x180043c48  mov     dword ptr [rsp+120h+var_100], ebx
0x180043c4c  call    sqlite3VdbeAddOp4Int
0x180043c51  mov     edx, ebx
0x180043c53  mov     rcx, r12
0x180043c56  call    sqlite3ReleaseTempReg
0x180043c5b  mov     ebx, [rbp+57h+arg_8]
0x180043c5e  lea     rax, [rbp+57h+var_C8]
0x180043c62  mov     [rsp+120h+var_E8], r14d
0x180043c67  xor     r9d, r9d
0x180043c6a  mov     [rsp+120h+var_F0], esi
0x180043c6e  mov     r8d, ebx
0x180043c71  mov     [rsp+120h+var_F8], rax
0x180043c76  mov     rdx, r15
0x180043c79  mov     [rsp+120h+var_100], 0
0x180043c82  call    selectInnerLoop
0x180043c87  mov     rcx, [rsp+120h+var_D8]
0x180043c8c  mov     edx, esi
0x180043c8e  call    sqlite3VdbeResolveLabel
0x180043c93  mov     r9d, edi
0x180043c96  mov     dword ptr [rsp+120h+var_100], r13d
0x180043c9b  mov     rdi, [rsp+120h+var_D8]
0x180043ca0  lea     edx, [r13+27h]
0x180043ca4  mov     rcx, rdi
0x180043ca7  mov     r8d, ebx
0x180043caa  call    sqlite3VdbeAddOp3
0x180043caf  mov     edx, r14d
0x180043cb2  mov     rcx, rdi
0x180043cb5  call    sqlite3VdbeResolveLabel
0x180043cba  xor     r9d, r9d
0x180043cbd  mov     dword ptr [rsp+120h+var_100], r13d
0x180043cc2  lea     r8d, [rbx+1]
0x180043cc6  mov     rcx, rdi
0x180043cc9  lea     edx, [r13+7Ah]
0x180043ccd  call    sqlite3VdbeAddOp3
0x180043cd2  mov     r8d, ebx
0x180043cd5  jmp     loc_180043FDA
0x180043cda  mov     eax, [r15+8]
0x180043cde  lea     r8, [rbp+57h+var_C8]
0x180043ce2  mov     [rbx+8], eax
0x180043ce5  mov     rdx, rbx
0x180043ce8  mov     eax, [r15+0Ch]
0x180043cec  mov     rcx, r12
0x180043cef  mov     [rbx+0Ch], eax
0x180043cf2  mov     rax, [r15+60h]
0x180043cf6  mov     [rbx+60h], rax
0x180043cfa  mov     [rbp+57h+arg_8], r13d
0x180043cfe  call    sqlite3Select
0x180043d03  xor     ecx, ecx
0x180043d05  mov     r13d, eax
0x180043d08  mov     [rbx+60h], rcx
0x180043d0c  test    eax, eax
0x180043d0e  jnz     loc_180044103
0x180043d14  mov     [r15+50h], rcx
0x180043d18  mov     esi, ecx
0x180043d1a  mov     r8d, [rbx+8]
0x180043d1e  mov     [r15+8], r8d
0x180043d22  mov     eax, [rbx+0Ch]
0x180043d25  mov     [r15+0Ch], eax
0x180043d29  test    r8d, r8d
0x180043d2c  jz      short loc_180043D63
0x180043d2e  mov     dword ptr [rsp+120h+var_100], ecx
0x180043d32  lea     edx, [rcx+11h]
0x180043d35  mov     rcx, rdi
0x180043d38  xor     r9d, r9d
0x180043d3b  call    sqlite3VdbeAddOp3
0x180043d40  mov     ecx, [r15+0Ch]
0x180043d44  mov     esi, eax
0x180043d46  test    ecx, ecx
0x180043d48  jz      short loc_180043D63
0x180043d4a  mov     r8d, [r15+8]
0x180043d4e  lea     r9d, [rcx+1]
0x180043d52  mov     dword ptr [rsp+120h+var_100], ecx
0x180043d56  mov     edx, 0A0h
0x180043d5b  mov     rcx, rdi
0x180043d5e  call    sqlite3VdbeAddOp3
0x180043d63  lea     r8, aUnionAll; "UNION ALL"
0x180043d6a  mov     edx, 1
0x180043d6f  mov     rcx, r12
0x180043d72  call    sqlite3VdbeExplain
0x180043d77  lea     r8, [rbp+57h+var_C8]
0x180043d7b  mov     rdx, r15
0x180043d7e  mov     rcx, r12
0x180043d81  call    sqlite3Select
0x180043d86  movzx   ecx, word ptr [r15+2]
0x180043d8b  mov     r13d, eax
0x180043d8e  mov     rax, [r15+50h]
0x180043d92  mov     [r15+50h], rbx
0x180043d96  movzx   edx, word ptr [rbx+2]
0x180043d9a  mov     [rbp+57h+var_D0], rax
0x180043d9e  call    sqlite3LogEstAdd
0x180043da3  mov     rcx, [r15+60h]
0x180043da7  mov     [r15+2], ax
0x180043dac  test    rcx, rcx
0x180043daf  jz      short loc_180043DE1
0x180043db1  mov     rcx, [rcx+10h]
0x180043db5  lea     rdx, [rbp+57h+arg_8]
0x180043db9  mov     r8, r12
0x180043dbc  call    sqlite3ExprIsInteger
0x180043dc1  test    eax, eax
0x180043dc3  jz      short loc_180043DE1
0x180043dc5  movsxd  rax, [rbp+57h+arg_8]
0x180043dc9  test    eax, eax
0x180043dcb  jle     short loc_180043DE1
0x180043dcd  mov     rcx, rax
0x180043dd0  call    sqlite3LogEst
0x180043dd5  cmp     [r15+2], ax
0x180043dda  jle     short loc_180043DE1
0x180043ddc  mov     [r15+2], ax
  ... truncated ...
```

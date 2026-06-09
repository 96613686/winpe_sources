# multiSelect

- ea: `0x180040990`
- end: `0x180041173`
- name: `multiSelect`
- size: `2019`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180008860`

## callees

- `0x180007fcc`
- `0x180008860`
- `0x18000b4bc`
- `0x18000b544`
- `0x180015e80`
- `0x180036354`
- `0x1800364e0`
- `0x180038974`
- `0x18003b520`
- `0x18003bf64`
- `0x18003bff4`
- `0x18003d480`
- `0x1800400d8`
- `0x180040990`
- `0x180041574`
- `0x18005a038`
- `0x18005f730`
- `0x1800620a0`
- `0x18006ccc0`
- `0x18006ce2c`
- `0x180080a50`
- `0x180083968`
- `0x1800857b8`
- `0x180088718`
- `0x18008982c`
- `0x18008ac04`
- `0x18008d4bc`

## string_xrefs

- `0x180040a98`: `COMPOUND QUERY`
- `0x180040ba0`: `%s USING TEMP B-TREE`
- `0x180040eec`: `%s USING TEMP B-TREE`

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
  int v30; // eax
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
  __int16 v41; // r10
  int v42; // r14d
  __int64 Rightmost; // rax
  char v44; // cl
  __int64 v45; // rsi
  const char *v46; // rax
  int v47; // eax
  bool v48; // zf
  unsigned int v49; // esi
  unsigned int v50; // edi
  int v51; // ebx
  __int64 v52; // rdx
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // r14
  int v57; // esi
  __int64 *v58; // rbx
  int v59; // edi
  __int64 v60; // rax
  int v61; // r12d
  __int64 v62; // rbx
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int128 *v66; // rcx
  __int64 v67; // [rsp+40h] [rbp-89h]
  __int64 v68; // [rsp+48h] [rbp-81h]
  __int64 v69; // [rsp+50h] [rbp-79h]
  __int128 v70; // [rsp+58h] [rbp-71h] BYREF
  __int128 v71; // [rsp+68h] [rbp-61h]
  __int64 v72; // [rsp+78h] [rbp-51h]
  _QWORD v73[5]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v74[37]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v75; // [rsp+D0h] [rbp+7h]
  int v77; // [rsp+138h] [rbp+6Fh] BYREF
  __int128 *v78; // [rsp+140h] [rbp+77h]
  __int64 v79; // [rsp+148h] [rbp+7Fh]

  v78 = a3;
  v3 = *a1;
  v4 = 0;
  v5 = a3[1];
  v6 = *((_QWORD *)a2 + 10);
  v70 = *a3;
  v8 = a2;
  v9 = a1;
  v72 = *((_QWORD *)a3 + 4);
  v69 = 0;
  v67 = v3;
  v71 = v5;
  Vdbe = sqlite3GetVdbe(a1);
  v11 = Vdbe;
  v68 = Vdbe;
  if ( (_BYTE)v70 == 12 )
  {
    sqlite3VdbeAddOp3(Vdbe, 118, DWORD1(v70), **((_DWORD **)v8 + 4), 0);
    LOBYTE(v70) = 14;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x400) != 0 )
  {
    v4 = multiSelectValues(v9, v8, &v70);
    if ( v4 >= 0 )
      goto LABEL_67;
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
      generateWithRecursiveQuery(v9, v8, &v70);
LABEL_51:
      if ( !*((_DWORD *)v9 + 12) && (v8[4] & 0x20) != 0 )
      {
        v77 = **((_DWORD **)v8 + 4);
        v55 = sqlite3KeyInfoAlloc(v3, (unsigned int)v77, 1);
        v79 = v55;
        v56 = v55;
        if ( v55 )
        {
          v57 = 0;
          v58 = (__int64 *)(v55 + 32);
          if ( v77 > 0 )
          {
            v59 = v77;
            do
            {
              v60 = multiSelectCollSeq(v9, v8, (unsigned int)v57);
              *v58 = v60;
              if ( !v60 )
                *v58 = *(_QWORD *)(v67 + 16);
              ++v57;
              ++v58;
            }
            while ( v57 < v59 );
            v11 = v68;
            v56 = v79;
          }
          v61 = v77;
          do
          {
            v62 = 0;
            do
            {
              v63 = *(unsigned int *)&v8[4 * v62 + 20];
              if ( (int)v63 < 0 )
                break;
              *(_DWORD *)(sqlite3VdbeGetOp(v11, v63) + 8) = v61;
              v64 = sqlite3KeyInfoRef(v56);
              sqlite3VdbeChangeP4(v11, v65, v64);
              *(_DWORD *)&v8[4 * v62 + 20] = -1;
              v62 = (unsigned int)(v62 + 1);
            }
            while ( (int)v62 < 2 );
            v8 = (unsigned __int8 *)*((_QWORD *)v8 + 10);
          }
          while ( v8 );
          sqlite3KeyInfoUnref(v56);
          v9 = a1;
        }
        else
        {
          v4 = 7;
        }
      }
      goto LABEL_67;
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
    case 0x86u:
      goto LABEL_36;
    case 0x87u:
      *(_DWORD *)(v6 + 8) = *((_DWORD *)v8 + 2);
      *(_DWORD *)(v6 + 12) = *((_DWORD *)v8 + 3);
      *(_QWORD *)(v6 + 96) = *((_QWORD *)v8 + 12);
      v77 = 0;
      v30 = sqlite3Select(v9, v6, &v70);
      *(_QWORD *)(v6 + 96) = 0;
      v4 = v30;
      if ( !v30 )
      {
        v31 = 0;
        *((_QWORD *)v8 + 10) = 0;
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
        v35 = sqlite3Select(v9, v8, &v70);
        v36 = *((unsigned __int16 *)v8 + 1);
        v4 = v35;
        v37 = *((_QWORD *)v8 + 10);
        *((_QWORD *)v8 + 10) = v6;
        v69 = v37;
        v38 = sqlite3LogEstAdd(v36, *(unsigned __int16 *)(v6 + 2));
        v39 = *((_QWORD *)v8 + 12);
        *((_WORD *)v8 + 1) = v38;
        if ( v39 )
        {
          if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v39 + 16), &v77) )
          {
            if ( v77 > 0 )
            {
              v40 = sqlite3LogEst(v77);
              if ( v41 > v40 )
                *((_WORD *)v8 + 1) = v40;
            }
          }
        }
        if ( v31 )
          *(_DWORD *)(sqlite3VdbeGetOp(v11, v31) + 8) = *(_DWORD *)(v11 + 144);
        goto LABEL_46;
      }
      break;
    case 0x88u:
LABEL_36:
      memset(v74, 0, sizeof(v74));
      if ( (_BYTE)v70 == 1 )
      {
        v42 = DWORD1(v70);
      }
      else
      {
        v42 = *((_DWORD *)v9 + 13);
        *((_DWORD *)v9 + 13) = v42 + 1;
        *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v42, 0, 0);
        Rightmost = findRightmost(v8);
        *(_DWORD *)(Rightmost + 4) |= 0x20u;
      }
      v74[0] = 1;
      *(_DWORD *)&v74[4] = v42;
      *(_QWORD *)&v74[8] = 0;
      *(_QWORD *)&v74[24] = 0;
      *(_DWORD *)&v74[16] = 0;
      v4 = sqlite3Select(v9, v6, v74);
      if ( !v4 )
      {
        v44 = *v8;
        v45 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 10) = 0;
        *((_QWORD *)v8 + 12) = 0;
        v74[0] = (v44 == -120) + 1;
        v46 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v46);
        v47 = sqlite3Select(v9, v8, v74);
        v48 = *v8 == 0x86;
        v4 = v47;
        v69 = *((_QWORD *)v8 + 10);
        *((_QWORD *)v8 + 10) = v6;
        *((_QWORD *)v8 + 9) = 0;
        if ( v48 )
          *((_WORD *)v8 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v8 + 1), *(unsigned __int16 *)(v6 + 2));
        sqlite3ExprDeleteGeneric(v67, *((_QWORD *)v8 + 12));
        v48 = (_BYTE)v70 == 1;
        *((_QWORD *)v8 + 12) = v45;
        *((_QWORD *)v8 + 1) = 0;
        if ( v48 || *(_BYTE *)(v67 + 103) )
        {
          v3 = v67;
LABEL_46:
          if ( !*((_QWORD *)v8 + 11) )
          {
            v53 = *((unsigned int *)v9 + 80);
            if ( (_DWORD)v53 )
              v54 = *(_DWORD *)(sqlite3VdbeGetOp(v9[2], v53) + 8);
            else
              v54 = 0;
            *((_DWORD *)v9 + 80) = v54;
          }
          goto LABEL_51;
        }
        v49 = *((_DWORD *)v9 + 17) - 1;
        v50 = *((_DWORD *)v9 + 17) - 2;
        *((_DWORD *)v9 + 17) = v50;
        computeLimitRegisters(v9, v8, v49);
        sqlite3VdbeAddOp3(v68, 36, v42, v49, 0);
        v51 = *(_DWORD *)(v68 + 144);
        selectInnerLoop((_DWORD)v9, (_DWORD)v8, v42, 0, 0, (__int64)&v70, v49 - 1, v49);
        v52 = v50;
        v11 = v68;
        sqlite3VdbeResolveLabel(v68, v52);
        sqlite3VdbeAddOp3(v68, 39, v42, v51, 0);
        sqlite3VdbeResolveLabel(v68, v49);
        sqlite3VdbeAddOp3(v68, 122, v42, 0, 0);
LABEL_24:
        v3 = v67;
        goto LABEL_46;
      }
      break;
    default:
      v14 = *((_DWORD *)v9 + 13);
      v77 = v14;
      memset(&v73[2], 0, 21);
      *((_DWORD *)v9 + 13) = v14 + 2;
      *(_OWORD *)v73 = 0;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v14, 0, 0);
      v15 = findRightmost(v8);
      *(_DWORD *)(v15 + 4) |= 0x20u;
      LOBYTE(v73[0]) = 1;
      HIDWORD(v73[0]) = v14;
      v73[1] = 0;
      v73[3] = 0;
      LODWORD(v73[2]) = 0;
      v4 = sqlite3Select(v9, v6, v73);
      if ( !v4 )
      {
        v16 = v14 + 1;
        LODWORD(v79) = v16;
        v17 = sqlite3VdbeAddOp3(v11, 118, v16, 0, 0);
        v18 = *v8;
        *((_DWORD *)v8 + 6) = v17;
        v75 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 10) = 0;
        *((_QWORD *)v8 + 12) = 0;
        HIDWORD(v73[0]) = v16;
        v19 = (const char *)sqlite3SelectOpName(v18);
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v19);
        v20 = sqlite3Select(v9, v8, v73);
        v21 = *((_QWORD *)v8 + 10);
        v4 = v20;
        *((_QWORD *)v8 + 10) = v6;
        v22 = *(_WORD *)(v6 + 2);
        v69 = v21;
        if ( *((__int16 *)v8 + 1) > v22 )
          *((_WORD *)v8 + 1) = v22;
        sqlite3ExprDeleteGeneric(v3, *((_QWORD *)v8 + 12));
        *((_QWORD *)v8 + 12) = v75;
        if ( v4 )
          goto LABEL_46;
        v23 = *((_DWORD *)v9 + 17) - 1;
        v24 = *((_DWORD *)v9 + 17) - 2;
        *((_DWORD *)v9 + 17) = v24;
        computeLimitRegisters(v9, v8, v23);
        sqlite3VdbeAddOp3(v11, 36, v77, v23, 0);
        TempReg = sqlite3GetTempReg(v9);
        v26 = sqlite3VdbeAddOp3(v11, 134, v77, TempReg, 0);
        sqlite3VdbeAddOp4Int(v68, 28, v79, v24, TempReg, 0);
        sqlite3ReleaseTempReg(v9, TempReg);
        v27 = v77;
        selectInnerLoop(v28, (_DWORD)v8, v77, 0, 0, (__int64)&v70, v23 - 1, v23);
        sqlite3VdbeResolveLabel(v68, v24);
        v29 = v26;
        v11 = v68;
        sqlite3VdbeAddOp3(v68, 39, v27, v29, 0);
        sqlite3VdbeResolveLabel(v68, v23);
        sqlite3VdbeAddOp3(v68, 122, v27 + 1, 0, 0);
        sqlite3VdbeAddOp3(v68, 122, v27, 0, 0);
        goto LABEL_24;
      }
      break;
  }
LABEL_67:
  v66 = v78;
  *((_DWORD *)v78 + 3) = HIDWORD(v70);
  *((_DWORD *)v66 + 4) = v71;
  if ( v69 )
    sqlite3ParserAddCleanup(v9, sqlite3SelectDeleteGeneric, v69);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180040990  mov     [rsp-8+arg_10], r8
0x180040995  mov     [rsp-8+arg_0], rcx
0x18004099a  push    rbp
0x18004099b  push    rbx
0x18004099c  push    rsi
0x18004099d  push    rdi
0x18004099e  push    r12
0x1800409a0  push    r13
0x1800409a2  push    r14
0x1800409a4  push    r15
0x1800409a6  lea     rbp, [rsp-1Fh]
0x1800409ab  sub     rsp, 0E8h
0x1800409b2  movups  xmm0, xmmword ptr [r8]
0x1800409b6  mov     r14, [rcx]
0x1800409b9  xor     r13d, r13d
0x1800409bc  movups  xmm1, xmmword ptr [r8+10h]
0x1800409c1  mov     rbx, [rdx+50h]
0x1800409c5  mov     rsi, r8
0x1800409c8  movups  [rbp+57h+var_C8], xmm0
0x1800409cc  mov     r15, rdx
0x1800409cf  mov     r12, rcx
0x1800409d2  movsd   xmm0, qword ptr [r8+20h]
0x1800409d8  movsd   [rbp+57h+var_A8], xmm0
0x1800409dd  mov     [rbp+57h+var_D0], r13
0x1800409e1  mov     [rsp+120h+var_E0], r14
0x1800409e6  movups  [rbp+57h+var_B8], xmm1
0x1800409ea  call    sqlite3GetVdbe
0x1800409ef  cmp     byte ptr [rbp+57h+var_C8], 0Ch
0x1800409f3  mov     rdi, rax
0x1800409f6  mov     [rsp+120h+var_D8], rax
0x1800409fb  jnz     short loc_180040A1D
0x1800409fd  mov     r9, [r15+20h]
0x180040a01  lea     edx, [r13+76h]
0x180040a05  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x180040a09  mov     rcx, rax
0x180040a0c  mov     dword ptr [rsp+120h+var_100], r13d
0x180040a11  mov     r9d, [r9]
0x180040a14  call    sqlite3VdbeAddOp3
0x180040a19  mov     byte ptr [rbp+57h+var_C8], 0Eh
0x180040a1d  test    dword ptr [r15+4], 400h
0x180040a25  jz      short loc_180040A44
0x180040a27  lea     r8, [rbp+57h+var_C8]
0x180040a2b  mov     rdx, r15
0x180040a2e  mov     rcx, r12
0x180040a31  call    multiSelectValues
0x180040a36  mov     r13d, eax
0x180040a39  test    eax, eax
0x180040a3b  jns     loc_180041131
0x180040a41  xor     r13d, r13d
0x180040a44  mov     ecx, 2000h
0x180040a49  test    [r15+4], ecx
0x180040a4d  jz      short loc_180040A79
0x180040a4f  mov     rax, r15
0x180040a52  test    [rax+4], ecx
0x180040a55  jz      short loc_180040A60
0x180040a57  mov     rax, [rax+50h]
0x180040a5b  test    rax, rax
0x180040a5e  jnz     short loc_180040A52
0x180040a60  test    rax, rax
0x180040a63  jz      short loc_180040A79
0x180040a65  lea     r8, [rbp+57h+var_C8]
0x180040a69  mov     rdx, r15
0x180040a6c  mov     rcx, r12
0x180040a6f  call    generateWithRecursiveQuery
0x180040a74  jmp     loc_180041050
0x180040a79  cmp     [r15+48h], r13
0x180040a7d  jz      short loc_180040A92
0x180040a7f  mov     r8, rsi
0x180040a82  mov     rdx, r15
0x180040a85  mov     rcx, r12
0x180040a88  call    multiSelectOrderBy
0x180040a8d  jmp     loc_18004115F
0x180040a92  cmp     [rbx+50h], r13
0x180040a96  jnz     short loc_180040AC0
0x180040a98  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x180040a9f  mov     edx, 1
0x180040aa4  mov     rcx, r12
0x180040aa7  call    sqlite3VdbeExplain
0x180040aac  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x180040ab3  mov     edx, 1
0x180040ab8  mov     rcx, r12
0x180040abb  call    sqlite3VdbeExplain
0x180040ac0  movzx   ecx, byte ptr [r15]
0x180040ac4  sub     ecx, 86h
0x180040aca  jz      loc_180040E3D
0x180040ad0  sub     ecx, 1
0x180040ad3  jz      loc_180040D17
0x180040ad9  cmp     ecx, 1
0x180040adc  jz      loc_180040E3D
0x180040ae2  mov     esi, [r12+34h]
0x180040ae7  xorps   xmm0, xmm0
0x180040aea  xor     eax, eax
0x180040aec  mov     [rbp+57h+arg_8], esi
0x180040aef  xor     r9d, r9d
0x180040af2  mov     dword ptr [rsp+120h+var_100], r13d
0x180040af7  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180040afb  mov     qword ptr [rbp+57h+var_90+0Dh], rax
0x180040aff  mov     r8d, esi
0x180040b02  lea     eax, [rsi+2]
0x180040b05  mov     rcx, rdi
0x180040b08  lea     edx, [r9+76h]
0x180040b0c  mov     [r12+34h], eax
0x180040b11  movups  [rbp+57h+var_A0], xmm0
0x180040b15  call    sqlite3VdbeAddOp3
0x180040b1a  mov     rcx, r15
0x180040b1d  mov     [r15+14h], eax
0x180040b21  call    findRightmost
0x180040b26  lea     r8, [rbp+57h+var_A0]
0x180040b2a  mov     rdx, rbx
0x180040b2d  mov     rcx, r12
0x180040b30  or      dword ptr [rax+4], 20h
0x180040b34  mov     byte ptr [rbp+57h+var_A0], 1
0x180040b38  mov     dword ptr [rbp+57h+var_A0+4], esi
0x180040b3b  mov     qword ptr [rbp+57h+var_A0+8], 0
0x180040b43  mov     qword ptr [rbp+57h+var_90+8], r13
0x180040b47  mov     dword ptr [rbp+57h+var_90], r13d
0x180040b4b  call    sqlite3Select
0x180040b50  mov     r13d, eax
0x180040b53  test    eax, eax
0x180040b55  jnz     loc_180041131
0x180040b5b  inc     esi
0x180040b5d  mov     dword ptr [rsp+120h+var_100], eax
0x180040b61  mov     r8d, esi
0x180040b64  mov     dword ptr [rbp+57h+arg_18], esi
0x180040b67  xor     r9d, r9d
0x180040b6a  lea     edx, [rax+76h]
0x180040b6d  mov     rcx, rdi
0x180040b70  call    sqlite3VdbeAddOp3
0x180040b75  movzx   ecx, byte ptr [r15]
0x180040b79  mov     [r15+18h], eax
0x180040b7d  mov     rax, [r15+60h]
0x180040b81  mov     [rbp+57h+var_50], rax
0x180040b85  mov     qword ptr [r15+50h], 0
0x180040b8d  mov     qword ptr [r15+60h], 0
0x180040b95  mov     dword ptr [rbp+57h+var_A0+4], esi
0x180040b98  call    sqlite3SelectOpName
0x180040b9d  mov     r9, rax
0x180040ba0  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x180040ba7  mov     rcx, r12
0x180040baa  lea     edx, [r13+1]
0x180040bae  call    sqlite3VdbeExplain
0x180040bb3  lea     r8, [rbp+57h+var_A0]
0x180040bb7  mov     rdx, r15
0x180040bba  mov     rcx, r12
0x180040bbd  call    sqlite3Select
0x180040bc2  mov     rsi, [r15+50h]
0x180040bc6  mov     r13d, eax
0x180040bc9  mov     [r15+50h], rbx
0x180040bcd  movzx   eax, word ptr [rbx+2]
0x180040bd1  mov     [rbp+57h+var_D0], rsi
0x180040bd5  cmp     [r15+2], ax
0x180040bda  jle     short loc_180040BE1
0x180040bdc  mov     [r15+2], ax
0x180040be1  mov     rdx, [r15+60h]
0x180040be5  mov     rcx, r14
0x180040be8  call    sqlite3ExprDeleteGeneric
0x180040bed  mov     rax, [rbp+57h+var_50]
0x180040bf1  mov     [r15+60h], rax
0x180040bf5  test    r13d, r13d
0x180040bf8  jnz     loc_180041024
0x180040bfe  mov     r14d, [r12+44h]
0x180040c03  mov     rdx, r15
0x180040c06  dec     r14d
0x180040c09  mov     rcx, r12
0x180040c0c  mov     r8d, r14d
0x180040c0f  lea     esi, [r14-1]
0x180040c13  mov     [r12+44h], esi
0x180040c18  call    computeLimitRegisters
0x180040c1d  mov     r8d, [rbp+57h+arg_8]
0x180040c21  lea     edx, [r13+24h]
0x180040c25  mov     r9d, r14d
0x180040c28  mov     dword ptr [rsp+120h+var_100], r13d
0x180040c2d  mov     rcx, rdi
0x180040c30  call    sqlite3VdbeAddOp3
0x180040c35  mov     rcx, r12
0x180040c38  call    sqlite3GetTempReg
0x180040c3d  mov     r8d, [rbp+57h+arg_8]
0x180040c41  mov     r9d, eax
0x180040c44  mov     edx, 86h
0x180040c49  mov     dword ptr [rsp+120h+var_100], r13d
0x180040c4e  mov     rcx, rdi
0x180040c51  mov     ebx, eax
0x180040c53  call    sqlite3VdbeAddOp3
0x180040c58  mov     r8d, dword ptr [rbp+57h+arg_18]
0x180040c5c  lea     edx, [r13+1Ch]
0x180040c60  mov     rcx, [rsp+120h+var_D8]
0x180040c65  mov     r9d, esi
0x180040c68  mov     dword ptr [rsp+120h+var_F8], r13d
0x180040c6d  mov     edi, eax
0x180040c6f  mov     dword ptr [rsp+120h+var_100], ebx
0x180040c73  call    sqlite3VdbeAddOp4Int
0x180040c78  mov     edx, ebx
0x180040c7a  mov     rcx, r12
0x180040c7d  call    sqlite3ReleaseTempReg
0x180040c82  mov     ebx, [rbp+57h+arg_8]
0x180040c85  lea     rax, [rbp+57h+var_C8]
0x180040c89  mov     [rsp+120h+var_E8], r14d
0x180040c8e  xor     r9d, r9d
0x180040c91  mov     [rsp+120h+var_F0], esi
0x180040c95  mov     r8d, ebx
0x180040c98  mov     [rsp+120h+var_F8], rax
0x180040c9d  mov     rdx, r15
0x180040ca0  mov     [rsp+120h+var_100], 0
0x180040ca9  call    selectInnerLoop
0x180040cae  mov     rcx, [rsp+120h+var_D8]
0x180040cb3  mov     edx, esi
0x180040cb5  call    sqlite3VdbeResolveLabel
0x180040cba  xor     esi, esi
0x180040cbc  mov     r9d, edi
0x180040cbf  mov     rdi, [rsp+120h+var_D8]
0x180040cc4  mov     r8d, ebx
0x180040cc7  mov     rcx, rdi
0x180040cca  mov     dword ptr [rsp+120h+var_100], esi
0x180040cce  lea     edx, [rsi+27h]
0x180040cd1  call    sqlite3VdbeAddOp3
0x180040cd6  mov     edx, r14d
0x180040cd9  mov     rcx, rdi
0x180040cdc  call    sqlite3VdbeResolveLabel
0x180040ce1  xor     r9d, r9d
0x180040ce4  mov     dword ptr [rsp+120h+var_100], esi
0x180040ce8  lea     r8d, [rbx+1]
0x180040cec  mov     rcx, rdi
0x180040cef  lea     edx, [rsi+7Ah]
0x180040cf2  call    sqlite3VdbeAddOp3
0x180040cf7  mov     r8d, ebx
0x180040cfa  mov     dword ptr [rsp+120h+var_100], esi
0x180040cfe  xor     r9d, r9d
0x180040d01  mov     rcx, rdi
0x180040d04  lea     edx, [r9+7Ah]
0x180040d08  call    sqlite3VdbeAddOp3
0x180040d0d  mov     r14, [rsp+120h+var_E0]
0x180040d12  jmp     loc_180041024
0x180040d17  mov     eax, [r15+8]
0x180040d1b  lea     r8, [rbp+57h+var_C8]
0x180040d1f  mov     [rbx+8], eax
0x180040d22  mov     rdx, rbx
0x180040d25  mov     eax, [r15+0Ch]
0x180040d29  mov     rcx, r12
0x180040d2c  mov     [rbx+0Ch], eax
0x180040d2f  mov     rax, [r15+60h]
0x180040d33  mov     [rbx+60h], rax
0x180040d37  mov     [rbp+57h+arg_8], r13d
0x180040d3b  call    sqlite3Select
0x180040d40  mov     qword ptr [rbx+60h], 0
0x180040d48  mov     r13d, eax
0x180040d4b  test    eax, eax
0x180040d4d  jnz     loc_180041131
0x180040d53  xor     esi, esi
0x180040d55  mov     [r15+50h], rsi
0x180040d59  mov     r8d, [rbx+8]
0x180040d5d  mov     [r15+8], r8d
0x180040d61  mov     eax, [rbx+0Ch]
0x180040d64  mov     [r15+0Ch], eax
0x180040d68  test    r8d, r8d
0x180040d6b  jz      short loc_180040DA2
0x180040d6d  xor     r9d, r9d
0x180040d70  mov     dword ptr [rsp+120h+var_100], esi
0x180040d74  lea     edx, [rsi+11h]
0x180040d77  mov     rcx, rdi
0x180040d7a  call    sqlite3VdbeAddOp3
0x180040d7f  mov     ecx, [r15+0Ch]
0x180040d83  mov     esi, eax
0x180040d85  test    ecx, ecx
0x180040d87  jz      short loc_180040DA2
0x180040d89  mov     r8d, [r15+8]
0x180040d8d  lea     r9d, [rcx+1]
0x180040d91  mov     dword ptr [rsp+120h+var_100], ecx
0x180040d95  mov     edx, 0A0h
0x180040d9a  mov     rcx, rdi
0x180040d9d  call    sqlite3VdbeAddOp3
0x180040da2  lea     r8, aUnionAll; "UNION ALL"
0x180040da9  mov     edx, 1
0x180040dae  mov     rcx, r12
0x180040db1  call    sqlite3VdbeExplain
0x180040db6  lea     r8, [rbp+57h+var_C8]
0x180040dba  mov     rdx, r15
0x180040dbd  mov     rcx, r12
0x180040dc0  call    sqlite3Select
0x180040dc5  movzx   ecx, word ptr [r15+2]
0x180040dca  mov     r13d, eax
0x180040dcd  mov     rax, [r15+50h]
0x180040dd1  mov     [r15+50h], rbx
0x180040dd5  movzx   edx, word ptr [rbx+2]
0x180040dd9  mov     [rbp+57h+var_D0], rax
0x180040ddd  call    sqlite3LogEstAdd
0x180040de2  mov     rcx, [r15+60h]
0x180040de6  movzx   r10d, ax
0x180040dea  mov     [r15+2], ax
0x180040def  test    rcx, rcx
0x180040df2  jz      short loc_180040E1D
0x180040df4  mov     rcx, [rcx+10h]
0x180040df8  lea     rdx, [rbp+57h+arg_8]
0x180040dfc  call    sqlite3ExprIsInteger
0x180040e01  test    eax, eax
0x180040e03  jz      short loc_180040E1D
0x180040e05  movsxd  rcx, [rbp+57h+arg_8]
0x180040e09  test    ecx, ecx
0x180040e0b  jle     short loc_180040E1D
0x180040e0d  call    sqlite3LogEst
0x180040e12  cmp     r10w, ax
  ... truncated ...
```

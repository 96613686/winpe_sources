# multiSelect

- ea: `0x1800711f4`
- end: `0x1800719d9`
- name: `multiSelect`
- size: `2021`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180005650`

## callees

- `0x18000506c`
- `0x180005650`
- `0x180009ac0`
- `0x180013fac`
- `0x180014034`
- `0x180015eb0`
- `0x1800168c0`
- `0x180016c60`
- `0x180016ef0`
- `0x18001bb70`
- `0x18001e090`
- `0x180023b60`
- `0x18004a418`
- `0x18004a478`
- `0x18004e9f4`
- `0x18004f280`
- `0x180052c0c`
- `0x1800579e4`
- `0x180062a28`
- `0x1800658bc`
- `0x18006e790`
- `0x1800711f4`
- `0x180076e6c`
- `0x18007eb9c`
- `0x180080260`
- `0x1800897fc`
- `0x180089968`

## string_xrefs

- `0x1800712fc`: `COMPOUND QUERY`
- `0x180071404`: `%s USING TEMP B-TREE`
- `0x180071741`: `%s USING TEMP B-TREE`

## pseudocode

```c
__int64 __fastcall multiSelect(__int64 *a1, unsigned __int8 *a2, __int128 *a3)
{
  __int64 v3; // r14
  int v4; // r13d
  __int128 v5; // xmm1
  __int64 v6; // rbx
  unsigned __int8 *v8; // r15
  __int64 v9; // r12
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
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rsi
  __int16 v24; // ax
  unsigned int v25; // r14d
  unsigned int v26; // esi
  __int64 v27; // rdx
  unsigned int TempReg; // ebx
  int v29; // edi
  int v30; // ebx
  int v31; // ecx
  int v32; // r9d
  int v33; // eax
  unsigned int v34; // esi
  int v35; // r8d
  unsigned int v36; // eax
  int v37; // ecx
  int v38; // eax
  __int64 v39; // r10
  __int64 v40; // rcx
  __int16 v41; // ax
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int16 v44; // ax
  __int16 v45; // r10
  int v46; // r14d
  __int64 Rightmost; // rax
  char v48; // cl
  __int64 v49; // rsi
  const char *v50; // rax
  int v51; // eax
  bool v52; // zf
  unsigned int v53; // esi
  unsigned int v54; // edi
  int v55; // ebx
  __int64 v56; // rdx
  __int64 v57; // rdx
  int v58; // eax
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r14
  int v63; // esi
  __int64 *v64; // rbx
  int v65; // edi
  __int64 v66; // rax
  int v67; // r12d
  __int64 v68; // rbx
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int128 *v72; // rcx
  __int64 v73; // [rsp+40h] [rbp-89h]
  __int64 v74; // [rsp+48h] [rbp-81h]
  __int64 v75; // [rsp+50h] [rbp-79h]
  __int128 v76; // [rsp+58h] [rbp-71h] BYREF
  __int128 v77; // [rsp+68h] [rbp-61h]
  __int64 v78; // [rsp+78h] [rbp-51h]
  _QWORD v79[5]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v80[37]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v81; // [rsp+D0h] [rbp+7h]
  int v83; // [rsp+138h] [rbp+6Fh] BYREF
  __int128 *v84; // [rsp+140h] [rbp+77h]
  __int64 v85; // [rsp+148h] [rbp+7Fh]

  v84 = a3;
  v3 = *a1;
  v4 = 0;
  v5 = a3[1];
  v6 = *((_QWORD *)a2 + 10);
  v76 = *a3;
  v8 = a2;
  v9 = (__int64)a1;
  v78 = *((_QWORD *)a3 + 4);
  v75 = 0;
  v73 = v3;
  v77 = v5;
  Vdbe = sqlite3GetVdbe(a1);
  v11 = Vdbe;
  v74 = Vdbe;
  if ( (_BYTE)v76 == 12 )
  {
    sqlite3VdbeAddOp3(Vdbe, 118, DWORD1(v76), **((_DWORD **)v8 + 4), 0);
    LOBYTE(v76) = 14;
  }
  if ( (*((_DWORD *)v8 + 1) & 0x400) != 0 )
  {
    v4 = multiSelectValues(v9, v8, &v76);
    if ( v4 >= 0 )
      goto LABEL_70;
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
      generateWithRecursiveQuery(v9, v8, &v76);
LABEL_54:
      if ( !*(_DWORD *)(v9 + 48) && (v8[4] & 0x20) != 0 )
      {
        v83 = **((_DWORD **)v8 + 4);
        v59 = sqlite3KeyInfoAlloc(v3, (unsigned int)v83, 1);
        v85 = v59;
        v62 = v59;
        if ( v59 )
        {
          v63 = 0;
          v64 = (__int64 *)(v59 + 32);
          if ( v83 > 0 )
          {
            v65 = v83;
            do
            {
              v66 = multiSelectCollSeq(v9, v8, (unsigned int)v63);
              *v64 = v66;
              if ( !v66 )
                *v64 = *(_QWORD *)(v73 + 16);
              ++v63;
              ++v64;
            }
            while ( v63 < v65 );
            v11 = v74;
            v62 = v85;
          }
          v67 = v83;
          do
          {
            v68 = 0;
            do
            {
              v69 = *(unsigned int *)&v8[4 * v68 + 20];
              if ( (int)v69 < 0 )
                break;
              *(_DWORD *)(sqlite3VdbeGetOp(v11, v69, v60, v61) + 8) = v67;
              v70 = sqlite3KeyInfoRef(v62);
              sqlite3VdbeChangeP4(v11, v71, v70, 4294967288LL);
              *(_DWORD *)&v8[4 * v68 + 20] = -1;
              v68 = (unsigned int)(v68 + 1);
            }
            while ( (int)v68 < 2 );
            v8 = (unsigned __int8 *)*((_QWORD *)v8 + 10);
          }
          while ( v8 );
          sqlite3KeyInfoUnref(v62);
          v9 = (__int64)a1;
        }
        else
        {
          v4 = 7;
        }
      }
      goto LABEL_70;
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
      goto LABEL_37;
    case 0x87u:
      *(_DWORD *)(v6 + 8) = *((_DWORD *)v8 + 2);
      *(_DWORD *)(v6 + 12) = *((_DWORD *)v8 + 3);
      *(_QWORD *)(v6 + 96) = *((_QWORD *)v8 + 12);
      v83 = 0;
      v33 = sqlite3Select(v9, v6, &v76);
      *(_QWORD *)(v6 + 96) = 0;
      v4 = v33;
      if ( !v33 )
      {
        v34 = 0;
        *((_QWORD *)v8 + 10) = 0;
        v35 = *(_DWORD *)(v6 + 8);
        *((_DWORD *)v8 + 2) = v35;
        *((_DWORD *)v8 + 3) = *(_DWORD *)(v6 + 12);
        if ( v35 )
        {
          v36 = sqlite3VdbeAddOp3(v11, 17, v35, 0, 0);
          v37 = *((_DWORD *)v8 + 3);
          v34 = v36;
          if ( v37 )
            sqlite3VdbeAddOp3(v11, 160, *((_DWORD *)v8 + 2), v37 + 1, v37);
        }
        sqlite3VdbeExplain(v9, 1, "UNION ALL");
        v38 = sqlite3Select(v9, v8, &v76);
        v39 = *((_QWORD *)v8 + 10);
        v4 = v38;
        v40 = *((unsigned __int16 *)v8 + 1);
        *((_QWORD *)v8 + 10) = v6;
        v75 = v39;
        v41 = sqlite3LogEstAdd(v40, *(unsigned __int16 *)(v6 + 2));
        v42 = *((_QWORD *)v8 + 12);
        *((_WORD *)v8 + 1) = v41;
        if ( v42 )
        {
          if ( (unsigned int)sqlite3ExprIsInteger(*(_QWORD *)(v42 + 16), &v83) )
          {
            if ( v83 > 0 )
            {
              v44 = sqlite3LogEst(v83, v43, v21, v22);
              if ( v45 > v44 )
                *((_WORD *)v8 + 1) = v44;
            }
          }
        }
        if ( v34 )
          *(_DWORD *)(sqlite3VdbeGetOp(v11, v34, v21, v22) + 8) = *(_DWORD *)(v11 + 144);
        goto LABEL_49;
      }
      break;
    case 0x88u:
LABEL_37:
      memset(v80, 0, sizeof(v80));
      if ( (_BYTE)v76 == 1 )
      {
        v46 = DWORD1(v76);
      }
      else
      {
        v46 = *(_DWORD *)(v9 + 52);
        *(_DWORD *)(v9 + 52) = v46 + 1;
        *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v46, 0, 0);
        Rightmost = findRightmost(v8);
        *(_DWORD *)(Rightmost + 4) |= 0x20u;
      }
      v80[0] = 1;
      *(_DWORD *)&v80[4] = v46;
      *(_QWORD *)&v80[8] = 0;
      *(_QWORD *)&v80[24] = 0;
      *(_DWORD *)&v80[16] = 0;
      v4 = sqlite3Select(v9, v6, v80);
      if ( !v4 )
      {
        v48 = *v8;
        v49 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 10) = 0;
        *((_QWORD *)v8 + 12) = 0;
        v80[0] = (v48 == -120) + 1;
        v50 = (const char *)((__int64 (*)(void))sqlite3SelectOpName)();
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v50);
        v51 = sqlite3Select(v9, v8, v80);
        v52 = *v8 == 0x86;
        v4 = v51;
        v75 = *((_QWORD *)v8 + 10);
        *((_QWORD *)v8 + 10) = v6;
        *((_QWORD *)v8 + 9) = 0;
        if ( v52 )
          *((_WORD *)v8 + 1) = sqlite3LogEstAdd(*((unsigned __int16 *)v8 + 1), *(unsigned __int16 *)(v6 + 2));
        if ( *((_QWORD *)v8 + 12) )
          sqlite3ExprDeleteNN(v73);
        v52 = (_BYTE)v76 == 1;
        *((_QWORD *)v8 + 12) = v49;
        *((_QWORD *)v8 + 1) = 0;
        if ( !v52 && !*(_BYTE *)(v73 + 103) )
        {
          v53 = *(_DWORD *)(v9 + 68) - 1;
          v54 = *(_DWORD *)(v9 + 68) - 2;
          *(_DWORD *)(v9 + 68) = v54;
          computeLimitRegisters(v9, (__int64)v8, v53);
          sqlite3VdbeAddOp3(v74, 36, v46, v53, 0);
          v55 = *(_DWORD *)(v74 + 144);
          selectInnerLoop(v9, (_DWORD)v8, v46, 0, 0, (__int64)&v76, v53 - 1, v53);
          v56 = v54;
          v11 = v74;
          sqlite3VdbeResolveLabel(v74, v56);
          sqlite3VdbeAddOp3(v74, 39, v46, v55, 0);
          sqlite3VdbeResolveLabel(v74, v53);
          sqlite3VdbeAddOp3(v74, 122, v46, 0, 0);
        }
        goto LABEL_48;
      }
      break;
    default:
      v14 = *(_DWORD *)(v9 + 52);
      v83 = v14;
      memset(&v79[2], 0, 21);
      *(_DWORD *)(v9 + 52) = v14 + 2;
      *(_OWORD *)v79 = 0;
      *((_DWORD *)v8 + 5) = sqlite3VdbeAddOp3(v11, 118, v14, 0, 0);
      v15 = findRightmost(v8);
      *(_DWORD *)(v15 + 4) |= 0x20u;
      LOBYTE(v79[0]) = 1;
      HIDWORD(v79[0]) = v14;
      v79[1] = 0;
      v79[3] = 0;
      LODWORD(v79[2]) = 0;
      v4 = sqlite3Select(v9, v6, v79);
      if ( !v4 )
      {
        v16 = v14 + 1;
        LODWORD(v85) = v16;
        v17 = sqlite3VdbeAddOp3(v11, 118, v16, 0, 0);
        v18 = *v8;
        *((_DWORD *)v8 + 6) = v17;
        v81 = *((_QWORD *)v8 + 12);
        *((_QWORD *)v8 + 10) = 0;
        *((_QWORD *)v8 + 12) = 0;
        HIDWORD(v79[0]) = v16;
        v19 = (const char *)sqlite3SelectOpName(v18);
        sqlite3VdbeExplain(v9, 1, "%s USING TEMP B-TREE", v19);
        v20 = sqlite3Select(v9, v8, v79);
        v23 = *((_QWORD *)v8 + 10);
        v4 = v20;
        *((_QWORD *)v8 + 10) = v6;
        v24 = *(_WORD *)(v6 + 2);
        v75 = v23;
        if ( *((__int16 *)v8 + 1) > v24 )
          *((_WORD *)v8 + 1) = v24;
        if ( *((_QWORD *)v8 + 12) )
          sqlite3ExprDeleteNN(v3);
        *((_QWORD *)v8 + 12) = v81;
        if ( v4 )
          goto LABEL_49;
        v25 = *(_DWORD *)(v9 + 68) - 1;
        v26 = *(_DWORD *)(v9 + 68) - 2;
        *(_DWORD *)(v9 + 68) = v26;
        computeLimitRegisters(v9, (__int64)v8, v25);
        sqlite3VdbeAddOp3(v11, 36, v83, v25, 0);
        TempReg = sqlite3GetTempReg(v9, v27);
        v29 = sqlite3VdbeAddOp3(v11, 134, v83, TempReg, 0);
        sqlite3VdbeAddOp4Int(v74, 28, v85, v26, TempReg, 0);
        sqlite3ReleaseTempReg(v9, TempReg);
        v30 = v83;
        selectInnerLoop(v31, (_DWORD)v8, v83, 0, 0, (__int64)&v76, v25 - 1, v25);
        sqlite3VdbeResolveLabel(v74, v26);
        v32 = v29;
        v11 = v74;
        sqlite3VdbeAddOp3(v74, 39, v30, v32, 0);
        sqlite3VdbeResolveLabel(v74, v25);
        sqlite3VdbeAddOp3(v74, 122, v30 + 1, 0, 0);
        sqlite3VdbeAddOp3(v74, 122, v30, 0, 0);
LABEL_48:
        v3 = v73;
LABEL_49:
        if ( !*((_QWORD *)v8 + 11) )
        {
          v57 = *(unsigned int *)(v9 + 320);
          if ( (_DWORD)v57 )
            v58 = *(_DWORD *)(sqlite3VdbeGetOp(*(_QWORD *)(v9 + 16), v57, v21, v22) + 8);
          else
            v58 = 0;
          *(_DWORD *)(v9 + 320) = v58;
        }
        goto LABEL_54;
      }
      break;
  }
LABEL_70:
  v72 = v84;
  *((_DWORD *)v84 + 3) = HIDWORD(v76);
  *((_DWORD *)v72 + 4) = v77;
  if ( v75 )
    sqlite3ParserAddCleanup(v9, sqlite3SelectDeleteGeneric, v75);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800711f4  mov     [rsp-8+arg_10], r8
0x1800711f9  mov     [rsp-8+arg_0], rcx
0x1800711fe  push    rbp
0x1800711ff  push    rbx
0x180071200  push    rsi
0x180071201  push    rdi
0x180071202  push    r12
0x180071204  push    r13
0x180071206  push    r14
0x180071208  push    r15
0x18007120a  lea     rbp, [rsp-1Fh]
0x18007120f  sub     rsp, 0E8h
0x180071216  movups  xmm0, xmmword ptr [r8]
0x18007121a  mov     r14, [rcx]
0x18007121d  xor     r13d, r13d
0x180071220  movups  xmm1, xmmword ptr [r8+10h]
0x180071225  mov     rbx, [rdx+50h]
0x180071229  mov     rsi, r8
0x18007122c  movups  [rbp+57h+var_C8], xmm0
0x180071230  mov     r15, rdx
0x180071233  mov     r12, rcx
0x180071236  movsd   xmm0, qword ptr [r8+20h]
0x18007123c  movsd   [rbp+57h+var_A8], xmm0
0x180071241  mov     [rbp+57h+var_D0], r13
0x180071245  mov     [rsp+120h+var_E0], r14
0x18007124a  movups  [rbp+57h+var_B8], xmm1
0x18007124e  call    sqlite3GetVdbe
0x180071253  cmp     byte ptr [rbp+57h+var_C8], 0Ch
0x180071257  mov     rdi, rax
0x18007125a  mov     [rsp+120h+var_D8], rax
0x18007125f  jnz     short loc_180071281
0x180071261  mov     r9, [r15+20h]
0x180071265  lea     edx, [r13+76h]
0x180071269  mov     r8d, dword ptr [rbp+57h+var_C8+4]
0x18007126d  mov     rcx, rax
0x180071270  mov     dword ptr [rsp+120h+var_100], r13d
0x180071275  mov     r9d, [r9]
0x180071278  call    sqlite3VdbeAddOp3
0x18007127d  mov     byte ptr [rbp+57h+var_C8], 0Eh
0x180071281  test    dword ptr [r15+4], 400h
0x180071289  jz      short loc_1800712A8
0x18007128b  lea     r8, [rbp+57h+var_C8]
0x18007128f  mov     rdx, r15
0x180071292  mov     rcx, r12
0x180071295  call    multiSelectValues
0x18007129a  mov     r13d, eax
0x18007129d  test    eax, eax
0x18007129f  jns     loc_180071997
0x1800712a5  xor     r13d, r13d
0x1800712a8  mov     ecx, 2000h
0x1800712ad  test    [r15+4], ecx
0x1800712b1  jz      short loc_1800712DD
0x1800712b3  mov     rax, r15
0x1800712b6  test    [rax+4], ecx
0x1800712b9  jz      short loc_1800712C4
0x1800712bb  mov     rax, [rax+50h]
0x1800712bf  test    rax, rax
0x1800712c2  jnz     short loc_1800712B6
0x1800712c4  test    rax, rax
0x1800712c7  jz      short loc_1800712DD
0x1800712c9  lea     r8, [rbp+57h+var_C8]
0x1800712cd  mov     rdx, r15
0x1800712d0  mov     rcx, r12
0x1800712d3  call    generateWithRecursiveQuery
0x1800712d8  jmp     loc_1800718B6
0x1800712dd  cmp     [r15+48h], r13
0x1800712e1  jz      short loc_1800712F6
0x1800712e3  mov     r8, rsi
0x1800712e6  mov     rdx, r15
0x1800712e9  mov     rcx, r12
0x1800712ec  call    multiSelectOrderBy
0x1800712f1  jmp     loc_1800719C5
0x1800712f6  cmp     [rbx+50h], r13
0x1800712fa  jnz     short loc_180071324
0x1800712fc  lea     r8, aCompoundQuery; "COMPOUND QUERY"
0x180071303  mov     edx, 1
0x180071308  mov     rcx, r12
0x18007130b  call    sqlite3VdbeExplain
0x180071310  lea     r8, aLeftMostSubque; "LEFT-MOST SUBQUERY"
0x180071317  mov     edx, 1
0x18007131c  mov     rcx, r12
0x18007131f  call    sqlite3VdbeExplain
0x180071324  movzx   ecx, byte ptr [r15]
0x180071328  sub     ecx, 86h
0x18007132e  jz      loc_180071692
0x180071334  sub     ecx, 1
0x180071337  jz      loc_18007156C
0x18007133d  cmp     ecx, 1
0x180071340  jz      loc_180071692
0x180071346  mov     esi, [r12+34h]
0x18007134b  xorps   xmm0, xmm0
0x18007134e  xor     eax, eax
0x180071350  mov     [rbp+57h+arg_8], esi
0x180071353  xor     r9d, r9d
0x180071356  mov     dword ptr [rsp+120h+var_100], r13d
0x18007135b  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18007135f  mov     qword ptr [rbp+57h+var_90+0Dh], rax
0x180071363  mov     r8d, esi
0x180071366  lea     eax, [rsi+2]
0x180071369  mov     rcx, rdi
0x18007136c  lea     edx, [r9+76h]
0x180071370  mov     [r12+34h], eax
0x180071375  movups  [rbp+57h+var_A0], xmm0
0x180071379  call    sqlite3VdbeAddOp3
0x18007137e  mov     rcx, r15
0x180071381  mov     [r15+14h], eax
0x180071385  call    findRightmost
0x18007138a  lea     r8, [rbp+57h+var_A0]
0x18007138e  mov     rdx, rbx
0x180071391  mov     rcx, r12
0x180071394  or      dword ptr [rax+4], 20h
0x180071398  mov     byte ptr [rbp+57h+var_A0], 1
0x18007139c  mov     dword ptr [rbp+57h+var_A0+4], esi
0x18007139f  mov     qword ptr [rbp+57h+var_A0+8], 0
0x1800713a7  mov     qword ptr [rbp+57h+var_90+8], r13
0x1800713ab  mov     dword ptr [rbp+57h+var_90], r13d
0x1800713af  call    sqlite3Select
0x1800713b4  mov     r13d, eax
0x1800713b7  test    eax, eax
0x1800713b9  jnz     loc_180071997
0x1800713bf  inc     esi
0x1800713c1  mov     dword ptr [rsp+120h+var_100], eax
0x1800713c5  mov     r8d, esi
0x1800713c8  mov     dword ptr [rbp+57h+arg_18], esi
0x1800713cb  xor     r9d, r9d
0x1800713ce  lea     edx, [rax+76h]
0x1800713d1  mov     rcx, rdi
0x1800713d4  call    sqlite3VdbeAddOp3
0x1800713d9  movzx   ecx, byte ptr [r15]
0x1800713dd  mov     [r15+18h], eax
0x1800713e1  mov     rax, [r15+60h]
0x1800713e5  mov     [rbp+57h+var_50], rax
0x1800713e9  mov     qword ptr [r15+50h], 0
0x1800713f1  mov     qword ptr [r15+60h], 0
0x1800713f9  mov     dword ptr [rbp+57h+var_A0+4], esi
0x1800713fc  call    sqlite3SelectOpName
0x180071401  mov     r9, rax
0x180071404  lea     r8, aSUsingTempBTre; "%s USING TEMP B-TREE"
0x18007140b  mov     rcx, r12
0x18007140e  lea     edx, [r13+1]
0x180071412  call    sqlite3VdbeExplain
0x180071417  lea     r8, [rbp+57h+var_A0]
0x18007141b  mov     rdx, r15
0x18007141e  mov     rcx, r12
0x180071421  call    sqlite3Select
0x180071426  mov     rsi, [r15+50h]
0x18007142a  mov     r13d, eax
0x18007142d  mov     [r15+50h], rbx
0x180071431  movzx   eax, word ptr [rbx+2]
0x180071435  mov     [rbp+57h+var_D0], rsi
0x180071439  cmp     [r15+2], ax
0x18007143e  jle     short loc_180071445
0x180071440  mov     [r15+2], ax
0x180071445  mov     rdx, [r15+60h]
0x180071449  test    rdx, rdx
0x18007144c  jz      short loc_180071456
0x18007144e  mov     rcx, r14
0x180071451  call    sqlite3ExprDeleteNN
0x180071456  mov     rax, [rbp+57h+var_50]
0x18007145a  mov     [r15+60h], rax
0x18007145e  test    r13d, r13d
0x180071461  jnz     loc_18007188A
0x180071467  mov     r14d, [r12+44h]
0x18007146c  mov     rdx, r15
0x18007146f  dec     r14d
0x180071472  mov     rcx, r12
0x180071475  mov     r8d, r14d
0x180071478  lea     esi, [r14-1]
0x18007147c  mov     [r12+44h], esi
0x180071481  call    computeLimitRegisters
0x180071486  mov     r8d, [rbp+57h+arg_8]
0x18007148a  lea     edx, [r13+24h]
0x18007148e  mov     r9d, r14d
0x180071491  mov     dword ptr [rsp+120h+var_100], r13d
0x180071496  mov     rcx, rdi
0x180071499  call    sqlite3VdbeAddOp3
0x18007149e  mov     rcx, r12
0x1800714a1  call    sqlite3GetTempReg
0x1800714a6  mov     r8d, [rbp+57h+arg_8]
0x1800714aa  mov     r9d, eax
0x1800714ad  mov     edx, 86h
0x1800714b2  mov     dword ptr [rsp+120h+var_100], r13d
0x1800714b7  mov     rcx, rdi
0x1800714ba  mov     ebx, eax
0x1800714bc  call    sqlite3VdbeAddOp3
0x1800714c1  mov     r8d, dword ptr [rbp+57h+arg_18]
0x1800714c5  lea     edx, [r13+1Ch]
0x1800714c9  mov     rcx, [rsp+120h+var_D8]
0x1800714ce  mov     r9d, esi
0x1800714d1  mov     dword ptr [rsp+120h+var_F8], r13d
0x1800714d6  mov     edi, eax
0x1800714d8  mov     dword ptr [rsp+120h+var_100], ebx
0x1800714dc  call    sqlite3VdbeAddOp4Int
0x1800714e1  mov     edx, ebx
0x1800714e3  mov     rcx, r12
0x1800714e6  call    sqlite3ReleaseTempReg
0x1800714eb  mov     ebx, [rbp+57h+arg_8]
0x1800714ee  lea     rax, [rbp+57h+var_C8]
0x1800714f2  mov     [rsp+120h+var_E8], r14d
0x1800714f7  xor     r9d, r9d
0x1800714fa  mov     [rsp+120h+var_F0], esi
0x1800714fe  mov     r8d, ebx
0x180071501  mov     [rsp+120h+var_F8], rax
0x180071506  mov     rdx, r15
0x180071509  mov     [rsp+120h+var_100], 0
0x180071512  call    selectInnerLoop
0x180071517  mov     rcx, [rsp+120h+var_D8]
0x18007151c  mov     edx, esi
0x18007151e  call    sqlite3VdbeResolveLabel
0x180071523  xor     esi, esi
0x180071525  mov     r9d, edi
0x180071528  mov     rdi, [rsp+120h+var_D8]
0x18007152d  mov     r8d, ebx
0x180071530  mov     rcx, rdi
0x180071533  mov     dword ptr [rsp+120h+var_100], esi
0x180071537  lea     edx, [rsi+27h]
0x18007153a  call    sqlite3VdbeAddOp3
0x18007153f  mov     edx, r14d
0x180071542  mov     rcx, rdi
0x180071545  call    sqlite3VdbeResolveLabel
0x18007154a  xor     r9d, r9d
0x18007154d  mov     dword ptr [rsp+120h+var_100], esi
0x180071551  lea     r8d, [rbx+1]
0x180071555  mov     rcx, rdi
0x180071558  lea     edx, [rsi+7Ah]
0x18007155b  call    sqlite3VdbeAddOp3
0x180071560  mov     r8d, ebx
0x180071563  mov     dword ptr [rsp+120h+var_100], esi
0x180071567  jmp     loc_180071876
0x18007156c  mov     eax, [r15+8]
0x180071570  lea     r8, [rbp+57h+var_C8]
0x180071574  mov     [rbx+8], eax
0x180071577  mov     rdx, rbx
0x18007157a  mov     eax, [r15+0Ch]
0x18007157e  mov     rcx, r12
0x180071581  mov     [rbx+0Ch], eax
0x180071584  mov     rax, [r15+60h]
0x180071588  mov     [rbx+60h], rax
0x18007158c  mov     [rbp+57h+arg_8], r13d
0x180071590  call    sqlite3Select
0x180071595  mov     qword ptr [rbx+60h], 0
0x18007159d  mov     r13d, eax
0x1800715a0  test    eax, eax
0x1800715a2  jnz     loc_180071997
0x1800715a8  xor     esi, esi
0x1800715aa  mov     [r15+50h], rsi
0x1800715ae  mov     r8d, [rbx+8]
0x1800715b2  mov     [r15+8], r8d
0x1800715b6  mov     eax, [rbx+0Ch]
0x1800715b9  mov     [r15+0Ch], eax
0x1800715bd  test    r8d, r8d
0x1800715c0  jz      short loc_1800715F7
0x1800715c2  xor     r9d, r9d
0x1800715c5  mov     dword ptr [rsp+120h+var_100], esi
0x1800715c9  lea     edx, [rsi+11h]
0x1800715cc  mov     rcx, rdi
0x1800715cf  call    sqlite3VdbeAddOp3
0x1800715d4  mov     ecx, [r15+0Ch]
0x1800715d8  mov     esi, eax
0x1800715da  test    ecx, ecx
0x1800715dc  jz      short loc_1800715F7
0x1800715de  mov     r8d, [r15+8]
0x1800715e2  lea     r9d, [rcx+1]
0x1800715e6  mov     dword ptr [rsp+120h+var_100], ecx
0x1800715ea  mov     edx, 0A0h
0x1800715ef  mov     rcx, rdi
0x1800715f2  call    sqlite3VdbeAddOp3
0x1800715f7  lea     r8, aUnionAll; "UNION ALL"
0x1800715fe  mov     edx, 1
0x180071603  mov     rcx, r12
0x180071606  call    sqlite3VdbeExplain
0x18007160b  lea     r8, [rbp+57h+var_C8]
0x18007160f  mov     rdx, r15
0x180071612  mov     rcx, r12
0x180071615  call    sqlite3Select
0x18007161a  mov     r10, [r15+50h]
0x18007161e  mov     r13d, eax
0x180071621  movzx   ecx, word ptr [r15+2]
0x180071626  mov     [r15+50h], rbx
0x18007162a  movzx   edx, word ptr [rbx+2]
0x18007162e  mov     [rbp+57h+var_D0], r10
0x180071632  call    sqlite3LogEstAdd
0x180071637  mov     rcx, [r15+60h]
0x18007163b  movzx   r10d, ax
0x18007163f  mov     [r15+2], ax
0x180071644  test    rcx, rcx
0x180071647  jz      short loc_180071672
0x180071649  mov     rcx, [rcx+10h]
0x18007164d  lea     rdx, [rbp+57h+arg_8]
0x180071651  call    sqlite3ExprIsInteger
0x180071656  test    eax, eax
0x180071658  jz      short loc_180071672
0x18007165a  movsxd  rcx, [rbp+57h+arg_8]
0x18007165e  test    ecx, ecx
0x180071660  jle     short loc_180071672
0x180071662  call    sqlite3LogEst
0x180071667  cmp     r10w, ax
0x18007166b  jle     short loc_180071672
0x18007166d  mov     [r15+2], ax
0x180071672  test    esi, esi
  ... truncated ...
```

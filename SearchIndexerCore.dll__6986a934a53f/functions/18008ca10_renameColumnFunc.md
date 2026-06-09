# renameColumnFunc

- ea: `0x18008ca10`
- end: `0x18008cfd5`
- name: `renameColumnFunc`
- size: `1477`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: ``

## callees

- `0x18000509c`
- `0x18000a038`
- `0x18000a180`
- `0x180018f60`
- `0x180018fd0`
- `0x1800191d0`
- `0x18001fe1c`
- `0x1800208bc`
- `0x180024b60`
- `0x180051fd0`
- `0x180053f60`
- `0x1800543d0`
- `0x180070500`
- `0x1800777a0`
- `0x180077a24`
- `0x180077ac4`
- `0x180078968`
- `0x1800789c0`
- `0x18008c928`
- `0x18008ca10`
- `0x18008cfdc`
- `0x18008d078`
- `0x18008d3e4`
- `0x18008d5b0`
- `0x18008de34`
- `0x18008de78`
- `0x18008dff0`
- `0x18009d8b0`

## pseudocode

```c
void *__fastcall renameColumnFunc(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r13
  __int64 v12; // rax
  __int64 v13; // rdx
  _BYTE *v14; // r14
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int8 *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // r15d
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r12
  __int64 v24; // rax
  __int64 v25; // rcx
  void *result; // rax
  __int64 Table; // rax
  __int64 v28; // rsi
  __int64 v29; // r9
  __int64 v30; // r12
  int v31; // ecx
  __int64 v32; // rdx
  __int64 v33; // rbx
  char v34; // al
  __int64 v35; // rbx
  __int64 v36; // rbx
  __int64 v37; // r14
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rsi
  __int64 v41; // rsi
  int v42; // esi
  __int64 v43; // rax
  __int64 v44; // rbx
  int v45; // edi
  int i; // esi
  _DWORD *v47; // r8
  __int64 v48; // r14
  unsigned int v49; // eax
  __int64 v50; // rdx
  _QWORD *v51; // rbx
  __int64 v52; // r8
  __int64 v53; // r8
  unsigned int v54; // eax
  int v55; // [rsp+20h] [rbp-E0h]
  __int128 v57; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v58; // [rsp+48h] [rbp-B8h]
  __int64 v59; // [rsp+58h] [rbp-A8h]
  __int64 v60; // [rsp+60h] [rbp-A0h]
  __int64 v61; // [rsp+68h] [rbp-98h]
  _QWORD *v62; // [rsp+70h] [rbp-90h]
  _OWORD v63[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-58h]
  __int64 v65; // [rsp+B0h] [rbp-50h]
  __int64 v66; // [rsp+B8h] [rbp-48h]
  __int64 v67; // [rsp+C0h] [rbp-40h]
  char v68[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-28h]
  unsigned int v70; // [rsp+E8h] [rbp-18h]
  __int64 v71; // [rsp+188h] [rbp+88h]
  __int64 v72; // [rsp+230h] [rbp+130h]
  __int64 v73; // [rsp+238h] [rbp+138h]
  __int64 v74; // [rsp+240h] [rbp+140h]

  v62 = a3;
  v4 = sqlite3_context_db_handle(a1);
  v5 = *a3;
  LOBYTE(v6) = 1;
  v64 = v4;
  v57 = 0;
  v7 = v4;
  v58 = 0;
  v8 = sqlite3ValueText(v5, v6);
  v9 = a3[3];
  LOBYTE(v10) = 1;
  v11 = v8;
  v61 = v8;
  v12 = sqlite3ValueText(v9, v10);
  LOBYTE(v13) = 1;
  v14 = (_BYTE *)v12;
  v15 = sqlite3ValueText(a3[4], v13);
  v16 = a3[5];
  v17 = (unsigned __int8 *)v15;
  v60 = v15;
  v18 = sqlite3VdbeIntValue(v16);
  LOBYTE(v19) = 1;
  v20 = v18;
  v21 = sqlite3ValueText(a3[6], v19);
  v22 = a3[7];
  v23 = v21;
  v66 = v21;
  v24 = sqlite3VdbeIntValue(v22);
  v25 = a3[8];
  v65 = v24;
  v59 = sqlite3VdbeIntValue(v25);
  result = memset_0(v68, 0, 0x1A8u);
  memset(v63, 0, sizeof(v63));
  if ( v11 && v17 && v23 && v20 >= 0 )
  {
    v67 = *(_QWORD *)(v7 + 512);
    sqlite3BtreeEnterAll(v7);
    Table = sqlite3FindTable(v7, v17, v14);
    v28 = Table;
    if ( !Table || v20 >= *(__int16 *)(Table + 54) )
      return (void *)sqlite3BtreeLeaveAll(v7);
    v29 = v61;
    v30 = *(_QWORD *)(*(_QWORD *)(Table + 8) + 24LL * v20);
    v31 = v20;
    v57 = 0;
    v58 = 0;
    v55 = v59;
    if ( v20 == *(__int16 *)(Table + 52) )
      v31 = -1;
    HIDWORD(v57) = v31;
    *(_QWORD *)(v7 + 512) = 0;
    v32 = (unsigned int)renameParseSql((__int64)v68, (__int64)v14, v7, v29, v55);
    *(_QWORD *)&v58 = v28;
    *(_QWORD *)&v63[0] = v68;
    *((_QWORD *)&v63[0] + 1) = renameColumnExprCb;
    *(_QWORD *)&v63[1] = renameColumnSelectCb;
    *((_QWORD *)&v63[2] + 1) = &v57;
    *(_OWORD *)((char *)&v63[1] + 8) = 0;
    if ( (_DWORD)v32 )
      goto LABEL_61;
    v33 = v72;
    if ( v72 )
    {
      v34 = *(_BYTE *)(v72 + 63);
      if ( v34 == 2 )
      {
        v35 = *(_QWORD *)(v72 + 64);
        *(_DWORD *)(v35 + 4) &= ~0x200000u;
        v70 = 0;
        sqlite3SelectPrep(v68, v35, 0);
        if ( *(_BYTE *)(v7 + 103) )
        {
          v36 = a1;
          v32 = 7;
LABEL_14:
          if ( v69 )
            renameColumnParseError(v36, (unsigned int)&Src, v62[1], v62[2], (__int64)v68);
          else
            sqlite3_result_error_code(v36, v32);
          goto LABEL_66;
        }
        v32 = v70;
        if ( !v70 )
        {
          sqlite3WalkSelect(v63, v35);
          goto LABEL_59;
        }
LABEL_61:
        v36 = a1;
LABEL_62:
        if ( (_DWORD)v32 != 1 || (*(_DWORD *)(v7 + 48) & 0x10000001) != 1 )
          goto LABEL_14;
        sqlite3_result_value(v36, *v62);
LABEL_66:
        renameParseCleanup(v68, v32);
        renameTokenFree(v7, v57);
        *(_QWORD *)(v7 + 512) = v67;
        return (void *)sqlite3BtreeLeaveAll(v7);
      }
      if ( !v34 )
      {
        v37 = v60;
        LODWORD(v59) = sqlite3_stricmp(v60, *(_QWORD *)v72);
        *(_QWORD *)&v58 = v33;
        if ( !(_DWORD)v59 )
        {
          if ( v20 < *(__int16 *)(v33 + 54) )
          {
            renameTokenFind(v68, &v57, *(_QWORD *)(*(_QWORD *)(v33 + 8) + 24LL * v20));
            v33 = v72;
          }
          if ( v57 < 0 )
          {
            renameTokenFind(v68, &v57, v33 + 52);
            v33 = v72;
          }
          sqlite3WalkExprList(v63, *(_QWORD *)(v33 + 32));
          v33 = v72;
          v40 = *(_QWORD *)(v72 + 16);
          if ( v40 )
          {
            do
            {
              sqlite3WalkExprList(v63, *(_QWORD *)(v40 + 80));
              v40 = *(_QWORD *)(v40 + 40);
            }
            while ( v40 );
            v33 = v72;
          }
          v41 = v73;
          if ( v73 )
          {
            do
            {
              sqlite3WalkExprList(v63, *(_QWORD *)(v41 + 80));
              v41 = *(_QWORD *)(v41 + 40);
            }
            while ( v41 );
            v33 = v72;
          }
          v42 = 0;
          if ( *(__int16 *)(v33 + 54) > 0 )
          {
            do
            {
              v43 = sqlite3ColumnExpr(v33, *(_QWORD *)(v33 + 8) + 24LL * v42, v38, v39);
              sqlite3WalkExpr(v63, v43);
              v33 = v72;
              ++v42;
            }
            while ( v42 < *(__int16 *)(v72 + 54) );
          }
        }
        v44 = *(_QWORD *)(v33 + 72);
        if ( v44 )
        {
          v45 = v59;
          do
          {
            for ( i = 0; i < *(_DWORD *)(v44 + 40); ++i )
            {
              if ( !v45 )
              {
                v47 = (_DWORD *)(v44 + 16 * (i + 4LL));
                if ( *v47 == v20 )
                  renameTokenFind(v68, &v57, v47);
              }
              if ( !(unsigned int)sqlite3_stricmp(*(_QWORD *)(v44 + 16), v37) )
              {
                v48 = *(_QWORD *)(v44 + 16LL * i + 72);
                if ( !(unsigned int)sqlite3_stricmp(v48, v30) )
                  renameTokenFind(v68, &v57, v48);
                v37 = v60;
              }
            }
            v44 = *(_QWORD *)(v44 + 8);
          }
          while ( v44 );
          v7 = v64;
        }
      }
    }
    else if ( v73 )
    {
      sqlite3WalkExprList(v63, *(_QWORD *)(v73 + 80));
      sqlite3WalkExpr(v63, *(_QWORD *)(v73 + 72));
    }
    else
    {
      v49 = renameResolveTrigger(v68);
      v32 = v49;
      if ( v49 )
        goto LABEL_61;
      v50 = v74;
      v51 = *(_QWORD **)(v74 + 56);
      if ( v51 )
      {
        do
        {
          v52 = v51[3];
          if ( v52 && sqlite3LocateTable(v68, 0, v52, v14) == v28 )
          {
            v53 = v51[8];
            if ( v53 )
              renameColumnElistNames(v68, &v57, *(_QWORD *)(v53 + 16), v30);
            renameColumnIdlistNames(v68, &v57, v51[7], v30);
            renameColumnElistNames(v68, &v57, v51[6], v30);
          }
          v51 = (_QWORD *)v51[10];
        }
        while ( v51 );
        v50 = v74;
      }
      if ( v71 == v28 )
        renameColumnIdlistNames(v68, &v57, *(_QWORD *)(v50 + 32), v30);
      renameWalkTrigger(v63);
    }
LABEL_59:
    v36 = a1;
    v54 = renameEditSql(a1, (unsigned int)&v57, v61, v66, v65);
    v32 = v54;
    if ( !v54 )
      goto LABEL_66;
    goto LABEL_62;
  }
  return result;
}

```

## disassembly

```asm
0x18008ca10  mov     [rsp-8+arg_8], rbx
0x18008ca15  push    rbp
0x18008ca16  push    rsi
0x18008ca17  push    rdi
0x18008ca18  push    r12
0x18008ca1a  push    r13
0x18008ca1c  push    r14
0x18008ca1e  push    r15
0x18008ca20  lea     rbp, [rsp-190h]
0x18008ca28  sub     rsp, 290h
0x18008ca2f  mov     rax, cs:__security_cookie
0x18008ca36  xor     rax, rsp
0x18008ca39  mov     [rbp+1C0h+var_40], rax
0x18008ca40  mov     rsi, r8
0x18008ca43  mov     [rsp+2C0h+var_250], r8
0x18008ca48  mov     [rsp+2C0h+var_290], rcx
0x18008ca4d  call    sqlite3_context_db_handle
0x18008ca52  mov     rcx, [rsi]
0x18008ca55  xorps   xmm0, xmm0
0x18008ca58  mov     dl, 1
0x18008ca5a  mov     [rbp+1C0h+var_218], rax
0x18008ca5e  movups  [rsp+2C0h+var_288], xmm0
0x18008ca63  mov     rdi, rax
0x18008ca66  movups  [rsp+2C0h+var_278], xmm0
0x18008ca6b  call    sqlite3ValueText
0x18008ca70  mov     rcx, [rsi+18h]
0x18008ca74  mov     dl, 1
0x18008ca76  mov     r13, rax
0x18008ca79  mov     [rsp+2C0h+var_258], rax
0x18008ca7e  call    sqlite3ValueText
0x18008ca83  mov     rcx, [rsi+20h]
0x18008ca87  mov     dl, 1
0x18008ca89  mov     r14, rax
0x18008ca8c  call    sqlite3ValueText
0x18008ca91  mov     rcx, [rsi+28h]
0x18008ca95  mov     rbx, rax
0x18008ca98  mov     [rsp+2C0h+var_260], rax
0x18008ca9d  call    sqlite3VdbeIntValue
0x18008caa2  mov     rcx, [rsi+30h]
0x18008caa6  mov     dl, 1
0x18008caa8  mov     r15, rax
0x18008caab  call    sqlite3ValueText
0x18008cab0  mov     rcx, [rsi+38h]
0x18008cab4  mov     r12, rax
0x18008cab7  mov     [rbp+1C0h+var_208], rax
0x18008cabb  call    sqlite3VdbeIntValue
0x18008cac0  mov     rcx, [rsi+40h]
0x18008cac4  mov     [rbp+1C0h+var_210], rax
0x18008cac8  call    sqlite3VdbeIntValue
0x18008cacd  xor     edx, edx; Val
0x18008cacf  mov     [rsp+2C0h+var_268], rax
0x18008cad4  mov     r8d, 1A8h; Size
0x18008cada  lea     rcx, [rbp+1C0h+var_1F0]; void *
0x18008cade  call    memset_0
0x18008cae3  xorps   xmm0, xmm0
0x18008cae6  movups  [rsp+2C0h+var_248], xmm0
0x18008caeb  movups  [rbp+1C0h+var_238], xmm0
0x18008caef  movups  [rbp+1C0h+var_228], xmm0
0x18008caf3  test    r13, r13
0x18008caf6  jz      loc_18008CFAB
0x18008cafc  test    rbx, rbx
0x18008caff  jz      loc_18008CFAB
0x18008cb05  test    r12, r12
0x18008cb08  jz      loc_18008CFAB
0x18008cb0e  test    r15d, r15d
0x18008cb11  js      loc_18008CFAB
0x18008cb17  mov     rax, [rdi+200h]
0x18008cb1e  mov     rcx, rdi
0x18008cb21  mov     [rbp+1C0h+var_200], rax
0x18008cb25  call    sqlite3BtreeEnterAll
0x18008cb2a  mov     r8, r14
0x18008cb2d  mov     rdx, rbx
0x18008cb30  mov     rcx, rdi
0x18008cb33  call    sqlite3FindTable
0x18008cb38  mov     rsi, rax
0x18008cb3b  test    rax, rax
0x18008cb3e  jz      loc_18008CFA3
0x18008cb44  movsx   ecx, word ptr [rax+36h]
0x18008cb48  cmp     r15d, ecx
0x18008cb4b  jge     loc_18008CFA3
0x18008cb51  mov     r9, [rsp+2C0h+var_258]
0x18008cb56  or      edx, 0FFFFFFFFh
0x18008cb59  xorps   xmm0, xmm0
0x18008cb5c  movsxd  rcx, r15d
0x18008cb5f  mov     r8, rdi
0x18008cb62  lea     r13, [rcx+rcx*2]
0x18008cb66  mov     rcx, [rax+8]
0x18008cb6a  mov     r12, [rcx+r13*8]
0x18008cb6e  mov     ecx, r15d
0x18008cb71  movups  [rsp+2C0h+var_288], xmm0
0x18008cb76  movups  [rsp+2C0h+var_278], xmm0
0x18008cb7b  movsx   eax, word ptr [rax+34h]
0x18008cb7f  cmp     r15d, eax
0x18008cb82  mov     rax, [rsp+2C0h+var_268]
0x18008cb87  mov     [rsp+2C0h+var_2A0], eax
0x18008cb8b  cmovz   ecx, edx
0x18008cb8e  mov     rdx, r14
0x18008cb91  mov     dword ptr [rsp+2C0h+var_288+0Ch], ecx
0x18008cb95  lea     rcx, [rbp+1C0h+var_1F0]
0x18008cb99  mov     qword ptr [rdi+200h], 0
0x18008cba4  call    renameParseSql
0x18008cba9  mov     edx, eax
0x18008cbab  mov     qword ptr [rsp+2C0h+var_278], rsi
0x18008cbb0  lea     rax, [rbp+1C0h+var_1F0]
0x18008cbb4  xorps   xmm0, xmm0
0x18008cbb7  mov     qword ptr [rsp+2C0h+var_248], rax
0x18008cbbc  lea     rax, renameColumnExprCb
0x18008cbc3  mov     qword ptr [rbp+1C0h+var_248+8], rax
0x18008cbc7  lea     rax, renameColumnSelectCb
0x18008cbce  mov     qword ptr [rbp+1C0h+var_238], rax
0x18008cbd2  lea     rax, [rsp+2C0h+var_288]
0x18008cbd7  mov     qword ptr [rbp+1C0h+var_228+8], rax
0x18008cbdb  movdqu  [rbp+1C0h+var_238+8], xmm0
0x18008cbe0  test    edx, edx
0x18008cbe2  jnz     loc_18008CF4B
0x18008cbe8  mov     rbx, [rbp+1C0h+var_90]
0x18008cbef  test    rbx, rbx
0x18008cbf2  jz      loc_18008CE26
0x18008cbf8  mov     al, [rbx+3Fh]
0x18008cbfb  cmp     al, 2
0x18008cbfd  jnz     short loc_18008CC7C
0x18008cbff  mov     rbx, [rbx+40h]
0x18008cc03  lea     rcx, [rbp+1C0h+var_1F0]
0x18008cc07  xor     r8d, r8d
0x18008cc0a  btr     dword ptr [rbx+4], 15h
0x18008cc0f  mov     [rbp+1C0h+var_1D8], edx
0x18008cc12  mov     rdx, rbx
0x18008cc15  call    sqlite3SelectPrep
0x18008cc1a  cmp     byte ptr [rdi+67h], 0
0x18008cc1e  jz      short loc_18008CC5F
0x18008cc20  mov     rbx, [rsp+2C0h+var_290]
0x18008cc25  mov     edx, 7
0x18008cc2a  cmp     [rbp+1C0h+var_1E8], 0
0x18008cc2f  mov     rcx, rbx
0x18008cc32  jz      loc_18008CF7D
0x18008cc38  mov     r8, [rsp+2C0h+var_250]
0x18008cc3d  lea     rax, [rbp+1C0h+var_1F0]
0x18008cc41  lea     rdx, Src
0x18008cc48  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18008cc4d  mov     r9, [r8+10h]
0x18008cc51  mov     r8, [r8+8]
0x18008cc55  call    renameColumnParseError
0x18008cc5a  jmp     loc_18008CF82
0x18008cc5f  mov     edx, [rbp+1C0h+var_1D8]
0x18008cc62  test    edx, edx
0x18008cc64  jnz     loc_18008CF4B
0x18008cc6a  mov     rdx, rbx
0x18008cc6d  lea     rcx, [rsp+2C0h+var_248]
0x18008cc72  call    sqlite3WalkSelect
0x18008cc77  jmp     loc_18008CF20
0x18008cc7c  test    al, al
0x18008cc7e  jnz     loc_18008CF20
0x18008cc84  mov     r14, [rsp+2C0h+var_260]
0x18008cc89  mov     rdx, [rbx]
0x18008cc8c  mov     rcx, r14
0x18008cc8f  call    sqlite3_stricmp
0x18008cc94  mov     dword ptr [rsp+2C0h+var_268], eax
0x18008cc98  mov     qword ptr [rsp+2C0h+var_278], rbx
0x18008cc9d  test    eax, eax
0x18008cc9f  jnz     loc_18008CD90
0x18008cca5  movsx   ecx, word ptr [rbx+36h]
0x18008cca9  cmp     r15d, ecx
0x18008ccac  jge     short loc_18008CCCB
0x18008ccae  mov     r8, [rbx+8]
0x18008ccb2  lea     rdx, [rsp+2C0h+var_288]
0x18008ccb7  lea     rcx, [rbp+1C0h+var_1F0]
0x18008ccbb  mov     r8, [r8+r13*8]
0x18008ccbf  call    renameTokenFind
0x18008ccc4  mov     rbx, [rbp+1C0h+var_90]
0x18008cccb  cmp     dword ptr [rsp+2C0h+var_288+0Ch], 0
0x18008ccd0  jge     short loc_18008CCEB
0x18008ccd2  lea     r8, [rbx+34h]
0x18008ccd6  lea     rdx, [rsp+2C0h+var_288]
0x18008ccdb  lea     rcx, [rbp+1C0h+var_1F0]
0x18008ccdf  call    renameTokenFind
0x18008cce4  mov     rbx, [rbp+1C0h+var_90]
0x18008cceb  mov     rdx, [rbx+20h]
0x18008ccef  lea     rcx, [rsp+2C0h+var_248]
0x18008ccf4  call    sqlite3WalkExprList
0x18008ccf9  mov     rbx, [rbp+1C0h+var_90]
0x18008cd00  mov     rsi, [rbx+10h]
0x18008cd04  test    rsi, rsi
0x18008cd07  jz      short loc_18008CD27
0x18008cd09  mov     rdx, [rsi+50h]
0x18008cd0d  lea     rcx, [rsp+2C0h+var_248]
0x18008cd12  call    sqlite3WalkExprList
0x18008cd17  mov     rsi, [rsi+28h]
0x18008cd1b  test    rsi, rsi
0x18008cd1e  jnz     short loc_18008CD09
0x18008cd20  mov     rbx, [rbp+1C0h+var_90]
0x18008cd27  mov     rsi, [rbp+1C0h+var_88]
0x18008cd2e  test    rsi, rsi
0x18008cd31  jz      short loc_18008CD51
0x18008cd33  mov     rdx, [rsi+50h]
0x18008cd37  lea     rcx, [rsp+2C0h+var_248]
0x18008cd3c  call    sqlite3WalkExprList
0x18008cd41  mov     rsi, [rsi+28h]
0x18008cd45  test    rsi, rsi
0x18008cd48  jnz     short loc_18008CD33
0x18008cd4a  mov     rbx, [rbp+1C0h+var_90]
0x18008cd51  xor     esi, esi
0x18008cd53  xor     eax, eax
0x18008cd55  cmp     ax, [rbx+36h]
0x18008cd59  jge     short loc_18008CD90
0x18008cd5b  movsxd  rax, esi
0x18008cd5e  lea     rcx, [rax+rax*2]
0x18008cd62  mov     rax, [rbx+8]
0x18008cd66  lea     rdx, [rax+rcx*8]
0x18008cd6a  mov     rcx, rbx
0x18008cd6d  call    sqlite3ColumnExpr
0x18008cd72  mov     rdx, rax
0x18008cd75  lea     rcx, [rsp+2C0h+var_248]
0x18008cd7a  call    sqlite3WalkExpr
0x18008cd7f  mov     rbx, [rbp+1C0h+var_90]
0x18008cd86  inc     esi
0x18008cd88  movsx   eax, word ptr [rbx+36h]
0x18008cd8c  cmp     esi, eax
0x18008cd8e  jl      short loc_18008CD5B
0x18008cd90  mov     rbx, [rbx+48h]
0x18008cd94  test    rbx, rbx
0x18008cd97  jz      loc_18008CF20
0x18008cd9d  mov     edi, dword ptr [rsp+2C0h+var_268]
0x18008cda1  xor     esi, esi
0x18008cda3  cmp     [rbx+28h], esi
0x18008cda6  jle     short loc_18008CE14
0x18008cda8  test    edi, edi
0x18008cdaa  jnz     short loc_18008CDCD
0x18008cdac  movsxd  r8, esi
0x18008cdaf  add     r8, 4
0x18008cdb3  shl     r8, 4
0x18008cdb7  add     r8, rbx
0x18008cdba  cmp     [r8], r15d
0x18008cdbd  jnz     short loc_18008CDCD
0x18008cdbf  lea     rdx, [rsp+2C0h+var_288]
0x18008cdc4  lea     rcx, [rbp+1C0h+var_1F0]
0x18008cdc8  call    renameTokenFind
0x18008cdcd  mov     rcx, [rbx+10h]
0x18008cdd1  mov     rdx, r14
0x18008cdd4  call    sqlite3_stricmp
0x18008cdd9  test    eax, eax
0x18008cddb  jnz     short loc_18008CE0D
0x18008cddd  movsxd  rax, esi
0x18008cde0  mov     rdx, r12
0x18008cde3  add     rax, rax
0x18008cde6  mov     r14, [rbx+rax*8+48h]
0x18008cdeb  mov     rcx, r14
0x18008cdee  call    sqlite3_stricmp
0x18008cdf3  test    eax, eax
0x18008cdf5  jnz     short loc_18008CE08
0x18008cdf7  mov     r8, r14
0x18008cdfa  lea     rdx, [rsp+2C0h+var_288]
0x18008cdff  lea     rcx, [rbp+1C0h+var_1F0]
0x18008ce03  call    renameTokenFind
0x18008ce08  mov     r14, [rsp+2C0h+var_260]
0x18008ce0d  inc     esi
0x18008ce0f  cmp     esi, [rbx+28h]
0x18008ce12  jl      short loc_18008CDA8
0x18008ce14  mov     rbx, [rbx+8]
0x18008ce18  test    rbx, rbx
0x18008ce1b  jnz     short loc_18008CDA1
0x18008ce1d  mov     rdi, [rbp+1C0h+var_218]
0x18008ce21  jmp     loc_18008CF20
0x18008ce26  mov     rdx, [rbp+1C0h+var_88]
0x18008ce2d  test    rdx, rdx
0x18008ce30  jz      short loc_18008CE5A
0x18008ce32  mov     rdx, [rdx+50h]
0x18008ce36  lea     rcx, [rsp+2C0h+var_248]
0x18008ce3b  call    sqlite3WalkExprList
0x18008ce40  mov     rdx, [rbp+1C0h+var_88]
0x18008ce47  lea     rcx, [rsp+2C0h+var_248]
0x18008ce4c  mov     rdx, [rdx+48h]
0x18008ce50  call    sqlite3WalkExpr
0x18008ce55  jmp     loc_18008CF20
0x18008ce5a  lea     rcx, [rbp+1C0h+var_1F0]
0x18008ce5e  call    renameResolveTrigger
0x18008ce63  mov     edx, eax
0x18008ce65  test    eax, eax
0x18008ce67  jnz     loc_18008CF4B
0x18008ce6d  mov     rdx, [rbp+1C0h+var_80]
0x18008ce74  mov     rbx, [rdx+38h]
0x18008ce78  test    rbx, rbx
0x18008ce7b  jz      short loc_18008CEF1
0x18008ce7d  mov     r8, [rbx+18h]
0x18008ce81  test    r8, r8
0x18008ce84  jz      short loc_18008CEE1
0x18008ce86  mov     r9, r14
0x18008ce89  lea     rcx, [rbp+1C0h+var_1F0]
0x18008ce8d  xor     edx, edx
0x18008ce8f  call    sqlite3LocateTable
0x18008ce94  cmp     rax, rsi
0x18008ce97  jnz     short loc_18008CEE1
0x18008ce99  mov     r8, [rbx+40h]
0x18008ce9d  test    r8, r8
0x18008cea0  jz      short loc_18008CEB7
0x18008cea2  mov     r8, [r8+10h]
0x18008cea6  lea     rdx, [rsp+2C0h+var_288]
0x18008ceab  mov     r9, r12
0x18008ceae  lea     rcx, [rbp+1C0h+var_1F0]
0x18008ceb2  call    renameColumnElistNames
0x18008ceb7  mov     r8, [rbx+38h]
  ... truncated ...
```

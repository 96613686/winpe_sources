# renameColumnFunc

- ea: `0x18007d6a0`
- end: `0x18007dc65`
- name: `renameColumnFunc`
- size: `1477`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: ``

## callees

- `0x18000e5c0`
- `0x18000e790`
- `0x18000e7f0`
- `0x180013c28`
- `0x180014434`
- `0x180014b90`
- `0x180028540`
- `0x180039850`
- `0x180047bbc`
- `0x180047c2c`
- `0x180047fb0`
- `0x180048d20`
- `0x18006170c`
- `0x180065930`
- `0x180065bf4`
- `0x180065c94`
- `0x1800680a0`
- `0x180068880`
- `0x18006910e`
- `0x18007d5b8`
- `0x18007d6a0`
- `0x18007dc6c`
- `0x18007dd08`
- `0x18007e074`
- `0x18007e240`
- `0x18007ead8`
- `0x18007eb1c`
- `0x18007eca4`

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
  __int64 v14; // r14
  __int64 v15; // rax
  __int64 v16; // rcx
  _BYTE *v17; // rbx
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
  __int64 v38; // rsi
  __int64 v39; // rsi
  int v40; // esi
  __int64 v41; // rax
  __int64 v42; // rbx
  int v43; // edi
  int i; // esi
  _DWORD *v45; // r8
  __int64 v46; // r14
  unsigned int v47; // eax
  __int64 v48; // rdx
  _QWORD *v49; // rbx
  __int64 v50; // r8
  __int64 v51; // r8
  unsigned int v52; // eax
  int v53; // [rsp+20h] [rbp-E0h]
  __int128 v55; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v56; // [rsp+48h] [rbp-B8h]
  __int64 v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h]
  __int64 v59; // [rsp+68h] [rbp-98h]
  _QWORD *v60; // [rsp+70h] [rbp-90h]
  _OWORD v61[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  char v66[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-28h]
  unsigned int v68; // [rsp+E8h] [rbp-18h]
  __int64 v69; // [rsp+188h] [rbp+88h]
  __int64 v70; // [rsp+230h] [rbp+130h]
  __int64 v71; // [rsp+238h] [rbp+138h]
  __int64 v72; // [rsp+240h] [rbp+140h]

  v60 = a3;
  v4 = sqlite3_context_db_handle(a1);
  v5 = *a3;
  LOBYTE(v6) = 1;
  v62 = v4;
  v55 = 0;
  v7 = v4;
  v56 = 0;
  v8 = sqlite3ValueText(v5, v6);
  v9 = a3[3];
  LOBYTE(v10) = 1;
  v11 = v8;
  v59 = v8;
  v12 = sqlite3ValueText(v9, v10);
  LOBYTE(v13) = 1;
  v14 = v12;
  v15 = sqlite3ValueText(a3[4], v13);
  v16 = a3[5];
  v17 = (_BYTE *)v15;
  v58 = v15;
  v18 = sqlite3_value_int64(v16);
  LOBYTE(v19) = 1;
  v20 = v18;
  v21 = sqlite3ValueText(a3[6], v19);
  v22 = a3[7];
  v23 = v21;
  v64 = v21;
  v24 = sqlite3_value_int64(v22);
  v25 = a3[8];
  v63 = v24;
  v57 = sqlite3_value_int64(v25);
  result = memset_0(v66, 0, 0x1A8u);
  memset(v61, 0, sizeof(v61));
  if ( v11 && v17 && v23 && v20 >= 0 )
  {
    v65 = *(_QWORD *)(v7 + 512);
    sqlite3BtreeEnterAll(v7);
    Table = sqlite3FindTable(v7, v17, v14);
    v28 = Table;
    if ( !Table || v20 >= *(__int16 *)(Table + 54) )
      return (void *)sqlite3BtreeLeaveAll(v7);
    v29 = v59;
    v30 = *(_QWORD *)(*(_QWORD *)(Table + 8) + 24LL * v20);
    v31 = v20;
    v55 = 0;
    v56 = 0;
    v53 = v57;
    if ( v20 == *(__int16 *)(Table + 52) )
      v31 = -1;
    HIDWORD(v55) = v31;
    *(_QWORD *)(v7 + 512) = 0;
    v32 = (unsigned int)renameParseSql((__int64)v66, v14, v7, v29, v53);
    *(_QWORD *)&v56 = v28;
    *(_QWORD *)&v61[0] = v66;
    *((_QWORD *)&v61[0] + 1) = renameColumnExprCb;
    *(_QWORD *)&v61[1] = renameColumnSelectCb;
    *((_QWORD *)&v61[2] + 1) = &v55;
    *(_OWORD *)((char *)&v61[1] + 8) = 0;
    if ( (_DWORD)v32 )
      goto LABEL_61;
    v33 = v70;
    if ( v70 )
    {
      v34 = *(_BYTE *)(v70 + 63);
      if ( v34 == 2 )
      {
        v35 = *(_QWORD *)(v70 + 64);
        *(_DWORD *)(v35 + 4) &= ~0x200000u;
        v68 = 0;
        sqlite3SelectPrep(v66, v35, 0);
        if ( *(_BYTE *)(v7 + 103) )
        {
          v36 = a1;
          v32 = 7;
LABEL_14:
          if ( v67 )
            renameColumnParseError(v36, (unsigned int)byte_18009EEF0, v60[1], v60[2], (__int64)v66);
          else
            sqlite3_result_error_code(v36, v32);
          goto LABEL_66;
        }
        v32 = v68;
        if ( !v68 )
        {
          sqlite3WalkSelect(v61, v35);
          goto LABEL_59;
        }
LABEL_61:
        v36 = a1;
LABEL_62:
        if ( (_DWORD)v32 != 1 || (*(_DWORD *)(v7 + 48) & 0x10000001) != 1 )
          goto LABEL_14;
        sqlite3_result_value(v36, *v60);
LABEL_66:
        renameParseCleanup(v66, v32);
        renameTokenFree(v7, v55);
        *(_QWORD *)(v7 + 512) = v65;
        return (void *)sqlite3BtreeLeaveAll(v7);
      }
      if ( !v34 )
      {
        v37 = v58;
        LODWORD(v57) = sqlite3_stricmp(v58, *(_QWORD *)v70);
        *(_QWORD *)&v56 = v33;
        if ( !(_DWORD)v57 )
        {
          if ( v20 < *(__int16 *)(v33 + 54) )
          {
            renameTokenFind(v66, &v55, *(_QWORD *)(*(_QWORD *)(v33 + 8) + 24LL * v20));
            v33 = v70;
          }
          if ( v55 < 0 )
          {
            renameTokenFind(v66, &v55, v33 + 52);
            v33 = v70;
          }
          sqlite3WalkExprList(v61, *(_QWORD *)(v33 + 32));
          v33 = v70;
          v38 = *(_QWORD *)(v70 + 16);
          if ( v38 )
          {
            do
            {
              sqlite3WalkExprList(v61, *(_QWORD *)(v38 + 80));
              v38 = *(_QWORD *)(v38 + 40);
            }
            while ( v38 );
            v33 = v70;
          }
          v39 = v71;
          if ( v71 )
          {
            do
            {
              sqlite3WalkExprList(v61, *(_QWORD *)(v39 + 80));
              v39 = *(_QWORD *)(v39 + 40);
            }
            while ( v39 );
            v33 = v70;
          }
          v40 = 0;
          if ( *(__int16 *)(v33 + 54) > 0 )
          {
            do
            {
              v41 = sqlite3ColumnExpr(v33);
              sqlite3WalkExpr(v61, v41);
              v33 = v70;
              ++v40;
            }
            while ( v40 < *(__int16 *)(v70 + 54) );
          }
        }
        v42 = *(_QWORD *)(v33 + 72);
        if ( v42 )
        {
          v43 = v57;
          do
          {
            for ( i = 0; i < *(_DWORD *)(v42 + 40); ++i )
            {
              if ( !v43 )
              {
                v45 = (_DWORD *)(v42 + 16 * (i + 4LL));
                if ( *v45 == v20 )
                  renameTokenFind(v66, &v55, v45);
              }
              if ( !(unsigned int)sqlite3_stricmp(*(_QWORD *)(v42 + 16), v37) )
              {
                v46 = *(_QWORD *)(v42 + 16LL * i + 72);
                if ( !(unsigned int)sqlite3_stricmp(v46, v30) )
                  renameTokenFind(v66, &v55, v46);
                v37 = v58;
              }
            }
            v42 = *(_QWORD *)(v42 + 8);
          }
          while ( v42 );
          v7 = v62;
        }
      }
    }
    else if ( v71 )
    {
      sqlite3WalkExprList(v61, *(_QWORD *)(v71 + 80));
      sqlite3WalkExpr(v61, *(_QWORD *)(v71 + 72));
    }
    else
    {
      v47 = renameResolveTrigger(v66);
      v32 = v47;
      if ( v47 )
        goto LABEL_61;
      v48 = v72;
      v49 = *(_QWORD **)(v72 + 56);
      if ( v49 )
      {
        do
        {
          v50 = v49[3];
          if ( v50 && sqlite3LocateTable(v66, 0, v50, v14) == v28 )
          {
            v51 = v49[8];
            if ( v51 )
              renameColumnElistNames(v66, &v55, *(_QWORD *)(v51 + 16), v30);
            renameColumnIdlistNames(v66, &v55, v49[7], v30);
            renameColumnElistNames(v66, &v55, v49[6], v30);
          }
          v49 = (_QWORD *)v49[10];
        }
        while ( v49 );
        v48 = v72;
      }
      if ( v69 == v28 )
        renameColumnIdlistNames(v66, &v55, *(_QWORD *)(v48 + 32), v30);
      renameWalkTrigger(v61);
    }
LABEL_59:
    v36 = a1;
    v52 = renameEditSql(a1, (unsigned int)&v55, v59, v64, v63);
    v32 = v52;
    if ( !v52 )
      goto LABEL_66;
    goto LABEL_62;
  }
  return result;
}

```

## disassembly

```asm
0x18007d6a0  mov     [rsp-8+arg_8], rbx
0x18007d6a5  push    rbp
0x18007d6a6  push    rsi
0x18007d6a7  push    rdi
0x18007d6a8  push    r12
0x18007d6aa  push    r13
0x18007d6ac  push    r14
0x18007d6ae  push    r15
0x18007d6b0  lea     rbp, [rsp-190h]
0x18007d6b8  sub     rsp, 290h
0x18007d6bf  mov     rax, cs:__security_cookie
0x18007d6c6  xor     rax, rsp
0x18007d6c9  mov     [rbp+1C0h+var_40], rax
0x18007d6d0  mov     rsi, r8
0x18007d6d3  mov     [rsp+2C0h+var_250], r8
0x18007d6d8  mov     [rsp+2C0h+var_290], rcx
0x18007d6dd  call    sqlite3_context_db_handle
0x18007d6e2  mov     rcx, [rsi]
0x18007d6e5  xorps   xmm0, xmm0
0x18007d6e8  mov     dl, 1
0x18007d6ea  mov     [rbp+1C0h+var_218], rax
0x18007d6ee  movups  [rsp+2C0h+var_288], xmm0
0x18007d6f3  mov     rdi, rax
0x18007d6f6  movups  [rsp+2C0h+var_278], xmm0
0x18007d6fb  call    sqlite3ValueText
0x18007d700  mov     rcx, [rsi+18h]
0x18007d704  mov     dl, 1
0x18007d706  mov     r13, rax
0x18007d709  mov     [rsp+2C0h+var_258], rax
0x18007d70e  call    sqlite3ValueText
0x18007d713  mov     rcx, [rsi+20h]
0x18007d717  mov     dl, 1
0x18007d719  mov     r14, rax
0x18007d71c  call    sqlite3ValueText
0x18007d721  mov     rcx, [rsi+28h]
0x18007d725  mov     rbx, rax
0x18007d728  mov     [rsp+2C0h+var_260], rax
0x18007d72d  call    sqlite3_value_int64
0x18007d732  mov     rcx, [rsi+30h]
0x18007d736  mov     dl, 1
0x18007d738  mov     r15, rax
0x18007d73b  call    sqlite3ValueText
0x18007d740  mov     rcx, [rsi+38h]
0x18007d744  mov     r12, rax
0x18007d747  mov     [rbp+1C0h+var_208], rax
0x18007d74b  call    sqlite3_value_int64
0x18007d750  mov     rcx, [rsi+40h]
0x18007d754  mov     [rbp+1C0h+var_210], rax
0x18007d758  call    sqlite3_value_int64
0x18007d75d  xor     edx, edx; Val
0x18007d75f  mov     [rsp+2C0h+var_268], rax
0x18007d764  mov     r8d, 1A8h; Size
0x18007d76a  lea     rcx, [rbp+1C0h+var_1F0]; void *
0x18007d76e  call    memset_0
0x18007d773  xorps   xmm0, xmm0
0x18007d776  movups  [rsp+2C0h+var_248], xmm0
0x18007d77b  movups  [rbp+1C0h+var_238], xmm0
0x18007d77f  movups  [rbp+1C0h+var_228], xmm0
0x18007d783  test    r13, r13
0x18007d786  jz      loc_18007DC3B
0x18007d78c  test    rbx, rbx
0x18007d78f  jz      loc_18007DC3B
0x18007d795  test    r12, r12
0x18007d798  jz      loc_18007DC3B
0x18007d79e  test    r15d, r15d
0x18007d7a1  js      loc_18007DC3B
0x18007d7a7  mov     rax, [rdi+200h]
0x18007d7ae  mov     rcx, rdi
0x18007d7b1  mov     [rbp+1C0h+var_200], rax
0x18007d7b5  call    sqlite3BtreeEnterAll
0x18007d7ba  mov     r8, r14
0x18007d7bd  mov     rdx, rbx
0x18007d7c0  mov     rcx, rdi
0x18007d7c3  call    sqlite3FindTable
0x18007d7c8  mov     rsi, rax
0x18007d7cb  test    rax, rax
0x18007d7ce  jz      loc_18007DC33
0x18007d7d4  movsx   ecx, word ptr [rax+36h]
0x18007d7d8  cmp     r15d, ecx
0x18007d7db  jge     loc_18007DC33
0x18007d7e1  mov     r9, [rsp+2C0h+var_258]
0x18007d7e6  or      edx, 0FFFFFFFFh
0x18007d7e9  xorps   xmm0, xmm0
0x18007d7ec  movsxd  rcx, r15d
0x18007d7ef  mov     r8, rdi
0x18007d7f2  lea     r13, [rcx+rcx*2]
0x18007d7f6  mov     rcx, [rax+8]
0x18007d7fa  mov     r12, [rcx+r13*8]
0x18007d7fe  mov     ecx, r15d
0x18007d801  movups  [rsp+2C0h+var_288], xmm0
0x18007d806  movups  [rsp+2C0h+var_278], xmm0
0x18007d80b  movsx   eax, word ptr [rax+34h]
0x18007d80f  cmp     r15d, eax
0x18007d812  mov     rax, [rsp+2C0h+var_268]
0x18007d817  mov     [rsp+2C0h+var_2A0], eax
0x18007d81b  cmovz   ecx, edx
0x18007d81e  mov     rdx, r14
0x18007d821  mov     dword ptr [rsp+2C0h+var_288+0Ch], ecx
0x18007d825  lea     rcx, [rbp+1C0h+var_1F0]
0x18007d829  mov     qword ptr [rdi+200h], 0
0x18007d834  call    renameParseSql
0x18007d839  mov     edx, eax
0x18007d83b  mov     qword ptr [rsp+2C0h+var_278], rsi
0x18007d840  lea     rax, [rbp+1C0h+var_1F0]
0x18007d844  xorps   xmm0, xmm0
0x18007d847  mov     qword ptr [rsp+2C0h+var_248], rax
0x18007d84c  lea     rax, renameColumnExprCb
0x18007d853  mov     qword ptr [rbp+1C0h+var_248+8], rax
0x18007d857  lea     rax, renameColumnSelectCb
0x18007d85e  mov     qword ptr [rbp+1C0h+var_238], rax
0x18007d862  lea     rax, [rsp+2C0h+var_288]
0x18007d867  mov     qword ptr [rbp+1C0h+var_228+8], rax
0x18007d86b  movdqu  [rbp+1C0h+var_238+8], xmm0
0x18007d870  test    edx, edx
0x18007d872  jnz     loc_18007DBDB
0x18007d878  mov     rbx, [rbp+1C0h+var_90]
0x18007d87f  test    rbx, rbx
0x18007d882  jz      loc_18007DAB6
0x18007d888  mov     al, [rbx+3Fh]
0x18007d88b  cmp     al, 2
0x18007d88d  jnz     short loc_18007D90C
0x18007d88f  mov     rbx, [rbx+40h]
0x18007d893  lea     rcx, [rbp+1C0h+var_1F0]
0x18007d897  xor     r8d, r8d
0x18007d89a  btr     dword ptr [rbx+4], 15h
0x18007d89f  mov     [rbp+1C0h+var_1D8], edx
0x18007d8a2  mov     rdx, rbx
0x18007d8a5  call    sqlite3SelectPrep
0x18007d8aa  cmp     byte ptr [rdi+67h], 0
0x18007d8ae  jz      short loc_18007D8EF
0x18007d8b0  mov     rbx, [rsp+2C0h+var_290]
0x18007d8b5  mov     edx, 7
0x18007d8ba  cmp     [rbp+1C0h+var_1E8], 0
0x18007d8bf  mov     rcx, rbx
0x18007d8c2  jz      loc_18007DC0D
0x18007d8c8  mov     r8, [rsp+2C0h+var_250]
0x18007d8cd  lea     rax, [rbp+1C0h+var_1F0]
0x18007d8d1  lea     rdx, byte_18009EEF0
0x18007d8d8  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18007d8dd  mov     r9, [r8+10h]
0x18007d8e1  mov     r8, [r8+8]
0x18007d8e5  call    renameColumnParseError
0x18007d8ea  jmp     loc_18007DC12
0x18007d8ef  mov     edx, [rbp+1C0h+var_1D8]
0x18007d8f2  test    edx, edx
0x18007d8f4  jnz     loc_18007DBDB
0x18007d8fa  mov     rdx, rbx
0x18007d8fd  lea     rcx, [rsp+2C0h+var_248]
0x18007d902  call    sqlite3WalkSelect
0x18007d907  jmp     loc_18007DBB0
0x18007d90c  test    al, al
0x18007d90e  jnz     loc_18007DBB0
0x18007d914  mov     r14, [rsp+2C0h+var_260]
0x18007d919  mov     rdx, [rbx]
0x18007d91c  mov     rcx, r14
0x18007d91f  call    sqlite3_stricmp
0x18007d924  mov     dword ptr [rsp+2C0h+var_268], eax
0x18007d928  mov     qword ptr [rsp+2C0h+var_278], rbx
0x18007d92d  test    eax, eax
0x18007d92f  jnz     loc_18007DA20
0x18007d935  movsx   ecx, word ptr [rbx+36h]
0x18007d939  cmp     r15d, ecx
0x18007d93c  jge     short loc_18007D95B
0x18007d93e  mov     r8, [rbx+8]
0x18007d942  lea     rdx, [rsp+2C0h+var_288]
0x18007d947  lea     rcx, [rbp+1C0h+var_1F0]
0x18007d94b  mov     r8, [r8+r13*8]
0x18007d94f  call    renameTokenFind
0x18007d954  mov     rbx, [rbp+1C0h+var_90]
0x18007d95b  cmp     dword ptr [rsp+2C0h+var_288+0Ch], 0
0x18007d960  jge     short loc_18007D97B
0x18007d962  lea     r8, [rbx+34h]
0x18007d966  lea     rdx, [rsp+2C0h+var_288]
0x18007d96b  lea     rcx, [rbp+1C0h+var_1F0]
0x18007d96f  call    renameTokenFind
0x18007d974  mov     rbx, [rbp+1C0h+var_90]
0x18007d97b  mov     rdx, [rbx+20h]
0x18007d97f  lea     rcx, [rsp+2C0h+var_248]
0x18007d984  call    sqlite3WalkExprList
0x18007d989  mov     rbx, [rbp+1C0h+var_90]
0x18007d990  mov     rsi, [rbx+10h]
0x18007d994  test    rsi, rsi
0x18007d997  jz      short loc_18007D9B7
0x18007d999  mov     rdx, [rsi+50h]
0x18007d99d  lea     rcx, [rsp+2C0h+var_248]
0x18007d9a2  call    sqlite3WalkExprList
0x18007d9a7  mov     rsi, [rsi+28h]
0x18007d9ab  test    rsi, rsi
0x18007d9ae  jnz     short loc_18007D999
0x18007d9b0  mov     rbx, [rbp+1C0h+var_90]
0x18007d9b7  mov     rsi, [rbp+1C0h+var_88]
0x18007d9be  test    rsi, rsi
0x18007d9c1  jz      short loc_18007D9E1
0x18007d9c3  mov     rdx, [rsi+50h]
0x18007d9c7  lea     rcx, [rsp+2C0h+var_248]
0x18007d9cc  call    sqlite3WalkExprList
0x18007d9d1  mov     rsi, [rsi+28h]
0x18007d9d5  test    rsi, rsi
0x18007d9d8  jnz     short loc_18007D9C3
0x18007d9da  mov     rbx, [rbp+1C0h+var_90]
0x18007d9e1  xor     esi, esi
0x18007d9e3  xor     eax, eax
0x18007d9e5  cmp     ax, [rbx+36h]
0x18007d9e9  jge     short loc_18007DA20
0x18007d9eb  movsxd  rax, esi
0x18007d9ee  lea     rcx, [rax+rax*2]
0x18007d9f2  mov     rax, [rbx+8]
0x18007d9f6  lea     rdx, [rax+rcx*8]
0x18007d9fa  mov     rcx, rbx
0x18007d9fd  call    sqlite3ColumnExpr
0x18007da02  mov     rdx, rax
0x18007da05  lea     rcx, [rsp+2C0h+var_248]
0x18007da0a  call    sqlite3WalkExpr
0x18007da0f  mov     rbx, [rbp+1C0h+var_90]
0x18007da16  inc     esi
0x18007da18  movsx   eax, word ptr [rbx+36h]
0x18007da1c  cmp     esi, eax
0x18007da1e  jl      short loc_18007D9EB
0x18007da20  mov     rbx, [rbx+48h]
0x18007da24  test    rbx, rbx
0x18007da27  jz      loc_18007DBB0
0x18007da2d  mov     edi, dword ptr [rsp+2C0h+var_268]
0x18007da31  xor     esi, esi
0x18007da33  cmp     [rbx+28h], esi
0x18007da36  jle     short loc_18007DAA4
0x18007da38  test    edi, edi
0x18007da3a  jnz     short loc_18007DA5D
0x18007da3c  movsxd  r8, esi
0x18007da3f  add     r8, 4
0x18007da43  shl     r8, 4
0x18007da47  add     r8, rbx
0x18007da4a  cmp     [r8], r15d
0x18007da4d  jnz     short loc_18007DA5D
0x18007da4f  lea     rdx, [rsp+2C0h+var_288]
0x18007da54  lea     rcx, [rbp+1C0h+var_1F0]
0x18007da58  call    renameTokenFind
0x18007da5d  mov     rcx, [rbx+10h]
0x18007da61  mov     rdx, r14
0x18007da64  call    sqlite3_stricmp
0x18007da69  test    eax, eax
0x18007da6b  jnz     short loc_18007DA9D
0x18007da6d  movsxd  rax, esi
0x18007da70  mov     rdx, r12
0x18007da73  add     rax, rax
0x18007da76  mov     r14, [rbx+rax*8+48h]
0x18007da7b  mov     rcx, r14
0x18007da7e  call    sqlite3_stricmp
0x18007da83  test    eax, eax
0x18007da85  jnz     short loc_18007DA98
0x18007da87  mov     r8, r14
0x18007da8a  lea     rdx, [rsp+2C0h+var_288]
0x18007da8f  lea     rcx, [rbp+1C0h+var_1F0]
0x18007da93  call    renameTokenFind
0x18007da98  mov     r14, [rsp+2C0h+var_260]
0x18007da9d  inc     esi
0x18007da9f  cmp     esi, [rbx+28h]
0x18007daa2  jl      short loc_18007DA38
0x18007daa4  mov     rbx, [rbx+8]
0x18007daa8  test    rbx, rbx
0x18007daab  jnz     short loc_18007DA31
0x18007daad  mov     rdi, [rbp+1C0h+var_218]
0x18007dab1  jmp     loc_18007DBB0
0x18007dab6  mov     rdx, [rbp+1C0h+var_88]
0x18007dabd  test    rdx, rdx
0x18007dac0  jz      short loc_18007DAEA
0x18007dac2  mov     rdx, [rdx+50h]
0x18007dac6  lea     rcx, [rsp+2C0h+var_248]
0x18007dacb  call    sqlite3WalkExprList
0x18007dad0  mov     rdx, [rbp+1C0h+var_88]
0x18007dad7  lea     rcx, [rsp+2C0h+var_248]
0x18007dadc  mov     rdx, [rdx+48h]
0x18007dae0  call    sqlite3WalkExpr
0x18007dae5  jmp     loc_18007DBB0
0x18007daea  lea     rcx, [rbp+1C0h+var_1F0]
0x18007daee  call    renameResolveTrigger
0x18007daf3  mov     edx, eax
0x18007daf5  test    eax, eax
0x18007daf7  jnz     loc_18007DBDB
0x18007dafd  mov     rdx, [rbp+1C0h+var_80]
0x18007db04  mov     rbx, [rdx+38h]
0x18007db08  test    rbx, rbx
0x18007db0b  jz      short loc_18007DB81
0x18007db0d  mov     r8, [rbx+18h]
0x18007db11  test    r8, r8
0x18007db14  jz      short loc_18007DB71
0x18007db16  mov     r9, r14
0x18007db19  lea     rcx, [rbp+1C0h+var_1F0]
0x18007db1d  xor     edx, edx
0x18007db1f  call    sqlite3LocateTable
0x18007db24  cmp     rax, rsi
0x18007db27  jnz     short loc_18007DB71
0x18007db29  mov     r8, [rbx+40h]
0x18007db2d  test    r8, r8
0x18007db30  jz      short loc_18007DB47
0x18007db32  mov     r8, [r8+10h]
0x18007db36  lea     rdx, [rsp+2C0h+var_288]
0x18007db3b  mov     r9, r12
0x18007db3e  lea     rcx, [rbp+1C0h+var_1F0]
0x18007db42  call    renameColumnElistNames
0x18007db47  mov     r8, [rbx+38h]
  ... truncated ...
```

# renameColumnFunc

- ea: `0x180072d70`
- end: `0x180073335`
- name: `renameColumnFunc`
- size: `1477`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: ``

## callees

- `0x180027eb0`
- `0x18002817c`
- `0x18003bcbc`
- `0x18003f71c`
- `0x18003fa48`
- `0x1800415f0`
- `0x1800427d0`
- `0x180042a54`
- `0x180042af4`
- `0x180042b88`
- `0x180042bcc`
- `0x180042c68`
- `0x180042dc4`
- `0x1800449f0`
- `0x180045374`
- `0x180072c80`
- `0x180072d70`
- `0x18007333c`
- `0x1800733d8`
- `0x180073744`
- `0x180073910`
- `0x180074194`
- `0x1800741d8`
- `0x180074350`
- `0x18007c408`
- `0x180094470`
- `0x1800970d0`
- `0x180097ea0`

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
  unsigned __int8 *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  int v22; // r15d
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r12
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r8
  void *result; // rax
  __int64 Table; // rax
  __int64 v34; // rsi
  _BYTE *v35; // r9
  __int64 v36; // r12
  int v37; // ecx
  __int64 v38; // rdx
  __int64 v39; // rbx
  char v40; // al
  __int64 v41; // rbx
  __int64 v42; // rbx
  __int64 v43; // r14
  __int64 v44; // rsi
  __int64 v45; // rsi
  int v46; // esi
  __int64 v47; // rax
  __int64 v48; // rbx
  int v49; // edi
  int i; // esi
  _DWORD *v51; // r8
  __int64 v52; // r14
  unsigned int v53; // eax
  __int64 v54; // rdx
  _QWORD *v55; // rbx
  __int64 v56; // r8
  __int64 v57; // r8
  unsigned int v58; // eax
  int v59; // [rsp+20h] [rbp-E0h]
  __int128 v61; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v62; // [rsp+48h] [rbp-B8h]
  __int64 v63; // [rsp+58h] [rbp-A8h]
  __int64 v64; // [rsp+60h] [rbp-A0h]
  _BYTE *v65; // [rsp+68h] [rbp-98h]
  _QWORD *v66; // [rsp+70h] [rbp-90h]
  _OWORD v67[3]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-58h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  char v72[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h]
  unsigned int v74; // [rsp+E8h] [rbp-18h]
  __int64 v75; // [rsp+188h] [rbp+88h]
  __int64 v76; // [rsp+230h] [rbp+130h]
  __int64 v77; // [rsp+238h] [rbp+138h]
  __int64 v78; // [rsp+240h] [rbp+140h]

  v66 = a3;
  v4 = sqlite3_context_db_handle(a1);
  v5 = *a3;
  LOBYTE(v6) = 1;
  v68 = v4;
  v61 = 0;
  v7 = v4;
  v62 = 0;
  v8 = sqlite3ValueText(v5, v6);
  v9 = a3[3];
  LOBYTE(v10) = 1;
  v11 = v8;
  v65 = (_BYTE *)v8;
  v12 = sqlite3ValueText(v9, v10);
  LOBYTE(v13) = 1;
  v14 = v12;
  v15 = sqlite3ValueText(a3[4], v13);
  v16 = a3[5];
  v17 = (unsigned __int8 *)v15;
  v64 = v15;
  v20 = sqlite3VdbeIntValue(v16, v18, v19);
  LOBYTE(v21) = 1;
  v22 = v20;
  v23 = sqlite3ValueText(a3[6], v21);
  v24 = a3[7];
  v25 = v23;
  v70 = v23;
  v28 = sqlite3VdbeIntValue(v24, v26, v27);
  v29 = a3[8];
  v69 = v28;
  v63 = sqlite3VdbeIntValue(v29, v30, v31);
  result = memset_0(v72, 0, 0x1A8u);
  memset(v67, 0, sizeof(v67));
  if ( v11 && v17 && v25 && v22 >= 0 )
  {
    v71 = *(_QWORD *)(v7 + 512);
    sqlite3BtreeEnterAll(v7);
    Table = sqlite3FindTable(v7, v17, v14);
    v34 = Table;
    if ( !Table || v22 >= *(__int16 *)(Table + 54) )
      return (void *)sqlite3BtreeLeaveAll(v7);
    v35 = v65;
    v36 = *(_QWORD *)(*(_QWORD *)(Table + 8) + 24LL * v22);
    v37 = v22;
    v61 = 0;
    v62 = 0;
    v59 = v63;
    if ( v22 == *(__int16 *)(Table + 52) )
      v37 = -1;
    HIDWORD(v61) = v37;
    *(_QWORD *)(v7 + 512) = 0;
    v38 = (unsigned int)renameParseSql((__int64)v72, v14, v7, v35, v59);
    *(_QWORD *)&v62 = v34;
    *(_QWORD *)&v67[0] = v72;
    *((_QWORD *)&v67[0] + 1) = renameColumnExprCb;
    *(_QWORD *)&v67[1] = renameColumnSelectCb;
    *((_QWORD *)&v67[2] + 1) = &v61;
    *(_OWORD *)((char *)&v67[1] + 8) = 0;
    if ( (_DWORD)v38 )
      goto LABEL_61;
    v39 = v76;
    if ( v76 )
    {
      v40 = *(_BYTE *)(v76 + 63);
      if ( v40 == 2 )
      {
        v41 = *(_QWORD *)(v76 + 64);
        *(_DWORD *)(v41 + 4) &= ~0x200000u;
        v74 = 0;
        sqlite3SelectPrep(v72, v41, 0);
        if ( *(_BYTE *)(v7 + 103) )
        {
          v42 = a1;
          v38 = 7;
LABEL_14:
          if ( v73 )
            renameColumnParseError(v42, (unsigned int)&Src, v66[1], v66[2], (__int64)v72);
          else
            sqlite3_result_error_code(v42, v38);
          goto LABEL_66;
        }
        v38 = v74;
        if ( !v74 )
        {
          sqlite3WalkSelect(v67, v41);
          goto LABEL_59;
        }
LABEL_61:
        v42 = a1;
LABEL_62:
        if ( (_DWORD)v38 != 1 || (*(_DWORD *)(v7 + 48) & 0x10000001) != 1 )
          goto LABEL_14;
        sqlite3_result_value(v42, *v66);
LABEL_66:
        renameParseCleanup(v72, v38);
        renameTokenFree(v7, v61);
        *(_QWORD *)(v7 + 512) = v71;
        return (void *)sqlite3BtreeLeaveAll(v7);
      }
      if ( !v40 )
      {
        v43 = v64;
        LODWORD(v63) = sqlite3_stricmp(v64, *(_QWORD *)v76);
        *(_QWORD *)&v62 = v39;
        if ( !(_DWORD)v63 )
        {
          if ( v22 < *(__int16 *)(v39 + 54) )
          {
            renameTokenFind(v72, &v61, *(_QWORD *)(*(_QWORD *)(v39 + 8) + 24LL * v22));
            v39 = v76;
          }
          if ( v61 < 0 )
          {
            renameTokenFind(v72, &v61, v39 + 52);
            v39 = v76;
          }
          sqlite3WalkExprList(v67, *(_QWORD *)(v39 + 32));
          v39 = v76;
          v44 = *(_QWORD *)(v76 + 16);
          if ( v44 )
          {
            do
            {
              sqlite3WalkExprList(v67, *(_QWORD *)(v44 + 80));
              v44 = *(_QWORD *)(v44 + 40);
            }
            while ( v44 );
            v39 = v76;
          }
          v45 = v77;
          if ( v77 )
          {
            do
            {
              sqlite3WalkExprList(v67, *(_QWORD *)(v45 + 80));
              v45 = *(_QWORD *)(v45 + 40);
            }
            while ( v45 );
            v39 = v76;
          }
          v46 = 0;
          if ( *(__int16 *)(v39 + 54) > 0 )
          {
            do
            {
              v47 = sqlite3ColumnExpr(v39, *(_QWORD *)(v39 + 8) + 24LL * v46);
              sqlite3WalkExpr(v67, v47);
              v39 = v76;
              ++v46;
            }
            while ( v46 < *(__int16 *)(v76 + 54) );
          }
        }
        v48 = *(_QWORD *)(v39 + 72);
        if ( v48 )
        {
          v49 = v63;
          do
          {
            for ( i = 0; i < *(_DWORD *)(v48 + 40); ++i )
            {
              if ( !v49 )
              {
                v51 = (_DWORD *)(v48 + 16 * (i + 4LL));
                if ( *v51 == v22 )
                  renameTokenFind(v72, &v61, v51);
              }
              if ( !(unsigned int)sqlite3_stricmp(*(_QWORD *)(v48 + 16), v43) )
              {
                v52 = *(_QWORD *)(v48 + 16LL * i + 72);
                if ( !(unsigned int)sqlite3_stricmp(v52, v36) )
                  renameTokenFind(v72, &v61, v52);
                v43 = v64;
              }
            }
            v48 = *(_QWORD *)(v48 + 8);
          }
          while ( v48 );
          v7 = v68;
        }
      }
    }
    else if ( v77 )
    {
      sqlite3WalkExprList(v67, *(_QWORD *)(v77 + 80));
      sqlite3WalkExpr(v67, *(_QWORD *)(v77 + 72));
    }
    else
    {
      v53 = renameResolveTrigger(v72);
      v38 = v53;
      if ( v53 )
        goto LABEL_61;
      v54 = v78;
      v55 = *(_QWORD **)(v78 + 56);
      if ( v55 )
      {
        do
        {
          v56 = v55[3];
          if ( v56 && sqlite3LocateTable(v72, 0, v56, v14) == v34 )
          {
            v57 = v55[8];
            if ( v57 )
              renameColumnElistNames(v72, &v61, *(_QWORD *)(v57 + 16), v36);
            renameColumnIdlistNames(v72, &v61, v55[7], v36);
            renameColumnElistNames(v72, &v61, v55[6], v36);
          }
          v55 = (_QWORD *)v55[10];
        }
        while ( v55 );
        v54 = v78;
      }
      if ( v75 == v34 )
        renameColumnIdlistNames(v72, &v61, *(_QWORD *)(v54 + 32), v36);
      renameWalkTrigger(v67);
    }
LABEL_59:
    v42 = a1;
    v58 = renameEditSql(a1, (unsigned int)&v61, (_DWORD)v65, v70, v69);
    v38 = v58;
    if ( !v58 )
      goto LABEL_66;
    goto LABEL_62;
  }
  return result;
}

```

## disassembly

```asm
0x180072d70  mov     [rsp-8+arg_8], rbx
0x180072d75  push    rbp
0x180072d76  push    rsi
0x180072d77  push    rdi
0x180072d78  push    r12
0x180072d7a  push    r13
0x180072d7c  push    r14
0x180072d7e  push    r15
0x180072d80  lea     rbp, [rsp-190h]
0x180072d88  sub     rsp, 290h
0x180072d8f  mov     rax, cs:__security_cookie
0x180072d96  xor     rax, rsp
0x180072d99  mov     [rbp+1C0h+var_40], rax
0x180072da0  mov     rsi, r8
0x180072da3  mov     [rsp+2C0h+var_250], r8
0x180072da8  mov     [rsp+2C0h+var_290], rcx
0x180072dad  call    sqlite3_context_db_handle
0x180072db2  mov     rcx, [rsi]
0x180072db5  xorps   xmm0, xmm0
0x180072db8  mov     dl, 1
0x180072dba  mov     [rbp+1C0h+var_218], rax
0x180072dbe  movups  [rsp+2C0h+var_288], xmm0
0x180072dc3  mov     rdi, rax
0x180072dc6  movups  [rsp+2C0h+var_278], xmm0
0x180072dcb  call    sqlite3ValueText
0x180072dd0  mov     rcx, [rsi+18h]
0x180072dd4  mov     dl, 1
0x180072dd6  mov     r13, rax
0x180072dd9  mov     [rsp+2C0h+var_258], rax
0x180072dde  call    sqlite3ValueText
0x180072de3  mov     rcx, [rsi+20h]
0x180072de7  mov     dl, 1
0x180072de9  mov     r14, rax
0x180072dec  call    sqlite3ValueText
0x180072df1  mov     rcx, [rsi+28h]
0x180072df5  mov     rbx, rax
0x180072df8  mov     [rsp+2C0h+var_260], rax
0x180072dfd  call    sqlite3VdbeIntValue
0x180072e02  mov     rcx, [rsi+30h]
0x180072e06  mov     dl, 1
0x180072e08  mov     r15, rax
0x180072e0b  call    sqlite3ValueText
0x180072e10  mov     rcx, [rsi+38h]
0x180072e14  mov     r12, rax
0x180072e17  mov     [rbp+1C0h+var_208], rax
0x180072e1b  call    sqlite3VdbeIntValue
0x180072e20  mov     rcx, [rsi+40h]
0x180072e24  mov     [rbp+1C0h+var_210], rax
0x180072e28  call    sqlite3VdbeIntValue
0x180072e2d  xor     edx, edx; Val
0x180072e2f  mov     [rsp+2C0h+var_268], rax
0x180072e34  mov     r8d, 1A8h; Size
0x180072e3a  lea     rcx, [rbp+1C0h+var_1F0]; void *
0x180072e3e  call    memset_0
0x180072e43  xorps   xmm0, xmm0
0x180072e46  movups  [rsp+2C0h+var_248], xmm0
0x180072e4b  movups  [rbp+1C0h+var_238], xmm0
0x180072e4f  movups  [rbp+1C0h+var_228], xmm0
0x180072e53  test    r13, r13
0x180072e56  jz      loc_18007330B
0x180072e5c  test    rbx, rbx
0x180072e5f  jz      loc_18007330B
0x180072e65  test    r12, r12
0x180072e68  jz      loc_18007330B
0x180072e6e  test    r15d, r15d
0x180072e71  js      loc_18007330B
0x180072e77  mov     rax, [rdi+200h]
0x180072e7e  mov     rcx, rdi
0x180072e81  mov     [rbp+1C0h+var_200], rax
0x180072e85  call    sqlite3BtreeEnterAll
0x180072e8a  mov     r8, r14
0x180072e8d  mov     rdx, rbx
0x180072e90  mov     rcx, rdi
0x180072e93  call    sqlite3FindTable
0x180072e98  mov     rsi, rax
0x180072e9b  test    rax, rax
0x180072e9e  jz      loc_180073303
0x180072ea4  movsx   ecx, word ptr [rax+36h]
0x180072ea8  cmp     r15d, ecx
0x180072eab  jge     loc_180073303
0x180072eb1  mov     r9, [rsp+2C0h+var_258]
0x180072eb6  or      edx, 0FFFFFFFFh
0x180072eb9  xorps   xmm0, xmm0
0x180072ebc  movsxd  rcx, r15d
0x180072ebf  mov     r8, rdi
0x180072ec2  lea     r13, [rcx+rcx*2]
0x180072ec6  mov     rcx, [rax+8]
0x180072eca  mov     r12, [rcx+r13*8]
0x180072ece  mov     ecx, r15d
0x180072ed1  movups  [rsp+2C0h+var_288], xmm0
0x180072ed6  movups  [rsp+2C0h+var_278], xmm0
0x180072edb  movsx   eax, word ptr [rax+34h]
0x180072edf  cmp     r15d, eax
0x180072ee2  mov     rax, [rsp+2C0h+var_268]
0x180072ee7  mov     [rsp+2C0h+var_2A0], eax
0x180072eeb  cmovz   ecx, edx
0x180072eee  mov     rdx, r14
0x180072ef1  mov     dword ptr [rsp+2C0h+var_288+0Ch], ecx
0x180072ef5  lea     rcx, [rbp+1C0h+var_1F0]
0x180072ef9  mov     qword ptr [rdi+200h], 0
0x180072f04  call    renameParseSql
0x180072f09  mov     edx, eax
0x180072f0b  mov     qword ptr [rsp+2C0h+var_278], rsi
0x180072f10  lea     rax, [rbp+1C0h+var_1F0]
0x180072f14  xorps   xmm0, xmm0
0x180072f17  mov     qword ptr [rsp+2C0h+var_248], rax
0x180072f1c  lea     rax, renameColumnExprCb
0x180072f23  mov     qword ptr [rbp+1C0h+var_248+8], rax
0x180072f27  lea     rax, renameColumnSelectCb
0x180072f2e  mov     qword ptr [rbp+1C0h+var_238], rax
0x180072f32  lea     rax, [rsp+2C0h+var_288]
0x180072f37  mov     qword ptr [rbp+1C0h+var_228+8], rax
0x180072f3b  movdqu  [rbp+1C0h+var_238+8], xmm0
0x180072f40  test    edx, edx
0x180072f42  jnz     loc_1800732AB
0x180072f48  mov     rbx, [rbp+1C0h+var_90]
0x180072f4f  test    rbx, rbx
0x180072f52  jz      loc_180073186
0x180072f58  mov     al, [rbx+3Fh]
0x180072f5b  cmp     al, 2
0x180072f5d  jnz     short loc_180072FDC
0x180072f5f  mov     rbx, [rbx+40h]
0x180072f63  lea     rcx, [rbp+1C0h+var_1F0]
0x180072f67  xor     r8d, r8d
0x180072f6a  btr     dword ptr [rbx+4], 15h
0x180072f6f  mov     [rbp+1C0h+var_1D8], edx
0x180072f72  mov     rdx, rbx
0x180072f75  call    sqlite3SelectPrep
0x180072f7a  cmp     byte ptr [rdi+67h], 0
0x180072f7e  jz      short loc_180072FBF
0x180072f80  mov     rbx, [rsp+2C0h+var_290]
0x180072f85  mov     edx, 7
0x180072f8a  cmp     [rbp+1C0h+var_1E8], 0
0x180072f8f  mov     rcx, rbx
0x180072f92  jz      loc_1800732DD
0x180072f98  mov     r8, [rsp+2C0h+var_250]
0x180072f9d  lea     rax, [rbp+1C0h+var_1F0]
0x180072fa1  lea     rdx, Src
0x180072fa8  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180072fad  mov     r9, [r8+10h]
0x180072fb1  mov     r8, [r8+8]
0x180072fb5  call    renameColumnParseError
0x180072fba  jmp     loc_1800732E2
0x180072fbf  mov     edx, [rbp+1C0h+var_1D8]
0x180072fc2  test    edx, edx
0x180072fc4  jnz     loc_1800732AB
0x180072fca  mov     rdx, rbx
0x180072fcd  lea     rcx, [rsp+2C0h+var_248]
0x180072fd2  call    sqlite3WalkSelect
0x180072fd7  jmp     loc_180073280
0x180072fdc  test    al, al
0x180072fde  jnz     loc_180073280
0x180072fe4  mov     r14, [rsp+2C0h+var_260]
0x180072fe9  mov     rdx, [rbx]
0x180072fec  mov     rcx, r14
0x180072fef  call    sqlite3_stricmp
0x180072ff4  mov     dword ptr [rsp+2C0h+var_268], eax
0x180072ff8  mov     qword ptr [rsp+2C0h+var_278], rbx
0x180072ffd  test    eax, eax
0x180072fff  jnz     loc_1800730F0
0x180073005  movsx   ecx, word ptr [rbx+36h]
0x180073009  cmp     r15d, ecx
0x18007300c  jge     short loc_18007302B
0x18007300e  mov     r8, [rbx+8]
0x180073012  lea     rdx, [rsp+2C0h+var_288]
0x180073017  lea     rcx, [rbp+1C0h+var_1F0]
0x18007301b  mov     r8, [r8+r13*8]
0x18007301f  call    renameTokenFind
0x180073024  mov     rbx, [rbp+1C0h+var_90]
0x18007302b  cmp     dword ptr [rsp+2C0h+var_288+0Ch], 0
0x180073030  jge     short loc_18007304B
0x180073032  lea     r8, [rbx+34h]
0x180073036  lea     rdx, [rsp+2C0h+var_288]
0x18007303b  lea     rcx, [rbp+1C0h+var_1F0]
0x18007303f  call    renameTokenFind
0x180073044  mov     rbx, [rbp+1C0h+var_90]
0x18007304b  mov     rdx, [rbx+20h]
0x18007304f  lea     rcx, [rsp+2C0h+var_248]
0x180073054  call    sqlite3WalkExprList
0x180073059  mov     rbx, [rbp+1C0h+var_90]
0x180073060  mov     rsi, [rbx+10h]
0x180073064  test    rsi, rsi
0x180073067  jz      short loc_180073087
0x180073069  mov     rdx, [rsi+50h]
0x18007306d  lea     rcx, [rsp+2C0h+var_248]
0x180073072  call    sqlite3WalkExprList
0x180073077  mov     rsi, [rsi+28h]
0x18007307b  test    rsi, rsi
0x18007307e  jnz     short loc_180073069
0x180073080  mov     rbx, [rbp+1C0h+var_90]
0x180073087  mov     rsi, [rbp+1C0h+var_88]
0x18007308e  test    rsi, rsi
0x180073091  jz      short loc_1800730B1
0x180073093  mov     rdx, [rsi+50h]
0x180073097  lea     rcx, [rsp+2C0h+var_248]
0x18007309c  call    sqlite3WalkExprList
0x1800730a1  mov     rsi, [rsi+28h]
0x1800730a5  test    rsi, rsi
0x1800730a8  jnz     short loc_180073093
0x1800730aa  mov     rbx, [rbp+1C0h+var_90]
0x1800730b1  xor     esi, esi
0x1800730b3  xor     eax, eax
0x1800730b5  cmp     ax, [rbx+36h]
0x1800730b9  jge     short loc_1800730F0
0x1800730bb  movsxd  rax, esi
0x1800730be  lea     rcx, [rax+rax*2]
0x1800730c2  mov     rax, [rbx+8]
0x1800730c6  lea     rdx, [rax+rcx*8]
0x1800730ca  mov     rcx, rbx
0x1800730cd  call    sqlite3ColumnExpr
0x1800730d2  mov     rdx, rax
0x1800730d5  lea     rcx, [rsp+2C0h+var_248]
0x1800730da  call    sqlite3WalkExpr
0x1800730df  mov     rbx, [rbp+1C0h+var_90]
0x1800730e6  inc     esi
0x1800730e8  movsx   eax, word ptr [rbx+36h]
0x1800730ec  cmp     esi, eax
0x1800730ee  jl      short loc_1800730BB
0x1800730f0  mov     rbx, [rbx+48h]
0x1800730f4  test    rbx, rbx
0x1800730f7  jz      loc_180073280
0x1800730fd  mov     edi, dword ptr [rsp+2C0h+var_268]
0x180073101  xor     esi, esi
0x180073103  cmp     [rbx+28h], esi
0x180073106  jle     short loc_180073174
0x180073108  test    edi, edi
0x18007310a  jnz     short loc_18007312D
0x18007310c  movsxd  r8, esi
0x18007310f  add     r8, 4
0x180073113  shl     r8, 4
0x180073117  add     r8, rbx
0x18007311a  cmp     [r8], r15d
0x18007311d  jnz     short loc_18007312D
0x18007311f  lea     rdx, [rsp+2C0h+var_288]
0x180073124  lea     rcx, [rbp+1C0h+var_1F0]
0x180073128  call    renameTokenFind
0x18007312d  mov     rcx, [rbx+10h]
0x180073131  mov     rdx, r14
0x180073134  call    sqlite3_stricmp
0x180073139  test    eax, eax
0x18007313b  jnz     short loc_18007316D
0x18007313d  movsxd  rax, esi
0x180073140  mov     rdx, r12
0x180073143  add     rax, rax
0x180073146  mov     r14, [rbx+rax*8+48h]
0x18007314b  mov     rcx, r14
0x18007314e  call    sqlite3_stricmp
0x180073153  test    eax, eax
0x180073155  jnz     short loc_180073168
0x180073157  mov     r8, r14
0x18007315a  lea     rdx, [rsp+2C0h+var_288]
0x18007315f  lea     rcx, [rbp+1C0h+var_1F0]
0x180073163  call    renameTokenFind
0x180073168  mov     r14, [rsp+2C0h+var_260]
0x18007316d  inc     esi
0x18007316f  cmp     esi, [rbx+28h]
0x180073172  jl      short loc_180073108
0x180073174  mov     rbx, [rbx+8]
0x180073178  test    rbx, rbx
0x18007317b  jnz     short loc_180073101
0x18007317d  mov     rdi, [rbp+1C0h+var_218]
0x180073181  jmp     loc_180073280
0x180073186  mov     rdx, [rbp+1C0h+var_88]
0x18007318d  test    rdx, rdx
0x180073190  jz      short loc_1800731BA
0x180073192  mov     rdx, [rdx+50h]
0x180073196  lea     rcx, [rsp+2C0h+var_248]
0x18007319b  call    sqlite3WalkExprList
0x1800731a0  mov     rdx, [rbp+1C0h+var_88]
0x1800731a7  lea     rcx, [rsp+2C0h+var_248]
0x1800731ac  mov     rdx, [rdx+48h]
0x1800731b0  call    sqlite3WalkExpr
0x1800731b5  jmp     loc_180073280
0x1800731ba  lea     rcx, [rbp+1C0h+var_1F0]
0x1800731be  call    renameResolveTrigger
0x1800731c3  mov     edx, eax
0x1800731c5  test    eax, eax
0x1800731c7  jnz     loc_1800732AB
0x1800731cd  mov     rdx, [rbp+1C0h+var_80]
0x1800731d4  mov     rbx, [rdx+38h]
0x1800731d8  test    rbx, rbx
0x1800731db  jz      short loc_180073251
0x1800731dd  mov     r8, [rbx+18h]
0x1800731e1  test    r8, r8
0x1800731e4  jz      short loc_180073241
0x1800731e6  mov     r9, r14
0x1800731e9  lea     rcx, [rbp+1C0h+var_1F0]
0x1800731ed  xor     edx, edx
0x1800731ef  call    sqlite3LocateTable
0x1800731f4  cmp     rax, rsi
0x1800731f7  jnz     short loc_180073241
0x1800731f9  mov     r8, [rbx+40h]
0x1800731fd  test    r8, r8
0x180073200  jz      short loc_180073217
0x180073202  mov     r8, [r8+10h]
0x180073206  lea     rdx, [rsp+2C0h+var_288]
0x18007320b  mov     r9, r12
0x18007320e  lea     rcx, [rbp+1C0h+var_1F0]
0x180073212  call    renameColumnElistNames
0x180073217  mov     r8, [rbx+38h]
  ... truncated ...
```

# sqlite3RunVacuum

- ea: `0x18008a3e0`
- end: `0x18008a87c`
- name: `sqlite3RunVacuum`
- size: `1180`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180021aa0`

## callees

- `0x180011a14`
- `0x18003ea38`
- `0x180042dc4`
- `0x18005d6a4`
- `0x18005d7a8`
- `0x1800798dc`
- `0x180079994`
- `0x180079b10`
- `0x18007a224`
- `0x18007a268`
- `0x18007a2c8`
- `0x18007ac70`
- `0x18007acd8`
- `0x18007ad40`
- `0x18007adf8`
- `0x18007ae40`
- `0x18007b348`
- `0x1800873b4`
- `0x180089a6c`
- `0x18008a3e0`
- `0x18008add8`

## string_xrefs

- `0x18008a576`: `output file already exists`

## pseudocode

```c
__int64 __fastcall sqlite3RunVacuum(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const char *v9; // r8
  int v10; // r14d
  __int64 v11; // rax
  const unsigned __int16 *v12; // r9
  __int64 v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r13
  unsigned int v19; // eax
  unsigned int updated; // ebx
  int v21; // ebx
  __int64 v22; // r14
  _QWORD *v23; // rcx
  __int64 v24; // rax
  int RequestedReserve; // eax
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  unsigned int AutoVacuum; // eax
  __int64 v30; // r9
  __int64 v31; // r9
  unsigned int v32; // eax
  int i; // ebp
  unsigned int v34; // eax
  unsigned int v35; // eax
  int v36; // [rsp+20h] [rbp-88h] BYREF
  __int64 v37; // [rsp+28h] [rbp-80h] BYREF
  __int64 v38; // [rsp+30h] [rbp-78h]
  int IsMemdb; // [rsp+38h] [rbp-70h]
  int v40; // [rsp+3Ch] [rbp-6Ch]
  __int64 v41; // [rsp+40h] [rbp-68h]
  __int64 v42; // [rsp+48h] [rbp-60h]
  __int64 v43; // [rsp+50h] [rbp-58h]
  __int64 v44; // [rsp+58h] [rbp-50h]
  char v45; // [rsp+B8h] [rbp+10h]

  v5 = (int)a3;
  v6 = a2;
  if ( !*(_BYTE *)(a2 + 101) )
  {
    sqlite3SetString(a1, a2, "cannot VACUUM from within a transaction");
    return 1;
  }
  if ( *(int *)(a2 + 216) > 1 )
  {
    v9 = "cannot VACUUM - SQL statements in progress";
LABEL_5:
    sqlite3SetString(a1, a2, v9);
    return 1;
  }
  v10 = *(_DWORD *)(a2 + 76);
  if ( a4 )
  {
    if ( *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(a4 + 20) & 0x3F)) != 3 )
    {
      v9 = "non-text filename";
      goto LABEL_5;
    }
    LOBYTE(a2) = 1;
    v11 = sqlite3ValueText(a4, a2);
    *(_DWORD *)(v6 + 76) &= ~1u;
    v12 = (const unsigned __int16 *)v11;
    *(_DWORD *)(v6 + 76) |= 6u;
  }
  else
  {
    v12 = &Src;
  }
  v13 = 0;
  v14 = *(_QWORD *)(v6 + 48);
  v15 = *(_QWORD *)(v6 + 120);
  v40 = *(_DWORD *)(v6 + 44);
  *(_DWORD *)(v6 + 44) = v40 | 6;
  v43 = v15;
  v16 = *(_QWORD *)(v6 + 128);
  v42 = v14;
  v44 = v16;
  LOBYTE(v16) = *(_BYTE *)(v6 + 110);
  *(_QWORD *)(v6 + 48) = v14 & 0xFFFFFFFEEFFFADFEuLL | 0x201;
  v17 = *(_QWORD *)(v6 + 32);
  *(_BYTE *)(v6 + 110) = 0;
  v45 = v16;
  v41 = 32 * v5;
  v18 = *(_QWORD *)(32 * v5 + v17 + 8);
  v38 = *(_QWORD *)(32 * v5 + v17);
  IsMemdb = sqlite3PagerIsMemdb(**(_QWORD **)(v18 + 8), 32 * v5, a3, v12);
  v36 = *(_DWORD *)(v6 + 40);
  v19 = execSqlF(v6, a1, "ATTACH %Q AS vacuum_db");
  *(_DWORD *)(v6 + 76) = v10;
  updated = v19;
  if ( !v19 )
  {
    v21 = 1;
    v13 = *(_QWORD *)(v6 + 32) + 32LL * v36;
    v22 = *(_QWORD *)(v13 + 8);
    if ( a4 )
    {
      v23 = *(_QWORD **)(**(_QWORD **)(v22 + 8) + 72LL);
      v37 = 0;
      if ( *v23 && ((unsigned int)sqlite3OsFileSize(v23, &v37) || v37 > 0) )
      {
        updated = 1;
        sqlite3SetString(a1, v6, "output file already exists");
        goto LABEL_43;
      }
      v24 = *(_QWORD *)(v6 + 32);
      *(_DWORD *)(v6 + 44) |= 8u;
      v21 = *(_DWORD *)(v6 + 48) & 0x38 | *(unsigned __int8 *)(v41 + v24 + 16);
    }
    RequestedReserve = sqlite3BtreeGetRequestedReserve(v18);
    v26 = *(_QWORD *)(v6 + 32);
    LODWORD(v37) = RequestedReserve;
    sqlite3BtreeSetCacheSize(v22, *(unsigned int *)(*(_QWORD *)(v41 + v26 + 24) + 116LL));
    v27 = sqlite3BtreeSetSpillSize(v18, 0);
    sqlite3BtreeSetSpillSize(v22, v27);
    sqlite3BtreeSetPagerFlags(v22, v21 | 0x20u);
    updated = execSql(v6, a1, "BEGIN");
    if ( !updated )
    {
      updated = sqlite3BtreeBeginTrans(v18, a4 == 0 ? 2 : 0, 0);
      if ( !updated )
      {
        if ( *(_BYTE *)(**(_QWORD **)(v18 + 8) + 9LL) == 5 && !a4 )
          *(_DWORD *)(v6 + 116) = 0;
        v28 = v37;
        if ( (unsigned int)sqlite3BtreeSetPageSize(
                             v22,
                             *(unsigned int *)(*(_QWORD *)(v18 + 8) + 52LL),
                             (unsigned int)v37,
                             0)
          || !IsMemdb && (unsigned int)sqlite3BtreeSetPageSize(v22, *(unsigned int *)(v6 + 116), v28, 0)
          || *(_BYTE *)(v6 + 103) )
        {
          updated = 7;
        }
        else
        {
          AutoVacuum = *(char *)(v6 + 106);
          if ( *(char *)(v6 + 106) < 0 )
            AutoVacuum = sqlite3BtreeGetAutoVacuum(v18);
          sqlite3BtreeSetAutoVacuum(v22, AutoVacuum);
          v30 = v38;
          *(_BYTE *)(v6 + 196) = v36;
          updated = execSqlF(
                      v6,
                      a1,
                      "SELECT sql FROM \"%w\".sqlite_schema WHERE type='table'AND name<>'sqlite_sequence' AND coalesce(rootpage,1)>0",
                      v30);
          if ( !updated )
          {
            updated = execSqlF(v6, a1, "SELECT sql FROM \"%w\".sqlite_schema WHERE type='index'", v38);
            if ( !updated )
            {
              v31 = v38;
              *(_BYTE *)(v6 + 196) = 0;
              v32 = execSqlF(
                      v6,
                      a1,
                      "SELECT'INSERT INTO vacuum_db.'||quote(name)||' SELECT*FROM\"%w\".'||quote(name)FROM vacuum_db.sqli"
                      "te_schema WHERE type='table'AND coalesce(rootpage,1)>0",
                      v31);
              *(_DWORD *)(v6 + 44) &= ~4u;
              updated = v32;
              if ( !v32 )
              {
                updated = execSqlF(
                            v6,
                            a1,
                            "INSERT INTO vacuum_db.sqlite_schema SELECT*FROM \"%w\".sqlite_schema WHERE type IN('view','t"
                            "rigger') OR(type='table'AND rootpage=0)",
                            v38);
                if ( !updated )
                {
                  v36 = 0;
                  for ( i = 0; i < 10; i += 2 )
                  {
                    sqlite3BtreeGetMeta(v18, *((unsigned __int8 *)qword_1800B61D0 + i), &v36);
                    updated = sqlite3BtreeUpdateMeta(
                                v22,
                                *((unsigned __int8 *)qword_1800B61D0 + i),
                                v36 + (unsigned int)*((unsigned __int8 *)qword_1800B61D0 + i + 1));
                    if ( updated )
                      goto LABEL_43;
                  }
                  if ( a4 || (updated = sqlite3BtreeCopyFile(v18, v22)) == 0 )
                  {
                    updated = sqlite3BtreeCommit(v22);
                    if ( !updated && !a4 )
                    {
                      v34 = sqlite3BtreeGetAutoVacuum(v22);
                      sqlite3BtreeSetAutoVacuum(v18, v34);
                      v35 = sqlite3BtreeGetRequestedReserve(v22);
                      updated = sqlite3BtreeSetPageSize(v18, *(unsigned int *)(*(_QWORD *)(v22 + 8) + 52LL), v35, 1);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  *(_DWORD *)(v6 + 44) = v40;
  *(_QWORD *)(v6 + 48) = v42;
  *(_QWORD *)(v6 + 120) = v43;
  *(_QWORD *)(v6 + 128) = v44;
  *(_BYTE *)(v6 + 110) = v45;
  *(_BYTE *)(v6 + 196) = 0;
  sqlite3BtreeSetPageSize(v18, 0xFFFFFFFFLL, 0, 1);
  *(_BYTE *)(v6 + 101) = 1;
  if ( v13 )
  {
    sqlite3BtreeClose(*(_QWORD *)(v13 + 8));
    *(_QWORD *)(v13 + 8) = 0;
    *(_QWORD *)(v13 + 24) = 0;
  }
  sqlite3ResetAllSchemasOfConnection(v6);
  return updated;
}

```

## disassembly

```asm
0x18008a3e0  push    rbx
0x18008a3e2  push    rbp
0x18008a3e3  push    rsi
0x18008a3e4  push    rdi
0x18008a3e5  push    r12
0x18008a3e7  push    r13
0x18008a3e9  push    r14
0x18008a3eb  push    r15
0x18008a3ed  sub     rsp, 68h
0x18008a3f1  cmp     byte ptr [rdx+65h], 0
0x18008a3f5  mov     r15, r9
0x18008a3f8  movsxd  rbx, r8d
0x18008a3fb  mov     rdi, rdx
0x18008a3fe  mov     rbp, rcx
0x18008a401  jnz     short loc_18008A419
0x18008a403  lea     r8, aCannotVacuumFr; "cannot VACUUM from within a transaction"
0x18008a40a  call    sqlite3SetString
0x18008a40f  mov     eax, 1
0x18008a414  jmp     loc_18008A86B
0x18008a419  mov     esi, 1
0x18008a41e  cmp     [rdx+0D8h], esi
0x18008a424  jle     short loc_18008A439
0x18008a426  lea     r8, aCannotVacuumSq; "cannot VACUUM - SQL statements in progr"...
0x18008a42d  call    sqlite3SetString
0x18008a432  mov     eax, esi
0x18008a434  jmp     loc_18008A86B
0x18008a439  mov     r14d, [rdx+4Ch]
0x18008a43d  lea     rcx, __ImageBase
0x18008a444  test    r15, r15
0x18008a447  jz      short loc_18008A47F
0x18008a449  movzx   eax, word ptr [r9+14h]
0x18008a44e  and     eax, 3Fh
0x18008a451  cmp     byte ptr [rax+rcx+0B9DC0h], 3
0x18008a459  jz      short loc_18008A467
0x18008a45b  lea     r8, aNonTextFilenam; "non-text filename"
0x18008a462  mov     rcx, rbp
0x18008a465  jmp     short loc_18008A42D
0x18008a467  mov     dl, sil
0x18008a46a  mov     rcx, r15
0x18008a46d  call    sqlite3ValueText
0x18008a472  and     dword ptr [rdi+4Ch], 0FFFFFFFEh
0x18008a476  mov     r9, rax
0x18008a479  or      dword ptr [rdi+4Ch], 6
0x18008a47d  jmp     short loc_18008A486
0x18008a47f  lea     r9, Src
0x18008a486  mov     eax, [rdi+2Ch]
0x18008a489  xor     r12d, r12d
0x18008a48c  mov     rcx, [rdi+30h]
0x18008a490  mov     rdx, [rdi+78h]
0x18008a494  mov     [rsp+0A8h+var_6C], eax
0x18008a498  or      eax, 6
0x18008a49b  mov     [rdi+2Ch], eax
0x18008a49e  mov     rax, rcx
0x18008a4a1  mov     [rsp+0A8h+var_58], rdx
0x18008a4a6  mov     rdx, [rdi+80h]
0x18008a4ad  mov     [rsp+0A8h+var_60], rcx
0x18008a4b2  mov     rcx, 0FFFFFFFEEFFFAFFFh
0x18008a4bc  and     rax, rcx
0x18008a4bf  mov     [rsp+0A8h+var_50], rdx
0x18008a4c4  mov     dl, [rdi+6Eh]
0x18008a4c7  or      rax, 201h
0x18008a4cd  mov     [rdi+30h], rax
0x18008a4d1  mov     rax, [rdi+20h]
0x18008a4d5  mov     [rdi+6Eh], r12b
0x18008a4d9  mov     [rsp+0A8h+arg_8], dl
0x18008a4e0  mov     rdx, rbx
0x18008a4e3  shl     rdx, 5
0x18008a4e7  mov     [rsp+0A8h+var_68], rdx
0x18008a4ec  mov     rcx, [rdx+rax]
0x18008a4f0  mov     r13, [rdx+rax+8]
0x18008a4f5  mov     [rsp+0A8h+var_78], rcx
0x18008a4fa  mov     rcx, [r13+8]
0x18008a4fe  mov     rcx, [rcx]
0x18008a501  call    sqlite3PagerIsMemdb
0x18008a506  mov     [rsp+0A8h+var_70], eax
0x18008a50a  lea     r8, aAttachQAsVacuu; "ATTACH %Q AS vacuum_db"
0x18008a511  mov     eax, [rdi+28h]
0x18008a514  mov     rdx, rbp
0x18008a517  mov     rcx, rdi
0x18008a51a  mov     [rsp+0A8h+var_88], eax
0x18008a51e  call    execSqlF
0x18008a523  mov     [rdi+4Ch], r14d
0x18008a527  mov     ebx, eax
0x18008a529  test    eax, eax
0x18008a52b  jnz     loc_18008A7FA
0x18008a531  movsxd  r12, [rsp+0A8h+var_88]
0x18008a536  mov     ebx, esi
0x18008a538  shl     r12, 5
0x18008a53c  add     r12, [rdi+20h]
0x18008a540  mov     r14, [r12+8]
0x18008a545  test    r15, r15
0x18008a548  jz      short loc_18008A5A9
0x18008a54a  mov     rax, [r14+8]
0x18008a54e  xor     ebx, ebx
0x18008a550  mov     rcx, [rax]
0x18008a553  mov     rcx, [rcx+48h]
0x18008a557  mov     [rsp+0A8h+var_80], rbx
0x18008a55c  cmp     [rcx], rbx
0x18008a55f  jz      short loc_18008A58F
0x18008a561  lea     rdx, [rsp+0A8h+var_80]
0x18008a566  call    sqlite3OsFileSize
0x18008a56b  test    eax, eax
0x18008a56d  jnz     short loc_18008A576
0x18008a56f  cmp     [rsp+0A8h+var_80], rbx
0x18008a574  jle     short loc_18008A58F
0x18008a576  lea     r8, aOutputFileAlre; "output file already exists"
0x18008a57d  mov     rdx, rdi
0x18008a580  mov     rcx, rbp
0x18008a583  mov     ebx, esi
0x18008a585  call    sqlite3SetString
0x18008a58a  jmp     loc_18008A7FA
0x18008a58f  mov     rax, [rdi+20h]
0x18008a593  or      dword ptr [rdi+2Ch], 8
0x18008a597  mov     rcx, [rsp+0A8h+var_68]
0x18008a59c  movzx   ebx, byte ptr [rcx+rax+10h]
0x18008a5a1  mov     eax, [rdi+30h]
0x18008a5a4  and     eax, 38h
0x18008a5a7  or      ebx, eax
0x18008a5a9  mov     rcx, r13
0x18008a5ac  call    sqlite3BtreeGetRequestedReserve
0x18008a5b1  mov     rcx, [rdi+20h]
0x18008a5b5  mov     dword ptr [rsp+0A8h+var_80], eax
0x18008a5b9  mov     rax, [rsp+0A8h+var_68]
0x18008a5be  mov     rdx, [rax+rcx+18h]
0x18008a5c3  mov     rcx, r14
0x18008a5c6  mov     edx, [rdx+74h]
0x18008a5c9  call    sqlite3BtreeSetCacheSize
0x18008a5ce  xor     edx, edx
0x18008a5d0  mov     rcx, r13
0x18008a5d3  call    sqlite3BtreeSetSpillSize
0x18008a5d8  mov     edx, eax
0x18008a5da  mov     rcx, r14
0x18008a5dd  call    sqlite3BtreeSetSpillSize
0x18008a5e2  or      ebx, 20h
0x18008a5e5  mov     rcx, r14
0x18008a5e8  mov     edx, ebx
0x18008a5ea  call    sqlite3BtreeSetPagerFlags
0x18008a5ef  lea     r8, aBegin; "BEGIN"
0x18008a5f6  mov     rdx, rbp
0x18008a5f9  mov     rcx, rdi
0x18008a5fc  call    execSql
0x18008a601  mov     ebx, eax
0x18008a603  test    eax, eax
0x18008a605  jnz     loc_18008A7FA
0x18008a60b  mov     rax, r15
0x18008a60e  mov     rcx, r13
0x18008a611  neg     rax
0x18008a614  sbb     edx, edx
0x18008a616  xor     r8d, r8d
0x18008a619  not     edx
0x18008a61b  and     edx, 2
0x18008a61e  call    sqlite3BtreeBeginTrans
0x18008a623  mov     ebx, eax
0x18008a625  test    eax, eax
0x18008a627  jnz     loc_18008A7FA
0x18008a62d  mov     rax, [r13+8]
0x18008a631  mov     rcx, [rax]
0x18008a634  cmp     byte ptr [rcx+9], 5
0x18008a638  jnz     short loc_18008A643
0x18008a63a  test    r15, r15
0x18008a63d  jnz     short loc_18008A643
0x18008a63f  mov     [rdi+74h], r15d
0x18008a643  mov     rdx, [r13+8]
0x18008a647  xor     r9d, r9d
0x18008a64a  mov     ebx, dword ptr [rsp+0A8h+var_80]
0x18008a64e  mov     rcx, r14
0x18008a651  mov     r8d, ebx
0x18008a654  mov     edx, [rdx+34h]
0x18008a657  call    sqlite3BtreeSetPageSize
0x18008a65c  test    eax, eax
0x18008a65e  jnz     loc_18008A7F5
0x18008a664  cmp     [rsp+0A8h+var_70], eax
0x18008a668  jnz     short loc_18008A683
0x18008a66a  mov     edx, [rdi+74h]
0x18008a66d  xor     r9d, r9d
0x18008a670  mov     r8d, ebx
0x18008a673  mov     rcx, r14
0x18008a676  call    sqlite3BtreeSetPageSize
0x18008a67b  test    eax, eax
0x18008a67d  jnz     loc_18008A7F5
0x18008a683  cmp     byte ptr [rdi+67h], 0
0x18008a687  jnz     loc_18008A7F5
0x18008a68d  movsx   eax, byte ptr [rdi+6Ah]
0x18008a691  test    al, al
0x18008a693  jns     short loc_18008A69D
0x18008a695  mov     rcx, r13
0x18008a698  call    sqlite3BtreeGetAutoVacuum
0x18008a69d  mov     edx, eax
0x18008a69f  mov     rcx, r14
0x18008a6a2  call    sqlite3BtreeSetAutoVacuum
0x18008a6a7  mov     eax, [rsp+0A8h+var_88]
0x18008a6ab  lea     r8, aSelectSqlFromW_0; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x18008a6b2  mov     r9, [rsp+0A8h+var_78]
0x18008a6b7  mov     rdx, rbp
0x18008a6ba  mov     rcx, rdi
0x18008a6bd  mov     [rdi+0C4h], al
0x18008a6c3  call    execSqlF
0x18008a6c8  mov     ebx, eax
0x18008a6ca  test    eax, eax
0x18008a6cc  jnz     loc_18008A7FA
0x18008a6d2  mov     r9, [rsp+0A8h+var_78]
0x18008a6d7  lea     r8, aSelectSqlFromW; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x18008a6de  mov     rdx, rbp
0x18008a6e1  mov     rcx, rdi
0x18008a6e4  call    execSqlF
0x18008a6e9  mov     ebx, eax
0x18008a6eb  test    eax, eax
0x18008a6ed  jnz     loc_18008A7FA
0x18008a6f3  mov     r9, [rsp+0A8h+var_78]
0x18008a6f8  lea     r8, aSelectInsertIn; "SELECT'INSERT INTO vacuum_db.'||quote(n"...
0x18008a6ff  mov     rdx, rbp
0x18008a702  mov     [rdi+0C4h], al
0x18008a708  mov     rcx, rdi
0x18008a70b  call    execSqlF
0x18008a710  and     dword ptr [rdi+2Ch], 0FFFFFFFBh
0x18008a714  mov     ebx, eax
0x18008a716  test    eax, eax
0x18008a718  jnz     loc_18008A7FA
0x18008a71e  mov     r9, [rsp+0A8h+var_78]
0x18008a723  lea     r8, aInsertIntoVacu; "INSERT INTO vacuum_db.sqlite_schema SEL"...
0x18008a72a  mov     rdx, rbp
0x18008a72d  mov     rcx, rdi
0x18008a730  call    execSqlF
0x18008a735  mov     ebx, eax
0x18008a737  test    eax, eax
0x18008a739  jnz     loc_18008A7FA
0x18008a73f  mov     [rsp+0A8h+var_88], eax
0x18008a743  xor     ebp, ebp
0x18008a745  cmp     ebp, 0Ah
0x18008a748  jge     short loc_18008A799
0x18008a74a  lea     rax, __ImageBase
0x18008a751  movsxd  rbx, ebp
0x18008a754  lea     r8, [rsp+0A8h+var_88]
0x18008a759  mov     rcx, r13
0x18008a75c  movzx   edx, byte ptr [rbx+rax+0B61D0h]
0x18008a764  call    sqlite3BtreeGetMeta
0x18008a769  lea     rax, __ImageBase
0x18008a770  mov     rcx, r14
0x18008a773  movzx   r8d, byte ptr [rbx+rax+0B61D1h]
0x18008a77c  add     r8d, [rsp+0A8h+var_88]
0x18008a781  movzx   edx, byte ptr [rbx+rax+0B61D0h]
0x18008a789  call    sqlite3BtreeUpdateMeta
0x18008a78e  mov     ebx, eax
0x18008a790  test    eax, eax
0x18008a792  jnz     short loc_18008A7FA
0x18008a794  add     ebp, 2
0x18008a797  jmp     short loc_18008A745
0x18008a799  test    r15, r15
0x18008a79c  jnz     short loc_18008A7AF
0x18008a79e  mov     rdx, r14
0x18008a7a1  mov     rcx, r13
0x18008a7a4  call    sqlite3BtreeCopyFile
0x18008a7a9  mov     ebx, eax
0x18008a7ab  test    eax, eax
0x18008a7ad  jnz     short loc_18008A7FA
0x18008a7af  mov     rcx, r14
0x18008a7b2  call    sqlite3BtreeCommit
0x18008a7b7  mov     ebx, eax
0x18008a7b9  test    eax, eax
0x18008a7bb  jnz     short loc_18008A7FA
0x18008a7bd  test    r15, r15
0x18008a7c0  jnz     short loc_18008A7FA
0x18008a7c2  mov     rcx, r14
0x18008a7c5  call    sqlite3BtreeGetAutoVacuum
0x18008a7ca  mov     edx, eax
0x18008a7cc  mov     rcx, r13
0x18008a7cf  call    sqlite3BtreeSetAutoVacuum
0x18008a7d4  mov     rcx, r14
0x18008a7d7  call    sqlite3BtreeGetRequestedReserve
0x18008a7dc  mov     rdx, [r14+8]
0x18008a7e0  mov     r9d, esi
0x18008a7e3  mov     r8d, eax
0x18008a7e6  mov     rcx, r13
0x18008a7e9  mov     edx, [rdx+34h]
0x18008a7ec  call    sqlite3BtreeSetPageSize
0x18008a7f1  mov     ebx, eax
0x18008a7f3  jmp     short loc_18008A7FA
0x18008a7f5  mov     ebx, 7
0x18008a7fa  mov     eax, [rsp+0A8h+var_6C]
0x18008a7fe  xor     r15d, r15d
0x18008a801  mov     [rdi+2Ch], eax
0x18008a804  mov     r9d, esi
0x18008a807  mov     rax, [rsp+0A8h+var_60]
0x18008a80c  xor     r8d, r8d
0x18008a80f  mov     [rdi+30h], rax
0x18008a813  or      edx, 0FFFFFFFFh
0x18008a816  mov     rax, [rsp+0A8h+var_58]
0x18008a81b  mov     rcx, r13
0x18008a81e  mov     [rdi+78h], rax
0x18008a822  mov     rax, [rsp+0A8h+var_50]
0x18008a827  mov     [rdi+80h], rax
0x18008a82e  mov     al, [rsp+0A8h+arg_8]
0x18008a835  mov     [rdi+6Eh], al
0x18008a838  mov     [rdi+0C4h], r15b
0x18008a83f  call    sqlite3BtreeSetPageSize
0x18008a844  mov     [rdi+65h], sil
0x18008a848  test    r12, r12
0x18008a84b  jz      short loc_18008A861
0x18008a84d  mov     rcx, [r12+8]
0x18008a852  call    sqlite3BtreeClose
  ... truncated ...
```

# sqlite3RunVacuum

- ea: `0x180097f9c`
- end: `0x180098479`
- name: `sqlite3RunVacuum`
- size: `1245`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800286a4`

## callees

- `0x180024b60`
- `0x180032470`
- `0x180032e28`
- `0x18003352c`
- `0x1800440f4`
- `0x180046be0`
- `0x180059d90`
- `0x18005ecf8`
- `0x18005edec`
- `0x180060c4c`
- `0x18006450c`
- `0x180064574`
- `0x180064cd4`
- `0x180067448`
- `0x18006ed3c`
- `0x18006ed54`
- `0x18007077c`
- `0x180072b8c`
- `0x1800766c8`
- `0x180090564`
- `0x1800911a0`
- `0x180097f9c`

## string_xrefs

- `0x18009813a`: `output file already exists`

## pseudocode

```c
__int64 __fastcall sqlite3RunVacuum(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const char *v9; // r8
  int v10; // r14d
  __int64 v11; // rax
  const wchar_t *v12; // r9
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
  int v25; // r10d
  unsigned int v26; // eax
  unsigned int v27; // ebx
  unsigned int AutoVacuum; // eax
  __int64 v29; // r9
  __int64 v30; // r9
  unsigned int v31; // eax
  int i; // ebp
  unsigned int v33; // eax
  unsigned int RequestedReserve; // eax
  int v35; // [rsp+20h] [rbp-88h] BYREF
  int v36; // [rsp+24h] [rbp-84h] BYREF
  __int64 v37; // [rsp+28h] [rbp-80h] BYREF
  __int64 v38; // [rsp+30h] [rbp-78h]
  int IsMemdb; // [rsp+38h] [rbp-70h]
  int v40; // [rsp+3Ch] [rbp-6Ch]
  __int64 v41; // [rsp+40h] [rbp-68h]
  __int64 v42; // [rsp+48h] [rbp-60h]
  __int64 v43; // [rsp+50h] [rbp-58h]
  __int64 v44; // [rsp+58h] [rbp-50h]
  _BYTE v45[72]; // [rsp+60h] [rbp-48h] BYREF
  char v46; // [rsp+B8h] [rbp+10h]
  unsigned int v47; // [rsp+C0h] [rbp+18h]

  v47 = a3;
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
    if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a4 + 20) & 0x3F)) != 3 )
    {
      v9 = "non-text filename";
      goto LABEL_5;
    }
    LOBYTE(a2) = 1;
    v11 = sqlite3ValueText(a4, a2);
    *(_DWORD *)(v6 + 76) &= ~1u;
    v12 = (const wchar_t *)v11;
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
  v46 = v16;
  v41 = 32 * v5;
  v18 = *(_QWORD *)(32 * v5 + v17 + 8);
  v38 = *(_QWORD *)(32 * v5 + v17);
  IsMemdb = sqlite3PagerIsMemdb(**(_QWORD **)(v18 + 8), 32 * v5, a3, v12);
  v35 = *(_DWORD *)(v6 + 40);
  v19 = execSqlF(v6, a1, "ATTACH %Q AS vacuum_db");
  *(_DWORD *)(v6 + 76) = v10;
  updated = v19;
  if ( !v19 )
  {
    v21 = 1;
    v13 = *(_QWORD *)(v6 + 32) + 32LL * v35;
    v22 = *(_QWORD *)(v13 + 8);
    if ( a4 )
    {
      v23 = *(_QWORD **)(**(_QWORD **)(v22 + 8) + 72LL);
      v37 = 0;
      if ( *v23 && ((unsigned int)sqlite3OsFileSize(v23, &v37) || v37 > 0) )
      {
        updated = 1;
        sqlite3SetString(a1, v6, "output file already exists");
        goto LABEL_46;
      }
      v24 = *(_QWORD *)(v6 + 32);
      *(_DWORD *)(v6 + 44) |= 8u;
      v21 = *(_DWORD *)(v6 + 48) & 0x38 | *(unsigned __int8 *)(v41 + v24 + 16);
    }
    LODWORD(v37) = sqlite3BtreeGetRequestedReserve(v18);
    if ( *(_DWORD *)(v6 + 116) )
    {
      v36 = 0;
      sqlite3CodecGetKey(v6, v47, v45, &v36);
      if ( v36 != v25 )
        *(_DWORD *)(v6 + 116) = v25;
    }
    sqlite3BtreeSetCacheSize(v22, *(unsigned int *)(*(_QWORD *)(v41 + *(_QWORD *)(v6 + 32) + 24) + 116LL));
    v26 = sqlite3BtreeSetSpillSize(v18, 0);
    sqlite3BtreeSetSpillSize(v22, v26);
    sqlite3BtreeSetPagerFlags(v22, v21 | 0x20u);
    updated = execSql(v6, a1, "BEGIN");
    if ( !updated )
    {
      updated = sqlite3BtreeBeginTrans(v18, a4 == 0 ? 2 : 0, 0);
      if ( !updated )
      {
        if ( *(_BYTE *)(**(_QWORD **)(v18 + 8) + 9LL) == 5 && !a4 )
          *(_DWORD *)(v6 + 116) = 0;
        v27 = v37;
        if ( (unsigned int)sqlite3BtreeSetPageSize(
                             v22,
                             *(unsigned int *)(*(_QWORD *)(v18 + 8) + 52LL),
                             (unsigned int)v37,
                             0)
          || !IsMemdb && (unsigned int)sqlite3BtreeSetPageSize(v22, *(unsigned int *)(v6 + 116), v27, 0)
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
          v29 = v38;
          *(_BYTE *)(v6 + 196) = v35;
          updated = execSqlF(
                      v6,
                      a1,
                      "SELECT sql FROM \"%w\".sqlite_schema WHERE type='table'AND name<>'sqlite_sequence' AND coalesce(rootpage,1)>0",
                      v29);
          if ( !updated )
          {
            updated = execSqlF(v6, a1, "SELECT sql FROM \"%w\".sqlite_schema WHERE type='index'", v38);
            if ( !updated )
            {
              v30 = v38;
              *(_BYTE *)(v6 + 196) = 0;
              v31 = execSqlF(
                      v6,
                      a1,
                      "SELECT'INSERT INTO vacuum_db.'||quote(name)||' SELECT*FROM\"%w\".'||quote(name)FROM vacuum_db.sqli"
                      "te_schema WHERE type='table'AND coalesce(rootpage,1)>0",
                      v30);
              *(_DWORD *)(v6 + 44) &= ~4u;
              updated = v31;
              if ( !v31 )
              {
                updated = execSqlF(
                            v6,
                            a1,
                            "INSERT INTO vacuum_db.sqlite_schema SELECT*FROM \"%w\".sqlite_schema WHERE type IN('view','t"
                            "rigger') OR(type='table'AND rootpage=0)",
                            v38);
                if ( !updated )
                {
                  v35 = 0;
                  for ( i = 0; i < 10; i += 2 )
                  {
                    sqlite3BtreeGetMeta(v18, *((unsigned __int8 *)&qword_1800BDE40[3] + i), &v35);
                    updated = sqlite3BtreeUpdateMeta(
                                v22,
                                *((unsigned __int8 *)&qword_1800BDE40[3] + i),
                                v35 + (unsigned int)*((unsigned __int8 *)&qword_1800BDE40[3] + i + 1));
                    if ( updated )
                      goto LABEL_46;
                  }
                  if ( a4 || (updated = sqlite3BtreeCopyFile(v18, v22)) == 0 )
                  {
                    updated = sqlite3BtreeCommit(v22);
                    if ( !updated && !a4 )
                    {
                      v33 = sqlite3BtreeGetAutoVacuum(v22);
                      sqlite3BtreeSetAutoVacuum(v18, v33);
                      RequestedReserve = sqlite3BtreeGetRequestedReserve(v22);
                      updated = sqlite3BtreeSetPageSize(
                                  v18,
                                  *(unsigned int *)(*(_QWORD *)(v22 + 8) + 52LL),
                                  RequestedReserve,
                                  1);
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
LABEL_46:
  *(_DWORD *)(v6 + 44) = v40;
  *(_QWORD *)(v6 + 48) = v42;
  *(_QWORD *)(v6 + 120) = v43;
  *(_QWORD *)(v6 + 128) = v44;
  *(_BYTE *)(v6 + 110) = v46;
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
0x180097f9c  mov     [rsp+arg_0], rbx
0x180097fa1  mov     [rsp+arg_10], r8d
0x180097fa6  push    rbp
0x180097fa7  push    rsi
0x180097fa8  push    rdi
0x180097fa9  push    r12
0x180097fab  push    r13
0x180097fad  push    r14
0x180097faf  push    r15
0x180097fb1  sub     rsp, 70h
0x180097fb5  cmp     byte ptr [rdx+65h], 0
0x180097fb9  mov     r15, r9
0x180097fbc  movsxd  rbx, r8d
0x180097fbf  mov     rdi, rdx
0x180097fc2  mov     rbp, rcx
0x180097fc5  jnz     short loc_180097FDD
0x180097fc7  lea     r8, aCannotVacuumFr; "cannot VACUUM from within a transaction"
0x180097fce  call    sqlite3SetString
0x180097fd3  mov     eax, 1
0x180097fd8  jmp     loc_180098461
0x180097fdd  mov     esi, 1
0x180097fe2  cmp     [rdx+0D8h], esi
0x180097fe8  jle     short loc_180097FFD
0x180097fea  lea     r8, aCannotVacuumSq; "cannot VACUUM - SQL statements in progr"...
0x180097ff1  call    sqlite3SetString
0x180097ff6  mov     eax, esi
0x180097ff8  jmp     loc_180098461
0x180097ffd  mov     r14d, [rdx+4Ch]
0x180098001  lea     rcx, __ImageBase
0x180098008  test    r15, r15
0x18009800b  jz      short loc_180098043
0x18009800d  movzx   eax, word ptr [r9+14h]
0x180098012  and     eax, 3Fh
0x180098015  cmp     byte ptr [rax+rcx+0B5270h], 3
0x18009801d  jz      short loc_18009802B
0x18009801f  lea     r8, aNonTextFilenam; "non-text filename"
0x180098026  mov     rcx, rbp
0x180098029  jmp     short loc_180097FF1
0x18009802b  mov     dl, sil
0x18009802e  mov     rcx, r15
0x180098031  call    sqlite3ValueText
0x180098036  and     dword ptr [rdi+4Ch], 0FFFFFFFEh
0x18009803a  mov     r9, rax
0x18009803d  or      dword ptr [rdi+4Ch], 6
0x180098041  jmp     short loc_18009804A
0x180098043  lea     r9, Src
0x18009804a  mov     eax, [rdi+2Ch]
0x18009804d  xor     r12d, r12d
0x180098050  mov     rcx, [rdi+30h]
0x180098054  mov     rdx, [rdi+78h]
0x180098058  mov     [rsp+0A8h+var_6C], eax
0x18009805c  or      eax, 6
0x18009805f  mov     [rdi+2Ch], eax
0x180098062  mov     rax, rcx
0x180098065  mov     [rsp+0A8h+var_58], rdx
0x18009806a  mov     rdx, [rdi+80h]
0x180098071  mov     [rsp+0A8h+var_60], rcx
0x180098076  mov     rcx, 0FFFFFFFEEFFFAFFFh
0x180098080  and     rax, rcx
0x180098083  mov     [rsp+0A8h+var_50], rdx
0x180098088  mov     dl, [rdi+6Eh]
0x18009808b  or      rax, 201h
0x180098091  mov     [rdi+30h], rax
0x180098095  mov     rax, [rdi+20h]
0x180098099  mov     [rdi+6Eh], r12b
0x18009809d  mov     [rsp+0A8h+arg_8], dl
0x1800980a4  mov     rdx, rbx
0x1800980a7  shl     rdx, 5
0x1800980ab  mov     [rsp+0A8h+var_68], rdx
0x1800980b0  mov     rcx, [rdx+rax]
0x1800980b4  mov     r13, [rdx+rax+8]
0x1800980b9  mov     [rsp+0A8h+var_78], rcx
0x1800980be  mov     rcx, [r13+8]
0x1800980c2  mov     rcx, [rcx]
0x1800980c5  call    sqlite3PagerIsMemdb
0x1800980ca  mov     [rsp+0A8h+var_70], eax
0x1800980ce  lea     r8, aAttachQAsVacuu; "ATTACH %Q AS vacuum_db"
0x1800980d5  mov     eax, [rdi+28h]
0x1800980d8  mov     rdx, rbp
0x1800980db  mov     rcx, rdi
0x1800980de  mov     [rsp+0A8h+var_88], eax
0x1800980e2  call    execSqlF
0x1800980e7  mov     [rdi+4Ch], r14d
0x1800980eb  mov     ebx, eax
0x1800980ed  test    eax, eax
0x1800980ef  jnz     loc_1800983F0
0x1800980f5  movsxd  r12, [rsp+0A8h+var_88]
0x1800980fa  mov     ebx, esi
0x1800980fc  shl     r12, 5
0x180098100  add     r12, [rdi+20h]
0x180098104  mov     r14, [r12+8]
0x180098109  test    r15, r15
0x18009810c  jz      short loc_18009816D
0x18009810e  mov     rax, [r14+8]
0x180098112  xor     ebx, ebx
0x180098114  mov     rcx, [rax]
0x180098117  mov     rcx, [rcx+48h]
0x18009811b  mov     [rsp+0A8h+var_80], rbx
0x180098120  cmp     [rcx], rbx
0x180098123  jz      short loc_180098153
0x180098125  lea     rdx, [rsp+0A8h+var_80]
0x18009812a  call    sqlite3OsFileSize
0x18009812f  test    eax, eax
0x180098131  jnz     short loc_18009813A
0x180098133  cmp     [rsp+0A8h+var_80], rbx
0x180098138  jle     short loc_180098153
0x18009813a  lea     r8, aOutputFileAlre; "output file already exists"
0x180098141  mov     rdx, rdi
0x180098144  mov     rcx, rbp
0x180098147  mov     ebx, esi
0x180098149  call    sqlite3SetString
0x18009814e  jmp     loc_1800983F0
0x180098153  mov     rax, [rdi+20h]
0x180098157  or      dword ptr [rdi+2Ch], 8
0x18009815b  mov     rcx, [rsp+0A8h+var_68]
0x180098160  movzx   ebx, byte ptr [rcx+rax+10h]
0x180098165  mov     eax, [rdi+30h]
0x180098168  and     eax, 38h
0x18009816b  or      ebx, eax
0x18009816d  mov     rcx, r13
0x180098170  call    sqlite3BtreeGetRequestedReserve
0x180098175  xor     r10d, r10d
0x180098178  mov     dword ptr [rsp+0A8h+var_80], eax
0x18009817c  cmp     [rdi+74h], r10d
0x180098180  jz      short loc_1800981AB
0x180098182  mov     edx, [rsp+0A8h+arg_10]
0x180098189  lea     r9, [rsp+0A8h+var_84]
0x18009818e  lea     r8, [rsp+0A8h+var_48]
0x180098193  mov     [rsp+0A8h+var_84], r10d
0x180098198  mov     rcx, rdi
0x18009819b  call    sqlite3CodecGetKey
0x1800981a0  cmp     [rsp+0A8h+var_84], r10d
0x1800981a5  jz      short loc_1800981AB
0x1800981a7  mov     [rdi+74h], r10d
0x1800981ab  mov     rax, [rdi+20h]
0x1800981af  mov     rcx, [rsp+0A8h+var_68]
0x1800981b4  mov     rdx, [rcx+rax+18h]
0x1800981b9  mov     rcx, r14
0x1800981bc  mov     edx, [rdx+74h]
0x1800981bf  call    sqlite3BtreeSetCacheSize
0x1800981c4  xor     edx, edx
0x1800981c6  mov     rcx, r13
0x1800981c9  call    sqlite3BtreeSetSpillSize
0x1800981ce  mov     edx, eax
0x1800981d0  mov     rcx, r14
0x1800981d3  call    sqlite3BtreeSetSpillSize
0x1800981d8  or      ebx, 20h
0x1800981db  mov     rcx, r14
0x1800981de  mov     edx, ebx
0x1800981e0  call    sqlite3BtreeSetPagerFlags
0x1800981e5  lea     r8, aBegin; "BEGIN"
0x1800981ec  mov     rdx, rbp
0x1800981ef  mov     rcx, rdi
0x1800981f2  call    execSql
0x1800981f7  mov     ebx, eax
0x1800981f9  test    eax, eax
0x1800981fb  jnz     loc_1800983F0
0x180098201  mov     rax, r15
0x180098204  mov     rcx, r13
0x180098207  neg     rax
0x18009820a  sbb     edx, edx
0x18009820c  xor     r8d, r8d
0x18009820f  not     edx
0x180098211  and     edx, 2
0x180098214  call    sqlite3BtreeBeginTrans
0x180098219  mov     ebx, eax
0x18009821b  test    eax, eax
0x18009821d  jnz     loc_1800983F0
0x180098223  mov     rax, [r13+8]
0x180098227  mov     rcx, [rax]
0x18009822a  cmp     byte ptr [rcx+9], 5
0x18009822e  jnz     short loc_180098239
0x180098230  test    r15, r15
0x180098233  jnz     short loc_180098239
0x180098235  mov     [rdi+74h], r15d
0x180098239  mov     rdx, [r13+8]
0x18009823d  xor     r9d, r9d
0x180098240  mov     ebx, dword ptr [rsp+0A8h+var_80]
0x180098244  mov     rcx, r14
0x180098247  mov     r8d, ebx
0x18009824a  mov     edx, [rdx+34h]
0x18009824d  call    sqlite3BtreeSetPageSize
0x180098252  test    eax, eax
0x180098254  jnz     loc_1800983EB
0x18009825a  cmp     [rsp+0A8h+var_70], eax
0x18009825e  jnz     short loc_180098279
0x180098260  mov     edx, [rdi+74h]
0x180098263  xor     r9d, r9d
0x180098266  mov     r8d, ebx
0x180098269  mov     rcx, r14
0x18009826c  call    sqlite3BtreeSetPageSize
0x180098271  test    eax, eax
0x180098273  jnz     loc_1800983EB
0x180098279  cmp     byte ptr [rdi+67h], 0
0x18009827d  jnz     loc_1800983EB
0x180098283  movsx   eax, byte ptr [rdi+6Ah]
0x180098287  test    al, al
0x180098289  jns     short loc_180098293
0x18009828b  mov     rcx, r13
0x18009828e  call    sqlite3BtreeGetAutoVacuum
0x180098293  mov     edx, eax
0x180098295  mov     rcx, r14
0x180098298  call    sqlite3BtreeSetAutoVacuum
0x18009829d  mov     eax, [rsp+0A8h+var_88]
0x1800982a1  lea     r8, aSelectSqlFromW_0; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x1800982a8  mov     r9, [rsp+0A8h+var_78]
0x1800982ad  mov     rdx, rbp
0x1800982b0  mov     rcx, rdi
0x1800982b3  mov     [rdi+0C4h], al
0x1800982b9  call    execSqlF
0x1800982be  mov     ebx, eax
0x1800982c0  test    eax, eax
0x1800982c2  jnz     loc_1800983F0
0x1800982c8  mov     r9, [rsp+0A8h+var_78]
0x1800982cd  lea     r8, aSelectSqlFromW; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x1800982d4  mov     rdx, rbp
0x1800982d7  mov     rcx, rdi
0x1800982da  call    execSqlF
0x1800982df  mov     ebx, eax
0x1800982e1  test    eax, eax
0x1800982e3  jnz     loc_1800983F0
0x1800982e9  mov     r9, [rsp+0A8h+var_78]
0x1800982ee  lea     r8, aSelectInsertIn; "SELECT'INSERT INTO vacuum_db.'||quote(n"...
0x1800982f5  mov     rdx, rbp
0x1800982f8  mov     [rdi+0C4h], al
0x1800982fe  mov     rcx, rdi
0x180098301  call    execSqlF
0x180098306  and     dword ptr [rdi+2Ch], 0FFFFFFFBh
0x18009830a  mov     ebx, eax
0x18009830c  test    eax, eax
0x18009830e  jnz     loc_1800983F0
0x180098314  mov     r9, [rsp+0A8h+var_78]
0x180098319  lea     r8, aInsertIntoVacu; "INSERT INTO vacuum_db.sqlite_schema SEL"...
0x180098320  mov     rdx, rbp
0x180098323  mov     rcx, rdi
0x180098326  call    execSqlF
0x18009832b  mov     ebx, eax
0x18009832d  test    eax, eax
0x18009832f  jnz     loc_1800983F0
0x180098335  mov     [rsp+0A8h+var_88], eax
0x180098339  xor     ebp, ebp
0x18009833b  cmp     ebp, 0Ah
0x18009833e  jge     short loc_18009838F
0x180098340  lea     rax, __ImageBase
0x180098347  movsxd  rbx, ebp
0x18009834a  lea     r8, [rsp+0A8h+var_88]
0x18009834f  mov     rcx, r13
0x180098352  movzx   edx, byte ptr [rbx+rax+0BDE58h]
0x18009835a  call    sqlite3BtreeGetMeta
0x18009835f  lea     rax, __ImageBase
0x180098366  mov     rcx, r14
0x180098369  movzx   r8d, byte ptr [rbx+rax+0BDE59h]
0x180098372  add     r8d, [rsp+0A8h+var_88]
0x180098377  movzx   edx, byte ptr [rbx+rax+0BDE58h]
0x18009837f  call    sqlite3BtreeUpdateMeta
0x180098384  mov     ebx, eax
0x180098386  test    eax, eax
0x180098388  jnz     short loc_1800983F0
0x18009838a  add     ebp, 2
0x18009838d  jmp     short loc_18009833B
0x18009838f  test    r15, r15
0x180098392  jnz     short loc_1800983A5
0x180098394  mov     rdx, r14
0x180098397  mov     rcx, r13
0x18009839a  call    sqlite3BtreeCopyFile
0x18009839f  mov     ebx, eax
0x1800983a1  test    eax, eax
0x1800983a3  jnz     short loc_1800983F0
0x1800983a5  mov     rcx, r14
0x1800983a8  call    sqlite3BtreeCommit
0x1800983ad  mov     ebx, eax
0x1800983af  test    eax, eax
0x1800983b1  jnz     short loc_1800983F0
0x1800983b3  test    r15, r15
0x1800983b6  jnz     short loc_1800983F0
0x1800983b8  mov     rcx, r14
0x1800983bb  call    sqlite3BtreeGetAutoVacuum
0x1800983c0  mov     edx, eax
0x1800983c2  mov     rcx, r13
0x1800983c5  call    sqlite3BtreeSetAutoVacuum
0x1800983ca  mov     rcx, r14
0x1800983cd  call    sqlite3BtreeGetRequestedReserve
0x1800983d2  mov     rdx, [r14+8]
0x1800983d6  mov     r9d, esi
0x1800983d9  mov     r8d, eax
0x1800983dc  mov     rcx, r13
0x1800983df  mov     edx, [rdx+34h]
0x1800983e2  call    sqlite3BtreeSetPageSize
0x1800983e7  mov     ebx, eax
0x1800983e9  jmp     short loc_1800983F0
0x1800983eb  mov     ebx, 7
0x1800983f0  mov     eax, [rsp+0A8h+var_6C]
0x1800983f4  xor     r15d, r15d
0x1800983f7  mov     [rdi+2Ch], eax
0x1800983fa  mov     r9d, esi
0x1800983fd  mov     rax, [rsp+0A8h+var_60]
0x180098402  xor     r8d, r8d
0x180098405  mov     [rdi+30h], rax
0x180098409  or      edx, 0FFFFFFFFh
0x18009840c  mov     rax, [rsp+0A8h+var_58]
  ... truncated ...
```

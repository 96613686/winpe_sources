# sqlite3RunVacuum

- ea: `0x180087060`
- end: `0x18008755d`
- name: `sqlite3RunVacuum`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002a050`

## callees

- `0x1800073ec`
- `0x18000875c`
- `0x180022288`
- `0x180028540`
- `0x180046938`
- `0x180057d8c`
- `0x18005a498`
- `0x18005bbe8`
- `0x18005d458`
- `0x18005deec`
- `0x18005ea50`
- `0x18005f2ec`
- `0x18005f8bc`
- `0x1800667c8`
- `0x1800668f8`
- `0x1800675fc`
- `0x180067830`
- `0x180067b40`
- `0x180068880`
- `0x180081a74`
- `0x180081ab8`
- `0x180082134`
- `0x180085d20`
- `0x180087060`

## string_xrefs

- `0x18008723e`: `output file already exists`

## pseudocode

```c
__int64 __fastcall sqlite3RunVacuum(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  bool v4; // zf
  __int64 v6; // r13
  __int64 v7; // rdi
  const char *v10; // r8
  __int64 v11; // rax
  __int64 *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r13
  __int64 v19; // r14
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
  unsigned int v31; // eax
  int i; // r15d
  unsigned int v33; // eax
  unsigned int v34; // eax
  __int64 v35; // rsi
  char v36; // [rsp+30h] [rbp-79h]
  __int64 v37; // [rsp+38h] [rbp-71h] BYREF
  __int64 v38; // [rsp+40h] [rbp-69h] BYREF
  __int64 v39; // [rsp+48h] [rbp-61h]
  int IsMemdb; // [rsp+50h] [rbp-59h]
  int v41; // [rsp+54h] [rbp-55h]
  __int64 v42; // [rsp+58h] [rbp-51h]
  __int64 v43; // [rsp+60h] [rbp-49h]
  __int64 v44; // [rsp+68h] [rbp-41h]
  __int64 v45; // [rsp+70h] [rbp-39h]
  __int64 v46; // [rsp+78h] [rbp-31h]
  _BYTE v47[48]; // [rsp+80h] [rbp-29h] BYREF

  v4 = *(_BYTE *)(a2 + 101) == 0;
  v6 = a3;
  v7 = a2;
  v38 = 0;
  if ( v4 )
  {
    sqlite3SetString(a1, a2, "cannot VACUUM from within a transaction");
    return 1;
  }
  if ( *(int *)(a2 + 216) > 1 )
  {
    v10 = "cannot VACUUM - SQL statements in progress";
LABEL_5:
    sqlite3SetString(a1, a2, v10);
    return 1;
  }
  LODWORD(v37) = *(_DWORD *)(a2 + 76);
  if ( a4 )
  {
    if ( *((_BYTE *)qword_18009EC50 + (*(_WORD *)(a4 + 20) & 0x3F)) != 3 )
    {
      v10 = "non-text filename";
      goto LABEL_5;
    }
    LOBYTE(a2) = 1;
    v11 = sqlite3ValueText(a4, a2);
    *(_DWORD *)(v7 + 76) &= ~1u;
    v12 = (__int64 *)v11;
    *(_DWORD *)(v7 + 76) |= 6u;
  }
  else
  {
    v12 = qword_18009EEF0;
  }
  v13 = *(_QWORD *)(v7 + 48);
  v14 = *(_QWORD *)(v7 + 120);
  v41 = *(_DWORD *)(v7 + 44);
  *(_DWORD *)(v7 + 44) = v41 | 6;
  v45 = v14;
  v15 = *(_QWORD *)(v7 + 128);
  v44 = v13;
  v46 = v15;
  LOBYTE(v15) = *(_BYTE *)(v7 + 110);
  *(_QWORD *)(v7 + 48) = v13 & 0xFFFFFFFEEFFFADFEuLL | 0x201;
  v16 = *(_QWORD *)(v7 + 32);
  *(_BYTE *)(v7 + 110) = 0;
  v36 = v15;
  v43 = 0;
  v42 = 32 * v6;
  v17 = *(_QWORD *)(32 * v6 + v16);
  v18 = *(_QWORD *)(32 * v6 + v16 + 8);
  v39 = v17;
  IsMemdb = sqlite3PagerIsMemdb(**(_QWORD **)(v18 + 8));
  sqlite3_randomness(8, &v38);
  sqlite3_snprintf(42, v47, "vacuum_%016llx", v38);
  v19 = *(int *)(v7 + 40);
  LODWORD(v38) = *(_DWORD *)(v7 + 40);
  updated = execSqlF(v7, a1, "ATTACH %Q AS %s", v12, v47);
  *(_DWORD *)(v7 + 76) = v37;
  if ( !updated )
  {
    v21 = 1;
    v43 = *(_QWORD *)(v7 + 32) + 32 * v19;
    v22 = *(_QWORD *)(v43 + 8);
    if ( a4 )
    {
      v23 = *(_QWORD **)(**(_QWORD **)(v22 + 8) + 72LL);
      v37 = 0;
      if ( *v23 && ((unsigned int)sqlite3OsFileSize(v23, &v37) || v37 > 0) )
      {
        updated = 1;
        sqlite3SetString(a1, v7, "output file already exists");
        goto LABEL_43;
      }
      v24 = *(_QWORD *)(v7 + 32);
      *(_DWORD *)(v7 + 44) |= 8u;
      v21 = *(_DWORD *)(v7 + 48) & 0x38 | *(unsigned __int8 *)(v42 + v24 + 16);
    }
    RequestedReserve = sqlite3BtreeGetRequestedReserve(v18);
    v26 = *(_QWORD *)(v7 + 32);
    LODWORD(v37) = RequestedReserve;
    sqlite3BtreeSetCacheSize(v22, *(unsigned int *)(*(_QWORD *)(v42 + v26 + 24) + 116LL));
    v27 = sqlite3BtreeSetSpillSize(v18, 0);
    sqlite3BtreeSetSpillSize(v22, v27);
    sqlite3BtreeSetPagerFlags(v22, v21 | 0x20u);
    updated = execSql(v7, a1, "BEGIN");
    if ( !updated )
    {
      updated = sqlite3BtreeBeginTrans(v18, a4 == 0 ? 2 : 0, 0);
      if ( !updated )
      {
        if ( *(_BYTE *)(**(_QWORD **)(v18 + 8) + 9LL) == 5 && !a4 )
          *(_DWORD *)(v7 + 116) = 0;
        v28 = v37;
        if ( (unsigned int)sqlite3BtreeSetPageSize(
                             v22,
                             *(unsigned int *)(*(_QWORD *)(v18 + 8) + 52LL),
                             (unsigned int)v37,
                             0)
          || !IsMemdb && (unsigned int)sqlite3BtreeSetPageSize(v22, *(unsigned int *)(v7 + 116), v28, 0)
          || *(_BYTE *)(v7 + 103) )
        {
          updated = 7;
        }
        else
        {
          AutoVacuum = *(char *)(v7 + 106);
          if ( *(char *)(v7 + 106) < 0 )
            AutoVacuum = sqlite3BtreeGetAutoVacuum(v18);
          sqlite3BtreeSetAutoVacuum(v22, AutoVacuum);
          v30 = v39;
          *(_BYTE *)(v7 + 196) = v38;
          updated = execSqlF(
                      v7,
                      a1,
                      "SELECT sql FROM \"%w\".sqlite_schema WHERE type='table'AND name<>'sqlite_sequence' AND coalesce(rootpage,1)>0",
                      v30);
          if ( !updated )
          {
            updated = execSqlF(v7, a1, "SELECT sql FROM \"%w\".sqlite_schema WHERE type='index'", v39);
            if ( !updated )
            {
              *(_BYTE *)(v7 + 196) = 0;
              v31 = execSqlF(
                      v7,
                      a1,
                      "SELECT'INSERT INTO %s.'||quote(name)||' SELECT*FROM\"%w\".'||quote(name)FROM %s.sqlite_schema WHER"
                      "E type='table'AND coalesce(rootpage,1)>0",
                      v47,
                      v39,
                      v47);
              *(_DWORD *)(v7 + 44) &= ~4u;
              updated = v31;
              if ( !v31 )
              {
                updated = execSqlF(
                            v7,
                            a1,
                            "INSERT INTO %s.sqlite_schema SELECT*FROM \"%w\".sqlite_schema WHERE type IN('view','trigger'"
                            ") OR(type='table'AND rootpage=0)",
                            v47,
                            v39);
                if ( !updated )
                {
                  LODWORD(v37) = 0;
                  for ( i = 0; i < 10; i += 2 )
                  {
                    sqlite3BtreeGetMeta(v18, *((unsigned __int8 *)qword_1800A6550 + i), &v37);
                    updated = sqlite3BtreeUpdateMeta(
                                v22,
                                *((unsigned __int8 *)qword_1800A6550 + i),
                                (unsigned int)v37 + *((unsigned __int8 *)qword_1800A6550 + i + 1));
                    if ( updated )
                      goto LABEL_43;
                  }
                  if ( a4 || (updated = sqlite3BtreeCopyFile(v18, v22)) == 0 )
                  {
                    updated = sqlite3BtreeCommit(v22);
                    if ( !updated && !a4 )
                    {
                      v33 = sqlite3BtreeGetAutoVacuum(v22);
                      sqlite3BtreeSetAutoVacuum(v18, v33);
                      v34 = sqlite3BtreeGetRequestedReserve(v22);
                      updated = sqlite3BtreeSetPageSize(v18, *(unsigned int *)(*(_QWORD *)(v22 + 8) + 52LL), v34, 1);
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
  *(_DWORD *)(v7 + 44) = v41;
  *(_QWORD *)(v7 + 48) = v44;
  *(_QWORD *)(v7 + 120) = v45;
  *(_QWORD *)(v7 + 128) = v46;
  *(_BYTE *)(v7 + 110) = v36;
  *(_BYTE *)(v7 + 196) = 0;
  sqlite3BtreeSetPageSize(v18, 0xFFFFFFFFLL, 0, 1);
  *(_BYTE *)(v7 + 101) = 1;
  v35 = v43;
  if ( v43 )
  {
    sqlite3BtreeClose(*(_QWORD *)(v43 + 8));
    *(_QWORD *)(v35 + 8) = 0;
    *(_QWORD *)(v35 + 24) = 0;
  }
  sqlite3ResetAllSchemasOfConnection(v7);
  return updated;
}

```

## disassembly

```asm
0x180087060  push    rbp
0x180087062  push    rbx
0x180087063  push    rsi
0x180087064  push    rdi
0x180087065  push    r12
0x180087067  push    r13
0x180087069  push    r14
0x18008706b  push    r15
0x18008706d  lea     rbp, [rsp-1Fh]
0x180087072  sub     rsp, 0C8h
0x180087079  mov     rax, cs:__security_cookie
0x180087080  xor     rax, rsp
0x180087083  mov     [rbp+57h+var_50], rax
0x180087087  cmp     byte ptr [rdx+65h], 0
0x18008708b  mov     r12, r9
0x18008708e  movsxd  r13, r8d
0x180087091  mov     rdi, rdx
0x180087094  mov     r15, rcx
0x180087097  mov     [rbp+57h+var_C0], 0
0x18008709f  jnz     short loc_1800870B7
0x1800870a1  lea     r8, aCannotVacuumFr; "cannot VACUUM from within a transaction"
0x1800870a8  call    sqlite3SetString
0x1800870ad  mov     eax, 1
0x1800870b2  jmp     loc_18008753D
0x1800870b7  mov     esi, 1
0x1800870bc  cmp     [rdx+0D8h], esi
0x1800870c2  jle     short loc_1800870D7
0x1800870c4  lea     r8, aCannotVacuumSq; "cannot VACUUM - SQL statements in progr"...
0x1800870cb  call    sqlite3SetString
0x1800870d0  mov     eax, esi
0x1800870d2  jmp     loc_18008753D
0x1800870d7  mov     eax, [rdx+4Ch]
0x1800870da  lea     rcx, cs:180000000h
0x1800870e1  mov     dword ptr [rbp+57h+var_C8], eax
0x1800870e4  test    r12, r12
0x1800870e7  jz      short loc_18008711F
0x1800870e9  movzx   eax, word ptr [r9+14h]
0x1800870ee  and     eax, 3Fh
0x1800870f1  cmp     byte ptr [rax+rcx+9EC50h], 3
0x1800870f9  jz      short loc_180087107
0x1800870fb  lea     r8, aNonTextFilenam; "non-text filename"
0x180087102  mov     rcx, r15
0x180087105  jmp     short loc_1800870CB
0x180087107  mov     dl, sil
0x18008710a  mov     rcx, r12
0x18008710d  call    sqlite3ValueText
0x180087112  and     dword ptr [rdi+4Ch], 0FFFFFFFEh
0x180087116  mov     rbx, rax
0x180087119  or      dword ptr [rdi+4Ch], 6
0x18008711d  jmp     short loc_180087126
0x18008711f  lea     rbx, qword_18009EEF0
0x180087126  mov     eax, [rdi+2Ch]
0x180087129  xor     r14d, r14d
0x18008712c  mov     rcx, [rdi+30h]
0x180087130  mov     rdx, [rdi+78h]
0x180087134  mov     [rbp+57h+var_AC], eax
0x180087137  or      eax, 6
0x18008713a  mov     [rdi+2Ch], eax
0x18008713d  mov     rax, rcx
0x180087140  mov     [rbp+57h+var_90], rdx
0x180087144  mov     rdx, [rdi+80h]
0x18008714b  mov     [rbp+57h+var_98], rcx
0x18008714f  mov     rcx, 0FFFFFFFEEFFFAFFFh
0x180087159  and     rax, rcx
0x18008715c  mov     [rbp+57h+var_88], rdx
0x180087160  mov     dl, [rdi+6Eh]
0x180087163  or      rax, 201h
0x180087169  mov     [rdi+30h], rax
0x18008716d  mov     rax, [rdi+20h]
0x180087171  mov     [rdi+6Eh], r14b
0x180087175  mov     [rbp+57h+var_D0], dl
0x180087178  mov     rdx, r13
0x18008717b  shl     rdx, 5
0x18008717f  mov     [rbp+57h+var_A0], r14
0x180087183  mov     [rbp+57h+var_A8], rdx
0x180087187  mov     rcx, [rdx+rax]
0x18008718b  mov     r13, [rdx+rax+8]
0x180087190  mov     [rbp+57h+var_B8], rcx
0x180087194  mov     rcx, [r13+8]
0x180087198  mov     rcx, [rcx]
0x18008719b  call    sqlite3PagerIsMemdb
0x1800871a0  lea     rdx, [rbp+57h+var_C0]
0x1800871a4  mov     [rbp+57h+var_B0], eax
0x1800871a7  lea     ecx, [r14+8]
0x1800871ab  call    sqlite3_randomness
0x1800871b0  mov     r9, [rbp+57h+var_C0]
0x1800871b4  lea     r8, aVacuum016llx; "vacuum_%016llx"
0x1800871bb  lea     rdx, [rbp+57h+var_80]
0x1800871bf  lea     ecx, [r14+2Ah]
0x1800871c3  call    sqlite3_snprintf
0x1800871c8  movsxd  r14, dword ptr [rdi+28h]
0x1800871cc  lea     rax, [rbp+57h+var_80]
0x1800871d0  mov     r9, rbx
0x1800871d3  mov     [rsp+100h+var_E0], rax
0x1800871d8  lea     r8, aAttachQAsS; "ATTACH %Q AS %s"
0x1800871df  mov     dword ptr [rbp+57h+var_C0], r14d
0x1800871e3  mov     rdx, r15
0x1800871e6  mov     rcx, rdi
0x1800871e9  call    execSqlF
0x1800871ee  mov     ebx, eax
0x1800871f0  mov     eax, dword ptr [rbp+57h+var_C8]
0x1800871f3  mov     [rdi+4Ch], eax
0x1800871f6  test    ebx, ebx
0x1800871f8  jnz     loc_1800874D3
0x1800871fe  shl     r14, 5
0x180087202  mov     ebx, esi
0x180087204  add     r14, [rdi+20h]
0x180087208  mov     [rbp+57h+var_A0], r14
0x18008720c  mov     r14, [r14+8]
0x180087210  test    r12, r12
0x180087213  jz      short loc_180087270
0x180087215  mov     rax, [r14+8]
0x180087219  xor     ebx, ebx
0x18008721b  mov     rcx, [rax]
0x18008721e  mov     rcx, [rcx+48h]
0x180087222  mov     [rbp+57h+var_C8], rbx
0x180087226  cmp     [rcx], rbx
0x180087229  jz      short loc_180087257
0x18008722b  lea     rdx, [rbp+57h+var_C8]
0x18008722f  call    sqlite3OsFileSize
0x180087234  test    eax, eax
0x180087236  jnz     short loc_18008723E
0x180087238  cmp     [rbp+57h+var_C8], rbx
0x18008723c  jle     short loc_180087257
0x18008723e  lea     r8, aOutputFileAlre; "output file already exists"
0x180087245  mov     rdx, rdi
0x180087248  mov     rcx, r15
0x18008724b  mov     ebx, esi
0x18008724d  call    sqlite3SetString
0x180087252  jmp     loc_1800874D3
0x180087257  mov     rax, [rdi+20h]
0x18008725b  or      dword ptr [rdi+2Ch], 8
0x18008725f  mov     rcx, [rbp+57h+var_A8]
0x180087263  movzx   ebx, byte ptr [rcx+rax+10h]
0x180087268  mov     eax, [rdi+30h]
0x18008726b  and     eax, 38h
0x18008726e  or      ebx, eax
0x180087270  mov     rcx, r13
0x180087273  call    sqlite3BtreeGetRequestedReserve
0x180087278  mov     rcx, [rdi+20h]
0x18008727c  mov     dword ptr [rbp+57h+var_C8], eax
0x18008727f  mov     rax, [rbp+57h+var_A8]
0x180087283  mov     rdx, [rax+rcx+18h]
0x180087288  mov     rcx, r14
0x18008728b  mov     edx, [rdx+74h]
0x18008728e  call    sqlite3BtreeSetCacheSize
0x180087293  xor     edx, edx
0x180087295  mov     rcx, r13
0x180087298  call    sqlite3BtreeSetSpillSize
0x18008729d  mov     edx, eax
0x18008729f  mov     rcx, r14
0x1800872a2  call    sqlite3BtreeSetSpillSize
0x1800872a7  or      ebx, 20h
0x1800872aa  mov     rcx, r14
0x1800872ad  mov     edx, ebx
0x1800872af  call    sqlite3BtreeSetPagerFlags
0x1800872b4  lea     r8, aBegin; "BEGIN"
0x1800872bb  mov     rdx, r15
0x1800872be  mov     rcx, rdi
0x1800872c1  call    execSql
0x1800872c6  mov     ebx, eax
0x1800872c8  test    eax, eax
0x1800872ca  jnz     loc_1800874D3
0x1800872d0  mov     rax, r12
0x1800872d3  mov     rcx, r13
0x1800872d6  neg     rax
0x1800872d9  sbb     edx, edx
0x1800872db  xor     r8d, r8d
0x1800872de  not     edx
0x1800872e0  and     edx, 2
0x1800872e3  call    sqlite3BtreeBeginTrans
0x1800872e8  mov     ebx, eax
0x1800872ea  test    eax, eax
0x1800872ec  jnz     loc_1800874D3
0x1800872f2  mov     rax, [r13+8]
0x1800872f6  mov     rcx, [rax]
0x1800872f9  cmp     byte ptr [rcx+9], 5
0x1800872fd  jnz     short loc_180087308
0x1800872ff  test    r12, r12
0x180087302  jnz     short loc_180087308
0x180087304  mov     [rdi+74h], r12d
0x180087308  mov     rdx, [r13+8]
0x18008730c  xor     r9d, r9d
0x18008730f  mov     ebx, dword ptr [rbp+57h+var_C8]
0x180087312  mov     rcx, r14
0x180087315  mov     r8d, ebx
0x180087318  mov     edx, [rdx+34h]
0x18008731b  call    sqlite3BtreeSetPageSize
0x180087320  test    eax, eax
0x180087322  jnz     loc_1800874CE
0x180087328  cmp     [rbp+57h+var_B0], eax
0x18008732b  jnz     short loc_180087346
0x18008732d  mov     edx, [rdi+74h]
0x180087330  xor     r9d, r9d
0x180087333  mov     r8d, ebx
0x180087336  mov     rcx, r14
0x180087339  call    sqlite3BtreeSetPageSize
0x18008733e  test    eax, eax
0x180087340  jnz     loc_1800874CE
0x180087346  cmp     byte ptr [rdi+67h], 0
0x18008734a  jnz     loc_1800874CE
0x180087350  movsx   eax, byte ptr [rdi+6Ah]
0x180087354  test    al, al
0x180087356  jns     short loc_180087360
0x180087358  mov     rcx, r13
0x18008735b  call    sqlite3BtreeGetAutoVacuum
0x180087360  mov     edx, eax
0x180087362  mov     rcx, r14
0x180087365  call    sqlite3BtreeSetAutoVacuum
0x18008736a  mov     eax, dword ptr [rbp+57h+var_C0]
0x18008736d  lea     r8, aSelectSqlFromW_0; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x180087374  mov     r9, [rbp+57h+var_B8]
0x180087378  mov     rdx, r15
0x18008737b  mov     rcx, rdi
0x18008737e  mov     [rdi+0C4h], al
0x180087384  call    execSqlF
0x180087389  mov     ebx, eax
0x18008738b  test    eax, eax
0x18008738d  jnz     loc_1800874D3
0x180087393  mov     r9, [rbp+57h+var_B8]
0x180087397  lea     r8, aSelectSqlFromW; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x18008739e  mov     rdx, r15
0x1800873a1  mov     rcx, rdi
0x1800873a4  call    execSqlF
0x1800873a9  mov     ebx, eax
0x1800873ab  test    eax, eax
0x1800873ad  jnz     loc_1800874D3
0x1800873b3  mov     [rdi+0C4h], al
0x1800873b9  lea     r9, [rbp+57h+var_80]
0x1800873bd  lea     rax, [rbp+57h+var_80]
0x1800873c1  mov     rdx, r15
0x1800873c4  mov     [rsp+100h+var_D8], rax
0x1800873c9  lea     r8, aSelectInsertIn; "SELECT'INSERT INTO %s.'||quote(name)||'"...
0x1800873d0  mov     rax, [rbp+57h+var_B8]
0x1800873d4  mov     rcx, rdi
0x1800873d7  mov     [rsp+100h+var_E0], rax
0x1800873dc  call    execSqlF
0x1800873e1  and     dword ptr [rdi+2Ch], 0FFFFFFFBh
0x1800873e5  mov     ebx, eax
0x1800873e7  test    eax, eax
0x1800873e9  jnz     loc_1800874D3
0x1800873ef  mov     rax, [rbp+57h+var_B8]
0x1800873f3  lea     r9, [rbp+57h+var_80]
0x1800873f7  lea     r8, aInsertIntoSSql; "INSERT INTO %s.sqlite_schema SELECT*FRO"...
0x1800873fe  mov     [rsp+100h+var_E0], rax
0x180087403  mov     rdx, r15
0x180087406  mov     rcx, rdi
0x180087409  call    execSqlF
0x18008740e  mov     ebx, eax
0x180087410  test    eax, eax
0x180087412  jnz     loc_1800874D3
0x180087418  mov     dword ptr [rbp+57h+var_C8], eax
0x18008741b  xor     r15d, r15d
0x18008741e  cmp     r15d, 0Ah
0x180087422  jge     short loc_180087472
0x180087424  lea     rax, cs:180000000h
0x18008742b  movsxd  rbx, r15d
0x18008742e  lea     r8, [rbp+57h+var_C8]
0x180087432  mov     rcx, r13
0x180087435  movzx   edx, byte ptr [rbx+rax+0A6550h]
0x18008743d  call    sqlite3BtreeGetMeta
0x180087442  lea     rax, cs:180000000h
0x180087449  mov     rcx, r14
0x18008744c  movzx   r8d, byte ptr [rbx+rax+0A6551h]
0x180087455  add     r8d, dword ptr [rbp+57h+var_C8]
0x180087459  movzx   edx, byte ptr [rbx+rax+0A6550h]
0x180087461  call    sqlite3BtreeUpdateMeta
0x180087466  mov     ebx, eax
0x180087468  test    eax, eax
0x18008746a  jnz     short loc_1800874D3
0x18008746c  add     r15d, 2
0x180087470  jmp     short loc_18008741E
0x180087472  test    r12, r12
0x180087475  jnz     short loc_180087488
0x180087477  mov     rdx, r14
0x18008747a  mov     rcx, r13
0x18008747d  call    sqlite3BtreeCopyFile
0x180087482  mov     ebx, eax
0x180087484  test    eax, eax
0x180087486  jnz     short loc_1800874D3
0x180087488  mov     rcx, r14
0x18008748b  call    sqlite3BtreeCommit
0x180087490  mov     ebx, eax
0x180087492  test    eax, eax
0x180087494  jnz     short loc_1800874D3
0x180087496  test    r12, r12
0x180087499  jnz     short loc_1800874D3
0x18008749b  mov     rcx, r14
0x18008749e  call    sqlite3BtreeGetAutoVacuum
0x1800874a3  mov     edx, eax
0x1800874a5  mov     rcx, r13
0x1800874a8  call    sqlite3BtreeSetAutoVacuum
0x1800874ad  mov     rcx, r14
0x1800874b0  call    sqlite3BtreeGetRequestedReserve
0x1800874b5  mov     rdx, [r14+8]
0x1800874b9  mov     r9d, esi
0x1800874bc  mov     r8d, eax
0x1800874bf  mov     rcx, r13
0x1800874c2  mov     edx, [rdx+34h]
0x1800874c5  call    sqlite3BtreeSetPageSize
  ... truncated ...
```

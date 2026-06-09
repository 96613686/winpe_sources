# sqlite3RunVacuum

- ea: `0x18008af1c`
- end: `0x18008b401`
- name: `sqlite3RunVacuum`
- size: `1253`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180092f80`

## callees

- `0x180043578`
- `0x18004367c`
- `0x18006a66c`
- `0x18006a7c8`
- `0x18006a988`
- `0x18006ab30`
- `0x18006b3ec`
- `0x18006b458`
- `0x18006b4d4`
- `0x18006d0c4`
- `0x18006d144`
- `0x18006d1c4`
- `0x18006d2a8`
- `0x18006d30c`
- `0x18006da8c`
- `0x18008a024`
- `0x18008af1c`
- `0x18008dccc`
- `0x180092290`
- `0x1800ca010`

## string_xrefs

- `0x18008b0ce`: `output file already exists`

## pseudocode

```c
__int64 __fastcall sqlite3RunVacuum(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  const char *v9; // r8
  int v10; // r15d
  __int64 v11; // rax
  const wchar_t *v12; // r9
  __int64 v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r13
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int updated; // ebx
  __int64 v24; // r15
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  unsigned int AutoVacuum; // eax
  __int64 v31; // r9
  __int64 v32; // r9
  unsigned int v33; // eax
  __int64 v34; // rbp
  unsigned int v35; // eax
  unsigned int RequestedReserve; // eax
  __int64 v37; // [rsp+20h] [rbp-88h] BYREF
  __int64 v38; // [rsp+28h] [rbp-80h] BYREF
  __int64 v39; // [rsp+30h] [rbp-78h]
  int v40; // [rsp+38h] [rbp-70h]
  __int64 v41; // [rsp+40h] [rbp-68h]
  __int64 v42; // [rsp+48h] [rbp-60h]
  __int64 v43; // [rsp+50h] [rbp-58h]
  __int64 v44; // [rsp+58h] [rbp-50h]
  char v45; // [rsp+B8h] [rbp+10h]

  v4 = a3;
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
    if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(a4 + 20) & 0x3F)) != 3 )
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
  v42 = v14;
  v43 = v15;
  v16 = *(_QWORD *)(v6 + 128);
  *(_QWORD *)(v6 + 48) = v14 & 0xFFFFFFFEEFFFADFEuLL | 0x201;
  v17 = *(_QWORD *)(v6 + 32);
  v44 = v16;
  LOBYTE(v16) = *(_BYTE *)(v6 + 110);
  *(_BYTE *)(v6 + 110) = 0;
  v18 = *(_QWORD *)(32 * v4 + v17 + 8);
  v45 = v16;
  v19 = *(_QWORD *)(32 * v4 + v17);
  v41 = 32 * v4;
  v20 = *(__int64 **)(v18 + 8);
  v39 = v19;
  v21 = *v20;
  if ( *(_BYTE *)(*v20 + 16) || (HIDWORD(v37) = 0, *(_BYTE *)(v21 + 20)) )
    HIDWORD(v37) = 1;
  LODWORD(v37) = *(_DWORD *)(v6 + 40);
  v22 = execSqlF(v6, a1, "ATTACH %Q AS vacuum_db", v12, v37);
  *(_DWORD *)(v6 + 76) = v10;
  updated = v22;
  if ( !v22 )
  {
    updated = 1;
    v13 = *(_QWORD *)(v6 + 32) + 32LL * (int)v37;
    v24 = *(_QWORD *)(v13 + 8);
    if ( a4 )
    {
      v25 = *(_QWORD *)(**(_QWORD **)(v24 + 8) + 72LL);
      v38 = 0;
      if ( *(_QWORD *)v25
        && ((*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 48LL))(v25, &v38) || v38 > 0) )
      {
        sqlite3SetString(a1, v6, "output file already exists");
        goto LABEL_49;
      }
      v26 = *(_QWORD *)(v6 + 32);
      *(_DWORD *)(v6 + 44) |= 8u;
      updated = *(_DWORD *)(v6 + 48) & 0x38 | *(unsigned __int8 *)(v41 + v26 + 16);
    }
    LODWORD(v38) = sqlite3BtreeGetRequestedReserve(v18);
    if ( *(_DWORD *)(v6 + 116) )
    {
      v27 = *(_QWORD *)(**(_QWORD **)(*(_QWORD *)(v41 + *(_QWORD *)(v6 + 32) + 8) + 8LL) + 304LL);
      if ( v27 )
      {
        if ( *(_QWORD *)(v27 + 8) )
          *(_DWORD *)(v6 + 116) = 0;
      }
    }
    sqlite3BtreeSetCacheSize(v24, *(unsigned int *)(*(_QWORD *)(v41 + *(_QWORD *)(v6 + 32) + 24) + 116LL));
    v28 = sqlite3BtreeSetSpillSize(v18, 0);
    sqlite3BtreeSetSpillSize(v24, v28);
    sqlite3BtreeSetPagerFlags(v24, updated | 0x20);
    updated = execSql(v6, a1, "BEGIN");
    if ( !updated )
    {
      updated = sqlite3BtreeBeginTrans(v18, a4 == 0 ? 2 : 0, 0);
      if ( !updated )
      {
        if ( *(_BYTE *)(**(_QWORD **)(v18 + 8) + 9LL) == 5 && !a4 )
          *(_DWORD *)(v6 + 116) = 0;
        v29 = v38;
        if ( (unsigned int)sqlite3BtreeSetPageSize(
                             v24,
                             *(unsigned int *)(*(_QWORD *)(v18 + 8) + 52LL),
                             (unsigned int)v38,
                             0)
          || !HIDWORD(v37) && (unsigned int)sqlite3BtreeSetPageSize(v24, *(unsigned int *)(v6 + 116), v29, 0)
          || *(_BYTE *)(v6 + 103) )
        {
          updated = 7;
        }
        else
        {
          AutoVacuum = *(char *)(v6 + 106);
          if ( *(char *)(v6 + 106) < 0 )
            AutoVacuum = sqlite3BtreeGetAutoVacuum(v18);
          sqlite3BtreeSetAutoVacuum(v24, AutoVacuum);
          v31 = v39;
          *(_BYTE *)(v6 + 196) = v37;
          updated = execSqlF(
                      v6,
                      a1,
                      "SELECT sql FROM \"%w\".sqlite_schema WHERE type='table'AND name<>'sqlite_sequence' AND coalesce(rootpage,1)>0",
                      v31);
          if ( !updated )
          {
            updated = execSqlF(v6, a1, "SELECT sql FROM \"%w\".sqlite_schema WHERE type='index'", v39);
            if ( !updated )
            {
              v32 = v39;
              *(_BYTE *)(v6 + 196) = 0;
              v33 = execSqlF(
                      v6,
                      a1,
                      "SELECT'INSERT INTO vacuum_db.'||quote(name)||' SELECT*FROM\"%w\".'||quote(name)FROM vacuum_db.sqli"
                      "te_schema WHERE type='table'AND coalesce(rootpage,1)>0",
                      v32);
              *(_DWORD *)(v6 + 44) &= ~4u;
              updated = v33;
              if ( !v33 )
              {
                updated = execSqlF(
                            v6,
                            a1,
                            "INSERT INTO vacuum_db.sqlite_schema SELECT*FROM \"%w\".sqlite_schema WHERE type IN('view','t"
                            "rigger') OR(type='table'AND rootpage=0)",
                            v39);
                if ( !updated )
                {
                  LODWORD(v37) = 0;
                  v34 = 0;
                  while ( 1 )
                  {
                    sqlite3BtreeGetMeta(v18, *((unsigned __int8 *)&qword_1800FB1A0[52] + v34), &v37);
                    updated = sqlite3BtreeUpdateMeta(
                                v24,
                                *((unsigned __int8 *)&qword_1800FB1A0[52] + v34),
                                (unsigned int)v37 + *((unsigned __int8 *)&qword_1800FB1A0[52] + v34 + 1));
                    if ( updated )
                      break;
                    v34 = (unsigned int)(v34 + 2);
                    if ( (int)v34 >= 10 )
                    {
                      if ( a4 || (updated = sqlite3BtreeCopyFile(v18, v24)) == 0 )
                      {
                        updated = sqlite3BtreeCommit(v24);
                        if ( !updated && !a4 )
                        {
                          v35 = sqlite3BtreeGetAutoVacuum(v24);
                          sqlite3BtreeSetAutoVacuum(v18, v35);
                          RequestedReserve = sqlite3BtreeGetRequestedReserve(v24);
                          updated = sqlite3BtreeSetPageSize(
                                      v18,
                                      *(unsigned int *)(*(_QWORD *)(v24 + 8) + 52LL),
                                      RequestedReserve,
                                      1);
                        }
                      }
                      break;
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
LABEL_49:
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
0x18008af1c  push    rbx
0x18008af1e  push    rbp
0x18008af1f  push    rsi
0x18008af20  push    rdi
0x18008af21  push    r12
0x18008af23  push    r13
0x18008af25  push    r14
0x18008af27  push    r15
0x18008af29  sub     rsp, 68h
0x18008af2d  movsxd  rbx, r8d
0x18008af30  mov     r14, r9
0x18008af33  xor     r8d, r8d
0x18008af36  mov     rdi, rdx
0x18008af39  mov     rbp, rcx
0x18008af3c  cmp     [rdx+65h], r8b
0x18008af40  jnz     short loc_18008AF58
0x18008af42  lea     r8, aCannotVacuumFr; "cannot VACUUM from within a transaction"
0x18008af49  call    sqlite3SetString
0x18008af4e  mov     eax, 1
0x18008af53  jmp     loc_18008B3F0
0x18008af58  mov     esi, 1
0x18008af5d  cmp     [rdx+0D8h], esi
0x18008af63  jle     short loc_18008AF78
0x18008af65  lea     r8, aCannotVacuumSq; "cannot VACUUM - SQL statements in progr"...
0x18008af6c  call    sqlite3SetString
0x18008af71  mov     eax, esi
0x18008af73  jmp     loc_18008B3F0
0x18008af78  mov     r15d, [rdx+4Ch]
0x18008af7c  lea     rcx, cs:180000000h
0x18008af83  test    r14, r14
0x18008af86  jz      short loc_18008AFC1
0x18008af88  movzx   eax, word ptr [r9+14h]
0x18008af8d  and     eax, 3Fh
0x18008af90  cmp     byte ptr [rax+rcx+0FE430h], 3
0x18008af98  jz      short loc_18008AFA6
0x18008af9a  lea     r8, aNonTextFilenam; "non-text filename"
0x18008afa1  mov     rcx, rbp
0x18008afa4  jmp     short loc_18008AF6C
0x18008afa6  mov     dl, sil
0x18008afa9  mov     rcx, r14
0x18008afac  call    sqlite3ValueText
0x18008afb1  and     dword ptr [rdi+4Ch], 0FFFFFFFEh
0x18008afb5  mov     r9, rax
0x18008afb8  or      dword ptr [rdi+4Ch], 6
0x18008afbc  xor     r8d, r8d
0x18008afbf  jmp     short loc_18008AFC8
0x18008afc1  lea     r9, Src
0x18008afc8  mov     eax, [rdi+2Ch]
0x18008afcb  mov     r12, r8
0x18008afce  mov     rcx, [rdi+30h]
0x18008afd2  mov     rdx, [rdi+78h]
0x18008afd6  mov     [rsp+0A8h+var_70], eax
0x18008afda  or      eax, 6
0x18008afdd  mov     [rdi+2Ch], eax
0x18008afe0  mov     rax, rcx
0x18008afe3  mov     [rsp+0A8h+var_60], rcx
0x18008afe8  mov     rcx, 0FFFFFFFEEFFFAFFFh
0x18008aff2  and     rax, rcx
0x18008aff5  mov     [rsp+0A8h+var_58], rdx
0x18008affa  mov     rdx, [rdi+80h]
0x18008b001  or      rax, 201h
0x18008b007  mov     [rdi+30h], rax
0x18008b00b  mov     rcx, rbx
0x18008b00e  mov     rax, [rdi+20h]
0x18008b012  shl     rcx, 5
0x18008b016  mov     [rsp+0A8h+var_50], rdx
0x18008b01b  mov     dl, [rdi+6Eh]
0x18008b01e  mov     [rdi+6Eh], r8b
0x18008b022  mov     r13, [rcx+rax+8]
0x18008b027  mov     [rsp+0A8h+arg_8], dl
0x18008b02e  mov     rdx, [rcx+rax]
0x18008b032  mov     [rsp+0A8h+var_68], rcx
0x18008b037  mov     rax, [r13+8]
0x18008b03b  mov     [rsp+0A8h+var_78], rdx
0x18008b040  mov     rcx, [rax]
0x18008b043  cmp     [rcx+10h], r8b
0x18008b047  jnz     short loc_18008B054
0x18008b049  mov     [rsp+0A8h+var_84], r8d
0x18008b04e  cmp     [rcx+14h], r8b
0x18008b052  jz      short loc_18008B058
0x18008b054  mov     [rsp+0A8h+var_84], esi
0x18008b058  mov     eax, [rdi+28h]
0x18008b05b  lea     r8, aAttachQAsVacuu; "ATTACH %Q AS vacuum_db"
0x18008b062  mov     rdx, rbp
0x18008b065  mov     [rsp+0A8h+var_88], eax
0x18008b069  mov     rcx, rdi
0x18008b06c  call    execSqlF
0x18008b071  mov     [rdi+4Ch], r15d
0x18008b075  mov     ebx, eax
0x18008b077  test    eax, eax
0x18008b079  jnz     loc_18008B37F
0x18008b07f  movsxd  r12, [rsp+0A8h+var_88]
0x18008b084  mov     ebx, esi
0x18008b086  shl     r12, 5
0x18008b08a  add     r12, [rdi+20h]
0x18008b08e  mov     r15, [r12+8]
0x18008b093  test    r14, r14
0x18008b096  jz      short loc_18008B0FF
0x18008b098  mov     rax, [r15+8]
0x18008b09c  mov     rcx, [rax]
0x18008b09f  mov     rcx, [rcx+48h]
0x18008b0a3  mov     [rsp+0A8h+var_80], 0
0x18008b0ac  mov     rax, [rcx]
0x18008b0af  test    rax, rax
0x18008b0b2  jz      short loc_18008B0E5
0x18008b0b4  mov     rax, [rax+30h]
0x18008b0b8  lea     rdx, [rsp+0A8h+var_80]
0x18008b0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b0c2  test    eax, eax
0x18008b0c4  jnz     short loc_18008B0CE
0x18008b0c6  cmp     [rsp+0A8h+var_80], 0
0x18008b0cc  jle     short loc_18008B0E5
0x18008b0ce  lea     r8, aOutputFileAlre; "output file already exists"
0x18008b0d5  mov     rdx, rdi
0x18008b0d8  mov     rcx, rbp
0x18008b0db  call    sqlite3SetString
0x18008b0e0  jmp     loc_18008B37F
0x18008b0e5  mov     rax, [rdi+20h]
0x18008b0e9  or      dword ptr [rdi+2Ch], 8
0x18008b0ed  mov     rcx, [rsp+0A8h+var_68]
0x18008b0f2  movzx   ebx, byte ptr [rcx+rax+10h]
0x18008b0f7  mov     eax, [rdi+30h]
0x18008b0fa  and     eax, 38h
0x18008b0fd  or      ebx, eax
0x18008b0ff  mov     rcx, r13
0x18008b102  call    sqlite3BtreeGetRequestedReserve
0x18008b107  xor     r8d, r8d
0x18008b10a  mov     dword ptr [rsp+0A8h+var_80], eax
0x18008b10e  cmp     [rdi+74h], r8d
0x18008b112  jz      short loc_18008B13F
0x18008b114  mov     rcx, [rdi+20h]
0x18008b118  mov     rax, [rsp+0A8h+var_68]
0x18008b11d  mov     rdx, [rax+rcx+8]
0x18008b122  mov     rcx, [rdx+8]
0x18008b126  mov     rdx, [rcx]
0x18008b129  mov     rcx, [rdx+130h]
0x18008b130  test    rcx, rcx
0x18008b133  jz      short loc_18008B13F
0x18008b135  cmp     [rcx+8], r8
0x18008b139  jz      short loc_18008B13F
0x18008b13b  mov     [rdi+74h], r8d
0x18008b13f  mov     rax, [rdi+20h]
0x18008b143  mov     rcx, [rsp+0A8h+var_68]
0x18008b148  mov     rdx, [rcx+rax+18h]
0x18008b14d  mov     rcx, r15
0x18008b150  mov     edx, [rdx+74h]
0x18008b153  call    sqlite3BtreeSetCacheSize
0x18008b158  xor     edx, edx
0x18008b15a  mov     rcx, r13
0x18008b15d  call    sqlite3BtreeSetSpillSize
0x18008b162  mov     edx, eax
0x18008b164  mov     rcx, r15
0x18008b167  call    sqlite3BtreeSetSpillSize
0x18008b16c  or      ebx, 20h
0x18008b16f  mov     rcx, r15
0x18008b172  mov     edx, ebx
0x18008b174  call    sqlite3BtreeSetPagerFlags
0x18008b179  lea     r8, aBegin; "BEGIN"
0x18008b180  mov     rdx, rbp
0x18008b183  mov     rcx, rdi
0x18008b186  call    execSql
0x18008b18b  mov     ebx, eax
0x18008b18d  test    eax, eax
0x18008b18f  jnz     loc_18008B37F
0x18008b195  mov     rax, r14
0x18008b198  mov     rcx, r13
0x18008b19b  neg     rax
0x18008b19e  sbb     edx, edx
0x18008b1a0  xor     r8d, r8d
0x18008b1a3  not     edx
0x18008b1a5  and     edx, 2
0x18008b1a8  call    sqlite3BtreeBeginTrans
0x18008b1ad  mov     ebx, eax
0x18008b1af  test    eax, eax
0x18008b1b1  jnz     loc_18008B37F
0x18008b1b7  mov     rax, [r13+8]
0x18008b1bb  mov     rcx, [rax]
0x18008b1be  cmp     byte ptr [rcx+9], 5
0x18008b1c2  jnz     short loc_18008B1CD
0x18008b1c4  test    r14, r14
0x18008b1c7  jnz     short loc_18008B1CD
0x18008b1c9  mov     [rdi+74h], r14d
0x18008b1cd  mov     rdx, [r13+8]
0x18008b1d1  xor     r9d, r9d
0x18008b1d4  mov     ebx, dword ptr [rsp+0A8h+var_80]
0x18008b1d8  mov     rcx, r15
0x18008b1db  mov     r8d, ebx
0x18008b1de  mov     edx, [rdx+34h]
0x18008b1e1  call    sqlite3BtreeSetPageSize
0x18008b1e6  test    eax, eax
0x18008b1e8  jnz     loc_18008B37A
0x18008b1ee  cmp     [rsp+0A8h+var_84], eax
0x18008b1f2  jnz     short loc_18008B20D
0x18008b1f4  mov     edx, [rdi+74h]
0x18008b1f7  xor     r9d, r9d
0x18008b1fa  mov     r8d, ebx
0x18008b1fd  mov     rcx, r15
0x18008b200  call    sqlite3BtreeSetPageSize
0x18008b205  test    eax, eax
0x18008b207  jnz     loc_18008B37A
0x18008b20d  cmp     byte ptr [rdi+67h], 0
0x18008b211  jnz     loc_18008B37A
0x18008b217  movsx   eax, byte ptr [rdi+6Ah]
0x18008b21b  test    al, al
0x18008b21d  jns     short loc_18008B227
0x18008b21f  mov     rcx, r13
0x18008b222  call    sqlite3BtreeGetAutoVacuum
0x18008b227  mov     edx, eax
0x18008b229  mov     rcx, r15
0x18008b22c  call    sqlite3BtreeSetAutoVacuum
0x18008b231  mov     eax, [rsp+0A8h+var_88]
0x18008b235  lea     r8, aSelectSqlFromW_0; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x18008b23c  mov     r9, [rsp+0A8h+var_78]
0x18008b241  mov     rdx, rbp
0x18008b244  mov     rcx, rdi
0x18008b247  mov     [rdi+0C4h], al
0x18008b24d  call    execSqlF
0x18008b252  mov     ebx, eax
0x18008b254  test    eax, eax
0x18008b256  jnz     loc_18008B37F
0x18008b25c  mov     r9, [rsp+0A8h+var_78]
0x18008b261  lea     r8, aSelectSqlFromW; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x18008b268  mov     rdx, rbp
0x18008b26b  mov     rcx, rdi
0x18008b26e  call    execSqlF
0x18008b273  mov     ebx, eax
0x18008b275  test    eax, eax
0x18008b277  jnz     loc_18008B37F
0x18008b27d  mov     r9, [rsp+0A8h+var_78]
0x18008b282  lea     r8, aSelectInsertIn; "SELECT'INSERT INTO vacuum_db.'||quote(n"...
0x18008b289  mov     rdx, rbp
0x18008b28c  mov     [rdi+0C4h], al
0x18008b292  mov     rcx, rdi
0x18008b295  call    execSqlF
0x18008b29a  and     dword ptr [rdi+2Ch], 0FFFFFFFBh
0x18008b29e  mov     ebx, eax
0x18008b2a0  test    eax, eax
0x18008b2a2  jnz     loc_18008B37F
0x18008b2a8  mov     r9, [rsp+0A8h+var_78]
0x18008b2ad  lea     r8, aInsertIntoVacu; "INSERT INTO vacuum_db.sqlite_schema SEL"...
0x18008b2b4  mov     rdx, rbp
0x18008b2b7  mov     rcx, rdi
0x18008b2ba  call    execSqlF
0x18008b2bf  mov     ebx, eax
0x18008b2c1  test    eax, eax
0x18008b2c3  jnz     loc_18008B37F
0x18008b2c9  mov     [rsp+0A8h+var_88], eax
0x18008b2cd  xor     ebp, ebp
0x18008b2cf  lea     rax, cs:180000000h
0x18008b2d6  mov     rcx, r13
0x18008b2d9  movzx   edx, byte ptr [rbp+rax+0FB340h]
0x18008b2e1  lea     r8, [rsp+0A8h+var_88]
0x18008b2e6  call    sqlite3BtreeGetMeta
0x18008b2eb  lea     rax, cs:180000000h
0x18008b2f2  mov     rcx, r15
0x18008b2f5  movzx   r8d, byte ptr [rbp+rax+0FB341h]
0x18008b2fe  add     r8d, [rsp+0A8h+var_88]
0x18008b303  movzx   edx, byte ptr [rbp+rax+0FB340h]
0x18008b30b  call    sqlite3BtreeUpdateMeta
0x18008b310  mov     ebx, eax
0x18008b312  test    eax, eax
0x18008b314  jnz     short loc_18008B37F
0x18008b316  add     ebp, 2
0x18008b319  cmp     ebp, 0Ah
0x18008b31c  jl      short loc_18008B2CF
0x18008b31e  test    r14, r14
0x18008b321  jnz     short loc_18008B334
0x18008b323  mov     rdx, r15
0x18008b326  mov     rcx, r13
0x18008b329  call    sqlite3BtreeCopyFile
0x18008b32e  mov     ebx, eax
0x18008b330  test    eax, eax
0x18008b332  jnz     short loc_18008B37F
0x18008b334  mov     rcx, r15
0x18008b337  call    sqlite3BtreeCommit
0x18008b33c  mov     ebx, eax
0x18008b33e  test    eax, eax
0x18008b340  jnz     short loc_18008B37F
0x18008b342  test    r14, r14
0x18008b345  jnz     short loc_18008B37F
0x18008b347  mov     rcx, r15
0x18008b34a  call    sqlite3BtreeGetAutoVacuum
0x18008b34f  mov     edx, eax
0x18008b351  mov     rcx, r13
0x18008b354  call    sqlite3BtreeSetAutoVacuum
0x18008b359  mov     rcx, r15
0x18008b35c  call    sqlite3BtreeGetRequestedReserve
0x18008b361  mov     rdx, [r15+8]
0x18008b365  mov     r9d, esi
0x18008b368  mov     r8d, eax
0x18008b36b  mov     rcx, r13
0x18008b36e  mov     edx, [rdx+34h]
0x18008b371  call    sqlite3BtreeSetPageSize
0x18008b376  mov     ebx, eax
0x18008b378  jmp     short loc_18008B37F
0x18008b37a  mov     ebx, 7
0x18008b37f  mov     eax, [rsp+0A8h+var_70]
0x18008b383  xor     r14d, r14d
0x18008b386  mov     [rdi+2Ch], eax
0x18008b389  mov     r9d, esi
  ... truncated ...
```

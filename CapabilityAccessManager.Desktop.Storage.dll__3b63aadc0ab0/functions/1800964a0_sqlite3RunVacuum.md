# sqlite3RunVacuum

- ea: `0x1800964a0`
- end: `0x180096ccd`
- name: `sqlite3RunVacuum`
- size: `2093`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800a4310`

## callees

- `0x180005980`
- `0x180029fd0`
- `0x18002b330`
- `0x180036040`
- `0x180036220`
- `0x18004dba0`
- `0x180052750`
- `0x180067750`
- `0x180067910`
- `0x180067b70`
- `0x1800684f0`
- `0x1800685e0`
- `0x18006a6e0`
- `0x18006a780`
- `0x18006a830`
- `0x18006a920`
- `0x18006a990`
- `0x18006b4f0`
- `0x180071400`
- `0x1800950a0`
- `0x1800964a0`
- `0x1800c1b30`
- `0x1800c3e10`
- `0x18010d010`

## string_xrefs

- `0x180096895`: `output file already exists`

## pseudocode

```c
__int64 __fastcall sqlite3RunVacuum(char **a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v5; // rdi
  char *v8; // rax
  char *v9; // rdi
  char *v10; // rcx
  __int64 result; // rax
  char *v12; // rax
  int v13; // ebp
  __int16 v14; // cx
  char *v15; // rax
  char *v16; // rdi
  char *v17; // rcx
  __int64 v18; // rdx
  const char *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r12
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // rax
  __int64 v28; // r13
  unsigned int v29; // eax
  unsigned int updated; // esi
  __int64 v31; // r13
  __int64 v32; // rcx
  char *v33; // rax
  char *v34; // rbp
  char *v35; // rcx
  __int64 v36; // rax
  unsigned int RequestedReserve; // ebp
  unsigned int v38; // eax
  __int64 v39; // rdx
  char v40; // al
  unsigned int v41; // eax
  unsigned int AutoVacuum; // eax
  __int64 v43; // rbp
  __int64 v44; // r9
  unsigned int v45; // eax
  __int64 v46; // rbp
  char v47; // r8
  int v48; // esi
  _QWORD *v49; // r14
  __int64 v50; // rdx
  __int64 *v51; // rax
  __int64 v52; // rcx
  int v53; // esi
  unsigned int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // rdi
  __int64 v58; // [rsp+20h] [rbp-68h]
  int v59; // [rsp+20h] [rbp-68h]
  char v60; // [rsp+24h] [rbp-64h]
  int v61; // [rsp+28h] [rbp-60h]
  __int64 v62; // [rsp+30h] [rbp-58h] BYREF
  __int64 v63; // [rsp+38h] [rbp-50h]
  __int64 v64; // [rsp+40h] [rbp-48h]
  __int64 v65; // [rsp+48h] [rbp-40h]
  __int64 v66; // [rsp+50h] [rbp-38h]
  __int64 v67; // [rsp+58h] [rbp-30h]
  char v68; // [rsp+98h] [rbp+10h]

  v5 = a3;
  if ( !*(_BYTE *)(a2 + 101) )
  {
    v8 = (char *)sqlite3DbMallocRawNN(a2, 40);
    v9 = v8;
    if ( v8 )
      strcpy(v8, "cannot VACUUM from within a transaction");
    v10 = *a1;
    if ( *a1 )
    {
      if ( (unsigned __int64)v10 < *(_QWORD *)(a2 + 496) )
      {
        if ( (unsigned __int64)v10 >= *(_QWORD *)(a2 + 480) )
        {
LABEL_7:
          *(_QWORD *)v10 = *(_QWORD *)(a2 + 472);
          result = 1;
          *(_QWORD *)(a2 + 472) = v10;
          *a1 = v9;
          return result;
        }
LABEL_8:
        if ( (unsigned __int64)v10 >= *(_QWORD *)(a2 + 488) )
        {
          *(_QWORD *)v10 = *(_QWORD *)(a2 + 456);
          result = 1;
          *(_QWORD *)(a2 + 456) = v10;
          *a1 = v9;
          return result;
        }
        goto LABEL_10;
      }
      goto LABEL_10;
    }
    goto LABEL_13;
  }
  if ( *(int *)(a2 + 216) > 1 )
  {
    v12 = (char *)sqlite3DbMallocRawNN(a2, 43);
    v9 = v12;
    if ( v12 )
      strcpy(v12, "cannot VACUUM - SQL statements in progress");
    v10 = *a1;
    if ( *a1 )
    {
      if ( (unsigned __int64)v10 < *(_QWORD *)(a2 + 496) )
      {
        if ( (unsigned __int64)v10 >= *(_QWORD *)(a2 + 480) )
          goto LABEL_7;
        goto LABEL_8;
      }
LABEL_10:
      if ( *(_QWORD *)(a2 + 776) )
      {
        measureAllocationSize(a2, v10);
        result = 1;
        *a1 = v9;
        return result;
      }
      sqlite3_free(v10);
    }
LABEL_13:
    *a1 = v9;
    return 1;
  }
  v13 = *(_DWORD *)(a2 + 76);
  if ( !a4 )
  {
    v19 = byte_180122168;
    goto LABEL_43;
  }
  v14 = *(_WORD *)(a4 + 20);
  if ( *((_BYTE *)qword_18010E020 + (v14 & 0x3F)) == 3 )
  {
    v18 = 514;
    if ( (v14 & 0x202) == 0x202 && *(_BYTE *)(a4 + 22) == 1 )
    {
      v19 = *(const char **)(a4 + 8);
      *(_DWORD *)(a2 + 76) &= ~1u;
      *(_DWORD *)(a2 + 76) |= 6u;
    }
    else
    {
      if ( (v14 & 1) != 0 )
      {
        *(_DWORD *)(a2 + 76) &= ~1u;
        v19 = 0;
      }
      else
      {
        LOBYTE(v18) = 1;
        v20 = valueToText(a4, v18);
        *(_DWORD *)(a2 + 76) &= ~1u;
        v19 = (const char *)v20;
      }
      *(_DWORD *)(a2 + 76) |= 6u;
    }
LABEL_43:
    v21 = *(_QWORD *)(a2 + 48);
    v22 = *(_QWORD *)(a2 + 120);
    v61 = *(_DWORD *)(a2 + 44);
    *(_DWORD *)(a2 + 44) = v61 | 6;
    v65 = v21;
    *(_QWORD *)(a2 + 48) = v21 & 0xFFFFFFFEEFFFADFEuLL | 0x201;
    v23 = *(_QWORD *)(a2 + 32);
    v24 = 32 * v5;
    v66 = v22;
    v67 = *(_QWORD *)(a2 + 128);
    LOBYTE(v22) = *(_BYTE *)(a2 + 110);
    *(_BYTE *)(a2 + 110) = 0;
    v25 = *(_QWORD *)(32 * v5 + v23);
    v26 = *(_QWORD *)(32 * v5 + v23 + 8);
    v64 = v25;
    v63 = 0;
    v68 = v22;
    v27 = *(_QWORD *)(v26 + 8);
    if ( *(_BYTE *)(*(_QWORD *)v27 + 16LL) || (LODWORD(v58) = 0, *(_BYTE *)(*(_QWORD *)v27 + 20LL)) )
      LODWORD(v58) = 1;
    v28 = *(int *)(a2 + 40);
    HIDWORD(v58) = *(_DWORD *)(a2 + 40);
    v29 = execSqlF(a2, a1, "ATTACH %Q AS vacuum_db", v19, v58);
    *(_DWORD *)(a2 + 76) = v13;
    updated = v29;
    if ( v29 )
      goto LABEL_111;
    updated = 1;
    v63 = *(_QWORD *)(a2 + 32) + 32 * v28;
    v31 = *(_QWORD *)(v63 + 8);
    if ( a4 )
    {
      v32 = *(_QWORD *)(**(_QWORD **)(v31 + 8) + 72LL);
      v62 = 0;
      if ( *(_QWORD *)v32
        && ((*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, &v62) || v62 > 0) )
      {
        v33 = (char *)sqlite3DbMallocRawNN(a2, 27);
        v34 = v33;
        if ( v33 )
          strcpy(v33, "output file already exists");
        v35 = *a1;
        if ( *a1 )
        {
          if ( (unsigned __int64)v35 < *(_QWORD *)(a2 + 496) )
          {
            if ( (unsigned __int64)v35 >= *(_QWORD *)(a2 + 480) )
            {
              *(_QWORD *)v35 = *(_QWORD *)(a2 + 472);
              *(_QWORD *)(a2 + 472) = v35;
              *a1 = v33;
LABEL_111:
              *(_DWORD *)(a2 + 44) = v61;
              *(_QWORD *)(a2 + 48) = v65;
              *(_QWORD *)(a2 + 120) = v66;
              *(_QWORD *)(a2 + 128) = v67;
              *(_BYTE *)(a2 + 110) = v68;
              *(_BYTE *)(a2 + 196) = 0;
              sqlite3BtreeSetPageSize(v26, 0xFFFFFFFFLL, 0, 1);
              v57 = v63;
              *(_BYTE *)(a2 + 101) = 1;
              if ( v57 )
              {
                sqlite3BtreeClose(*(_QWORD *)(v57 + 8));
                *(_QWORD *)(v57 + 8) = 0;
                *(_QWORD *)(v57 + 24) = 0;
              }
              sqlite3ResetAllSchemasOfConnection(a2);
              return updated;
            }
            if ( (unsigned __int64)v35 >= *(_QWORD *)(a2 + 488) )
            {
              *(_QWORD *)v35 = *(_QWORD *)(a2 + 456);
              *(_QWORD *)(a2 + 456) = v35;
              *a1 = v33;
              goto LABEL_111;
            }
          }
          if ( *(_QWORD *)(a2 + 776) )
          {
            measureAllocationSize(a2, *a1);
            *a1 = v34;
            goto LABEL_111;
          }
          sqlite3_free(v35);
        }
        *a1 = v34;
        goto LABEL_111;
      }
      v36 = *(_QWORD *)(a2 + 32);
      *(_DWORD *)(a2 + 44) |= 8u;
      updated = *(_DWORD *)(a2 + 48) & 0x38 | *(unsigned __int8 *)(v24 + v36 + 16);
    }
    RequestedReserve = sqlite3BtreeGetRequestedReserve(v26);
    sqlite3BtreeSetCacheSize(v31, *(unsigned int *)(*(_QWORD *)(v24 + *(_QWORD *)(a2 + 32) + 24) + 116LL));
    v38 = sqlite3BtreeSetSpillSize(v26, 0);
    sqlite3BtreeSetSpillSize(v31, v38);
    sqlite3BtreeSetPagerFlags(v31, updated | 0x20);
    updated = execSql(a2, a1, "BEGIN");
    if ( updated )
      goto LABEL_111;
    v39 = 0;
    if ( !a4 )
      v39 = 2;
    if ( *(_BYTE *)(v26 + 17) == (_BYTE)updated )
    {
      v40 = *(_BYTE *)(v26 + 16);
      if ( v40 )
      {
        if ( v40 != 1 )
        {
          if ( a4 )
            goto LABEL_74;
          v50 = *(unsigned int *)(*(_QWORD *)v26 + 752LL);
          v51 = *(__int64 **)(v26 + 8);
          v52 = *v51;
          if ( (int)v50 <= *(_DWORD *)(*v51 + 128) || !*(_BYTE *)(v52 + 10) )
          {
            updated = 0;
LABEL_73:
            if ( updated )
              goto LABEL_111;
LABEL_74:
            if ( *(_BYTE *)(**(_QWORD **)(v26 + 8) + 9LL) == 5 && !a4 )
              *(_DWORD *)(a2 + 116) = 0;
            if ( (unsigned int)sqlite3BtreeSetPageSize(
                                 v31,
                                 *(unsigned int *)(*(_QWORD *)(v26 + 8) + 52LL),
                                 RequestedReserve,
                                 0)
              || !v59 && (unsigned int)sqlite3BtreeSetPageSize(v31, *(unsigned int *)(a2 + 116), RequestedReserve, 0)
              || *(_BYTE *)(a2 + 103) )
            {
              updated = 7;
            }
            else
            {
              AutoVacuum = *(char *)(a2 + 106);
              if ( *(char *)(a2 + 106) < 0 )
                AutoVacuum = sqlite3BtreeGetAutoVacuum(v26);
              sqlite3BtreeSetAutoVacuum(v31, AutoVacuum);
              v43 = v64;
              v44 = v64;
              *(_BYTE *)(a2 + 196) = v60;
              updated = execSqlF(
                          a2,
                          a1,
                          "SELECT sql FROM \"%w\".sqlite_schema WHERE type='table'AND name<>'sqlite_sequence' AND coalesce(rootpage,1)>0",
                          v44);
              if ( !updated )
              {
                updated = execSqlF(a2, a1, "SELECT sql FROM \"%w\".sqlite_schema WHERE type='index'", v43);
                if ( !updated )
                {
                  *(_BYTE *)(a2 + 196) = 0;
                  v45 = execSqlF(
                          a2,
                          a1,
                          "SELECT'INSERT INTO vacuum_db.'||quote(name)||' SELECT*FROM\"%w\".'||quote(name)FROM vacuum_db."
                          "sqlite_schema WHERE type='table'AND coalesce(rootpage,1)>0",
                          v43);
                  *(_DWORD *)(a2 + 44) &= ~4u;
                  updated = v45;
                  if ( !v45 )
                  {
                    updated = execSqlF(
                                a2,
                                a1,
                                "INSERT INTO vacuum_db.sqlite_schema SELECT*FROM \"%w\".sqlite_schema WHERE type IN('view"
                                "','trigger') OR(type='table'AND rootpage=0)",
                                v43);
                    if ( !updated )
                    {
                      v46 = 0;
                      while ( 1 )
                      {
                        v47 = *(_BYTE *)(v26 + 17);
                        v48 = *((unsigned __int8 *)qword_1801140A8 + v46);
                        v49 = *(_QWORD **)(v26 + 8);
                        if ( v47 )
                        {
                          ++*(_DWORD *)(v26 + 20);
                          if ( !*(_BYTE *)(v26 + 18) )
                          {
                            btreeLockCarefully(v26);
                            v47 = *(_BYTE *)(v26 + 17);
                          }
                        }
                        else
                        {
                          v47 = 0;
                        }
                        if ( v48 == 15 )
                          v53 = *(_DWORD *)(v26 + 28) + *(_DWORD *)(*v49 + 132LL);
                        else
                          v53 = _byteswap_ulong(*(_DWORD *)((unsigned int)(4 * v48 + 36) + *(_QWORD *)(v49[3] + 80LL)));
                        if ( v47 )
                        {
                          if ( (*(_DWORD *)(v26 + 20))-- == 1 )
                            unlockBtreeMutex(v26);
                        }
                        updated = sqlite3BtreeUpdateMeta(
                                    v31,
                                    *((unsigned __int8 *)qword_1801140A8 + v46),
                                    v53 + (unsigned int)*((unsigned __int8 *)qword_1801140A8 + v46 + 1));
                        if ( updated )
                          break;
                        v46 = (unsigned int)(v46 + 2);
                        if ( (int)v46 >= 10 )
                        {
                          if ( a4 || (updated = sqlite3BtreeCopyFile(v26, v31)) == 0 )
                          {
                            updated = sqlite3BtreeCommit(v31);
                            if ( !updated && !a4 )
                            {
                              v55 = sqlite3BtreeGetAutoVacuum(v31);
                              sqlite3BtreeSetAutoVacuum(v26, v55);
                              v56 = sqlite3BtreeGetRequestedReserve(v31);
                              updated = sqlite3BtreeSetPageSize(
                                          v26,
                                          *(unsigned int *)(*(_QWORD *)(v31 + 8) + 52LL),
                                          v56,
                                          1);
                            }
                          }
                          goto LABEL_111;
                        }
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_111;
          }
          v41 = pagerOpenSavepoint(v52, v50);
LABEL_72:
          updated = v41;
          goto LABEL_73;
        }
        if ( a4 )
          goto LABEL_74;
      }
    }
    v41 = btreeBeginTrans(v26, v39, 0);
    goto LABEL_72;
  }
  v15 = (char *)sqlite3DbMallocRawNN(a2, 18);
  v16 = v15;
  if ( v15 )
    strcpy(v15, "non-text filename");
  v17 = *a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)v17 < *(_QWORD *)(a2 + 496) )
    {
      if ( (unsigned __int64)v17 >= *(_QWORD *)(a2 + 480) )
      {
        *(_QWORD *)v17 = *(_QWORD *)(a2 + 472);
        result = 1;
        *(_QWORD *)(a2 + 472) = v17;
        *a1 = v16;
        return result;
      }
      if ( (unsigned __int64)v17 >= *(_QWORD *)(a2 + 488) )
      {
        *(_QWORD *)v17 = *(_QWORD *)(a2 + 456);
        result = 1;
        *(_QWORD *)(a2 + 456) = v17;
        *a1 = v16;
        return result;
      }
    }
    if ( *(_QWORD *)(a2 + 776) )
    {
      measureAllocationSize(a2, *a1);
      result = 1;
      *a1 = v16;
      return result;
    }
    sqlite3_free(v17);
  }
  *a1 = v16;
  return 1;
}

```

## disassembly

```asm
0x1800964a0  push    rbx
0x1800964a2  push    rdi
0x1800964a3  push    r14
0x1800964a5  push    r15
0x1800964a7  sub     rsp, 68h
0x1800964ab  cmp     byte ptr [rdx+65h], 0
0x1800964af  mov     r15, r9
0x1800964b2  movsxd  rdi, r8d
0x1800964b5  mov     rbx, rdx
0x1800964b8  mov     r14, rcx
0x1800964bb  jnz     loc_1800965A7
0x1800964c1  mov     edx, 28h ; '('
0x1800964c6  mov     rcx, rbx
0x1800964c9  call    sqlite3DbMallocRawNN
0x1800964ce  mov     rdi, rax
0x1800964d1  test    rax, rax
0x1800964d4  jz      short loc_1800964F8
0x1800964d6  movups  xmm0, xmmword ptr cs:aCannotVacuumFr; "cannot VACUUM from within a transaction"
0x1800964dd  movups  xmmword ptr [rax], xmm0
0x1800964e0  movups  xmm1, xmmword ptr cs:aCannotVacuumFr+10h; "om within a transaction"
0x1800964e7  movups  xmmword ptr [rax+10h], xmm1
0x1800964eb  movsd   xmm0, qword ptr cs:aCannotVacuumFr+20h; "saction"
0x1800964f3  movsd   qword ptr [rax+20h], xmm0
0x1800964f8  mov     rcx, [r14]
0x1800964fb  test    rcx, rcx
0x1800964fe  jz      loc_180096594
0x180096504  cmp     rcx, [rbx+1F0h]
0x18009650b  jnb     short loc_180096567
0x18009650d  cmp     rcx, [rbx+1E0h]
0x180096514  jb      short loc_18009653A
0x180096516  mov     rax, [rbx+1D8h]
0x18009651d  mov     [rcx], rax
0x180096520  mov     eax, 1
0x180096525  mov     [rbx+1D8h], rcx
0x18009652c  mov     [r14], rdi
0x18009652f  add     rsp, 68h
0x180096533  pop     r15
0x180096535  pop     r14
0x180096537  pop     rdi
0x180096538  pop     rbx
0x180096539  retn
0x18009653a  cmp     rcx, [rbx+1E8h]
0x180096541  jb      short loc_180096567
0x180096543  mov     rax, [rbx+1C8h]
0x18009654a  mov     [rcx], rax
0x18009654d  mov     eax, 1
0x180096552  mov     [rbx+1C8h], rcx
0x180096559  mov     [r14], rdi
0x18009655c  add     rsp, 68h
0x180096560  pop     r15
0x180096562  pop     r14
0x180096564  pop     rdi
0x180096565  pop     rbx
0x180096566  retn
0x180096567  cmp     qword ptr [rbx+308h], 0
0x18009656f  jz      short loc_18009658F
0x180096571  mov     rdx, rcx
0x180096574  mov     rcx, rbx
0x180096577  call    measureAllocationSize
0x18009657c  mov     eax, 1
0x180096581  mov     [r14], rdi
0x180096584  add     rsp, 68h
0x180096588  pop     r15
0x18009658a  pop     r14
0x18009658c  pop     rdi
0x18009658d  pop     rbx
0x18009658e  retn
0x18009658f  call    sqlite3_free
0x180096594  mov     [r14], rdi
0x180096597  mov     eax, 1
0x18009659c  add     rsp, 68h
0x1800965a0  pop     r15
0x1800965a2  pop     r14
0x1800965a4  pop     rdi
0x1800965a5  pop     rbx
0x1800965a6  retn
0x1800965a7  cmp     dword ptr [rdx+0D8h], 1
0x1800965ae  jle     short loc_18009660C
0x1800965b0  mov     edx, 2Bh ; '+'
0x1800965b5  mov     rcx, rbx
0x1800965b8  call    sqlite3DbMallocRawNN
0x1800965bd  mov     rdi, rax
0x1800965c0  test    rax, rax
0x1800965c3  jz      short loc_1800965E5
0x1800965c5  movups  xmm0, xmmword ptr cs:aCannotVacuumSq; "cannot VACUUM - SQL statements in progr"...
0x1800965cc  movups  xmmword ptr [rax], xmm0
0x1800965cf  movups  xmm1, xmmword ptr cs:aCannotVacuumSq+10h; "SQL statements in progress"
0x1800965d6  movups  xmmword ptr [rax+10h], xmm1
0x1800965da  movups  xmm0, xmmword ptr cs:aCannotVacuumSq+1Bh; "nts in progress"
0x1800965e1  movups  xmmword ptr [rax+1Bh], xmm0
0x1800965e5  mov     rcx, [r14]
0x1800965e8  test    rcx, rcx
0x1800965eb  jz      short loc_180096594
0x1800965ed  cmp     rcx, [rbx+1F0h]
0x1800965f4  jnb     loc_180096567
0x1800965fa  cmp     rcx, [rbx+1E0h]
0x180096601  jnb     loc_180096516
0x180096607  jmp     loc_18009653A
0x18009660c  mov     [rsp+88h+arg_0], rbp
0x180096614  mov     ebp, [rdx+4Ch]
0x180096617  lea     rdx, cs:180000000h
0x18009661e  test    r15, r15
0x180096621  jz      loc_18009674A
0x180096627  movzx   ecx, word ptr [r9+14h]
0x18009662c  mov     eax, ecx
0x18009662e  and     eax, 3Fh
0x180096631  cmp     byte ptr [rax+rdx+10E020h], 3
0x180096639  jz      loc_1800966FC
0x18009663f  mov     edx, 12h
0x180096644  mov     rcx, rbx
0x180096647  call    sqlite3DbMallocRawNN
0x18009664c  mov     rdi, rax
0x18009664f  test    rax, rax
0x180096652  jz      short loc_180096669
0x180096654  movups  xmm0, xmmword ptr cs:aNonTextFilenam; "non-text filename"
0x18009665b  movups  xmmword ptr [rax], xmm0
0x18009665e  movzx   ecx, word ptr cs:aNonTextFilenam+10h; "e"
0x180096665  mov     [rax+10h], cx
0x180096669  mov     rcx, [r14]
0x18009666c  test    rcx, rcx
0x18009666f  jz      short loc_1800966EF
0x180096671  cmp     rcx, [rbx+1F0h]
0x180096678  jnb     short loc_1800966C8
0x18009667a  cmp     rcx, [rbx+1E0h]
0x180096681  jb      short loc_1800966A1
0x180096683  mov     rax, [rbx+1D8h]
0x18009668a  mov     [rcx], rax
0x18009668d  mov     eax, 1
0x180096692  mov     [rbx+1D8h], rcx
0x180096699  mov     [r14], rdi
0x18009669c  jmp     loc_180096CBA
0x1800966a1  cmp     rcx, [rbx+1E8h]
0x1800966a8  jb      short loc_1800966C8
0x1800966aa  mov     rax, [rbx+1C8h]
0x1800966b1  mov     [rcx], rax
0x1800966b4  mov     eax, 1
0x1800966b9  mov     [rbx+1C8h], rcx
0x1800966c0  mov     [r14], rdi
0x1800966c3  jmp     loc_180096CBA
0x1800966c8  cmp     qword ptr [rbx+308h], 0
0x1800966d0  jz      short loc_1800966EA
0x1800966d2  mov     rdx, rcx
0x1800966d5  mov     rcx, rbx
0x1800966d8  call    measureAllocationSize
0x1800966dd  mov     eax, 1
0x1800966e2  mov     [r14], rdi
0x1800966e5  jmp     loc_180096CBA
0x1800966ea  call    sqlite3_free
0x1800966ef  mov     [r14], rdi
0x1800966f2  mov     eax, 1
0x1800966f7  jmp     loc_180096CBA
0x1800966fc  mov     edx, 202h
0x180096701  movzx   eax, cx
0x180096704  and     ax, dx
0x180096707  cmp     ax, dx
0x18009670a  jnz     short loc_180096721
0x18009670c  cmp     byte ptr [r9+16h], 1
0x180096711  jnz     short loc_180096721
0x180096713  mov     r9, [r9+8]
0x180096717  and     dword ptr [rbx+4Ch], 0FFFFFFFEh
0x18009671b  or      dword ptr [rbx+4Ch], 6
0x18009671f  jmp     short loc_180096751
0x180096721  test    cl, 1
0x180096724  jz      short loc_180096733
0x180096726  and     dword ptr [rbx+4Ch], 0FFFFFFFEh
0x18009672a  xor     r9d, r9d
0x18009672d  or      dword ptr [rbx+4Ch], 6
0x180096731  jmp     short loc_180096751
0x180096733  mov     dl, 1
0x180096735  mov     rcx, r15
0x180096738  call    valueToText
0x18009673d  and     dword ptr [rbx+4Ch], 0FFFFFFFEh
0x180096741  mov     r9, rax
0x180096744  or      dword ptr [rbx+4Ch], 6
0x180096748  jmp     short loc_180096751
0x18009674a  lea     r9, byte_180122168
0x180096751  mov     eax, [rbx+2Ch]
0x180096754  mov     rcx, [rbx+30h]
0x180096758  mov     rdx, [rbx+78h]
0x18009675c  mov     [rsp+88h+var_60], eax
0x180096760  or      eax, 6
0x180096763  mov     [rbx+2Ch], eax
0x180096766  mov     rax, rcx
0x180096769  mov     [rsp+88h+var_40], rcx
0x18009676e  mov     rcx, 0FFFFFFFEEFFFAFFFh
0x180096778  and     rax, rcx
0x18009677b  mov     [rsp+88h+arg_10], rsi
0x180096783  or      rax, 201h
0x180096789  mov     [rsp+88h+arg_18], r12
0x180096791  mov     [rbx+30h], rax
0x180096795  mov     r12, rdi
0x180096798  mov     rax, [rbx+20h]
0x18009679c  shl     r12, 5
0x1800967a0  mov     [rsp+88h+var_38], rdx
0x1800967a5  mov     rdx, [rbx+80h]
0x1800967ac  mov     [rsp+88h+var_28], r13
0x1800967b1  xor     r13d, r13d
0x1800967b4  mov     [rsp+88h+var_30], rdx
0x1800967b9  movzx   edx, byte ptr [rbx+6Eh]
0x1800967bd  mov     [rbx+6Eh], r13b
0x1800967c1  mov     rcx, [r12+rax]
0x1800967c5  mov     rdi, [r12+rax+8]
0x1800967ca  mov     [rsp+88h+var_48], rcx
0x1800967cf  mov     [rsp+88h+var_50], r13
0x1800967d4  mov     [rsp+88h+arg_8], dl
0x1800967db  mov     rax, [rdi+8]
0x1800967df  mov     rcx, [rax]
0x1800967e2  cmp     [rcx+10h], r13b
0x1800967e6  jnz     short loc_1800967F3
0x1800967e8  mov     [rsp+88h+var_68], r13d
0x1800967ed  cmp     [rcx+14h], r13b
0x1800967f1  jz      short loc_1800967FB
0x1800967f3  mov     [rsp+88h+var_68], 1
0x1800967fb  movsxd  r13, dword ptr [rbx+28h]
0x1800967ff  lea     r8, aAttachQAsVacuu; "ATTACH %Q AS vacuum_db"
0x180096806  mov     rdx, r14
0x180096809  mov     [rsp+88h+var_64], r13d
0x18009680e  mov     rcx, rbx
0x180096811  call    execSqlF
0x180096816  mov     [rbx+4Ch], ebp
0x180096819  mov     esi, eax
0x18009681b  test    eax, eax
0x18009681d  jnz     loc_180096C27
0x180096823  shl     r13, 5
0x180096827  mov     esi, 1
0x18009682c  add     r13, [rbx+20h]
0x180096830  mov     [rsp+88h+var_50], r13
0x180096835  mov     r13, [r13+8]
0x180096839  test    r15, r15
0x18009683c  jz      loc_18009693F
0x180096842  mov     rax, [r13+8]
0x180096846  mov     rcx, [rax]
0x180096849  mov     rcx, [rcx+48h]
0x18009684d  mov     [rsp+88h+var_58], 0
0x180096856  mov     rax, [rcx]
0x180096859  test    rax, rax
0x18009685c  jz      loc_180096929
0x180096862  mov     rax, [rax+30h]
0x180096866  lea     rdx, [rsp+88h+var_58]
0x18009686b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096870  test    eax, eax
0x180096872  jnz     short loc_180096880
0x180096874  cmp     [rsp+88h+var_58], 0
0x18009687a  jle     loc_180096929
0x180096880  mov     edx, 1Bh
0x180096885  mov     rcx, rbx
0x180096888  call    sqlite3DbMallocRawNN
0x18009688d  mov     rbp, rax
0x180096890  test    rax, rax
0x180096893  jz      short loc_1800968AA
0x180096895  movups  xmm0, xmmword ptr cs:aOutputFileAlre; "output file already exists"
0x18009689c  movups  xmmword ptr [rax], xmm0
0x18009689f  movups  xmm1, xmmword ptr cs:aOutputFileAlre+0Bh; " already exists"
0x1800968a6  movups  xmmword ptr [rax+0Bh], xmm1
0x1800968aa  mov     rcx, [r14]
0x1800968ad  test    rcx, rcx
0x1800968b0  jz      short loc_180096921
0x1800968b2  cmp     rcx, [rbx+1F0h]
0x1800968b9  jnb     short loc_1800968FF
0x1800968bb  cmp     rcx, [rbx+1E0h]
0x1800968c2  jb      short loc_1800968DD
0x1800968c4  mov     rax, [rbx+1D8h]
0x1800968cb  mov     [rcx], rax
0x1800968ce  mov     [rbx+1D8h], rcx
0x1800968d5  mov     [r14], rbp
0x1800968d8  jmp     loc_180096C27
0x1800968dd  cmp     rcx, [rbx+1E8h]
0x1800968e4  jb      short loc_1800968FF
0x1800968e6  mov     rax, [rbx+1C8h]
0x1800968ed  mov     [rcx], rax
0x1800968f0  mov     [rbx+1C8h], rcx
0x1800968f7  mov     [r14], rbp
0x1800968fa  jmp     loc_180096C27
0x1800968ff  cmp     qword ptr [rbx+308h], 0
0x180096907  jz      short loc_18009691C
0x180096909  mov     rdx, rcx
0x18009690c  mov     rcx, rbx
0x18009690f  call    measureAllocationSize
0x180096914  mov     [r14], rbp
0x180096917  jmp     loc_180096C27
0x18009691c  call    sqlite3_free
0x180096921  mov     [r14], rbp
0x180096924  jmp     loc_180096C27
0x180096929  mov     rax, [rbx+20h]
0x18009692d  or      dword ptr [rbx+2Ch], 8
0x180096931  movzx   esi, byte ptr [r12+rax+10h]
0x180096937  mov     eax, [rbx+30h]
0x18009693a  and     eax, 38h
0x18009693d  or      esi, eax
0x18009693f  mov     rcx, rdi
0x180096942  call    sqlite3BtreeGetRequestedReserve
0x180096947  mov     rcx, [rbx+20h]
0x18009694b  mov     ebp, eax
0x18009694d  mov     rdx, [r12+rcx+18h]
0x180096952  mov     rcx, r13
0x180096955  mov     edx, [rdx+74h]
0x180096958  call    sqlite3BtreeSetCacheSize
0x18009695d  xor     edx, edx
0x18009695f  mov     rcx, rdi
0x180096962  call    sqlite3BtreeSetSpillSize
  ... truncated ...
```

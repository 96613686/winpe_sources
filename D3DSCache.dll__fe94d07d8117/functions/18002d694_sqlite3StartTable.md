# sqlite3StartTable

- ea: `0x18002d694`
- end: `0x18002de00`
- name: `sqlite3StartTable`
- size: `1900`
- prototype: ``
- caller_count: `3`
- callee_count: `29`
- tags: ``

## callers

- `0x18001bc30`
- `0x18007d68c`
- `0x18008f8ec`

## callees

- `0x180007ac4`
- `0x18000b4bc`
- `0x180014464`
- `0x1800156f4`
- `0x180020d70`
- `0x18002817c`
- `0x1800283fc`
- `0x18002d694`
- `0x1800367a0`
- `0x1800369e4`
- `0x180037880`
- `0x180039494`
- `0x18003be78`
- `0x18003d480`
- `0x18003f5a8`
- `0x18003ff28`
- `0x180041574`
- `0x180041894`
- `0x180042bb0`
- `0x180042cd4`
- `0x180045374`
- `0x1800811ec`
- `0x1800817c0`
- `0x1800829d8`
- `0x180086810`
- `0x180088ee0`
- `0x180089934`
- `0x180097ea0`
- `0x1800a8010`

## string_xrefs

- `0x18002d6da`: `sqlite_temp_master`
- `0x18002d8d2`: `sqlite_temp_master`
- `0x18002d753`: `temporary table name must be unqualified`
- `0x18002da9d`: `%s %T already exists`
- `0x18002dae7`: `there is already an index named %s`

## pseudocode

```c
char __fastcall sqlite3StartTable(__int64 *a1, __int64 a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  __int64 v7; // rsi
  const char *v10; // r8
  __int64 v12; // rbx
  __int64 Vdbe; // rax
  unsigned int v14; // r14d
  const char *v15; // rdx
  __int64 v16; // rbp
  bool v17; // zf
  __int64 v18; // r15
  const char *v19; // r13
  const char *v20; // rcx
  _QWORD *v21; // r15
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // r9
  const char *v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // r15d
  __int64 v29; // rcx
  __int64 (__fastcall *v30)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64); // rax
  int v31; // eax
  int v32; // r15d
  __int64 v33; // r15
  __int64 Table; // rax
  __int64 v35; // rax
  _QWORD *v36; // rbx
  __int64 v37; // rbp
  int v38; // r13d
  int v39; // r15d
  int v40; // r12d
  int v41; // ecx
  unsigned int v42; // ebx
  int v43; // ecx
  __int64 v45; // [rsp+40h] [rbp-58h]
  __int64 v46; // [rsp+48h] [rbp-50h]
  int v47; // [rsp+A0h] [rbp+8h]

  v7 = *a1;
  v10 = "sqlite_master";
  v12 = a2;
  LOBYTE(Vdbe) = *(_BYTE *)(*a1 + 197);
  if ( (_BYTE)Vdbe && *(_DWORD *)(v7 + 192) == 1 )
  {
    v14 = *(unsigned __int8 *)(v7 + 196);
    v15 = "sqlite_temp_master";
    if ( v14 != 1 )
      v15 = "sqlite_master";
    Vdbe = sqlite3DbStrDup(v7, v15);
    v16 = Vdbe;
  }
  else
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      if ( (_BYTE)Vdbe )
      {
        LOBYTE(Vdbe) = sqlite3ErrorMsg(a1, "corrupt database", "sqlite_master");
        return Vdbe;
      }
      LODWORD(Vdbe) = sqlite3FindDb(v7, a2, "sqlite_master");
      v14 = Vdbe;
      if ( (int)Vdbe < 0 )
      {
        LOBYTE(Vdbe) = sqlite3ErrorMsg(a1, "unknown database %T", v12);
        return Vdbe;
      }
      v12 = a3;
    }
    else
    {
      v14 = *(unsigned __int8 *)(v7 + 196);
    }
    v17 = a4 == 0;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && v14 != 1 )
      {
        LOBYTE(Vdbe) = sqlite3ErrorMsg(a1, "temporary table name must be unqualified", v10);
        return Vdbe;
      }
      v17 = a4 == 0;
    }
    if ( !v17 )
      v14 = 1;
    if ( v12 )
    {
      v16 = sqlite3DbStrNDup(v7, *(_QWORD *)v12, *(unsigned int *)(v12 + 8));
      LOBYTE(Vdbe) = sqlite3Dequote(v16);
    }
    else
    {
      v16 = 0;
    }
    if ( *((_BYTE *)a1 + 308) >= 2u )
      LOBYTE(Vdbe) = sqlite3RenameTokenMap(a1, v16, v12);
  }
  *((_OWORD *)a1 + 17) = *(_OWORD *)v12;
  if ( !v16 )
    return Vdbe;
  v18 = *a1;
  v19 = "view";
  v20 = "view";
  if ( !a5 )
    v20 = "table";
  if ( (*(_DWORD *)(v18 + 48) & 0x10000001) != 1 && (*(_BYTE *)(v18 + 200) & 2) == 0 && byte_1800C6979 )
  {
    if ( *(_BYTE *)(v18 + 197) )
    {
      v21 = *(_QWORD **)(v18 + 208);
      if ( (unsigned int)sqlite3_stricmp(v20, *v21)
        || (unsigned int)sqlite3_stricmp(v16, v21[1])
        || (unsigned int)sqlite3_stricmp(v16, v21[2]) )
      {
        sqlite3ErrorMsg(a1, (const char *)&Src);
LABEL_105:
        *((_BYTE *)a1 + 29) = 1;
        LOBYTE(Vdbe) = sqlite3DbFree(v7, v16);
        return Vdbe;
      }
    }
    else if ( !*((_BYTE *)a1 + 30) && !(unsigned int)sqlite3_strnicmp(v16, "sqlite_", 7)
           || (unsigned int)sqlite3ReadOnlyShadowTables(v18) && (unsigned int)sqlite3ShadowTableName(v22, v16) )
    {
      sqlite3ErrorMsg(a1, "object name reserved for internal use: %s", v16);
      goto LABEL_105;
    }
  }
  v23 = 1;
  if ( *(_BYTE *)(v7 + 196) != 1 )
    v23 = a4;
  v45 = 32LL * v14;
  v47 = v23;
  v24 = *(_QWORD *)(v45 + *(_QWORD *)(v7 + 32));
  v25 = "sqlite_temp_master";
  v46 = v24;
  if ( v23 != 1 )
    v25 = "sqlite_master";
  v26 = *a1;
  if ( *(_QWORD *)(*a1 + 512) && !*(_BYTE *)(v26 + 197) && !*((_BYTE *)a1 + 308) )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *))(*a1 + 512))(*(_QWORD *)(v26 + 520), 18, v25);
    v28 = v27;
    if ( v27 == 1 )
    {
      sqlite3ErrorMsg(a1, "not authorized");
      *((_DWORD *)a1 + 6) = 23;
    }
    else if ( (v27 & 0xFFFFFFFD) != 0 )
    {
      v28 = 1;
      sqlite3ErrorMsg(a1, "authorizer malfunction");
      *((_DWORD *)a1 + 6) = 1;
    }
    if ( v28 )
      goto LABEL_105;
    v23 = v47;
    v24 = v46;
  }
  if ( !a6 )
  {
    v29 = *a1;
    v30 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))(*a1 + 512);
    if ( v30 )
    {
      if ( *(_BYTE *)(v29 + 197) == (_BYTE)a6 )
      {
        if ( *((_BYTE *)a1 + 308) != (_BYTE)a6 )
          goto LABEL_75;
        v31 = v30(*(_QWORD *)(v29 + 520), *((unsigned __int8 *)&dword_1800B7544 + 2 * a5 + v23), v16, 0, v24, a1[47]);
        v32 = v31;
        if ( v31 == 1 )
        {
          sqlite3ErrorMsg(a1, "not authorized");
          *((_DWORD *)a1 + 6) = 23;
        }
        else if ( (v31 & 0xFFFFFFFD) != 0 )
        {
          v32 = 1;
          sqlite3ErrorMsg(a1, "authorizer malfunction");
          *((_DWORD *)a1 + 6) = 1;
        }
        if ( v32 )
          goto LABEL_105;
      }
    }
  }
  if ( !*((_BYTE *)a1 + 308) )
  {
    v33 = *(_QWORD *)(v45 + *(_QWORD *)(v7 + 32));
    if ( (unsigned int)sqlite3ReadSchema(a1) )
      goto LABEL_105;
    Table = sqlite3FindTable(v7, v16, v33);
    if ( Table )
    {
      if ( a7 )
      {
        sqlite3CodeVerifySchema(a1, v14);
        sqlite3ForceNotReadOnly(a1);
      }
      else
      {
        if ( *(_BYTE *)(Table + 63) != 2 )
          v19 = "table";
        sqlite3ErrorMsg(a1, "%s %T already exists", v19, v12);
      }
      goto LABEL_105;
    }
    if ( sqlite3FindIndex(v7, v16, v33) )
    {
      sqlite3ErrorMsg(a1, "there is already an index named %s", v16);
      goto LABEL_105;
    }
  }
LABEL_75:
  if ( !v7 )
  {
    v35 = sqlite3Malloc(104);
    goto LABEL_93;
  }
  if ( *(_WORD *)(v7 + 420) >= 0x68u )
  {
    v36 = *(_QWORD **)(v7 + 472);
    if ( v36 )
    {
      *(_QWORD *)(v7 + 472) = *v36;
    }
    else
    {
      v36 = *(_QWORD **)(v7 + 464);
      if ( v36 )
      {
        *(_QWORD *)(v7 + 464) = *v36;
      }
      else
      {
        v36 = *(_QWORD **)(v7 + 456);
        if ( v36 )
        {
          *(_QWORD *)(v7 + 456) = *v36;
        }
        else
        {
          v36 = *(_QWORD **)(v7 + 448);
          if ( !v36 )
          {
            ++*(_DWORD *)(v7 + 440);
            goto LABEL_79;
          }
          *(_QWORD *)(v7 + 448) = *v36;
        }
      }
    }
    ++*(_DWORD *)(v7 + 432);
  }
  else
  {
    if ( !*(_DWORD *)(v7 + 416) )
    {
      ++*(_DWORD *)(v7 + 436);
LABEL_79:
      v35 = dbMallocRawFinish(v7, 104, v10, v24);
LABEL_93:
      v36 = (_QWORD *)v35;
      goto LABEL_94;
    }
    if ( !*(_BYTE *)(v7 + 103) )
      goto LABEL_79;
    v36 = 0;
  }
LABEL_94:
  if ( !v36 )
  {
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 7;
    goto LABEL_105;
  }
  memset_0(v36, 0, 0x68u);
  *v36 = v16;
  *((_WORD *)v36 + 26) = -1;
  Vdbe = *(_QWORD *)(*(_QWORD *)(v7 + 32) + v45 + 24);
  v36[12] = Vdbe;
  *((_DWORD *)v36 + 11) = 1;
  *((_WORD *)v36 + 29) = 200;
  a1[44] = (__int64)v36;
  if ( !*(_BYTE *)(v7 + 197) )
  {
    Vdbe = sqlite3GetVdbe(a1);
    v37 = Vdbe;
    if ( Vdbe )
    {
      sqlite3BeginWriteOperation(a1, 1, v14);
      if ( a6 )
        sqlite3VdbeAddOp3(v37, 170, 0, 0, 0);
      v38 = *((_DWORD *)a1 + 14) + 1;
      *((_DWORD *)a1 + 34) = v38;
      v39 = v38 + 1;
      v40 = v38 + 2;
      *((_DWORD *)a1 + 35) = v38 + 1;
      *((_DWORD *)a1 + 14) = v38 + 2;
      sqlite3VdbeAddOp3(v37, 99, v14, v38 + 2, 2);
      sqlite3VdbeUsesBtree(v37, v14);
      v42 = sqlite3VdbeAddOp3(v41, 16, v38 + 2, 0, 0);
      sqlite3VdbeAddOp3(v37, 100, v14, 2, (*(_BYTE *)(v7 + 48) & 2) != 0 ? 1 : 4);
      sqlite3VdbeAddOp3(v37, 100, v14, 5, *(unsigned __int8 *)(v7 + 100));
      *(_DWORD *)(sqlite3VdbeGetOp(v37, v42) + 8) = *(_DWORD *)(v37 + 144);
      if ( a5 || a6 )
        sqlite3VdbeAddOp3(v37, 71, 0, v39, 0);
      else
        *((_DWORD *)a1 + 52) = sqlite3VdbeAddOp3(v37, 147, v14, v39, 1);
      sqlite3OpenSchemaTable(a1, v14);
      sqlite3VdbeAddOp3(v37, 127, 0, v38, 0);
      sqlite3VdbeAddOp4(v37, 77, 6, v40, 0, (__int64)&qword_1800B6738, -1);
      sqlite3VdbeAddOp3(v37, 128, 0, v40, v38);
      sqlite3VdbeChangeP5(v37, 8);
      LOBYTE(Vdbe) = sqlite3VdbeAddOp3(v43, 122, 0, 0, 0);
    }
  }
  return Vdbe;
}

```

## disassembly

```asm
0x18002d694  push    rbx
0x18002d696  push    rbp
0x18002d697  push    rsi
0x18002d698  push    rdi
0x18002d699  push    r12
0x18002d69b  push    r13
0x18002d69d  push    r14
0x18002d69f  push    r15
0x18002d6a1  sub     rsp, 58h
0x18002d6a5  mov     rsi, [rcx]
0x18002d6a8  mov     rbp, r8
0x18002d6ab  mov     rdi, rcx
0x18002d6ae  lea     r8, aSqliteMaster; "sqlite_master"
0x18002d6b5  mov     r12d, r9d
0x18002d6b8  mov     rbx, rdx
0x18002d6bb  mov     ecx, 1
0x18002d6c0  mov     al, [rsi+0C5h]
0x18002d6c6  test    al, al
0x18002d6c8  jz      short loc_18002D6F8
0x18002d6ca  cmp     [rsi+0C0h], ecx
0x18002d6d0  jnz     short loc_18002D6F8
0x18002d6d2  movzx   r14d, byte ptr [rsi+0C4h]
0x18002d6da  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x18002d6e1  cmp     r14d, ecx
0x18002d6e4  mov     rcx, rsi
0x18002d6e7  cmovnz  rdx, r8
0x18002d6eb  call    sqlite3DbStrDup
0x18002d6f0  mov     rbp, rax
0x18002d6f3  jmp     loc_18002D7A8
0x18002d6f8  cmp     dword ptr [rbp+8], 0
0x18002d6fc  jbe     short loc_18002D73B
0x18002d6fe  test    al, al
0x18002d700  jz      short loc_18002D70B
0x18002d702  lea     rdx, aCorruptDatabas; "corrupt database"
0x18002d709  jmp     short loc_18002D75A
0x18002d70b  mov     rcx, rsi
0x18002d70e  call    sqlite3FindDb
0x18002d713  mov     r14d, eax
0x18002d716  test    eax, eax
0x18002d718  jns     short loc_18002D731
0x18002d71a  mov     r8, rbx
0x18002d71d  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x18002d724  mov     rcx, rdi
0x18002d727  call    sqlite3ErrorMsg
0x18002d72c  jmp     loc_18002DDEF
0x18002d731  mov     rbx, rbp
0x18002d734  mov     ecx, 1
0x18002d739  jmp     short loc_18002D743
0x18002d73b  movzx   r14d, byte ptr [rsi+0C4h]
0x18002d743  test    r12d, r12d
0x18002d746  jz      short loc_18002D76A
0x18002d748  cmp     dword ptr [rbp+8], 0
0x18002d74c  jbe     short loc_18002D767
0x18002d74e  cmp     r14d, ecx
0x18002d751  jz      short loc_18002D767
0x18002d753  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x18002d75a  mov     rcx, rdi
0x18002d75d  call    sqlite3ErrorMsg
0x18002d762  jmp     loc_18002DDEF
0x18002d767  test    r12d, r12d
0x18002d76a  cmovnz  r14d, ecx
0x18002d76e  test    rbx, rbx
0x18002d771  jz      short loc_18002D78F
0x18002d773  mov     r8d, [rbx+8]
0x18002d777  mov     rcx, rsi
0x18002d77a  mov     rdx, [rbx]
0x18002d77d  call    sqlite3DbStrNDup
0x18002d782  mov     rcx, rax
0x18002d785  mov     rbp, rax
0x18002d788  call    sqlite3Dequote
0x18002d78d  jmp     short loc_18002D791
0x18002d78f  xor     ebp, ebp
0x18002d791  cmp     byte ptr [rdi+134h], 2
0x18002d798  jb      short loc_18002D7A8
0x18002d79a  mov     r8, rbx
0x18002d79d  mov     rdx, rbp
0x18002d7a0  mov     rcx, rdi
0x18002d7a3  call    sqlite3RenameTokenMap
0x18002d7a8  movups  xmm0, xmmword ptr [rbx]
0x18002d7ab  movdqu  xmmword ptr [rdi+110h], xmm0
0x18002d7b3  test    rbp, rbp
0x18002d7b6  jz      loc_18002DDEF
0x18002d7bc  cmp     [rsp+98h+arg_20], 0
0x18002d7c4  lea     rax, aTable; "table"
0x18002d7cb  mov     r15, [rdi]
0x18002d7ce  lea     r13, aView_0; "view"
0x18002d7d5  mov     rcx, r13
0x18002d7d8  cmovz   rcx, rax
0x18002d7dc  mov     eax, [r15+30h]
0x18002d7e0  and     eax, 10000001h
0x18002d7e5  cmp     rax, 1
0x18002d7e9  jz      loc_18002D89E
0x18002d7ef  test    byte ptr [r15+0C8h], 2
0x18002d7f7  jnz     loc_18002D89E
0x18002d7fd  cmp     cs:byte_1800C6979, 0
0x18002d804  jz      loc_18002D89E
0x18002d80a  cmp     byte ptr [r15+0C5h], 0
0x18002d812  jz      short loc_18002D85B
0x18002d814  mov     r15, [r15+0D0h]
0x18002d81b  mov     rdx, [r15]
0x18002d81e  call    sqlite3_stricmp
0x18002d823  test    eax, eax
0x18002d825  jnz     short loc_18002D847
0x18002d827  mov     rdx, [r15+8]
0x18002d82b  mov     rcx, rbp
0x18002d82e  call    sqlite3_stricmp
0x18002d833  test    eax, eax
0x18002d835  jnz     short loc_18002D847
0x18002d837  mov     rdx, [r15+10h]
0x18002d83b  mov     rcx, rbp
0x18002d83e  call    sqlite3_stricmp
0x18002d843  test    eax, eax
0x18002d845  jz      short loc_18002D89E
0x18002d847  lea     rdx, Src
0x18002d84e  mov     rcx, rdi
0x18002d851  call    sqlite3ErrorMsg
0x18002d856  jmp     loc_18002DDE0
0x18002d85b  cmp     byte ptr [rdi+1Eh], 0
0x18002d85f  jnz     short loc_18002D87A
0x18002d861  mov     r8d, 7
0x18002d867  lea     rdx, aSqlite_0; "sqlite_"
0x18002d86e  mov     rcx, rbp
0x18002d871  call    sqlite3_strnicmp
0x18002d876  test    eax, eax
0x18002d878  jz      short loc_18002D892
0x18002d87a  mov     rcx, r15
0x18002d87d  call    sqlite3ReadOnlyShadowTables
0x18002d882  test    eax, eax
0x18002d884  jz      short loc_18002D89E
0x18002d886  mov     rdx, rbp
0x18002d889  call    sqlite3ShadowTableName
0x18002d88e  test    eax, eax
0x18002d890  jz      short loc_18002D89E
0x18002d892  lea     rdx, aObjectNameRese; "object name reserved for internal use: "...
0x18002d899  jmp     loc_18002DAEE
0x18002d89e  mov     rax, [rsi+20h]
0x18002d8a2  mov     edx, 1
0x18002d8a7  cmp     [rsi+0C4h], dl
0x18002d8ad  mov     ecx, r14d
0x18002d8b0  cmovnz  edx, r12d
0x18002d8b4  shl     rcx, 5
0x18002d8b8  mov     [rsp+98h+var_58], rcx
0x18002d8bd  cmp     edx, 1
0x18002d8c0  mov     [rsp+98h+arg_0], edx
0x18002d8c7  mov     r9, [rcx+rax]
0x18002d8cb  lea     rcx, aSqliteMaster; "sqlite_master"
0x18002d8d2  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x18002d8d9  mov     [rsp+98h+var_50], r9
0x18002d8de  cmovnz  rax, rcx
0x18002d8e2  mov     rcx, [rdi]
0x18002d8e5  mov     r10, [rcx+200h]
0x18002d8ec  test    r10, r10
0x18002d8ef  jz      loc_18002D98A
0x18002d8f5  cmp     byte ptr [rcx+0C5h], 0
0x18002d8fc  jnz     loc_18002D98A
0x18002d902  cmp     byte ptr [rdi+134h], 0
0x18002d909  jnz     short loc_18002D98A
0x18002d90b  mov     rdx, [rdi+178h]
0x18002d912  mov     r8, rax
0x18002d915  mov     rcx, [rcx+208h]
0x18002d91c  mov     rax, r10
0x18002d91f  mov     [rsp+98h+var_70], rdx
0x18002d924  mov     [rsp+98h+var_78], r9
0x18002d929  xor     r9d, r9d
0x18002d92c  lea     edx, [r9+12h]
0x18002d930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d935  mov     r15d, eax
0x18002d938  cmp     eax, 1
0x18002d93b  jnz     short loc_18002D955
0x18002d93d  lea     rdx, aNotAuthorized; "not authorized"
0x18002d944  mov     rcx, rdi
0x18002d947  call    sqlite3ErrorMsg
0x18002d94c  mov     dword ptr [rdi+18h], 17h
0x18002d953  jmp     short loc_18002D975
0x18002d955  test    eax, 0FFFFFFFDh
0x18002d95a  jz      short loc_18002D975
0x18002d95c  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x18002d963  mov     rcx, rdi
0x18002d966  mov     r15d, 1
0x18002d96c  call    sqlite3ErrorMsg
0x18002d971  mov     [rdi+18h], r15d
0x18002d975  test    r15d, r15d
0x18002d978  jnz     loc_18002DDE0
0x18002d97e  mov     edx, [rsp+98h+arg_0]
0x18002d985  mov     r9, [rsp+98h+var_50]
0x18002d98a  mov     r12d, [rsp+98h+arg_28]
0x18002d992  test    r12d, r12d
0x18002d995  jnz     loc_18002DA4F
0x18002d99b  mov     rcx, [rdi]
0x18002d99e  mov     rax, [rcx+200h]
0x18002d9a5  test    rax, rax
0x18002d9a8  jz      loc_18002DA4F
0x18002d9ae  cmp     [rcx+0C5h], r12b
0x18002d9b5  jnz     loc_18002DA4F
0x18002d9bb  cmp     [rdi+134h], r12b
0x18002d9c2  jnz     loc_18002DAFE
0x18002d9c8  mov     r8d, [rsp+98h+arg_20]
0x18002d9d0  mov     rcx, [rcx+208h]
0x18002d9d7  lea     edx, [rdx+r8*2]
0x18002d9db  movsxd  r8, edx
0x18002d9de  lea     rdx, dword_1800B7544
0x18002d9e5  movzx   edx, byte ptr [r8+rdx]
0x18002d9ea  mov     r8, [rdi+178h]
0x18002d9f1  mov     [rsp+98h+var_70], r8
0x18002d9f6  mov     r8, rbp
0x18002d9f9  mov     [rsp+98h+var_78], r9
0x18002d9fe  xor     r9d, r9d
0x18002da01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da06  mov     r15d, eax
0x18002da09  cmp     eax, 1
0x18002da0c  jnz     short loc_18002DA26
0x18002da0e  lea     rdx, aNotAuthorized; "not authorized"
0x18002da15  mov     rcx, rdi
0x18002da18  call    sqlite3ErrorMsg
0x18002da1d  mov     dword ptr [rdi+18h], 17h
0x18002da24  jmp     short loc_18002DA46
0x18002da26  test    eax, 0FFFFFFFDh
0x18002da2b  jz      short loc_18002DA46
0x18002da2d  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x18002da34  mov     rcx, rdi
0x18002da37  mov     r15d, 1
0x18002da3d  call    sqlite3ErrorMsg
0x18002da42  mov     [rdi+18h], r15d
0x18002da46  test    r15d, r15d
0x18002da49  jnz     loc_18002DDE0
0x18002da4f  cmp     byte ptr [rdi+134h], 0
0x18002da56  jnz     loc_18002DAFE
0x18002da5c  mov     rax, [rsi+20h]
0x18002da60  mov     rcx, rdi
0x18002da63  mov     r15, [rsp+98h+var_58]
0x18002da68  mov     r15, [r15+rax]
0x18002da6c  call    sqlite3ReadSchema
0x18002da71  test    eax, eax
0x18002da73  jnz     loc_18002DDE0
0x18002da79  mov     r8, r15
0x18002da7c  mov     rdx, rbp
0x18002da7f  mov     rcx, rsi
0x18002da82  call    sqlite3FindTable
0x18002da87  test    rax, rax
0x18002da8a  jz      short loc_18002DAD4
0x18002da8c  cmp     [rsp+98h+arg_30], 0
0x18002da94  mov     rcx, rdi
0x18002da97  jnz     short loc_18002DABF
0x18002da99  cmp     byte ptr [rax+3Fh], 2
0x18002da9d  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x18002daa4  lea     rax, aTable; "table"
0x18002daab  mov     r9, rbx
0x18002daae  cmovnz  r13, rax
0x18002dab2  mov     r8, r13
0x18002dab5  call    sqlite3ErrorMsg
0x18002daba  jmp     loc_18002DDE0
0x18002dabf  mov     edx, r14d
0x18002dac2  call    sqlite3CodeVerifySchema
0x18002dac7  mov     rcx, rdi
0x18002daca  call    sqlite3ForceNotReadOnly
0x18002dacf  jmp     loc_18002DDE0
0x18002dad4  mov     r8, r15
0x18002dad7  mov     rdx, rbp
0x18002dada  mov     rcx, rsi
0x18002dadd  call    sqlite3FindIndex
0x18002dae2  test    rax, rax
0x18002dae5  jz      short loc_18002DAFE
0x18002dae7  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x18002daee  mov     r8, rbp
0x18002daf1  mov     rcx, rdi
0x18002daf4  call    sqlite3ErrorMsg
0x18002daf9  jmp     loc_18002DDE0
0x18002dafe  mov     r15d, 68h ; 'h'
0x18002db04  test    rsi, rsi
0x18002db07  jz      loc_18002DBB1
0x18002db0d  cmp     r15w, [rsi+1A4h]
0x18002db15  jbe     short loc_18002DB40
0x18002db17  cmp     dword ptr [rsi+1A0h], 0
0x18002db1e  jnz     short loc_18002DB36
0x18002db20  inc     dword ptr [rsi+1B4h]
0x18002db26  mov     rdx, r15
0x18002db29  mov     rcx, rsi
0x18002db2c  call    dbMallocRawFinish
0x18002db31  jmp     loc_18002DBB9
0x18002db36  cmp     byte ptr [rsi+67h], 0
0x18002db3a  jz      short loc_18002DB26
0x18002db3c  xor     ebx, ebx
0x18002db3e  jmp     short loc_18002DBBC
0x18002db40  mov     rbx, [rsi+1D8h]
0x18002db47  test    rbx, rbx
0x18002db4a  jz      short loc_18002DB5E
0x18002db4c  mov     rax, [rbx]
0x18002db4f  mov     [rsi+1D8h], rax
0x18002db56  inc     dword ptr [rsi+1B0h]
0x18002db5c  jmp     short loc_18002DBBC
0x18002db5e  mov     rbx, [rsi+1D0h]
0x18002db65  test    rbx, rbx
0x18002db68  jz      short loc_18002DB76
0x18002db6a  mov     rax, [rbx]
0x18002db6d  mov     [rsi+1D0h], rax
0x18002db74  jmp     short loc_18002DB56
0x18002db76  mov     rbx, [rsi+1C8h]
0x18002db7d  test    rbx, rbx
0x18002db80  jz      short loc_18002DB8E
0x18002db82  mov     rax, [rbx]
  ... truncated ...
```

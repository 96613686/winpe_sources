# sqlite3StartTable

- ea: `0x18009c7d0`
- end: `0x18009cf09`
- name: `sqlite3StartTable`
- size: `1849`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `reparse_path`

## callers

- `0x180070f50`
- `0x1800d8b00`

## callees

- `0x180005980`
- `0x180023dd0`
- `0x180044640`
- `0x18004c5e0`
- `0x18004dba0`
- `0x1800658d0`
- `0x1800669c0`
- `0x18006b6d0`
- `0x180071400`
- `0x1800743d0`
- `0x18007b1b0`
- `0x18007c060`
- `0x18007c190`
- `0x18007e7f0`
- `0x180088560`
- `0x180088db0`
- `0x1800896a0`
- `0x180093650`
- `0x180094d20`
- `0x18009c7d0`
- `0x1800a2f60`
- `0x1800a2fd0`
- `0x1800a3040`
- `0x1800a30b0`
- `0x1800a3b40`
- `0x1800ae640`
- `0x1800b23b0`
- `0x1800c3f40`
- `0x1800e4dce`
- `0x1800e4dfe`

## string_xrefs

- `0x18009c816`: `sqlite_temp_master`
- `0x18009c961`: `sqlite_temp_master`
- `0x18009c8d3`: `temporary table name must be unqualified`
- `0x18009ca47`: `%s %T already exists`
- `0x18009cab2`: `there is already an index named %s`

## pseudocode

```c
char *__fastcall sqlite3StartTable(__int64 *a1, _OWORD *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  __int64 v7; // rsi
  char v12; // al
  unsigned int Db; // ebp
  const char *v14; // r15
  size_t v15; // rax
  size_t v16; // r12
  char *result; // rax
  char *v18; // rbx
  _BYTE *v19; // r15
  bool v20; // zf
  const char *v21; // r12
  const char *v22; // r8
  const char *v23; // r8
  int v24; // ecx
  __int64 v25; // r13
  __int64 v26; // r15
  __int64 Table; // rax
  __int64 *v28; // rcx
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  char *v32; // r14
  unsigned int v33; // r12d
  __int64 v34; // rcx
  unsigned int v35; // ebx
  int v36; // ecx
  unsigned int v37; // esi
  int v38; // r9d
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // [rsp+20h] [rbp-68h]
  __int64 v50; // [rsp+30h] [rbp-58h]
  int v51; // [rsp+90h] [rbp+8h]
  int v52; // [rsp+90h] [rbp+8h]

  v7 = *a1;
  v12 = *(_BYTE *)(*a1 + 197);
  if ( v12 && *(_DWORD *)(v7 + 192) == 1 )
  {
    Db = *(unsigned __int8 *)(v7 + 196);
    v14 = "sqlite_temp_master";
    if ( Db != 1 )
      v14 = "sqlite_master";
    v15 = strlen_0(v14);
    v16 = v15 + 1;
    if ( v7 )
      result = (char *)sqlite3DbMallocRawNN(v7, v15 + 1);
    else
      result = (char *)sqlite3Malloc(v15 + 1);
    v18 = result;
    if ( result )
      result = (char *)memcpy_0(result, v14, v16);
    v19 = (char *)a1 + 300;
  }
  else
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      if ( v12 )
        return (char *)sqlite3ErrorMsg(a1, "corrupt database");
      Db = sqlite3FindDb(v7);
      if ( (Db & 0x80000000) != 0 )
        return (char *)sqlite3ErrorMsg(a1, "unknown database %T", a2);
      a2 = (_OWORD *)a3;
    }
    else
    {
      Db = *(unsigned __int8 *)(v7 + 196);
    }
    v20 = a4 == 0;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && Db != 1 )
        return (char *)sqlite3ErrorMsg(a1, "temporary table name must be unqualified");
      v20 = a4 == 0;
    }
    if ( !v20 )
      Db = 1;
    result = (char *)sqlite3NameFromToken(v7, a2);
    v19 = (char *)a1 + 300;
    v18 = result;
    if ( *((_BYTE *)a1 + 300) >= 2u )
      result = (char *)sqlite3RenameTokenMap(a1, result, a2);
  }
  *(_OWORD *)(a1 + 33) = *a2;
  if ( !v18 )
    return result;
  v21 = "table";
  v22 = "table";
  if ( a5 )
    v22 = "view";
  if ( !(unsigned int)sqlite3CheckObjectName(a1, v18, v22, v18) )
  {
    v23 = "sqlite_temp_master";
    v24 = 1;
    if ( *(_BYTE *)(v7 + 196) != 1 )
      v24 = a4;
    v51 = v24;
    v25 = 32LL * Db;
    if ( v24 != 1 )
      v23 = "sqlite_master";
    v50 = *(_QWORD *)(*(_QWORD *)(v7 + 32) + 32LL * Db);
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v23, 0, v50)
      && (a6
       || !(unsigned int)sqlite3AuthCheck(
                           (_DWORD)a1,
                           (unsigned __int8)byte_18010F828[2 * a5 + v51],
                           (_DWORD)v18,
                           0,
                           v50)) )
    {
      if ( *v19 )
        goto LABEL_53;
      v26 = *(_QWORD *)(*(_QWORD *)(v7 + 32) + 32LL * Db);
      if ( !(unsigned int)sqlite3ReadSchema(a1) )
      {
        Table = sqlite3FindTable(v7, v18, v26);
        if ( Table )
        {
          v28 = a1;
          if ( a7 )
          {
            if ( a1[21] )
              v28 = (__int64 *)a1[21];
            v29 = *((_DWORD *)v28 + 31);
            if ( !_bittest(&v29, Db) )
            {
              *((_DWORD *)v28 + 31) = v29 | (1 << Db);
              if ( Db == 1 )
                sqlite3OpenTempDatabase();
            }
            sqlite3ForceNotReadOnly(a1);
          }
          else
          {
            if ( *(_BYTE *)(Table + 63) == 2 )
              v21 = "view";
            sqlite3ErrorMsg(a1, "%s %T already exists", v21, a2);
          }
          goto LABEL_97;
        }
        if ( sqlite3FindIndex(v7, v18, v26) )
        {
          sqlite3ErrorMsg(a1, "there is already an index named %s", v18);
          goto LABEL_97;
        }
LABEL_53:
        if ( v7 )
          v30 = sqlite3DbMallocRawNN(v7, 104);
        else
          v30 = sqlite3Malloc(104);
        v31 = v30;
        if ( v30 )
        {
          *(_OWORD *)v30 = 0;
          *(_OWORD *)(v30 + 16) = 0;
          *(_OWORD *)(v30 + 32) = 0;
          *(_OWORD *)(v30 + 48) = 0;
          *(_OWORD *)(v30 + 64) = 0;
          *(_OWORD *)(v30 + 80) = 0;
          *(_QWORD *)(v30 + 96) = 0;
          *(_QWORD *)v30 = v18;
          *(_WORD *)(v30 + 52) = -1;
          result = *(char **)(v7 + 32);
          *(_QWORD *)(v31 + 96) = *(_QWORD *)&result[v25 + 24];
          *(_DWORD *)(v31 + 44) = 1;
          *(_WORD *)(v31 + 58) = 200;
          a1[43] = v31;
          if ( !*(_BYTE *)(v7 + 197) )
          {
            v32 = (char *)a1[2];
            if ( v32 )
              goto LABEL_63;
            if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
              *((_BYTE *)a1 + 35) = 1;
            result = (char *)sqlite3VdbeCreate(a1);
            v32 = result;
            if ( result )
            {
LABEL_63:
              sqlite3BeginWriteOperation(a1, 1, Db);
              if ( a6 )
                sqlite3VdbeAddOp0(v32, 170);
              v52 = *((_DWORD *)a1 + 14) + 1;
              *((_DWORD *)a1 + 32) = v52;
              *((_DWORD *)a1 + 33) = v52 + 1;
              v33 = v52 + 2;
              *((_DWORD *)a1 + 14) = v52 + 2;
              sqlite3VdbeAddOp3((_DWORD)v32, 99, Db, v52 + 2, 2);
              sqlite3VdbeUsesBtree(v32, Db);
              v35 = sqlite3VdbeAddOp1(v34, 16, (unsigned int)(v52 + 2));
              v36 = 4;
              if ( (*(_BYTE *)(v7 + 48) & 2) != 0 )
                v36 = 1;
              sqlite3VdbeAddOp3((_DWORD)v32, 100, Db, 2, v36);
              sqlite3VdbeAddOp3((_DWORD)v32, 100, Db, 5, *(unsigned __int8 *)(v7 + 100));
              sqlite3VdbeJumpHere(v32, v35);
              if ( a5 || a6 )
              {
                v37 = v52;
                sqlite3VdbeAddOp2(v32, 71, 0, (unsigned int)(v52 + 1));
              }
              else
              {
                v37 = v52;
                *((_DWORD *)a1 + 50) = sqlite3VdbeAddOp3((_DWORD)v32, 147, Db, v52 + 1, 1);
              }
              v39 = a1[2];
              if ( !v39 )
              {
                if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
                  *((_BYTE *)a1 + 35) = 1;
                v39 = sqlite3VdbeCreate(a1);
              }
              if ( Db != 1 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*a1 + 32) + v25 + 8) + 17LL) )
              {
                LOBYTE(v38) = 1;
                lockTable((_DWORD)a1, Db, 1, v38, (__int64)"sqlite_master");
              }
              v40 = *(int *)(v39 + 144);
              if ( *(_DWORD *)(v39 + 148) > (int)v40 )
              {
                *(_DWORD *)(v39 + 144) = v40 + 1;
                v41 = 3 * v40;
                v42 = *(_QWORD *)(v39 + 136);
                *(_QWORD *)(v42 + 8 * v41) = 64881;
                *(_DWORD *)(v42 + 8 * v41 + 8) = 1;
                *(_DWORD *)(v42 + 8 * v41 + 12) = Db;
                *(_DWORD *)(v42 + 8 * v41 + 16) = 5;
              }
              else
              {
                addOp4IntSlow(v39, 113, 0, 1, Db, 5);
              }
              if ( !*((_DWORD *)a1 + 13) )
                *((_DWORD *)a1 + 13) = 1;
              sqlite3VdbeAddOp2(v32, 127, 0, v37);
              v43 = *((int *)v32 + 36);
              if ( *((_DWORD *)v32 + 37) > (int)v43 )
              {
                *((_DWORD *)v32 + 36) = v43 + 1;
                v44 = 3 * v43;
                v45 = *((_QWORD *)v32 + 17);
                *(_DWORD *)(v45 + 8 * v44) = 77;
                *(_DWORD *)(v45 + 8 * v44 + 4) = 6;
                *(_DWORD *)(v45 + 8 * v44 + 8) = v33;
                v46 = v45 + 24 * v43;
                *(_DWORD *)(v46 + 12) = 0;
                *(_QWORD *)(v46 + 16) = 0;
              }
              else
              {
                LODWORD(v49) = 0;
                LODWORD(v43) = growOp3(v32, 77, 6, v33, v49);
              }
              if ( !*(_BYTE *)(*(_QWORD *)v32 + 103LL) )
              {
                if ( (int)v43 < 0 )
                  LODWORD(v43) = *((_DWORD *)v32 + 36) - 1;
                v47 = *((_QWORD *)v32 + 17) + 24LL * (int)v43;
                if ( *(_BYTE *)(v47 + 1) )
                {
                  vdbeChangeP4Full(v32, v47, &dword_18010F82C, 0xFFFFFFFFLL);
                }
                else
                {
                  *(_BYTE *)(v47 + 1) = -1;
                  *(_QWORD *)(v47 + 16) = &dword_18010F82C;
                }
              }
              sqlite3VdbeAddOp3((_DWORD)v32, 128, 0, v33, v37);
              v48 = *((int *)v32 + 36);
              if ( (int)v48 > 0 )
                *(_WORD *)(*((_QWORD *)v32 + 17) + 24 * v48 - 22) = 8;
              return (char *)sqlite3VdbeAddOp0(v32, 122);
            }
          }
          return result;
        }
        ++*((_DWORD *)a1 + 12);
        *((_DWORD *)a1 + 6) = 7;
      }
    }
  }
LABEL_97:
  *((_BYTE *)a1 + 29) = 1;
  if ( !v7 )
    return (char *)sqlite3_free(v18);
  if ( (unsigned __int64)v18 < *(_QWORD *)(v7 + 496) )
  {
    if ( (unsigned __int64)v18 >= *(_QWORD *)(v7 + 480) )
    {
      result = *(char **)(v7 + 472);
      *(_QWORD *)v18 = result;
      *(_QWORD *)(v7 + 472) = v18;
      return result;
    }
    if ( (unsigned __int64)v18 >= *(_QWORD *)(v7 + 488) )
    {
      result = *(char **)(v7 + 456);
      *(_QWORD *)v18 = result;
      *(_QWORD *)(v7 + 456) = v18;
      return result;
    }
  }
  if ( *(_QWORD *)(v7 + 776) )
    return (char *)measureAllocationSize(v7, v18);
  else
    return (char *)sqlite3_free(v18);
}

```

## disassembly

```asm
0x18009c7d0  push    rbx
0x18009c7d2  push    rbp
0x18009c7d3  push    rsi
0x18009c7d4  push    rdi
0x18009c7d5  push    r12
0x18009c7d7  push    r13
0x18009c7d9  push    r14
0x18009c7db  push    r15
0x18009c7dd  sub     rsp, 48h
0x18009c7e1  mov     rsi, [rcx]
0x18009c7e4  mov     r14, rdx
0x18009c7e7  mov     rdi, rcx
0x18009c7ea  lea     rdx, aSqliteMaster; "sqlite_master"
0x18009c7f1  mov     r13d, r9d
0x18009c7f4  mov     rbx, r8
0x18009c7f7  mov     ecx, 1
0x18009c7fc  movzx   eax, byte ptr [rsi+0C5h]
0x18009c803  test    al, al
0x18009c805  jz      short loc_18009C86B
0x18009c807  cmp     [rsi+0C0h], ecx
0x18009c80d  jnz     short loc_18009C86B
0x18009c80f  movzx   ebp, byte ptr [rsi+0C4h]
0x18009c816  lea     r15, aSqliteTempMast; "sqlite_temp_master"
0x18009c81d  cmp     ebp, ecx
0x18009c81f  cmovnz  r15, rdx
0x18009c823  mov     rcx, r15; Str
0x18009c826  call    strlen_0
0x18009c82b  lea     r12, [rax+1]
0x18009c82f  test    rsi, rsi
0x18009c832  jz      short loc_18009C841
0x18009c834  mov     rdx, r12
0x18009c837  mov     rcx, rsi
0x18009c83a  call    sqlite3DbMallocRawNN
0x18009c83f  jmp     short loc_18009C849
0x18009c841  mov     rcx, r12
0x18009c844  call    sqlite3Malloc
0x18009c849  mov     rbx, rax
0x18009c84c  test    rax, rax
0x18009c84f  jz      short loc_18009C85F
0x18009c851  mov     r8, r12; Size
0x18009c854  mov     rdx, r15; Src
0x18009c857  mov     rcx, rax; void *
0x18009c85a  call    memcpy_0
0x18009c85f  lea     r15, [rdi+12Ch]
0x18009c866  jmp     loc_18009C916
0x18009c86b  cmp     dword ptr [r8+8], 0
0x18009c870  jbe     short loc_18009C8BC
0x18009c872  test    al, al
0x18009c874  jz      short loc_18009C88A
0x18009c876  lea     rdx, aCorruptDatabas; "corrupt database"
0x18009c87d  mov     rcx, rdi
0x18009c880  call    sqlite3ErrorMsg
0x18009c885  jmp     loc_18009CEF8
0x18009c88a  mov     rdx, r14
0x18009c88d  mov     rcx, rsi
0x18009c890  call    sqlite3FindDb
0x18009c895  mov     ebp, eax
0x18009c897  test    eax, eax
0x18009c899  jns     short loc_18009C8B2
0x18009c89b  mov     r8, r14
0x18009c89e  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x18009c8a5  mov     rcx, rdi
0x18009c8a8  call    sqlite3ErrorMsg
0x18009c8ad  jmp     loc_18009CEF8
0x18009c8b2  mov     r14, rbx
0x18009c8b5  mov     ecx, 1
0x18009c8ba  jmp     short loc_18009C8C3
0x18009c8bc  movzx   ebp, byte ptr [rsi+0C4h]
0x18009c8c3  test    r13d, r13d
0x18009c8c6  jz      short loc_18009C8EA
0x18009c8c8  cmp     dword ptr [rbx+8], 0
0x18009c8cc  jbe     short loc_18009C8E7
0x18009c8ce  cmp     ebp, 1
0x18009c8d1  jz      short loc_18009C8E7
0x18009c8d3  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x18009c8da  mov     rcx, rdi
0x18009c8dd  call    sqlite3ErrorMsg
0x18009c8e2  jmp     loc_18009CEF8
0x18009c8e7  test    r13d, r13d
0x18009c8ea  cmovnz  ebp, ecx
0x18009c8ed  mov     rdx, r14
0x18009c8f0  mov     rcx, rsi
0x18009c8f3  call    sqlite3NameFromToken
0x18009c8f8  lea     r15, [rdi+12Ch]
0x18009c8ff  mov     rbx, rax
0x18009c902  cmp     byte ptr [r15], 2
0x18009c906  jb      short loc_18009C916
0x18009c908  mov     r8, r14
0x18009c90b  mov     rdx, rax
0x18009c90e  mov     rcx, rdi
0x18009c911  call    sqlite3RenameTokenMap
0x18009c916  movups  xmm0, xmmword ptr [r14]
0x18009c91a  movups  xmmword ptr [rdi+108h], xmm0
0x18009c921  test    rbx, rbx
0x18009c924  jz      loc_18009CEF8
0x18009c92a  cmp     [rsp+88h+arg_20], 0
0x18009c932  lea     rax, aView_0; "view"
0x18009c939  lea     r12, aTable; "table"
0x18009c940  mov     r9, rbx
0x18009c943  mov     r8, r12
0x18009c946  mov     rdx, rbx
0x18009c949  cmovnz  r8, rax
0x18009c94d  mov     rcx, rdi
0x18009c950  call    sqlite3CheckObjectName
0x18009c955  test    eax, eax
0x18009c957  jnz     loc_18009CE8F
0x18009c95d  mov     rax, [rsi+20h]
0x18009c961  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18009c968  mov     ecx, 1
0x18009c96d  cmp     [rsi+0C4h], cl
0x18009c973  cmovnz  ecx, r13d
0x18009c977  mov     r13d, ebp
0x18009c97a  mov     [rsp+88h+arg_0], ecx
0x18009c981  shl     r13, 5
0x18009c985  cmp     ecx, 1
0x18009c988  lea     rcx, aSqliteMaster; "sqlite_master"
0x18009c98f  cmovnz  r8, rcx
0x18009c993  xor     r9d, r9d
0x18009c996  mov     rdx, [rax+r13]
0x18009c99a  mov     rcx, rdi
0x18009c99d  mov     [rsp+88h+var_58], rdx
0x18009c9a2  mov     [rsp+88h+var_68], rdx
0x18009c9a7  mov     edx, 12h
0x18009c9ac  call    sqlite3AuthCheck
0x18009c9b1  test    eax, eax
0x18009c9b3  jnz     loc_18009CE8F
0x18009c9b9  cmp     [rsp+88h+arg_28], eax
0x18009c9c0  jnz     short loc_18009CA01
0x18009c9c2  mov     eax, [rsp+88h+arg_0]
0x18009c9c9  xor     r9d, r9d
0x18009c9cc  mov     ecx, [rsp+88h+arg_20]
0x18009c9d3  mov     r8, rbx
0x18009c9d6  lea     eax, [rax+rcx*2]
0x18009c9d9  movsxd  rcx, eax
0x18009c9dc  lea     rax, byte_18010F828
0x18009c9e3  movzx   edx, byte ptr [rcx+rax]
0x18009c9e7  mov     rcx, rdi
0x18009c9ea  mov     rax, [rsp+88h+var_58]
0x18009c9ef  mov     [rsp+88h+var_68], rax
0x18009c9f4  call    sqlite3AuthCheck
0x18009c9f9  test    eax, eax
0x18009c9fb  jnz     loc_18009CE8F
0x18009ca01  cmp     byte ptr [r15], 0
0x18009ca05  jnz     loc_18009CAC6
0x18009ca0b  mov     rax, [rsi+20h]
0x18009ca0f  mov     rcx, rdi
0x18009ca12  mov     r15, [rax+r13]
0x18009ca16  call    sqlite3ReadSchema
0x18009ca1b  test    eax, eax
0x18009ca1d  jnz     loc_18009CE8F
0x18009ca23  mov     r8, r15
0x18009ca26  mov     rdx, rbx
0x18009ca29  mov     rcx, rsi
0x18009ca2c  call    sqlite3FindTable
0x18009ca31  test    rax, rax
0x18009ca34  jz      short loc_18009CA9C
0x18009ca36  cmp     [rsp+88h+arg_30], 0
0x18009ca3e  mov     rcx, rdi
0x18009ca41  jnz     short loc_18009CA69
0x18009ca43  cmp     byte ptr [rax+3Fh], 2
0x18009ca47  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x18009ca4e  lea     rax, aView_0; "view"
0x18009ca55  mov     r9, r14
0x18009ca58  cmovz   r12, rax
0x18009ca5c  mov     r8, r12
0x18009ca5f  call    sqlite3ErrorMsg
0x18009ca64  jmp     loc_18009CE8F
0x18009ca69  mov     rax, [rdi+0A8h]
0x18009ca70  test    rax, rax
0x18009ca73  cmovnz  rcx, rax
0x18009ca77  mov     eax, [rcx+7Ch]
0x18009ca7a  bt      eax, ebp
0x18009ca7d  jb      short loc_18009CA8F
0x18009ca7f  bts     eax, ebp
0x18009ca82  mov     [rcx+7Ch], eax
0x18009ca85  cmp     ebp, 1
0x18009ca88  jnz     short loc_18009CA8F
0x18009ca8a  call    sqlite3OpenTempDatabase
0x18009ca8f  mov     rcx, rdi
0x18009ca92  call    sqlite3ForceNotReadOnly
0x18009ca97  jmp     loc_18009CE8F
0x18009ca9c  mov     r8, r15
0x18009ca9f  mov     rdx, rbx
0x18009caa2  mov     rcx, rsi
0x18009caa5  call    sqlite3FindIndex
0x18009caaa  test    rax, rax
0x18009caad  jz      short loc_18009CAC6
0x18009caaf  mov     r8, rbx
0x18009cab2  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x18009cab9  mov     rcx, rdi
0x18009cabc  call    sqlite3ErrorMsg
0x18009cac1  jmp     loc_18009CE8F
0x18009cac6  test    rsi, rsi
0x18009cac9  jz      short loc_18009CADA
0x18009cacb  mov     edx, 68h ; 'h'
0x18009cad0  mov     rcx, rsi
0x18009cad3  call    sqlite3DbMallocRawNN
0x18009cad8  jmp     short loc_18009CAE4
0x18009cada  mov     ecx, 68h ; 'h'
0x18009cadf  call    sqlite3Malloc
0x18009cae4  mov     rdx, rax
0x18009cae7  test    rax, rax
0x18009caea  jz      loc_18009CE85
0x18009caf0  xorps   xmm0, xmm0
0x18009caf3  xor     eax, eax
0x18009caf5  movups  xmmword ptr [rdx], xmm0
0x18009caf8  movups  xmmword ptr [rdx+10h], xmm0
0x18009cafc  movups  xmmword ptr [rdx+20h], xmm0
0x18009cb00  movups  xmmword ptr [rdx+30h], xmm0
0x18009cb04  movups  xmmword ptr [rdx+40h], xmm0
0x18009cb08  movups  xmmword ptr [rdx+50h], xmm0
0x18009cb0c  mov     [rdx+60h], rax
0x18009cb10  mov     [rdx], rbx
0x18009cb13  mov     ebx, 1
0x18009cb18  mov     word ptr [rdx+34h], 0FFFFh
0x18009cb1e  mov     rax, [rsi+20h]
0x18009cb22  mov     rcx, [rax+r13+18h]
0x18009cb27  mov     [rdx+60h], rcx
0x18009cb2b  mov     [rdx+2Ch], ebx
0x18009cb2e  mov     word ptr [rdx+3Ah], 0C8h
0x18009cb34  mov     [rdi+158h], rdx
0x18009cb3b  cmp     byte ptr [rsi+0C5h], 0
0x18009cb42  jnz     loc_18009CEF8
0x18009cb48  mov     r14, [rdi+10h]
0x18009cb4c  test    r14, r14
0x18009cb4f  jnz     short loc_18009CB7A
0x18009cb51  cmp     [rdi+0A8h], r14
0x18009cb58  jnz     short loc_18009CB66
0x18009cb5a  mov     rax, [rdi]
0x18009cb5d  test    byte ptr [rax+60h], 8
0x18009cb61  jnz     short loc_18009CB66
0x18009cb63  mov     [rdi+23h], bl
0x18009cb66  mov     rcx, rdi
0x18009cb69  call    sqlite3VdbeCreate
0x18009cb6e  mov     r14, rax
0x18009cb71  test    rax, rax
0x18009cb74  jz      loc_18009CEF8
0x18009cb7a  mov     r8d, ebp
0x18009cb7d  mov     edx, ebx
0x18009cb7f  mov     rcx, rdi
0x18009cb82  call    sqlite3BeginWriteOperation
0x18009cb87  mov     r15d, [rsp+88h+arg_28]
0x18009cb8f  test    r15d, r15d
0x18009cb92  jz      short loc_18009CBA1
0x18009cb94  mov     edx, 0AAh
0x18009cb99  mov     rcx, r14
0x18009cb9c  call    sqlite3VdbeAddOp0
0x18009cba1  mov     eax, [rdi+38h]
0x18009cba4  mov     r8d, ebp
0x18009cba7  inc     eax
0x18009cba9  mov     dword ptr [rsp+88h+var_68], 2
0x18009cbb1  mov     [rsp+88h+arg_0], eax
0x18009cbb8  mov     edx, 63h ; 'c'
0x18009cbbd  mov     [rdi+80h], eax
0x18009cbc3  mov     rcx, r14
0x18009cbc6  inc     eax
0x18009cbc8  mov     [rdi+84h], eax
0x18009cbce  lea     r12d, [rax+1]
0x18009cbd2  mov     r9d, r12d
0x18009cbd5  mov     [rdi+38h], r12d
0x18009cbd9  call    sqlite3VdbeAddOp3
0x18009cbde  mov     edx, ebp
0x18009cbe0  mov     rcx, r14
0x18009cbe3  call    sqlite3VdbeUsesBtree
0x18009cbe8  mov     r8d, r12d
0x18009cbeb  mov     edx, 10h
0x18009cbf0  call    sqlite3VdbeAddOp1
0x18009cbf5  test    byte ptr [rsi+30h], 2
0x18009cbf9  mov     ebx, eax
0x18009cbfb  mov     eax, 1
0x18009cc00  mov     ecx, 4
0x18009cc05  cmovnz  ecx, eax
0x18009cc08  mov     r9d, 2
0x18009cc0e  mov     dword ptr [rsp+88h+var_68], ecx
0x18009cc12  mov     r8d, ebp
0x18009cc15  mov     rcx, r14
0x18009cc18  mov     edx, 64h ; 'd'
0x18009cc1d  call    sqlite3VdbeAddOp3
0x18009cc22  movzx   ecx, byte ptr [rsi+64h]
0x18009cc26  mov     r9d, 5
0x18009cc2c  mov     dword ptr [rsp+88h+var_68], ecx
0x18009cc30  mov     r8d, ebp
0x18009cc33  mov     rcx, r14
0x18009cc36  mov     edx, 64h ; 'd'
0x18009cc3b  call    sqlite3VdbeAddOp3
0x18009cc40  mov     edx, ebx
0x18009cc42  mov     rcx, r14
0x18009cc45  call    sqlite3VdbeJumpHere
0x18009cc4a  cmp     [rsp+88h+arg_20], 0
0x18009cc52  jnz     short loc_18009CC87
0x18009cc54  test    r15d, r15d
0x18009cc57  jnz     short loc_18009CC87
0x18009cc59  mov     esi, [rsp+88h+arg_0]
0x18009cc60  mov     r15d, 1
0x18009cc66  mov     r8d, ebp
0x18009cc69  mov     dword ptr [rsp+88h+var_68], r15d
0x18009cc6e  mov     edx, 93h
0x18009cc73  mov     rcx, r14
0x18009cc76  lea     r9d, [rsi+1]
0x18009cc7a  call    sqlite3VdbeAddOp3
  ... truncated ...
```

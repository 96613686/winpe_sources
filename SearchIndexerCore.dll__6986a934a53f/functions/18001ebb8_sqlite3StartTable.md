# sqlite3StartTable

- ea: `0x18001ebb8`
- end: `0x18001f0e7`
- name: `sqlite3StartTable`
- size: `1327`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x18000213c`
- `0x18007243c`
- `0x180075d14`

## callees

- `0x18000506c`
- `0x180008be8`
- `0x18000968c`
- `0x180009e04`
- `0x18000a180`
- `0x18000a6bc`
- `0x18000e818`
- `0x180011bcc`
- `0x180015eb0`
- `0x1800168c0`
- `0x180016c60`
- `0x18001ebb8`
- `0x18001f0f0`
- `0x18001f19c`
- `0x18001f530`
- `0x18003d110`
- `0x18003d380`
- `0x180041d10`
- `0x1800587c8`
- `0x18005880c`
- `0x1800589fc`
- `0x180060b38`
- `0x180091ff0`

## string_xrefs

- `0x18001ec89`: `sqlite_temp_master`
- `0x18001ee1f`: `sqlite_temp_master`
- `0x18001f021`: `temporary table name must be unqualified`
- `0x18001f054`: `%s %T already exists`
- `0x18001f079`: `there is already an index named %s`

## pseudocode

```c
__int64 __fastcall sqlite3StartTable(__int64 *a1, _OWORD *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  __int64 v7; // rsi
  const char *v10; // r8
  _OWORD *v12; // r14
  char v13; // al
  unsigned int Db; // ebp
  bool v15; // zf
  __int64 result; // rax
  _BYTE *v17; // r15
  const char *v18; // rbx
  const char *v19; // r12
  const char *v20; // r8
  int v21; // edx
  const char *v22; // r8
  __int64 v23; // rcx
  __int64 Table; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  const char *v28; // rdx
  __int64 v29; // r9
  __int64 v30; // r14
  int v31; // r15d
  int v32; // r12d
  int v33; // ecx
  unsigned int v34; // ebx
  __int64 v35; // r8
  __int64 v36; // r9
  unsigned int v37; // eax
  int v38; // ecx
  __int64 v39; // [rsp+30h] [rbp-58h]
  __int64 v40; // [rsp+38h] [rbp-50h]
  int v41; // [rsp+90h] [rbp+8h]
  __int64 v42; // [rsp+90h] [rbp+8h]
  int v43; // [rsp+90h] [rbp+8h]

  v7 = *a1;
  v10 = "sqlite_master";
  v12 = a2;
  v13 = *(_BYTE *)(*a1 + 197);
  if ( v13 && *(_DWORD *)(v7 + 192) == 1 )
  {
    Db = *(unsigned __int8 *)(v7 + 196);
    v28 = "sqlite_temp_master";
    if ( Db != 1 )
      v28 = "sqlite_master";
    result = sqlite3DbStrDup(v7, v28);
    v18 = (const char *)result;
    v17 = (char *)a1 + 308;
  }
  else
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      if ( v13 )
        return sqlite3ErrorMsg(a1, "corrupt database", "sqlite_master");
      Db = sqlite3FindDb(v7, a2, "sqlite_master");
      if ( (Db & 0x80000000) != 0 )
        return sqlite3ErrorMsg(a1, "unknown database %T", v12);
      v12 = (_OWORD *)a3;
    }
    else
    {
      Db = *(unsigned __int8 *)(v7 + 196);
    }
    v15 = a4 == 0;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && Db != 1 )
        return sqlite3ErrorMsg(a1, "temporary table name must be unqualified", v10);
      v15 = a4 == 0;
    }
    if ( !v15 )
      Db = 1;
    result = sqlite3NameFromToken(v7, v12);
    v17 = (char *)a1 + 308;
    v18 = (const char *)result;
    if ( *((_BYTE *)a1 + 308) >= 2u )
      result = sqlite3RenameTokenMap(a1, result, v12);
  }
  *((_OWORD *)a1 + 17) = *v12;
  if ( v18 )
  {
    v19 = "view";
    v20 = "view";
    if ( !a5 )
      v20 = "table";
    if ( (unsigned int)sqlite3CheckObjectName(a1, v18, v20, v18) )
      goto LABEL_30;
    v21 = 1;
    v22 = "sqlite_temp_master";
    if ( *(_BYTE *)(v7 + 196) != 1 )
      v21 = a4;
    v23 = 32LL * Db;
    v41 = v21;
    v39 = v23;
    if ( v21 != 1 )
      v22 = "sqlite_master";
    v40 = *(_QWORD *)(v23 + *(_QWORD *)(v7 + 32));
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v22, 0, v40)
      || !a6
      && (unsigned int)sqlite3AuthCheck(
                         (_DWORD)a1,
                         *((unsigned __int8 *)&qword_1800B51C0 + 2 * a5 + v41),
                         (_DWORD)v18,
                         0,
                         v40) )
    {
      goto LABEL_30;
    }
    if ( !*v17 )
    {
      v42 = *(_QWORD *)(v39 + *(_QWORD *)(v7 + 32));
      if ( (unsigned int)sqlite3ReadSchema(a1) )
        goto LABEL_30;
      Table = sqlite3FindTable(v7, v18, v42);
      if ( Table )
      {
        if ( a7 )
        {
          sqlite3CodeVerifySchema(a1, Db);
          sqlite3ForceNotReadOnly(a1);
        }
        else
        {
          if ( *(_BYTE *)(Table + 63) != 2 )
            v19 = "table";
          sqlite3ErrorMsg(a1, "%s %T already exists", v19, v12);
        }
        goto LABEL_30;
      }
      if ( sqlite3FindIndex(v7, v18, v42) )
      {
        sqlite3ErrorMsg(a1, "there is already an index named %s", v18);
        goto LABEL_30;
      }
    }
    v25 = sqlite3DbMallocZero(v7, 104);
    v26 = v25;
    if ( v25 )
    {
      *(_QWORD *)v25 = v18;
      *(_WORD *)(v25 + 52) = -1;
      result = *(_QWORD *)(v7 + 32);
      v27 = *(_QWORD *)(v39 + result + 24);
      *(_DWORD *)(v26 + 44) = 1;
      *(_QWORD *)(v26 + 96) = v27;
      *(_WORD *)(v26 + 58) = 200;
      a1[44] = v26;
      if ( !*(_BYTE *)(v7 + 197) )
      {
        result = sqlite3GetVdbe(a1);
        v30 = result;
        if ( result )
        {
          sqlite3BeginWriteOperation(a1, 1, Db, v29);
          if ( a6 )
            sqlite3VdbeAddOp3(v30, 170, 0, 0, 0);
          v43 = *((_DWORD *)a1 + 14) + 1;
          *((_DWORD *)a1 + 34) = v43;
          v31 = v43 + 1;
          v32 = v43 + 2;
          *((_DWORD *)a1 + 35) = v43 + 1;
          *((_DWORD *)a1 + 14) = v43 + 2;
          sqlite3VdbeAddOp3(v30, 99, Db, v43 + 2, 2);
          sqlite3VdbeUsesBtree(v30, Db);
          v34 = sqlite3VdbeAddOp3(v33, 16, v43 + 2, 0, 0);
          sqlite3VdbeAddOp3(v30, 100, Db, 2, (*(_BYTE *)(v7 + 48) & 2) != 0 ? 1 : 4);
          sqlite3VdbeAddOp3(v30, 100, Db, 5, *(unsigned __int8 *)(v7 + 100));
          *(_DWORD *)(sqlite3VdbeGetOp(v30, v34, v35, v36) + 8) = *(_DWORD *)(v30 + 144);
          if ( a5 || a6 )
            sqlite3VdbeAddOp3(v30, 71, 0, v31, 0);
          else
            *((_DWORD *)a1 + 52) = sqlite3VdbeAddOp3(v30, 147, Db, v31, 1);
          sqlite3OpenSchemaTable(a1, Db);
          sqlite3VdbeAddOp3(v30, 127, 0, v43, 0);
          v37 = sqlite3VdbeAddOp3(v30, 77, 6, v32, 0);
          sqlite3VdbeChangeP4(v30, v37, &qword_1800B54D0, 0xFFFFFFFFLL);
          sqlite3VdbeAddOp3(v30, 128, 0, v32, v43);
          sqlite3VdbeChangeP5(v30, 8);
          return sqlite3VdbeAddOp3(v38, 122, 0, 0, 0);
        }
      }
      return result;
    }
    ++*((_DWORD *)a1 + 12);
    *((_DWORD *)a1 + 6) = 7;
LABEL_30:
    *((_BYTE *)a1 + 29) = 1;
    return sqlite3DbFree(v7, v18);
  }
  return result;
}

```

## disassembly

```asm
0x18001ebb8  push    rbx
0x18001ebba  push    rbp
0x18001ebbb  push    rsi
0x18001ebbc  push    rdi
0x18001ebbd  push    r12
0x18001ebbf  push    r13
0x18001ebc1  push    r14
0x18001ebc3  push    r15
0x18001ebc5  sub     rsp, 48h
0x18001ebc9  mov     rsi, [rcx]
0x18001ebcc  mov     rbx, r8
0x18001ebcf  mov     rdi, rcx
0x18001ebd2  lea     r8, aSqliteMaster; "sqlite_master"
0x18001ebd9  mov     r13d, r9d
0x18001ebdc  mov     r14, rdx
0x18001ebdf  mov     ecx, 1
0x18001ebe4  mov     al, [rsi+0C5h]
0x18001ebea  test    al, al
0x18001ebec  jz      short loc_18001EBFA
0x18001ebee  cmp     [rsi+0C0h], ecx
0x18001ebf4  jz      loc_18001EE18
0x18001ebfa  cmp     dword ptr [rbx+8], 0
0x18001ebfe  ja      loc_18001EFD8
0x18001ec04  movzx   ebp, byte ptr [rsi+0C4h]
0x18001ec0b  test    r13d, r13d
0x18001ec0e  jnz     loc_18001F017
0x18001ec14  cmovnz  ebp, ecx
0x18001ec17  mov     rdx, r14
0x18001ec1a  mov     rcx, rsi
0x18001ec1d  call    sqlite3NameFromToken
0x18001ec22  lea     r15, [rdi+134h]
0x18001ec29  mov     rbx, rax
0x18001ec2c  cmp     byte ptr [r15], 2
0x18001ec30  jnb     loc_18001F03D
0x18001ec36  movups  xmm0, xmmword ptr [r14]
0x18001ec3a  movdqu  xmmword ptr [rdi+110h], xmm0
0x18001ec42  test    rbx, rbx
0x18001ec45  jz      loc_18001EDD6
0x18001ec4b  cmp     [rsp+88h+arg_20], 0
0x18001ec53  lea     rax, aTable; "table"
0x18001ec5a  lea     r12, aView_0; "view"
0x18001ec61  mov     r9, rbx
0x18001ec64  mov     r8, r12
0x18001ec67  mov     rdx, rbx
0x18001ec6a  cmovz   r8, rax
0x18001ec6e  mov     rcx, rdi
0x18001ec71  call    sqlite3CheckObjectName
0x18001ec76  test    eax, eax
0x18001ec78  jnz     loc_18001EE07
0x18001ec7e  lea     edx, [rax+1]
0x18001ec81  mov     ecx, ebp
0x18001ec83  cmp     [rsi+0C4h], dl
0x18001ec89  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18001ec90  mov     rax, [rsi+20h]
0x18001ec94  cmovnz  edx, r13d
0x18001ec98  shl     rcx, 5
0x18001ec9c  cmp     edx, 1
0x18001ec9f  mov     dword ptr [rsp+88h+arg_0], edx
0x18001eca6  lea     rdx, aSqliteMaster; "sqlite_master"
0x18001ecad  mov     [rsp+88h+var_58], rcx
0x18001ecb2  cmovnz  r8, rdx
0x18001ecb6  xor     r9d, r9d
0x18001ecb9  mov     rcx, [rcx+rax]
0x18001ecbd  mov     [rsp+88h+var_50], rcx
0x18001ecc2  mov     [rsp+88h+var_68], rcx
0x18001ecc7  mov     rcx, rdi
0x18001ecca  lea     edx, [r9+12h]
0x18001ecce  call    sqlite3AuthCheck
0x18001ecd3  test    eax, eax
0x18001ecd5  jnz     loc_18001EE07
0x18001ecdb  mov     r13d, [rsp+88h+arg_28]
0x18001ece3  test    r13d, r13d
0x18001ece6  jnz     short loc_18001ED27
0x18001ece8  mov     eax, dword ptr [rsp+88h+arg_0]
0x18001ecef  xor     r9d, r9d
0x18001ecf2  mov     ecx, [rsp+88h+arg_20]
0x18001ecf9  mov     r8, rbx
0x18001ecfc  lea     eax, [rax+rcx*2]
0x18001ecff  movsxd  rcx, eax
0x18001ed02  lea     rax, qword_1800B51C0
0x18001ed09  movzx   edx, byte ptr [rcx+rax]
0x18001ed0d  mov     rcx, rdi
0x18001ed10  mov     rax, [rsp+88h+var_50]
0x18001ed15  mov     [rsp+88h+var_68], rax
0x18001ed1a  call    sqlite3AuthCheck
0x18001ed1f  test    eax, eax
0x18001ed21  jnz     loc_18001EE07
0x18001ed27  cmp     byte ptr [r15], 0
0x18001ed2b  mov     r15, [rsp+88h+var_58]
0x18001ed30  jnz     short loc_18001ED86
0x18001ed32  mov     rax, [rsi+20h]
0x18001ed36  mov     rcx, rdi
0x18001ed39  mov     rax, [r15+rax]
0x18001ed3d  mov     [rsp+88h+arg_0], rax
0x18001ed45  call    sqlite3ReadSchema
0x18001ed4a  test    eax, eax
0x18001ed4c  jnz     loc_18001EE07
0x18001ed52  mov     r8, [rsp+88h+arg_0]
0x18001ed5a  mov     rdx, rbx
0x18001ed5d  mov     rcx, rsi
0x18001ed60  call    sqlite3FindTable
0x18001ed65  test    rax, rax
0x18001ed68  jnz     short loc_18001EDE7
0x18001ed6a  mov     r8, [rsp+88h+arg_0]
0x18001ed72  mov     rdx, rbx
0x18001ed75  mov     rcx, rsi
0x18001ed78  call    sqlite3FindIndex
0x18001ed7d  test    rax, rax
0x18001ed80  jnz     loc_18001F076
0x18001ed86  mov     edx, 68h ; 'h'
0x18001ed8b  mov     rcx, rsi
0x18001ed8e  call    sqlite3DbMallocZero
0x18001ed93  mov     rdx, rax
0x18001ed96  test    rax, rax
0x18001ed99  jz      loc_18001F08D
0x18001ed9f  mov     [rax], rbx
0x18001eda2  xor     ebx, ebx
0x18001eda4  mov     word ptr [rax+34h], 0FFFFh
0x18001edaa  mov     rax, [rsi+20h]
0x18001edae  mov     rcx, [r15+rax+18h]
0x18001edb3  mov     r15d, 1
0x18001edb9  mov     [rdx+2Ch], r15d
0x18001edbd  mov     [rdx+60h], rcx
0x18001edc1  mov     word ptr [rdx+3Ah], 0C8h
0x18001edc7  mov     [rdi+160h], rdx
0x18001edce  cmp     [rsi+0C5h], bl
0x18001edd4  jz      short loc_18001EE43
0x18001edd6  add     rsp, 48h
0x18001edda  pop     r15
0x18001eddc  pop     r14
0x18001edde  pop     r13
0x18001ede0  pop     r12
0x18001ede2  pop     rdi
0x18001ede3  pop     rsi
0x18001ede4  pop     rbp
0x18001ede5  pop     rbx
0x18001ede6  retn
0x18001ede7  cmp     [rsp+88h+arg_30], 0
0x18001edef  mov     rcx, rdi
0x18001edf2  jz      loc_18001F050
0x18001edf8  mov     edx, ebp
0x18001edfa  call    sqlite3CodeVerifySchema
0x18001edff  mov     rcx, rdi
0x18001ee02  call    sqlite3ForceNotReadOnly
0x18001ee07  mov     rdx, rbx
0x18001ee0a  mov     byte ptr [rdi+1Dh], 1
0x18001ee0e  mov     rcx, rsi
0x18001ee11  call    sqlite3DbFree
0x18001ee16  jmp     short loc_18001EDD6
0x18001ee18  movzx   ebp, byte ptr [rsi+0C4h]
0x18001ee1f  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x18001ee26  cmp     ebp, ecx
0x18001ee28  mov     rcx, rsi
0x18001ee2b  cmovnz  rdx, r8
0x18001ee2f  call    sqlite3DbStrDup
0x18001ee34  mov     rbx, rax
0x18001ee37  lea     r15, [rdi+134h]
0x18001ee3e  jmp     loc_18001EC36
0x18001ee43  mov     rcx, rdi
0x18001ee46  call    sqlite3GetVdbe
0x18001ee4b  mov     r14, rax
0x18001ee4e  test    rax, rax
0x18001ee51  jz      short loc_18001EDD6
0x18001ee53  mov     r8d, ebp
0x18001ee56  mov     edx, r15d
0x18001ee59  mov     rcx, rdi
0x18001ee5c  call    sqlite3BeginWriteOperation
0x18001ee61  test    r13d, r13d
0x18001ee64  jnz     loc_18001F09C
0x18001ee6a  mov     eax, [rdi+38h]
0x18001ee6d  mov     r8d, ebp
0x18001ee70  inc     eax
0x18001ee72  mov     dword ptr [rsp+88h+var_68], 2
0x18001ee7a  mov     edx, 63h ; 'c'
0x18001ee7f  mov     dword ptr [rsp+88h+arg_0], eax
0x18001ee86  mov     rcx, r14
0x18001ee89  mov     [rdi+88h], eax
0x18001ee8f  lea     r15d, [rax+1]
0x18001ee93  lea     r12d, [r15+1]
0x18001ee97  mov     [rdi+8Ch], r15d
0x18001ee9e  mov     r9d, r12d
0x18001eea1  mov     [rdi+38h], r12d
0x18001eea5  call    sqlite3VdbeAddOp3
0x18001eeaa  mov     edx, ebp
0x18001eeac  mov     rcx, r14
0x18001eeaf  call    sqlite3VdbeUsesBtree
0x18001eeb4  xor     r9d, r9d
0x18001eeb7  mov     dword ptr [rsp+88h+var_68], ebx
0x18001eebb  mov     r8d, r12d
0x18001eebe  lea     edx, [r9+10h]
0x18001eec2  call    sqlite3VdbeAddOp3
0x18001eec7  mov     cl, [rsi+30h]
0x18001eeca  mov     r9d, 2
0x18001eed0  and     cl, 2
0x18001eed3  mov     r8d, ebp
0x18001eed6  neg     cl
0x18001eed8  mov     ebx, eax
0x18001eeda  mov     rcx, r14
0x18001eedd  sbb     edx, edx
0x18001eedf  and     edx, 0FFFFFFFDh
0x18001eee2  add     edx, 4
0x18001eee5  mov     dword ptr [rsp+88h+var_68], edx
0x18001eee9  lea     edx, [r9+62h]
0x18001eeed  call    sqlite3VdbeAddOp3
0x18001eef2  movzx   eax, byte ptr [rsi+64h]
0x18001eef6  mov     r9d, 5
0x18001eefc  mov     r8d, ebp
0x18001eeff  mov     dword ptr [rsp+88h+var_68], eax
0x18001ef03  mov     rcx, r14
0x18001ef06  lea     edx, [r9+5Fh]
0x18001ef0a  call    sqlite3VdbeAddOp3
0x18001ef0f  mov     edx, ebx
0x18001ef11  mov     rcx, r14
0x18001ef14  call    sqlite3VdbeGetOp
0x18001ef19  mov     ecx, [r14+90h]
0x18001ef20  xor     esi, esi
0x18001ef22  mov     [rax+8], ecx
0x18001ef25  cmp     [rsp+88h+arg_20], esi
0x18001ef2c  jz      loc_18001F0B8
0x18001ef32  xor     r8d, r8d
0x18001ef35  mov     dword ptr [rsp+88h+var_68], esi
0x18001ef39  mov     r9d, r15d
0x18001ef3c  mov     rcx, r14
0x18001ef3f  lea     edx, [r8+47h]
0x18001ef43  call    sqlite3VdbeAddOp3
0x18001ef48  mov     edx, ebp
0x18001ef4a  mov     rcx, rdi
0x18001ef4d  call    sqlite3OpenSchemaTable
0x18001ef52  mov     ebx, dword ptr [rsp+88h+arg_0]
0x18001ef59  xor     r8d, r8d
0x18001ef5c  mov     r9d, ebx
0x18001ef5f  mov     dword ptr [rsp+88h+var_68], esi
0x18001ef63  mov     rcx, r14
0x18001ef66  lea     edx, [r8+7Fh]
0x18001ef6a  call    sqlite3VdbeAddOp3
0x18001ef6f  mov     edx, 4Dh ; 'M'
0x18001ef74  mov     dword ptr [rsp+88h+var_68], esi
0x18001ef78  mov     r9d, r12d
0x18001ef7b  mov     rcx, r14
0x18001ef7e  lea     r8d, [rdx-47h]
0x18001ef82  call    sqlite3VdbeAddOp3
0x18001ef87  or      r9d, 0FFFFFFFFh
0x18001ef8b  lea     r8, qword_1800B54D0
0x18001ef92  mov     edx, eax
0x18001ef94  mov     rcx, r14
0x18001ef97  call    sqlite3VdbeChangeP4
0x18001ef9c  mov     r9d, r12d
0x18001ef9f  mov     dword ptr [rsp+88h+var_68], ebx
0x18001efa3  xor     r8d, r8d
0x18001efa6  mov     edx, 80h
0x18001efab  mov     rcx, r14
0x18001efae  call    sqlite3VdbeAddOp3
0x18001efb3  mov     edx, 8
0x18001efb8  mov     rcx, r14
0x18001efbb  call    sqlite3VdbeChangeP5
0x18001efc0  xor     r9d, r9d
0x18001efc3  mov     dword ptr [rsp+88h+var_68], esi
0x18001efc7  xor     r8d, r8d
0x18001efca  lea     edx, [r9+7Ah]
0x18001efce  call    sqlite3VdbeAddOp3
0x18001efd3  jmp     loc_18001EDD6
0x18001efd8  test    al, al
0x18001efda  jz      short loc_18001EFE5
0x18001efdc  lea     rdx, aCorruptDatabas; "corrupt database"
0x18001efe3  jmp     short loc_18001F028
0x18001efe5  mov     rcx, rsi
0x18001efe8  call    sqlite3FindDb
0x18001efed  mov     ebp, eax
0x18001efef  test    eax, eax
0x18001eff1  jns     short loc_18001F00A
0x18001eff3  mov     r8, r14
0x18001eff6  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x18001effd  mov     rcx, rdi
0x18001f000  call    sqlite3ErrorMsg
0x18001f005  jmp     loc_18001EDD6
0x18001f00a  mov     r14, rbx
0x18001f00d  mov     ecx, 1
0x18001f012  jmp     loc_18001EC0B
0x18001f017  cmp     dword ptr [rbx+8], 0
0x18001f01b  jbe     short loc_18001F035
0x18001f01d  cmp     ebp, ecx
0x18001f01f  jz      short loc_18001F035
0x18001f021  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x18001f028  mov     rcx, rdi
0x18001f02b  call    sqlite3ErrorMsg
0x18001f030  jmp     loc_18001EDD6
0x18001f035  test    r13d, r13d
0x18001f038  jmp     loc_18001EC14
0x18001f03d  mov     r8, r14
0x18001f040  mov     rdx, rax
0x18001f043  mov     rcx, rdi
0x18001f046  call    sqlite3RenameTokenMap
0x18001f04b  jmp     loc_18001EC36
0x18001f050  cmp     byte ptr [rax+3Fh], 2
0x18001f054  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x18001f05b  lea     rax, aTable; "table"
0x18001f062  mov     r9, r14
0x18001f065  cmovnz  r12, rax
0x18001f069  mov     r8, r12
0x18001f06c  call    sqlite3ErrorMsg
  ... truncated ...
```

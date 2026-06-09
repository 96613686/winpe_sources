# sqlite3DropTable

- ea: `0x18010a370`
- end: `0x18010a61e`
- name: `sqlite3DropTable`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180174050`

## callees

- `0x1800fdf90`
- `0x1800ff2c0`
- `0x180103370`
- `0x180103c20`
- `0x180104f10`
- `0x18010a370`
- `0x18010b290`
- `0x1801144d0`
- `0x180114d60`
- `0x18011d960`
- `0x180128f40`
- `0x180130eb0`
- `0x180138140`
- `0x18015abd0`
- `0x180162150`

## string_xrefs

- `0x18010a449`: `sqlite_temp_master`
- `0x18010a55a`: `use DROP TABLE to delete table %s`
- `0x18010a575`: `use DROP VIEW to delete view %s`

## pseudocode

```c
__int64 __fastcall sqlite3DropTable(__int64 *a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v4; // rbp
  __int64 v9; // r8
  __int64 TableItem; // rax
  __int64 v11; // r14
  const char **v12; // rsi
  __int64 v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // r12
  _QWORD *i; // rax
  const char *v17; // r8
  int j; // edx
  _QWORD *v19; // rax
  char v20; // al
  __int64 v22; // [rsp+60h] [rbp+8h]

  v4 = *a1;
  if ( !*(_BYTE *)(*a1 + 103) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    v9 = a2 + 8;
    if ( a4 )
    {
      ++*(_BYTE *)(v4 + 107);
      TableItem = sqlite3LocateTableItem(a1, a3, v9);
      --*(_BYTE *)(v4 + 107);
    }
    else
    {
      TableItem = sqlite3LocateTableItem(a1, a3, v9);
    }
    v11 = TableItem;
    v12 = (const char **)TableItem;
    if ( TableItem )
    {
      v13 = *(_QWORD *)(TableItem + 96);
      v14 = -32768;
      LODWORD(v15) = 0;
      if ( v13 )
      {
        v14 = 0;
        for ( i = (_QWORD *)(*(_QWORD *)(v4 + 32) + 24LL); *i != v13; i += 4 )
          ++v14;
      }
      if ( *(_BYTE *)(v11 + 63) != 1 || !(unsigned int)viewGetColumnNames(a1, v11) )
      {
        v17 = "sqlite_temp_master";
        if ( v14 != 1 )
          v17 = "sqlite_master";
        v22 = *(_QWORD *)(32LL * (int)v14 + *(_QWORD *)(v4 + 32));
        if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v17, 0, v22) )
        {
          if ( a3 )
          {
            j = 15;
            if ( v14 != 1 )
              j = 17;
          }
          else if ( *(_BYTE *)(v11 + 63) == 1 )
          {
            v19 = *(_QWORD **)(v11 + 80);
            for ( j = 30; v19; v19 = (_QWORD *)v19[5] )
            {
              if ( *v19 == v4 )
                break;
            }
            v15 = *(_QWORD *)(v19[1] + 8LL);
          }
          else
          {
            j = 11;
            if ( v14 == 1 )
              j = 13;
          }
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, j, (unsigned int)*v12, v15, v22)
            && !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (unsigned int)*v12, 0, v22) )
          {
            if ( (unsigned int)tableMayNotBeDropped(v4, v11) )
            {
              sqlite3ErrorMsg(a1, "table %s may not be dropped", *v12);
            }
            else
            {
              v20 = *((_BYTE *)v12 + 63);
              if ( a3 )
              {
                if ( v20 != 2 )
                {
                  sqlite3ErrorMsg(a1, "use DROP TABLE to delete table %s", *v12);
                  return sqlite3SrcListDelete(v4, a2);
                }
              }
              else if ( v20 == 2 )
              {
                sqlite3ErrorMsg(a1, "use DROP VIEW to delete view %s", *v12);
                return sqlite3SrcListDelete(v4, a2);
              }
              if ( a1[2] )
                goto LABEL_42;
              if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
                *((_BYTE *)a1 + 35) = 1;
              if ( sqlite3VdbeCreate(a1) )
              {
LABEL_42:
                sqlite3BeginWriteOperation(a1, 1, v14);
                if ( !a3 )
                {
                  sqlite3ClearStatTables(a1, v14, "tbl", *v12);
                  sqlite3FkDropTable(a1, a2, v11);
                }
                sqlite3CodeDropTable(a1, v11, v14, a3);
              }
            }
          }
        }
      }
    }
    else if ( a4 )
    {
      sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 16));
      sqlite3ForceNotReadOnly(a1);
    }
  }
  return sqlite3SrcListDelete(v4, a2);
}

```

## disassembly

```asm
0x18010a370  push    rbx
0x18010a372  push    rbp
0x18010a373  push    rdi
0x18010a374  push    r13
0x18010a376  push    r15
0x18010a378  sub     rsp, 30h
0x18010a37c  mov     rbp, [rcx]
0x18010a37f  mov     edi, r9d
0x18010a382  mov     r15d, r8d
0x18010a385  mov     r13, rdx
0x18010a388  mov     rbx, rcx
0x18010a38b  cmp     byte ptr [rbp+67h], 0
0x18010a38f  jnz     loc_18010A608
0x18010a395  call    sqlite3ReadSchema
0x18010a39a  test    eax, eax
0x18010a39c  jnz     loc_18010A608
0x18010a3a2  mov     [rsp+58h+arg_8], rsi
0x18010a3a7  lea     r8, [r13+8]
0x18010a3ab  mov     [rsp+58h+arg_18], r14
0x18010a3b0  mov     edx, r15d
0x18010a3b3  mov     rcx, rbx
0x18010a3b6  test    edi, edi
0x18010a3b8  jz      short loc_18010A3C7
0x18010a3ba  inc     byte ptr [rbp+6Bh]
0x18010a3bd  call    sqlite3LocateTableItem
0x18010a3c2  dec     byte ptr [rbp+6Bh]
0x18010a3c5  jmp     short loc_18010A3CC
0x18010a3c7  call    sqlite3LocateTableItem
0x18010a3cc  mov     r14, rax
0x18010a3cf  mov     rsi, rax
0x18010a3d2  test    rax, rax
0x18010a3d5  jnz     short loc_18010A3F8
0x18010a3d7  test    edi, edi
0x18010a3d9  jz      loc_18010A5FE
0x18010a3df  mov     rdx, [r13+10h]
0x18010a3e3  mov     rcx, rbx
0x18010a3e6  call    sqlite3CodeVerifyNamedSchema
0x18010a3eb  mov     rcx, rbx
0x18010a3ee  call    sqlite3ForceNotReadOnly
0x18010a3f3  jmp     loc_18010A5FE
0x18010a3f8  mov     rcx, [rsi+60h]
0x18010a3fc  mov     edi, 0FFFF8000h
0x18010a401  mov     [rsp+58h+arg_10], r12
0x18010a406  xor     r12d, r12d
0x18010a409  test    rcx, rcx
0x18010a40c  jz      short loc_18010A42B
0x18010a40e  mov     rax, [rbp+20h]
0x18010a412  mov     edi, r12d
0x18010a415  add     rax, 18h
0x18010a419  cmp     [rax], rcx
0x18010a41c  jz      short loc_18010A42B
0x18010a41e  xchg    ax, ax
0x18010a420  inc     edi
0x18010a422  lea     rax, [rax+20h]
0x18010a426  cmp     [rax], rcx
0x18010a429  jnz     short loc_18010A420
0x18010a42b  cmp     byte ptr [r14+3Fh], 1
0x18010a430  jnz     short loc_18010A445
0x18010a432  mov     rdx, r14
0x18010a435  mov     rcx, rbx
0x18010a438  call    viewGetColumnNames
0x18010a43d  test    eax, eax
0x18010a43f  jnz     loc_18010A5F9
0x18010a445  mov     rax, [rbp+20h]
0x18010a449  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18010a450  movsxd  rcx, edi
0x18010a453  mov     edx, 9
0x18010a458  shl     rcx, 5
0x18010a45c  cmp     edi, 1
0x18010a45f  mov     rax, [rcx+rax]
0x18010a463  lea     rcx, aSqliteMaster; "sqlite_master"
0x18010a46a  cmovnz  r8, rcx
0x18010a46e  mov     [rsp+58h+arg_0], rax
0x18010a473  xor     r9d, r9d
0x18010a476  mov     [rsp+58h+var_38], rax
0x18010a47b  mov     rcx, rbx
0x18010a47e  call    sqlite3AuthCheck
0x18010a483  test    eax, eax
0x18010a485  jnz     loc_18010A5F9
0x18010a48b  test    r15d, r15d
0x18010a48e  jz      short loc_18010A4A2
0x18010a490  cmp     edi, 1
0x18010a493  mov     edx, 0Fh
0x18010a498  mov     eax, 11h
0x18010a49d  cmovnz  edx, eax
0x18010a4a0  jmp     short loc_18010A4DF
0x18010a4a2  cmp     byte ptr [r14+3Fh], 1
0x18010a4a7  jnz     short loc_18010A4CF
0x18010a4a9  mov     rax, [r14+50h]
0x18010a4ad  mov     edx, 1Eh
0x18010a4b2  test    rax, rax
0x18010a4b5  jz      short loc_18010A4C5
0x18010a4b7  cmp     [rax], rbp
0x18010a4ba  jz      short loc_18010A4C5
0x18010a4bc  mov     rax, [rax+28h]
0x18010a4c0  test    rax, rax
0x18010a4c3  jnz     short loc_18010A4B7
0x18010a4c5  mov     rax, [rax+8]
0x18010a4c9  mov     r12, [rax+8]
0x18010a4cd  jmp     short loc_18010A4DF
0x18010a4cf  cmp     edi, 1
0x18010a4d2  mov     edx, 0Bh
0x18010a4d7  mov     eax, 0Dh
0x18010a4dc  cmovz   edx, eax
0x18010a4df  mov     rax, [rsp+58h+arg_0]
0x18010a4e4  mov     r9, r12
0x18010a4e7  mov     r8, [rsi]
0x18010a4ea  mov     rcx, rbx
0x18010a4ed  mov     [rsp+58h+var_38], rax
0x18010a4f2  call    sqlite3AuthCheck
0x18010a4f7  test    eax, eax
0x18010a4f9  jnz     loc_18010A5F9
0x18010a4ff  mov     rax, [rsp+58h+arg_0]
0x18010a504  xor     r9d, r9d
0x18010a507  mov     r8, [rsi]
0x18010a50a  mov     edx, 9
0x18010a50f  mov     rcx, rbx
0x18010a512  mov     [rsp+58h+var_38], rax
0x18010a517  call    sqlite3AuthCheck
0x18010a51c  test    eax, eax
0x18010a51e  jnz     loc_18010A5F9
0x18010a524  mov     rdx, r14
0x18010a527  mov     rcx, rbp
0x18010a52a  call    tableMayNotBeDropped
0x18010a52f  test    eax, eax
0x18010a531  jz      short loc_18010A54A
0x18010a533  mov     r8, [rsi]
0x18010a536  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x18010a53d  mov     rcx, rbx
0x18010a540  call    sqlite3ErrorMsg
0x18010a545  jmp     loc_18010A5F9
0x18010a54a  movzx   eax, byte ptr [rsi+3Fh]
0x18010a54e  test    r15d, r15d
0x18010a551  jz      short loc_18010A56E
0x18010a553  cmp     al, 2
0x18010a555  jz      short loc_18010A586
0x18010a557  mov     r8, [rsi]
0x18010a55a  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x18010a561  mov     rcx, rbx
0x18010a564  call    sqlite3ErrorMsg
0x18010a569  jmp     loc_18010A5F9
0x18010a56e  cmp     al, 2
0x18010a570  jnz     short loc_18010A586
0x18010a572  mov     r8, [rsi]
0x18010a575  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x18010a57c  mov     rcx, rbx
0x18010a57f  call    sqlite3ErrorMsg
0x18010a584  jmp     short loc_18010A5F9
0x18010a586  cmp     qword ptr [rbx+10h], 0
0x18010a58b  jnz     short loc_18010A5B1
0x18010a58d  cmp     qword ptr [rbx+0A8h], 0
0x18010a595  jnz     short loc_18010A5A4
0x18010a597  mov     rax, [rbx]
0x18010a59a  test    byte ptr [rax+60h], 8
0x18010a59e  jnz     short loc_18010A5A4
0x18010a5a0  mov     byte ptr [rbx+23h], 1
0x18010a5a4  mov     rcx, rbx
0x18010a5a7  call    sqlite3VdbeCreate
0x18010a5ac  test    rax, rax
0x18010a5af  jz      short loc_18010A5F9
0x18010a5b1  mov     r8d, edi
0x18010a5b4  mov     edx, 1
0x18010a5b9  mov     rcx, rbx
0x18010a5bc  call    sqlite3BeginWriteOperation
0x18010a5c1  test    r15d, r15d
0x18010a5c4  jnz     short loc_18010A5E8
0x18010a5c6  mov     r9, [rsi]
0x18010a5c9  lea     r8, aTbl; "tbl"
0x18010a5d0  mov     edx, edi
0x18010a5d2  mov     rcx, rbx
0x18010a5d5  call    sqlite3ClearStatTables
0x18010a5da  mov     r8, r14
0x18010a5dd  mov     rdx, r13
0x18010a5e0  mov     rcx, rbx
0x18010a5e3  call    sqlite3FkDropTable
0x18010a5e8  mov     r9d, r15d
0x18010a5eb  mov     r8d, edi
0x18010a5ee  mov     rdx, r14
0x18010a5f1  mov     rcx, rbx
0x18010a5f4  call    sqlite3CodeDropTable
0x18010a5f9  mov     r12, [rsp+58h+arg_10]
0x18010a5fe  mov     r14, [rsp+58h+arg_18]
0x18010a603  mov     rsi, [rsp+58h+arg_8]
0x18010a608  mov     rdx, r13
0x18010a60b  mov     rcx, rbp
0x18010a60e  add     rsp, 30h
0x18010a612  pop     r15
0x18010a614  pop     r13
0x18010a616  pop     rdi
0x18010a617  pop     rbp
0x18010a618  pop     rbx
0x18010a619  jmp     sqlite3SrcListDelete
```

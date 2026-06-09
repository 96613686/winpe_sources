# sqlite3DropTable

- ea: `0x18004a49c`
- end: `0x18004a6d2`
- name: `sqlite3DropTable`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x18000213c`

## callees

- `0x1800087d0`
- `0x180009e04`
- `0x180009fe0`
- `0x18000a6bc`
- `0x18000a754`
- `0x180011bcc`
- `0x180015eb0`
- `0x18001f0f0`
- `0x18001f418`
- `0x18004a49c`
- `0x18004a6d8`
- `0x18004a7fc`
- `0x18004ad90`
- `0x18004aec8`
- `0x180060b38`
- `0x1800619e8`
- `0x180090ffc`

## string_xrefs

- `0x18004a517`: `sqlite_temp_master`
- `0x18004a6c0`: `use DROP TABLE to delete table %s`
- `0x18004a6c9`: `use DROP VIEW to delete view %s`

## pseudocode

```c
__int64 __fastcall sqlite3DropTable(__int64 *a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v4; // rsi
  __int64 TableItem; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rbp
  const char *v12; // r8
  __int64 v13; // r12
  __int64 v14; // r9
  int v15; // r10d
  __int64 v16; // r9

  v4 = *a1;
  if ( !*(_BYTE *)(*a1 + 103) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    if ( a4 )
      ++*(_BYTE *)(v4 + 107);
    TableItem = sqlite3LocateTableItem(a1, a3, a2 + 8);
    v10 = (_QWORD *)TableItem;
    if ( a4 )
      --*(_BYTE *)(v4 + 107);
    if ( TableItem )
    {
      v11 = (int)sqlite3SchemaToIndex(v4, *(_QWORD *)(TableItem + 96));
      if ( *((_BYTE *)v10 + 63) != 1 || !(unsigned int)sqlite3ViewGetColumnNames(a1, v10) )
      {
        v12 = "sqlite_temp_master";
        v13 = *(_QWORD *)(32 * v11 + *(_QWORD *)(v4 + 32));
        if ( (_DWORD)v11 != 1 )
          v12 = "sqlite_master";
        if ( !(unsigned int)sqlite3AuthCheck(
                              (_DWORD)a1,
                              9,
                              (_DWORD)v12,
                              0,
                              *(_QWORD *)(32 * v11 + *(_QWORD *)(v4 + 32))) )
        {
          LODWORD(v14) = 0;
          if ( a3 )
          {
            v15 = 15;
            if ( (_DWORD)v11 != 1 )
              v15 = 17;
          }
          else if ( *((_BYTE *)v10 + 63) == 1 )
          {
            v14 = *(_QWORD *)(*(_QWORD *)(sqlite3GetVTable(v4, v10) + 8) + 8LL);
          }
          else
          {
            v15 = 11;
            if ( (_DWORD)v11 == 1 )
              v15 = 13;
          }
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v15, *v10, v14, v13)
            && !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, *v10, 0, v13) )
          {
            if ( (unsigned int)tableMayNotBeDropped(v4, v10) )
            {
              sqlite3ErrorMsg(a1, "table %s may not be dropped", *v10);
            }
            else
            {
              if ( a3 )
              {
                if ( *((_BYTE *)v10 + 63) != 2 )
                {
                  sqlite3ErrorMsg(a1, "use DROP TABLE to delete table %s", *v10);
                  return sqlite3SrcListDelete(v4, a2);
                }
              }
              else if ( *((_BYTE *)v10 + 63) == 2 )
              {
                sqlite3ErrorMsg(a1, "use DROP VIEW to delete view %s", *v10);
                return sqlite3SrcListDelete(v4, a2);
              }
              if ( sqlite3GetVdbe(a1) )
              {
                sqlite3BeginWriteOperation(a1, 1, (unsigned int)v11, v16);
                if ( !a3 )
                {
                  sqlite3ClearStatTables(a1, (unsigned int)v11, "tbl", *v10);
                  sqlite3FkDropTable(a1, a2, v10);
                }
                sqlite3CodeDropTable(a1, v10, (unsigned int)v11, a3);
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
0x18004a49c  push    rbx
0x18004a49e  push    rbp
0x18004a49f  push    rsi
0x18004a4a0  push    rdi
0x18004a4a1  push    r12
0x18004a4a3  push    r14
0x18004a4a5  push    r15
0x18004a4a7  sub     rsp, 30h
0x18004a4ab  mov     rsi, [rcx]
0x18004a4ae  mov     ebp, r9d
0x18004a4b1  mov     r14d, r8d
0x18004a4b4  mov     r15, rdx
0x18004a4b7  mov     rbx, rcx
0x18004a4ba  cmp     byte ptr [rsi+67h], 0
0x18004a4be  jnz     loc_18004A628
0x18004a4c4  call    sqlite3ReadSchema
0x18004a4c9  test    eax, eax
0x18004a4cb  jnz     loc_18004A628
0x18004a4d1  test    ebp, ebp
0x18004a4d3  jz      short loc_18004A4D8
0x18004a4d5  inc     byte ptr [rsi+6Bh]
0x18004a4d8  lea     r8, [r15+8]
0x18004a4dc  mov     edx, r14d
0x18004a4df  mov     rcx, rbx
0x18004a4e2  call    sqlite3LocateTableItem
0x18004a4e7  mov     rdi, rax
0x18004a4ea  test    ebp, ebp
0x18004a4ec  jz      short loc_18004A4F1
0x18004a4ee  dec     byte ptr [rsi+6Bh]
0x18004a4f1  test    rdi, rdi
0x18004a4f4  jz      loc_18004A66A
0x18004a4fa  mov     rdx, [rax+60h]
0x18004a4fe  mov     rcx, rsi
0x18004a501  call    sqlite3SchemaToIndex
0x18004a506  cmp     byte ptr [rdi+3Fh], 1
0x18004a50a  movsxd  rbp, eax
0x18004a50d  jz      loc_18004A684
0x18004a513  mov     rax, [rsi+20h]
0x18004a517  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18004a51e  mov     rcx, rbp
0x18004a521  shl     rcx, 5
0x18004a525  cmp     ebp, 1
0x18004a528  mov     r12, [rcx+rax]
0x18004a52c  lea     rax, aSqliteMaster; "sqlite_master"
0x18004a533  cmovnz  r8, rax
0x18004a537  mov     [rsp+68h+var_48], r12
0x18004a53c  xor     r9d, r9d
0x18004a53f  mov     rcx, rbx
0x18004a542  lea     edx, [r9+9]
0x18004a546  call    sqlite3AuthCheck
0x18004a54b  test    eax, eax
0x18004a54d  jnz     loc_18004A628
0x18004a553  xor     r9d, r9d
0x18004a556  test    r14d, r14d
0x18004a559  jnz     loc_18004A641
0x18004a55f  cmp     byte ptr [rdi+3Fh], 1
0x18004a563  jz      loc_18004A698
0x18004a569  cmp     ebp, 1
0x18004a56c  lea     eax, [r9+0Dh]
0x18004a570  lea     r10d, [r9+0Bh]
0x18004a574  cmovz   r10d, eax
0x18004a578  mov     r8, [rdi]
0x18004a57b  mov     edx, r10d
0x18004a57e  mov     rcx, rbx
0x18004a581  mov     [rsp+68h+var_48], r12
0x18004a586  call    sqlite3AuthCheck
0x18004a58b  test    eax, eax
0x18004a58d  jnz     loc_18004A628
0x18004a593  mov     r8, [rdi]
0x18004a596  lea     edx, [rax+9]
0x18004a599  xor     r9d, r9d
0x18004a59c  mov     [rsp+68h+var_48], r12
0x18004a5a1  mov     rcx, rbx
0x18004a5a4  call    sqlite3AuthCheck
0x18004a5a9  test    eax, eax
0x18004a5ab  jnz     short loc_18004A628
0x18004a5ad  mov     rdx, rdi
0x18004a5b0  mov     rcx, rsi
0x18004a5b3  call    tableMayNotBeDropped
0x18004a5b8  test    eax, eax
0x18004a5ba  jnz     loc_18004A656
0x18004a5c0  test    r14d, r14d
0x18004a5c3  jnz     loc_18004A6B6
0x18004a5c9  cmp     byte ptr [rdi+3Fh], 2
0x18004a5cd  jz      loc_18004A6C9
0x18004a5d3  mov     rcx, rbx
0x18004a5d6  call    sqlite3GetVdbe
0x18004a5db  test    rax, rax
0x18004a5de  jz      short loc_18004A628
0x18004a5e0  mov     r8d, ebp
0x18004a5e3  mov     edx, 1
0x18004a5e8  mov     rcx, rbx
0x18004a5eb  call    sqlite3BeginWriteOperation
0x18004a5f0  test    r14d, r14d
0x18004a5f3  jnz     short loc_18004A617
0x18004a5f5  mov     r9, [rdi]
0x18004a5f8  lea     r8, aTbl; "tbl"
0x18004a5ff  mov     edx, ebp
0x18004a601  mov     rcx, rbx
0x18004a604  call    sqlite3ClearStatTables
0x18004a609  mov     r8, rdi
0x18004a60c  mov     rdx, r15
0x18004a60f  mov     rcx, rbx
0x18004a612  call    sqlite3FkDropTable
0x18004a617  mov     r9d, r14d
0x18004a61a  mov     r8d, ebp
0x18004a61d  mov     rdx, rdi
0x18004a620  mov     rcx, rbx
0x18004a623  call    sqlite3CodeDropTable
0x18004a628  mov     rdx, r15
0x18004a62b  mov     rcx, rsi
0x18004a62e  add     rsp, 30h
0x18004a632  pop     r15
0x18004a634  pop     r14
0x18004a636  pop     r12
0x18004a638  pop     rdi
0x18004a639  pop     rsi
0x18004a63a  pop     rbp
0x18004a63b  pop     rbx
0x18004a63c  jmp     sqlite3SrcListDelete
0x18004a641  mov     eax, 11h
0x18004a646  cmp     ebp, 1
0x18004a649  lea     r10d, [rax-2]
0x18004a64d  cmovnz  r10d, eax
0x18004a651  jmp     loc_18004A578
0x18004a656  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x18004a65d  mov     r8, [rdi]
0x18004a660  mov     rcx, rbx
0x18004a663  call    sqlite3ErrorMsg
0x18004a668  jmp     short loc_18004A628
0x18004a66a  test    ebp, ebp
0x18004a66c  jz      short loc_18004A628
0x18004a66e  mov     rdx, [r15+10h]
0x18004a672  mov     rcx, rbx
0x18004a675  call    sqlite3CodeVerifyNamedSchema
0x18004a67a  mov     rcx, rbx
0x18004a67d  call    sqlite3ForceNotReadOnly
0x18004a682  jmp     short loc_18004A628
0x18004a684  mov     rdx, rdi
0x18004a687  mov     rcx, rbx
0x18004a68a  call    sqlite3ViewGetColumnNames
0x18004a68f  test    eax, eax
0x18004a691  jnz     short loc_18004A628
0x18004a693  jmp     loc_18004A513
0x18004a698  mov     rdx, rdi
0x18004a69b  mov     rcx, rsi
0x18004a69e  mov     r10d, 1Eh
0x18004a6a4  call    sqlite3GetVTable
0x18004a6a9  mov     rcx, [rax+8]
0x18004a6ad  mov     r9, [rcx+8]
0x18004a6b1  jmp     loc_18004A578
0x18004a6b6  cmp     byte ptr [rdi+3Fh], 2
0x18004a6ba  jz      loc_18004A5D3
0x18004a6c0  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x18004a6c7  jmp     short loc_18004A65D
0x18004a6c9  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x18004a6d0  jmp     short loc_18004A65D
```

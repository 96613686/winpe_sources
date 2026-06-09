# sqlite3AlterRenameColumn

- ea: `0x1800809a0`
- end: `0x180080c00`
- name: `sqlite3AlterRenameColumn`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x180031b38`

## callees

- `0x18000a9e0`
- `0x18000ca30`
- `0x18000fd7c`
- `0x180013bc0`
- `0x1800143f0`
- `0x1800398f0`
- `0x18003f6dc`
- `0x180060ce8`
- `0x18007222c`
- `0x180072788`
- `0x18007e02c`
- `0x18007e1ac`
- `0x18007ea64`
- `0x1800809a0`
- `0x1800857c4`

## string_xrefs

- `0x180080bad`: `after rename`
- `0x180080b3e`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x180080b71`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int8 **a4)
{
  __int64 v4; // rbp
  __int64 v7; // r15
  __int64 v8; // r12
  __int64 TableItem; // rax
  _QWORD *v10; // rsi
  __int64 v11; // r13
  int v12; // r11d
  __int64 v13; // r14
  __int64 v14; // r8
  _QWORD *v15; // rcx
  int v16; // ebx
  __int64 v18; // [rsp+20h] [rbp-78h]
  __int64 v19; // [rsp+30h] [rbp-68h]
  unsigned int v20; // [rsp+A0h] [rbp+8h]

  v4 = *a1;
  v7 = 0;
  v8 = 0;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v10 = (_QWORD *)TableItem;
  if ( TableItem )
  {
    if ( !(unsigned int)isAlterableTable(a1, TableItem) && !(unsigned int)isRealTable(a1, v10, 0) )
    {
      v20 = sqlite3SchemaToIndex(v4, v10[12]);
      v11 = *(_QWORD *)(32LL * (int)v20 + *(_QWORD *)(v4 + 32));
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v11, *v10, 0) )
      {
        v7 = sqlite3NameFromToken(v4, a3);
        if ( v7 )
        {
          v12 = *((__int16 *)v10 + 27);
          v13 = 0;
          if ( v12 <= 0 )
          {
LABEL_10:
            if ( (_DWORD)v13 == v12 )
            {
              sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
              goto LABEL_16;
            }
          }
          else
          {
            v14 = v10[1];
            while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v14 + 24 * v13), v7) )
            {
              v14 = v10[1];
              v13 = (unsigned int)(v13 + 1);
              if ( (int)v13 >= v12 )
                goto LABEL_10;
            }
          }
          renameTestSchema((_DWORD)a1, v11, v20 == 1, (unsigned int)qword_18009EEF0, 0);
          renameFixQuotes(a1, v11, v20 == 1);
          v15 = a1;
          if ( a1[22] )
            v15 = (_QWORD *)a1[22];
          *((_BYTE *)v15 + 33) = 1;
          v8 = sqlite3NameFromToken(v4, a4);
          if ( v8 )
          {
            v16 = *((_BYTE *)&qword_18009E630 + **a4) & 0x80;
            sqlite3NestedParse(
              a1,
              "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE "
              "name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
              v11,
              v11,
              *v10,
              v13,
              v8,
              v16,
              v20 == 1,
              *v10);
            LODWORD(v19) = v16;
            LODWORD(v18) = v13;
            sqlite3NestedParse(
              a1,
              "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE typ"
              "e IN ('trigger', 'view')",
              v11,
              *v10,
              v18,
              v8,
              v19);
            renameReloadSchema(a1, v20, 1);
            renameTestSchema((_DWORD)a1, v11, v20 == 1, (unsigned int)"after rename", 1);
          }
        }
      }
    }
  }
LABEL_16:
  sqlite3SrcListDelete(v4, a2);
  sqlite3DbFree(v4, v7);
  return sqlite3DbFree(v4, v8);
}

```

## disassembly

```asm
0x1800809a0  mov     [rsp+arg_10], rbx
0x1800809a5  mov     [rsp+arg_18], r9
0x1800809aa  mov     [rsp+arg_8], rdx
0x1800809af  push    rbp
0x1800809b0  push    rsi
0x1800809b1  push    rdi
0x1800809b2  push    r12
0x1800809b4  push    r13
0x1800809b6  push    r14
0x1800809b8  push    r15
0x1800809ba  sub     rsp, 60h
0x1800809be  mov     rbp, [rcx]
0x1800809c1  mov     rbx, r8
0x1800809c4  lea     r8, [rdx+8]
0x1800809c8  mov     rdi, rcx
0x1800809cb  xor     edx, edx
0x1800809cd  xor     r15d, r15d
0x1800809d0  xor     r12d, r12d
0x1800809d3  call    sqlite3LocateTableItem
0x1800809d8  mov     rsi, rax
0x1800809db  test    rax, rax
0x1800809de  jz      loc_180080BC3
0x1800809e4  mov     rdx, rax
0x1800809e7  mov     rcx, rdi
0x1800809ea  call    isAlterableTable
0x1800809ef  test    eax, eax
0x1800809f1  jnz     loc_180080BC3
0x1800809f7  xor     r8d, r8d
0x1800809fa  mov     rdx, rsi
0x1800809fd  mov     rcx, rdi
0x180080a00  call    isRealTable
0x180080a05  test    eax, eax
0x180080a07  jnz     loc_180080BC3
0x180080a0d  mov     rdx, [rsi+60h]
0x180080a11  mov     rcx, rbp
0x180080a14  call    sqlite3SchemaToIndex
0x180080a19  mov     r9, [rsi]
0x180080a1c  lea     edx, [r15+1Ah]
0x180080a20  movsxd  rcx, eax
0x180080a23  shl     rcx, 5
0x180080a27  mov     [rsp+98h+arg_0], eax
0x180080a2e  mov     rax, [rbp+20h]
0x180080a32  mov     [rsp+98h+var_78], r12
0x180080a37  mov     r13, [rcx+rax]
0x180080a3b  mov     rcx, rdi
0x180080a3e  mov     r8, r13
0x180080a41  call    sqlite3AuthCheck
0x180080a46  test    eax, eax
0x180080a48  jnz     loc_180080BC3
0x180080a4e  mov     rdx, rbx
0x180080a51  mov     rcx, rbp
0x180080a54  call    sqlite3NameFromToken
0x180080a59  mov     r15, rax
0x180080a5c  test    rax, rax
0x180080a5f  jz      loc_180080BC3
0x180080a65  movsx   r11d, word ptr [rsi+36h]
0x180080a6a  xor     r14d, r14d
0x180080a6d  test    r11d, r11d
0x180080a70  jle     short loc_180080A96
0x180080a72  mov     r8, [rsi+8]
0x180080a76  lea     rcx, [r14+r14*2]
0x180080a7a  mov     rdx, r15
0x180080a7d  mov     rcx, [r8+rcx*8]
0x180080a81  call    sqlite3StrICmp
0x180080a86  test    eax, eax
0x180080a88  jz      short loc_180080AB2
0x180080a8a  mov     r8, [rsi+8]
0x180080a8e  inc     r14d
0x180080a91  cmp     r14d, r11d
0x180080a94  jl      short loc_180080A76
0x180080a96  cmp     r14d, r11d
0x180080a99  jnz     short loc_180080AB2
0x180080a9b  mov     r8, rbx
0x180080a9e  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x180080aa5  mov     rcx, rdi
0x180080aa8  call    sqlite3ErrorMsg
0x180080aad  jmp     loc_180080BC3
0x180080ab2  xor     ebx, ebx
0x180080ab4  mov     dword ptr [rsp+98h+var_78], r12d
0x180080ab9  cmp     [rsp+98h+arg_0], 1
0x180080ac1  lea     r9, qword_18009EEF0
0x180080ac8  mov     rdx, r13
0x180080acb  mov     rcx, rdi
0x180080ace  setz    bl
0x180080ad1  mov     r8d, ebx
0x180080ad4  mov     [rsp+98h+var_48], ebx
0x180080ad8  call    renameTestSchema
0x180080add  mov     r8d, ebx
0x180080ae0  mov     rdx, r13
0x180080ae3  mov     rcx, rdi
0x180080ae6  call    renameFixQuotes
0x180080aeb  mov     rax, [rdi+0B0h]
0x180080af2  mov     rcx, rdi
0x180080af5  mov     rbx, [rsp+98h+arg_18]
0x180080afd  test    rax, rax
0x180080b00  mov     rdx, rbx
0x180080b03  cmovnz  rcx, rax
0x180080b07  mov     byte ptr [rcx+21h], 1
0x180080b0b  mov     rcx, rbp
0x180080b0e  call    sqlite3NameFromToken
0x180080b13  mov     r12, rax
0x180080b16  test    rax, rax
0x180080b19  jz      loc_180080BC3
0x180080b1f  mov     rcx, [rbx]
0x180080b22  lea     rax, qword_18009E630
0x180080b29  mov     r9, r13
0x180080b2c  mov     r8, r13
0x180080b2f  movzx   edx, byte ptr [rcx]
0x180080b32  mov     rcx, [rsi]
0x180080b35  mov     [rsp+98h+var_50], rcx
0x180080b3a  movzx   ebx, byte ptr [rdx+rax]
0x180080b3e  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180080b45  mov     eax, [rsp+98h+var_48]
0x180080b49  and     ebx, 80h
0x180080b4f  mov     [rsp+98h+var_58], eax
0x180080b53  mov     [rsp+98h+var_60], ebx
0x180080b57  mov     [rsp+98h+var_68], r12
0x180080b5c  mov     dword ptr [rsp+98h+var_70], r14d
0x180080b61  mov     [rsp+98h+var_78], rcx
0x180080b66  mov     rcx, rdi
0x180080b69  call    sqlite3NestedParse
0x180080b6e  mov     r9, [rsi]
0x180080b71  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x180080b78  mov     dword ptr [rsp+98h+var_68], ebx
0x180080b7c  mov     r8, r13
0x180080b7f  mov     [rsp+98h+var_70], r12
0x180080b84  mov     rcx, rdi
0x180080b87  mov     dword ptr [rsp+98h+var_78], r14d
0x180080b8c  call    sqlite3NestedParse
0x180080b91  mov     edx, [rsp+98h+arg_0]
0x180080b98  mov     ebx, 1
0x180080b9d  mov     r8d, ebx
0x180080ba0  mov     rcx, rdi
0x180080ba3  call    renameReloadSchema
0x180080ba8  mov     r8d, [rsp+98h+var_48]
0x180080bad  lea     r9, aAfterRename; "after rename"
0x180080bb4  mov     rdx, r13
0x180080bb7  mov     dword ptr [rsp+98h+var_78], ebx
0x180080bbb  mov     rcx, rdi
0x180080bbe  call    renameTestSchema
0x180080bc3  mov     rdx, [rsp+98h+arg_8]
0x180080bcb  mov     rcx, rbp
0x180080bce  call    sqlite3SrcListDelete
0x180080bd3  mov     rdx, r15
0x180080bd6  mov     rcx, rbp
0x180080bd9  call    sqlite3DbFree
0x180080bde  mov     rdx, r12
0x180080be1  mov     rcx, rbp
0x180080be4  mov     rbx, [rsp+98h+arg_10]
0x180080bec  add     rsp, 60h
0x180080bf0  pop     r15
0x180080bf2  pop     r14
0x180080bf4  pop     r13
0x180080bf6  pop     r12
0x180080bf8  pop     rdi
0x180080bf9  pop     rsi
0x180080bfa  pop     rbp
0x180080bfb  jmp     sqlite3DbFree
```

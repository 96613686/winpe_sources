# sqlite3AlterRenameColumn

- ea: `0x180072cf0`
- end: `0x180072f50`
- name: `sqlite3AlterRenameColumn`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x18000213c`

## callees

- `0x180009fe0`
- `0x18000a710`
- `0x18000a754`
- `0x180011bcc`
- `0x18001f0f0`
- `0x18001f418`
- `0x18001f530`
- `0x180041d10`
- `0x18004a9b8`
- `0x180072cf0`
- `0x180081560`
- `0x180081a84`
- `0x18008d39c`
- `0x18008d51c`
- `0x18008ddc0`

## string_xrefs

- `0x180072efd`: `after rename`
- `0x180072e8e`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x180072ec1`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

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
    if ( !(unsigned int)isAlterableTable(a1, TableItem) && !(unsigned int)isRealTable((__int64)a1, (__int64)v10, 0) )
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
          renameTestSchema((_DWORD)a1, v11, v20 == 1, (unsigned int)&Src, 0);
          renameFixQuotes(a1, v11, v20 == 1);
          v15 = a1;
          if ( a1[22] )
            v15 = (_QWORD *)a1[22];
          *((_BYTE *)v15 + 33) = 1;
          v8 = sqlite3NameFromToken(v4, a4);
          if ( v8 )
          {
            v16 = *((_BYTE *)&qword_1800B4FF0 + **a4) & 0x80;
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
0x180072cf0  mov     [rsp+arg_10], rbx
0x180072cf5  mov     [rsp+arg_18], r9
0x180072cfa  mov     [rsp+arg_8], rdx
0x180072cff  push    rbp
0x180072d00  push    rsi
0x180072d01  push    rdi
0x180072d02  push    r12
0x180072d04  push    r13
0x180072d06  push    r14
0x180072d08  push    r15
0x180072d0a  sub     rsp, 60h
0x180072d0e  mov     rbp, [rcx]
0x180072d11  mov     rbx, r8
0x180072d14  lea     r8, [rdx+8]
0x180072d18  mov     rdi, rcx
0x180072d1b  xor     edx, edx
0x180072d1d  xor     r15d, r15d
0x180072d20  xor     r12d, r12d
0x180072d23  call    sqlite3LocateTableItem
0x180072d28  mov     rsi, rax
0x180072d2b  test    rax, rax
0x180072d2e  jz      loc_180072F13
0x180072d34  mov     rdx, rax
0x180072d37  mov     rcx, rdi
0x180072d3a  call    isAlterableTable
0x180072d3f  test    eax, eax
0x180072d41  jnz     loc_180072F13
0x180072d47  xor     r8d, r8d
0x180072d4a  mov     rdx, rsi
0x180072d4d  mov     rcx, rdi
0x180072d50  call    isRealTable
0x180072d55  test    eax, eax
0x180072d57  jnz     loc_180072F13
0x180072d5d  mov     rdx, [rsi+60h]
0x180072d61  mov     rcx, rbp
0x180072d64  call    sqlite3SchemaToIndex
0x180072d69  mov     r9, [rsi]
0x180072d6c  lea     edx, [r15+1Ah]
0x180072d70  movsxd  rcx, eax
0x180072d73  shl     rcx, 5
0x180072d77  mov     [rsp+98h+arg_0], eax
0x180072d7e  mov     rax, [rbp+20h]
0x180072d82  mov     [rsp+98h+var_78], r12
0x180072d87  mov     r13, [rcx+rax]
0x180072d8b  mov     rcx, rdi
0x180072d8e  mov     r8, r13
0x180072d91  call    sqlite3AuthCheck
0x180072d96  test    eax, eax
0x180072d98  jnz     loc_180072F13
0x180072d9e  mov     rdx, rbx
0x180072da1  mov     rcx, rbp
0x180072da4  call    sqlite3NameFromToken
0x180072da9  mov     r15, rax
0x180072dac  test    rax, rax
0x180072daf  jz      loc_180072F13
0x180072db5  movsx   r11d, word ptr [rsi+36h]
0x180072dba  xor     r14d, r14d
0x180072dbd  test    r11d, r11d
0x180072dc0  jle     short loc_180072DE6
0x180072dc2  mov     r8, [rsi+8]
0x180072dc6  lea     rcx, [r14+r14*2]
0x180072dca  mov     rdx, r15
0x180072dcd  mov     rcx, [r8+rcx*8]
0x180072dd1  call    sqlite3StrICmp
0x180072dd6  test    eax, eax
0x180072dd8  jz      short loc_180072E02
0x180072dda  mov     r8, [rsi+8]
0x180072dde  inc     r14d
0x180072de1  cmp     r14d, r11d
0x180072de4  jl      short loc_180072DC6
0x180072de6  cmp     r14d, r11d
0x180072de9  jnz     short loc_180072E02
0x180072deb  mov     r8, rbx
0x180072dee  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x180072df5  mov     rcx, rdi
0x180072df8  call    sqlite3ErrorMsg
0x180072dfd  jmp     loc_180072F13
0x180072e02  xor     ebx, ebx
0x180072e04  mov     dword ptr [rsp+98h+var_78], r12d
0x180072e09  cmp     [rsp+98h+arg_0], 1
0x180072e11  lea     r9, Src
0x180072e18  mov     rdx, r13
0x180072e1b  mov     rcx, rdi
0x180072e1e  setz    bl
0x180072e21  mov     r8d, ebx
0x180072e24  mov     [rsp+98h+var_48], ebx
0x180072e28  call    renameTestSchema
0x180072e2d  mov     r8d, ebx
0x180072e30  mov     rdx, r13
0x180072e33  mov     rcx, rdi
0x180072e36  call    renameFixQuotes
0x180072e3b  mov     rax, [rdi+0B0h]
0x180072e42  mov     rcx, rdi
0x180072e45  mov     rbx, [rsp+98h+arg_18]
0x180072e4d  test    rax, rax
0x180072e50  mov     rdx, rbx
0x180072e53  cmovnz  rcx, rax
0x180072e57  mov     byte ptr [rcx+21h], 1
0x180072e5b  mov     rcx, rbp
0x180072e5e  call    sqlite3NameFromToken
0x180072e63  mov     r12, rax
0x180072e66  test    rax, rax
0x180072e69  jz      loc_180072F13
0x180072e6f  mov     rcx, [rbx]
0x180072e72  lea     rax, qword_1800B4FF0
0x180072e79  mov     r9, r13
0x180072e7c  mov     r8, r13
0x180072e7f  movzx   edx, byte ptr [rcx]
0x180072e82  mov     rcx, [rsi]
0x180072e85  mov     [rsp+98h+var_50], rcx
0x180072e8a  movzx   ebx, byte ptr [rdx+rax]
0x180072e8e  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180072e95  mov     eax, [rsp+98h+var_48]
0x180072e99  and     ebx, 80h
0x180072e9f  mov     [rsp+98h+var_58], eax
0x180072ea3  mov     [rsp+98h+var_60], ebx
0x180072ea7  mov     [rsp+98h+var_68], r12
0x180072eac  mov     dword ptr [rsp+98h+var_70], r14d
0x180072eb1  mov     [rsp+98h+var_78], rcx
0x180072eb6  mov     rcx, rdi
0x180072eb9  call    sqlite3NestedParse
0x180072ebe  mov     r9, [rsi]
0x180072ec1  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x180072ec8  mov     dword ptr [rsp+98h+var_68], ebx
0x180072ecc  mov     r8, r13
0x180072ecf  mov     [rsp+98h+var_70], r12
0x180072ed4  mov     rcx, rdi
0x180072ed7  mov     dword ptr [rsp+98h+var_78], r14d
0x180072edc  call    sqlite3NestedParse
0x180072ee1  mov     edx, [rsp+98h+arg_0]
0x180072ee8  mov     ebx, 1
0x180072eed  mov     r8d, ebx
0x180072ef0  mov     rcx, rdi
0x180072ef3  call    renameReloadSchema
0x180072ef8  mov     r8d, [rsp+98h+var_48]
0x180072efd  lea     r9, aAfterRename; "after rename"
0x180072f04  mov     rdx, r13
0x180072f07  mov     dword ptr [rsp+98h+var_78], ebx
0x180072f0b  mov     rcx, rdi
0x180072f0e  call    renameTestSchema
0x180072f13  mov     rdx, [rsp+98h+arg_8]
0x180072f1b  mov     rcx, rbp
0x180072f1e  call    sqlite3SrcListDelete
0x180072f23  mov     rdx, r15
0x180072f26  mov     rcx, rbp
0x180072f29  call    sqlite3DbFree
0x180072f2e  mov     rdx, r12
0x180072f31  mov     rcx, rbp
0x180072f34  mov     rbx, [rsp+98h+arg_10]
0x180072f3c  add     rsp, 60h
0x180072f40  pop     r15
0x180072f42  pop     r14
0x180072f44  pop     r13
0x180072f46  pop     r12
0x180072f48  pop     rdi
0x180072f49  pop     rsi
0x180072f4a  pop     rbp
0x180072f4b  jmp     sqlite3DbFree
```

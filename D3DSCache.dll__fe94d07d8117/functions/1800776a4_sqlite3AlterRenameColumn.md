# sqlite3AlterRenameColumn

- ea: `0x1800776a4`
- end: `0x180077909`
- name: `sqlite3AlterRenameColumn`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x18001bc30`

## callees

- `0x180014464`
- `0x180027e60`
- `0x18002e290`
- `0x18003cc7c`
- `0x18003f960`
- `0x18004002c`
- `0x180042130`
- `0x180042bb0`
- `0x180042c38`
- `0x18006415c`
- `0x18006497c`
- `0x1800736fc`
- `0x18007387c`
- `0x180074120`
- `0x1800776a4`

## string_xrefs

- `0x1800778b6`: `after rename`
- `0x180077847`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x18007787a`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int8 **a4)
{
  __int64 v4; // rbp
  __int64 v7; // r15
  __int64 v8; // r13
  __int64 TableItem; // rax
  _QWORD *v10; // rsi
  int v11; // ebx
  __int64 v12; // r14
  __int64 v13; // r8
  _QWORD *v14; // rcx
  int v15; // ebx
  __int64 v17; // [rsp+20h] [rbp-78h]
  __int64 v18; // [rsp+30h] [rbp-68h]
  __int64 v19; // [rsp+58h] [rbp-40h]
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
      v19 = *(_QWORD *)(32LL * (int)v20 + *(_QWORD *)(v4 + 32));
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v19, *v10, 0) )
      {
        v7 = sqlite3NameFromToken(v4, a3);
        if ( v7 )
        {
          v11 = *((__int16 *)v10 + 27);
          v12 = 0;
          if ( v11 <= 0 )
          {
LABEL_10:
            if ( (_DWORD)v12 == v11 )
            {
              sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
              goto LABEL_16;
            }
          }
          else
          {
            v13 = v10[1];
            while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v13 + 24 * v12), v7) )
            {
              v13 = v10[1];
              v12 = (unsigned int)(v12 + 1);
              if ( (int)v12 >= v11 )
                goto LABEL_10;
            }
          }
          renameTestSchema((_DWORD)a1, v19, v20 == 1, (unsigned int)&Src, 0);
          renameFixQuotes(a1, v19, v20 == 1);
          v14 = a1;
          if ( a1[22] )
            v14 = (_QWORD *)a1[22];
          *((_BYTE *)v14 + 33) = 1;
          v8 = sqlite3NameFromToken(v4, a4);
          if ( v8 )
          {
            v15 = *((_BYTE *)&qword_1800ADE90 + **a4) & 0x80;
            sqlite3NestedParse(
              a1,
              "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE "
              "name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
              v19,
              v19,
              *v10,
              v12,
              v8,
              v15,
              v20 == 1,
              *v10);
            LODWORD(v18) = v15;
            LODWORD(v17) = v12;
            sqlite3NestedParse(
              a1,
              "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE typ"
              "e IN ('trigger', 'view')",
              v19,
              *v10,
              v17,
              v8,
              v18);
            renameReloadSchema(a1, v20, 1);
            renameTestSchema((_DWORD)a1, v19, v20 == 1, (unsigned int)"after rename", 1);
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
0x1800776a4  mov     [rsp+arg_10], rbx
0x1800776a9  mov     [rsp+arg_18], r9
0x1800776ae  mov     [rsp+arg_8], rdx
0x1800776b3  push    rbp
0x1800776b4  push    rsi
0x1800776b5  push    rdi
0x1800776b6  push    r12
0x1800776b8  push    r13
0x1800776ba  push    r14
0x1800776bc  push    r15
0x1800776be  sub     rsp, 60h
0x1800776c2  mov     rbp, [rcx]
0x1800776c5  mov     r12, r8
0x1800776c8  lea     r8, [rdx+8]
0x1800776cc  mov     rdi, rcx
0x1800776cf  xor     edx, edx
0x1800776d1  xor     r15d, r15d
0x1800776d4  xor     r13d, r13d
0x1800776d7  call    sqlite3LocateTableItem
0x1800776dc  mov     rsi, rax
0x1800776df  test    rax, rax
0x1800776e2  jz      loc_1800778CC
0x1800776e8  mov     rdx, rax
0x1800776eb  mov     rcx, rdi
0x1800776ee  call    isAlterableTable
0x1800776f3  test    eax, eax
0x1800776f5  jnz     loc_1800778CC
0x1800776fb  xor     r8d, r8d
0x1800776fe  mov     rdx, rsi
0x180077701  mov     rcx, rdi
0x180077704  call    isRealTable
0x180077709  test    eax, eax
0x18007770b  jnz     loc_1800778CC
0x180077711  mov     rdx, [rsi+60h]
0x180077715  mov     rcx, rbp
0x180077718  call    sqlite3SchemaToIndex
0x18007771d  mov     r9, [rsi]
0x180077720  lea     edx, [r15+1Ah]
0x180077724  movsxd  rcx, eax
0x180077727  shl     rcx, 5
0x18007772b  mov     [rsp+98h+arg_0], eax
0x180077732  mov     rax, [rbp+20h]
0x180077736  mov     [rsp+98h+var_78], r13
0x18007773b  mov     r8, [rcx+rax]
0x18007773f  mov     rcx, rdi
0x180077742  mov     [rsp+98h+var_40], r8
0x180077747  call    sqlite3AuthCheck
0x18007774c  test    eax, eax
0x18007774e  jnz     loc_1800778CC
0x180077754  mov     rdx, r12
0x180077757  mov     rcx, rbp
0x18007775a  call    sqlite3NameFromToken
0x18007775f  mov     r15, rax
0x180077762  test    rax, rax
0x180077765  jz      loc_1800778CC
0x18007776b  movsx   ebx, word ptr [rsi+36h]
0x18007776f  xor     r14d, r14d
0x180077772  test    ebx, ebx
0x180077774  jle     short loc_18007779A
0x180077776  mov     r8, [rsi+8]
0x18007777a  lea     rcx, [r14+r14*2]
0x18007777e  mov     rdx, r15
0x180077781  mov     rcx, [r8+rcx*8]
0x180077785  call    sqlite3StrICmp
0x18007778a  test    eax, eax
0x18007778c  jz      short loc_1800777B6
0x18007778e  mov     r8, [rsi+8]
0x180077792  inc     r14d
0x180077795  cmp     r14d, ebx
0x180077798  jl      short loc_18007777A
0x18007779a  cmp     r14d, ebx
0x18007779d  jnz     short loc_1800777B6
0x18007779f  mov     r8, r12
0x1800777a2  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x1800777a9  mov     rcx, rdi
0x1800777ac  call    sqlite3ErrorMsg
0x1800777b1  jmp     loc_1800778CC
0x1800777b6  mov     r12, [rsp+98h+var_40]
0x1800777bb  lea     r9, Src
0x1800777c2  xor     ebx, ebx
0x1800777c4  mov     dword ptr [rsp+98h+var_78], r13d
0x1800777c9  cmp     [rsp+98h+arg_0], 1
0x1800777d1  mov     rdx, r12
0x1800777d4  mov     rcx, rdi
0x1800777d7  setz    bl
0x1800777da  mov     r8d, ebx
0x1800777dd  mov     [rsp+98h+var_48], ebx
0x1800777e1  call    renameTestSchema
0x1800777e6  mov     r8d, ebx
0x1800777e9  mov     rdx, r12
0x1800777ec  mov     rcx, rdi
0x1800777ef  call    renameFixQuotes
0x1800777f4  mov     rax, [rdi+0B0h]
0x1800777fb  mov     rcx, rdi
0x1800777fe  mov     rbx, [rsp+98h+arg_18]
0x180077806  test    rax, rax
0x180077809  mov     rdx, rbx
0x18007780c  cmovnz  rcx, rax
0x180077810  mov     byte ptr [rcx+21h], 1
0x180077814  mov     rcx, rbp
0x180077817  call    sqlite3NameFromToken
0x18007781c  mov     r13, rax
0x18007781f  test    rax, rax
0x180077822  jz      loc_1800778CC
0x180077828  mov     rcx, [rbx]
0x18007782b  lea     rax, qword_1800ADE90
0x180077832  mov     r9, r12
0x180077835  mov     r8, r12
0x180077838  movzx   edx, byte ptr [rcx]
0x18007783b  mov     rcx, [rsi]
0x18007783e  mov     [rsp+98h+var_50], rcx
0x180077843  movzx   ebx, byte ptr [rdx+rax]
0x180077847  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x18007784e  mov     eax, [rsp+98h+var_48]
0x180077852  and     ebx, 80h
0x180077858  mov     [rsp+98h+var_58], eax
0x18007785c  mov     [rsp+98h+var_60], ebx
0x180077860  mov     [rsp+98h+var_68], r13
0x180077865  mov     dword ptr [rsp+98h+var_70], r14d
0x18007786a  mov     [rsp+98h+var_78], rcx
0x18007786f  mov     rcx, rdi
0x180077872  call    sqlite3NestedParse
0x180077877  mov     r9, [rsi]
0x18007787a  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x180077881  mov     dword ptr [rsp+98h+var_68], ebx
0x180077885  mov     r8, r12
0x180077888  mov     [rsp+98h+var_70], r13
0x18007788d  mov     rcx, rdi
0x180077890  mov     dword ptr [rsp+98h+var_78], r14d
0x180077895  call    sqlite3NestedParse
0x18007789a  mov     edx, [rsp+98h+arg_0]
0x1800778a1  mov     ebx, 1
0x1800778a6  mov     r8d, ebx
0x1800778a9  mov     rcx, rdi
0x1800778ac  call    renameReloadSchema
0x1800778b1  mov     r8d, [rsp+98h+var_48]
0x1800778b6  lea     r9, aAfterRename; "after rename"
0x1800778bd  mov     rdx, r12
0x1800778c0  mov     dword ptr [rsp+98h+var_78], ebx
0x1800778c4  mov     rcx, rdi
0x1800778c7  call    renameTestSchema
0x1800778cc  mov     rdx, [rsp+98h+arg_8]
0x1800778d4  mov     rcx, rbp
0x1800778d7  call    sqlite3SrcListDelete
0x1800778dc  mov     rdx, r15
0x1800778df  mov     rcx, rbp
0x1800778e2  call    sqlite3DbFree
0x1800778e7  mov     rdx, r13
0x1800778ea  mov     rcx, rbp
0x1800778ed  mov     rbx, [rsp+98h+arg_10]
0x1800778f5  add     rsp, 60h
0x1800778f9  pop     r15
0x1800778fb  pop     r14
0x1800778fd  pop     r13
0x1800778ff  pop     r12
0x180077901  pop     rdi
0x180077902  pop     rsi
0x180077903  pop     rbp
0x180077904  jmp     sqlite3DbFree
```

# sqlite3AlterRenameColumn

- ea: `0x1800682a4`
- end: `0x18006854d`
- name: `sqlite3AlterRenameColumn`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x1800c3bd8`

## callees

- `0x18004c564`
- `0x18004cf78`
- `0x180061040`
- `0x180061bb4`
- `0x1800682a4`
- `0x1800693b0`
- `0x1800716fc`
- `0x180073aec`
- `0x180080774`
- `0x180081754`
- `0x1800817f4`
- `0x18008e124`
- `0x18008ed60`

## string_xrefs

- `0x180068405`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x18006841c`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x1800684f3`: `after rename`
- `0x180068480`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x1800684b6`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int8 **a4)
{
  __int64 v4; // rsi
  __int64 v7; // r12
  __int64 v8; // r13
  __int64 TableItem; // rax
  __int64 v10; // r14
  __int64 v11; // rcx
  int v12; // ebp
  __int64 v13; // rdx
  __int64 v14; // rbx
  int v15; // r11d
  __int64 v16; // r15
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 result; // rax
  __int64 v20; // [rsp+20h] [rbp-88h]
  int v21; // [rsp+38h] [rbp-70h]

  v4 = *a1;
  v7 = 0;
  v8 = 0;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v10 = TableItem;
  if ( TableItem && !(unsigned int)isAlterableTable(a1, TableItem) && !(unsigned int)isRealTable(a1, v10, 0) )
  {
    v11 = *(_QWORD *)(v10 + 96);
    v12 = -32768;
    if ( v11 )
    {
      v13 = *(_QWORD *)(v4 + 32);
      v12 = 0;
      if ( *(_QWORD *)(v13 + 24) != v11 )
      {
        do
          ++v12;
        while ( *(_QWORD *)(32LL * v12 + v13 + 24) != v11 );
      }
    }
    v14 = *(_QWORD *)(32LL * v12 + *(_QWORD *)(v4 + 32));
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v14, *(_QWORD *)v10, 0) )
    {
      v7 = sqlite3NameFromToken(v4, a3);
      if ( v7 )
      {
        v15 = *(__int16 *)(v10 + 54);
        v16 = 0;
        if ( v15 <= 0 )
        {
LABEL_13:
          if ( (_DWORD)v16 == v15 )
          {
            sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
            goto LABEL_21;
          }
        }
        else
        {
          v17 = *(_QWORD *)(v10 + 8);
          while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v17 + 24 * v16), v7) )
          {
            v17 = *(_QWORD *)(v10 + 8);
            v16 = (unsigned int)(v16 + 1);
            if ( (int)v16 >= v15 )
              goto LABEL_13;
          }
        }
        renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)&Src, 0);
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE '"
          "X' AND sql NOT LIKE 'create virtual%%'",
          v14,
          v14);
        if ( v12 != 1 )
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCA"
            "PE 'X' AND sql NOT LIKE 'create virtual%%'");
        v18 = a1;
        if ( a1[22] )
          v18 = (_QWORD *)a1[22];
        *((_BYTE *)v18 + 33) = 1;
        v8 = sqlite3NameFromToken(v4, a4);
        if ( v8 )
        {
          v21 = *((_BYTE *)&qword_1800FB500 + **a4) & 0x80;
          v20 = *(_QWORD *)v10;
          sqlite3NestedParse(
            a1,
            "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE na"
            "me NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
            v14);
          LODWORD(v20) = v16;
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type "
            "IN ('trigger', 'view')",
            v14,
            *(_QWORD *)v10,
            v20,
            v8,
            __PAIR64__(HIDWORD(v8), v21));
          renameReloadSchema(a1, (unsigned int)v12, 1);
          renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)"after rename", 1);
        }
      }
    }
  }
LABEL_21:
  result = sqlite3SrcListDelete(v4, a2);
  if ( v7 )
    result = sqlite3DbFreeNN(v4);
  if ( v8 )
    return sqlite3DbFreeNN(v4);
  return result;
}

```

## disassembly

```asm
0x1800682a4  mov     [rsp+arg_18], r9
0x1800682a9  mov     [rsp+arg_10], r8
0x1800682ae  mov     [rsp+arg_8], rdx
0x1800682b3  push    rbx
0x1800682b4  push    rbp
0x1800682b5  push    rsi
0x1800682b6  push    rdi
0x1800682b7  push    r12
0x1800682b9  push    r13
0x1800682bb  push    r14
0x1800682bd  push    r15
0x1800682bf  sub     rsp, 68h
0x1800682c3  mov     rsi, [rcx]
0x1800682c6  mov     r15, r8
0x1800682c9  lea     r8, [rdx+8]
0x1800682cd  mov     rdi, rcx
0x1800682d0  xor     edx, edx
0x1800682d2  xor     r12d, r12d
0x1800682d5  xor     r13d, r13d
0x1800682d8  call    sqlite3LocateTableItem
0x1800682dd  mov     r14, rax
0x1800682e0  test    rax, rax
0x1800682e3  jz      loc_18006850C
0x1800682e9  mov     rdx, rax
0x1800682ec  mov     rcx, rdi
0x1800682ef  call    isAlterableTable
0x1800682f4  test    eax, eax
0x1800682f6  jnz     loc_18006850C
0x1800682fc  xor     r8d, r8d
0x1800682ff  mov     rdx, r14
0x180068302  mov     rcx, rdi
0x180068305  call    isRealTable
0x18006830a  test    eax, eax
0x18006830c  jnz     loc_18006850C
0x180068312  mov     rcx, [r14+60h]
0x180068316  mov     ebp, 0FFFF8000h
0x18006831b  test    rcx, rcx
0x18006831e  jz      short loc_18006833C
0x180068320  mov     rdx, [rsi+20h]
0x180068324  xor     ebp, ebp
0x180068326  cmp     [rdx+18h], rcx
0x18006832a  jz      short loc_18006833C
0x18006832c  inc     ebp
0x18006832e  movsxd  rax, ebp
0x180068331  shl     rax, 5
0x180068335  cmp     [rax+rdx+18h], rcx
0x18006833a  jnz     short loc_18006832C
0x18006833c  mov     rax, [rsi+20h]
0x180068340  mov     edx, 1Ah
0x180068345  mov     r9, [r14]
0x180068348  movsxd  rcx, ebp
0x18006834b  shl     rcx, 5
0x18006834f  mov     [rsp+0A8h+var_88], r12
0x180068354  mov     rbx, [rcx+rax]
0x180068358  mov     rcx, rdi
0x18006835b  mov     r8, rbx
0x18006835e  mov     [rsp+0A8h+var_58], rbx
0x180068363  call    sqlite3AuthCheck
0x180068368  test    eax, eax
0x18006836a  jnz     loc_18006850C
0x180068370  mov     rdx, r15
0x180068373  mov     rcx, rsi
0x180068376  call    sqlite3NameFromToken
0x18006837b  mov     r12, rax
0x18006837e  test    rax, rax
0x180068381  jz      loc_18006850C
0x180068387  movsx   r11d, word ptr [r14+36h]
0x18006838c  xor     r15d, r15d
0x18006838f  test    r11d, r11d
0x180068392  jle     short loc_1800683B8
0x180068394  mov     rax, [r14+8]
0x180068398  lea     rcx, [r15+r15*2]
0x18006839c  mov     rdx, r12
0x18006839f  mov     rcx, [rax+rcx*8]
0x1800683a3  call    sqlite3StrICmp
0x1800683a8  test    eax, eax
0x1800683aa  jz      short loc_1800683D9
0x1800683ac  mov     rax, [r14+8]
0x1800683b0  inc     r15d
0x1800683b3  cmp     r15d, r11d
0x1800683b6  jl      short loc_180068398
0x1800683b8  cmp     r15d, r11d
0x1800683bb  jnz     short loc_1800683D9
0x1800683bd  mov     r8, [rsp+0A8h+arg_10]
0x1800683c5  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x1800683cc  mov     rcx, rdi
0x1800683cf  call    sqlite3ErrorMsg
0x1800683d4  jmp     loc_18006850C
0x1800683d9  xor     eax, eax
0x1800683db  mov     dword ptr [rsp+0A8h+var_88], r13d
0x1800683e0  cmp     ebp, 1
0x1800683e3  lea     r9, Src
0x1800683ea  mov     rdx, rbx
0x1800683ed  mov     rcx, rdi
0x1800683f0  setz    al
0x1800683f3  mov     r8d, eax
0x1800683f6  mov     [rsp+0A8h+arg_0], eax
0x1800683fd  call    renameTestSchema
0x180068402  mov     r9, rbx
0x180068405  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x18006840c  mov     r8, rbx
0x18006840f  mov     rcx, rdi
0x180068412  call    sqlite3NestedParse
0x180068417  cmp     ebp, 1
0x18006841a  jz      short loc_18006842B
0x18006841c  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x180068423  mov     rcx, rdi
0x180068426  call    sqlite3NestedParse
0x18006842b  mov     rax, [rdi+0B0h]
0x180068432  mov     rcx, rdi
0x180068435  mov     rbx, [rsp+0A8h+arg_18]
0x18006843d  test    rax, rax
0x180068440  mov     rdx, rbx
0x180068443  cmovnz  rcx, rax
0x180068447  mov     byte ptr [rcx+21h], 1
0x18006844b  mov     rcx, rsi
0x18006844e  call    sqlite3NameFromToken
0x180068453  mov     r13, rax
0x180068456  test    rax, rax
0x180068459  jz      loc_18006850C
0x18006845f  mov     rcx, [rbx]
0x180068462  lea     rax, qword_1800FB500
0x180068469  mov     r9, [rsp+0A8h+var_58]
0x18006846e  mov     r8, r9
0x180068471  movzx   edx, byte ptr [rcx]
0x180068474  mov     rcx, [r14]
0x180068477  mov     [rsp+0A8h+var_60], rcx
0x18006847c  movzx   ebx, byte ptr [rdx+rax]
0x180068480  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180068487  mov     eax, [rsp+0A8h+arg_0]
0x18006848e  and     ebx, 80h
0x180068494  mov     [rsp+0A8h+var_68], eax
0x180068498  mov     [rsp+0A8h+var_70], ebx
0x18006849c  mov     [rsp+0A8h+var_78], r13
0x1800684a1  mov     dword ptr [rsp+0A8h+var_80], r15d
0x1800684a6  mov     [rsp+0A8h+var_88], rcx
0x1800684ab  mov     rcx, rdi
0x1800684ae  call    sqlite3NestedParse
0x1800684b3  mov     r9, [r14]
0x1800684b6  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x1800684bd  mov     r8, [rsp+0A8h+var_58]
0x1800684c2  mov     rcx, rdi
0x1800684c5  mov     dword ptr [rsp+0A8h+var_78], ebx
0x1800684c9  mov     [rsp+0A8h+var_80], r13
0x1800684ce  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800684d3  call    sqlite3NestedParse
0x1800684d8  mov     r14d, 1
0x1800684de  mov     edx, ebp
0x1800684e0  mov     r8d, r14d
0x1800684e3  mov     rcx, rdi
0x1800684e6  call    renameReloadSchema
0x1800684eb  mov     r8d, [rsp+0A8h+arg_0]
0x1800684f3  lea     r9, aAfterRename; "after rename"
0x1800684fa  mov     rdx, [rsp+0A8h+var_58]
0x1800684ff  mov     rcx, rdi
0x180068502  mov     dword ptr [rsp+0A8h+var_88], r14d
0x180068507  call    renameTestSchema
0x18006850c  mov     rdx, [rsp+0A8h+arg_8]
0x180068514  mov     rcx, rsi
0x180068517  call    sqlite3SrcListDelete
0x18006851c  test    r12, r12
0x18006851f  jz      short loc_18006852C
0x180068521  mov     rdx, r12
0x180068524  mov     rcx, rsi
0x180068527  call    sqlite3DbFreeNN
0x18006852c  test    r13, r13
0x18006852f  jz      short loc_18006853C
0x180068531  mov     rdx, r13
0x180068534  mov     rcx, rsi
0x180068537  call    sqlite3DbFreeNN
0x18006853c  add     rsp, 68h
0x180068540  pop     r15
0x180068542  pop     r14
0x180068544  pop     r13
0x180068546  pop     r12
0x180068548  pop     rdi
0x180068549  pop     rsi
0x18006854a  pop     rbp
0x18006854b  pop     rbx
0x18006854c  retn
```

# sqlite3AlterRenameColumn

- ea: `0x18008552c`
- end: `0x1800857d5`
- name: `sqlite3AlterRenameColumn`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x1800de91c`

## callees

- `0x18006be34`
- `0x18006c838`
- `0x18007e600`
- `0x18007f174`
- `0x18008552c`
- `0x18008662c`
- `0x18008e6ac`
- `0x180090934`
- `0x18009d07c`
- `0x18009dccc`
- `0x18009dcfc`
- `0x1800a9f20`
- `0x1800aab5c`

## string_xrefs

- `0x18008568d`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x1800856a4`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x18008577b`: `after rename`
- `0x18008573e`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`
- `0x180085708`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`

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
        renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)&word_1800F2B62, 0);
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
        if ( a1[21] )
          v18 = (_QWORD *)a1[21];
        *((_BYTE *)v18 + 33) = 1;
        v8 = sqlite3NameFromToken(v4, a4);
        if ( v8 )
        {
          v21 = byte_1800FD680[**a4] & 0x80;
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
0x18008552c  mov     [rsp+arg_18], r9
0x180085531  mov     [rsp+arg_10], r8
0x180085536  mov     [rsp+arg_8], rdx
0x18008553b  push    rbx
0x18008553c  push    rbp
0x18008553d  push    rsi
0x18008553e  push    rdi
0x18008553f  push    r12
0x180085541  push    r13
0x180085543  push    r14
0x180085545  push    r15
0x180085547  sub     rsp, 68h
0x18008554b  mov     rsi, [rcx]
0x18008554e  mov     r15, r8
0x180085551  lea     r8, [rdx+8]
0x180085555  mov     rdi, rcx
0x180085558  xor     edx, edx
0x18008555a  xor     r12d, r12d
0x18008555d  xor     r13d, r13d
0x180085560  call    sqlite3LocateTableItem
0x180085565  mov     r14, rax
0x180085568  test    rax, rax
0x18008556b  jz      loc_180085794
0x180085571  mov     rdx, rax
0x180085574  mov     rcx, rdi
0x180085577  call    isAlterableTable
0x18008557c  test    eax, eax
0x18008557e  jnz     loc_180085794
0x180085584  xor     r8d, r8d
0x180085587  mov     rdx, r14
0x18008558a  mov     rcx, rdi
0x18008558d  call    isRealTable
0x180085592  test    eax, eax
0x180085594  jnz     loc_180085794
0x18008559a  mov     rcx, [r14+60h]
0x18008559e  mov     ebp, 0FFFF8000h
0x1800855a3  test    rcx, rcx
0x1800855a6  jz      short loc_1800855C4
0x1800855a8  mov     rdx, [rsi+20h]
0x1800855ac  xor     ebp, ebp
0x1800855ae  cmp     [rdx+18h], rcx
0x1800855b2  jz      short loc_1800855C4
0x1800855b4  inc     ebp
0x1800855b6  movsxd  rax, ebp
0x1800855b9  shl     rax, 5
0x1800855bd  cmp     [rax+rdx+18h], rcx
0x1800855c2  jnz     short loc_1800855B4
0x1800855c4  mov     rax, [rsi+20h]
0x1800855c8  mov     edx, 1Ah
0x1800855cd  mov     r9, [r14]
0x1800855d0  movsxd  rcx, ebp
0x1800855d3  shl     rcx, 5
0x1800855d7  mov     [rsp+0A8h+var_88], r12
0x1800855dc  mov     rbx, [rcx+rax]
0x1800855e0  mov     rcx, rdi
0x1800855e3  mov     r8, rbx
0x1800855e6  mov     [rsp+0A8h+var_58], rbx
0x1800855eb  call    sqlite3AuthCheck
0x1800855f0  test    eax, eax
0x1800855f2  jnz     loc_180085794
0x1800855f8  mov     rdx, r15
0x1800855fb  mov     rcx, rsi
0x1800855fe  call    sqlite3NameFromToken
0x180085603  mov     r12, rax
0x180085606  test    rax, rax
0x180085609  jz      loc_180085794
0x18008560f  movsx   r11d, word ptr [r14+36h]
0x180085614  xor     r15d, r15d
0x180085617  test    r11d, r11d
0x18008561a  jle     short loc_180085640
0x18008561c  mov     rax, [r14+8]
0x180085620  lea     rcx, [r15+r15*2]
0x180085624  mov     rdx, r12
0x180085627  mov     rcx, [rax+rcx*8]
0x18008562b  call    sqlite3StrICmp
0x180085630  test    eax, eax
0x180085632  jz      short loc_180085661
0x180085634  mov     rax, [r14+8]
0x180085638  inc     r15d
0x18008563b  cmp     r15d, r11d
0x18008563e  jl      short loc_180085620
0x180085640  cmp     r15d, r11d
0x180085643  jnz     short loc_180085661
0x180085645  mov     r8, [rsp+0A8h+arg_10]
0x18008564d  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x180085654  mov     rcx, rdi
0x180085657  call    sqlite3ErrorMsg
0x18008565c  jmp     loc_180085794
0x180085661  xor     eax, eax
0x180085663  mov     dword ptr [rsp+0A8h+var_88], r13d
0x180085668  cmp     ebp, 1
0x18008566b  lea     r9, word_1800F2B62
0x180085672  mov     rdx, rbx
0x180085675  mov     rcx, rdi
0x180085678  setz    al
0x18008567b  mov     r8d, eax
0x18008567e  mov     [rsp+0A8h+arg_0], eax
0x180085685  call    renameTestSchema
0x18008568a  mov     r9, rbx
0x18008568d  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180085694  mov     r8, rbx
0x180085697  mov     rcx, rdi
0x18008569a  call    sqlite3NestedParse
0x18008569f  cmp     ebp, 1
0x1800856a2  jz      short loc_1800856B3
0x1800856a4  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x1800856ab  mov     rcx, rdi
0x1800856ae  call    sqlite3NestedParse
0x1800856b3  mov     rax, [rdi+0A8h]
0x1800856ba  mov     rcx, rdi
0x1800856bd  mov     rbx, [rsp+0A8h+arg_18]
0x1800856c5  test    rax, rax
0x1800856c8  mov     rdx, rbx
0x1800856cb  cmovnz  rcx, rax
0x1800856cf  mov     byte ptr [rcx+21h], 1
0x1800856d3  mov     rcx, rsi
0x1800856d6  call    sqlite3NameFromToken
0x1800856db  mov     r13, rax
0x1800856de  test    rax, rax
0x1800856e1  jz      loc_180085794
0x1800856e7  mov     rcx, [rbx]
0x1800856ea  lea     rax, byte_1800FD680
0x1800856f1  mov     r9, [rsp+0A8h+var_58]
0x1800856f6  mov     r8, r9
0x1800856f9  movzx   edx, byte ptr [rcx]
0x1800856fc  mov     rcx, [r14]
0x1800856ff  mov     [rsp+0A8h+var_60], rcx
0x180085704  movzx   ebx, byte ptr [rdx+rax]
0x180085708  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x18008570f  mov     eax, [rsp+0A8h+arg_0]
0x180085716  and     ebx, 80h
0x18008571c  mov     [rsp+0A8h+var_68], eax
0x180085720  mov     [rsp+0A8h+var_70], ebx
0x180085724  mov     [rsp+0A8h+var_78], r13
0x180085729  mov     dword ptr [rsp+0A8h+var_80], r15d
0x18008572e  mov     [rsp+0A8h+var_88], rcx
0x180085733  mov     rcx, rdi
0x180085736  call    sqlite3NestedParse
0x18008573b  mov     r9, [r14]
0x18008573e  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x180085745  mov     r8, [rsp+0A8h+var_58]
0x18008574a  mov     rcx, rdi
0x18008574d  mov     dword ptr [rsp+0A8h+var_78], ebx
0x180085751  mov     [rsp+0A8h+var_80], r13
0x180085756  mov     dword ptr [rsp+0A8h+var_88], r15d
0x18008575b  call    sqlite3NestedParse
0x180085760  mov     r14d, 1
0x180085766  mov     edx, ebp
0x180085768  mov     r8d, r14d
0x18008576b  mov     rcx, rdi
0x18008576e  call    renameReloadSchema
0x180085773  mov     r8d, [rsp+0A8h+arg_0]
0x18008577b  lea     r9, aAfterRename; "after rename"
0x180085782  mov     rdx, [rsp+0A8h+var_58]
0x180085787  mov     rcx, rdi
0x18008578a  mov     dword ptr [rsp+0A8h+var_88], r14d
0x18008578f  call    renameTestSchema
0x180085794  mov     rdx, [rsp+0A8h+arg_8]
0x18008579c  mov     rcx, rsi
0x18008579f  call    sqlite3SrcListDelete
0x1800857a4  test    r12, r12
0x1800857a7  jz      short loc_1800857B4
0x1800857a9  mov     rdx, r12
0x1800857ac  mov     rcx, rsi
0x1800857af  call    sqlite3DbFreeNN
0x1800857b4  test    r13, r13
0x1800857b7  jz      short loc_1800857C4
0x1800857b9  mov     rdx, r13
0x1800857bc  mov     rcx, rsi
0x1800857bf  call    sqlite3DbFreeNN
0x1800857c4  add     rsp, 68h
0x1800857c8  pop     r15
0x1800857ca  pop     r14
0x1800857cc  pop     r13
0x1800857ce  pop     r12
0x1800857d0  pop     rdi
0x1800857d1  pop     rsi
0x1800857d2  pop     rbp
0x1800857d3  pop     rbx
0x1800857d4  retn
```

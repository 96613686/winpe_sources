# renameFixQuotes

- ea: `0x18008d39c`
- end: `0x18008d3dc`
- name: `renameFixQuotes`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180072cf0`
- `0x18008f450`

## callees

- `0x18004a9b8`
- `0x18008d39c`

## string_xrefs

- `0x18008d3b2`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x18008d3c2`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`

## pseudocode

```c
__int64 __fastcall renameFixQuotes(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  result = sqlite3NestedParse(
             a1,
             "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAP"
             "E 'X' AND sql NOT LIKE 'create virtual%%'",
             a2,
             a2);
  if ( !a3 )
    return sqlite3NestedParse(
             a1,
             "UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESC"
             "APE 'X' AND sql NOT LIKE 'create virtual%%'");
  return result;
}

```

## disassembly

```asm
0x18008d39c  mov     [rsp+arg_0], rbx
0x18008d3a1  push    rdi
0x18008d3a2  sub     rsp, 20h
0x18008d3a6  mov     ebx, r8d
0x18008d3a9  mov     r9, rdx
0x18008d3ac  mov     r8, rdx
0x18008d3af  mov     rdi, rcx
0x18008d3b2  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x18008d3b9  call    sqlite3NestedParse
0x18008d3be  test    ebx, ebx
0x18008d3c0  jnz     short loc_18008D3D1
0x18008d3c2  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x18008d3c9  mov     rcx, rdi
0x18008d3cc  call    sqlite3NestedParse
0x18008d3d1  mov     rbx, [rsp+28h+arg_0]
0x18008d3d6  add     rsp, 20h
0x18008d3da  pop     rdi
0x18008d3db  retn
```

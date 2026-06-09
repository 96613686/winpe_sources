# renameFixQuotes

- ea: `0x18007e02c`
- end: `0x18007e06c`
- name: `renameFixQuotes`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180080120`
- `0x1800809a0`

## callees

- `0x18007e02c`
- `0x1800857c4`

## string_xrefs

- `0x18007e042`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x18007e052`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`

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
0x18007e02c  mov     [rsp+arg_0], rbx
0x18007e031  push    rdi
0x18007e032  sub     rsp, 20h
0x18007e036  mov     ebx, r8d
0x18007e039  mov     r9, rdx
0x18007e03c  mov     r8, rdx
0x18007e03f  mov     rdi, rcx
0x18007e042  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x18007e049  call    sqlite3NestedParse
0x18007e04e  test    ebx, ebx
0x18007e050  jnz     short loc_18007E061
0x18007e052  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x18007e059  mov     rcx, rdi
0x18007e05c  call    sqlite3NestedParse
0x18007e061  mov     rbx, [rsp+28h+arg_0]
0x18007e066  add     rsp, 20h
0x18007e06a  pop     rdi
0x18007e06b  retn
```

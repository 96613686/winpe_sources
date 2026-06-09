# renameFixQuotes

- ea: `0x1800736fc`
- end: `0x18007373c`
- name: `renameFixQuotes`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180076e24`
- `0x1800776a4`

## callees

- `0x18003cc7c`
- `0x1800736fc`

## string_xrefs

- `0x180073712`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x180073722`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`

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
0x1800736fc  mov     [rsp+arg_0], rbx
0x180073701  push    rdi
0x180073702  sub     rsp, 20h
0x180073706  mov     ebx, r8d
0x180073709  mov     r9, rdx
0x18007370c  mov     r8, rdx
0x18007370f  mov     rdi, rcx
0x180073712  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180073719  call    sqlite3NestedParse
0x18007371e  test    ebx, ebx
0x180073720  jnz     short loc_180073731
0x180073722  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x180073729  mov     rcx, rdi
0x18007372c  call    sqlite3NestedParse
0x180073731  mov     rbx, [rsp+28h+arg_0]
0x180073736  add     rsp, 20h
0x18007373a  pop     rdi
0x18007373b  retn
```

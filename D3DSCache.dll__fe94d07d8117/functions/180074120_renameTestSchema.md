# renameTestSchema

- ea: `0x180074120`
- end: `0x18007418c`
- name: `renameTestSchema`
- size: `108`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180076e24`
- `0x1800776a4`
- `0x180077910`

## callees

- `0x18003cc7c`
- `0x180074120`

## string_xrefs

- `0x180074154`: `SELECT 1 FROM "%w".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL `
- `0x180074172`: `SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL `

## pseudocode

```c
__int64 __fastcall renameTestSchema(__int64 a1, __int64 a2, int a3, __int64 a4, int a5)
{
  __int64 result; // rax
  __int64 v10; // [rsp+20h] [rbp-48h]

  *(_BYTE *)(a1 + 28) = 1;
  result = sqlite3NestedParse(
             a1,
             "SELECT 1 FROM \"%w\".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create vir"
             "tual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL ",
             a2,
             a2,
             a3,
             a4,
             a5);
  if ( !a3 )
  {
    LODWORD(v10) = a5;
    return sqlite3NestedParse(
             a1,
             "SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtu"
             "al%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL ",
             a2,
             a4,
             v10);
  }
  return result;
}

```

## disassembly

```asm
0x180074120  push    rbx
0x180074122  push    rbp
0x180074123  push    rsi
0x180074124  push    rdi
0x180074125  push    r14
0x180074127  sub     rsp, 40h
0x18007412b  mov     r14d, [rsp+68h+arg_20]
0x180074133  mov     ebx, r8d
0x180074136  mov     [rsp+68h+var_38], r14d
0x18007413b  mov     rbp, r9
0x18007413e  mov     [rsp+68h+var_40], r9
0x180074143  mov     rdi, rdx
0x180074146  mov     r9, rdx
0x180074149  mov     byte ptr [rcx+1Ch], 1
0x18007414d  mov     r8, rdx
0x180074150  mov     dword ptr [rsp+68h+var_48], ebx
0x180074154  lea     rdx, aSelect1FromWSq; "SELECT 1 FROM \"%w\".sqlite_master WHER"...
0x18007415b  mov     rsi, rcx
0x18007415e  call    sqlite3NestedParse
0x180074163  test    ebx, ebx
0x180074165  jnz     short loc_180074181
0x180074167  mov     r9, rbp
0x18007416a  mov     dword ptr [rsp+68h+var_48], r14d
0x18007416f  mov     r8, rdi
0x180074172  lea     rdx, aSelect1FromTem; "SELECT 1 FROM temp.sqlite_master WHERE "...
0x180074179  mov     rcx, rsi
0x18007417c  call    sqlite3NestedParse
0x180074181  add     rsp, 40h
0x180074185  pop     r14
0x180074187  pop     rdi
0x180074188  pop     rsi
0x180074189  pop     rbp
0x18007418a  pop     rbx
0x18007418b  retn
```

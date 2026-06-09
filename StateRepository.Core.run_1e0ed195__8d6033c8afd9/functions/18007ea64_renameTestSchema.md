# renameTestSchema

- ea: `0x18007ea64`
- end: `0x18007ead0`
- name: `renameTestSchema`
- size: `108`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180080120`
- `0x1800809a0`
- `0x180080c08`

## callees

- `0x18007ea64`
- `0x1800857c4`

## string_xrefs

- `0x18007ea98`: `SELECT 1 FROM "%w".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL `
- `0x18007eab6`: `SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL `

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
0x18007ea64  push    rbx
0x18007ea66  push    rbp
0x18007ea67  push    rsi
0x18007ea68  push    rdi
0x18007ea69  push    r14
0x18007ea6b  sub     rsp, 40h
0x18007ea6f  mov     r14d, [rsp+68h+arg_20]
0x18007ea77  mov     ebx, r8d
0x18007ea7a  mov     [rsp+68h+var_38], r14d
0x18007ea7f  mov     rbp, r9
0x18007ea82  mov     [rsp+68h+var_40], r9
0x18007ea87  mov     rdi, rdx
0x18007ea8a  mov     r9, rdx
0x18007ea8d  mov     byte ptr [rcx+1Ch], 1
0x18007ea91  mov     r8, rdx
0x18007ea94  mov     dword ptr [rsp+68h+var_48], ebx
0x18007ea98  lea     rdx, aSelect1FromWSq; "SELECT 1 FROM \"%w\".sqlite_master WHER"...
0x18007ea9f  mov     rsi, rcx
0x18007eaa2  call    sqlite3NestedParse
0x18007eaa7  test    ebx, ebx
0x18007eaa9  jnz     short loc_18007EAC5
0x18007eaab  mov     r9, rbp
0x18007eaae  mov     dword ptr [rsp+68h+var_48], r14d
0x18007eab3  mov     r8, rdi
0x18007eab6  lea     rdx, aSelect1FromTem; "SELECT 1 FROM temp.sqlite_master WHERE "...
0x18007eabd  mov     rcx, rsi
0x18007eac0  call    sqlite3NestedParse
0x18007eac5  add     rsp, 40h
0x18007eac9  pop     r14
0x18007eacb  pop     rdi
0x18007eacc  pop     rsi
0x18007eacd  pop     rbp
0x18007eace  pop     rbx
0x18007eacf  retn
```

# renameTestSchema

- ea: `0x140044904`
- end: `0x140044970`
- name: `renameTestSchema`
- size: `108`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14004a40c`
- `0x14004acbc`
- `0x14004af6c`

## callees

- `0x140044904`
- `0x14006348c`

## string_xrefs

- `0x140044956`: `SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL `
- `0x140044938`: `SELECT 1 FROM "%w".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL `

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
0x140044904  push    rbx
0x140044906  push    rbp
0x140044907  push    rsi
0x140044908  push    rdi
0x140044909  push    r14
0x14004490b  sub     rsp, 40h
0x14004490f  mov     r14d, [rsp+68h+arg_20]
0x140044917  mov     ebx, r8d
0x14004491a  mov     [rsp+68h+var_38], r14d
0x14004491f  mov     rbp, r9
0x140044922  mov     [rsp+68h+var_40], r9
0x140044927  mov     rdi, rdx
0x14004492a  mov     r9, rdx
0x14004492d  mov     byte ptr [rcx+1Ch], 1
0x140044931  mov     r8, rdx
0x140044934  mov     dword ptr [rsp+68h+var_48], ebx
0x140044938  lea     rdx, aSelect1FromWSq; "SELECT 1 FROM \"%w\".sqlite_master WHER"...
0x14004493f  mov     rsi, rcx
0x140044942  call    sqlite3NestedParse
0x140044947  test    ebx, ebx
0x140044949  jnz     short loc_140044965
0x14004494b  mov     r9, rbp
0x14004494e  mov     dword ptr [rsp+68h+var_48], r14d
0x140044953  mov     r8, rdi
0x140044956  lea     rdx, aSelect1FromTem; "SELECT 1 FROM temp.sqlite_master WHERE "...
0x14004495d  mov     rcx, rsi
0x140044960  call    sqlite3NestedParse
0x140044965  add     rsp, 40h
0x140044969  pop     r14
0x14004496b  pop     rdi
0x14004496c  pop     rsi
0x14004496d  pop     rbp
0x14004496e  pop     rbx
0x14004496f  retn
```

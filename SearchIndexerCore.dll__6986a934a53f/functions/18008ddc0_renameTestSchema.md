# renameTestSchema

- ea: `0x18008ddc0`
- end: `0x18008de2c`
- name: `renameTestSchema`
- size: `108`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180072cf0`
- `0x180073c34`
- `0x18008f450`

## callees

- `0x18004a9b8`
- `0x18008ddc0`

## string_xrefs

- `0x18008ddf4`: `SELECT 1 FROM "%w".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL `
- `0x18008de12`: `SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL `

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
0x18008ddc0  push    rbx
0x18008ddc2  push    rbp
0x18008ddc3  push    rsi
0x18008ddc4  push    rdi
0x18008ddc5  push    r14
0x18008ddc7  sub     rsp, 40h
0x18008ddcb  mov     r14d, [rsp+68h+arg_20]
0x18008ddd3  mov     ebx, r8d
0x18008ddd6  mov     [rsp+68h+var_38], r14d
0x18008dddb  mov     rbp, r9
0x18008ddde  mov     [rsp+68h+var_40], r9
0x18008dde3  mov     rdi, rdx
0x18008dde6  mov     r9, rdx
0x18008dde9  mov     byte ptr [rcx+1Ch], 1
0x18008dded  mov     r8, rdx
0x18008ddf0  mov     dword ptr [rsp+68h+var_48], ebx
0x18008ddf4  lea     rdx, aSelect1FromWSq; "SELECT 1 FROM \"%w\".sqlite_master WHER"...
0x18008ddfb  mov     rsi, rcx
0x18008ddfe  call    sqlite3NestedParse
0x18008de03  test    ebx, ebx
0x18008de05  jnz     short loc_18008DE21
0x18008de07  mov     r9, rbp
0x18008de0a  mov     dword ptr [rsp+68h+var_48], r14d
0x18008de0f  mov     r8, rdi
0x18008de12  lea     rdx, aSelect1FromTem; "SELECT 1 FROM temp.sqlite_master WHERE "...
0x18008de19  mov     rcx, rsi
0x18008de1c  call    sqlite3NestedParse
0x18008de21  add     rsp, 40h
0x18008de25  pop     r14
0x18008de27  pop     rdi
0x18008de28  pop     rsi
0x18008de29  pop     rbp
0x18008de2a  pop     rbx
0x18008de2b  retn
```

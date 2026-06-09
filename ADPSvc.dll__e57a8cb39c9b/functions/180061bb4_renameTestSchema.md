# renameTestSchema

- ea: `0x180061bb4`
- end: `0x180061c20`
- name: `renameTestSchema`
- size: `108`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18006799c`
- `0x1800682a4`
- `0x180068554`

## callees

- `0x180061bb4`
- `0x1800817f4`

## string_xrefs

- `0x180061be8`: `SELECT 1 FROM "%w".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL `
- `0x180061c06`: `SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL `

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
0x180061bb4  push    rbx
0x180061bb6  push    rbp
0x180061bb7  push    rsi
0x180061bb8  push    rdi
0x180061bb9  push    r14
0x180061bbb  sub     rsp, 40h
0x180061bbf  mov     r14d, [rsp+68h+arg_20]
0x180061bc7  mov     ebx, r8d
0x180061bca  mov     [rsp+68h+var_38], r14d
0x180061bcf  mov     rbp, r9
0x180061bd2  mov     [rsp+68h+var_40], r9
0x180061bd7  mov     rdi, rdx
0x180061bda  mov     r9, rdx
0x180061bdd  mov     byte ptr [rcx+1Ch], 1
0x180061be1  mov     r8, rdx
0x180061be4  mov     dword ptr [rsp+68h+var_48], ebx
0x180061be8  lea     rdx, aSelect1FromWSq; "SELECT 1 FROM \"%w\".sqlite_master WHER"...
0x180061bef  mov     rsi, rcx
0x180061bf2  call    sqlite3NestedParse
0x180061bf7  test    ebx, ebx
0x180061bf9  jnz     short loc_180061C15
0x180061bfb  mov     r9, rbp
0x180061bfe  mov     dword ptr [rsp+68h+var_48], r14d
0x180061c03  mov     r8, rdi
0x180061c06  lea     rdx, aSelect1FromTem; "SELECT 1 FROM temp.sqlite_master WHERE "...
0x180061c0d  mov     rcx, rsi
0x180061c10  call    sqlite3NestedParse
0x180061c15  add     rsp, 40h
0x180061c19  pop     r14
0x180061c1b  pop     rdi
0x180061c1c  pop     rsi
0x180061c1d  pop     rbp
0x180061c1e  pop     rbx
0x180061c1f  retn
```

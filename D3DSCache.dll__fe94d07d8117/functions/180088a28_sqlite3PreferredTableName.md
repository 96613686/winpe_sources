# sqlite3PreferredTableName

- ea: `0x180088a28`
- end: `0x180088a86`
- name: `sqlite3PreferredTableName`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016bf4`

## callees

- `0x18002e290`
- `0x1800367a0`
- `0x180088a28`

## string_xrefs

- `0x180088a72`: `sqlite_temp_schema`

## pseudocode

```c
const char *__fastcall sqlite3PreferredTableName(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx

  v1 = a1;
  if ( !(unsigned int)sqlite3_strnicmp(a1, "sqlite_", 7) )
  {
    if ( !(unsigned int)sqlite3StrICmp(v1 + 7, "master") )
      return "sqlite_schema";
    if ( !(unsigned int)sqlite3StrICmp(v2, "temp_master") )
      return "sqlite_temp_schema";
  }
  return (const char *)v1;
}

```

## disassembly

```asm
0x180088a28  push    rbx
0x180088a2a  sub     rsp, 20h
0x180088a2e  mov     r8d, 7
0x180088a34  lea     rdx, aSqlite_0; "sqlite_"
0x180088a3b  mov     rbx, rcx
0x180088a3e  call    sqlite3_strnicmp
0x180088a43  test    eax, eax
0x180088a45  jnz     short loc_180088A7D
0x180088a47  lea     rcx, [rbx+7]
0x180088a4b  lea     rdx, aSqliteMaster+7; "master"
0x180088a52  call    sqlite3StrICmp
0x180088a57  test    eax, eax
0x180088a59  jnz     short loc_180088A64
0x180088a5b  lea     rax, aSqliteSchema; "sqlite_schema"
0x180088a62  jmp     short loc_180088A80
0x180088a64  lea     rdx, aSqliteTempMast+7; "temp_master"
0x180088a6b  call    sqlite3StrICmp
0x180088a70  test    eax, eax
0x180088a72  lea     rcx, aSqliteTempSche; "sqlite_temp_schema"
0x180088a79  cmovz   rbx, rcx
0x180088a7d  mov     rax, rbx
0x180088a80  add     rsp, 20h
0x180088a84  pop     rbx
0x180088a85  retn
```

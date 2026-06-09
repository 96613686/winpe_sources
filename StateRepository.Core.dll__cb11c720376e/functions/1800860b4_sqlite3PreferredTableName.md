# sqlite3PreferredTableName

- ea: `0x1800860b4`
- end: `0x180086116`
- name: `sqlite3PreferredTableName`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180050420`

## callees

- `0x1800143f0`
- `0x18004b050`
- `0x1800860b4`

## string_xrefs

- `0x180086102`: `sqlite_temp_schema`

## pseudocode

```c
const char *__fastcall sqlite3PreferredTableName(__int64 a1)
{
  __int64 v1; // rbx

  v1 = a1;
  if ( !(unsigned int)sqlite3_strnicmp(a1, "sqlite_", 7) )
  {
    if ( !(unsigned int)sqlite3StrICmp(v1 + 7, "master") )
      return "sqlite_schema";
    if ( !(unsigned int)sqlite3StrICmp(v1 + 7, "temp_master") )
      return "sqlite_temp_schema";
  }
  return (const char *)v1;
}

```

## disassembly

```asm
0x1800860b4  push    rbx
0x1800860b6  sub     rsp, 20h
0x1800860ba  mov     r8d, 7
0x1800860c0  lea     rdx, aSqlite_0; "sqlite_"
0x1800860c7  mov     rbx, rcx
0x1800860ca  call    sqlite3_strnicmp
0x1800860cf  test    eax, eax
0x1800860d1  jnz     short loc_18008610D
0x1800860d3  lea     rdx, aSqliteMaster+7; "master"
0x1800860da  lea     rcx, [rbx+7]
0x1800860de  call    sqlite3StrICmp
0x1800860e3  test    eax, eax
0x1800860e5  jnz     short loc_1800860F0
0x1800860e7  lea     rax, aSqliteSchema; "sqlite_schema"
0x1800860ee  jmp     short loc_180086110
0x1800860f0  lea     rdx, aSqliteTempMast+7; "temp_master"
0x1800860f7  lea     rcx, [rbx+7]
0x1800860fb  call    sqlite3StrICmp
0x180086100  test    eax, eax
0x180086102  lea     rcx, aSqliteTempSche; "sqlite_temp_schema"
0x180086109  cmovz   rbx, rcx
0x18008610d  mov     rax, rbx
0x180086110  add     rsp, 20h
0x180086114  pop     rbx
0x180086115  retn
```

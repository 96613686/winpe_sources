# StateRepository::Database::GetLastInsertRowID(void)

- ea: `0x180018e9c`
- end: `0x180018ee7`
- name: `?GetLastInsertRowID@Database@StateRepository@@QEBA_JXZ`
- size: `75`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b1fc`
- `0x180021770`

## callees

- `0x1800194a4`

## import_xrefs

- `StateRepository.Core!sqlite3_last_insert_rowid` at `0x180018ee0`

## string_xrefs

- `0x180018eb2`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018ea6`: `GetLastInsertRowID() called but !db.IsOpen()`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::GetLastInsertRowID(StateRepository::Database *this)
{
  int v3; // [rsp+20h] [rbp-18h]
  const char *v4; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LOBYTE(v3) = *(_QWORD *)this == 0;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x6C0,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)0x8007139FLL,
    v3,
    (bool)"GetLastInsertRowID() called but !db.IsOpen()",
    v4);
  return sqlite3_last_insert_rowid(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180018e9c  push    rbx; char *
0x180018e9e  sub     rsp, 30h
0x180018ea2  cmp     qword ptr [rcx], 0
0x180018ea6  lea     rdx, aGetlastinsertr; "GetLastInsertRowID() called but !db.IsO"...
0x180018ead  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180018eb2  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018eb9  setz    al
0x180018ebc  mov     rbx, rcx
0x180018ebf  mov     rcx, [rsp+38h]; this
0x180018ec4  mov     r9d, 8007139Fh; char *
0x180018eca  mov     edx, 6C0h; void *
0x180018ecf  mov     byte ptr [rsp+38h+var_18], al; int
0x180018ed3  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180018ed8  mov     rcx, [rbx]
0x180018edb  add     rsp, 30h
0x180018edf  pop     rbx
0x180018ee0  jmp     cs:__imp_sqlite3_last_insert_rowid
```

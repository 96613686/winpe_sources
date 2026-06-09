# StateRepository::Database::GetChanges(void)

- ea: `0x180018e04`
- end: `0x180018e4f`
- name: `?GetChanges@Database@StateRepository@@QEBAHXZ`
- size: `75`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cf88`
- `0x18001df68`
- `0x18001e0c8`
- `0x18001ed34`
- `0x18001f1c8`
- `0x18001fafc`
- `0x180020108`
- `0x180022d2c`
- `0x180025b24`

## callees

- `0x1800194a4`

## import_xrefs

- `StateRepository.Core!sqlite3_changes` at `0x180018e48`

## string_xrefs

- `0x180018e1a`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018e0e`: `GetChanges() called but !db.IsOpen()`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::GetChanges(StateRepository::Database *this)
{
  int v3; // [rsp+20h] [rbp-18h]
  const char *v4; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LOBYTE(v3) = *(_QWORD *)this == 0;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x6B2,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)0x8007139FLL,
    v3,
    (bool)"GetChanges() called but !db.IsOpen()",
    v4);
  return sqlite3_changes(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180018e04  push    rbx; char *
0x180018e06  sub     rsp, 30h
0x180018e0a  cmp     qword ptr [rcx], 0
0x180018e0e  lea     rdx, aGetchangesCall; "GetChanges() called but !db.IsOpen()"
0x180018e15  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180018e1a  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018e21  setz    al
0x180018e24  mov     rbx, rcx
0x180018e27  mov     rcx, [rsp+38h]; this
0x180018e2c  mov     r9d, 8007139Fh; char *
0x180018e32  mov     edx, 6B2h; void *
0x180018e37  mov     byte ptr [rsp+38h+var_18], al; int
0x180018e3b  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180018e40  mov     rcx, [rbx]
0x180018e43  add     rsp, 30h
0x180018e47  pop     rbx
0x180018e48  jmp     cs:__imp_sqlite3_changes
```

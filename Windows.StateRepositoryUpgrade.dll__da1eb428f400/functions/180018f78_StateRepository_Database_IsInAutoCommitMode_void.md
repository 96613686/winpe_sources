# StateRepository::Database::IsInAutoCommitMode(void)

- ea: `0x180018f78`
- end: `0x180018fc8`
- name: `?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ`
- size: `80`
- prototype: `bool __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `28`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bb64`
- `0x18001b164`
- `0x18001c950`
- `0x18001cc04`
- `0x18001cc98`
- `0x18001cf88`
- `0x18001d990`
- `0x18001de14`
- `0x18001dea8`
- `0x18001df68`
- `0x18001e89c`
- `0x18001e958`
- `0x18001ebe0`
- `0x18001ec74`
- `0x18001ed34`
- `0x18001f724`
- `0x180020058`
- `0x180020664`
- `0x180021688`
- `0x180021f50`
- `0x18002216c`
- `0x180022d2c`
- `0x180022ec4`
- `0x180025070`
- `0x180025658`
- `0x180025840`
- `0x180026080`
- `0x180026118`

## callees

- `0x1800194a4`

## import_xrefs

- `StateRepository.Core!sqlite3_get_autocommit` at `0x180018fb7`
- `StateRepository.Core!sqlite3_get_autocommit` at `0x180018fb7`

## string_xrefs

- `0x180018f8e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018f82`: `IsInAutoCommitMode() called but !db.IsOpen()`

## pseudocode

```c
bool __fastcall StateRepository::Database::IsInAutoCommitMode(StateRepository::Database *this)
{
  int v3; // [rsp+20h] [rbp-18h]
  const char *v4; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LOBYTE(v3) = *(_QWORD *)this == 0;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x1D2,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)0x8007139FLL,
    v3,
    (bool)"IsInAutoCommitMode() called but !db.IsOpen()",
    v4);
  return (unsigned int)sqlite3_get_autocommit(*(_QWORD *)this) != 0;
}

```

## disassembly

```asm
0x180018f78  push    rbx; char *
0x180018f7a  sub     rsp, 30h
0x180018f7e  cmp     qword ptr [rcx], 0
0x180018f82  lea     rdx, aIsinautocommit; "IsInAutoCommitMode() called but !db.IsO"...
0x180018f89  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180018f8e  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018f95  setz    al
0x180018f98  mov     rbx, rcx
0x180018f9b  mov     rcx, [rsp+38h]; this
0x180018fa0  mov     r9d, 8007139Fh; char *
0x180018fa6  mov     edx, 1D2h; void *
0x180018fab  mov     byte ptr [rsp+38h+var_18], al; int
0x180018faf  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180018fb4  mov     rcx, [rbx]
0x180018fb7  call    cs:__imp_sqlite3_get_autocommit
0x180018fbd  test    eax, eax
0x180018fbf  setnz   al
0x180018fc2  add     rsp, 30h
0x180018fc6  pop     rbx
0x180018fc7  retn
```

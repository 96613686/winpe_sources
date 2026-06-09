# StateRepository::Statement::Bind(int,int)

- ea: `0x18001b5dc`
- end: `0x18001b643`
- name: `?Bind@Statement@StateRepository@@QEAAJHH@Z`
- size: `103`
- prototype: `__int64 __fastcall(StateRepository::Statement *__hidden this, int, int)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b1fc`
- `0x18001d708`
- `0x18001e0c8`
- `0x18001f1c8`
- `0x18001fafc`
- `0x180021770`
- `0x18002216c`
- `0x180022330`
- `0x1800223c0`
- `0x180022d2c`
- `0x180025b24`

## callees

- `0x18000a3c0`
- `0x180014ca0`
- `0x18001b5dc`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int` at `0x18001b62c`
- `StateRepository.Core!sqlite3_bind_int` at `0x18001b62c`

## string_xrefs

- `0x18001b5e9`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001b60e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Statement::Bind(StateRepository::Statement *this, int a2)
{
  __int64 result; // rax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      v3);
  if ( *(_QWORD *)this )
  {
    result = sqlite3_bind_int();
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x87AF0000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v3);
    return 2147947423LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001b5dc  sub     rsp, 28h
0x18001b5e0  test    edx, edx
0x18001b5e2  jns     short loc_18001B601
0x18001b5e4  mov     rcx, [rsp+28h]; this
0x18001b5e9  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b5f0  mov     r9d, 80070057h; char *
0x18001b5f6  mov     edx, 0A1h; void *
0x18001b5fb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001b601  mov     rcx, [rcx]
0x18001b604  test    rcx, rcx
0x18001b607  jnz     short loc_18001B62C
0x18001b609  mov     rcx, [rsp+28h]; this
0x18001b60e  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b615  mov     r9d, 8007139Fh; char *
0x18001b61b  mov     edx, 0A3h; void *
0x18001b620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b625  mov     eax, 8007139Fh
0x18001b62a  jmp     short loc_18001B63E
0x18001b62c  call    cs:__imp_sqlite3_bind_int
0x18001b632  test    eax, eax
0x18001b634  jle     short loc_18001B63E
0x18001b636  movzx   eax, ax
0x18001b639  or      eax, 87AF0000h
0x18001b63e  add     rsp, 28h
0x18001b642  retn
```

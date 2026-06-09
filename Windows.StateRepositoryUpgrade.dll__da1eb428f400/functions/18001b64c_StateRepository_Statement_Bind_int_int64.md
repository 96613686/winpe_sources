# StateRepository::Statement::Bind(int,__int64)

- ea: `0x18001b64c`
- end: `0x18001b6b3`
- name: `?Bind@Statement@StateRepository@@QEAAJH_J@Z`
- size: `103`
- prototype: `__int64 __fastcall(StateRepository::Statement *__hidden this, int, __int64)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b1fc`
- `0x18001b810`
- `0x18001c900`
- `0x18001cf88`
- `0x18001df68`
- `0x18001e0c8`
- `0x18001ed34`
- `0x18001f1c8`
- `0x18001fafc`
- `0x180020108`
- `0x180021770`
- `0x180022d2c`
- `0x1800257f0`
- `0x180025b24`
- `0x180029de4`
- `0x180029f90`
- `0x18002a160`

## callees

- `0x18000a3c0`
- `0x180014ca0`
- `0x18001b64c`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int64` at `0x18001b69c`
- `StateRepository.Core!sqlite3_bind_int64` at `0x18001b69c`

## string_xrefs

- `0x18001b659`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001b67e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

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
      (void *)0xC7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      v3);
  if ( *(_QWORD *)this )
  {
    result = sqlite3_bind_int64();
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x87AF0000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
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
0x18001b64c  sub     rsp, 28h
0x18001b650  test    edx, edx
0x18001b652  jns     short loc_18001B671
0x18001b654  mov     rcx, [rsp+28h]; this
0x18001b659  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b660  mov     r9d, 80070057h; char *
0x18001b666  mov     edx, 0C7h; void *
0x18001b66b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001b671  mov     rcx, [rcx]
0x18001b674  test    rcx, rcx
0x18001b677  jnz     short loc_18001B69C
0x18001b679  mov     rcx, [rsp+28h]; this
0x18001b67e  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b685  mov     r9d, 8007139Fh; char *
0x18001b68b  mov     edx, 0C9h; void *
0x18001b690  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b695  mov     eax, 8007139Fh
0x18001b69a  jmp     short loc_18001B6AE
0x18001b69c  call    cs:__imp_sqlite3_bind_int64
0x18001b6a2  test    eax, eax
0x18001b6a4  jle     short loc_18001B6AE
0x18001b6a6  movzx   eax, ax
0x18001b6a9  or      eax, 87AF0000h
0x18001b6ae  add     rsp, 28h
0x18001b6b2  retn
```

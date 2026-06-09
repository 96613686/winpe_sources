# StateRepository::Statement::BindAddress(int,int,void const *)

- ea: `0x18001b6d0`
- end: `0x18001b749`
- name: `?BindAddress@Statement@StateRepository@@QEAAJHHPEBX@Z`
- size: `121`
- prototype: `__int64 __fastcall(StateRepository::Statement *__hidden this, int, int, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b7cc`

## callees

- `0x18000a3c0`
- `0x180014ca0`
- `0x18001b6d0`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_blob` at `0x18001b732`
- `StateRepository.Core!sqlite3_bind_blob` at `0x18001b732`

## string_xrefs

- `0x18001b6e0`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001b705`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Statement::BindAddress(
        StateRepository::Statement *this,
        __int64 a2,
        unsigned int a3,
        const void *a4)
{
  __int64 v4; // rcx
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (int)a2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      v6);
  v4 = *(_QWORD *)this;
  if ( v4 )
  {
    result = sqlite3_bind_blob(v4, a2, a4, a3, 0);
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x87AF0000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v6);
    return 2147947423LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001b6d0  sub     rsp, 38h
0x18001b6d4  mov     rax, r9
0x18001b6d7  test    edx, edx
0x18001b6d9  jns     short loc_18001B6F8
0x18001b6db  mov     rcx, [rsp+38h]; this
0x18001b6e0  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b6e7  mov     r9d, 80070057h; char *
0x18001b6ed  mov     edx, 1E2h; void *
0x18001b6f2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001b6f8  mov     rcx, [rcx]
0x18001b6fb  test    rcx, rcx
0x18001b6fe  jnz     short loc_18001B723
0x18001b700  mov     rcx, [rsp+38h]; this
0x18001b705  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b70c  mov     r9d, 8007139Fh; char *
0x18001b712  mov     edx, 1E4h; void *
0x18001b717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b71c  mov     eax, 8007139Fh
0x18001b721  jmp     short loc_18001B744
0x18001b723  mov     r9d, r8d
0x18001b726  mov     qword ptr [rsp+38h+var_18], 0
0x18001b72f  mov     r8, rax
0x18001b732  call    cs:__imp_sqlite3_bind_blob
0x18001b738  test    eax, eax
0x18001b73a  jle     short loc_18001B744
0x18001b73c  movzx   eax, ax
0x18001b73f  or      eax, 87AF0000h
0x18001b744  add     rsp, 38h
0x18001b748  retn
```

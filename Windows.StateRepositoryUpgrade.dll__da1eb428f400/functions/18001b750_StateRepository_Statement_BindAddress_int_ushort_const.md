# StateRepository::Statement::BindAddress(int,ushort const *)

- ea: `0x18001b750`
- end: `0x18001b7c4`
- name: `?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z`
- size: `116`
- prototype: `__int64 __fastcall(StateRepository::Statement *__hidden this, int, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b1fc`
- `0x18001d708`
- `0x18001e0c8`
- `0x18001f1c8`
- `0x18001fafc`
- `0x180020108`
- `0x180021720`
- `0x180021770`
- `0x180025020`
- `0x180025b24`

## callees

- `0x18000a3c0`
- `0x180014ca0`
- `0x18001b750`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_text16` at `0x18001b7ad`
- `StateRepository.Core!sqlite3_bind_text16` at `0x18001b7ad`

## string_xrefs

- `0x18001b75d`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001b782`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Statement::BindAddress(
        StateRepository::Statement *this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rcx
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (int)a2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x80070057LL,
      v5);
  v3 = *(_QWORD *)this;
  if ( v3 )
  {
    result = sqlite3_bind_text16(v3, a2, a3, 0xFFFFFFFFLL, 0);
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x87AF0000;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v5);
    return 2147947423LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001b750  sub     rsp, 38h
0x18001b754  test    edx, edx
0x18001b756  jns     short loc_18001B775
0x18001b758  mov     rcx, [rsp+38h]; this
0x18001b75d  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b764  mov     r9d, 80070057h; char *
0x18001b76a  mov     edx, 1B6h; void *
0x18001b76f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001b775  mov     rcx, [rcx]
0x18001b778  test    rcx, rcx
0x18001b77b  jnz     short loc_18001B7A0
0x18001b77d  mov     rcx, [rsp+38h]; this
0x18001b782  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001b789  mov     r9d, 8007139Fh; char *
0x18001b78f  mov     edx, 1B8h; void *
0x18001b794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b799  mov     eax, 8007139Fh
0x18001b79e  jmp     short loc_18001B7BF
0x18001b7a0  or      r9d, 0FFFFFFFFh
0x18001b7a4  mov     qword ptr [rsp+38h+var_18], 0
0x18001b7ad  call    cs:__imp_sqlite3_bind_text16
0x18001b7b3  test    eax, eax
0x18001b7b5  jle     short loc_18001B7BF
0x18001b7b7  movzx   eax, ax
0x18001b7ba  or      eax, 87AF0000h
0x18001b7bf  add     rsp, 38h
0x18001b7c3  retn
```

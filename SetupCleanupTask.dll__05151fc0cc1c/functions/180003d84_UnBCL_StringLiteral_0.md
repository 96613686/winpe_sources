# UnBCL::_::StringLiteral_0_

- ea: `0x180003d84`
- end: `0x180003dc6`
- name: `UnBCL::_::StringLiteral_0_`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c90`

## callees

- `0x180003d84`

## import_xrefs

- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x180003da5`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x180003da5`

## string_xrefs

- `0x180003d97`: `attempt to StreamRead on non-larval Array instance`

## pseudocode

```c
__int64 __fastcall UnBCL::_::StringLiteral_0_(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  if ( qword_180052E58 )
  {
    LODWORD(v4) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&v4);
  }
  else
  {
    UnBCL::_::SetLiteralStorage(
      (UnBCL::_ *)&qword_180052E58,
      (const struct UnBCL::String **)L"attempt to StreamRead on non-larval Array instance",
      a3);
  }
  return qword_180052E58;
}

```

## disassembly

```asm
0x180003d84  mov     [rsp+arg_0], rcx
0x180003d89  sub     rsp, 28h
0x180003d8d  cmp     cs:qword_180052E58, 0
0x180003d95  jnz     short loc_180003DAD
0x180003d97  lea     rdx, aAttemptToStrea; "attempt to StreamRead on non-larval Arr"...
0x180003d9e  lea     rcx, qword_180052E58
0x180003da5  call    cs:__imp_?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z; UnBCL::_::SetLiteralStorage(UnBCL::String const * *,ushort const *)
0x180003dab  jmp     short loc_180003DBA
0x180003dad  mov     dword ptr [rsp+28h+arg_0], 0
0x180003db5  lock inc dword ptr [rsp+28h+arg_0]
0x180003dba  mov     rax, cs:qword_180052E58
0x180003dc1  add     rsp, 28h
0x180003dc5  retn
```

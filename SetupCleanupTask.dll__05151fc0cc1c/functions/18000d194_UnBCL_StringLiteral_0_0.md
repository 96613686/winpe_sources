# UnBCL::_::StringLiteral_0__0

- ea: `0x18000d194`
- end: `0x18000d1d6`
- name: `UnBCL::_::StringLiteral_0__0`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800104b0`

## callees

- `0x18000d194`

## import_xrefs

- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d1b5`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d1b5`

## string_xrefs

- `0x18000d1a7`: `attempt to StreamRead on non-larval Array instance`

## pseudocode

```c
__int64 __fastcall UnBCL::_::StringLiteral_0__0(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  if ( qword_180052E68 )
  {
    LODWORD(v4) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&v4);
  }
  else
  {
    UnBCL::_::SetLiteralStorage(
      (UnBCL::_ *)&qword_180052E68,
      (const struct UnBCL::String **)L"attempt to StreamRead on non-larval Array instance",
      a3);
  }
  return qword_180052E68;
}

```

## disassembly

```asm
0x18000d194  mov     [rsp+arg_0], rcx
0x18000d199  sub     rsp, 28h
0x18000d19d  cmp     cs:qword_180052E68, 0
0x18000d1a5  jnz     short loc_18000D1BD
0x18000d1a7  lea     rdx, aAttemptToStrea; "attempt to StreamRead on non-larval Arr"...
0x18000d1ae  lea     rcx, qword_180052E68
0x18000d1b5  call    cs:__imp_?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z; UnBCL::_::SetLiteralStorage(UnBCL::String const * *,ushort const *)
0x18000d1bb  jmp     short loc_18000D1CA
0x18000d1bd  mov     dword ptr [rsp+28h+arg_0], 0
0x18000d1c5  lock inc dword ptr [rsp+28h+arg_0]
0x18000d1ca  mov     rax, cs:qword_180052E68
0x18000d1d1  add     rsp, 28h
0x18000d1d5  retn
```

# UnBCL::_::StringLiteral_1_

- ea: `0x18000d0bc`
- end: `0x18000d0fe`
- name: `UnBCL::_::StringLiteral_1_`
- size: `66`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013dd8`

## callees

- `0x18000d0bc`

## import_xrefs

- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d0dd`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d0dd`

## string_xrefs

- `0x18000d0cf`: `Path too long on Win9x`

## pseudocode

```c
__int64 __fastcall UnBCL::_::StringLiteral_1_(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  if ( qword_180052E88 )
  {
    LODWORD(v4) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&v4);
  }
  else
  {
    UnBCL::_::SetLiteralStorage(
      (UnBCL::_ *)&qword_180052E88,
      (const struct UnBCL::String **)L"Path too long on Win9x",
      a3);
  }
  return qword_180052E88;
}

```

## disassembly

```asm
0x18000d0bc  mov     [rsp+arg_0], rcx
0x18000d0c1  sub     rsp, 28h
0x18000d0c5  cmp     cs:qword_180052E88, 0
0x18000d0cd  jnz     short loc_18000D0E5
0x18000d0cf  lea     rdx, aPathTooLongOnW; "Path too long on Win9x"
0x18000d0d6  lea     rcx, qword_180052E88
0x18000d0dd  call    cs:__imp_?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z; UnBCL::_::SetLiteralStorage(UnBCL::String const * *,ushort const *)
0x18000d0e3  jmp     short loc_18000D0F2
0x18000d0e5  mov     dword ptr [rsp+28h+arg_0], 0
0x18000d0ed  lock inc dword ptr [rsp+28h+arg_0]
0x18000d0f2  mov     rax, cs:qword_180052E88
0x18000d0f9  add     rsp, 28h
0x18000d0fd  retn
```

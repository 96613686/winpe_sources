# UnBCL::_::StringLiteral_3_

- ea: `0x18000d14c`
- end: `0x18000d18e`
- name: `UnBCL::_::StringLiteral_3_`
- size: `66`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013dd8`

## callees

- `0x18000d14c`

## import_xrefs

- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d16d`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d16d`

## string_xrefs

- `0x18000d15f`: `Path too long on NT/2k+`

## pseudocode

```c
__int64 __fastcall UnBCL::_::StringLiteral_3_(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  if ( qword_180052E78 )
  {
    LODWORD(v4) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&v4);
  }
  else
  {
    UnBCL::_::SetLiteralStorage(
      (UnBCL::_ *)&qword_180052E78,
      (const struct UnBCL::String **)L"Path too long on NT/2k+",
      a3);
  }
  return qword_180052E78;
}

```

## disassembly

```asm
0x18000d14c  mov     [rsp+arg_0], rcx
0x18000d151  sub     rsp, 28h
0x18000d155  cmp     cs:qword_180052E78, 0
0x18000d15d  jnz     short loc_18000D175
0x18000d15f  lea     rdx, aPathTooLongOnN; "Path too long on NT/2k+"
0x18000d166  lea     rcx, qword_180052E78
0x18000d16d  call    cs:__imp_?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z; UnBCL::_::SetLiteralStorage(UnBCL::String const * *,ushort const *)
0x18000d173  jmp     short loc_18000D182
0x18000d175  mov     dword ptr [rsp+28h+arg_0], 0
0x18000d17d  lock inc dword ptr [rsp+28h+arg_0]
0x18000d182  mov     rax, cs:qword_180052E78
0x18000d189  add     rsp, 28h
0x18000d18d  retn
```

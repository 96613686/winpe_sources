# UnBCL::_::StringLiteral_2_

- ea: `0x18000d104`
- end: `0x18000d146`
- name: `UnBCL::_::StringLiteral_2_`
- size: `66`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013dd8`

## callees

- `0x18000d104`

## import_xrefs

- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d125`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x18000d125`

## string_xrefs

- `0x18000d117`: `Long-prefixed path too long on NT/2k+`

## pseudocode

```c
__int64 __fastcall UnBCL::_::StringLiteral_2_(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  if ( qword_180052E80 )
  {
    LODWORD(v4) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&v4);
  }
  else
  {
    UnBCL::_::SetLiteralStorage(
      (UnBCL::_ *)&qword_180052E80,
      (const struct UnBCL::String **)L"Long-prefixed path too long on NT/2k+",
      a3);
  }
  return qword_180052E80;
}

```

## disassembly

```asm
0x18000d104  mov     [rsp+arg_0], rcx
0x18000d109  sub     rsp, 28h
0x18000d10d  cmp     cs:qword_180052E80, 0
0x18000d115  jnz     short loc_18000D12D
0x18000d117  lea     rdx, aLongPrefixedPa; "Long-prefixed path too long on NT/2k+"
0x18000d11e  lea     rcx, qword_180052E80
0x18000d125  call    cs:__imp_?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z; UnBCL::_::SetLiteralStorage(UnBCL::String const * *,ushort const *)
0x18000d12b  jmp     short loc_18000D13A
0x18000d12d  mov     dword ptr [rsp+28h+arg_0], 0
0x18000d135  lock inc dword ptr [rsp+28h+arg_0]
0x18000d13a  mov     rax, cs:qword_180052E80
0x18000d141  add     rsp, 28h
0x18000d145  retn
```

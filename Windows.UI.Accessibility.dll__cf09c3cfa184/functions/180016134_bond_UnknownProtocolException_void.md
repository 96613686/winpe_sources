# bond::UnknownProtocolException(void)

- ea: `0x180016134`
- end: `0x180016196`
- name: `?UnknownProtocolException@bond@@YAXXZ`
- size: `98`
- prototype: `void __fastcall __noreturn(bond *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012110`
- `0x180019124`
- `0x18001f4c8`

## callees

- `0x1800050da`
- `0x18001274c`
- `0x180012a80`
- `0x180013a84`

## string_xrefs

- `0x180016158`: `Unmarshaling failed: unsupported protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn bond::UnknownProtocolException(bond *this)
{
  __int64 v1; // rax
  __int64 v2; // rax
  _QWORD pExceptionObject[8]; // [rsp+20h] [rbp-4A8h] BYREF
  _BYTE v4[1104]; // [rsp+60h] [rbp-468h] BYREF

  v1 = bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(v4);
  v2 = bond::detail::basic_string_stream<1024>::operator<<(v1, "Unmarshaling failed: unsupported protocol");
  bond::Exception::Exception((bond::Exception *)pExceptionObject, *(const char **)(v2 + 1072));
  pExceptionObject[0] = &bond::StreamException::`vftable';
  throw (bond::CoreException *)pExceptionObject;
}

```

## disassembly

```asm
0x180016134  sub     rsp, 4C8h
0x18001613b  mov     rax, cs:__security_cookie
0x180016142  xor     rax, rsp
0x180016145  mov     [rsp+4C8h+var_18], rax
0x18001614d  lea     rcx, [rsp+4C8h+var_468]
0x180016152  call    ??0?$basic_string_stream@$0EAA@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(void)
0x180016157  nop
0x180016158  lea     rdx, aUnmarshalingFa; "Unmarshaling failed: unsupported protoc"...
0x18001615f  mov     rcx, rax
0x180016162  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x180016167  mov     rdx, [rax+430h]; char *
0x18001616e  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x180016173  call    ??0Exception@bond@@IEAA@PEBD@Z; bond::Exception::Exception(char const *)
0x180016178  lea     rax, ??_7StreamException@bond@@6B@; const bond::StreamException::`vftable'
0x18001617f  mov     [rsp+4C8h+pExceptionObject], rax
0x180016184  lea     rdx, _TI4?AUCoreException@bond@@; pThrowInfo
0x18001618b  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x180016190  call    _CxxThrowException_0
```

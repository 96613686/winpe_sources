# bond::UnknownProtocolException(void)

- ea: `0x180022594`
- end: `0x1800225f6`
- name: `?UnknownProtocolException@bond@@YAXXZ`
- size: `98`
- prototype: `void __fastcall __noreturn(bond *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`

## callees

- `0x180003fe0`
- `0x180019cf8`
- `0x18001a11c`
- `0x18001bae0`

## string_xrefs

- `0x1800225b8`: `Unmarshaling failed: unsupported protocol`

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
  pExceptionObject[0] = &bond::CoreException::`vftable';
  throw (bond::CoreException *)pExceptionObject;
}

```

## disassembly

```asm
0x180022594  sub     rsp, 4C8h
0x18002259b  mov     rax, cs:__security_cookie
0x1800225a2  xor     rax, rsp
0x1800225a5  mov     [rsp+4C8h+var_18], rax
0x1800225ad  lea     rcx, [rsp+4C8h+var_468]
0x1800225b2  call    ??0?$basic_string_stream@$0EAA@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(void)
0x1800225b7  nop
0x1800225b8  lea     rdx, aUnmarshalingFa; "Unmarshaling failed: unsupported protoc"...
0x1800225bf  mov     rcx, rax
0x1800225c2  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x1800225c7  mov     rdx, [rax+430h]; char *
0x1800225ce  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x1800225d3  call    ??0Exception@bond@@IEAA@PEBD@Z; bond::Exception::Exception(char const *)
0x1800225d8  lea     rax, ??_7CoreException@bond@@6B@; const bond::CoreException::`vftable'
0x1800225df  mov     [rsp+4C8h+pExceptionObject], rax
0x1800225e4  lea     rdx, _TI4?AUCoreException@bond@@; pThrowInfo
0x1800225eb  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x1800225f0  call    _CxxThrowException_0
```

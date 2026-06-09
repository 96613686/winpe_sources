# bond::UnknownProtocolException(void)

- ea: `0x18001b5a8`
- end: `0x18001b5ed`
- name: `?UnknownProtocolException@bond@@YAXXZ`
- size: `69`
- prototype: `void __fastcall __noreturn(bond *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ef9c`

## callees

- `0x180003318`
- `0x18000f78c`
- `0x18000fc00`
- `0x1800122a4`
- `0x18001e328`

## string_xrefs

- `0x18001b5b7`: `Unmarshaling failed: unsupported protocol`

## pseudocode

```c
void __fastcall __noreturn bond::UnknownProtocolException(bond *this)
{
  __int64 v1; // rax
  __int64 v2; // rax
  const char *v3; // rax
  _BYTE v4[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+38h] [rbp-40h] BYREF

  v1 = bond::detail::basic_string_stream<1024,std::allocator<char>>::basic_string_stream<1024,std::allocator<char>>(v4);
  v2 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(
         v1,
         "Unmarshaling failed: unsupported protocol");
  v3 = (const char *)bond::detail::basic_string_stream<1024,std::allocator<char>>::content(v2);
  bond::CoreException::CoreException((bond::CoreException *)pExceptionObject, v3);
  throw (bond::CoreException *)pExceptionObject;
}

```

## disassembly

```asm
0x18001b5a8  sub     rsp, 78h
0x18001b5ac  lea     rcx, [rsp+78h+var_58]
0x18001b5b1  call    ??0?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024,std::allocator<char>>::basic_string_stream<1024,std::allocator<char>>(void)
0x18001b5b6  nop
0x18001b5b7  lea     rdx, aUnmarshalingFa; "Unmarshaling failed: unsupported protoc"...
0x18001b5be  mov     rcx, rax
0x18001b5c1  call    ??6?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(char const *)
0x18001b5c6  mov     rcx, rax
0x18001b5c9  call    ?content@?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEBAPEBDXZ; bond::detail::basic_string_stream<1024,std::allocator<char>>::content(void)
0x18001b5ce  mov     rdx, rax; char *
0x18001b5d1  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001b5d6  call    ??0CoreException@bond@@QEAA@PEBD@Z; bond::CoreException::CoreException(char const *)
0x18001b5db  lea     rdx, _TI4?AUCoreException@bond@@; pThrowInfo
0x18001b5e2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001b5e7  call    _CxxThrowException_0
```

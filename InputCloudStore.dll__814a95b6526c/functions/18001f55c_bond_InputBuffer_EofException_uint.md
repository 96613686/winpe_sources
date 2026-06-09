# bond::InputBuffer::EofException(uint)

- ea: `0x18001f55c`
- end: `0x18001f607`
- name: `?EofException@InputBuffer@bond@@IEBAXI@Z`
- size: `171`
- prototype: `void __fastcall __noreturn(bond::InputBuffer *__hidden this, unsigned int)`
- caller_count: `50`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a4b0`
- `0x18000a540`
- `0x18000a5d0`
- `0x18000a690`
- `0x18000a760`
- `0x18000a804`
- `0x18000a8a8`
- `0x18000a94c`
- `0x18000a9f0`
- `0x18000aa94`
- `0x18000ab38`
- `0x18000ae24`
- `0x18000b3fc`
- `0x18000b79c`
- `0x18000ba0c`
- `0x18000ce44`
- `0x18000d8e4`
- `0x18000d9c4`
- `0x18000daa8`
- `0x18000dd18`
- `0x18000de00`
- `0x18000df8c`
- `0x18000e060`
- `0x18000e134`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000e3a4`
- `0x18000e564`
- `0x18000e728`
- `0x18000e7fc`
- `0x18000e9c0`
- `0x18000ea94`
- `0x18000eb64`
- `0x18000ec38`
- `0x18000ed0c`
- `0x18000ef58`
- `0x18000f194`
- `0x18000f334`
- `0x18000f4c8`
- `0x18000f61c`
- `0x18000f6ec`
- `0x18001bc40`
- `0x18001be18`
- `0x18001beec`
- `0x18001bfc0`
- `0x18001c088`
- `0x18001c15c`
- `0x18001c5c0`
- `0x18001c694`
- `0x180020960`

## callees

- `0x180003fe0`
- `0x180019cf8`
- `0x18001a11c`
- `0x18001ba7c`
- `0x18001bae0`

## string_xrefs

- `0x18001f58b`: `Read out of bounds: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn bond::InputBuffer::EofException(bond::InputBuffer *this, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD pExceptionObject[8]; // [rsp+20h] [rbp-4A8h] BYREF
  _BYTE v12[1104]; // [rsp+60h] [rbp-468h] BYREF

  v4 = bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(v12);
  v5 = bond::detail::basic_string_stream<1024>::operator<<(v4, "Read out of bounds: ");
  v6 = bond::detail::basic_string_stream<1024>::operator<<(v5, a2);
  v7 = bond::detail::basic_string_stream<1024>::operator<<(v6, " bytes requested, offset: ");
  v8 = bond::detail::basic_string_stream<1024>::operator<<(v7, *((unsigned int *)this + 8));
  v9 = bond::detail::basic_string_stream<1024>::operator<<(v8, ", length: ");
  v10 = bond::detail::basic_string_stream<1024>::operator<<(v9, *((unsigned int *)this + 6));
  bond::Exception::Exception((bond::Exception *)pExceptionObject, *(const char **)(v10 + 1072));
  pExceptionObject[0] = &bond::StreamException::`vftable';
  throw (bond::StreamException *)pExceptionObject;
}

```

## disassembly

```asm
0x18001f55c  mov     [rsp+arg_10], rbx
0x18001f561  push    rdi
0x18001f562  sub     rsp, 4C0h
0x18001f569  mov     rax, cs:__security_cookie
0x18001f570  xor     rax, rsp
0x18001f573  mov     [rsp+4C8h+var_18], rax
0x18001f57b  mov     ebx, edx
0x18001f57d  mov     rdi, rcx
0x18001f580  lea     rcx, [rsp+4C8h+var_468]
0x18001f585  call    ??0?$basic_string_stream@$0EAA@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(void)
0x18001f58a  nop
0x18001f58b  lea     rdx, aReadOutOfBound; "Read out of bounds: "
0x18001f592  mov     rcx, rax
0x18001f595  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x18001f59a  mov     edx, ebx
0x18001f59c  mov     rcx, rax
0x18001f59f  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x18001f5a4  lea     rdx, aBytesRequested; " bytes requested, offset: "
0x18001f5ab  mov     rcx, rax
0x18001f5ae  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x18001f5b3  mov     edx, [rdi+20h]
0x18001f5b6  mov     rcx, rax
0x18001f5b9  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x18001f5be  lea     rdx, aLength; ", length: "
0x18001f5c5  mov     rcx, rax
0x18001f5c8  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x18001f5cd  mov     edx, [rdi+18h]
0x18001f5d0  mov     rcx, rax
0x18001f5d3  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x18001f5d8  mov     rdx, [rax+430h]; char *
0x18001f5df  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x18001f5e4  call    ??0Exception@bond@@IEAA@PEBD@Z; bond::Exception::Exception(char const *)
0x18001f5e9  lea     rax, ??_7StreamException@bond@@6B@; const bond::StreamException::`vftable'
0x18001f5f0  mov     [rsp+4C8h+pExceptionObject], rax
0x18001f5f5  lea     rdx, _TI4?AUStreamException@bond@@; pThrowInfo
0x18001f5fc  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x18001f601  call    _CxxThrowException_0
```

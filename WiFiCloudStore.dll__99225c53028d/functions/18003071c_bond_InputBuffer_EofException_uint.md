# bond::InputBuffer::EofException(uint)

- ea: `0x18003071c`
- end: `0x1800307c7`
- name: `?EofException@InputBuffer@bond@@IEBAXI@Z`
- size: `171`
- prototype: `void __fastcall __noreturn(bond::InputBuffer *__hidden this, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x1800027d4`
- `0x180002834`
- `0x180002a00`
- `0x180002b30`
- `0x180002e70`
- `0x180003350`
- `0x180003d6c`
- `0x180004050`
- `0x180018f74`
- `0x18001aa20`
- `0x1800269f4`

## callees

- `0x18002aadc`
- `0x18002fa58`
- `0x18002fb60`
- `0x1800300c0`
- `0x180030124`

## string_xrefs

- `0x18003074b`: `Read out of bounds: `

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
0x18003071c  mov     [rsp+arg_10], rbx
0x180030721  push    rdi
0x180030722  sub     rsp, 4C0h
0x180030729  mov     rax, cs:__security_cookie
0x180030730  xor     rax, rsp
0x180030733  mov     [rsp+4C8h+var_18], rax
0x18003073b  mov     ebx, edx
0x18003073d  mov     rdi, rcx
0x180030740  lea     rcx, [rsp+4C8h+var_468]
0x180030745  call    ??0?$basic_string_stream@$0EAA@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(void)
0x18003074a  nop
0x18003074b  lea     rdx, aReadOutOfBound; "Read out of bounds: "
0x180030752  mov     rcx, rax
0x180030755  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x18003075a  mov     edx, ebx
0x18003075c  mov     rcx, rax
0x18003075f  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x180030764  lea     rdx, aBytesRequested; " bytes requested, offset: "
0x18003076b  mov     rcx, rax
0x18003076e  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x180030773  mov     edx, [rdi+20h]
0x180030776  mov     rcx, rax
0x180030779  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x18003077e  lea     rdx, aLength; ", length: "
0x180030785  mov     rcx, rax
0x180030788  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x18003078d  mov     edx, [rdi+18h]
0x180030790  mov     rcx, rax
0x180030793  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x180030798  mov     rdx, [rax+430h]; char *
0x18003079f  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x1800307a4  call    ??0Exception@bond@@IEAA@PEBD@Z; bond::Exception::Exception(char const *)
0x1800307a9  lea     rax, ??_7StreamException@bond@@6B@; const bond::StreamException::`vftable'
0x1800307b0  mov     [rsp+4C8h+pExceptionObject], rax
0x1800307b5  lea     rdx, _TI4?AUStreamException@bond@@; pThrowInfo
0x1800307bc  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x1800307c1  call    _CxxThrowException_0
```

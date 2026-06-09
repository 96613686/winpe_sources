# bond::InputBuffer::EofException(uint)

- ea: `0x18001466c`
- end: `0x180014714`
- name: `?EofException@InputBuffer@bond@@IEBAXI@Z`
- size: `168`
- prototype: `void __fastcall __noreturn(bond::InputBuffer *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a768`
- `0x18000ab04`
- `0x1800173f0`
- `0x180019808`

## callees

- `0x180003318`
- `0x1800098d0`
- `0x18000f78c`
- `0x18000fc74`
- `0x1800122a4`
- `0x18001e328`

## string_xrefs

- `0x180014687`: `Read or skip out of bounds: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn bond::InputBuffer::EofException(bond::InputBuffer *this, int a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  const char *v10; // rax
  int v11; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v12[24]; // [rsp+28h] [rbp-60h] BYREF
  _QWORD pExceptionObject[9]; // [rsp+40h] [rbp-48h] BYREF

  v11 = a2;
  v3 = bond::detail::basic_string_stream<1024,std::allocator<char>>::basic_string_stream<1024,std::allocator<char>>(v12);
  v4 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(v3, "Read or skip out of bounds: ");
  v5 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<<unsigned int>(v4, &v11);
  v6 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(v5, " bytes requested, offset: ");
  v7 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<<unsigned int>(v6, (char *)this + 24);
  v8 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(v7, ", length: ");
  v11 = *((_DWORD *)this + 4);
  v9 = bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<<unsigned int>(v8, &v11);
  v10 = (const char *)bond::detail::basic_string_stream<1024,std::allocator<char>>::content(v9);
  bond::Exception::Exception((bond::Exception *)pExceptionObject, v10);
  pExceptionObject[0] = &bond::StreamException::`vftable';
  throw (bond::StreamException *)pExceptionObject;
}

```

## disassembly

```asm
0x18001466c  push    rbx
0x18001466e  sub     rsp, 80h
0x180014675  mov     rbx, rcx
0x180014678  mov     [rsp+88h+var_68], edx
0x18001467c  lea     rcx, [rsp+88h+var_60]
0x180014681  call    ??0?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024,std::allocator<char>>::basic_string_stream<1024,std::allocator<char>>(void)
0x180014686  nop
0x180014687  lea     rdx, aReadOrSkipOutO; "Read or skip out of bounds: "
0x18001468e  mov     rcx, rax
0x180014691  call    ??6?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(char const *)
0x180014696  lea     rdx, [rsp+88h+var_68]
0x18001469b  mov     rcx, rax
0x18001469e  call    ??$?6I@?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@AEBI@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<<uint>(uint const &)
0x1800146a3  lea     rdx, aBytesRequested; " bytes requested, offset: "
0x1800146aa  mov     rcx, rax
0x1800146ad  call    ??6?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(char const *)
0x1800146b2  lea     rdx, [rbx+18h]
0x1800146b6  mov     rcx, rax
0x1800146b9  call    ??$?6I@?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@AEBI@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<<uint>(uint const &)
0x1800146be  lea     rdx, aLength; ", length: "
0x1800146c5  mov     rcx, rax
0x1800146c8  call    ??6?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<(char const *)
0x1800146cd  mov     ecx, [rbx+10h]
0x1800146d0  mov     [rsp+88h+var_68], ecx
0x1800146d4  lea     rdx, [rsp+88h+var_68]
0x1800146d9  mov     rcx, rax
0x1800146dc  call    ??$?6I@?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEAAAEAV012@AEBI@Z; bond::detail::basic_string_stream<1024,std::allocator<char>>::operator<<<uint>(uint const &)
0x1800146e1  mov     rcx, rax
0x1800146e4  call    ?content@?$basic_string_stream@$0EAA@V?$allocator@D@std@@@detail@bond@@QEBAPEBDXZ; bond::detail::basic_string_stream<1024,std::allocator<char>>::content(void)
0x1800146e9  mov     rdx, rax; char *
0x1800146ec  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800146f1  call    ??0Exception@bond@@IEAA@PEBD@Z; bond::Exception::Exception(char const *)
0x1800146f6  lea     rax, ??_7StreamException@bond@@6B@; const bond::StreamException::`vftable'
0x1800146fd  mov     [rsp+88h+pExceptionObject], rax
0x180014702  lea     rdx, _TI4?AUStreamException@bond@@; pThrowInfo
0x180014709  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001470e  call    _CxxThrowException_0
```

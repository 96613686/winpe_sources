# bond::InputBuffer::EofException(uint)

- ea: `0x180014278`
- end: `0x180014323`
- name: `?EofException@InputBuffer@bond@@IEBAXI@Z`
- size: `171`
- prototype: `void __fastcall __noreturn(bond::InputBuffer *__hidden this, unsigned int)`
- caller_count: `18`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f2ec`
- `0x18000f3b8`
- `0x18000fab0`
- `0x18000fbc0`
- `0x18000fca4`
- `0x18000fd78`
- `0x18000fe4c`
- `0x180010080`
- `0x180015508`
- `0x18001786c`
- `0x180017dd8`
- `0x180017ebc`
- `0x180017f90`
- `0x180018064`
- `0x1800182a0`
- `0x180018374`
- `0x180019790`
- `0x180019860`

## callees

- `0x1800050da`
- `0x18001274c`
- `0x180012a80`
- `0x180013a20`
- `0x180013a84`

## string_xrefs

- `0x1800142a7`: `Read out of bounds: `

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
0x180014278  mov     [rsp+arg_10], rbx
0x18001427d  push    rdi
0x18001427e  sub     rsp, 4C0h
0x180014285  mov     rax, cs:__security_cookie
0x18001428c  xor     rax, rsp
0x18001428f  mov     [rsp+4C8h+var_18], rax
0x180014297  mov     ebx, edx
0x180014299  mov     rdi, rcx
0x18001429c  lea     rcx, [rsp+4C8h+var_468]
0x1800142a1  call    ??0?$basic_string_stream@$0EAA@@detail@bond@@QEAA@XZ; bond::detail::basic_string_stream<1024>::basic_string_stream<1024>(void)
0x1800142a6  nop
0x1800142a7  lea     rdx, aReadOutOfBound; "Read out of bounds: "
0x1800142ae  mov     rcx, rax
0x1800142b1  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x1800142b6  mov     edx, ebx
0x1800142b8  mov     rcx, rax
0x1800142bb  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x1800142c0  lea     rdx, aBytesRequested; " bytes requested, offset: "
0x1800142c7  mov     rcx, rax
0x1800142ca  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x1800142cf  mov     edx, [rdi+20h]
0x1800142d2  mov     rcx, rax
0x1800142d5  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x1800142da  lea     rdx, aLength; ", length: "
0x1800142e1  mov     rcx, rax
0x1800142e4  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@PEBD@Z; bond::detail::basic_string_stream<1024>::operator<<(char const *)
0x1800142e9  mov     edx, [rdi+18h]
0x1800142ec  mov     rcx, rax
0x1800142ef  call    ??6?$basic_string_stream@$0EAA@@detail@bond@@QEAAAEAV012@I@Z; bond::detail::basic_string_stream<1024>::operator<<(uint)
0x1800142f4  mov     rdx, [rax+430h]; char *
0x1800142fb  lea     rcx, [rsp+4C8h+pExceptionObject]; this
0x180014300  call    ??0Exception@bond@@IEAA@PEBD@Z; bond::Exception::Exception(char const *)
0x180014305  lea     rax, ??_7StreamException@bond@@6B@; const bond::StreamException::`vftable'
0x18001430c  mov     [rsp+4C8h+pExceptionObject], rax
0x180014311  lea     rdx, _TI4?AUStreamException@bond@@; pThrowInfo
0x180014318  lea     rcx, [rsp+4C8h+pExceptionObject]; pExceptionObject
0x18001431d  call    _CxxThrowException_0
```

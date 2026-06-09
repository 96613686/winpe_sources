# std::bad_alloc::bad_alloc(char const *)

- ea: `0x180003140`
- end: `0x18000316b`
- name: `??0bad_alloc@std@@QEAA@PEBD@Z`
- size: `43`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const char *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001444`
- `0x1800035a4`
- `0x180009682`
- `0x180009a51`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180003152`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180003152`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const char *a2)
{
  const char *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2;
  exception::exception(this, &v4);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180003140  mov     [rsp+arg_8], rdx
0x180003145  push    rbx
0x180003146  sub     rsp, 20h
0x18000314a  mov     rbx, rcx
0x18000314d  lea     rdx, [rsp+28h+arg_8]
0x180003152  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180003158  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000315f  mov     [rbx], rax
0x180003162  mov     rax, rbx
0x180003165  add     rsp, 20h
0x180003169  pop     rbx
0x18000316a  retn
```

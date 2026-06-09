# std::bad_alloc::bad_alloc(void)

- ea: `0x180003140`
- end: `0x18000316f`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a3a4`
- `0x18000bce4`
- `0x18000be1c`
- `0x18000f0c8`
- `0x18000f170`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180003156`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180003156`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this)
{
  exception::exception(this, &std::_bad_alloc_Message, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180003140  push    rbx
0x180003142  sub     rsp, 20h
0x180003146  mov     rbx, rcx
0x180003149  mov     r8d, 1
0x18000314f  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180003156  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000315c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180003163  mov     [rbx], rax
0x180003166  mov     rax, rbx
0x180003169  add     rsp, 20h
0x18000316d  pop     rbx
0x18000316e  retn
```

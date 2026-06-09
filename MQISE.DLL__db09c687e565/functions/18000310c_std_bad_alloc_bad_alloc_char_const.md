# std::bad_alloc::bad_alloc(char const *)

- ea: `0x18000310c`
- end: `0x180003137`
- name: `??0bad_alloc@std@@QEAA@PEBD@Z`
- size: `43`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const char *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b11c`
- `0x18000b728`
- `0x18000b98c`
- `0x18000fd38`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000311e`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000311e`

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
0x18000310c  mov     [rsp+arg_8], rdx
0x180003111  push    rbx
0x180003112  sub     rsp, 20h
0x180003116  mov     rbx, rcx
0x180003119  lea     rdx, [rsp+28h+arg_8]
0x18000311e  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180003124  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000312b  mov     [rbx], rax
0x18000312e  mov     rax, rbx
0x180003131  add     rsp, 20h
0x180003135  pop     rbx
0x180003136  retn
```

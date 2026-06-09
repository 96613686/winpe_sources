# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x1400038a0`
- end: `0x1400038dd`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const struct std::bad_alloc *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400038e0`

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x1400038c4`
- `VCRUNTIME140!__std_exception_copy` at `0x1400038c4`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const struct std::bad_alloc *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x1400038a0  push    rbx
0x1400038a2  sub     rsp, 20h
0x1400038a6  mov     rbx, rcx
0x1400038a9  mov     rax, rdx
0x1400038ac  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1400038b3  xorps   xmm0, xmm0
0x1400038b6  lea     rdx, [rbx+8]
0x1400038ba  mov     [rbx], rcx
0x1400038bd  lea     rcx, [rax+8]
0x1400038c1  movups  xmmword ptr [rdx], xmm0
0x1400038c4  call    cs:__imp___std_exception_copy
0x1400038ca  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1400038d1  mov     [rbx], rax
0x1400038d4  mov     rax, rbx
0x1400038d7  add     rsp, 20h
0x1400038db  pop     rbx
0x1400038dc  retn
```

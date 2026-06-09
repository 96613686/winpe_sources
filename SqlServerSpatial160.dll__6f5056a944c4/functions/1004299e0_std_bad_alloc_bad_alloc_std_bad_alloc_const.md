# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x1004299e0`
- end: `0x100429a1d`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const struct std::bad_alloc *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x100429a04`
- `VCRUNTIME140!__std_exception_copy` at `0x100429a04`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const struct std::bad_alloc *a2)
{
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x1004299e0  push    rbx
0x1004299e2  sub     rsp, 20h
0x1004299e6  mov     rbx, rcx
0x1004299e9  mov     rax, rdx
0x1004299ec  lea     rcx, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1004299f3  xorps   xmm0, xmm0
0x1004299f6  lea     rdx, [rbx+8]
0x1004299fa  mov     [rbx], rcx
0x1004299fd  lea     rcx, [rax+8]
0x100429a01  movups  xmmword ptr [rdx], xmm0
0x100429a04  call    cs:__imp___std_exception_copy
0x100429a0a  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x100429a11  mov     [rbx], rax
0x100429a14  mov     rax, rbx
0x100429a17  add     rsp, 20h
0x100429a1b  pop     rbx
0x100429a1c  retn
```

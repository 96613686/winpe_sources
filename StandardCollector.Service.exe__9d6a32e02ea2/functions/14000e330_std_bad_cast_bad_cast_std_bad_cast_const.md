# std::bad_cast::bad_cast(std::bad_cast const &)

- ea: `0x14000e330`
- end: `0x14000e36d`
- name: `??0bad_cast@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `std::bad_cast *__fastcall(std::bad_cast *this, const struct std::bad_cast *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x14000e354`
- `VCRUNTIME140!__std_exception_copy` at `0x14000e354`

## pseudocode

```c
std::bad_cast *__fastcall std::bad_cast::bad_cast(std::bad_cast *this, const struct std::bad_cast *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::bad_cast::`vftable';
  return this;
}

```

## disassembly

```asm
0x14000e330  push    rbx
0x14000e332  sub     rsp, 20h
0x14000e336  mov     rbx, rcx
0x14000e339  mov     rax, rdx
0x14000e33c  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000e343  xorps   xmm0, xmm0
0x14000e346  mov     [rbx], rcx
0x14000e349  lea     rdx, [rbx+8]
0x14000e34d  lea     rcx, [rax+8]
0x14000e351  movups  xmmword ptr [rdx], xmm0
0x14000e354  call    cs:__imp___std_exception_copy
0x14000e35a  lea     rax, ??_7bad_cast@std@@6B@; const std::bad_cast::`vftable'
0x14000e361  mov     [rbx], rax
0x14000e364  mov     rax, rbx
0x14000e367  add     rsp, 20h
0x14000e36b  pop     rbx
0x14000e36c  retn
```

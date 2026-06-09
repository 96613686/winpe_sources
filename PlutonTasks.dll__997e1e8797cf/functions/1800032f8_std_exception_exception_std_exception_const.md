# std::exception::exception(std::exception const &)

- ea: `0x1800032f8`
- end: `0x18000332a`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003144`
- `0x180009540`
- `0x180009568`

## callees

- `0x180002776`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0((char *)a2 + 8);
  return this;
}

```

## disassembly

```asm
0x1800032f8  push    rbx
0x1800032fa  sub     rsp, 20h
0x1800032fe  mov     rbx, rcx
0x180003301  mov     rax, rdx
0x180003304  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000330b  xorps   xmm0, xmm0
0x18000330e  mov     [rbx], rcx
0x180003311  lea     rdx, [rbx+8]
0x180003315  lea     rcx, [rax+8]
0x180003319  movups  xmmword ptr [rdx], xmm0
0x18000331c  call    _o___std_exception_copy_0
0x180003321  mov     rax, rbx
0x180003324  add     rsp, 20h
0x180003328  pop     rbx
0x180003329  retn
```

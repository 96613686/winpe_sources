# std::exception::exception(std::exception const &)

- ea: `0x1800052a4`
- end: `0x1800052d6`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ec8`
- `0x1800051fc`
- `0x180005224`
- `0x1800052dc`
- `0x18000533c`
- `0x180005688`

## callees

- `0x180003552`

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
0x1800052a4  push    rbx
0x1800052a6  sub     rsp, 20h
0x1800052aa  mov     rbx, rcx
0x1800052ad  mov     rax, rdx
0x1800052b0  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800052b7  xorps   xmm0, xmm0
0x1800052ba  mov     [rbx], rcx
0x1800052bd  lea     rdx, [rbx+8]
0x1800052c1  lea     rcx, [rax+8]
0x1800052c5  movups  xmmword ptr [rdx], xmm0
0x1800052c8  call    _o___std_exception_copy_0
0x1800052cd  mov     rax, rbx
0x1800052d0  add     rsp, 20h
0x1800052d4  pop     rbx
0x1800052d5  retn
```

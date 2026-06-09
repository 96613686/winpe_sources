# std::exception::exception(std::exception const &)

- ea: `0x180007204`
- end: `0x180007236`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `50`
- prototype: `__int64 __fastcall(std::exception *__hidden this, const struct std::exception *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007084`
- `0x18000718c`
- `0x1800071b4`

## callees

- `0x1800044ee`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  o___std_exception_copy_0();
  return this;
}

```

## disassembly

```asm
0x180007204  push    rbx
0x180007206  sub     rsp, 20h
0x18000720a  mov     rbx, rcx
0x18000720d  mov     rax, rdx
0x180007210  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180007217  xorps   xmm0, xmm0
0x18000721a  mov     [rbx], rcx
0x18000721d  lea     rdx, [rbx+8]
0x180007221  lea     rcx, [rax+8]
0x180007225  movups  xmmword ptr [rdx], xmm0
0x180007228  call    _o___std_exception_copy_0
0x18000722d  mov     rax, rbx
0x180007230  add     rsp, 20h
0x180007234  pop     rbx
0x180007235  retn
```

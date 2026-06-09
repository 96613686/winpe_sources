# std::exception::exception(std::exception const &)

- ea: `0x140003504`
- end: `0x140003537`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `51`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x140003528`
- `VCRUNTIME140!__std_exception_copy` at `0x140003528`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  return this;
}

```

## disassembly

```asm
0x140003504  push    rbx
0x140003506  sub     rsp, 20h
0x14000350a  mov     rbx, rcx
0x14000350d  mov     rax, rdx
0x140003510  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140003517  xorps   xmm0, xmm0
0x14000351a  mov     [rbx], rcx
0x14000351d  lea     rdx, [rbx+8]
0x140003521  lea     rcx, [rax+8]
0x140003525  movups  xmmword ptr [rdx], xmm0
0x140003528  call    cs:__imp___std_exception_copy
0x14000352e  mov     rax, rbx
0x140003531  add     rsp, 20h
0x140003535  pop     rbx
0x140003536  retn
```

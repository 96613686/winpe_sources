# std::exception::exception(std::exception const &)

- ea: `0x140003910`
- end: `0x140003943`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `51`
- prototype: `__int64 __fastcall(std::exception *__hidden this, const struct std::exception *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x140003934`
- `VCRUNTIME140!__std_exception_copy` at `0x140003934`

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
0x140003910  push    rbx
0x140003912  sub     rsp, 20h
0x140003916  mov     rbx, rcx
0x140003919  mov     rax, rdx
0x14000391c  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140003923  xorps   xmm0, xmm0
0x140003926  lea     rdx, [rbx+8]
0x14000392a  mov     [rbx], rcx
0x14000392d  lea     rcx, [rax+8]
0x140003931  movups  xmmword ptr [rdx], xmm0
0x140003934  call    cs:__imp___std_exception_copy
0x14000393a  mov     rax, rbx
0x14000393d  add     rsp, 20h
0x140003941  pop     rbx
0x140003942  retn
```

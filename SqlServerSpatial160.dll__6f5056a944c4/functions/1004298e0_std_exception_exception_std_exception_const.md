# std::exception::exception(std::exception const &)

- ea: `0x1004298e0`
- end: `0x100429913`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `51`
- prototype: `__int64 __fastcall(std::exception *__hidden this, const struct std::exception *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x100429904`
- `VCRUNTIME140!__std_exception_copy` at `0x100429904`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  return this;
}

```

## disassembly

```asm
0x1004298e0  push    rbx
0x1004298e2  sub     rsp, 20h
0x1004298e6  mov     rbx, rcx
0x1004298e9  mov     rax, rdx
0x1004298ec  lea     rcx, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1004298f3  xorps   xmm0, xmm0
0x1004298f6  lea     rdx, [rbx+8]
0x1004298fa  mov     [rbx], rcx
0x1004298fd  lea     rcx, [rax+8]
0x100429901  movups  xmmword ptr [rdx], xmm0
0x100429904  call    cs:__imp___std_exception_copy
0x10042990a  mov     rax, rbx
0x10042990d  add     rsp, 20h
0x100429911  pop     rbx
0x100429912  retn
```

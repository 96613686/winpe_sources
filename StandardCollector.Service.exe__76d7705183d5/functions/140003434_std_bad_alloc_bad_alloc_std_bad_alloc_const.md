# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x140003434`
- end: `0x140003471`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const struct std::bad_alloc *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x140003458`
- `VCRUNTIME140!__std_exception_copy` at `0x140003458`

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
0x140003434  push    rbx
0x140003436  sub     rsp, 20h
0x14000343a  mov     rbx, rcx
0x14000343d  mov     rax, rdx
0x140003440  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140003447  xorps   xmm0, xmm0
0x14000344a  mov     [rbx], rcx
0x14000344d  lea     rdx, [rbx+8]
0x140003451  lea     rcx, [rax+8]
0x140003455  movups  xmmword ptr [rdx], xmm0
0x140003458  call    cs:__imp___std_exception_copy
0x14000345e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140003465  mov     [rbx], rax
0x140003468  mov     rax, rbx
0x14000346b  add     rsp, 20h
0x14000346f  pop     rbx
0x140003470  retn
```

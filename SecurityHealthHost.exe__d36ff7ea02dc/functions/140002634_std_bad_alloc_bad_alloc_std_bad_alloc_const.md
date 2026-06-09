# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x140002634`
- end: `0x140002671`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this, const struct std::bad_alloc *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140002658`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140002658`

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
0x140002634  push    rbx
0x140002636  sub     rsp, 20h
0x14000263a  mov     rbx, rcx
0x14000263d  mov     rax, rdx
0x140002640  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140002647  xorps   xmm0, xmm0
0x14000264a  mov     [rbx], rcx
0x14000264d  lea     rdx, [rbx+8]
0x140002651  lea     rcx, [rax+8]
0x140002655  movups  xmmword ptr [rdx], xmm0
0x140002658  call    cs:__imp___std_exception_copy
0x14000265e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140002665  mov     [rbx], rax
0x140002668  mov     rax, rbx
0x14000266b  add     rsp, 20h
0x14000266f  pop     rbx
0x140002670  retn
```

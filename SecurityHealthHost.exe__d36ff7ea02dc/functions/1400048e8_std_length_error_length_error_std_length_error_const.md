# std::length_error::length_error(std::length_error const &)

- ea: `0x1400048e8`
- end: `0x140004925`
- name: `??0length_error@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `std::length_error *__fastcall(std::length_error *this, const struct std::length_error *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000490c`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000490c`

## pseudocode

```c
std::length_error *__fastcall std::length_error::length_error(
        std::length_error *this,
        const struct std::length_error *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::length_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x1400048e8  push    rbx
0x1400048ea  sub     rsp, 20h
0x1400048ee  mov     rbx, rcx
0x1400048f1  mov     rax, rdx
0x1400048f4  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1400048fb  xorps   xmm0, xmm0
0x1400048fe  mov     [rbx], rcx
0x140004901  lea     rdx, [rbx+8]
0x140004905  lea     rcx, [rax+8]
0x140004909  movups  xmmword ptr [rdx], xmm0
0x14000490c  call    cs:__imp___std_exception_copy
0x140004912  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x140004919  mov     [rbx], rax
0x14000491c  mov     rax, rbx
0x14000491f  add     rsp, 20h
0x140004923  pop     rbx
0x140004924  retn
```

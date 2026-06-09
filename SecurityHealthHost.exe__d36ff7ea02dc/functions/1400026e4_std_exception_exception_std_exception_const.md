# std::exception::exception(std::exception const &)

- ea: `0x1400026e4`
- end: `0x140002717`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `51`
- prototype: `std::exception *__fastcall(std::exception *this, const struct std::exception *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140002708`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140002708`

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
0x1400026e4  push    rbx
0x1400026e6  sub     rsp, 20h
0x1400026ea  mov     rbx, rcx
0x1400026ed  mov     rax, rdx
0x1400026f0  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1400026f7  xorps   xmm0, xmm0
0x1400026fa  mov     [rbx], rcx
0x1400026fd  lea     rdx, [rbx+8]
0x140002701  lea     rcx, [rax+8]
0x140002705  movups  xmmword ptr [rdx], xmm0
0x140002708  call    cs:__imp___std_exception_copy
0x14000270e  mov     rax, rbx
0x140002711  add     rsp, 20h
0x140002715  pop     rbx
0x140002716  retn
```

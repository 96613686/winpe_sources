# std::logic_error::logic_error(std::logic_error const &)

- ea: `0x140004988`
- end: `0x1400049c5`
- name: `??0logic_error@std@@QEAA@AEBV01@@Z`
- size: `61`
- prototype: `std::logic_error *__fastcall(std::logic_error *this, const struct std::logic_error *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x1400049ac`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x1400049ac`

## pseudocode

```c
std::logic_error *__fastcall std::logic_error::logic_error(std::logic_error *this, const struct std::logic_error *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::logic_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x140004988  push    rbx
0x14000498a  sub     rsp, 20h
0x14000498e  mov     rbx, rcx
0x140004991  mov     rax, rdx
0x140004994  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000499b  xorps   xmm0, xmm0
0x14000499e  mov     [rbx], rcx
0x1400049a1  lea     rdx, [rbx+8]
0x1400049a5  lea     rcx, [rax+8]
0x1400049a9  movups  xmmword ptr [rdx], xmm0
0x1400049ac  call    cs:__imp___std_exception_copy
0x1400049b2  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x1400049b9  mov     [rbx], rax
0x1400049bc  mov     rax, rbx
0x1400049bf  add     rsp, 20h
0x1400049c3  pop     rbx
0x1400049c4  retn
```

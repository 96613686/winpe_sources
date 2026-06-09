# std::runtime_error::runtime_error(std::runtime_error const &)

- ea: `0x1800039d0`
- end: `0x180003a10`
- name: `??0runtime_error@std@@QEAA@AEBV01@@Z`
- size: `64`
- prototype: `__int64 __fastcall(std::runtime_error *__hidden this, const struct std::runtime_error *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x1800039f7`
- `VCRUNTIME140!__std_exception_copy` at `0x1800039f7`

## pseudocode

```c
std::runtime_error *__fastcall std::runtime_error::runtime_error(
        std::runtime_error *this,
        const struct std::runtime_error *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::runtime_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800039d0  push    rbx
0x1800039d2  sub     rsp, 20h
0x1800039d6  mov     rbx, rcx
0x1800039d9  mov     rax, rdx
0x1800039dc  lea     rdx, [rbx+8]
0x1800039e0  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800039e7  mov     [rbx], rcx
0x1800039ea  xor     ecx, ecx
0x1800039ec  mov     [rdx], rcx
0x1800039ef  mov     [rdx+8], rcx
0x1800039f3  lea     rcx, [rax+8]
0x1800039f7  call    cs:__imp___std_exception_copy
0x1800039fd  lea     rax, ??_7runtime_error@std@@6B@; const std::runtime_error::`vftable'
0x180003a04  mov     [rbx], rax
0x180003a07  mov     rax, rbx
0x180003a0a  add     rsp, 20h
0x180003a0e  pop     rbx
0x180003a0f  retn
```

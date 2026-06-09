# std::exception::exception(std::exception const &)

- ea: `0x180001c80`
- end: `0x180001cb6`
- name: `??0exception@std@@QEAA@AEBV01@@Z`
- size: `54`
- prototype: `__int64 __fastcall(std::exception *__hidden this, const struct std::exception *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180001ca7`
- `VCRUNTIME140!__std_exception_copy` at `0x180001ca7`

## pseudocode

```c
std::exception *__fastcall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  __std_exception_copy((char *)a2 + 8);
  return this;
}

```

## disassembly

```asm
0x180001c80  push    rbx
0x180001c82  sub     rsp, 20h
0x180001c86  mov     rbx, rcx
0x180001c89  mov     rax, rdx
0x180001c8c  lea     rdx, [rbx+8]
0x180001c90  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180001c97  mov     [rbx], rcx
0x180001c9a  xor     ecx, ecx
0x180001c9c  mov     [rdx], rcx
0x180001c9f  mov     [rdx+8], rcx
0x180001ca3  lea     rcx, [rax+8]
0x180001ca7  call    cs:__imp___std_exception_copy
0x180001cad  mov     rax, rbx
0x180001cb0  add     rsp, 20h
0x180001cb4  pop     rbx
0x180001cb5  retn
```

# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x180001ba0`
- end: `0x180001be0`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `64`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const struct std::bad_alloc *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180001bc7`
- `VCRUNTIME140!__std_exception_copy` at `0x180001bc7`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const struct std::bad_alloc *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001ba0  push    rbx
0x180001ba2  sub     rsp, 20h
0x180001ba6  mov     rbx, rcx
0x180001ba9  mov     rax, rdx
0x180001bac  lea     rdx, [rbx+8]
0x180001bb0  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180001bb7  mov     [rbx], rcx
0x180001bba  xor     ecx, ecx
0x180001bbc  mov     [rdx], rcx
0x180001bbf  mov     [rdx+8], rcx
0x180001bc3  lea     rcx, [rax+8]
0x180001bc7  call    cs:__imp___std_exception_copy
0x180001bcd  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001bd4  mov     [rbx], rax
0x180001bd7  mov     rax, rbx
0x180001bda  add     rsp, 20h
0x180001bde  pop     rbx
0x180001bdf  retn
```

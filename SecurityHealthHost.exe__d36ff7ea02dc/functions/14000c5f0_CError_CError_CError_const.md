# CError::CError(CError const &)

- ea: `0x14000c5f0`
- end: `0x14000c63c`
- name: `??0CError@@QEAA@AEBV0@@Z`
- size: `76`
- prototype: `CError *__fastcall(CError *__hidden this, const struct CError *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000c618`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x14000c618`

## pseudocode

```c
CError *__fastcall CError::CError(CError *this, const struct CError *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &CError::`vftable';
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
  return this;
}

```

## disassembly

```asm
0x14000c5f0  mov     [rsp+arg_0], rbx
0x14000c5f5  push    rdi
0x14000c5f6  sub     rsp, 20h
0x14000c5fa  mov     rbx, rdx
0x14000c5fd  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14000c604  mov     [rcx], rax
0x14000c607  lea     rdx, [rcx+8]
0x14000c60b  mov     rdi, rcx
0x14000c60e  xorps   xmm0, xmm0
0x14000c611  movups  xmmword ptr [rdx], xmm0
0x14000c614  lea     rcx, [rbx+8]
0x14000c618  call    cs:__imp___std_exception_copy
0x14000c61e  lea     rax, ??_7CError@@6B@; const CError::`vftable'
0x14000c625  mov     [rdi], rax
0x14000c628  mov     eax, [rbx+18h]
0x14000c62b  mov     rbx, [rsp+28h+arg_0]
0x14000c630  mov     [rdi+18h], eax
0x14000c633  mov     rax, rdi
0x14000c636  add     rsp, 20h
0x14000c63a  pop     rdi
0x14000c63b  retn
```

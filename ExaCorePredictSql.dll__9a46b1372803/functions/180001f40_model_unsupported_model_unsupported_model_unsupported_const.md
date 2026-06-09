# model_unsupported::model_unsupported(model_unsupported const &)

- ea: `0x180001f40`
- end: `0x180001f80`
- name: `??0model_unsupported@@QEAA@AEBV0@@Z`
- size: `64`
- prototype: `model_unsupported *__fastcall(model_unsupported *__hidden this, const struct model_unsupported *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180001f67`
- `VCRUNTIME140!__std_exception_copy` at `0x180001f67`

## pseudocode

```c
model_unsupported *__fastcall model_unsupported::model_unsupported(
        model_unsupported *this,
        const struct model_unsupported *a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &model_unsupported::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001f40  push    rbx; public: model_unsupported::model_unsupported(class model_unsupported &&)
0x180001f42  sub     rsp, 20h
0x180001f46  mov     rbx, rcx
0x180001f49  mov     rax, rdx
0x180001f4c  lea     rdx, [rbx+8]
0x180001f50  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180001f57  mov     [rbx], rcx
0x180001f5a  xor     ecx, ecx
0x180001f5c  mov     [rdx], rcx
0x180001f5f  mov     [rdx+8], rcx
0x180001f63  lea     rcx, [rax+8]
0x180001f67  call    cs:__imp___std_exception_copy
0x180001f6d  lea     rax, ??_7model_unsupported@@6B@; const model_unsupported::`vftable'
0x180001f74  mov     [rbx], rax
0x180001f77  mov     rax, rbx
0x180001f7a  add     rsp, 20h
0x180001f7e  pop     rbx
0x180001f7f  retn
```

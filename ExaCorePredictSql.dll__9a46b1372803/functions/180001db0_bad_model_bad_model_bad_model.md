# bad_model::bad_model(bad_model &&)

- ea: `0x180001db0`
- end: `0x180001df0`
- name: `??0bad_model@@QEAA@$$QEAV0@@Z`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180001dd7`
- `VCRUNTIME140!__std_exception_copy` at `0x180001dd7`

## pseudocode

```c
_QWORD *__fastcall bad_model::bad_model(_QWORD *a1, __int64 a2)
{
  *a1 = &std::exception::`vftable';
  a1[1] = 0;
  a1[2] = 0;
  __std_exception_copy(a2 + 8);
  *a1 = &bad_model::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180001db0  push    rbx; public: bad_model::bad_model(class bad_model &&)
0x180001db2  sub     rsp, 20h
0x180001db6  mov     rbx, rcx
0x180001db9  mov     rax, rdx
0x180001dbc  lea     rdx, [rbx+8]
0x180001dc0  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180001dc7  mov     [rbx], rcx
0x180001dca  xor     ecx, ecx
0x180001dcc  mov     [rdx], rcx
0x180001dcf  mov     [rdx+8], rcx
0x180001dd3  lea     rcx, [rax+8]
0x180001dd7  call    cs:__imp___std_exception_copy
0x180001ddd  lea     rax, ??_7bad_model@@6B@; const bad_model::`vftable'
0x180001de4  mov     [rbx], rax
0x180001de7  mov     rax, rbx
0x180001dea  add     rsp, 20h
0x180001dee  pop     rbx
0x180001def  retn
```

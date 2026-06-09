# std::length_error::length_error(char const *)

- ea: `0x180001320`
- end: `0x18000134f`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015c8`
- `0x1800015f4`

## callees

- `0x180002512`

## pseudocode

```c
std::length_error *__fastcall std::length_error::length_error(std::length_error *this, char *a2)
{
  char *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a2;
  exception::exception(this, (const char *const *)&v4);
  *(_QWORD *)this = &std::length_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001320  mov     [rsp+arg_0], rcx
0x180001325  push    rbx
0x180001326  sub     rsp, 20h
0x18000132a  mov     [rsp+28h+arg_0], rdx
0x18000132f  mov     rbx, rcx
0x180001332  lea     rdx, [rsp+28h+arg_0]; char **
0x180001337  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x18000133c  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x180001343  mov     [rbx], rax
0x180001346  mov     rax, rbx
0x180001349  add     rsp, 20h
0x18000134d  pop     rbx
0x18000134e  retn
```

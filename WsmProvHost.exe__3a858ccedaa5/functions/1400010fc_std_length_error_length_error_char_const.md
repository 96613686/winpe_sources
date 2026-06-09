# std::length_error::length_error(char const *)

- ea: `0x1400010fc`
- end: `0x14000112b`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400013a8`
- `0x1400013d4`

## callees

- `0x140001e55`

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
0x1400010fc  mov     [rsp+arg_0], rcx
0x140001101  push    rbx
0x140001102  sub     rsp, 20h
0x140001106  mov     [rsp+28h+arg_0], rdx
0x14000110b  mov     rbx, rcx
0x14000110e  lea     rdx, [rsp+28h+arg_0]; char **
0x140001113  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x140001118  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x14000111f  mov     [rbx], rax
0x140001122  mov     rax, rbx
0x140001125  add     rsp, 20h
0x140001129  pop     rbx
0x14000112a  retn
```

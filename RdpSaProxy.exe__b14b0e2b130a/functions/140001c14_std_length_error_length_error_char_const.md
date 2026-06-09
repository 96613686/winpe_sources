# std::length_error::length_error(char const *)

- ea: `0x140001c14`
- end: `0x140001c43`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `std::length_error *__fastcall(std::length_error *this, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001eb8`
- `0x140001ee4`

## callees

- `0x1400024b8`

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
0x140001c14  mov     [rsp+arg_0], rcx
0x140001c19  push    rbx
0x140001c1a  sub     rsp, 20h
0x140001c1e  mov     [rsp+28h+arg_0], rdx
0x140001c23  mov     rbx, rcx
0x140001c26  lea     rdx, [rsp+28h+arg_0]; char **
0x140001c2b  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x140001c30  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x140001c37  mov     [rbx], rax
0x140001c3a  mov     rax, rbx
0x140001c3d  add     rsp, 20h
0x140001c41  pop     rbx
0x140001c42  retn
```

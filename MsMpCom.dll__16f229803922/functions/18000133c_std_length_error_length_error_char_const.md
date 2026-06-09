# std::length_error::length_error(char const *)

- ea: `0x18000133c`
- end: `0x18000136b`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `__int64 __fastcall(std::length_error *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001440`
- `0x18000146c`

## callees

- `0x180001c84`

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
0x18000133c  mov     [rsp+arg_0], rcx
0x180001341  push    rbx
0x180001342  sub     rsp, 20h
0x180001346  mov     [rsp+28h+arg_0], rdx
0x18000134b  mov     rbx, rcx
0x18000134e  lea     rdx, [rsp+28h+arg_0]; char **
0x180001353  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001358  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x18000135f  mov     [rbx], rax
0x180001362  mov     rax, rbx
0x180001365  add     rsp, 20h
0x180001369  pop     rbx
0x18000136a  retn
```

# std::length_error::length_error(char const *)

- ea: `0x180001c18`
- end: `0x180001c47`
- name: `??0length_error@std@@QEAA@PEBD@Z`
- size: `47`
- prototype: `__int64 __fastcall(std::length_error *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ec8`
- `0x180001ef4`

## callees

- `0x18000251c`

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
0x180001c18  mov     [rsp+arg_0], rcx
0x180001c1d  push    rbx
0x180001c1e  sub     rsp, 20h
0x180001c22  mov     [rsp+28h+arg_0], rdx
0x180001c27  mov     rbx, rcx
0x180001c2a  lea     rdx, [rsp+28h+arg_0]; char **
0x180001c2f  call    ??0exception@@QEAA@AEBQEBD@Z_0; exception::exception(char const * const &)
0x180001c34  lea     rax, ??_7length_error@std@@6B@; const std::length_error::`vftable'
0x180001c3b  mov     [rbx], rax
0x180001c3e  mov     rax, rbx
0x180001c41  add     rsp, 20h
0x180001c45  pop     rbx
0x180001c46  retn
```

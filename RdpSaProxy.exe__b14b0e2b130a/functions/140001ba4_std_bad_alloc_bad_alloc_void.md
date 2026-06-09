# std::bad_alloc::bad_alloc(void)

- ea: `0x140001ba4`
- end: `0x140001be5`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `65`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e78`

## callees

- `0x1400024c4`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this)
{
  char *v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = "bad allocation";
  exception::exception(this, (const char *const *)&v3, 1);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x140001ba4  push    rbx
0x140001ba6  sub     rsp, 30h
0x140001baa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001bb3  mov     rbx, rcx
0x140001bb6  lea     rax, aBadAllocation; "bad allocation"
0x140001bbd  mov     [rsp+38h+arg_0], rax
0x140001bc2  mov     r8d, 1; int
0x140001bc8  lea     rdx, [rsp+38h+arg_0]; char **
0x140001bcd  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x140001bd2  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140001bd9  mov     [rbx], rax
0x140001bdc  mov     rax, rbx
0x140001bdf  add     rsp, 30h
0x140001be3  pop     rbx
0x140001be4  retn
```

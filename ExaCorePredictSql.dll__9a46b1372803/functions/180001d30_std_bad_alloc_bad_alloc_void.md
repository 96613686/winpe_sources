# std::bad_alloc::bad_alloc(void)

- ea: `0x180001d30`
- end: `0x180001d4f`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b10`
- `0x180002030`
- `0x1800024e0`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this)
{
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = "bad allocation";
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001d30  xor     eax, eax
0x180001d32  mov     [rcx+10h], rax
0x180001d36  lea     rax, aBadAllocation
0x180001d3d  mov     [rcx+8], rax
0x180001d41  lea     rax, ??_7bad_alloc@std@@6B@
0x180001d48  mov     [rcx], rax
0x180001d4b  mov     rax, rcx
0x180001d4e  retn
```

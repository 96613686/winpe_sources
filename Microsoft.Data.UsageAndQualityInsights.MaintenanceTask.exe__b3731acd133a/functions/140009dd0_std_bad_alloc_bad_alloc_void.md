# std::bad_alloc::bad_alloc(void)

- ea: `0x140009dd0`
- end: `0x140009df1`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `33`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002054`
- `0x14000b0a8`
- `0x14000b2d4`

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
0x140009dd0  lea     rax, aBadAllocation; "bad allocation"
0x140009dd7  mov     qword ptr [rcx+10h], 0
0x140009ddf  mov     [rcx+8], rax
0x140009de3  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140009dea  mov     [rcx], rax
0x140009ded  mov     rax, rcx
0x140009df0  retn
```

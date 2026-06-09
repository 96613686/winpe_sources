# std::bad_alloc::bad_alloc(void)

- ea: `0x18000490c`
- end: `0x18000492d`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `33`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002140`
- `0x180004ae8`
- `0x18000bde4`

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
0x18000490c  lea     rax, aBadAllocation; "bad allocation"
0x180004913  mov     qword ptr [rcx+10h], 0
0x18000491b  mov     [rcx+8], rax
0x18000491f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180004926  mov     [rcx], rax
0x180004929  mov     rax, rcx
0x18000492c  retn
```

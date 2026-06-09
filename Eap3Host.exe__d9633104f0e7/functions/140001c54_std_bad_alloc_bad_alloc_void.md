# std::bad_alloc::bad_alloc(void)

- ea: `0x140001c54`
- end: `0x140001c75`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `33`
- prototype: `std::bad_alloc *__fastcall(std::bad_alloc *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d84`

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
0x140001c54  lea     rax, aBadAllocation; "bad allocation"
0x140001c5b  mov     qword ptr [rcx+10h], 0
0x140001c63  mov     [rcx+8], rax
0x140001c67  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140001c6e  mov     [rcx], rax
0x140001c71  mov     rax, rcx
0x140001c74  retn
```

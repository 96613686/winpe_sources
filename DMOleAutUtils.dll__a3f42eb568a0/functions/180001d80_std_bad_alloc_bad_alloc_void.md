# std::bad_alloc::bad_alloc(void)

- ea: `0x180001d80`
- end: `0x180001da1`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001eb4`

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
0x180001d80  lea     rax, aBadAllocation; "bad allocation"
0x180001d87  mov     qword ptr [rcx+10h], 0
0x180001d8f  mov     [rcx+8], rax
0x180001d93  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001d9a  mov     [rcx], rax
0x180001d9d  mov     rax, rcx
0x180001da0  retn
```

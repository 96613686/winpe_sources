# std::bad_alloc::bad_alloc(void)

- ea: `0x1800068f8`
- end: `0x180006919`
- name: `??0bad_alloc@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f0c`
- `0x180006700`
- `0x180006edc`

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
0x1800068f8  lea     rax, aBadAllocation; "bad allocation"
0x1800068ff  mov     qword ptr [rcx+10h], 0
0x180006907  mov     [rcx+8], rax
0x18000690b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006912  mov     [rcx], rax
0x180006915  mov     rax, rcx
0x180006918  retn
```

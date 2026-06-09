# CILogCreateStorage2A::Release(void)

- ea: `0x1800025c0`
- end: `0x1800025d0`
- name: `?Release@CILogCreateStorage2A@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CILogCreateStorage2A *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogCreateStorage2A::Release(CILogCreateStorage2A *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x1800025c0  mov     rcx, [rcx+10h]
0x1800025c4  mov     rax, [rcx]
0x1800025c7  mov     rax, [rax+10h]
0x1800025cb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

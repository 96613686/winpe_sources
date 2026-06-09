# CILogRead::AddRef(void)

- ea: `0x180002730`
- end: `0x180002740`
- name: `?AddRef@CILogRead@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CILogRead *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogRead::AddRef(CILogRead *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180002730  mov     rcx, [rcx+8]
0x180002734  mov     rax, [rcx]
0x180002737  mov     rax, [rax+18h]
0x18000273b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

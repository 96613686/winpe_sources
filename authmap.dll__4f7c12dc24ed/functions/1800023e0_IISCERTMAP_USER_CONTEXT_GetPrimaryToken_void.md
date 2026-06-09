# IISCERTMAP_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x1800023e0`
- end: `0x1800023f0`
- name: `?GetPrimaryToken@IISCERTMAP_USER_CONTEXT@@UEAAPEAXXZ`
- size: `16`
- prototype: `void *__fastcall(IISCERTMAP_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008010`

## pseudocode

```c
__int64 __fastcall IISCERTMAP_USER_CONTEXT::GetPrimaryToken(IISCERTMAP_USER_CONTEXT *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x1800023e0  mov     rcx, [rcx+10h]
0x1800023e4  mov     rax, [rcx]
0x1800023e7  mov     rax, [rax+40h]
0x1800023eb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

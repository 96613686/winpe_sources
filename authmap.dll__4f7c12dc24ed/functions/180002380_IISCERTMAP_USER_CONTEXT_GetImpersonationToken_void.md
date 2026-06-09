# IISCERTMAP_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x180002380`
- end: `0x180002390`
- name: `?GetImpersonationToken@IISCERTMAP_USER_CONTEXT@@UEAAPEAXXZ`
- size: `16`
- prototype: `void *__fastcall(IISCERTMAP_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008010`

## pseudocode

```c
__int64 __fastcall IISCERTMAP_USER_CONTEXT::GetImpersonationToken(IISCERTMAP_USER_CONTEXT *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x180002380  mov     rcx, [rcx+10h]
0x180002384  mov     rax, [rcx]
0x180002387  mov     rax, [rax+38h]
0x18000238b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

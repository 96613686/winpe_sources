# BASIC_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x180002770`
- end: `0x180002780`
- name: `?GetPrimaryToken@BASIC_USER_CONTEXT@@UEAAPEAXXZ`
- size: `16`
- prototype: `void *__fastcall(BASIC_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall BASIC_USER_CONTEXT::GetPrimaryToken(BASIC_USER_CONTEXT *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x180002770  mov     rcx, [rcx+10h]
0x180002774  mov     rax, [rcx]
0x180002777  mov     rax, [rax+40h]
0x18000277b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

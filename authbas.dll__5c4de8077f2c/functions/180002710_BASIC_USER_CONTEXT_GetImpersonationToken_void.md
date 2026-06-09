# BASIC_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x180002710`
- end: `0x180002720`
- name: `?GetImpersonationToken@BASIC_USER_CONTEXT@@UEAAPEAXXZ`
- size: `16`
- prototype: `__int64 __fastcall(BASIC_USER_CONTEXT *this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall BASIC_USER_CONTEXT::GetImpersonationToken(BASIC_USER_CONTEXT *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x180002710  mov     rcx, [rcx+10h]
0x180002714  mov     rax, [rcx]
0x180002717  mov     rax, [rax+38h]
0x18000271b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

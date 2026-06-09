# CERTMAP_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x180002020`
- end: `0x180002025`
- name: `?GetImpersonationToken@CERTMAP_USER_CONTEXT@@UEAAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(CERTMAP_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void *__fastcall CERTMAP_USER_CONTEXT::GetImpersonationToken(CERTMAP_USER_CONTEXT *this)
{
  return (void *)*((_QWORD *)this + 9);
}

```

## disassembly

```asm
0x180002020  mov     rax, [rcx+48h]
0x180002024  retn
```

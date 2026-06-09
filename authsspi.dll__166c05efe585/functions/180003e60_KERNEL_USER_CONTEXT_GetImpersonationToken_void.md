# KERNEL_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x180003e60`
- end: `0x180003e65`
- name: `?GetImpersonationToken@KERNEL_USER_CONTEXT@@UEAAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(KERNEL_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void *__fastcall KERNEL_USER_CONTEXT::GetImpersonationToken(KERNEL_USER_CONTEXT *this)
{
  return (void *)*((_QWORD *)this + 3);
}

```

## disassembly

```asm
0x180003e60  mov     rax, [rcx+18h]
0x180003e64  retn
```

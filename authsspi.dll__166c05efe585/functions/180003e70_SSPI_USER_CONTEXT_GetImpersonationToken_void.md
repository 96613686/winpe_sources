# SSPI_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x180003e70`
- end: `0x180003e75`
- name: `?GetImpersonationToken@SSPI_USER_CONTEXT@@UEAAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(SSPI_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void *__fastcall SSPI_USER_CONTEXT::GetImpersonationToken(SSPI_USER_CONTEXT *this)
{
  return (void *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x180003e70  mov     rax, [rcx+10h]
0x180003e74  retn
```

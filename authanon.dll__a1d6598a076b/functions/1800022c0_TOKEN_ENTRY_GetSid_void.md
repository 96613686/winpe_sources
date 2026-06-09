# TOKEN_ENTRY::GetSid(void)

- ea: `0x1800022c0`
- end: `0x1800022c5`
- name: `?GetSid@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `5`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetSid(TOKEN_ENTRY *this)
{
  return (void *)*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x1800022c0  mov     rax, [rcx+20h]
0x1800022c4  retn
```

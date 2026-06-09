# TOKEN_KEY::GetPasswordHash(void)

- ea: `0x180002760`
- end: `0x180002765`
- name: `?GetPasswordHash@TOKEN_KEY@@UEBAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const unsigned __int16 *__fastcall TOKEN_KEY::GetPasswordHash(TOKEN_KEY *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 12);
}

```

## disassembly

```asm
0x180002760  mov     rax, [rcx+60h]
0x180002764  retn
```

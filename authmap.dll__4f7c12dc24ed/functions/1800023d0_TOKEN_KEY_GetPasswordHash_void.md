# TOKEN_KEY::GetPasswordHash(void)

- ea: `0x1800023d0`
- end: `0x1800023d5`
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
0x1800023d0  mov     rax, [rcx+60h]
0x1800023d4  retn
```

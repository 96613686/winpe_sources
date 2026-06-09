# TOKEN_KEY::GetUserNameW(void)

- ea: `0x1800027b0`
- end: `0x1800027b5`
- name: `?GetUserNameW@TOKEN_KEY@@UEBAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const unsigned __int16 *__fastcall TOKEN_KEY::GetUserNameW(TOKEN_KEY *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 5);
}

```

## disassembly

```asm
0x1800027b0  mov     rax, [rcx+28h]
0x1800027b4  retn
```

# TOKEN_KEY::GetUserNameW(void)

- ea: `0x180002410`
- end: `0x180002415`
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
0x180002410  mov     rax, [rcx+28h]
0x180002414  retn
```

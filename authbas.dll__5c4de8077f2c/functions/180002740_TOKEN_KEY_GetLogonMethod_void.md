# TOKEN_KEY::GetLogonMethod(void)

- ea: `0x180002740`
- end: `0x180002744`
- name: `?GetLogonMethod@TOKEN_KEY@@UEBAKXZ`
- size: `4`
- prototype: `unsigned int __fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GetLogonMethod(TOKEN_KEY *this)
{
  return *((unsigned int *)this + 30);
}

```

## disassembly

```asm
0x180002740  mov     eax, [rcx+78h]
0x180002743  retn
```

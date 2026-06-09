# TOKEN_KEY::GetLogonMethod(void)

- ea: `0x1800023b0`
- end: `0x1800023b4`
- name: `?GetLogonMethod@TOKEN_KEY@@UEBAKXZ`
- size: `4`
- prototype: `__int64 __fastcall(TOKEN_KEY *this)`
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
0x1800023b0  mov     eax, [rcx+78h]
0x1800023b3  retn
```

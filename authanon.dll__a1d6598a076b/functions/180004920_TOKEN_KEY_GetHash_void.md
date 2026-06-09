# TOKEN_KEY::GetHash(void)

- ea: `0x180004920`
- end: `0x180004924`
- name: `?GetHash@TOKEN_KEY@@UEBAKXZ`
- size: `4`
- prototype: `unsigned int __fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GetHash(TOKEN_KEY *this)
{
  return *((unsigned int *)this + 31);
}

```

## disassembly

```asm
0x180004920  mov     eax, [rcx+7Ch]
0x180004923  retn
```

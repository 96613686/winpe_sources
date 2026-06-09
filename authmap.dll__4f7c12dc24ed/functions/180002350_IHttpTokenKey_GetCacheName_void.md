# IHttpTokenKey::GetCacheName(void)

- ea: `0x180002350`
- end: `0x180002358`
- name: `?GetCacheName@IHttpTokenKey@@UEBAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(IHttpTokenKey *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x180002350`: `TOKEN`

## pseudocode

```c
const unsigned __int16 *__fastcall IHttpTokenKey::GetCacheName(IHttpTokenKey *this)
{
  return L"TOKEN";
}

```

## disassembly

```asm
0x180002350  lea     rax, aToken; "TOKEN"
0x180002357  retn
```

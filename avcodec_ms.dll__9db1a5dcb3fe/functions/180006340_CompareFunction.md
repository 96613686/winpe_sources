# CompareFunction

- ea: `0x180006340`
- end: `0x180006345`
- name: `CompareFunction`
- size: `5`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CompareFunction(_DWORD *a1, _DWORD *a2)
{
  return (unsigned int)(*a1 - *a2);
}

```

## disassembly

```asm
0x180006340  mov     eax, [rcx]
0x180006342  sub     eax, [rdx]
0x180006344  retn
```

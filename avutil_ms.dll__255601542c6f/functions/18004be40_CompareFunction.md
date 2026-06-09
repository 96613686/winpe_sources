# CompareFunction

- ea: `0x18004be40`
- end: `0x18004be48`
- name: `CompareFunction`
- size: `8`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002d5b0`

## pseudocode

```c
__int64 __fastcall CompareFunction(const void *a1, _QWORD *a2)
{
  return av_strcasecmp(a1, *a2);
}

```

## disassembly

```asm
0x18004be40  mov     rdx, [rdx]
0x18004be43  jmp     av_strcasecmp
```

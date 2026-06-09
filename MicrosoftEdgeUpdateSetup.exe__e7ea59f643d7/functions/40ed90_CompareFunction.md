# CompareFunction

- ea: `0x40ed90`
- end: `0x40eda8`
- name: `CompareFunction`
- size: `24`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x40ed90`

## pseudocode

```c
// Microsoft VisualC universal runtime
int __cdecl CompareFunction(const void *a1, const void *a2)
{
  if ( a2 <= a1 )
    return a2 < a1;
  else
    return -1;
}

```

## disassembly

```asm
0x40ed90  mov     edi, edi
0x40ed92  push    ebp
0x40ed93  mov     ebp, esp
0x40ed95  mov     eax, [ebp+arg_4]
0x40ed98  cmp     eax, [ebp+arg_0]
0x40ed9b  jbe     short loc_40EDA2
0x40ed9d  or      eax, 0FFFFFFFFh
0x40eda0  pop     ebp
0x40eda1  retn
0x40eda2  sbb     eax, eax
0x40eda4  neg     eax
0x40eda6  pop     ebp
0x40eda7  retn
```

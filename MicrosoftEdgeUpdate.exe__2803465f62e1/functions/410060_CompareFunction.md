# CompareFunction

- ea: `0x410060`
- end: `0x410078`
- name: `CompareFunction`
- size: `24`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x410060`

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
0x410060  mov     edi, edi
0x410062  push    ebp
0x410063  mov     ebp, esp
0x410065  mov     eax, [ebp+arg_4]
0x410068  cmp     eax, [ebp+arg_0]
0x41006b  jbe     short loc_410072
0x41006d  or      eax, 0FFFFFFFFh
0x410070  pop     ebp
0x410071  retn
0x410072  sbb     eax, eax
0x410074  neg     eax
0x410076  pop     ebp
0x410077  retn
```

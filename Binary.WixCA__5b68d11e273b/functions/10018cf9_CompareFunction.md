# CompareFunction

- ea: `0x10018cf9`
- end: `0x10018d11`
- name: `CompareFunction`
- size: `24`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10018cf9`

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
0x10018cf9  mov     edi, edi
0x10018cfb  push    ebp
0x10018cfc  mov     ebp, esp
0x10018cfe  mov     eax, [ebp+arg_4]
0x10018d01  cmp     eax, [ebp+arg_0]
0x10018d04  jbe     short loc_10018D0B
0x10018d06  or      eax, 0FFFFFFFFh
0x10018d09  pop     ebp
0x10018d0a  retn
0x10018d0b  sbb     eax, eax
0x10018d0d  neg     eax
0x10018d0f  pop     ebp
0x10018d10  retn
```

# CompareFunction

- ea: `0x413e80`
- end: `0x413e98`
- name: `CompareFunction`
- size: `24`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x413e80`

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
0x413e80  mov     edi, edi
0x413e82  push    ebp
0x413e83  mov     ebp, esp
0x413e85  mov     eax, [ebp+arg_4]
0x413e88  cmp     eax, [ebp+arg_0]
0x413e8b  jbe     short loc_413E92
0x413e8d  or      eax, 0FFFFFFFFh
0x413e90  pop     ebp
0x413e91  retn
0x413e92  sbb     eax, eax
0x413e94  neg     eax
0x413e96  pop     ebp
0x413e97  retn
```

# PortPriorityCompare(void const *,void const *)

- ea: `0x1800216d0`
- end: `0x1800216e9`
- name: `?PortPriorityCompare@@YAHPEBX0@Z`
- size: `25`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800216d0`

## pseudocode

```c
__int64 __fastcall PortPriorityCompare(_DWORD *a1, _DWORD *a2)
{
  unsigned int v2; // r8d

  v2 = a1[5];
  if ( v2 >= a2[5] )
    return v2 > a2[5];
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800216d0  mov     r8d, [rcx+14h]
0x1800216d4  cmp     r8d, [rdx+14h]
0x1800216d8  jnb     short loc_1800216DF
0x1800216da  or      eax, 0FFFFFFFFh
0x1800216dd  retn
0x1800216df  xor     eax, eax
0x1800216e1  cmp     r8d, [rdx+14h]
0x1800216e5  setnbe  al
0x1800216e8  retn
```

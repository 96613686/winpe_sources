# ValidateBaseKeyHandle

- ea: `0x180009740`
- end: `0x18000975c`
- name: `ValidateBaseKeyHandle`
- size: `28`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180008890`
- `0x180009570`
- `0x180009ba0`
- `0x18000acc0`
- `0x18000af30`
- `0x18000b1d0`
- `0x1800101c0`
- `0x180014510`
- `0x180014740`

## callees

- `0x180009740`

## pseudocode

```c
_DWORD *__fastcall ValidateBaseKeyHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x20u )
    return 0;
  result = 0;
  if ( a1[1] == 1431655762 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180009740  test    rcx, rcx
0x180009743  jz      short loc_180009759
0x180009745  cmp     dword ptr [rcx], 20h ; ' '
0x180009748  jb      short loc_180009759
0x18000974a  xor     eax, eax
0x18000974c  cmp     dword ptr [rcx+4], 55555552h
0x180009753  cmovz   rax, rcx
0x180009757  retn
0x180009759  xor     eax, eax
0x18000975b  retn
```

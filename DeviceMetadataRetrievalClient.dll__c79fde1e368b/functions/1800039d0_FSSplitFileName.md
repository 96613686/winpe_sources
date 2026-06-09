# FSSplitFileName

- ea: `0x1800039d0`
- end: `0x180003a0c`
- name: `FSSplitFileName`
- size: `60`
- prototype: `_WORD *__fastcall(_WORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003514`
- `0x1800038c8`
- `0x18000c880`
- `0x18000ca5c`

## callees

- `0x1800039d0`

## pseudocode

```c
_WORD *__fastcall FSSplitFileName(_WORD *a1)
{
  __int64 v2; // rcx
  _WORD *i; // rcx

  if ( !a1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  for ( i = &a1[v2]; *i != 92; --i )
  {
    if ( i == a1 )
      return 0;
  }
  if ( i == a1 )
    return 0;
  *i = 0;
  return i + 1;
}

```

## disassembly

```asm
0x1800039d0  xor     edx, edx
0x1800039d2  mov     rax, rcx
0x1800039d5  test    rcx, rcx
0x1800039d8  jz      short loc_180003A09
0x1800039da  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800039de  inc     rcx
0x1800039e1  cmp     [rax+rcx*2], dx
0x1800039e5  jnz     short loc_1800039DE
0x1800039e7  lea     rcx, [rax+rcx*2]
0x1800039eb  jmp     short loc_1800039F6
0x1800039ed  cmp     rcx, rax
0x1800039f0  jz      short loc_180003A09
0x1800039f2  sub     rcx, 2
0x1800039f6  cmp     word ptr [rcx], 5Ch ; '\'
0x1800039fa  jnz     short loc_1800039ED
0x1800039fc  cmp     rcx, rax
0x1800039ff  jz      short loc_180003A09
0x180003a01  mov     [rcx], dx
0x180003a04  lea     rax, [rcx+2]
0x180003a08  retn
0x180003a09  xor     eax, eax
0x180003a0b  retn
```

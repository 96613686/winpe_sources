# DtlAddNodeLast

- ea: `0x180025fe4`
- end: `0x18002601d`
- name: `DtlAddNodeLast`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002541c`
- `0x180025740`
- `0x180025d98`

## callees

- `0x180025fe4`

## pseudocode

```c
_QWORD *__fastcall DtlAddNodeLast(__int64 a1, _QWORD *a2)
{
  if ( a1 && a2 )
  {
    if ( *(_DWORD *)(a1 + 16) )
    {
      *a2 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = a2;
    }
    else
    {
      *a2 = 0;
      *(_QWORD *)a1 = a2;
    }
    *(_QWORD *)(a1 + 8) = a2;
    a2[1] = 0;
    ++*(_DWORD *)(a1 + 16);
  }
  return a2;
}

```

## disassembly

```asm
0x180025fe4  xor     r8d, r8d
0x180025fe7  test    rcx, rcx
0x180025fea  jz      short loc_180026019
0x180025fec  test    rdx, rdx
0x180025fef  jz      short loc_180026019
0x180025ff1  cmp     [rcx+10h], r8d
0x180025ff5  jz      short loc_180026008
0x180025ff7  mov     rax, [rcx+8]
0x180025ffb  mov     [rdx], rax
0x180025ffe  mov     rax, [rcx+8]
0x180026002  mov     [rax+8], rdx
0x180026006  jmp     short loc_18002600E
0x180026008  mov     [rdx], r8
0x18002600b  mov     [rcx], rdx
0x18002600e  mov     [rcx+8], rdx
0x180026012  mov     [rdx+8], r8
0x180026016  inc     dword ptr [rcx+10h]
0x180026019  mov     rax, rdx
0x18002601c  retn
```

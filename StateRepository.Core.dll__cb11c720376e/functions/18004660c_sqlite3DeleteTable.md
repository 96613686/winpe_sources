# sqlite3DeleteTable

- ea: `0x18004660c`
- end: `0x180046627`
- name: `sqlite3DeleteTable`
- size: `27`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180008894`
- `0x18000ca30`
- `0x18000d770`
- `0x1800184cc`
- `0x18001cd8c`
- `0x180030d98`
- `0x180039490`
- `0x1800461e0`
- `0x1800647cc`
- `0x180065c94`
- `0x1800830c0`
- `0x180087ae0`
- `0x18008995c`
- `0x180089bc4`
- `0x18008dfb0`
- `0x180094ddc`

## callees

- `0x18004660c`
- `0x1800569e0`

## pseudocode

```c
__int64 __fastcall sqlite3DeleteTable(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  if ( a2 )
  {
    if ( *(_QWORD *)(a1 + 776) )
      return deleteTable(a1, a2);
    if ( (*(_DWORD *)(a2 + 44))-- == 1 )
      return deleteTable(a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18004660c  test    rdx, rdx
0x18004660f  jz      short locret_180046621
0x180046611  cmp     qword ptr [rcx+308h], 0
0x180046619  jnz     short loc_180046622
0x18004661b  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x18004661f  jz      short loc_180046622
0x180046621  retn
0x180046622  jmp     deleteTable
```

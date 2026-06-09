# VfsCheckPackageDirectoryForRename

- ea: `0x14000b2a4`
- end: `0x14000b2d2`
- name: `VfsCheckPackageDirectoryForRename`
- size: `46`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ca28`
- `0x14000cd04`
- `0x14000cfd8`

## callees

- `0x14000b2a4`

## pseudocode

```c
__int64 __fastcall VfsCheckPackageDirectoryForRename(__int64 a1, __int64 a2)
{
  int v2; // ecx

  v2 = *(_DWORD *)(*(_QWORD *)(a2 + 24) + 272LL);
  if ( (v2 & 2) == 0 )
    return 0;
  if ( (*(_DWORD *)(a2 + 4) & 4) != 0 )
    return 3221225659LL;
  return (v2 & 4) != 0 ? 0xC00000BB : 0;
}

```

## disassembly

```asm
0x14000b2a4  mov     rax, [rdx+18h]
0x14000b2a8  mov     ecx, [rax+110h]
0x14000b2ae  test    cl, 2
0x14000b2b1  jz      short loc_14000B2CF
0x14000b2b3  mov     eax, [rdx+4]
0x14000b2b6  test    al, 4
0x14000b2b8  jnz     short loc_14000B2C8
0x14000b2ba  and     cl, 4
0x14000b2bd  neg     cl
0x14000b2bf  sbb     eax, eax
0x14000b2c1  and     eax, 0C00000BBh
0x14000b2c6  retn
0x14000b2c8  mov     eax, 0C00000BBh
0x14000b2cd  retn
0x14000b2cf  xor     eax, eax
0x14000b2d1  retn
```

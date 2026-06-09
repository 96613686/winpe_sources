# compare_same

- ea: `0x180061908`
- end: `0x18006192b`
- name: `compare_same`
- size: `35`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005f070`
- `0x180061998`
- `0x180061ab8`
- `0x180061b30`
- `0x1800622a0`
- `0x1800626cc`

## callees

- `0x180061908`

## pseudocode

```c
__int64 __fastcall compare_same(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // eax
  unsigned int v5; // edx

  while ( a3 )
  {
    --a3;
    v4 = *(_DWORD *)(a1 + 4 * a3);
    v5 = *(_DWORD *)(a2 + 4 * a3);
    if ( v5 != v4 )
      return v5 < v4 ? 1 : -1;
  }
  return 0;
}

```

## disassembly

```asm
0x180061908  mov     r9, rdx
0x18006190b  test    r8, r8
0x18006190e  jz      short loc_180061928
0x180061910  dec     r8
0x180061913  mov     eax, [rcx+r8*4]
0x180061917  mov     edx, [r9+r8*4]
0x18006191b  cmp     edx, eax
0x18006191d  jz      short loc_18006190B
0x18006191f  sbb     eax, eax
0x180061921  and     eax, 2
0x180061924  dec     eax
0x180061926  retn
0x180061928  xor     eax, eax
0x18006192a  retn
```

# CfpGetPlaceholderState

- ea: `0x18001a730`
- end: `0x18001a789`
- name: `CfpGetPlaceholderState`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b080`
- `0x18001a670`
- `0x18001a680`
- `0x18001a720`

## callees

- `0x18001a730`

## pseudocode

```c
__int64 __fastcall CfpGetPlaceholderState(int a1, int a2)
{
  unsigned int v2; // r8d

  v2 = 0;
  if ( (a1 & 0x400) != 0 && (a2 & 0xFFFF0FFF) == 0x9000001A )
  {
    v2 = (a1 & 0x440000) != 0 ? 17 : 1;
    if ( (a2 & 0x1000) != 0 )
      v2 |= 2u;
    if ( (a2 & 0x4000) != 0 )
      v2 |= 8u;
    if ( (a2 & 0x2000) == 0 )
      v2 |= 0x20u;
    if ( (a2 & 0x8000) != 0 )
      v2 |= 4u;
  }
  return v2;
}

```

## disassembly

```asm
0x18001a730  xor     r8d, r8d
0x18001a733  bt      ecx, 0Ah
0x18001a737  jnb     short loc_18001A785
0x18001a739  mov     eax, edx
0x18001a73b  and     eax, 0FFFF0FFFh
0x18001a740  cmp     eax, 9000001Ah
0x18001a745  jnz     short loc_18001A785
0x18001a747  and     ecx, 440000h
0x18001a74d  neg     ecx
0x18001a74f  sbb     r8d, r8d
0x18001a752  and     r8d, 10h
0x18001a756  inc     r8d
0x18001a759  bt      edx, 0Ch
0x18001a75d  jnb     short loc_18001A763
0x18001a75f  or      r8d, 2
0x18001a763  bt      edx, 0Eh
0x18001a767  jnb     short loc_18001A76D
0x18001a769  or      r8d, 8
0x18001a76d  mov     eax, r8d
0x18001a770  or      eax, 20h
0x18001a773  bt      edx, 0Dh
0x18001a777  cmovnb  r8d, eax
0x18001a77b  bt      edx, 0Fh
0x18001a77f  jnb     short loc_18001A785
0x18001a781  or      r8d, 4
0x18001a785  mov     eax, r8d
0x18001a788  retn
```

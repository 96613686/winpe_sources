# shfileSeek

- ea: `0x180014928`
- end: `0x180014959`
- name: `shfileSeek`
- size: `49`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000420c`
- `0x1800067a0`
- `0x180009800`
- `0x18000b87c`
- `0x18000c410`
- `0x180014468`
- `0x180014600`
- `0x180014694`

## callees

- `0x180014928`

## import_xrefs

- `WINMM!mmioSeek` at `0x180014952`

## pseudocode

```c
LONG __fastcall shfileSeek(__int64 a1, LONG a2, int a3)
{
  __int64 v3; // rax

  v3 = *(_QWORD *)(a1 + 16);
  if ( !v3 )
    return mmioSeek(*(HMMIO *)(a1 + 8), a2, a3);
  if ( a3 == 1 )
    a2 += *(_DWORD *)(v3 + 372);
  *(_DWORD *)(v3 + 372) = a2;
  return *(_DWORD *)(*(_QWORD *)(a1 + 16) + 372LL);
}

```

## disassembly

```asm
0x180014928  mov     rax, [rcx+10h]
0x18001492c  test    rax, rax
0x18001492f  jz      short loc_18001494E
0x180014931  cmp     r8d, 1
0x180014935  jnz     short loc_18001493D
0x180014937  add     edx, [rax+174h]
0x18001493d  mov     [rax+174h], edx
0x180014943  mov     rax, [rcx+10h]
0x180014947  mov     eax, [rax+174h]
0x18001494d  retn
0x18001494e  mov     rcx, [rcx+8]
0x180014952  jmp     cs:__imp_mmioSeek
```

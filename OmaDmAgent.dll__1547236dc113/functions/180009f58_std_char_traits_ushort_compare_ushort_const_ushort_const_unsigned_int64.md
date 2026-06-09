# std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)

- ea: `0x180009f58`
- end: `0x180009f80`
- name: `?compare@?$char_traits@G@std@@SAHPEBG0_K@Z`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009fb0`
- `0x180012af4`
- `0x18001e848`

## callees

- `0x180009f58`

## pseudocode

```c
__int64 __fastcall std::char_traits<unsigned short>::compare(_WORD *a1, _WORD *a2, __int64 a3)
{
  while ( a3 )
  {
    if ( *a1 != *a2 )
      return *a1 < *a2 ? -1 : 1;
    ++a1;
    ++a2;
    --a3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009f58  xchg    ax, ax
0x180009f5a  test    r8, r8
0x180009f5d  jz      short loc_180009F7D
0x180009f5f  movzx   eax, word ptr [rcx]
0x180009f62  cmp     ax, [rdx]
0x180009f65  jnz     short loc_180009F74
0x180009f67  add     rcx, 2
0x180009f6b  add     rdx, 2
0x180009f6f  dec     r8
0x180009f72  jmp     short loc_180009F5A
0x180009f74  sbb     eax, eax
0x180009f76  and     eax, 0FFFFFFFEh
0x180009f79  inc     eax
0x180009f7b  retn
0x180009f7d  xor     eax, eax
0x180009f7f  retn
```

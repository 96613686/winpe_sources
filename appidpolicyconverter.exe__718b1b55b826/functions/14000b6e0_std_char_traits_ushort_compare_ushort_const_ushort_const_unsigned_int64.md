# std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)

- ea: `0x14000b6e0`
- end: `0x14000b707`
- name: `?compare@?$char_traits@G@std@@SAHPEBG0_K@Z`
- size: `39`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b68c`
- `0x14001072c`

## callees

- `0x14000b6e0`

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
0x14000b6e0  xchg    ax, ax
0x14000b6e2  test    r8, r8
0x14000b6e5  jz      short loc_14000B704
0x14000b6e7  movzx   eax, word ptr [rcx]
0x14000b6ea  cmp     ax, [rdx]
0x14000b6ed  jnz     short loc_14000B6FC
0x14000b6ef  add     rcx, 2
0x14000b6f3  add     rdx, 2
0x14000b6f7  dec     r8
0x14000b6fa  jmp     short loc_14000B6E2
0x14000b6fc  sbb     eax, eax
0x14000b6fe  and     eax, 0FFFFFFFEh
0x14000b701  inc     eax
0x14000b703  retn
0x14000b704  xor     eax, eax
0x14000b706  retn
```

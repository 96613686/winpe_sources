# std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)

- ea: `0x140011e9c`
- end: `0x140011ec3`
- name: `?compare@?$char_traits@G@std@@SAHPEBG0_K@Z`
- size: `39`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011e48`
- `0x140012878`

## callees

- `0x140011e9c`

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
0x140011e9c  xchg    ax, ax
0x140011e9e  test    r8, r8
0x140011ea1  jz      short loc_140011EC0
0x140011ea3  movzx   eax, word ptr [rcx]
0x140011ea6  cmp     ax, [rdx]
0x140011ea9  jnz     short loc_140011EB8
0x140011eab  add     rcx, 2
0x140011eaf  add     rdx, 2
0x140011eb3  dec     r8
0x140011eb6  jmp     short loc_140011E9E
0x140011eb8  sbb     eax, eax
0x140011eba  and     eax, 0FFFFFFFEh
0x140011ebd  inc     eax
0x140011ebf  retn
0x140011ec0  xor     eax, eax
0x140011ec2  retn
```

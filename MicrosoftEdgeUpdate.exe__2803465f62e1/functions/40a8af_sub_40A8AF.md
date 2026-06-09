# sub_40A8AF

- ea: `0x40a8af`
- end: `0x40a8da`
- name: `sub_40A8AF`
- size: `43`
- prototype: `int __fastcall(_DWORD *Block, unsigned int)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x409fa6`
- `0x40a034`
- `0x40a410`
- `0x40a4de`
- `0x40a581`
- `0x40a616`
- `0x40a6a7`
- `0x40a75a`
- `0x40a7db`
- `0x40aab8`

## callees

- `0x40a8af`
- `0x40b61e`
- `0x40de64`

## pseudocode

```c
int __fastcall sub_40A8AF(_DWORD *Block, unsigned int a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned int)Block - *(Block - 1) - 4 > 0x1F )
      _invalid_parameter_noinfo_noreturn();
    Block = (_DWORD *)*(Block - 1);
  }
  return sub_40B61E(Block);
}

```

## disassembly

```asm
0x40a8af  cmp     edx, 1000h
0x40a8b5  jb      short loc_40A8CB
0x40a8b7  push    esi
0x40a8b8  mov     esi, [ecx-4]
0x40a8bb  add     edx, 23h ; '#'
0x40a8be  sub     ecx, esi
0x40a8c0  lea     eax, [ecx-4]
0x40a8c3  cmp     eax, 1Fh
0x40a8c6  ja      short loc_40A8D5
0x40a8c8  mov     ecx, esi
0x40a8ca  pop     esi
0x40a8cb  push    edx
0x40a8cc  push    ecx; Block
0x40a8cd  call    sub_40B61E
0x40a8d2  pop     ecx
0x40a8d3  pop     ecx
0x40a8d4  retn
0x40a8d5  call    __invalid_parameter_noinfo_noreturn
```

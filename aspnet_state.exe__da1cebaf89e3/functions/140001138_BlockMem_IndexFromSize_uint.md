# BlockMem::IndexFromSize(uint)

- ea: `0x140001138`
- end: `0x1400011ac`
- name: `?IndexFromSize@BlockMem@@CAHI@Z`
- size: `116`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001090`
- `0x1400011ac`

## callees

- `0x140001138`

## pseudocode

```c
__int64 __fastcall BlockMem::IndexFromSize(unsigned int a1)
{
  unsigned int v1; // r8d
  __int64 result; // rax

  if ( (a1 & 0xFFFF0000) != 0 )
  {
    v1 = (a1 & 0xFF000000) != 0 ? 0x80000000 : 0x800000;
    result = (a1 & 0xFF000000) != 0 ? 64 : 48;
  }
  else if ( (a1 & 0xFF00) != 0 )
  {
    result = 32;
    v1 = 0x8000;
  }
  else
  {
    result = 16;
    v1 = 128;
  }
  while ( v1 > a1 )
  {
    v1 >>= 1;
    result = (unsigned int)(result - 2);
  }
  if ( v1 < a1 )
  {
    result = (unsigned int)(result + 1);
    if ( v1 + (v1 >> 1) < a1 )
      return (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x140001138  mov     r9d, ecx
0x14000113b  test    ecx, 0FFFF0000h
0x140001141  jz      short loc_14000116C
0x140001143  mov     edx, ecx
0x140001145  and     edx, 0FF000000h
0x14000114b  mov     eax, edx
0x14000114d  neg     eax
0x14000114f  sbb     r8d, r8d
0x140001152  and     r8d, 7F800000h
0x140001159  add     r8d, 800000h
0x140001160  neg     edx
0x140001162  sbb     eax, eax
0x140001164  and     eax, 10h
0x140001167  add     eax, 30h ; '0'
0x14000116a  jmp     short loc_140001193
0x14000116c  test    r9d, 0FF00h
0x140001173  jz      short loc_140001182
0x140001175  mov     eax, 20h ; ' '
0x14000117a  mov     r8d, 8000h
0x140001180  jmp     short loc_140001193
0x140001182  mov     eax, 10h
0x140001187  lea     r8d, [rax+70h]
0x14000118b  jmp     short loc_140001193
0x14000118d  shr     r8d, 1
0x140001190  sub     eax, 2
0x140001193  cmp     r8d, r9d
0x140001196  ja      short loc_14000118D
0x140001198  jnb     short locret_1400011AB
0x14000119a  mov     ecx, r8d
0x14000119d  inc     eax
0x14000119f  shr     ecx, 1
0x1400011a1  add     ecx, r8d
0x1400011a4  cmp     ecx, r9d
0x1400011a7  jnb     short locret_1400011AB
0x1400011a9  inc     eax
0x1400011ab  retn
```

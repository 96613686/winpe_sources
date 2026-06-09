# sub_409FFF

- ea: `0x409fff`
- end: `0x40a034`
- name: `sub_409FFF`
- size: `53`
- prototype: `_DWORD *__thiscall(_DWORD *this, void *Src)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x408153`
- `0x4081d0`
- `0x408685`
- `0x4089b5`
- `0x4089ff`

## callees

- `0x409fff`
- `0x40a0b1`

## pseudocode

```c
_DWORD *__thiscall sub_409FFF(_DWORD *this, void *Src)
{
  *this = 0;
  this[4] = 0;
  this[5] = 15;
  sub_40A0B1(this, Src, strlen((const char *)Src));
  return this;
}

```

## disassembly

```asm
0x409fff  push    ebp
0x40a000  mov     ebp, esp
0x40a002  mov     edx, [ebp+Src]
0x40a005  push    esi
0x40a006  mov     esi, ecx
0x40a008  lea     ecx, [edx+1]
0x40a00b  and     dword ptr [esi], 0
0x40a00e  and     dword ptr [esi+10h], 0
0x40a012  mov     dword ptr [esi+14h], 0Fh
0x40a019  mov     al, [edx]
0x40a01b  inc     edx
0x40a01c  test    al, al
0x40a01e  jnz     short loc_40A019
0x40a020  sub     edx, ecx
0x40a022  mov     ecx, esi; void *
0x40a024  push    edx; Size
0x40a025  push    [ebp+Src]; Src
0x40a028  call    sub_40A0B1
0x40a02d  mov     eax, esi
0x40a02f  pop     esi
0x40a030  pop     ebp
0x40a031  retn    4
```

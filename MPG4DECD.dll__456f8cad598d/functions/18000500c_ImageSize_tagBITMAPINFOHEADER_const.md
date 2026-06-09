# ImageSize(tagBITMAPINFOHEADER const *)

- ea: `0x18000500c`
- end: `0x1800050b5`
- name: `?ImageSize@@YAKPEBUtagBITMAPINFOHEADER@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(const struct tagBITMAPINFOHEADER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004620`
- `0x180004810`
- `0x180007440`

## callees

- `0x18000500c`

## pseudocode

```c
__int64 __fastcall ImageSize(const struct tagBITMAPINFOHEADER *a1)
{
  unsigned int v2; // ecx
  __int64 result; // rax
  unsigned int v4; // eax
  int v5; // ecx
  LONG biWidth; // ecx
  int v7; // eax
  LONG biHeight; // ecx

  if ( a1->biCompression == 808530550 )
  {
    biWidth = -a1->biWidth;
    if ( biWidth < 0 )
      biWidth = a1->biWidth;
    v7 = (biWidth + 47) / 48;
    biHeight = -a1->biHeight;
    if ( a1->biHeight > 0 )
      biHeight = a1->biHeight;
    return (unsigned int)((biHeight * v7) << 7);
  }
  else if ( a1->biCompression == 808596553
         || a1->biCompression == 825316942
         || a1->biCompression == 842094158
         || a1->biCompression == 842094169
         || a1->biCompression == 1448433993 )
  {
    v4 = a1->biWidth * a1->biHeight * a1->biBitCount / 8;
    v5 = a1->biWidth * a1->biHeight * a1->biBitCount / -8;
    if ( v5 < 0 )
      return v4;
    return (unsigned int)v5;
  }
  else
  {
    v2 = a1->biHeight * (((a1->biWidth * (unsigned int)a1->biBitCount + 31) >> 3) & 0x1FFFFFFC);
    result = -v2;
    if ( a1->biHeight >= 0 )
      return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18000500c  mov     edx, [rcx+10h]
0x18000500f  mov     r8, rcx
0x180005012  sub     edx, 30313276h
0x180005018  jz      short loc_180005085
0x18000501a  sub     edx, 101D3h
0x180005020  jz      short loc_180005066
0x180005022  sub     edx, 0FF2205h
0x180005028  jz      short loc_180005066
0x18000502a  sub     edx, 1000000h
0x180005030  jz      short loc_180005066
0x180005032  sub     edx, 0Bh
0x180005035  jz      short loc_180005066
0x180005037  cmp     edx, 242402F0h
0x18000503d  jz      short loc_180005066
0x18000503f  movzx   ecx, word ptr [rcx+0Eh]
0x180005043  imul    ecx, [r8+4]
0x180005048  add     ecx, 1Fh
0x18000504b  shr     ecx, 3
0x18000504e  and     ecx, 1FFFFFFCh
0x180005054  imul    ecx, [r8+8]
0x180005059  mov     eax, ecx
0x18000505b  neg     eax
0x18000505d  cmp     dword ptr [r8+8], 0
0x180005062  cmovge  eax, ecx
0x180005065  retn
0x180005066  movzx   eax, word ptr [rcx+0Eh]
0x18000506a  imul    eax, [rcx+8]
0x18000506e  imul    eax, [rcx+4]
0x180005072  cdq
0x180005073  and     edx, 7
0x180005076  add     eax, edx
0x180005078  sar     eax, 3
0x18000507b  mov     ecx, eax
0x18000507d  neg     ecx
0x18000507f  cmovs   ecx, eax
0x180005082  mov     eax, ecx
0x180005084  retn
0x180005085  mov     ecx, [rcx+4]
0x180005088  mov     eax, 2AAAAAABh
0x18000508d  neg     ecx
0x18000508f  cmovs   ecx, [r8+4]
0x180005094  add     ecx, 2Fh ; '/'
0x180005097  imul    ecx
0x180005099  mov     ecx, [r8+8]
0x18000509d  sar     edx, 3
0x1800050a0  mov     eax, edx
0x1800050a2  shr     eax, 1Fh
0x1800050a5  add     eax, edx
0x1800050a7  neg     ecx
0x1800050a9  cmovs   ecx, [r8+8]
0x1800050ae  imul    eax, ecx
0x1800050b1  shl     eax, 7
0x1800050b4  retn
```

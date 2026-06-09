# ImageSize(tagBITMAPINFOHEADER const *)

- ea: `0x180004f4c`
- end: `0x180004ff5`
- name: `?ImageSize@@YAKPEBUtagBITMAPINFOHEADER@@@Z`
- size: `169`
- prototype: `unsigned int __fastcall(const struct tagBITMAPINFOHEADER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004560`
- `0x180004750`
- `0x180007380`

## callees

- `0x180004f4c`

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
0x180004f4c  mov     edx, [rcx+10h]
0x180004f4f  mov     r8, rcx
0x180004f52  sub     edx, 30313276h
0x180004f58  jz      short loc_180004FC5
0x180004f5a  sub     edx, 101D3h
0x180004f60  jz      short loc_180004FA6
0x180004f62  sub     edx, 0FF2205h
0x180004f68  jz      short loc_180004FA6
0x180004f6a  sub     edx, 1000000h
0x180004f70  jz      short loc_180004FA6
0x180004f72  sub     edx, 0Bh
0x180004f75  jz      short loc_180004FA6
0x180004f77  cmp     edx, 242402F0h
0x180004f7d  jz      short loc_180004FA6
0x180004f7f  movzx   ecx, word ptr [rcx+0Eh]
0x180004f83  imul    ecx, [r8+4]
0x180004f88  add     ecx, 1Fh
0x180004f8b  shr     ecx, 3
0x180004f8e  and     ecx, 1FFFFFFCh
0x180004f94  imul    ecx, [r8+8]
0x180004f99  mov     eax, ecx
0x180004f9b  neg     eax
0x180004f9d  cmp     dword ptr [r8+8], 0
0x180004fa2  cmovge  eax, ecx
0x180004fa5  retn
0x180004fa6  movzx   eax, word ptr [rcx+0Eh]
0x180004faa  imul    eax, [rcx+8]
0x180004fae  imul    eax, [rcx+4]
0x180004fb2  cdq
0x180004fb3  and     edx, 7
0x180004fb6  add     eax, edx
0x180004fb8  sar     eax, 3
0x180004fbb  mov     ecx, eax
0x180004fbd  neg     ecx
0x180004fbf  cmovs   ecx, eax
0x180004fc2  mov     eax, ecx
0x180004fc4  retn
0x180004fc5  mov     ecx, [rcx+4]
0x180004fc8  mov     eax, 2AAAAAABh
0x180004fcd  neg     ecx
0x180004fcf  cmovs   ecx, [r8+4]
0x180004fd4  add     ecx, 2Fh ; '/'
0x180004fd7  imul    ecx
0x180004fd9  mov     ecx, [r8+8]
0x180004fdd  sar     edx, 3
0x180004fe0  mov     eax, edx
0x180004fe2  shr     eax, 1Fh
0x180004fe5  add     eax, edx
0x180004fe7  neg     ecx
0x180004fe9  cmovs   ecx, [r8+8]
0x180004fee  imul    eax, ecx
0x180004ff1  shl     eax, 7
0x180004ff4  retn
```

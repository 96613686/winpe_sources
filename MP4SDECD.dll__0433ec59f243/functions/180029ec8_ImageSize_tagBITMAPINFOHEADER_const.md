# ImageSize(tagBITMAPINFOHEADER const *)

- ea: `0x180029ec8`
- end: `0x180029f71`
- name: `?ImageSize@@YAKPEBUtagBITMAPINFOHEADER@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(const struct tagBITMAPINFOHEADER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012cd0`
- `0x180012e50`
- `0x180029020`

## callees

- `0x180029ec8`

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
0x180029ec8  mov     edx, [rcx+10h]
0x180029ecb  mov     r8, rcx
0x180029ece  sub     edx, 30313276h
0x180029ed4  jz      short loc_180029F41
0x180029ed6  sub     edx, 101D3h
0x180029edc  jz      short loc_180029F22
0x180029ede  sub     edx, 0FF2205h
0x180029ee4  jz      short loc_180029F22
0x180029ee6  sub     edx, 1000000h
0x180029eec  jz      short loc_180029F22
0x180029eee  sub     edx, 0Bh
0x180029ef1  jz      short loc_180029F22
0x180029ef3  cmp     edx, 242402F0h
0x180029ef9  jz      short loc_180029F22
0x180029efb  movzx   ecx, word ptr [rcx+0Eh]
0x180029eff  imul    ecx, [r8+4]
0x180029f04  add     ecx, 1Fh
0x180029f07  shr     ecx, 3
0x180029f0a  and     ecx, 1FFFFFFCh
0x180029f10  imul    ecx, [r8+8]
0x180029f15  mov     eax, ecx
0x180029f17  neg     eax
0x180029f19  cmp     dword ptr [r8+8], 0
0x180029f1e  cmovge  eax, ecx
0x180029f21  retn
0x180029f22  movzx   eax, word ptr [rcx+0Eh]
0x180029f26  imul    eax, [rcx+8]
0x180029f2a  imul    eax, [rcx+4]
0x180029f2e  cdq
0x180029f2f  and     edx, 7
0x180029f32  add     eax, edx
0x180029f34  sar     eax, 3
0x180029f37  mov     ecx, eax
0x180029f39  neg     ecx
0x180029f3b  cmovs   ecx, eax
0x180029f3e  mov     eax, ecx
0x180029f40  retn
0x180029f41  mov     ecx, [rcx+4]
0x180029f44  mov     eax, 2AAAAAABh
0x180029f49  neg     ecx
0x180029f4b  cmovs   ecx, [r8+4]
0x180029f50  add     ecx, 2Fh ; '/'
0x180029f53  imul    ecx
0x180029f55  mov     ecx, [r8+8]
0x180029f59  sar     edx, 3
0x180029f5c  mov     eax, edx
0x180029f5e  shr     eax, 1Fh
0x180029f61  add     eax, edx
0x180029f63  neg     ecx
0x180029f65  cmovs   ecx, [r8+8]
0x180029f6a  imul    eax, ecx
0x180029f6d  shl     eax, 7
0x180029f70  retn
```

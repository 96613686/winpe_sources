# g_ConfigureBMPSizeAndPointersInfo_OnScreen(tagBITMAPINFOHEADER *,CDeColorConvParams *,long,long,long,long,long,long,ulong,ulong,ulong)

- ea: `0x18001e1d0`
- end: `0x18001e2c0`
- name: `?g_ConfigureBMPSizeAndPointersInfo_OnScreen@@YAXPEAUtagBITMAPINFOHEADER@@PEAVCDeColorConvParams@@JJJJJJKKK@Z`
- size: `240`
- prototype: `void __fastcall(struct tagBITMAPINFOHEADER *, struct CDeColorConvParams *, int, int, int, int, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001e2c8`

## callees

- `0x18001e1d0`

## pseudocode

```c
void __fastcall g_ConfigureBMPSizeAndPointersInfo_OnScreen(
        struct tagBITMAPINFOHEADER *a1,
        struct CDeColorConvParams *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  int v8; // r8d
  unsigned int v11; // r10d
  int v12; // eax
  unsigned int v13; // r10d
  int v14; // eax
  int v15; // ecx
  int v16; // edx
  LONG biHeight; // edx
  int v18; // ebx
  LONG v19; // eax
  int v20; // r8d
  int v21; // r10d
  int v22; // r11d
  int v23; // ecx
  int v24; // eax

  v8 = *((_DWORD *)a2 + 2);
  v11 = *((unsigned __int16 *)a2 + 7);
  v12 = *((_DWORD *)a2 + 1) * v11;
  v13 = v11 >> 3;
  *((_DWORD *)a2 + 17) = v13;
  v14 = (int)((v12 + 31) & 0xFFFFFFE0) / 8;
  v15 = -v8;
  *((_DWORD *)a2 + 16) = v14;
  v16 = v14;
  if ( v8 > 0 )
    v15 = v8;
  *((_DWORD *)a2 + 18) = v14 * v15;
  if ( v8 > 0 )
  {
    v16 = -v14;
    *((_DWORD *)a2 + 16) = -v14;
  }
  *((_DWORD *)a2 + 19) = 16 * v13;
  *((_DWORD *)a2 + 20) = 8 * v13;
  *((_DWORD *)a2 + 21) = 16 * v16;
  *((_DWORD *)a2 + 22) = 8 * (v16 - v13);
  biHeight = a1->biHeight;
  v18 = (int)((a1->biWidth * a1->biBitCount + 31) & 0xFFFFFFE0) / 8;
  v19 = -biHeight;
  if ( biHeight > 0 )
    v19 = a1->biHeight;
  v20 = a6 * v18;
  v21 = a5 * v13;
  v22 = v18 * (a8 - 1);
  if ( biHeight >= 0 )
  {
    v23 = v21 + v22 + v20;
    v24 = v23;
  }
  else
  {
    v23 = 0;
    v24 = v21 + v18 * (v19 - 1) - v22 - v20;
  }
  *((_DWORD *)a2 + 26) = v24;
  *((_DWORD *)a2 + 27) = v23;
  *((_DWORD *)a2 + 28) = v23;
  *((_DWORD *)a2 + 29) = v23;
}

```

## disassembly

```asm
0x18001e1d0  mov     [rsp+arg_0], rbx
0x18001e1d5  mov     r8d, [rdx+8]
0x18001e1d9  mov     r9, rdx
0x18001e1dc  movzx   eax, word ptr [rdx+0Eh]
0x18001e1e0  mov     r11, rcx
0x18001e1e3  mov     r10d, eax
0x18001e1e6  mov     ecx, r8d
0x18001e1e9  imul    eax, [rdx+4]
0x18001e1ed  shr     r10d, 3
0x18001e1f1  mov     [rdx+44h], r10d
0x18001e1f5  add     eax, 1Fh
0x18001e1f8  and     eax, 0FFFFFFE0h
0x18001e1fb  cdq
0x18001e1fc  and     edx, 7
0x18001e1ff  add     eax, edx
0x18001e201  sar     eax, 3
0x18001e204  neg     ecx
0x18001e206  mov     [r9+40h], eax
0x18001e20a  mov     edx, eax
0x18001e20c  cmovs   ecx, r8d
0x18001e210  imul    ecx, eax
0x18001e213  mov     [r9+48h], ecx
0x18001e217  test    r8d, r8d
0x18001e21a  jle     short loc_18001E222
0x18001e21c  neg     edx
0x18001e21e  mov     [r9+40h], edx
0x18001e222  mov     eax, r10d
0x18001e225  shl     eax, 4
0x18001e228  mov     [r9+4Ch], eax
0x18001e22c  lea     eax, ds:0[r10*8]
0x18001e234  mov     [r9+50h], eax
0x18001e238  mov     eax, edx
0x18001e23a  shl     eax, 4
0x18001e23d  sub     edx, r10d
0x18001e240  mov     [r9+54h], eax
0x18001e244  shl     edx, 3
0x18001e247  mov     [r9+58h], edx
0x18001e24b  movzx   eax, word ptr [r11+0Eh]
0x18001e250  imul    eax, [r11+4]
0x18001e255  add     eax, 1Fh
0x18001e258  and     eax, 0FFFFFFE0h
0x18001e25b  cdq
0x18001e25c  and     edx, 7
0x18001e25f  lea     ebx, [rdx+rax]
0x18001e262  mov     edx, [r11+8]
0x18001e266  mov     r11d, [rsp+arg_38]
0x18001e26b  mov     eax, edx
0x18001e26d  sar     ebx, 3
0x18001e270  neg     eax
0x18001e272  mov     r8d, ebx
0x18001e275  cmovs   eax, edx
0x18001e278  imul    r8d, [rsp+arg_28]
0x18001e27e  imul    r10d, [rsp+arg_20]
0x18001e284  dec     r11d
0x18001e287  imul    r11d, ebx
0x18001e28b  test    edx, edx
0x18001e28d  jns     short loc_18001E2A1
0x18001e28f  xor     ecx, ecx
0x18001e291  dec     eax
0x18001e293  imul    eax, ebx
0x18001e296  sub     eax, r11d
0x18001e299  sub     eax, r8d
0x18001e29c  add     eax, r10d
0x18001e29f  jmp     short loc_18001E2AA
0x18001e2a1  lea     ecx, [r11+r8]
0x18001e2a5  add     ecx, r10d
0x18001e2a8  mov     eax, ecx
0x18001e2aa  mov     [r9+68h], eax
0x18001e2ae  mov     [r9+6Ch], ecx
0x18001e2b2  mov     [r9+70h], ecx
0x18001e2b6  mov     [r9+74h], ecx
0x18001e2ba  mov     rbx, [rsp+arg_0]
0x18001e2bf  retn
```

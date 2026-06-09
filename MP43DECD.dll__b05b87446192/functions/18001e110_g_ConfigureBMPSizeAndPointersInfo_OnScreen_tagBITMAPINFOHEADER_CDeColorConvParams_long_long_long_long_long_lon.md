# g_ConfigureBMPSizeAndPointersInfo_OnScreen(tagBITMAPINFOHEADER *,CDeColorConvParams *,long,long,long,long,long,long,ulong,ulong,ulong)

- ea: `0x18001e110`
- end: `0x18001e200`
- name: `?g_ConfigureBMPSizeAndPointersInfo_OnScreen@@YAXPEAUtagBITMAPINFOHEADER@@PEAVCDeColorConvParams@@JJJJJJKKK@Z`
- size: `240`
- prototype: `void __fastcall(struct tagBITMAPINFOHEADER *, struct CDeColorConvParams *, __int64, __int64, int, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001e208`

## callees

- `0x18001e110`

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
0x18001e110  mov     [rsp+arg_0], rbx
0x18001e115  mov     r8d, [rdx+8]
0x18001e119  mov     r9, rdx
0x18001e11c  movzx   eax, word ptr [rdx+0Eh]
0x18001e120  mov     r11, rcx
0x18001e123  mov     r10d, eax
0x18001e126  mov     ecx, r8d
0x18001e129  imul    eax, [rdx+4]
0x18001e12d  shr     r10d, 3
0x18001e131  mov     [rdx+44h], r10d
0x18001e135  add     eax, 1Fh
0x18001e138  and     eax, 0FFFFFFE0h
0x18001e13b  cdq
0x18001e13c  and     edx, 7
0x18001e13f  add     eax, edx
0x18001e141  sar     eax, 3
0x18001e144  neg     ecx
0x18001e146  mov     [r9+40h], eax
0x18001e14a  mov     edx, eax
0x18001e14c  cmovs   ecx, r8d
0x18001e150  imul    ecx, eax
0x18001e153  mov     [r9+48h], ecx
0x18001e157  test    r8d, r8d
0x18001e15a  jle     short loc_18001E162
0x18001e15c  neg     edx
0x18001e15e  mov     [r9+40h], edx
0x18001e162  mov     eax, r10d
0x18001e165  shl     eax, 4
0x18001e168  mov     [r9+4Ch], eax
0x18001e16c  lea     eax, ds:0[r10*8]
0x18001e174  mov     [r9+50h], eax
0x18001e178  mov     eax, edx
0x18001e17a  shl     eax, 4
0x18001e17d  sub     edx, r10d
0x18001e180  mov     [r9+54h], eax
0x18001e184  shl     edx, 3
0x18001e187  mov     [r9+58h], edx
0x18001e18b  movzx   eax, word ptr [r11+0Eh]
0x18001e190  imul    eax, [r11+4]
0x18001e195  add     eax, 1Fh
0x18001e198  and     eax, 0FFFFFFE0h
0x18001e19b  cdq
0x18001e19c  and     edx, 7
0x18001e19f  lea     ebx, [rdx+rax]
0x18001e1a2  mov     edx, [r11+8]
0x18001e1a6  mov     r11d, [rsp+arg_38]
0x18001e1ab  mov     eax, edx
0x18001e1ad  sar     ebx, 3
0x18001e1b0  neg     eax
0x18001e1b2  mov     r8d, ebx
0x18001e1b5  cmovs   eax, edx
0x18001e1b8  imul    r8d, [rsp+arg_28]
0x18001e1be  imul    r10d, [rsp+arg_20]
0x18001e1c4  dec     r11d
0x18001e1c7  imul    r11d, ebx
0x18001e1cb  test    edx, edx
0x18001e1cd  jns     short loc_18001E1E1
0x18001e1cf  xor     ecx, ecx
0x18001e1d1  dec     eax
0x18001e1d3  imul    eax, ebx
0x18001e1d6  sub     eax, r11d
0x18001e1d9  sub     eax, r8d
0x18001e1dc  add     eax, r10d
0x18001e1df  jmp     short loc_18001E1EA
0x18001e1e1  lea     ecx, [r11+r8]
0x18001e1e5  add     ecx, r10d
0x18001e1e8  mov     eax, ecx
0x18001e1ea  mov     [r9+68h], eax
0x18001e1ee  mov     [r9+6Ch], ecx
0x18001e1f2  mov     [r9+70h], ecx
0x18001e1f6  mov     [r9+74h], ecx
0x18001e1fa  mov     rbx, [rsp+arg_0]
0x18001e1ff  retn
```

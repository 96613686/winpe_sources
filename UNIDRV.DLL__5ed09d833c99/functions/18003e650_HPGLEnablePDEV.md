# HPGLEnablePDEV

- ea: `0x18003e650`
- end: `0x18003e9c2`
- name: `HPGLEnablePDEV`
- size: `882`
- prototype: `_DWORD *__fastcall(_QWORD *, __int64, __int64, __int64, unsigned int, __int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18003e650`
- `0x1800462f4`
- `0x1800498cc`
- `0x18004a71c`
- `0x1800631dc`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18003e936`
- `WINSPOOL!GetPrinterDataW` at `0x18003e936`
- `KERNEL32!LocalFree` at `0x18003e9a6`
- `KERNEL32!LocalFree` at `0x18003e9a6`
- `KERNEL32!LocalAlloc` at `0x18003e69e`
- `KERNEL32!LocalAlloc` at `0x18003e69e`
- `GDI32!EngCreatePalette` at `0x18003e7be`
- `GDI32!EngCreatePalette` at `0x18003e7be`
- `GDI32!EngDeletePalette` at `0x18003e990`
- `GDI32!EngDeletePalette` at `0x18003e990`

## pseudocode

```c
_DWORD *__fastcall HPGLEnablePDEV(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9)
{
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  __int64 v12; // r8
  __int64 i; // rcx
  int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rbx
  HPALETTE Palette; // rax
  _DWORD *v18; // rax
  _DWORD *v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  BrushCache *v26; // rax
  BrushCache *v27; // rax
  BrushCache *v28; // rax
  BrushCache *v29; // rax
  BrushCache *v30; // rcx
  void *v31; // rcx
  HPALETTE v33; // rcx
  DWORD pcbNeeded[18]; // [rsp+30h] [rbp-48h] BYREF
  int pData; // [rsp+80h] [rbp+8h] BYREF

  pData = 0;
  pcbNeeded[0] = 0;
  if ( !a1 )
    return 0;
  if ( a5 < 0x140 )
    return 0;
  if ( a7 < 0x138 )
    return 0;
  v10 = LocalAlloc(0, 0x1188u);
  v11 = v10;
  if ( !v10 )
    return 0;
  memset_0(v10, 0, 0x1188u);
  v12 = a9;
  *v11 = 1752196972;
  v11[1108] = -1;
  for ( i = 0; i != 23; ++i )
  {
    v14 = *(_DWORD *)(v12 + 4);
    v15 = *(_QWORD *)(v12 + 8);
    while ( v14 >= 0 )
    {
      if ( LODWORD(qword_1800925A0[2 * i]) == *(_DWORD *)v15 )
      {
        *(_QWORD *)&v11[2 * i + 2] = *(_QWORD *)(v15 + 8);
        break;
      }
      --v14;
      v15 += 16;
    }
  }
  v11[48] = 0;
  v11[1082] = 255;
  v11[1087] = -1;
  v11[1083] = -1;
  memset_0(v11 + 567, -1, 0x400u);
  v11[1084] = -1;
  v16 = a8;
  v11[1091] = 1;
  v11[1092] = 1;
  v11[1093] = 1;
  v11[1088] = 7;
  v11[1089] = 4;
  *(_DWORD *)v16 = -536870401;
  *(_QWORD *)(v16 + 284) = 5;
  v11[1098] = 0;
  v11[1100] = 1;
  Palette = EngCreatePalette(4u, 0, 0, 0, 0, 0);
  *(_QWORD *)(v16 + 296) = Palette;
  *((_QWORD *)v11 + 548) = Palette;
  v11[1090] = 4;
  v18 = (_DWORD *)a1[483];
  if ( !v18 )
    goto LABEL_19;
  if ( *v18 != 2400 )
  {
    if ( *v18 == 1200 )
    {
      v11[1099] = 3;
      goto LABEL_20;
    }
    if ( *v18 == 300 )
    {
      v11[1099] = 1;
      goto LABEL_20;
    }
LABEL_19:
    v11[1099] = 2;
    goto LABEL_20;
  }
  v11[1099] = 4;
LABEL_20:
  v19 = (_DWORD *)a1[485];
  if ( !v19 || (v20 = 1, *v19 != 1) )
    v20 = 0;
  v11[1116] = v20;
  if ( !v20 )
    *(_DWORD *)(a6 + 240) = 0;
  v11[1118] = 1;
  v21 = a1[498];
  if ( v21 )
  {
    v22 = *(_DWORD *)(v21 + 24) - 1;
    if ( v22 && (v23 = v22 - 1) != 0 )
    {
      v24 = v23 - 1;
      if ( v24 && (v25 = v24 - 1) != 0 )
      {
        if ( v25 == 1 )
          v11[1118] = 4;
      }
      else
      {
        v11[1118] = 3;
      }
    }
    else
    {
      v11[1118] = 2;
    }
  }
  v26 = (BrushCache *)operator new(0x18u);
  if ( v26 )
    v27 = BrushCache::BrushCache(v26);
  else
    v27 = 0;
  *((_QWORD *)v11 + 551) = v27;
  v28 = (BrushCache *)operator new(0x18u);
  if ( v28 )
    v29 = BrushCache::BrushCache(v28);
  else
    v29 = 0;
  v30 = (BrushCache *)*((_QWORD *)v11 + 551);
  *((_QWORD *)v11 + 552) = v29;
  if ( !v30 )
    goto LABEL_50;
  if ( !v29 || !*((_QWORD *)v30 + 2) || !*((_QWORD *)v29 + 2) )
  {
    BrushCache::`scalar deleting destructor'(v30);
    v29 = (BrushCache *)*((_QWORD *)v11 + 552);
    *((_QWORD *)v11 + 551) = 0;
LABEL_50:
    if ( v29 )
    {
      BrushCache::`scalar deleting destructor'(v29);
      *((_QWORD *)v11 + 552) = 0;
    }
    v33 = (HPALETTE)*((_QWORD *)v11 + 548);
    if ( v33 )
    {
      EngDeletePalette(v33);
      *((_QWORD *)v11 + 548) = 0;
    }
    LocalFree(v11);
    return 0;
  }
  v31 = (void *)a1[3];
  if ( v31 && !GetPrinterDataW(v31, (LPWSTR)L"UseNupHalftoneMatrix", 0, (LPBYTE)&pData, 4u, pcbNeeded) && pData == 1 )
    v11[1106] |= 0x80u;
  return v11;
}

```

## disassembly

```asm
0x18003e650  mov     rax, rsp
0x18003e653  push    rbx
0x18003e654  push    rbp
0x18003e655  push    rsi
0x18003e656  push    rdi
0x18003e657  push    r14
0x18003e659  push    r15
0x18003e65b  sub     rsp, 48h
0x18003e65f  xor     ebp, ebp
0x18003e661  mov     rsi, rcx
0x18003e664  mov     [rax+8], ebp
0x18003e667  mov     [rax-48h], ebp
0x18003e66a  test    rcx, rcx
0x18003e66d  jz      loc_18003E9B2
0x18003e673  cmp     [rsp+78h+arg_20], 140h
0x18003e67e  jb      loc_18003E9B2
0x18003e684  cmp     [rsp+78h+arg_30], 138h
0x18003e68f  jb      loc_18003E9B2
0x18003e695  mov     ebx, 1188h
0x18003e69a  xor     ecx, ecx; uFlags
0x18003e69c  mov     edx, ebx; uBytes
0x18003e69e  call    cs:__imp_LocalAlloc
0x18003e6a5  nop     dword ptr [rax+rax+00h]
0x18003e6aa  mov     rdi, rax
0x18003e6ad  test    rax, rax
0x18003e6b0  jz      loc_18003E9B2
0x18003e6b6  mov     r8d, ebx; Size
0x18003e6b9  xor     edx, edx; Val
0x18003e6bb  mov     rcx, rax; void *
0x18003e6be  call    memset_0
0x18003e6c3  mov     r8, [rsp+78h+arg_40]
0x18003e6cb  lea     r14d, [rbp+1]
0x18003e6cf  or      r10d, 0FFFFFFFFh
0x18003e6d3  mov     dword ptr [rdi], 6870676Ch
0x18003e6d9  mov     [rdi+1150h], r10d
0x18003e6e0  mov     ecx, ebp
0x18003e6e2  mov     edx, [r8+4]
0x18003e6e6  lea     r9, qword_1800925A0
0x18003e6ed  mov     rax, rcx
0x18003e6f0  add     rax, rax
0x18003e6f3  mov     r9d, [r9+rax*8]
0x18003e6f7  mov     rax, [r8+8]
0x18003e6fb  test    edx, edx
0x18003e6fd  js      short loc_18003E716
0x18003e6ff  cmp     r9d, [rax]
0x18003e702  jz      short loc_18003E70D
0x18003e704  sub     edx, r14d
0x18003e707  add     rax, 10h
0x18003e70b  jmp     short loc_18003E6FB
0x18003e70d  mov     rax, [rax+8]
0x18003e711  mov     [rdi+rcx*8+8], rax
0x18003e716  inc     rcx
0x18003e719  cmp     rcx, 17h
0x18003e71d  jnz     short loc_18003E6E2
0x18003e71f  or      ebx, 0FFFFFFFFh
0x18003e722  mov     [rdi+0C0h], ebp
0x18003e728  mov     edx, ebx; Val
0x18003e72a  mov     dword ptr [rdi+10E8h], 0FFh
0x18003e734  lea     rcx, [rdi+8DCh]; void *
0x18003e73b  mov     [rdi+10FCh], ebx
0x18003e741  mov     r8d, 400h; Size
0x18003e747  mov     [rdi+10ECh], r10d
0x18003e74e  call    memset_0
0x18003e753  mov     [rdi+10F0h], ebx
0x18003e759  mov     r15d, 4
0x18003e75f  mov     rbx, [rsp+78h+arg_38]
0x18003e767  xor     r9d, r9d; flRed
0x18003e76a  mov     [rdi+110Ch], r14d
0x18003e771  xor     r8d, r8d; pulColors
0x18003e774  mov     [rdi+1110h], r14d
0x18003e77b  xor     edx, edx; cColors
0x18003e77d  mov     [rdi+1114h], r14d
0x18003e784  mov     ecx, r15d; iMode
0x18003e787  mov     dword ptr [rdi+1100h], 7
0x18003e791  mov     [rdi+1104h], r15d
0x18003e798  mov     dword ptr [rbx], 0E00001FFh
0x18003e79e  mov     qword ptr [rbx+11Ch], 5
0x18003e7a9  mov     [rsp+78h+flBlue], ebp; flBlue
0x18003e7ad  mov     [rdi+1128h], ebp
0x18003e7b3  mov     [rdi+1130h], r14d
0x18003e7ba  mov     [rsp+78h+flGreen], ebp; flGreen
0x18003e7be  call    cs:__imp_EngCreatePalette
0x18003e7c5  nop     dword ptr [rax+rax+00h]
0x18003e7ca  mov     [rbx+128h], rax
0x18003e7d1  lea     edx, [r15-2]
0x18003e7d5  mov     [rdi+1120h], rax
0x18003e7dc  lea     r8d, [r15-1]
0x18003e7e0  mov     [rdi+1108h], r15d
0x18003e7e7  mov     rax, [rsi+0F18h]
0x18003e7ee  test    rax, rax
0x18003e7f1  jz      short loc_18003E82E
0x18003e7f3  cmp     dword ptr [rax], 960h
0x18003e7f9  jnz     short loc_18003E804
0x18003e7fb  mov     [rdi+112Ch], r15d
0x18003e802  jmp     short loc_18003E834
0x18003e804  cmp     dword ptr [rax], 4B0h
0x18003e80a  jnz     short loc_18003E815
0x18003e80c  mov     [rdi+112Ch], r8d
0x18003e813  jmp     short loc_18003E834
0x18003e815  cmp     dword ptr [rax], 258h
0x18003e81b  jz      short loc_18003E82E
0x18003e81d  cmp     dword ptr [rax], 12Ch
0x18003e823  jnz     short loc_18003E82E
0x18003e825  mov     [rdi+112Ch], r14d
0x18003e82c  jmp     short loc_18003E834
0x18003e82e  mov     [rdi+112Ch], edx
0x18003e834  mov     rcx, [rsi+0F28h]
0x18003e83b  test    rcx, rcx
0x18003e83e  jz      short loc_18003E848
0x18003e840  mov     eax, r14d
0x18003e843  cmp     [rcx], r14d
0x18003e846  jz      short loc_18003E84A
0x18003e848  mov     eax, ebp
0x18003e84a  mov     [rdi+1170h], eax
0x18003e850  test    eax, eax
0x18003e852  jnz     short loc_18003E862
0x18003e854  mov     rax, [rsp+78h+arg_28]
0x18003e85c  mov     [rax+0F0h], ebp
0x18003e862  mov     [rdi+1178h], r14d
0x18003e869  mov     rcx, [rsi+0F90h]
0x18003e870  test    rcx, rcx
0x18003e873  jz      short loc_18003E8A9
0x18003e875  mov     ecx, [rcx+18h]
0x18003e878  sub     ecx, r14d
0x18003e87b  jz      short loc_18003E8A3
0x18003e87d  sub     ecx, r14d
0x18003e880  jz      short loc_18003E8A3
0x18003e882  sub     ecx, r14d
0x18003e885  jz      short loc_18003E89A
0x18003e887  sub     ecx, r14d
0x18003e88a  jz      short loc_18003E89A
0x18003e88c  cmp     ecx, r14d
0x18003e88f  jnz     short loc_18003E8A9
0x18003e891  mov     [rdi+1178h], r15d
0x18003e898  jmp     short loc_18003E8A9
0x18003e89a  mov     [rdi+1178h], r8d
0x18003e8a1  jmp     short loc_18003E8A9
0x18003e8a3  mov     [rdi+1178h], edx
0x18003e8a9  mov     ebx, 18h
0x18003e8ae  mov     ecx, ebx; Size
0x18003e8b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e8b5  test    rax, rax
0x18003e8b8  jz      short loc_18003E8C4
0x18003e8ba  mov     rcx, rax; this
0x18003e8bd  call    ??0BrushCache@@QEAA@XZ; BrushCache::BrushCache(void)
0x18003e8c2  jmp     short loc_18003E8C7
0x18003e8c4  mov     rax, rbp
0x18003e8c7  mov     rcx, rbx; Size
0x18003e8ca  mov     [rdi+1138h], rax
0x18003e8d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e8d6  test    rax, rax
0x18003e8d9  jz      short loc_18003E8E5
0x18003e8db  mov     rcx, rax; this
0x18003e8de  call    ??0BrushCache@@QEAA@XZ; BrushCache::BrushCache(void)
0x18003e8e3  jmp     short loc_18003E8E8
0x18003e8e5  mov     rax, rbp
0x18003e8e8  mov     rcx, [rdi+1138h]; this
0x18003e8ef  mov     [rdi+1140h], rax
0x18003e8f6  test    rcx, rcx
0x18003e8f9  jz      short loc_18003E970
0x18003e8fb  test    rax, rax
0x18003e8fe  jz      short loc_18003E95D
0x18003e900  cmp     [rcx+10h], rbp
0x18003e904  jz      short loc_18003E95D
0x18003e906  cmp     [rax+10h], rbp
0x18003e90a  jz      short loc_18003E95D
0x18003e90c  mov     rcx, [rsi+18h]; hPrinter
0x18003e910  test    rcx, rcx
0x18003e913  jz      short loc_18003E958
0x18003e915  lea     rax, [rsp+78h+pcbNeeded]
0x18003e91a  xor     r8d, r8d; pType
0x18003e91d  mov     qword ptr [rsp+78h+flBlue], rax; pcbNeeded
0x18003e922  lea     r9, [rsp+78h+pData]; pData
0x18003e92a  lea     rdx, aUsenuphalftone; "UseNupHalftoneMatrix"
0x18003e931  mov     [rsp+78h+flGreen], r15d; nSize
0x18003e936  call    cs:__imp_GetPrinterDataW
0x18003e93d  nop     dword ptr [rax+rax+00h]
0x18003e942  test    eax, eax
0x18003e944  jnz     short loc_18003E958
0x18003e946  cmp     [rsp+78h+pData], r14d
0x18003e94e  jnz     short loc_18003E958
0x18003e950  bts     dword ptr [rdi+1148h], 7
0x18003e958  mov     rax, rdi
0x18003e95b  jmp     short loc_18003E9B4
0x18003e95d  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x18003e962  mov     rax, [rdi+1140h]
0x18003e969  mov     [rdi+1138h], rbp
0x18003e970  test    rax, rax
0x18003e973  jz      short loc_18003E984
0x18003e975  mov     rcx, rax; this
0x18003e978  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x18003e97d  mov     [rdi+1140h], rbp
0x18003e984  mov     rcx, [rdi+1120h]; hpal
0x18003e98b  test    rcx, rcx
0x18003e98e  jz      short loc_18003E9A3
0x18003e990  call    cs:__imp_EngDeletePalette
0x18003e997  nop     dword ptr [rax+rax+00h]
0x18003e99c  mov     [rdi+1120h], rbp
0x18003e9a3  mov     rcx, rdi; hMem
0x18003e9a6  call    cs:__imp_LocalFree
0x18003e9ad  nop     dword ptr [rax+rax+00h]
0x18003e9b2  xor     eax, eax
0x18003e9b4  add     rsp, 48h
0x18003e9b8  pop     r15
0x18003e9ba  pop     r14
0x18003e9bc  pop     rdi
0x18003e9bd  pop     rsi
0x18003e9be  pop     rbp
0x18003e9bf  pop     rbx
0x18003e9c0  retn
```

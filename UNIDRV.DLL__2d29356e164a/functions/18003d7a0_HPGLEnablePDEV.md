# HPGLEnablePDEV

- ea: `0x18003d7a0`
- end: `0x18003daf3`
- name: `HPGLEnablePDEV`
- size: `851`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18003d7a0`
- `0x180044fb0`
- `0x1800483a8`
- `0x1800491dc`
- `0x180061c68`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18003da7a`
- `WINSPOOL!GetPrinterDataW` at `0x18003da7a`
- `KERNEL32!LocalFree` at `0x18003dade`
- `KERNEL32!LocalFree` at `0x18003dade`
- `KERNEL32!LocalAlloc` at `0x18003d7ee`
- `KERNEL32!LocalAlloc` at `0x18003d7ee`
- `GDI32!EngCreatePalette` at `0x18003d908`
- `GDI32!EngCreatePalette` at `0x18003d908`
- `GDI32!EngDeletePalette` at `0x18003dace`
- `GDI32!EngDeletePalette` at `0x18003dace`

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
  unsigned int v29; // edx
  BrushCache *v30; // rax
  BrushCache *v31; // rcx
  void *v32; // rcx
  HPALETTE v34; // rcx
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
      if ( LODWORD(qword_1800905A0[2 * i]) == *(_DWORD *)v15 )
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
    v30 = BrushCache::BrushCache(v28);
  else
    v30 = 0;
  v31 = (BrushCache *)*((_QWORD *)v11 + 551);
  *((_QWORD *)v11 + 552) = v30;
  if ( !v31 )
    goto LABEL_50;
  if ( !v30 || !*((_QWORD *)v31 + 2) || !*((_QWORD *)v30 + 2) )
  {
    BrushCache::`scalar deleting destructor'(v31, v29);
    v30 = (BrushCache *)*((_QWORD *)v11 + 552);
    *((_QWORD *)v11 + 551) = 0;
LABEL_50:
    if ( v30 )
    {
      BrushCache::`scalar deleting destructor'(v30, v29);
      *((_QWORD *)v11 + 552) = 0;
    }
    v34 = (HPALETTE)*((_QWORD *)v11 + 548);
    if ( v34 )
    {
      EngDeletePalette(v34);
      *((_QWORD *)v11 + 548) = 0;
    }
    LocalFree(v11);
    return 0;
  }
  v32 = (void *)a1[3];
  if ( v32 && !GetPrinterDataW(v32, (LPWSTR)L"UseNupHalftoneMatrix", 0, (LPBYTE)&pData, 4u, pcbNeeded) && pData == 1 )
    v11[1106] |= 0x80u;
  return v11;
}

```

## disassembly

```asm
0x18003d7a0  mov     rax, rsp
0x18003d7a3  push    rbx
0x18003d7a4  push    rbp
0x18003d7a5  push    rsi
0x18003d7a6  push    rdi
0x18003d7a7  push    r14
0x18003d7a9  push    r15
0x18003d7ab  sub     rsp, 48h
0x18003d7af  xor     ebp, ebp
0x18003d7b1  mov     rsi, rcx
0x18003d7b4  mov     [rax+8], ebp
0x18003d7b7  mov     [rax-48h], ebp
0x18003d7ba  test    rcx, rcx
0x18003d7bd  jz      loc_18003DAE4
0x18003d7c3  cmp     [rsp+78h+arg_20], 140h
0x18003d7ce  jb      loc_18003DAE4
0x18003d7d4  cmp     [rsp+78h+arg_30], 138h
0x18003d7df  jb      loc_18003DAE4
0x18003d7e5  mov     ebx, 1188h
0x18003d7ea  xor     ecx, ecx; uFlags
0x18003d7ec  mov     edx, ebx; uBytes
0x18003d7ee  call    cs:__imp_LocalAlloc
0x18003d7f4  mov     rdi, rax
0x18003d7f7  test    rax, rax
0x18003d7fa  jz      loc_18003DAE4
0x18003d800  mov     r8d, ebx; Size
0x18003d803  xor     edx, edx; Val
0x18003d805  mov     rcx, rax; void *
0x18003d808  call    memset_0
0x18003d80d  mov     r8, [rsp+78h+arg_40]
0x18003d815  lea     r14d, [rbp+1]
0x18003d819  or      r10d, 0FFFFFFFFh
0x18003d81d  mov     dword ptr [rdi], 6870676Ch
0x18003d823  mov     [rdi+1150h], r10d
0x18003d82a  mov     ecx, ebp
0x18003d82c  mov     edx, [r8+4]
0x18003d830  lea     r9, qword_1800905A0
0x18003d837  mov     rax, rcx
0x18003d83a  add     rax, rax
0x18003d83d  mov     r9d, [r9+rax*8]
0x18003d841  mov     rax, [r8+8]
0x18003d845  test    edx, edx
0x18003d847  js      short loc_18003D860
0x18003d849  cmp     r9d, [rax]
0x18003d84c  jz      short loc_18003D857
0x18003d84e  sub     edx, r14d
0x18003d851  add     rax, 10h
0x18003d855  jmp     short loc_18003D845
0x18003d857  mov     rax, [rax+8]
0x18003d85b  mov     [rdi+rcx*8+8], rax
0x18003d860  inc     rcx
0x18003d863  cmp     rcx, 17h
0x18003d867  jnz     short loc_18003D82C
0x18003d869  or      ebx, 0FFFFFFFFh
0x18003d86c  mov     [rdi+0C0h], ebp
0x18003d872  mov     edx, ebx; Val
0x18003d874  mov     dword ptr [rdi+10E8h], 0FFh
0x18003d87e  lea     rcx, [rdi+8DCh]; void *
0x18003d885  mov     [rdi+10FCh], ebx
0x18003d88b  mov     r8d, 400h; Size
0x18003d891  mov     [rdi+10ECh], r10d
0x18003d898  call    memset_0
0x18003d89d  mov     [rdi+10F0h], ebx
0x18003d8a3  mov     r15d, 4
0x18003d8a9  mov     rbx, [rsp+78h+arg_38]
0x18003d8b1  xor     r9d, r9d; flRed
0x18003d8b4  mov     [rdi+110Ch], r14d
0x18003d8bb  xor     r8d, r8d; pulColors
0x18003d8be  mov     [rdi+1110h], r14d
0x18003d8c5  xor     edx, edx; cColors
0x18003d8c7  mov     [rdi+1114h], r14d
0x18003d8ce  mov     ecx, r15d; iMode
0x18003d8d1  mov     dword ptr [rdi+1100h], 7
0x18003d8db  mov     [rdi+1104h], r15d
0x18003d8e2  mov     dword ptr [rbx], 0E00001FFh
0x18003d8e8  mov     qword ptr [rbx+11Ch], 5
0x18003d8f3  mov     [rsp+78h+flBlue], ebp; flBlue
0x18003d8f7  mov     [rdi+1128h], ebp
0x18003d8fd  mov     [rdi+1130h], r14d
0x18003d904  mov     [rsp+78h+flGreen], ebp; flGreen
0x18003d908  call    cs:__imp_EngCreatePalette
0x18003d90e  mov     [rbx+128h], rax
0x18003d915  lea     edx, [r15-2]
0x18003d919  mov     [rdi+1120h], rax
0x18003d920  lea     r8d, [r15-1]
0x18003d924  mov     [rdi+1108h], r15d
0x18003d92b  mov     rax, [rsi+0F18h]
0x18003d932  test    rax, rax
0x18003d935  jz      short loc_18003D972
0x18003d937  cmp     dword ptr [rax], 960h
0x18003d93d  jnz     short loc_18003D948
0x18003d93f  mov     [rdi+112Ch], r15d
0x18003d946  jmp     short loc_18003D978
0x18003d948  cmp     dword ptr [rax], 4B0h
0x18003d94e  jnz     short loc_18003D959
0x18003d950  mov     [rdi+112Ch], r8d
0x18003d957  jmp     short loc_18003D978
0x18003d959  cmp     dword ptr [rax], 258h
0x18003d95f  jz      short loc_18003D972
0x18003d961  cmp     dword ptr [rax], 12Ch
0x18003d967  jnz     short loc_18003D972
0x18003d969  mov     [rdi+112Ch], r14d
0x18003d970  jmp     short loc_18003D978
0x18003d972  mov     [rdi+112Ch], edx
0x18003d978  mov     rcx, [rsi+0F28h]
0x18003d97f  test    rcx, rcx
0x18003d982  jz      short loc_18003D98C
0x18003d984  mov     eax, r14d
0x18003d987  cmp     [rcx], r14d
0x18003d98a  jz      short loc_18003D98E
0x18003d98c  mov     eax, ebp
0x18003d98e  mov     [rdi+1170h], eax
0x18003d994  test    eax, eax
0x18003d996  jnz     short loc_18003D9A6
0x18003d998  mov     rax, [rsp+78h+arg_28]
0x18003d9a0  mov     [rax+0F0h], ebp
0x18003d9a6  mov     [rdi+1178h], r14d
0x18003d9ad  mov     rcx, [rsi+0F90h]
0x18003d9b4  test    rcx, rcx
0x18003d9b7  jz      short loc_18003D9ED
0x18003d9b9  mov     ecx, [rcx+18h]
0x18003d9bc  sub     ecx, r14d
0x18003d9bf  jz      short loc_18003D9E7
0x18003d9c1  sub     ecx, r14d
0x18003d9c4  jz      short loc_18003D9E7
0x18003d9c6  sub     ecx, r14d
0x18003d9c9  jz      short loc_18003D9DE
0x18003d9cb  sub     ecx, r14d
0x18003d9ce  jz      short loc_18003D9DE
0x18003d9d0  cmp     ecx, r14d
0x18003d9d3  jnz     short loc_18003D9ED
0x18003d9d5  mov     [rdi+1178h], r15d
0x18003d9dc  jmp     short loc_18003D9ED
0x18003d9de  mov     [rdi+1178h], r8d
0x18003d9e5  jmp     short loc_18003D9ED
0x18003d9e7  mov     [rdi+1178h], edx
0x18003d9ed  mov     ebx, 18h
0x18003d9f2  mov     ecx, ebx; Size
0x18003d9f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d9f9  test    rax, rax
0x18003d9fc  jz      short loc_18003DA08
0x18003d9fe  mov     rcx, rax; this
0x18003da01  call    ??0BrushCache@@QEAA@XZ; BrushCache::BrushCache(void)
0x18003da06  jmp     short loc_18003DA0B
0x18003da08  mov     rax, rbp
0x18003da0b  mov     rcx, rbx; Size
0x18003da0e  mov     [rdi+1138h], rax
0x18003da15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003da1a  test    rax, rax
0x18003da1d  jz      short loc_18003DA29
0x18003da1f  mov     rcx, rax; this
0x18003da22  call    ??0BrushCache@@QEAA@XZ; BrushCache::BrushCache(void)
0x18003da27  jmp     short loc_18003DA2C
0x18003da29  mov     rax, rbp
0x18003da2c  mov     rcx, [rdi+1138h]; this
0x18003da33  mov     [rdi+1140h], rax
0x18003da3a  test    rcx, rcx
0x18003da3d  jz      short loc_18003DAAE
0x18003da3f  test    rax, rax
0x18003da42  jz      short loc_18003DA9B
0x18003da44  cmp     [rcx+10h], rbp
0x18003da48  jz      short loc_18003DA9B
0x18003da4a  cmp     [rax+10h], rbp
0x18003da4e  jz      short loc_18003DA9B
0x18003da50  mov     rcx, [rsi+18h]; hPrinter
0x18003da54  test    rcx, rcx
0x18003da57  jz      short loc_18003DA96
0x18003da59  lea     rax, [rsp+78h+pcbNeeded]
0x18003da5e  xor     r8d, r8d; pType
0x18003da61  mov     qword ptr [rsp+78h+flBlue], rax; pcbNeeded
0x18003da66  lea     r9, [rsp+78h+pData]; pData
0x18003da6e  lea     rdx, aUsenuphalftone; "UseNupHalftoneMatrix"
0x18003da75  mov     [rsp+78h+flGreen], r15d; nSize
0x18003da7a  call    cs:__imp_GetPrinterDataW
0x18003da80  test    eax, eax
0x18003da82  jnz     short loc_18003DA96
0x18003da84  cmp     [rsp+78h+pData], r14d
0x18003da8c  jnz     short loc_18003DA96
0x18003da8e  bts     dword ptr [rdi+1148h], 7
0x18003da96  mov     rax, rdi
0x18003da99  jmp     short loc_18003DAE6
0x18003da9b  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x18003daa0  mov     rax, [rdi+1140h]
0x18003daa7  mov     [rdi+1138h], rbp
0x18003daae  test    rax, rax
0x18003dab1  jz      short loc_18003DAC2
0x18003dab3  mov     rcx, rax; this
0x18003dab6  call    ??_GBrushCache@@QEAAPEAXI@Z; BrushCache::`scalar deleting destructor'(uint)
0x18003dabb  mov     [rdi+1140h], rbp
0x18003dac2  mov     rcx, [rdi+1120h]; hpal
0x18003dac9  test    rcx, rcx
0x18003dacc  jz      short loc_18003DADB
0x18003dace  call    cs:__imp_EngDeletePalette
0x18003dad4  mov     [rdi+1120h], rbp
0x18003dadb  mov     rcx, rdi; hMem
0x18003dade  call    cs:__imp_LocalFree
0x18003dae4  xor     eax, eax
0x18003dae6  add     rsp, 48h
0x18003daea  pop     r15
0x18003daec  pop     r14
0x18003daee  pop     rdi
0x18003daef  pop     rsi
0x18003daf0  pop     rbp
0x18003daf1  pop     rbx
0x18003daf2  retn
```

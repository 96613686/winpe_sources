# CreateIndexedImageFromDirect(_RASTER_DATA *,_PALETTE *)

- ea: `0x18006c47c`
- end: `0x18006c62c`
- name: `?CreateIndexedImageFromDirect@@YAPEAU_RASTER_DATA@@PEAU1@PEAU_PALETTE@@@Z`
- size: `432`
- prototype: `struct _RASTER_DATA *__fastcall(struct _RASTER_DATA *, struct _PALETTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180065a34`

## callees

- `0x18006c47c`
- `0x18006cadc`
- `0x18006cda8`
- `0x18006cec0`
- `0x18006cf14`
- `0x18006cf48`
- `0x18006cf7c`
- `0x18006cfb0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18006c4f1`
- `KERNEL32!LocalAlloc` at `0x18006c4f1`

## pseudocode

```c
struct _RASTER_DATA *__fastcall CreateIndexedImageFromDirect(struct _RASTER_DATA *a1, struct _PALETTE *a2)
{
  int v4; // ebx
  char *v5; // rax
  char *v6; // rsi
  char *v7; // rax
  __int64 v8; // rax
  int v9; // r9d
  int i; // edi
  int j; // ebx
  int PaletteEntry; // eax
  _OWORD v14[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h]
  _OWORD v16[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+68h] [rbp-8h]
  __int64 v18; // [rsp+90h] [rbp+20h] BYREF

  v15 = 0;
  v17 = 0;
  v18 = 0;
  memset(v14, 0, sizeof(v14));
  memset(v16, 0, sizeof(v16));
  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  v4 = HIDWORD(*(_QWORD *)((char *)a1 + 20)) * (((*(_QWORD *)((_BYTE *)a1 + 20) & 0x1FFFFFFF) + 3) & 0xFFFFFFFC);
  v5 = (char *)LocalAlloc(0, v4 + 48LL);
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = v5 + 48;
  *((_DWORD *)v6 + 4) = v4;
  *(_QWORD *)v6 = v7;
  *((_QWORD *)v6 + 1) = v7;
  v8 = *(_QWORD *)((char *)a1 + 20);
  *(_QWORD *)(v6 + 20) = v8;
  *((_DWORD *)v6 + 8) = 8;
  *((_DWORD *)v6 + 9) = 1;
  *((_DWORD *)v6 + 7) = ((v8 & 0x1FFFFFFF) + 3) & 0xFFFFFFFC;
  *((_DWORD *)v6 + 10) = *((_DWORD *)a1 + 10);
  RI_Init((struct _RASTER_ITERATOR *)v14, a1, 0, 0);
  RI_Init((struct _RASTER_ITERATOR *)v16, (struct _RASTER_DATA *)v6, 0, v9);
  for ( i = 0; i < (int)RI_NumRows((struct _RASTER_ITERATOR *)v14); ++i )
  {
    RI_SelectRow((struct _RASTER_ITERATOR *)v14, i);
    RI_SelectRow((struct _RASTER_ITERATOR *)v16, i);
    for ( j = 0; j < (int)RI_NumCols((struct _RASTER_ITERATOR *)v14); ++j )
    {
      RI_GetPixel((struct _RASTER_ITERATOR *)v14, j, (struct _PIXEL *)&v18);
      if ( (_DWORD)v18 == 32 )
        HIDWORD(v18) &= 0xFFFFFFu;
      PaletteEntry = FindPaletteEntry(a2, (struct _PIXEL *)&v18);
      if ( PaletteEntry < 0 || (HIDWORD(v18) = PaletteEntry, (unsigned int)PaletteEntry > 0xFF) )
        HIDWORD(v18) = 0;
      LODWORD(v18) = 8;
      RI_SetPixel((struct _RASTER_ITERATOR *)v16, j, (struct _PIXEL *)&v18);
    }
  }
  return (struct _RASTER_DATA *)v6;
}

```

## disassembly

```asm
0x18006c47c  mov     [rsp-18h+arg_8], rbx
0x18006c481  mov     [rsp-18h+arg_10], rsi
0x18006c486  push    rbp
0x18006c487  push    rdi
0x18006c488  push    r14
0x18006c48a  mov     rbp, rsp
0x18006c48d  sub     rsp, 70h
0x18006c491  xor     eax, eax
0x18006c493  xorps   xmm0, xmm0
0x18006c496  mov     [rbp+var_30], rax
0x18006c49a  xorps   xmm1, xmm1
0x18006c49d  mov     [rbp+var_8], rax
0x18006c4a1  mov     r14, rdx
0x18006c4a4  mov     [rbp+arg_0], rax
0x18006c4a8  mov     rdi, rcx
0x18006c4ab  movups  [rbp+var_50], xmm0
0x18006c4af  movups  [rbp+var_40], xmm0
0x18006c4b3  movups  [rbp+var_28], xmm1
0x18006c4b7  movups  [rbp+var_18], xmm1
0x18006c4bb  test    rcx, rcx
0x18006c4be  jz      loc_18006C614
0x18006c4c4  test    rdx, rdx
0x18006c4c7  jz      loc_18006C614
0x18006c4cd  mov     rax, [rcx+14h]
0x18006c4d1  xor     ecx, ecx; uFlags
0x18006c4d3  lea     ebx, ds:0[rax*8]
0x18006c4da  shr     rax, 20h
0x18006c4de  shr     ebx, 3
0x18006c4e1  add     ebx, 3
0x18006c4e4  and     ebx, 0FFFFFFFCh
0x18006c4e7  imul    ebx, eax
0x18006c4ea  movsxd  rdx, ebx
0x18006c4ed  add     rdx, 30h ; '0'; uBytes
0x18006c4f1  call    cs:__imp_LocalAlloc
0x18006c4f8  nop     dword ptr [rax+rax+00h]
0x18006c4fd  mov     rsi, rax
0x18006c500  test    rax, rax
0x18006c503  jz      loc_18006C614
0x18006c509  add     rax, 30h ; '0'
0x18006c50d  mov     [rsi+10h], ebx
0x18006c510  mov     [rsi], rax
0x18006c513  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c517  mov     [rsi+8], rax
0x18006c51b  xor     r9d, r9d; unsigned int
0x18006c51e  mov     rax, [rdi+14h]
0x18006c522  xor     r8d, r8d; struct _RECTL *
0x18006c525  mov     [rsi+14h], rax
0x18006c529  mov     rdx, rdi; struct _RASTER_DATA *
0x18006c52c  and     eax, 1FFFFFFFh
0x18006c531  mov     dword ptr [rsi+20h], 8
0x18006c538  add     eax, 3
0x18006c53b  mov     dword ptr [rsi+24h], 1
0x18006c542  and     eax, 0FFFFFFFCh
0x18006c545  mov     [rsi+1Ch], eax
0x18006c548  mov     eax, [rdi+28h]
0x18006c54b  mov     [rsi+28h], eax
0x18006c54e  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x18006c553  xor     r8d, r8d; struct _RECTL *
0x18006c556  lea     rcx, [rbp+var_28]; struct _RASTER_ITERATOR *
0x18006c55a  mov     rdx, rsi; struct _RASTER_DATA *
0x18006c55d  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x18006c562  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c566  xor     edi, edi
0x18006c568  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x18006c56d  test    eax, eax
0x18006c56f  jle     loc_18006C60F
0x18006c575  mov     edx, edi; int
0x18006c577  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c57b  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x18006c580  mov     edx, edi; int
0x18006c582  lea     rcx, [rbp+var_28]; struct _RASTER_ITERATOR *
0x18006c586  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x18006c58b  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c58f  xor     ebx, ebx
0x18006c591  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x18006c596  test    eax, eax
0x18006c598  jle     short loc_18006C5FC
0x18006c59a  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006c59e  mov     edx, ebx; int
0x18006c5a0  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c5a4  call    ?RI_GetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_GetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x18006c5a9  cmp     dword ptr [rbp+arg_0], 20h ; ' '
0x18006c5ad  jnz     short loc_18006C5B6
0x18006c5af  and     dword ptr [rbp+arg_0+4], 0FFFFFFh
0x18006c5b6  lea     rdx, [rbp+arg_0]; struct _PIXEL *
0x18006c5ba  mov     rcx, r14; struct _PALETTE *
0x18006c5bd  call    ?FindPaletteEntry@@YAJPEAU_PALETTE@@PEAU_PIXEL@@@Z; FindPaletteEntry(_PALETTE *,_PIXEL *)
0x18006c5c2  test    eax, eax
0x18006c5c4  js      short loc_18006C5D0
0x18006c5c6  mov     dword ptr [rbp+arg_0+4], eax
0x18006c5c9  cmp     eax, 0FFh
0x18006c5ce  jbe     short loc_18006C5D7
0x18006c5d0  mov     dword ptr [rbp+arg_0+4], 0
0x18006c5d7  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006c5db  mov     dword ptr [rbp+arg_0], 8
0x18006c5e2  mov     edx, ebx; int
0x18006c5e4  lea     rcx, [rbp+var_28]; struct _RASTER_ITERATOR *
0x18006c5e8  call    ?RI_SetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_SetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x18006c5ed  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c5f1  inc     ebx
0x18006c5f3  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x18006c5f8  cmp     ebx, eax
0x18006c5fa  jl      short loc_18006C59A
0x18006c5fc  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006c600  inc     edi
0x18006c602  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x18006c607  cmp     edi, eax
0x18006c609  jl      loc_18006C575
0x18006c60f  mov     rax, rsi
0x18006c612  jmp     short loc_18006C616
0x18006c614  xor     eax, eax
0x18006c616  lea     r11, [rsp+70h+var_s0]
0x18006c61b  mov     rbx, [r11+28h]
0x18006c61f  mov     rsi, [r11+30h]
0x18006c623  mov     rsp, r11
0x18006c626  pop     r14
0x18006c628  pop     rdi
0x18006c629  pop     rbp
0x18006c62a  retn
```

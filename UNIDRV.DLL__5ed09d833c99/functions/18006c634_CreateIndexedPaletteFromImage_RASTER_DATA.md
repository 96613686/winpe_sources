# CreateIndexedPaletteFromImage(_RASTER_DATA *)

- ea: `0x18006c634`
- end: `0x18006c75d`
- name: `?CreateIndexedPaletteFromImage@@YAPEAU_PALETTE@@PEAU_RASTER_DATA@@@Z`
- size: `297`
- prototype: `struct _PALETTE *__fastcall(struct _RASTER_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180065a34`

## callees

- `0x18006c634`
- `0x18006cadc`
- `0x18006cda8`
- `0x18006cec0`
- `0x18006cf14`
- `0x18006cf48`
- `0x18006cf7c`
- `0x18006d164`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006c740`
- `KERNEL32!LocalFree` at `0x18006c740`
- `KERNEL32!LocalAlloc` at `0x18006c68b`
- `KERNEL32!LocalAlloc` at `0x18006c68b`

## pseudocode

```c
struct _PALETTE *__fastcall CreateIndexedPaletteFromImage(struct _RASTER_DATA *a1)
{
  int v2; // ecx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  int v5; // esi
  int i; // edi
  unsigned int v7; // edx
  _OWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+80h] [rbp+28h] BYREF

  v10 = 0;
  v11 = 0;
  memset(v9, 0, sizeof(v9));
  if ( !a1 )
    return 0;
  if ( *((_DWORD *)a1 + 9) )
    return 0;
  v2 = *((_DWORD *)a1 + 8);
  if ( ((v2 - 16) & 0xFFFFFFE7) != 0 )
    return 0;
  if ( v2 == 40 )
    return 0;
  v3 = LocalAlloc(0, 0x310u);
  v4 = v3;
  if ( !v3 )
    return 0;
  *v3 = 24;
  v3[1] = v3 + 2;
  RI_Init((struct _RASTER_ITERATOR *)v9, a1, 0, 0);
  v5 = 0;
LABEL_7:
  if ( v5 < (int)RI_NumRows((struct _RASTER_ITERATOR *)v9) )
  {
    RI_SelectRow((struct _RASTER_ITERATOR *)v9, v5);
    for ( i = 0; ; ++i )
    {
      if ( i >= (int)RI_NumCols((struct _RASTER_ITERATOR *)v9) )
      {
        ++v5;
        goto LABEL_7;
      }
      RI_GetPixel((struct _RASTER_ITERATOR *)v9, i, (struct _PIXEL *)&v11);
      if ( (unsigned int)FindPaletteEntry((struct _PALETTE *)v4, (struct _PIXEL *)&v11) == -1 )
      {
        v7 = *((_DWORD *)v4 + 1);
        if ( v7 >= 0x100 )
          goto LABEL_16;
        *((_DWORD *)v4 + 1) = v7 + 1;
        if ( !(unsigned int)SetPaletteEntry((struct _PALETTE *)v4, v7, (struct _PIXEL *)&v11) )
          break;
      }
    }
    --*((_DWORD *)v4 + 1);
LABEL_16:
    LocalFree(v4);
    return 0;
  }
  return (struct _PALETTE *)v4;
}

```

## disassembly

```asm
0x18006c634  push    rbp
0x18006c636  push    rbx
0x18006c637  push    rsi
0x18006c638  push    rdi
0x18006c639  mov     rbp, rsp
0x18006c63c  sub     rsp, 58h
0x18006c640  xor     eax, eax
0x18006c642  xorps   xmm0, xmm0
0x18006c645  mov     [rbp+var_18], rax
0x18006c649  mov     rdi, rcx
0x18006c64c  mov     [rbp+arg_0], rax
0x18006c650  movups  [rbp+var_38], xmm0
0x18006c654  movups  [rbp+var_28], xmm0
0x18006c658  test    rcx, rcx
0x18006c65b  jz      loc_18006C74C
0x18006c661  cmp     [rcx+24h], eax
0x18006c664  jnz     loc_18006C74C
0x18006c66a  mov     ecx, [rcx+20h]
0x18006c66d  lea     eax, [rcx-10h]
0x18006c670  test    eax, 0FFFFFFE7h
0x18006c675  jnz     loc_18006C74C
0x18006c67b  cmp     ecx, 28h ; '('
0x18006c67e  jz      loc_18006C74C
0x18006c684  mov     edx, 310h; uBytes
0x18006c689  xor     ecx, ecx; uFlags
0x18006c68b  call    cs:__imp_LocalAlloc
0x18006c692  nop     dword ptr [rax+rax+00h]
0x18006c697  mov     rbx, rax
0x18006c69a  test    rax, rax
0x18006c69d  jz      loc_18006C74C
0x18006c6a3  mov     qword ptr [rax], 18h
0x18006c6aa  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006c6ae  add     rax, 10h
0x18006c6b2  xor     r9d, r9d; unsigned int
0x18006c6b5  xor     r8d, r8d; struct _RECTL *
0x18006c6b8  mov     [rbx+8], rax
0x18006c6bc  mov     rdx, rdi; struct _RASTER_DATA *
0x18006c6bf  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x18006c6c4  xor     esi, esi
0x18006c6c6  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006c6ca  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x18006c6cf  cmp     esi, eax
0x18006c6d1  jge     loc_18006C758
0x18006c6d7  mov     edx, esi; int
0x18006c6d9  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006c6dd  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x18006c6e2  xor     edi, edi
0x18006c6e4  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006c6e8  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x18006c6ed  cmp     edi, eax
0x18006c6ef  jge     short loc_18006C736
0x18006c6f1  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006c6f5  mov     edx, edi; int
0x18006c6f7  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006c6fb  call    ?RI_GetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_GetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x18006c700  lea     rdx, [rbp+arg_0]; struct _PIXEL *
0x18006c704  mov     rcx, rbx; struct _PALETTE *
0x18006c707  call    ?FindPaletteEntry@@YAJPEAU_PALETTE@@PEAU_PIXEL@@@Z; FindPaletteEntry(_PALETTE *,_PIXEL *)
0x18006c70c  cmp     eax, 0FFFFFFFFh
0x18006c70f  jnz     short loc_18006C732
0x18006c711  mov     edx, [rbx+4]; unsigned int
0x18006c714  cmp     edx, 100h
0x18006c71a  jnb     short loc_18006C73D
0x18006c71c  lea     eax, [rdx+1]
0x18006c71f  mov     rcx, rbx; struct _PALETTE *
0x18006c722  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006c726  mov     [rbx+4], eax
0x18006c729  call    ?SetPaletteEntry@@YAHPEAU_PALETTE@@KPEAU_PIXEL@@@Z; SetPaletteEntry(_PALETTE *,ulong,_PIXEL *)
0x18006c72e  test    eax, eax
0x18006c730  jz      short loc_18006C73A
0x18006c732  inc     edi
0x18006c734  jmp     short loc_18006C6E4
0x18006c736  inc     esi
0x18006c738  jmp     short loc_18006C6C6
0x18006c73a  dec     dword ptr [rbx+4]
0x18006c73d  mov     rcx, rbx; hMem
0x18006c740  call    cs:__imp_LocalFree
0x18006c747  nop     dword ptr [rax+rax+00h]
0x18006c74c  xor     eax, eax
0x18006c74e  add     rsp, 58h
0x18006c752  pop     rdi
0x18006c753  pop     rsi
0x18006c754  pop     rbx
0x18006c755  pop     rbp
0x18006c756  retn
0x18006c758  mov     rax, rbx
0x18006c75b  jmp     short loc_18006C74E
```

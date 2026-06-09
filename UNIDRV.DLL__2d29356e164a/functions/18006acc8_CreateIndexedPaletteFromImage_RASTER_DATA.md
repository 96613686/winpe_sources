# CreateIndexedPaletteFromImage(_RASTER_DATA *)

- ea: `0x18006acc8`
- end: `0x18006ade0`
- name: `?CreateIndexedPaletteFromImage@@YAPEAU_PALETTE@@PEAU_RASTER_DATA@@@Z`
- size: `280`
- prototype: `struct _PALETTE *__fastcall(struct _RASTER_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180064378`

## callees

- `0x18006acc8`
- `0x18006b150`
- `0x18006b418`
- `0x18006b52c`
- `0x18006b57c`
- `0x18006b5b0`
- `0x18006b5e4`
- `0x18006b7c8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006adca`
- `KERNEL32!LocalFree` at `0x18006adca`
- `KERNEL32!LocalAlloc` at `0x18006ad1f`
- `KERNEL32!LocalAlloc` at `0x18006ad1f`

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
0x18006acc8  push    rbp
0x18006acca  push    rbx
0x18006accb  push    rsi
0x18006accc  push    rdi
0x18006accd  mov     rbp, rsp
0x18006acd0  sub     rsp, 58h
0x18006acd4  xor     eax, eax
0x18006acd6  xorps   xmm0, xmm0
0x18006acd9  mov     [rbp+var_18], rax
0x18006acdd  mov     rdi, rcx
0x18006ace0  mov     [rbp+arg_0], rax
0x18006ace4  movups  [rbp+var_38], xmm0
0x18006ace8  movups  [rbp+var_28], xmm0
0x18006acec  test    rcx, rcx
0x18006acef  jz      loc_18006ADD0
0x18006acf5  cmp     [rcx+24h], eax
0x18006acf8  jnz     loc_18006ADD0
0x18006acfe  mov     ecx, [rcx+20h]
0x18006ad01  lea     eax, [rcx-10h]
0x18006ad04  test    eax, 0FFFFFFE7h
0x18006ad09  jnz     loc_18006ADD0
0x18006ad0f  cmp     ecx, 28h ; '('
0x18006ad12  jz      loc_18006ADD0
0x18006ad18  mov     edx, 310h; uBytes
0x18006ad1d  xor     ecx, ecx; uFlags
0x18006ad1f  call    cs:__imp_LocalAlloc
0x18006ad25  mov     rbx, rax
0x18006ad28  test    rax, rax
0x18006ad2b  jz      loc_18006ADD0
0x18006ad31  mov     qword ptr [rax], 18h
0x18006ad38  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006ad3c  add     rax, 10h
0x18006ad40  xor     r9d, r9d; unsigned int
0x18006ad43  xor     r8d, r8d; struct _RECTL *
0x18006ad46  mov     [rbx+8], rax
0x18006ad4a  mov     rdx, rdi; struct _RASTER_DATA *
0x18006ad4d  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x18006ad52  xor     esi, esi
0x18006ad54  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006ad58  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x18006ad5d  cmp     esi, eax
0x18006ad5f  jge     short loc_18006ADDB
0x18006ad61  mov     edx, esi; int
0x18006ad63  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006ad67  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x18006ad6c  xor     edi, edi
0x18006ad6e  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006ad72  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x18006ad77  cmp     edi, eax
0x18006ad79  jge     short loc_18006ADC0
0x18006ad7b  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006ad7f  mov     edx, edi; int
0x18006ad81  lea     rcx, [rbp+var_38]; struct _RASTER_ITERATOR *
0x18006ad85  call    ?RI_GetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_GetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x18006ad8a  lea     rdx, [rbp+arg_0]; struct _PIXEL *
0x18006ad8e  mov     rcx, rbx; struct _PALETTE *
0x18006ad91  call    ?FindPaletteEntry@@YAJPEAU_PALETTE@@PEAU_PIXEL@@@Z; FindPaletteEntry(_PALETTE *,_PIXEL *)
0x18006ad96  cmp     eax, 0FFFFFFFFh
0x18006ad99  jnz     short loc_18006ADBC
0x18006ad9b  mov     edx, [rbx+4]; unsigned int
0x18006ad9e  cmp     edx, 100h
0x18006ada4  jnb     short loc_18006ADC7
0x18006ada6  lea     eax, [rdx+1]
0x18006ada9  mov     rcx, rbx; struct _PALETTE *
0x18006adac  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006adb0  mov     [rbx+4], eax
0x18006adb3  call    ?SetPaletteEntry@@YAHPEAU_PALETTE@@KPEAU_PIXEL@@@Z; SetPaletteEntry(_PALETTE *,ulong,_PIXEL *)
0x18006adb8  test    eax, eax
0x18006adba  jz      short loc_18006ADC4
0x18006adbc  inc     edi
0x18006adbe  jmp     short loc_18006AD6E
0x18006adc0  inc     esi
0x18006adc2  jmp     short loc_18006AD54
0x18006adc4  dec     dword ptr [rbx+4]
0x18006adc7  mov     rcx, rbx; hMem
0x18006adca  call    cs:__imp_LocalFree
0x18006add0  xor     eax, eax
0x18006add2  add     rsp, 58h
0x18006add6  pop     rdi
0x18006add7  pop     rsi
0x18006add8  pop     rbx
0x18006add9  pop     rbp
0x18006adda  retn
0x18006addb  mov     rax, rbx
0x18006adde  jmp     short loc_18006ADD2
```

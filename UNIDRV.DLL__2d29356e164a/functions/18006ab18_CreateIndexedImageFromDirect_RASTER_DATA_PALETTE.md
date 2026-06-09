# CreateIndexedImageFromDirect(_RASTER_DATA *,_PALETTE *)

- ea: `0x18006ab18`
- end: `0x18006acc1`
- name: `?CreateIndexedImageFromDirect@@YAPEAU_RASTER_DATA@@PEAU1@PEAU_PALETTE@@@Z`
- size: `425`
- prototype: `struct _RASTER_DATA *__fastcall(struct _RASTER_DATA *, struct _PALETTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180064378`

## callees

- `0x18006ab18`
- `0x18006b150`
- `0x18006b418`
- `0x18006b52c`
- `0x18006b57c`
- `0x18006b5b0`
- `0x18006b5e4`
- `0x18006b618`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18006ab8d`
- `KERNEL32!LocalAlloc` at `0x18006ab8d`

## pseudocode

```c
struct _RASTER_DATA *__fastcall CreateIndexedImageFromDirect(struct _RASTER_DATA *a1, struct _PALETTE *a2)
{
  int v4; // ebx
  char *v5; // rax
  char *v6; // rsi
  char *v7; // rax
  __int64 v8; // rax
  unsigned int v9; // r9d
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
0x18006ab18  mov     [rsp-18h+arg_8], rbx
0x18006ab1d  mov     [rsp-18h+arg_10], rsi
0x18006ab22  push    rbp
0x18006ab23  push    rdi
0x18006ab24  push    r14
0x18006ab26  mov     rbp, rsp
0x18006ab29  sub     rsp, 70h
0x18006ab2d  xor     eax, eax
0x18006ab2f  xorps   xmm0, xmm0
0x18006ab32  mov     [rbp+var_30], rax
0x18006ab36  xorps   xmm1, xmm1
0x18006ab39  mov     [rbp+var_8], rax
0x18006ab3d  mov     r14, rdx
0x18006ab40  mov     [rbp+arg_0], rax
0x18006ab44  mov     rdi, rcx
0x18006ab47  movups  [rbp+var_50], xmm0
0x18006ab4b  movups  [rbp+var_40], xmm0
0x18006ab4f  movups  [rbp+var_28], xmm1
0x18006ab53  movups  [rbp+var_18], xmm1
0x18006ab57  test    rcx, rcx
0x18006ab5a  jz      loc_18006ACAA
0x18006ab60  test    rdx, rdx
0x18006ab63  jz      loc_18006ACAA
0x18006ab69  mov     rax, [rcx+14h]
0x18006ab6d  xor     ecx, ecx; uFlags
0x18006ab6f  lea     ebx, ds:0[rax*8]
0x18006ab76  shr     rax, 20h
0x18006ab7a  shr     ebx, 3
0x18006ab7d  add     ebx, 3
0x18006ab80  and     ebx, 0FFFFFFFCh
0x18006ab83  imul    ebx, eax
0x18006ab86  movsxd  rdx, ebx
0x18006ab89  add     rdx, 30h ; '0'; uBytes
0x18006ab8d  call    cs:__imp_LocalAlloc
0x18006ab93  mov     rsi, rax
0x18006ab96  test    rax, rax
0x18006ab99  jz      loc_18006ACAA
0x18006ab9f  add     rax, 30h ; '0'
0x18006aba3  mov     [rsi+10h], ebx
0x18006aba6  mov     [rsi], rax
0x18006aba9  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006abad  mov     [rsi+8], rax
0x18006abb1  xor     r9d, r9d; unsigned int
0x18006abb4  mov     rax, [rdi+14h]
0x18006abb8  xor     r8d, r8d; struct _RECTL *
0x18006abbb  mov     [rsi+14h], rax
0x18006abbf  mov     rdx, rdi; struct _RASTER_DATA *
0x18006abc2  and     eax, 1FFFFFFFh
0x18006abc7  mov     dword ptr [rsi+20h], 8
0x18006abce  add     eax, 3
0x18006abd1  mov     dword ptr [rsi+24h], 1
0x18006abd8  and     eax, 0FFFFFFFCh
0x18006abdb  mov     [rsi+1Ch], eax
0x18006abde  mov     eax, [rdi+28h]
0x18006abe1  mov     [rsi+28h], eax
0x18006abe4  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x18006abe9  xor     r8d, r8d; struct _RECTL *
0x18006abec  lea     rcx, [rbp+var_28]; struct _RASTER_ITERATOR *
0x18006abf0  mov     rdx, rsi; struct _RASTER_DATA *
0x18006abf3  call    ?RI_Init@@YAXPEAU_RASTER_ITERATOR@@PEAU_RASTER_DATA@@PEAU_RECTL@@K@Z; RI_Init(_RASTER_ITERATOR *,_RASTER_DATA *,_RECTL *,ulong)
0x18006abf8  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006abfc  xor     edi, edi
0x18006abfe  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x18006ac03  test    eax, eax
0x18006ac05  jle     loc_18006ACA5
0x18006ac0b  mov     edx, edi; int
0x18006ac0d  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006ac11  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x18006ac16  mov     edx, edi; int
0x18006ac18  lea     rcx, [rbp+var_28]; struct _RASTER_ITERATOR *
0x18006ac1c  call    ?RI_SelectRow@@YAXPEAU_RASTER_ITERATOR@@J@Z; RI_SelectRow(_RASTER_ITERATOR *,long)
0x18006ac21  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006ac25  xor     ebx, ebx
0x18006ac27  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x18006ac2c  test    eax, eax
0x18006ac2e  jle     short loc_18006AC92
0x18006ac30  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006ac34  mov     edx, ebx; int
0x18006ac36  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006ac3a  call    ?RI_GetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_GetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x18006ac3f  cmp     dword ptr [rbp+arg_0], 20h ; ' '
0x18006ac43  jnz     short loc_18006AC4C
0x18006ac45  and     dword ptr [rbp+arg_0+4], 0FFFFFFh
0x18006ac4c  lea     rdx, [rbp+arg_0]; struct _PIXEL *
0x18006ac50  mov     rcx, r14; struct _PALETTE *
0x18006ac53  call    ?FindPaletteEntry@@YAJPEAU_PALETTE@@PEAU_PIXEL@@@Z; FindPaletteEntry(_PALETTE *,_PIXEL *)
0x18006ac58  test    eax, eax
0x18006ac5a  js      short loc_18006AC66
0x18006ac5c  mov     dword ptr [rbp+arg_0+4], eax
0x18006ac5f  cmp     eax, 0FFh
0x18006ac64  jbe     short loc_18006AC6D
0x18006ac66  mov     dword ptr [rbp+arg_0+4], 0
0x18006ac6d  lea     r8, [rbp+arg_0]; struct _PIXEL *
0x18006ac71  mov     dword ptr [rbp+arg_0], 8
0x18006ac78  mov     edx, ebx; int
0x18006ac7a  lea     rcx, [rbp+var_28]; struct _RASTER_ITERATOR *
0x18006ac7e  call    ?RI_SetPixel@@YAHPEAU_RASTER_ITERATOR@@JPEAU_PIXEL@@@Z; RI_SetPixel(_RASTER_ITERATOR *,long,_PIXEL *)
0x18006ac83  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006ac87  inc     ebx
0x18006ac89  call    ?RI_NumCols@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumCols(_RASTER_ITERATOR *)
0x18006ac8e  cmp     ebx, eax
0x18006ac90  jl      short loc_18006AC30
0x18006ac92  lea     rcx, [rbp+var_50]; struct _RASTER_ITERATOR *
0x18006ac96  inc     edi
0x18006ac98  call    ?RI_NumRows@@YAJPEAU_RASTER_ITERATOR@@@Z; RI_NumRows(_RASTER_ITERATOR *)
0x18006ac9d  cmp     edi, eax
0x18006ac9f  jl      loc_18006AC0B
0x18006aca5  mov     rax, rsi
0x18006aca8  jmp     short loc_18006ACAC
0x18006acaa  xor     eax, eax
0x18006acac  lea     r11, [rsp+70h+var_s0]
0x18006acb1  mov     rbx, [r11+28h]
0x18006acb5  mov     rsi, [r11+30h]
0x18006acb9  mov     rsp, r11
0x18006acbc  pop     r14
0x18006acbe  pop     rdi
0x18006acbf  pop     rbp
0x18006acc0  retn
```

# BFillDevInfo

- ea: `0x180002a34`
- end: `0x180002d54`
- name: `BFillDevInfo`
- size: `800`
- prototype: `HPALETTE __fastcall(__int64, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004240`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180002a34`
- `0x18005e0c4`

## import_xrefs

- `GDI32!EngCreatePalette` at `0x180002cf9`
- `GDI32!EngCreatePalette` at `0x180002cf9`
- `GDI32!EngGetCurrentCodePage` at `0x180002b01`
- `GDI32!EngGetCurrentCodePage` at `0x180002b01`

## string_xrefs

- `0x180002b98`: `Courier`

## pseudocode

```c
HPALETTE __fastcall BFillDevInfo(__int64 a1, void *a2, unsigned int a3)
{
  size_t v3; // r14
  size_t v6; // rdi
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  int v10; // esi
  int v11; // eax
  int v12; // r8d
  int v13; // r10d
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rcx
  const wchar_t *v18; // r10
  __int64 v19; // r8
  _WORD *v20; // rax
  _WORD *v21; // rcx
  __int64 v22; // rcx
  const wchar_t *v23; // r10
  __int64 v24; // r8
  _WORD *v25; // rax
  _WORD *v26; // rcx
  const wchar_t *v27; // rcx
  _WORD *v28; // rax
  _WORD *v29; // rcx
  char v30; // cl
  HPALETTE result; // rax
  USHORT AnsiCodePage[2]; // [rsp+30h] [rbp-D0h] BYREF
  USHORT OemCodePage; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v34; // [rsp+38h] [rbp-C8h]
  int Src; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+64h] [rbp-9Ch]
  __int128 v37; // [rsp+74h] [rbp-8Ch] BYREF
  __int128 v38; // [rsp+84h] [rbp-7Ch]
  __int128 v39; // [rsp+94h] [rbp-6Ch]
  _DWORD v40[11]; // [rsp+A4h] [rbp-5Ch]
  _OWORD v41[3]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v42[23]; // [rsp+100h] [rbp+0h]
  _BYTE v43[28]; // [rsp+15Ch] [rbp+5Ch]
  int v44; // [rsp+178h] [rbp+78h]
  __int64 v45; // [rsp+17Ch] [rbp+7Ch]
  HPALETTE v46; // [rsp+188h] [rbp+88h]
  int v47; // [rsp+190h] [rbp+90h]

  v3 = a3;
  v6 = 312;
  v34 = 0;
  memset_0(&Src, 0, 0x138u);
  v7 = *(_QWORD *)(a1 + 96);
  v8 = 1610613023;
  if ( (*(_DWORD *)(v7 + 4) & 0x2000) == 0 )
    v8 = 1610621215;
  Src = v8;
  if ( *(_DWORD *)(a1 + 708) && *(int *)(v7 + 140) > 1 )
    Src = v8 | 0x6000000;
  if ( *(int *)(v7 + 140) >= 2 && *(_DWORD *)(*(_QWORD *)(a1 + 2144) + 20LL) >= 0x7DAu )
    v47 |= 1u;
  v9 = *(_QWORD *)(a1 + 3656);
  OemCodePage = 0;
  AnsiCodePage[0] = 0;
  v10 = *(_DWORD *)(v9 + 28);
  v44 = v10;
  EngGetCurrentCodePage(&OemCodePage, AnsiCodePage);
  v11 = 0;
  while ( HIDWORD(CharSetInfo[v11]) != AnsiCodePage[0] )
  {
    if ( ++v11 >= 14 )
    {
      v12 = v34;
      goto LABEL_14;
    }
  }
  v12 = CharSetInfo[v11];
  v13 = 0;
  LODWORD(v34) = v12;
  if ( v12 )
    goto LABEL_15;
LABEL_14:
  v13 = 1;
LABEL_15:
  v14 = *(_DWORD *)(a1 + 712);
  LODWORD(v37) = 400;
  BYTE11(v37) = 49;
  LODWORD(v36) = (10 * v14 + 36) / -72;
  if ( v10 )
  {
    v15 = 32;
    v16 = 2147483646;
    if ( v13 )
    {
      v17 = 2147483646;
      v18 = L"Courier";
      v19 = 32;
      v20 = (_WORD *)&v37 + 6;
      do
      {
        if ( !v17 )
          break;
        if ( !*v18 )
          break;
        *v20++ = *v18++;
        --v17;
        --v19;
      }
      while ( v19 );
      v21 = v20 - 1;
      if ( v19 )
        v21 = v20;
      *v21 = 0;
      BYTE7(v37) = 0;
    }
    else if ( v12 == 128 )
    {
      v22 = 2147483646;
      v23 = L"Ryumin-Light-90ms-RKSJ-H";
      v24 = 32;
      v25 = (_WORD *)&v37 + 6;
      do
      {
        if ( !v22 )
          break;
        if ( !*v23 )
          break;
        *v25++ = *v23++;
        --v22;
        --v24;
      }
      while ( v24 );
      v26 = v25 - 1;
      if ( v24 )
        v26 = v25;
      *v26 = 0;
      BYTE11(v37) = 17;
      BYTE7(v37) = 0x80;
    }
    else
    {
      BYTE7(v37) = v12;
    }
    v27 = L"Helvetica";
    v28 = (_WORD *)v41 + 6;
    *(_OWORD *)v43 = *(_OWORD *)v40;
    *(_OWORD *)v42 = *(_OWORD *)v40;
    *(_OWORD *)&v43[12] = *(_OWORD *)&v40[3];
    *(_OWORD *)&v42[3] = *(_OWORD *)&v40[3];
    *(_OWORD *)&v42[7] = v36;
    *(_OWORD *)&v42[11] = v37;
    *(_OWORD *)&v42[15] = v38;
    *(_OWORD *)&v42[19] = v39;
    *(_OWORD *)&v40[7] = v36;
    v41[0] = v37;
    v41[1] = v38;
    v41[2] = v39;
    do
    {
      if ( !v16 )
        break;
      if ( !*v27 )
        break;
      *v28++ = *v27++;
      --v16;
      --v15;
    }
    while ( v15 );
    v29 = v28 - 1;
    if ( v15 )
      v29 = v28;
    *v29 = 0;
    BYTE11(v41[0]) = 34;
  }
  else
  {
    v30 = v34;
    if ( v13 )
      v30 = 0;
    BYTE7(v37) = v30;
  }
  v45 = 5;
  result = EngCreatePalette(4u, 0, 0, 0, 0, 0);
  *(_QWORD *)(a1 + 120) = result;
  if ( result )
  {
    v46 = result;
    if ( (unsigned int)v3 < 0x138 )
      v6 = v3;
    memcpy_0(a2, &Src, v6);
    return (HPALETTE)1;
  }
  return result;
}

```

## disassembly

```asm
0x180002a34  push    rbp
0x180002a36  push    rbx
0x180002a37  push    rsi
0x180002a38  push    rdi
0x180002a39  push    r12
0x180002a3b  push    r14
0x180002a3d  push    r15
0x180002a3f  lea     rbp, [rsp-0B0h]
0x180002a47  sub     rsp, 1B0h
0x180002a4e  mov     rax, cs:__security_cookie
0x180002a55  xor     rax, rsp
0x180002a58  mov     [rbp+0E0h+var_40], rax
0x180002a5f  mov     r14d, r8d
0x180002a62  mov     r15, rdx
0x180002a65  mov     rbx, rcx
0x180002a68  xorps   xmm0, xmm0
0x180002a6b  mov     edi, 138h
0x180002a70  lea     rcx, [rsp+1E0h+Src]; void *
0x180002a75  mov     r8d, edi; Size
0x180002a78  xor     edx, edx; Val
0x180002a7a  movups  [rsp+1E0h+var_1A8], xmm0
0x180002a7f  call    memset_0
0x180002a84  mov     rcx, [rbx+60h]
0x180002a88  mov     eax, 6000011Fh
0x180002a8d  mov     edx, 6000211Fh
0x180002a92  test    dword ptr [rcx+4], 2000h
0x180002a99  cmovz   eax, edx
0x180002a9c  xor     r12d, r12d
0x180002a9f  mov     [rsp+1E0h+Src], eax
0x180002aa3  cmp     [rbx+2C4h], r12d
0x180002aaa  jz      short loc_180002ABE
0x180002aac  cmp     dword ptr [rcx+8Ch], 1
0x180002ab3  jle     short loc_180002ABE
0x180002ab5  or      eax, 6000000h
0x180002aba  mov     [rsp+1E0h+Src], eax
0x180002abe  cmp     dword ptr [rcx+8Ch], 2
0x180002ac5  jl      short loc_180002ADE
0x180002ac7  mov     rax, [rbx+860h]
0x180002ace  cmp     dword ptr [rax+14h], 7DAh
0x180002ad5  jb      short loc_180002ADE
0x180002ad7  or      [rbp+0E0h+var_50], 1
0x180002ade  mov     rax, [rbx+0E48h]
0x180002ae5  lea     rdx, [rsp+1E0h+AnsiCodePage]; AnsiCodePage
0x180002aea  lea     rcx, [rsp+1E0h+OemCodePage]; OemCodePage
0x180002aef  mov     [rsp+1E0h+OemCodePage], r12w
0x180002af5  mov     [rsp+1E0h+AnsiCodePage], r12w
0x180002afb  mov     esi, [rax+1Ch]
0x180002afe  mov     [rbp+0E0h+var_68], esi
0x180002b01  call    cs:__imp_EngGetCurrentCodePage
0x180002b08  nop     dword ptr [rax+rax+00h]
0x180002b0d  movzx   ecx, [rsp+1E0h+AnsiCodePage]
0x180002b12  lea     rdx, CharSetInfo
0x180002b19  mov     eax, r12d
0x180002b1c  mov     r8d, eax
0x180002b1f  cmp     [rdx+r8*8+4], ecx
0x180002b24  jz      short loc_180002B34
0x180002b26  inc     eax
0x180002b28  cmp     eax, 0Eh
0x180002b2b  jl      short loc_180002B1C
0x180002b2d  mov     r8d, dword ptr [rsp+1E0h+var_1A8]
0x180002b32  jmp     short loc_180002B45
0x180002b34  mov     r8d, [rdx+r8*8]
0x180002b38  mov     r10d, r12d
0x180002b3b  mov     dword ptr [rsp+1E0h+var_1A8], r8d
0x180002b40  test    r8d, r8d
0x180002b43  jnz     short loc_180002B4B
0x180002b45  mov     r10d, 1
0x180002b4b  mov     eax, [rbx+2C8h]
0x180002b51  mov     dword ptr [rsp+1E0h+var_16C], 190h
0x180002b59  mov     byte ptr [rsp+1E0h+var_16C+0Bh], 31h ; '1'
0x180002b5e  lea     ecx, [rax+rax*4]
0x180002b61  mov     eax, 0C71C71C7h
0x180002b66  lea     ecx, ds:24h[rcx*2]
0x180002b6d  imul    ecx
0x180002b6f  sar     edx, 4
0x180002b72  mov     eax, edx
0x180002b74  shr     eax, 1Fh
0x180002b77  add     edx, eax
0x180002b79  mov     dword ptr [rsp+1E0h+var_17C], edx
0x180002b7d  test    esi, esi
0x180002b7f  jz      loc_180002CCC
0x180002b85  mov     edx, 20h ; ' '
0x180002b8a  mov     r9d, 7FFFFFFEh
0x180002b90  test    r10d, r10d
0x180002b93  jz      short loc_180002BE0
0x180002b95  mov     ecx, r9d
0x180002b98  lea     r10, aCourier; "Courier"
0x180002b9f  mov     r8d, edx
0x180002ba2  lea     rax, [rbp+0E0h+var_16C+0Ch]
0x180002ba6  test    rcx, rcx
0x180002ba9  jz      short loc_180002BCA
0x180002bab  movzx   r11d, word ptr [r10]
0x180002baf  test    r11w, r11w
0x180002bb3  jz      short loc_180002BCA
0x180002bb5  mov     [rax], r11w
0x180002bb9  add     r10, 2
0x180002bbd  add     rax, 2
0x180002bc1  dec     rcx
0x180002bc4  sub     r8, 1
0x180002bc8  jnz     short loc_180002BA6
0x180002bca  test    r8, r8
0x180002bcd  lea     rcx, [rax-2]
0x180002bd1  cmovnz  rcx, rax
0x180002bd5  mov     [rcx], r12w
0x180002bd9  mov     byte ptr [rsp+1E0h+var_16C+7], r12b
0x180002bde  jmp     short loc_180002C3E
0x180002be0  cmp     r8d, 80h
0x180002be7  jnz     short loc_180002C39
0x180002be9  mov     rcx, r9
0x180002bec  lea     r10, aRyuminLight90m; "Ryumin-Light-90ms-RKSJ-H"
0x180002bf3  mov     r8, rdx
0x180002bf6  lea     rax, [rbp+0E0h+var_16C+0Ch]
0x180002bfa  test    rcx, rcx
0x180002bfd  jz      short loc_180002C1E
0x180002bff  movzx   r11d, word ptr [r10]
0x180002c03  test    r11w, r11w
0x180002c07  jz      short loc_180002C1E
0x180002c09  mov     [rax], r11w
0x180002c0d  add     r10, 2
0x180002c11  add     rax, 2
0x180002c15  dec     rcx
0x180002c18  sub     r8, 1
0x180002c1c  jnz     short loc_180002BFA
0x180002c1e  test    r8, r8
0x180002c21  lea     rcx, [rax-2]
0x180002c25  cmovnz  rcx, rax
0x180002c29  mov     [rcx], r12w
0x180002c2d  mov     byte ptr [rsp+1E0h+var_16C+0Bh], 11h
0x180002c32  mov     byte ptr [rsp+1E0h+var_16C+7], 80h
0x180002c37  jmp     short loc_180002C3E
0x180002c39  mov     byte ptr [rsp+1E0h+var_16C+7], r8b
0x180002c3e  movups  xmm1, xmmword ptr [rbp+0E0h+var_13C]
0x180002c42  lea     rcx, aHelvetica_0; "Helvetica"
0x180002c49  movups  xmm5, [rsp+1E0h+var_17C]
0x180002c4e  lea     rax, [rbp+0E0h+var_104]
0x180002c52  movups  xmm4, [rsp+1E0h+var_16C]
0x180002c57  movups  xmm3, [rbp+0E0h+var_15C]
0x180002c5b  movups  xmm2, [rbp+0E0h+var_14C]
0x180002c5f  movaps  xmm0, xmmword ptr [rbp+0E0h+var_13C+0Ch]
0x180002c63  movups  xmmword ptr [rbp+0E0h+var_84], xmm1
0x180002c67  movaps  xmmword ptr [rbp+0E0h+var_E0], xmm1
0x180002c6b  movups  xmmword ptr [rbp+0E0h+var_84+0Ch], xmm0
0x180002c6f  movups  xmmword ptr [rbp+0E0h+var_E0+0Ch], xmm0
0x180002c73  movups  [rbp+0E0h+var_C4], xmm5
0x180002c77  movups  [rbp+0E0h+var_B4], xmm4
0x180002c7b  movups  [rbp+0E0h+var_A4], xmm3
0x180002c7f  movups  [rbp+0E0h+var_94], xmm2
0x180002c83  movaps  [rbp+0E0h+var_120], xmm5
0x180002c87  movaps  xmmword ptr [rbp-30h], xmm4
0x180002c8b  movaps  [rbp+0E0h+var_100], xmm3
0x180002c8f  movaps  [rbp+0E0h+var_F0], xmm2
0x180002c93  test    r9, r9
0x180002c96  jz      short loc_180002CB7
0x180002c98  movzx   r8d, word ptr [rcx]
0x180002c9c  test    r8w, r8w
0x180002ca0  jz      short loc_180002CB7
0x180002ca2  mov     [rax], r8w
0x180002ca6  add     rcx, 2
0x180002caa  add     rax, 2
0x180002cae  dec     r9
0x180002cb1  sub     rdx, 1
0x180002cb5  jnz     short loc_180002C93
0x180002cb7  test    rdx, rdx
0x180002cba  lea     rcx, [rax-2]
0x180002cbe  cmovnz  rcx, rax
0x180002cc2  mov     [rcx], r12w
0x180002cc6  mov     [rbp+0E0h+var_105], 22h ; '"'
0x180002cca  jmp     short loc_180002CDC
0x180002ccc  movzx   ecx, byte ptr [rsp+1E0h+var_1A8]
0x180002cd1  test    r10d, r10d
0x180002cd4  cmovnz  ecx, r12d
0x180002cd8  mov     byte ptr [rsp+1E0h+var_16C+7], cl
0x180002cdc  xor     edx, edx; cColors
0x180002cde  mov     [rsp+1E0h+flBlue], r12d; flBlue
0x180002ce3  xor     r9d, r9d; flRed
0x180002ce6  mov     [rbp+0E0h+var_64], 5
0x180002cee  xor     r8d, r8d; pulColors
0x180002cf1  mov     [rsp+1E0h+flGreen], r12d; flGreen
0x180002cf6  lea     ecx, [rdx+4]; iMode
0x180002cf9  call    cs:__imp_EngCreatePalette
0x180002d00  nop     dword ptr [rax+rax+00h]
0x180002d05  mov     [rbx+78h], rax
0x180002d09  test    rax, rax
0x180002d0c  jz      short loc_180002D32
0x180002d0e  mov     [rbp+0E0h+var_58], rax
0x180002d15  cmp     r14d, edi
0x180002d18  jnb     short loc_180002D1D
0x180002d1a  mov     rdi, r14
0x180002d1d  mov     r8, rdi; Size
0x180002d20  lea     rdx, [rsp+1E0h+Src]; Src
0x180002d25  mov     rcx, r15; void *
0x180002d28  call    memcpy_0
0x180002d2d  mov     eax, 1
0x180002d32  mov     rcx, [rbp+0E0h+var_40]
0x180002d39  xor     rcx, rsp; StackCookie
0x180002d3c  call    __security_check_cookie
0x180002d41  add     rsp, 1B0h
0x180002d48  pop     r15
0x180002d4a  pop     r14
0x180002d4c  pop     r12
0x180002d4e  pop     rdi
0x180002d4f  pop     rsi
0x180002d50  pop     rbx
0x180002d51  pop     rbp
0x180002d52  retn
```

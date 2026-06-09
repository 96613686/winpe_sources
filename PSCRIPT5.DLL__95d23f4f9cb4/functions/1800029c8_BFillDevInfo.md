# BFillDevInfo

- ea: `0x1800029c8`
- end: `0x180002cdb`
- name: `BFillDevInfo`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800041a0`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x1800029c8`
- `0x18005c434`

## import_xrefs

- `GDI32!EngCreatePalette` at `0x180002c87`
- `GDI32!EngCreatePalette` at `0x180002c87`
- `GDI32!EngGetCurrentCodePage` at `0x180002a95`
- `GDI32!EngGetCurrentCodePage` at `0x180002a95`

## string_xrefs

- `0x180002b26`: `Courier`

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
0x1800029c8  push    rbp
0x1800029ca  push    rbx
0x1800029cb  push    rsi
0x1800029cc  push    rdi
0x1800029cd  push    r12
0x1800029cf  push    r14
0x1800029d1  push    r15
0x1800029d3  lea     rbp, [rsp-0B0h]
0x1800029db  sub     rsp, 1B0h
0x1800029e2  mov     rax, cs:__security_cookie
0x1800029e9  xor     rax, rsp
0x1800029ec  mov     [rbp+0E0h+var_40], rax
0x1800029f3  mov     r14d, r8d
0x1800029f6  mov     r15, rdx
0x1800029f9  mov     rbx, rcx
0x1800029fc  xorps   xmm0, xmm0
0x1800029ff  mov     edi, 138h
0x180002a04  lea     rcx, [rsp+1E0h+Src]; void *
0x180002a09  mov     r8d, edi; Size
0x180002a0c  xor     edx, edx; Val
0x180002a0e  movups  [rsp+1E0h+var_1A8], xmm0
0x180002a13  call    memset_0
0x180002a18  mov     rcx, [rbx+60h]
0x180002a1c  mov     eax, 6000011Fh
0x180002a21  mov     edx, 6000211Fh
0x180002a26  test    dword ptr [rcx+4], 2000h
0x180002a2d  cmovz   eax, edx
0x180002a30  xor     r12d, r12d
0x180002a33  mov     [rsp+1E0h+Src], eax
0x180002a37  cmp     [rbx+2C4h], r12d
0x180002a3e  jz      short loc_180002A52
0x180002a40  cmp     dword ptr [rcx+8Ch], 1
0x180002a47  jle     short loc_180002A52
0x180002a49  or      eax, 6000000h
0x180002a4e  mov     [rsp+1E0h+Src], eax
0x180002a52  cmp     dword ptr [rcx+8Ch], 2
0x180002a59  jl      short loc_180002A72
0x180002a5b  mov     rax, [rbx+860h]
0x180002a62  cmp     dword ptr [rax+14h], 7DAh
0x180002a69  jb      short loc_180002A72
0x180002a6b  or      [rbp+0E0h+var_50], 1
0x180002a72  mov     rax, [rbx+0E48h]
0x180002a79  lea     rdx, [rsp+1E0h+AnsiCodePage]; AnsiCodePage
0x180002a7e  lea     rcx, [rsp+1E0h+OemCodePage]; OemCodePage
0x180002a83  mov     [rsp+1E0h+OemCodePage], r12w
0x180002a89  mov     [rsp+1E0h+AnsiCodePage], r12w
0x180002a8f  mov     esi, [rax+1Ch]
0x180002a92  mov     [rbp+0E0h+var_68], esi
0x180002a95  call    cs:__imp_EngGetCurrentCodePage
0x180002a9b  movzx   ecx, [rsp+1E0h+AnsiCodePage]
0x180002aa0  lea     rdx, CharSetInfo
0x180002aa7  mov     eax, r12d
0x180002aaa  mov     r8d, eax
0x180002aad  cmp     [rdx+r8*8+4], ecx
0x180002ab2  jz      short loc_180002AC2
0x180002ab4  inc     eax
0x180002ab6  cmp     eax, 0Eh
0x180002ab9  jl      short loc_180002AAA
0x180002abb  mov     r8d, dword ptr [rsp+1E0h+var_1A8]
0x180002ac0  jmp     short loc_180002AD3
0x180002ac2  mov     r8d, [rdx+r8*8]
0x180002ac6  mov     r10d, r12d
0x180002ac9  mov     dword ptr [rsp+1E0h+var_1A8], r8d
0x180002ace  test    r8d, r8d
0x180002ad1  jnz     short loc_180002AD9
0x180002ad3  mov     r10d, 1
0x180002ad9  mov     eax, [rbx+2C8h]
0x180002adf  mov     dword ptr [rsp+1E0h+var_16C], 190h
0x180002ae7  mov     byte ptr [rsp+1E0h+var_16C+0Bh], 31h ; '1'
0x180002aec  lea     ecx, [rax+rax*4]
0x180002aef  mov     eax, 0C71C71C7h
0x180002af4  lea     ecx, ds:24h[rcx*2]
0x180002afb  imul    ecx
0x180002afd  sar     edx, 4
0x180002b00  mov     eax, edx
0x180002b02  shr     eax, 1Fh
0x180002b05  add     edx, eax
0x180002b07  mov     dword ptr [rsp+1E0h+var_17C], edx
0x180002b0b  test    esi, esi
0x180002b0d  jz      loc_180002C5A
0x180002b13  mov     edx, 20h ; ' '
0x180002b18  mov     r9d, 7FFFFFFEh
0x180002b1e  test    r10d, r10d
0x180002b21  jz      short loc_180002B6E
0x180002b23  mov     ecx, r9d
0x180002b26  lea     r10, aCourier; "Courier"
0x180002b2d  mov     r8d, edx
0x180002b30  lea     rax, [rbp+0E0h+var_16C+0Ch]
0x180002b34  test    rcx, rcx
0x180002b37  jz      short loc_180002B58
0x180002b39  movzx   r11d, word ptr [r10]
0x180002b3d  test    r11w, r11w
0x180002b41  jz      short loc_180002B58
0x180002b43  mov     [rax], r11w
0x180002b47  add     r10, 2
0x180002b4b  add     rax, 2
0x180002b4f  dec     rcx
0x180002b52  sub     r8, 1
0x180002b56  jnz     short loc_180002B34
0x180002b58  test    r8, r8
0x180002b5b  lea     rcx, [rax-2]
0x180002b5f  cmovnz  rcx, rax
0x180002b63  mov     [rcx], r12w
0x180002b67  mov     byte ptr [rsp+1E0h+var_16C+7], r12b
0x180002b6c  jmp     short loc_180002BCC
0x180002b6e  cmp     r8d, 80h
0x180002b75  jnz     short loc_180002BC7
0x180002b77  mov     rcx, r9
0x180002b7a  lea     r10, aRyuminLight90m; "Ryumin-Light-90ms-RKSJ-H"
0x180002b81  mov     r8, rdx
0x180002b84  lea     rax, [rbp+0E0h+var_16C+0Ch]
0x180002b88  test    rcx, rcx
0x180002b8b  jz      short loc_180002BAC
0x180002b8d  movzx   r11d, word ptr [r10]
0x180002b91  test    r11w, r11w
0x180002b95  jz      short loc_180002BAC
0x180002b97  mov     [rax], r11w
0x180002b9b  add     r10, 2
0x180002b9f  add     rax, 2
0x180002ba3  dec     rcx
0x180002ba6  sub     r8, 1
0x180002baa  jnz     short loc_180002B88
0x180002bac  test    r8, r8
0x180002baf  lea     rcx, [rax-2]
0x180002bb3  cmovnz  rcx, rax
0x180002bb7  mov     [rcx], r12w
0x180002bbb  mov     byte ptr [rsp+1E0h+var_16C+0Bh], 11h
0x180002bc0  mov     byte ptr [rsp+1E0h+var_16C+7], 80h
0x180002bc5  jmp     short loc_180002BCC
0x180002bc7  mov     byte ptr [rsp+1E0h+var_16C+7], r8b
0x180002bcc  movups  xmm1, xmmword ptr [rbp+0E0h+var_13C]
0x180002bd0  lea     rcx, aHelvetica_0; "Helvetica"
0x180002bd7  movups  xmm5, [rsp+1E0h+var_17C]
0x180002bdc  lea     rax, [rbp+0E0h+var_104]
0x180002be0  movups  xmm4, [rsp+1E0h+var_16C]
0x180002be5  movups  xmm3, [rbp+0E0h+var_15C]
0x180002be9  movups  xmm2, [rbp+0E0h+var_14C]
0x180002bed  movaps  xmm0, xmmword ptr [rbp+0E0h+var_13C+0Ch]
0x180002bf1  movups  xmmword ptr [rbp+0E0h+var_84], xmm1
0x180002bf5  movaps  xmmword ptr [rbp+0E0h+var_E0], xmm1
0x180002bf9  movups  xmmword ptr [rbp+0E0h+var_84+0Ch], xmm0
0x180002bfd  movups  xmmword ptr [rbp+0E0h+var_E0+0Ch], xmm0
0x180002c01  movups  [rbp+0E0h+var_C4], xmm5
0x180002c05  movups  [rbp+0E0h+var_B4], xmm4
0x180002c09  movups  [rbp+0E0h+var_A4], xmm3
0x180002c0d  movups  [rbp+0E0h+var_94], xmm2
0x180002c11  movaps  [rbp+0E0h+var_120], xmm5
0x180002c15  movaps  xmmword ptr [rbp-30h], xmm4
0x180002c19  movaps  [rbp+0E0h+var_100], xmm3
0x180002c1d  movaps  [rbp+0E0h+var_F0], xmm2
0x180002c21  test    r9, r9
0x180002c24  jz      short loc_180002C45
0x180002c26  movzx   r8d, word ptr [rcx]
0x180002c2a  test    r8w, r8w
0x180002c2e  jz      short loc_180002C45
0x180002c30  mov     [rax], r8w
0x180002c34  add     rcx, 2
0x180002c38  add     rax, 2
0x180002c3c  dec     r9
0x180002c3f  sub     rdx, 1
0x180002c43  jnz     short loc_180002C21
0x180002c45  test    rdx, rdx
0x180002c48  lea     rcx, [rax-2]
0x180002c4c  cmovnz  rcx, rax
0x180002c50  mov     [rcx], r12w
0x180002c54  mov     [rbp+0E0h+var_105], 22h ; '"'
0x180002c58  jmp     short loc_180002C6A
0x180002c5a  movzx   ecx, byte ptr [rsp+1E0h+var_1A8]
0x180002c5f  test    r10d, r10d
0x180002c62  cmovnz  ecx, r12d
0x180002c66  mov     byte ptr [rsp+1E0h+var_16C+7], cl
0x180002c6a  xor     edx, edx; cColors
0x180002c6c  mov     [rsp+1E0h+flBlue], r12d; flBlue
0x180002c71  xor     r9d, r9d; flRed
0x180002c74  mov     [rbp+0E0h+var_64], 5
0x180002c7c  xor     r8d, r8d; pulColors
0x180002c7f  mov     [rsp+1E0h+flGreen], r12d; flGreen
0x180002c84  lea     ecx, [rdx+4]; iMode
0x180002c87  call    cs:__imp_EngCreatePalette
0x180002c8d  mov     [rbx+78h], rax
0x180002c91  test    rax, rax
0x180002c94  jz      short loc_180002CBA
0x180002c96  mov     [rbp+0E0h+var_58], rax
0x180002c9d  cmp     r14d, edi
0x180002ca0  jnb     short loc_180002CA5
0x180002ca2  mov     rdi, r14
0x180002ca5  mov     r8, rdi; Size
0x180002ca8  lea     rdx, [rsp+1E0h+Src]; Src
0x180002cad  mov     rcx, r15; void *
0x180002cb0  call    memcpy_0
0x180002cb5  mov     eax, 1
0x180002cba  mov     rcx, [rbp+0E0h+var_40]
0x180002cc1  xor     rcx, rsp; StackCookie
0x180002cc4  call    __security_check_cookie
0x180002cc9  add     rsp, 1B0h
0x180002cd0  pop     r15
0x180002cd2  pop     r14
0x180002cd4  pop     r12
0x180002cd6  pop     rdi
0x180002cd7  pop     rsi
0x180002cd8  pop     rbx
0x180002cd9  pop     rbp
0x180002cda  retn
```

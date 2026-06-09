# common_control87

- ea: `0x18005e0c0`
- end: `0x18005e351`
- name: `common_control87`
- size: `657`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005df40`
- `0x18005df50`
- `0x18005e030`

## callees

- `0x18005e0c0`
- `0x18005ec30`
- `0x18005ec50`

## pseudocode

```c
__int64 __fastcall common_control87(int a1, int a2)
{
  int v3; // edi
  unsigned int fpsr; // eax
  __int16 v5; // r11
  int v6; // r10d
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // edx
  int v11; // eax
  int v12; // r11d
  int v13; // r11d
  int v14; // r8d
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  unsigned int v19; // ebx
  int v20; // eax
  int v21; // r8d
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  int v27; // ebx
  int v28; // ebx

  v3 = a2 & 0x308031F;
  fpsr = get_fpsr();
  v5 = fpsr;
  v6 = (fpsr >> 3) & 0x10 | 8;
  if ( (fpsr & 0x200) == 0 )
    v6 = (fpsr >> 3) & 0x10;
  v7 = v6 | 4;
  if ( (fpsr & 0x400) == 0 )
    v7 = v6;
  v8 = v7 | 2;
  if ( (fpsr & 0x800) == 0 )
    v8 = v7;
  v9 = v8 | 1;
  if ( (fpsr & 0x1000) == 0 )
    v9 = v8;
  v10 = v9 | 0x80000;
  if ( (fpsr & 0x100) == 0 )
    v10 = v9;
  v11 = fpsr & 0x6000;
  if ( v11 )
  {
    switch ( v11 )
    {
      case 8192:
        v10 |= 0x100u;
        break;
      case 16384:
        v10 |= 0x200u;
        break;
      case 24576:
        v10 |= 0x300u;
        break;
    }
  }
  v12 = (v5 & 0x8040) - 64;
  if ( v12 )
  {
    v13 = v12 - 32704;
    if ( v13 )
    {
      if ( v13 == 64 )
        v10 |= 0x1000000u;
    }
    else
    {
      v10 |= 0x3000000u;
    }
  }
  else
  {
    v10 |= 0x2000000u;
  }
  v14 = v3 & a1 | v10 & ~v3;
  if ( v14 != v10 )
  {
    v15 = (8 * (v14 & 0x10)) | 0x200;
    if ( (v14 & 8) == 0 )
      v15 = 8 * (v14 & 0x10);
    v16 = v15 | 0x400;
    if ( (v14 & 4) == 0 )
      v16 = v15;
    v17 = v16 | 0x800;
    if ( (v14 & 2) == 0 )
      v17 = v16;
    v18 = v17 | 0x1000;
    if ( (v14 & 1) == 0 )
      v18 = v17;
    v19 = v18 | 0x100;
    if ( (v14 & 0x80000) == 0 )
      v19 = v18;
    v20 = v14 & 0x300;
    if ( (v14 & 0x300) != 0 )
    {
      switch ( v20 )
      {
        case 256:
          v19 |= 0x2000u;
          break;
        case 512:
          v19 |= 0x4000u;
          break;
        case 768:
          v19 |= 0x6000u;
          break;
      }
    }
    v21 = v14 & 0x3000000;
    switch ( v21 )
    {
      case 16777216:
        v19 |= 0x8040u;
        break;
      case 33554432:
        v19 |= 0x40u;
        break;
      case 50331648:
        v19 |= 0x8000u;
        break;
    }
    if ( byte_180077BE0 && (v19 & 0x40) != 0 )
    {
      set_fpsr(v19);
    }
    else
    {
      v19 &= ~0x40u;
      set_fpsr(v19);
    }
    v22 = (v19 >> 3) & 0x10 | 8;
    if ( (v19 & 0x200) == 0 )
      v22 = (v19 >> 3) & 0x10;
    v23 = v22 | 4;
    if ( (v19 & 0x400) == 0 )
      v23 = v22;
    v24 = v23 | 2;
    if ( (v19 & 0x800) == 0 )
      v24 = v23;
    v25 = v24 | 1;
    if ( (v19 & 0x1000) == 0 )
      v25 = v24;
    v10 = v25 | 0x80000;
    if ( (v19 & 0x100) == 0 )
      v10 = v25;
    v26 = v19 & 0x6000;
    if ( (v19 & 0x6000) != 0 )
    {
      switch ( v26 )
      {
        case 8192:
          v10 |= 0x100u;
          break;
        case 16384:
          v10 |= 0x200u;
          break;
        case 24576:
          v10 |= 0x300u;
          break;
      }
    }
    v27 = (v19 & 0x8040) - 64;
    if ( v27 )
    {
      v28 = v27 - 32704;
      if ( !v28 )
        return v10 | 0x3000000;
      if ( v28 == 64 )
        return v10 | 0x1000000;
    }
    else
    {
      v10 |= 0x2000000u;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005e0c0  mov     [rsp+arg_8], rbx
0x18005e0c5  push    rdi
0x18005e0c6  sub     rsp, 20h
0x18005e0ca  mov     edi, edx
0x18005e0cc  mov     ebx, ecx
0x18005e0ce  and     edi, 308031Fh
0x18005e0d4  call    _get_fpsr
0x18005e0d9  mov     r11d, eax
0x18005e0dc  mov     r9d, eax
0x18005e0df  shr     r9d, 3
0x18005e0e3  and     r9d, 10h
0x18005e0e7  mov     r10d, r9d
0x18005e0ea  or      r10d, 8
0x18005e0ee  bt      eax, 9
0x18005e0f2  cmovnb  r10d, r9d
0x18005e0f6  mov     ecx, r10d
0x18005e0f9  or      ecx, 4
0x18005e0fc  bt      eax, 0Ah
0x18005e100  cmovnb  ecx, r10d
0x18005e104  mov     edx, ecx
0x18005e106  or      edx, 2
0x18005e109  bt      eax, 0Bh
0x18005e10d  cmovnb  edx, ecx
0x18005e110  mov     ecx, edx
0x18005e112  or      ecx, 1
0x18005e115  bt      eax, 0Ch
0x18005e119  cmovnb  ecx, edx
0x18005e11c  mov     edx, ecx
0x18005e11e  bts     edx, 13h
0x18005e122  bt      eax, 8
0x18005e126  cmovnb  edx, ecx
0x18005e129  and     eax, 6000h
0x18005e12e  jz      short loc_18005E157
0x18005e130  cmp     eax, 2000h
0x18005e135  jz      short loc_18005E153
0x18005e137  cmp     eax, 4000h
0x18005e13c  jz      short loc_18005E14D
0x18005e13e  cmp     eax, 6000h
0x18005e143  jnz     short loc_18005E157
0x18005e145  or      edx, 300h
0x18005e14b  jmp     short loc_18005E157
0x18005e14d  bts     edx, 9
0x18005e151  jmp     short loc_18005E157
0x18005e153  bts     edx, 8
0x18005e157  and     r11d, 8040h
0x18005e15e  sub     r11d, 40h ; '@'
0x18005e162  jz      short loc_18005E181
0x18005e164  sub     r11d, 7FC0h
0x18005e16b  jz      short loc_18005E179
0x18005e16d  cmp     r11d, 40h ; '@'
0x18005e171  jnz     short loc_18005E185
0x18005e173  bts     edx, 18h
0x18005e177  jmp     short loc_18005E185
0x18005e179  or      edx, 3000000h
0x18005e17f  jmp     short loc_18005E185
0x18005e181  bts     edx, 19h
0x18005e185  mov     r8d, edi
0x18005e188  not     r8d
0x18005e18b  and     r8d, edx
0x18005e18e  and     ebx, edi
0x18005e190  or      r8d, ebx
0x18005e193  cmp     r8d, edx
0x18005e196  jz      loc_18005E344
0x18005e19c  mov     ecx, r8d
0x18005e19f  and     ecx, 10h
0x18005e1a2  shl     ecx, 3
0x18005e1a5  mov     edx, ecx
0x18005e1a7  bts     edx, 9
0x18005e1ab  test    r8b, 8
0x18005e1af  cmovz   edx, ecx
0x18005e1b2  mov     ecx, edx
0x18005e1b4  bts     ecx, 0Ah
0x18005e1b8  test    r8b, 4
0x18005e1bc  cmovz   ecx, edx
0x18005e1bf  mov     edx, ecx
0x18005e1c1  bts     edx, 0Bh
0x18005e1c5  test    r8b, 2
0x18005e1c9  cmovz   edx, ecx
0x18005e1cc  mov     ecx, edx
0x18005e1ce  bts     ecx, 0Ch
0x18005e1d2  test    r8b, 1
0x18005e1d6  cmovz   ecx, edx
0x18005e1d9  mov     ebx, ecx
0x18005e1db  bts     ebx, 8
0x18005e1df  bt      r8d, 13h
0x18005e1e4  cmovnb  ebx, ecx
0x18005e1e7  mov     eax, r8d
0x18005e1ea  and     eax, 300h
0x18005e1ef  jz      short loc_18005E21C
0x18005e1f1  cmp     eax, 100h
0x18005e1f6  jz      short loc_18005E218
0x18005e1f8  cmp     eax, 200h
0x18005e1fd  jz      short loc_18005E212
0x18005e1ff  mov     [rsp+28h+arg_0], ebx
0x18005e203  cmp     eax, 300h
0x18005e208  jnz     short loc_18005E220
0x18005e20a  or      ebx, 6000h
0x18005e210  jmp     short loc_18005E21C
0x18005e212  bts     ebx, 0Eh
0x18005e216  jmp     short loc_18005E21C
0x18005e218  bts     ebx, 0Dh
0x18005e21c  mov     [rsp+28h+arg_0], ebx
0x18005e220  and     r8d, 3000000h
0x18005e227  cmp     r8d, 1000000h
0x18005e22e  jz      short loc_18005E24D
0x18005e230  cmp     r8d, 2000000h
0x18005e237  jz      short loc_18005E248
0x18005e239  cmp     r8d, 3000000h
0x18005e240  jnz     short loc_18005E257
0x18005e242  bts     ebx, 0Fh
0x18005e246  jmp     short loc_18005E253
0x18005e248  or      ebx, 40h
0x18005e24b  jmp     short loc_18005E253
0x18005e24d  or      ebx, 8040h
0x18005e253  mov     [rsp+28h+arg_0], ebx
0x18005e257  cmp     cs:byte_180077BE0, 0
0x18005e25e  jz      short loc_18005E285
0x18005e260  test    bl, 40h
0x18005e263  jz      short loc_18005E285
0x18005e265  mov     ecx, ebx
0x18005e267  call    _set_fpsr
0x18005e26c  jmp     short loc_18005E28F
0x18005e26e  mov     cs:byte_180077BE0, 0
0x18005e275  mov     ebx, [rsp+28h+arg_0]
0x18005e279  and     ebx, 0FFFFFFBFh
0x18005e27c  mov     ecx, ebx
0x18005e27e  call    _set_fpsr
0x18005e283  jmp     short loc_18005E28F
0x18005e285  and     ebx, 0FFFFFFBFh
0x18005e288  mov     ecx, ebx
0x18005e28a  call    _set_fpsr
0x18005e28f  mov     ecx, ebx
0x18005e291  shr     ecx, 3
0x18005e294  and     ecx, 10h
0x18005e297  mov     edx, ecx
0x18005e299  or      edx, 8
0x18005e29c  bt      ebx, 9
0x18005e2a0  cmovnb  edx, ecx
0x18005e2a3  mov     ecx, edx
0x18005e2a5  or      ecx, 4
0x18005e2a8  bt      ebx, 0Ah
0x18005e2ac  cmovnb  ecx, edx
0x18005e2af  mov     edx, ecx
0x18005e2b1  or      edx, 2
0x18005e2b4  bt      ebx, 0Bh
0x18005e2b8  cmovnb  edx, ecx
0x18005e2bb  mov     ecx, edx
0x18005e2bd  or      ecx, 1
0x18005e2c0  bt      ebx, 0Ch
0x18005e2c4  cmovnb  ecx, edx
0x18005e2c7  mov     edx, ecx
0x18005e2c9  bts     edx, 13h
0x18005e2cd  bt      ebx, 8
0x18005e2d1  cmovnb  edx, ecx
0x18005e2d4  mov     eax, ebx
0x18005e2d6  and     eax, 6000h
0x18005e2db  jz      short loc_18005E304
0x18005e2dd  cmp     eax, 2000h
0x18005e2e2  jz      short loc_18005E300
0x18005e2e4  cmp     eax, 4000h
0x18005e2e9  jz      short loc_18005E2FA
0x18005e2eb  cmp     eax, 6000h
0x18005e2f0  jnz     short loc_18005E304
0x18005e2f2  or      edx, 300h
0x18005e2f8  jmp     short loc_18005E304
0x18005e2fa  bts     edx, 9
0x18005e2fe  jmp     short loc_18005E304
0x18005e300  bts     edx, 8
0x18005e304  and     ebx, 8040h
0x18005e30a  sub     ebx, 40h ; '@'
0x18005e30d  jz      short loc_18005E340
0x18005e30f  sub     ebx, 7FC0h
0x18005e315  jz      short loc_18005E32D
0x18005e317  cmp     ebx, 40h ; '@'
0x18005e31a  jnz     short loc_18005E344
0x18005e31c  bts     edx, 18h
0x18005e320  mov     eax, edx
0x18005e322  mov     rbx, [rsp+28h+arg_8]
0x18005e327  add     rsp, 20h
0x18005e32b  pop     rdi
0x18005e32c  retn
0x18005e32d  or      edx, 3000000h
0x18005e333  mov     eax, edx
0x18005e335  mov     rbx, [rsp+28h+arg_8]
0x18005e33a  add     rsp, 20h
0x18005e33e  pop     rdi
0x18005e33f  retn
0x18005e340  bts     edx, 19h
0x18005e344  mov     eax, edx
0x18005e346  mov     rbx, [rsp+28h+arg_8]
0x18005e34b  add     rsp, 20h
0x18005e34f  pop     rdi
0x18005e350  retn
0x1800618b0  push    rbp
0x1800618b2  sub     rsp, 20h
0x1800618b6  mov     rbp, rdx
0x1800618b9  mov     rax, [rcx]
0x1800618bc  mov     ecx, [rax]
0x1800618be  cmp     ecx, 0C0000005h
0x1800618c4  jz      short loc_1800618D2
0x1800618c6  cmp     ecx, 0C000001Dh
0x1800618cc  jz      short loc_1800618D2
0x1800618ce  xor     eax, eax
0x1800618d0  jmp     short loc_1800618D7
0x1800618d2  mov     eax, 1
0x1800618d7  add     rsp, 20h
0x1800618db  pop     rbp
0x1800618dc  retn
```

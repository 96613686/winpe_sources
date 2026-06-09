# common_control87

- ea: `0x18005e3a0`
- end: `0x18005e631`
- name: `common_control87`
- size: `657`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005e220`
- `0x18005e230`
- `0x18005e310`

## callees

- `0x18005e3a0`
- `0x18005ef10`
- `0x18005ef30`

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
    if ( byte_18007B120 && (v19 & 0x40) != 0 )
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
0x18005e3a0  mov     [rsp+arg_8], rbx
0x18005e3a5  push    rdi
0x18005e3a6  sub     rsp, 20h
0x18005e3aa  mov     edi, edx
0x18005e3ac  mov     ebx, ecx
0x18005e3ae  and     edi, 308031Fh
0x18005e3b4  call    _get_fpsr
0x18005e3b9  mov     r11d, eax
0x18005e3bc  mov     r9d, eax
0x18005e3bf  shr     r9d, 3
0x18005e3c3  and     r9d, 10h
0x18005e3c7  mov     r10d, r9d
0x18005e3ca  or      r10d, 8
0x18005e3ce  bt      eax, 9
0x18005e3d2  cmovnb  r10d, r9d
0x18005e3d6  mov     ecx, r10d
0x18005e3d9  or      ecx, 4
0x18005e3dc  bt      eax, 0Ah
0x18005e3e0  cmovnb  ecx, r10d
0x18005e3e4  mov     edx, ecx
0x18005e3e6  or      edx, 2
0x18005e3e9  bt      eax, 0Bh
0x18005e3ed  cmovnb  edx, ecx
0x18005e3f0  mov     ecx, edx
0x18005e3f2  or      ecx, 1
0x18005e3f5  bt      eax, 0Ch
0x18005e3f9  cmovnb  ecx, edx
0x18005e3fc  mov     edx, ecx
0x18005e3fe  bts     edx, 13h
0x18005e402  bt      eax, 8
0x18005e406  cmovnb  edx, ecx
0x18005e409  and     eax, 6000h
0x18005e40e  jz      short loc_18005E437
0x18005e410  cmp     eax, 2000h
0x18005e415  jz      short loc_18005E433
0x18005e417  cmp     eax, 4000h
0x18005e41c  jz      short loc_18005E42D
0x18005e41e  cmp     eax, 6000h
0x18005e423  jnz     short loc_18005E437
0x18005e425  or      edx, 300h
0x18005e42b  jmp     short loc_18005E437
0x18005e42d  bts     edx, 9
0x18005e431  jmp     short loc_18005E437
0x18005e433  bts     edx, 8
0x18005e437  and     r11d, 8040h
0x18005e43e  sub     r11d, 40h ; '@'
0x18005e442  jz      short loc_18005E461
0x18005e444  sub     r11d, 7FC0h
0x18005e44b  jz      short loc_18005E459
0x18005e44d  cmp     r11d, 40h ; '@'
0x18005e451  jnz     short loc_18005E465
0x18005e453  bts     edx, 18h
0x18005e457  jmp     short loc_18005E465
0x18005e459  or      edx, 3000000h
0x18005e45f  jmp     short loc_18005E465
0x18005e461  bts     edx, 19h
0x18005e465  mov     r8d, edi
0x18005e468  not     r8d
0x18005e46b  and     r8d, edx
0x18005e46e  and     ebx, edi
0x18005e470  or      r8d, ebx
0x18005e473  cmp     r8d, edx
0x18005e476  jz      loc_18005E624
0x18005e47c  mov     ecx, r8d
0x18005e47f  and     ecx, 10h
0x18005e482  shl     ecx, 3
0x18005e485  mov     edx, ecx
0x18005e487  bts     edx, 9
0x18005e48b  test    r8b, 8
0x18005e48f  cmovz   edx, ecx
0x18005e492  mov     ecx, edx
0x18005e494  bts     ecx, 0Ah
0x18005e498  test    r8b, 4
0x18005e49c  cmovz   ecx, edx
0x18005e49f  mov     edx, ecx
0x18005e4a1  bts     edx, 0Bh
0x18005e4a5  test    r8b, 2
0x18005e4a9  cmovz   edx, ecx
0x18005e4ac  mov     ecx, edx
0x18005e4ae  bts     ecx, 0Ch
0x18005e4b2  test    r8b, 1
0x18005e4b6  cmovz   ecx, edx
0x18005e4b9  mov     ebx, ecx
0x18005e4bb  bts     ebx, 8
0x18005e4bf  bt      r8d, 13h
0x18005e4c4  cmovnb  ebx, ecx
0x18005e4c7  mov     eax, r8d
0x18005e4ca  and     eax, 300h
0x18005e4cf  jz      short loc_18005E4FC
0x18005e4d1  cmp     eax, 100h
0x18005e4d6  jz      short loc_18005E4F8
0x18005e4d8  cmp     eax, 200h
0x18005e4dd  jz      short loc_18005E4F2
0x18005e4df  mov     [rsp+28h+arg_0], ebx
0x18005e4e3  cmp     eax, 300h
0x18005e4e8  jnz     short loc_18005E500
0x18005e4ea  or      ebx, 6000h
0x18005e4f0  jmp     short loc_18005E4FC
0x18005e4f2  bts     ebx, 0Eh
0x18005e4f6  jmp     short loc_18005E4FC
0x18005e4f8  bts     ebx, 0Dh
0x18005e4fc  mov     [rsp+28h+arg_0], ebx
0x18005e500  and     r8d, 3000000h
0x18005e507  cmp     r8d, 1000000h
0x18005e50e  jz      short loc_18005E52D
0x18005e510  cmp     r8d, 2000000h
0x18005e517  jz      short loc_18005E528
0x18005e519  cmp     r8d, 3000000h
0x18005e520  jnz     short loc_18005E537
0x18005e522  bts     ebx, 0Fh
0x18005e526  jmp     short loc_18005E533
0x18005e528  or      ebx, 40h
0x18005e52b  jmp     short loc_18005E533
0x18005e52d  or      ebx, 8040h
0x18005e533  mov     [rsp+28h+arg_0], ebx
0x18005e537  cmp     cs:byte_18007B120, 0
0x18005e53e  jz      short loc_18005E565
0x18005e540  test    bl, 40h
0x18005e543  jz      short loc_18005E565
0x18005e545  mov     ecx, ebx
0x18005e547  call    _set_fpsr
0x18005e54c  jmp     short loc_18005E56F
0x18005e54e  mov     cs:byte_18007B120, 0
0x18005e555  mov     ebx, [rsp+28h+arg_0]
0x18005e559  and     ebx, 0FFFFFFBFh
0x18005e55c  mov     ecx, ebx
0x18005e55e  call    _set_fpsr
0x18005e563  jmp     short loc_18005E56F
0x18005e565  and     ebx, 0FFFFFFBFh
0x18005e568  mov     ecx, ebx
0x18005e56a  call    _set_fpsr
0x18005e56f  mov     ecx, ebx
0x18005e571  shr     ecx, 3
0x18005e574  and     ecx, 10h
0x18005e577  mov     edx, ecx
0x18005e579  or      edx, 8
0x18005e57c  bt      ebx, 9
0x18005e580  cmovnb  edx, ecx
0x18005e583  mov     ecx, edx
0x18005e585  or      ecx, 4
0x18005e588  bt      ebx, 0Ah
0x18005e58c  cmovnb  ecx, edx
0x18005e58f  mov     edx, ecx
0x18005e591  or      edx, 2
0x18005e594  bt      ebx, 0Bh
0x18005e598  cmovnb  edx, ecx
0x18005e59b  mov     ecx, edx
0x18005e59d  or      ecx, 1
0x18005e5a0  bt      ebx, 0Ch
0x18005e5a4  cmovnb  ecx, edx
0x18005e5a7  mov     edx, ecx
0x18005e5a9  bts     edx, 13h
0x18005e5ad  bt      ebx, 8
0x18005e5b1  cmovnb  edx, ecx
0x18005e5b4  mov     eax, ebx
0x18005e5b6  and     eax, 6000h
0x18005e5bb  jz      short loc_18005E5E4
0x18005e5bd  cmp     eax, 2000h
0x18005e5c2  jz      short loc_18005E5E0
0x18005e5c4  cmp     eax, 4000h
0x18005e5c9  jz      short loc_18005E5DA
0x18005e5cb  cmp     eax, 6000h
0x18005e5d0  jnz     short loc_18005E5E4
0x18005e5d2  or      edx, 300h
0x18005e5d8  jmp     short loc_18005E5E4
0x18005e5da  bts     edx, 9
0x18005e5de  jmp     short loc_18005E5E4
0x18005e5e0  bts     edx, 8
0x18005e5e4  and     ebx, 8040h
0x18005e5ea  sub     ebx, 40h ; '@'
0x18005e5ed  jz      short loc_18005E620
0x18005e5ef  sub     ebx, 7FC0h
0x18005e5f5  jz      short loc_18005E60D
0x18005e5f7  cmp     ebx, 40h ; '@'
0x18005e5fa  jnz     short loc_18005E624
0x18005e5fc  bts     edx, 18h
0x18005e600  mov     eax, edx
0x18005e602  mov     rbx, [rsp+28h+arg_8]
0x18005e607  add     rsp, 20h
0x18005e60b  pop     rdi
0x18005e60c  retn
0x18005e60d  or      edx, 3000000h
0x18005e613  mov     eax, edx
0x18005e615  mov     rbx, [rsp+28h+arg_8]
0x18005e61a  add     rsp, 20h
0x18005e61e  pop     rdi
0x18005e61f  retn
0x18005e620  bts     edx, 19h
0x18005e624  mov     eax, edx
0x18005e626  mov     rbx, [rsp+28h+arg_8]
0x18005e62b  add     rsp, 20h
0x18005e62f  pop     rdi
0x18005e630  retn
0x180061b90  push    rbp
0x180061b92  sub     rsp, 20h
0x180061b96  mov     rbp, rdx
0x180061b99  mov     rax, [rcx]
0x180061b9c  mov     ecx, [rax]
0x180061b9e  cmp     ecx, 0C0000005h
0x180061ba4  jz      short loc_180061BB2
0x180061ba6  cmp     ecx, 0C000001Dh
0x180061bac  jz      short loc_180061BB2
0x180061bae  xor     eax, eax
0x180061bb0  jmp     short loc_180061BB7
0x180061bb2  mov     eax, 1
0x180061bb7  add     rsp, 20h
0x180061bbb  pop     rbp
0x180061bbc  retn
```

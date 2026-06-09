# common_control87

- ea: `0x14001c0e0`
- end: `0x14001c371`
- name: `common_control87`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c0d0`

## callees

- `0x14001c0e0`
- `0x14001c950`
- `0x14001c960`

## pseudocode

```c
__int64 __fastcall common_control87(int a1, int a2)
{
  int v3; // edi
  unsigned int fpcsr; // eax
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
  fpcsr = get_fpcsr();
  v5 = fpcsr;
  v6 = (fpcsr >> 3) & 0x10 | 8;
  if ( (fpcsr & 0x200) == 0 )
    v6 = (fpcsr >> 3) & 0x10;
  v7 = v6 | 4;
  if ( (fpcsr & 0x400) == 0 )
    v7 = v6;
  v8 = v7 | 2;
  if ( (fpcsr & 0x800) == 0 )
    v8 = v7;
  v9 = v8 | 1;
  if ( (fpcsr & 0x1000) == 0 )
    v9 = v8;
  v10 = v9 | 0x80000;
  if ( (fpcsr & 0x100) == 0 )
    v10 = v9;
  v11 = fpcsr & 0x6000;
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
    if ( byte_14003BB80 && (v19 & 0x40) != 0 )
    {
      set_fpcsr(v19);
    }
    else
    {
      v19 &= ~0x40u;
      set_fpcsr(v19);
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
0x14001c0e0  mov     [rsp+arg_8], rbx
0x14001c0e5  push    rdi
0x14001c0e6  sub     rsp, 20h
0x14001c0ea  mov     edi, edx
0x14001c0ec  mov     ebx, ecx
0x14001c0ee  and     edi, 308031Fh
0x14001c0f4  call    _get_fpcsr
0x14001c0f9  mov     r11d, eax
0x14001c0fc  mov     r9d, eax
0x14001c0ff  shr     r9d, 3
0x14001c103  and     r9d, 10h
0x14001c107  mov     r10d, r9d
0x14001c10a  or      r10d, 8
0x14001c10e  bt      eax, 9
0x14001c112  cmovnb  r10d, r9d
0x14001c116  mov     ecx, r10d
0x14001c119  or      ecx, 4
0x14001c11c  bt      eax, 0Ah
0x14001c120  cmovnb  ecx, r10d
0x14001c124  mov     edx, ecx
0x14001c126  or      edx, 2
0x14001c129  bt      eax, 0Bh
0x14001c12d  cmovnb  edx, ecx
0x14001c130  mov     ecx, edx
0x14001c132  or      ecx, 1
0x14001c135  bt      eax, 0Ch
0x14001c139  cmovnb  ecx, edx
0x14001c13c  mov     edx, ecx
0x14001c13e  bts     edx, 13h
0x14001c142  bt      eax, 8
0x14001c146  cmovnb  edx, ecx
0x14001c149  and     eax, 6000h
0x14001c14e  jz      short loc_14001C177
0x14001c150  cmp     eax, 2000h
0x14001c155  jz      short loc_14001C173
0x14001c157  cmp     eax, 4000h
0x14001c15c  jz      short loc_14001C16D
0x14001c15e  cmp     eax, 6000h
0x14001c163  jnz     short loc_14001C177
0x14001c165  or      edx, 300h
0x14001c16b  jmp     short loc_14001C177
0x14001c16d  bts     edx, 9
0x14001c171  jmp     short loc_14001C177
0x14001c173  bts     edx, 8
0x14001c177  and     r11d, 8040h
0x14001c17e  sub     r11d, 40h ; '@'
0x14001c182  jz      short loc_14001C1A1
0x14001c184  sub     r11d, 7FC0h
0x14001c18b  jz      short loc_14001C199
0x14001c18d  cmp     r11d, 40h ; '@'
0x14001c191  jnz     short loc_14001C1A5
0x14001c193  bts     edx, 18h
0x14001c197  jmp     short loc_14001C1A5
0x14001c199  or      edx, 3000000h
0x14001c19f  jmp     short loc_14001C1A5
0x14001c1a1  bts     edx, 19h
0x14001c1a5  mov     r8d, edi
0x14001c1a8  not     r8d
0x14001c1ab  and     r8d, edx
0x14001c1ae  and     ebx, edi
0x14001c1b0  or      r8d, ebx
0x14001c1b3  cmp     r8d, edx
0x14001c1b6  jz      loc_14001C364
0x14001c1bc  mov     ecx, r8d
0x14001c1bf  and     ecx, 10h
0x14001c1c2  shl     ecx, 3
0x14001c1c5  mov     edx, ecx
0x14001c1c7  bts     edx, 9
0x14001c1cb  test    r8b, 8
0x14001c1cf  cmovz   edx, ecx
0x14001c1d2  mov     ecx, edx
0x14001c1d4  bts     ecx, 0Ah
0x14001c1d8  test    r8b, 4
0x14001c1dc  cmovz   ecx, edx
0x14001c1df  mov     edx, ecx
0x14001c1e1  bts     edx, 0Bh
0x14001c1e5  test    r8b, 2
0x14001c1e9  cmovz   edx, ecx
0x14001c1ec  mov     ecx, edx
0x14001c1ee  bts     ecx, 0Ch
0x14001c1f2  test    r8b, 1
0x14001c1f6  cmovz   ecx, edx
0x14001c1f9  mov     ebx, ecx
0x14001c1fb  bts     ebx, 8
0x14001c1ff  bt      r8d, 13h
0x14001c204  cmovnb  ebx, ecx
0x14001c207  mov     eax, r8d
0x14001c20a  and     eax, 300h
0x14001c20f  jz      short loc_14001C23C
0x14001c211  cmp     eax, 100h
0x14001c216  jz      short loc_14001C238
0x14001c218  cmp     eax, 200h
0x14001c21d  jz      short loc_14001C232
0x14001c21f  mov     [rsp+28h+arg_0], ebx
0x14001c223  cmp     eax, 300h
0x14001c228  jnz     short loc_14001C240
0x14001c22a  or      ebx, 6000h
0x14001c230  jmp     short loc_14001C23C
0x14001c232  bts     ebx, 0Eh
0x14001c236  jmp     short loc_14001C23C
0x14001c238  bts     ebx, 0Dh
0x14001c23c  mov     [rsp+28h+arg_0], ebx
0x14001c240  and     r8d, 3000000h
0x14001c247  cmp     r8d, 1000000h
0x14001c24e  jz      short loc_14001C26D
0x14001c250  cmp     r8d, 2000000h
0x14001c257  jz      short loc_14001C268
0x14001c259  cmp     r8d, 3000000h
0x14001c260  jnz     short loc_14001C277
0x14001c262  bts     ebx, 0Fh
0x14001c266  jmp     short loc_14001C273
0x14001c268  or      ebx, 40h
0x14001c26b  jmp     short loc_14001C273
0x14001c26d  or      ebx, 8040h
0x14001c273  mov     [rsp+28h+arg_0], ebx
0x14001c277  cmp     cs:byte_14003BB80, 0
0x14001c27e  jz      short loc_14001C2A5
0x14001c280  test    bl, 40h
0x14001c283  jz      short loc_14001C2A5
0x14001c285  mov     ecx, ebx
0x14001c287  call    _set_fpcsr
0x14001c28c  jmp     short loc_14001C2AF
0x14001c28e  mov     cs:byte_14003BB80, 0
0x14001c295  mov     ebx, [rsp+28h+arg_0]
0x14001c299  and     ebx, 0FFFFFFBFh
0x14001c29c  mov     ecx, ebx
0x14001c29e  call    _set_fpcsr
0x14001c2a3  jmp     short loc_14001C2AF
0x14001c2a5  and     ebx, 0FFFFFFBFh
0x14001c2a8  mov     ecx, ebx
0x14001c2aa  call    _set_fpcsr
0x14001c2af  mov     ecx, ebx
0x14001c2b1  shr     ecx, 3
0x14001c2b4  and     ecx, 10h
0x14001c2b7  mov     edx, ecx
0x14001c2b9  or      edx, 8
0x14001c2bc  bt      ebx, 9
0x14001c2c0  cmovnb  edx, ecx
0x14001c2c3  mov     ecx, edx
0x14001c2c5  or      ecx, 4
0x14001c2c8  bt      ebx, 0Ah
0x14001c2cc  cmovnb  ecx, edx
0x14001c2cf  mov     edx, ecx
0x14001c2d1  or      edx, 2
0x14001c2d4  bt      ebx, 0Bh
0x14001c2d8  cmovnb  edx, ecx
0x14001c2db  mov     ecx, edx
0x14001c2dd  or      ecx, 1
0x14001c2e0  bt      ebx, 0Ch
0x14001c2e4  cmovnb  ecx, edx
0x14001c2e7  mov     edx, ecx
0x14001c2e9  bts     edx, 13h
0x14001c2ed  bt      ebx, 8
0x14001c2f1  cmovnb  edx, ecx
0x14001c2f4  mov     eax, ebx
0x14001c2f6  and     eax, 6000h
0x14001c2fb  jz      short loc_14001C324
0x14001c2fd  cmp     eax, 2000h
0x14001c302  jz      short loc_14001C320
0x14001c304  cmp     eax, 4000h
0x14001c309  jz      short loc_14001C31A
0x14001c30b  cmp     eax, 6000h
0x14001c310  jnz     short loc_14001C324
0x14001c312  or      edx, 300h
0x14001c318  jmp     short loc_14001C324
0x14001c31a  bts     edx, 9
0x14001c31e  jmp     short loc_14001C324
0x14001c320  bts     edx, 8
0x14001c324  and     ebx, 8040h
0x14001c32a  sub     ebx, 40h ; '@'
0x14001c32d  jz      short loc_14001C360
0x14001c32f  sub     ebx, 7FC0h
0x14001c335  jz      short loc_14001C34D
0x14001c337  cmp     ebx, 40h ; '@'
0x14001c33a  jnz     short loc_14001C364
0x14001c33c  bts     edx, 18h
0x14001c340  mov     eax, edx
0x14001c342  mov     rbx, [rsp+28h+arg_8]
0x14001c347  add     rsp, 20h
0x14001c34b  pop     rdi
0x14001c34c  retn
0x14001c34d  or      edx, 3000000h
0x14001c353  mov     eax, edx
0x14001c355  mov     rbx, [rsp+28h+arg_8]
0x14001c35a  add     rsp, 20h
0x14001c35e  pop     rdi
0x14001c35f  retn
0x14001c360  bts     edx, 19h
0x14001c364  mov     eax, edx
0x14001c366  mov     rbx, [rsp+28h+arg_8]
0x14001c36b  add     rsp, 20h
0x14001c36f  pop     rdi
0x14001c370  retn
0x1400260d0  push    rbp
0x1400260d2  sub     rsp, 20h
0x1400260d6  mov     rbp, rdx
0x1400260d9  mov     rax, [rcx]
0x1400260dc  mov     ecx, [rax]
0x1400260de  cmp     ecx, 0C0000005h
0x1400260e4  jz      short loc_1400260F2
0x1400260e6  cmp     ecx, 0C000001Dh
0x1400260ec  jz      short loc_1400260F2
0x1400260ee  xor     eax, eax
0x1400260f0  jmp     short loc_1400260F7
0x1400260f2  mov     eax, 1
0x1400260f7  add     rsp, 20h
0x1400260fb  pop     rbp
0x1400260fc  retn
```

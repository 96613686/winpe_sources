# common_control87

- ea: `0x180019d38`
- end: `0x180019ff6`
- name: `common_control87`
- size: `702`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019d30`

## callees

- `0x180019d38`
- `0x18001a780`
- `0x18001a790`
- `0x18001ab58`

## pseudocode

```c
__int64 __fastcall common_control87(int a1, int a2)
{
  int v3; // r12d
  unsigned int fpsr; // eax
  __int16 v5; // r10
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // edx
  int v11; // eax
  int v12; // r10d
  int v13; // r10d
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
  if ( (v5 & 0x6000) != 0 )
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
    if ( byte_18003DA50 && (v19 & 0x40) != 0 )
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
      if ( v28 )
      {
        if ( v28 == 64 )
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
  }
  return v10;
}

```

## disassembly

```asm
0x180019d38  mov     [rsp+arg_8], rbx
0x180019d3d  mov     [rsp+arg_10], rsi
0x180019d42  push    r12
0x180019d44  push    r14
0x180019d46  push    r15
0x180019d48  sub     rsp, 20h
0x180019d4c  mov     r12d, edx
0x180019d4f  mov     ebx, ecx
0x180019d51  and     r12d, 308031Fh
0x180019d58  call    _get_fpsr
0x180019d5d  mov     r10d, eax
0x180019d60  mov     r9d, eax
0x180019d63  shr     r9d, 3
0x180019d67  and     r9d, 10h
0x180019d6b  mov     r8d, eax
0x180019d6e  mov     r14d, 200h
0x180019d74  mov     edx, r9d
0x180019d77  or      edx, 8
0x180019d7a  and     r8d, r14d
0x180019d7d  cmovz   edx, r9d
0x180019d81  mov     ecx, edx
0x180019d83  or      ecx, 4
0x180019d86  and     eax, 400h
0x180019d8b  cmovz   ecx, edx
0x180019d8e  mov     eax, r10d
0x180019d91  mov     r9d, 800h
0x180019d97  mov     edx, ecx
0x180019d99  or      edx, 2
0x180019d9c  and     eax, r9d
0x180019d9f  cmovz   edx, ecx
0x180019da2  mov     eax, r10d
0x180019da5  mov     r11d, 1000h
0x180019dab  mov     ecx, edx
0x180019dad  or      ecx, 1
0x180019db0  and     eax, r11d
0x180019db3  cmovz   ecx, edx
0x180019db6  mov     eax, r10d
0x180019db9  mov     esi, 100h
0x180019dbe  mov     edx, ecx
0x180019dc0  bts     edx, 13h
0x180019dc4  and     eax, esi
0x180019dc6  cmovz   edx, ecx
0x180019dc9  mov     eax, r10d
0x180019dcc  mov     r15d, 6000h
0x180019dd2  and     eax, r15d
0x180019dd5  jz      short loc_180019DF9
0x180019dd7  cmp     eax, 2000h
0x180019ddc  jz      short loc_180019DF7
0x180019dde  cmp     eax, 4000h
0x180019de3  jz      short loc_180019DF2
0x180019de5  cmp     eax, r15d
0x180019de8  jnz     short loc_180019DF9
0x180019dea  or      edx, 300h
0x180019df0  jmp     short loc_180019DF9
0x180019df2  or      edx, r14d
0x180019df5  jmp     short loc_180019DF9
0x180019df7  or      edx, esi
0x180019df9  and     r10d, 8040h
0x180019e00  sub     r10d, 40h ; '@'
0x180019e04  jz      short loc_180019E23
0x180019e06  sub     r10d, 7FC0h
0x180019e0d  jz      short loc_180019E1B
0x180019e0f  cmp     r10d, 40h ; '@'
0x180019e13  jnz     short loc_180019E27
0x180019e15  bts     edx, 18h
0x180019e19  jmp     short loc_180019E27
0x180019e1b  or      edx, 3000000h
0x180019e21  jmp     short loc_180019E27
0x180019e23  bts     edx, 19h
0x180019e27  mov     r8d, r12d
0x180019e2a  not     r8d
0x180019e2d  and     r8d, edx
0x180019e30  and     ebx, r12d
0x180019e33  or      r8d, ebx
0x180019e36  cmp     r8d, edx
0x180019e39  jz      loc_180019FDF
0x180019e3f  mov     ecx, r8d
0x180019e42  and     ecx, 10h
0x180019e45  shl     ecx, 3
0x180019e48  mov     eax, r8d
0x180019e4b  mov     edx, ecx
0x180019e4d  or      edx, r14d
0x180019e50  and     al, 8
0x180019e52  cmovz   edx, ecx
0x180019e55  mov     eax, r8d
0x180019e58  mov     ecx, edx
0x180019e5a  bts     ecx, 0Ah
0x180019e5e  and     al, 4
0x180019e60  cmovz   ecx, edx
0x180019e63  mov     eax, r8d
0x180019e66  mov     edx, ecx
0x180019e68  or      edx, r9d
0x180019e6b  and     al, 2
0x180019e6d  cmovz   edx, ecx
0x180019e70  mov     eax, r8d
0x180019e73  mov     ecx, edx
0x180019e75  or      ecx, r11d
0x180019e78  and     al, 1
0x180019e7a  cmovz   ecx, edx
0x180019e7d  mov     eax, r8d
0x180019e80  mov     ebx, ecx
0x180019e82  or      ebx, esi
0x180019e84  and     eax, 80000h
0x180019e89  cmovz   ebx, ecx
0x180019e8c  mov     eax, r8d
0x180019e8f  and     eax, 300h
0x180019e94  jz      short loc_180019EB9
0x180019e96  cmp     eax, esi
0x180019e98  jz      short loc_180019EB5
0x180019e9a  cmp     eax, r14d
0x180019e9d  jz      short loc_180019EAF
0x180019e9f  mov     [rsp+38h+arg_0], ebx
0x180019ea3  cmp     eax, 300h
0x180019ea8  jnz     short loc_180019EBD
0x180019eaa  or      ebx, r15d
0x180019ead  jmp     short loc_180019EB9
0x180019eaf  bts     ebx, 0Eh
0x180019eb3  jmp     short loc_180019EB9
0x180019eb5  bts     ebx, 0Dh
0x180019eb9  mov     [rsp+38h+arg_0], ebx
0x180019ebd  and     r8d, 3000000h
0x180019ec4  cmp     r8d, 1000000h
0x180019ecb  jz      short loc_180019EEA
0x180019ecd  cmp     r8d, 2000000h
0x180019ed4  jz      short loc_180019EE5
0x180019ed6  cmp     r8d, 3000000h
0x180019edd  jnz     short loc_180019EF4
0x180019edf  bts     ebx, 0Fh
0x180019ee3  jmp     short loc_180019EF0
0x180019ee5  or      ebx, 40h
0x180019ee8  jmp     short loc_180019EF0
0x180019eea  or      ebx, 8040h
0x180019ef0  mov     [rsp+38h+arg_0], ebx
0x180019ef4  cmp     cs:byte_18003DA50, 0
0x180019efb  jz      short loc_180019F33
0x180019efd  test    bl, 40h
0x180019f00  jz      short loc_180019F33
0x180019f02  mov     ecx, ebx
0x180019f04  call    _set_fpsr
0x180019f09  jmp     short loc_180019F3D
0x180019f0b  mov     cs:byte_18003DA50, 0
0x180019f12  mov     ebx, [rsp+38h+arg_0]
0x180019f16  and     ebx, 0FFFFFFBFh
0x180019f19  mov     ecx, ebx
0x180019f1b  call    _set_fpsr
0x180019f20  mov     esi, 100h
0x180019f25  mov     r14d, 200h
0x180019f2b  mov     r15d, 6000h
0x180019f31  jmp     short loc_180019F3D
0x180019f33  and     ebx, 0FFFFFFBFh
0x180019f36  mov     ecx, ebx
0x180019f38  call    _set_fpsr
0x180019f3d  mov     ecx, ebx
0x180019f3f  shr     ecx, 3
0x180019f42  and     ecx, 10h
0x180019f45  mov     eax, ebx
0x180019f47  mov     edx, ecx
0x180019f49  or      edx, 8
0x180019f4c  and     eax, r14d
0x180019f4f  cmovz   edx, ecx
0x180019f52  mov     eax, ebx
0x180019f54  mov     ecx, edx
0x180019f56  or      ecx, 4
0x180019f59  and     eax, 400h
0x180019f5e  cmovz   ecx, edx
0x180019f61  mov     eax, ebx
0x180019f63  mov     edx, ecx
0x180019f65  or      edx, 2
0x180019f68  and     eax, 800h
0x180019f6d  cmovz   edx, ecx
0x180019f70  mov     eax, ebx
0x180019f72  mov     ecx, edx
0x180019f74  or      ecx, 1
0x180019f77  and     eax, 1000h
0x180019f7c  cmovz   ecx, edx
0x180019f7f  mov     eax, ebx
0x180019f81  mov     edx, ecx
0x180019f83  bts     edx, 13h
0x180019f87  and     eax, esi
0x180019f89  cmovz   edx, ecx
0x180019f8c  mov     eax, ebx
0x180019f8e  and     eax, r15d
0x180019f91  jz      short loc_180019FB5
0x180019f93  cmp     eax, 2000h
0x180019f98  jz      short loc_180019FB3
0x180019f9a  cmp     eax, 4000h
0x180019f9f  jz      short loc_180019FAE
0x180019fa1  cmp     eax, r15d
0x180019fa4  jnz     short loc_180019FB5
0x180019fa6  or      edx, 300h
0x180019fac  jmp     short loc_180019FB5
0x180019fae  or      edx, r14d
0x180019fb1  jmp     short loc_180019FB5
0x180019fb3  or      edx, esi
0x180019fb5  and     ebx, 8040h
0x180019fbb  sub     ebx, 40h ; '@'
0x180019fbe  jz      short loc_180019FDB
0x180019fc0  sub     ebx, 7FC0h
0x180019fc6  jz      short loc_180019FD3
0x180019fc8  cmp     ebx, 40h ; '@'
0x180019fcb  jnz     short loc_180019FDF
0x180019fcd  bts     edx, 18h
0x180019fd1  jmp     short loc_180019FDF
0x180019fd3  or      edx, 3000000h
0x180019fd9  jmp     short loc_180019FDF
0x180019fdb  bts     edx, 19h
0x180019fdf  mov     eax, edx
0x180019fe1  mov     rbx, [rsp+38h+arg_8]
0x180019fe6  mov     rsi, [rsp+38h+arg_10]
0x180019feb  add     rsp, 20h
0x180019fef  pop     r15
0x180019ff1  pop     r14
0x180019ff3  pop     r12
0x180019ff5  retn
0x1800252f6  push    rbp
0x1800252f8  sub     rsp, 20h
0x1800252fc  mov     rbp, rdx
0x1800252ff  mov     rax, [rcx]
0x180025302  cmp     dword ptr [rax], 0C0000005h
0x180025308  jz      short loc_180025316
0x18002530a  cmp     dword ptr [rax], 0C000001Dh
0x180025310  jz      short loc_180025316
0x180025312  xor     eax, eax
0x180025314  jmp     short loc_18002531B
0x180025316  mov     eax, 1
0x18002531b  add     rsp, 20h
0x18002531f  pop     rbp
0x180025320  retn
```

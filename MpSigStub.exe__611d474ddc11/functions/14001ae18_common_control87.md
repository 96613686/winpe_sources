# common_control87

- ea: `0x14001ae18`
- end: `0x14001b0b2`
- name: `common_control87`
- size: `666`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001ae10`

## callees

- `0x14001ae18`
- `0x14001b870`
- `0x14001b87c`

## pseudocode

```c
__int64 __fastcall common_control87(int a1, int a2)
{
  int v3; // r12d
  unsigned int fpsw_inline; // eax
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
  fpsw_inline = get_fpsw_inline();
  v5 = fpsw_inline;
  v6 = (fpsw_inline >> 3) & 0x10 | 8;
  if ( (fpsw_inline & 0x200) == 0 )
    v6 = (fpsw_inline >> 3) & 0x10;
  v7 = v6 | 4;
  if ( (fpsw_inline & 0x400) == 0 )
    v7 = v6;
  v8 = v7 | 2;
  if ( (fpsw_inline & 0x800) == 0 )
    v8 = v7;
  v9 = v8 | 1;
  if ( (fpsw_inline & 0x1000) == 0 )
    v9 = v8;
  v10 = v9 | 0x80000;
  if ( (fpsw_inline & 0x100) == 0 )
    v10 = v9;
  v11 = fpsw_inline & 0x6000;
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
    if ( byte_1400D68D0 && (v19 & 0x40) != 0 )
    {
      set_fpsw_inline(v19);
    }
    else
    {
      v19 &= ~0x40u;
      set_fpsw_inline(v19);
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
0x14001ae18  mov     [rsp+arg_8], rbx
0x14001ae1d  mov     [rsp+arg_10], rsi
0x14001ae22  push    r12
0x14001ae24  push    r14
0x14001ae26  push    r15
0x14001ae28  sub     rsp, 20h
0x14001ae2c  mov     r12d, edx
0x14001ae2f  mov     ebx, ecx
0x14001ae31  and     r12d, 308031Fh
0x14001ae38  call    get_fpsw_inline
0x14001ae3d  mov     r10d, eax
0x14001ae40  mov     r9d, eax
0x14001ae43  shr     r9d, 3
0x14001ae47  and     r9d, 10h
0x14001ae4b  mov     r14d, 200h
0x14001ae51  mov     edx, r9d
0x14001ae54  or      edx, 8
0x14001ae57  test    r14d, eax
0x14001ae5a  cmovz   edx, r9d
0x14001ae5e  mov     ecx, edx
0x14001ae60  or      ecx, 4
0x14001ae63  bt      eax, 0Ah
0x14001ae67  cmovnb  ecx, edx
0x14001ae6a  mov     r9d, 800h
0x14001ae70  mov     edx, ecx
0x14001ae72  or      edx, 2
0x14001ae75  test    r9d, eax
0x14001ae78  cmovz   edx, ecx
0x14001ae7b  mov     r11d, 1000h
0x14001ae81  mov     ecx, edx
0x14001ae83  or      ecx, 1
0x14001ae86  test    r11d, eax
0x14001ae89  cmovz   ecx, edx
0x14001ae8c  mov     esi, 100h
0x14001ae91  mov     edx, ecx
0x14001ae93  bts     edx, 13h
0x14001ae97  test    esi, eax
0x14001ae99  cmovz   edx, ecx
0x14001ae9c  mov     r15d, 6000h
0x14001aea2  and     eax, r15d
0x14001aea5  jz      short loc_14001AEC9
0x14001aea7  cmp     eax, 2000h
0x14001aeac  jz      short loc_14001AEC7
0x14001aeae  cmp     eax, 4000h
0x14001aeb3  jz      short loc_14001AEC2
0x14001aeb5  cmp     eax, r15d
0x14001aeb8  jnz     short loc_14001AEC9
0x14001aeba  or      edx, 300h
0x14001aec0  jmp     short loc_14001AEC9
0x14001aec2  or      edx, r14d
0x14001aec5  jmp     short loc_14001AEC9
0x14001aec7  or      edx, esi
0x14001aec9  and     r10d, 8040h
0x14001aed0  sub     r10d, 40h ; '@'
0x14001aed4  jz      short loc_14001AEF3
0x14001aed6  sub     r10d, 7FC0h
0x14001aedd  jz      short loc_14001AEEB
0x14001aedf  cmp     r10d, 40h ; '@'
0x14001aee3  jnz     short loc_14001AEF7
0x14001aee5  bts     edx, 18h
0x14001aee9  jmp     short loc_14001AEF7
0x14001aeeb  or      edx, 3000000h
0x14001aef1  jmp     short loc_14001AEF7
0x14001aef3  bts     edx, 19h
0x14001aef7  mov     r8d, r12d
0x14001aefa  not     r8d
0x14001aefd  and     r8d, edx
0x14001af00  and     ebx, r12d
0x14001af03  or      r8d, ebx
0x14001af06  cmp     r8d, edx
0x14001af09  jz      loc_14001B09B
0x14001af0f  mov     ecx, r8d
0x14001af12  and     ecx, 10h
0x14001af15  shl     ecx, 3
0x14001af18  mov     edx, ecx
0x14001af1a  or      edx, r14d
0x14001af1d  test    r8b, 8
0x14001af21  cmovz   edx, ecx
0x14001af24  mov     ecx, edx
0x14001af26  bts     ecx, 0Ah
0x14001af2a  test    r8b, 4
0x14001af2e  cmovz   ecx, edx
0x14001af31  mov     edx, ecx
0x14001af33  or      edx, r9d
0x14001af36  test    r8b, 2
0x14001af3a  cmovz   edx, ecx
0x14001af3d  mov     ecx, edx
0x14001af3f  or      ecx, r11d
0x14001af42  test    r8b, 1
0x14001af46  cmovz   ecx, edx
0x14001af49  mov     ebx, ecx
0x14001af4b  or      ebx, esi
0x14001af4d  bt      r8d, 13h
0x14001af52  cmovnb  ebx, ecx
0x14001af55  mov     eax, r8d
0x14001af58  and     eax, 300h
0x14001af5d  jz      short loc_14001AF82
0x14001af5f  cmp     eax, esi
0x14001af61  jz      short loc_14001AF7E
0x14001af63  cmp     eax, r14d
0x14001af66  jz      short loc_14001AF78
0x14001af68  mov     [rsp+38h+arg_0], ebx
0x14001af6c  cmp     eax, 300h
0x14001af71  jnz     short loc_14001AF86
0x14001af73  or      ebx, r15d
0x14001af76  jmp     short loc_14001AF82
0x14001af78  bts     ebx, 0Eh
0x14001af7c  jmp     short loc_14001AF82
0x14001af7e  bts     ebx, 0Dh
0x14001af82  mov     [rsp+38h+arg_0], ebx
0x14001af86  and     r8d, 3000000h
0x14001af8d  cmp     r8d, 1000000h
0x14001af94  jz      short loc_14001AFB3
0x14001af96  cmp     r8d, 2000000h
0x14001af9d  jz      short loc_14001AFAE
0x14001af9f  cmp     r8d, 3000000h
0x14001afa6  jnz     short loc_14001AFBD
0x14001afa8  bts     ebx, 0Fh
0x14001afac  jmp     short loc_14001AFB9
0x14001afae  or      ebx, 40h
0x14001afb1  jmp     short loc_14001AFB9
0x14001afb3  or      ebx, 8040h
0x14001afb9  mov     [rsp+38h+arg_0], ebx
0x14001afbd  cmp     cs:byte_1400D68D0, 0
0x14001afc4  jz      short loc_14001AFFC
0x14001afc6  test    bl, 40h
0x14001afc9  jz      short loc_14001AFFC
0x14001afcb  mov     ecx, ebx
0x14001afcd  call    set_fpsw_inline
0x14001afd2  jmp     short loc_14001B006
0x14001afd4  mov     cs:byte_1400D68D0, 0
0x14001afdb  mov     ebx, [rsp+38h+arg_0]
0x14001afdf  and     ebx, 0FFFFFFBFh
0x14001afe2  mov     ecx, ebx
0x14001afe4  call    set_fpsw_inline
0x14001afe9  mov     esi, 100h
0x14001afee  mov     r14d, 200h
0x14001aff4  mov     r15d, 6000h
0x14001affa  jmp     short loc_14001B006
0x14001affc  and     ebx, 0FFFFFFBFh
0x14001afff  mov     ecx, ebx
0x14001b001  call    set_fpsw_inline
0x14001b006  mov     ecx, ebx
0x14001b008  shr     ecx, 3
0x14001b00b  and     ecx, 10h
0x14001b00e  mov     edx, ecx
0x14001b010  or      edx, 8
0x14001b013  test    r14d, ebx
0x14001b016  cmovz   edx, ecx
0x14001b019  mov     ecx, edx
0x14001b01b  or      ecx, 4
0x14001b01e  bt      ebx, 0Ah
0x14001b022  cmovnb  ecx, edx
0x14001b025  mov     edx, ecx
0x14001b027  or      edx, 2
0x14001b02a  bt      ebx, 0Bh
0x14001b02e  cmovnb  edx, ecx
0x14001b031  mov     ecx, edx
0x14001b033  or      ecx, 1
0x14001b036  bt      ebx, 0Ch
0x14001b03a  cmovnb  ecx, edx
0x14001b03d  mov     edx, ecx
0x14001b03f  bts     edx, 13h
0x14001b043  test    esi, ebx
0x14001b045  cmovz   edx, ecx
0x14001b048  mov     eax, ebx
0x14001b04a  and     eax, r15d
0x14001b04d  jz      short loc_14001B071
0x14001b04f  cmp     eax, 2000h
0x14001b054  jz      short loc_14001B06F
0x14001b056  cmp     eax, 4000h
0x14001b05b  jz      short loc_14001B06A
0x14001b05d  cmp     eax, r15d
0x14001b060  jnz     short loc_14001B071
0x14001b062  or      edx, 300h
0x14001b068  jmp     short loc_14001B071
0x14001b06a  or      edx, r14d
0x14001b06d  jmp     short loc_14001B071
0x14001b06f  or      edx, esi
0x14001b071  and     ebx, 8040h
0x14001b077  sub     ebx, 40h ; '@'
0x14001b07a  jz      short loc_14001B097
0x14001b07c  sub     ebx, 7FC0h
0x14001b082  jz      short loc_14001B08F
0x14001b084  cmp     ebx, 40h ; '@'
0x14001b087  jnz     short loc_14001B09B
0x14001b089  bts     edx, 18h
0x14001b08d  jmp     short loc_14001B09B
0x14001b08f  or      edx, 3000000h
0x14001b095  jmp     short loc_14001B09B
0x14001b097  bts     edx, 19h
0x14001b09b  mov     eax, edx
0x14001b09d  mov     rbx, [rsp+38h+arg_8]
0x14001b0a2  mov     rsi, [rsp+38h+arg_10]
0x14001b0a7  add     rsp, 20h
0x14001b0ab  pop     r15
0x14001b0ad  pop     r14
0x14001b0af  pop     r12
0x14001b0b1  retn
0x1400ae396  push    rbp; Microsoft VisualC 64bit universal runtime
0x1400ae398  sub     rsp, 20h
0x1400ae39c  mov     rbp, rdx
0x1400ae39f  mov     rax, [rcx]
0x1400ae3a2  cmp     dword ptr [rax], 0C0000005h
0x1400ae3a8  jz      short loc_1400AE3B6
0x1400ae3aa  cmp     dword ptr [rax], 0C000001Dh
0x1400ae3b0  jz      short loc_1400AE3B6
0x1400ae3b2  xor     eax, eax
0x1400ae3b4  jmp     short loc_1400AE3BB
0x1400ae3b6  mov     eax, 1
0x1400ae3bb  add     rsp, 20h
0x1400ae3bf  pop     rbp
0x1400ae3c0  retn
```

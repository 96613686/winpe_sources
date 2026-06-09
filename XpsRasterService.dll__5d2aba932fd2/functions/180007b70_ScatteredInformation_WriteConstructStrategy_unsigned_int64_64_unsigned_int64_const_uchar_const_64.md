# ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])

- ea: `0x180007b70`
- end: `0x180007e2d`
- name: `??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z`
- size: `701`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b40`
- `0x18000c660`
- `0x18000d7e0`
- `0x18000dbb0`
- `0x18000e1d0`
- `0x18000e700`
- `0x1800108d0`
- `0x180011680`
- `0x180011b20`
- `0x180019db0`
- `0x18001a0a0`
- `0x18001e8d0`
- `0x1800224a0`
- `0x1800273b0`
- `0x180028710`
- `0x180031e00`
- `0x180036a30`
- `0x18003d450`
- `0x18003ddb0`
- `0x180042680`
- `0x1800445b0`
- `0x180044b90`
- `0x18004b7d0`
- `0x18004d430`

## callees

- `0x180007b70`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 result; // rax
  unsigned int v5; // edx

  v3 = *a2;
  result = 0;
  v5 = 2;
  do
  {
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 - 2 + a3)) )
      _bittestandset64(&result, v5 - 2);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 - 1 + a3)) )
      _bittestandset64(&result, v5 - 1);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + a3)) )
      _bittestandset64(&result, v5);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 1 + a3)) )
      _bittestandset64(&result, v5 + 1);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 2 + a3)) )
      _bittestandset64(&result, v5 + 2);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 3 + a3)) )
      _bittestandset64(&result, v5 + 3);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 4 + a3)) )
      _bittestandset64(&result, v5 + 4);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 5 + a3)) )
      _bittestandset64(&result, v5 + 5);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 6 + a3)) )
      _bittestandset64(&result, v5 + 6);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 7 + a3)) )
      _bittestandset64(&result, v5 + 7);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 8 + a3)) )
      _bittestandset64(&result, v5 + 8);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 9 + a3)) )
      _bittestandset64(&result, v5 + 9);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 10 + a3)) )
      _bittestandset64(&result, v5 + 10);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 11 + a3)) )
      _bittestandset64(&result, v5 + 11);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 12 + a3)) )
      _bittestandset64(&result, v5 + 12);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 13 + a3)) )
      _bittestandset64(&result, v5 + 13);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 14 + a3)) )
      _bittestandset64(&result, v5 + 14);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 15 + a3)) )
      _bittestandset64(&result, v5 + 15);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 16 + a3)) )
      _bittestandset64(&result, v5 + 16);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 17 + a3)) )
      _bittestandset64(&result, v5 + 17);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 18 + a3)) )
      _bittestandset64(&result, v5 + 18);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 19 + a3)) )
      _bittestandset64(&result, v5 + 19);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 20 + a3)) )
      _bittestandset64(&result, v5 + 20);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 21 + a3)) )
      _bittestandset64(&result, v5 + 21);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 22 + a3)) )
      _bittestandset64(&result, v5 + 22);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 23 + a3)) )
      _bittestandset64(&result, v5 + 23);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 24 + a3)) )
      _bittestandset64(&result, v5 + 24);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 25 + a3)) )
      _bittestandset64(&result, v5 + 25);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 26 + a3)) )
      _bittestandset64(&result, v5 + 26);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 27 + a3)) )
      _bittestandset64(&result, v5 + 27);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 28 + a3)) )
      _bittestandset64(&result, v5 + 28);
    if ( _bittest64(&v3, *(unsigned __int8 *)(v5 + 29 + a3)) )
      _bittestandset64(&result, v5 + 29);
    v5 += 32;
  }
  while ( v5 - 2 < 0x40 );
  return result;
}

```

## disassembly

```asm
0x180007b70  mov     r9, [rdx]
0x180007b73  xor     eax, eax
0x180007b75  mov     edx, 2
0x180007b7a  nop     word ptr [rax+rax+00h]
0x180007b80  lea     ecx, [rdx-2]
0x180007b83  mov     r10d, ecx
0x180007b86  movzx   ecx, byte ptr [rcx+r8]
0x180007b8b  bt      r9, rcx
0x180007b8f  jnb     short loc_180007B95
0x180007b91  bts     rax, r10
0x180007b95  lea     ecx, [rdx-1]
0x180007b98  mov     r10d, ecx
0x180007b9b  movzx   ecx, byte ptr [rcx+r8]
0x180007ba0  bt      r9, rcx
0x180007ba4  jnb     short loc_180007BAA
0x180007ba6  bts     rax, r10
0x180007baa  mov     r10d, edx
0x180007bad  movzx   ecx, byte ptr [r10+r8]
0x180007bb2  bt      r9, rcx
0x180007bb6  jnb     short loc_180007BBC
0x180007bb8  bts     rax, r10
0x180007bbc  lea     ecx, [rdx+1]
0x180007bbf  mov     r10d, ecx
0x180007bc2  movzx   ecx, byte ptr [rcx+r8]
0x180007bc7  bt      r9, rcx
0x180007bcb  jnb     short loc_180007BD1
0x180007bcd  bts     rax, r10
0x180007bd1  lea     ecx, [rdx+2]
0x180007bd4  mov     r10d, ecx
0x180007bd7  movzx   ecx, byte ptr [rcx+r8]
0x180007bdc  bt      r9, rcx
0x180007be0  jnb     short loc_180007BE6
0x180007be2  bts     rax, r10
0x180007be6  lea     ecx, [rdx+3]
0x180007be9  mov     r10d, ecx
0x180007bec  movzx   ecx, byte ptr [rcx+r8]
0x180007bf1  bt      r9, rcx
0x180007bf5  jnb     short loc_180007BFB
0x180007bf7  bts     rax, r10
0x180007bfb  lea     ecx, [rdx+4]
0x180007bfe  mov     r10d, ecx
0x180007c01  movzx   ecx, byte ptr [rcx+r8]
0x180007c06  bt      r9, rcx
0x180007c0a  jnb     short loc_180007C10
0x180007c0c  bts     rax, r10
0x180007c10  lea     ecx, [rdx+5]
0x180007c13  mov     r10d, ecx
0x180007c16  movzx   ecx, byte ptr [rcx+r8]
0x180007c1b  bt      r9, rcx
0x180007c1f  jnb     short loc_180007C25
0x180007c21  bts     rax, r10
0x180007c25  lea     ecx, [rdx+6]
0x180007c28  mov     r10d, ecx
0x180007c2b  movzx   ecx, byte ptr [rcx+r8]
0x180007c30  bt      r9, rcx
0x180007c34  jnb     short loc_180007C3A
0x180007c36  bts     rax, r10
0x180007c3a  lea     ecx, [rdx+7]
0x180007c3d  mov     r10d, ecx
0x180007c40  movzx   ecx, byte ptr [rcx+r8]
0x180007c45  bt      r9, rcx
0x180007c49  jnb     short loc_180007C4F
0x180007c4b  bts     rax, r10
0x180007c4f  lea     ecx, [rdx+8]
0x180007c52  mov     r10d, ecx
0x180007c55  movzx   ecx, byte ptr [rcx+r8]
0x180007c5a  bt      r9, rcx
0x180007c5e  jnb     short loc_180007C64
0x180007c60  bts     rax, r10
0x180007c64  lea     ecx, [rdx+9]
0x180007c67  mov     r10d, ecx
0x180007c6a  movzx   ecx, byte ptr [rcx+r8]
0x180007c6f  bt      r9, rcx
0x180007c73  jnb     short loc_180007C79
0x180007c75  bts     rax, r10
0x180007c79  lea     ecx, [rdx+0Ah]
0x180007c7c  mov     r10d, ecx
0x180007c7f  movzx   ecx, byte ptr [rcx+r8]
0x180007c84  bt      r9, rcx
0x180007c88  jnb     short loc_180007C8E
0x180007c8a  bts     rax, r10
0x180007c8e  lea     ecx, [rdx+0Bh]
0x180007c91  mov     r10d, ecx
0x180007c94  movzx   ecx, byte ptr [rcx+r8]
0x180007c99  bt      r9, rcx
0x180007c9d  jnb     short loc_180007CA3
0x180007c9f  bts     rax, r10
0x180007ca3  lea     ecx, [rdx+0Ch]
0x180007ca6  mov     r10d, ecx
0x180007ca9  movzx   ecx, byte ptr [rcx+r8]
0x180007cae  bt      r9, rcx
0x180007cb2  jnb     short loc_180007CB8
0x180007cb4  bts     rax, r10
0x180007cb8  lea     ecx, [rdx+0Dh]
0x180007cbb  mov     r10d, ecx
0x180007cbe  movzx   ecx, byte ptr [rcx+r8]
0x180007cc3  bt      r9, rcx
0x180007cc7  jnb     short loc_180007CCD
0x180007cc9  bts     rax, r10
0x180007ccd  lea     ecx, [rdx+0Eh]
0x180007cd0  mov     r10d, ecx
0x180007cd3  movzx   ecx, byte ptr [rcx+r8]
0x180007cd8  bt      r9, rcx
0x180007cdc  jnb     short loc_180007CE2
0x180007cde  bts     rax, r10
0x180007ce2  lea     ecx, [rdx+0Fh]
0x180007ce5  mov     r10d, ecx
0x180007ce8  movzx   ecx, byte ptr [rcx+r8]
0x180007ced  bt      r9, rcx
0x180007cf1  jnb     short loc_180007CF7
0x180007cf3  bts     rax, r10
0x180007cf7  lea     ecx, [rdx+10h]
0x180007cfa  mov     r10d, ecx
0x180007cfd  movzx   ecx, byte ptr [rcx+r8]
0x180007d02  bt      r9, rcx
0x180007d06  jnb     short loc_180007D0C
0x180007d08  bts     rax, r10
0x180007d0c  lea     ecx, [rdx+11h]
0x180007d0f  mov     r10d, ecx
0x180007d12  movzx   ecx, byte ptr [rcx+r8]
0x180007d17  bt      r9, rcx
0x180007d1b  jnb     short loc_180007D21
0x180007d1d  bts     rax, r10
0x180007d21  lea     ecx, [rdx+12h]
0x180007d24  mov     r10d, ecx
0x180007d27  movzx   ecx, byte ptr [rcx+r8]
0x180007d2c  bt      r9, rcx
0x180007d30  jnb     short loc_180007D36
0x180007d32  bts     rax, r10
0x180007d36  lea     ecx, [rdx+13h]
0x180007d39  mov     r10d, ecx
0x180007d3c  movzx   ecx, byte ptr [rcx+r8]
0x180007d41  bt      r9, rcx
0x180007d45  jnb     short loc_180007D4B
0x180007d47  bts     rax, r10
0x180007d4b  lea     ecx, [rdx+14h]
0x180007d4e  mov     r10d, ecx
0x180007d51  movzx   ecx, byte ptr [rcx+r8]
0x180007d56  bt      r9, rcx
0x180007d5a  jnb     short loc_180007D60
0x180007d5c  bts     rax, r10
0x180007d60  lea     ecx, [rdx+15h]
0x180007d63  mov     r10d, ecx
0x180007d66  movzx   ecx, byte ptr [rcx+r8]
0x180007d6b  bt      r9, rcx
0x180007d6f  jnb     short loc_180007D75
0x180007d71  bts     rax, r10
0x180007d75  lea     ecx, [rdx+16h]
0x180007d78  mov     r10d, ecx
0x180007d7b  movzx   ecx, byte ptr [rcx+r8]
0x180007d80  bt      r9, rcx
0x180007d84  jnb     short loc_180007D8A
0x180007d86  bts     rax, r10
0x180007d8a  lea     ecx, [rdx+17h]
0x180007d8d  mov     r10d, ecx
0x180007d90  movzx   ecx, byte ptr [rcx+r8]
0x180007d95  bt      r9, rcx
0x180007d99  jnb     short loc_180007D9F
0x180007d9b  bts     rax, r10
0x180007d9f  lea     ecx, [rdx+18h]
0x180007da2  mov     r10d, ecx
0x180007da5  movzx   ecx, byte ptr [rcx+r8]
0x180007daa  bt      r9, rcx
0x180007dae  jnb     short loc_180007DB4
0x180007db0  bts     rax, r10
0x180007db4  lea     ecx, [rdx+19h]
0x180007db7  mov     r10d, ecx
0x180007dba  movzx   ecx, byte ptr [rcx+r8]
0x180007dbf  bt      r9, rcx
0x180007dc3  jnb     short loc_180007DC9
0x180007dc5  bts     rax, r10
0x180007dc9  lea     ecx, [rdx+1Ah]
0x180007dcc  mov     r10d, ecx
0x180007dcf  movzx   ecx, byte ptr [rcx+r8]
0x180007dd4  bt      r9, rcx
0x180007dd8  jnb     short loc_180007DDE
0x180007dda  bts     rax, r10
0x180007dde  lea     ecx, [rdx+1Bh]
0x180007de1  mov     r10d, ecx
0x180007de4  movzx   ecx, byte ptr [rcx+r8]
0x180007de9  bt      r9, rcx
0x180007ded  jnb     short loc_180007DF3
0x180007def  bts     rax, r10
0x180007df3  lea     ecx, [rdx+1Ch]
0x180007df6  mov     r10d, ecx
0x180007df9  movzx   ecx, byte ptr [rcx+r8]
0x180007dfe  bt      r9, rcx
0x180007e02  jnb     short loc_180007E08
0x180007e04  bts     rax, r10
0x180007e08  lea     ecx, [rdx+1Dh]
0x180007e0b  mov     r10d, ecx
0x180007e0e  movzx   ecx, byte ptr [rcx+r8]
0x180007e13  bt      r9, rcx
0x180007e17  jnb     short loc_180007E1D
0x180007e19  bts     rax, r10
0x180007e1d  add     edx, 20h ; ' '
0x180007e20  lea     ecx, [rdx-2]
0x180007e23  cmp     ecx, 40h ; '@'
0x180007e26  jb      loc_180007B80
0x180007e2c  retn
```

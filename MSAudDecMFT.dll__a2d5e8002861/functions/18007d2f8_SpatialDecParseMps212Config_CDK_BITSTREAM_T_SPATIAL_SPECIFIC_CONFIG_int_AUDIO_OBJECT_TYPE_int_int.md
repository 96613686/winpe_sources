# SpatialDecParseMps212Config(CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG *,int,AUDIO_OBJECT_TYPE,int,int)

- ea: `0x18007d2f8`
- end: `0x18007d4ee`
- name: `?SpatialDecParseMps212Config@@YA?AW4SACDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@HW4AUDIO_OBJECT_TYPE@@HH@Z`
- size: `502`
- prototype: `enum SACDEC_ERROR __high(struct CDK_BITSTREAM *, struct T_SPATIAL_SPECIFIC_CONFIG *, int, enum AUDIO_OBJECT_TYPE, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800723b4`

## callees

- `0x1800110c0`
- `0x18004dd14`
- `0x18007ca70`
- `0x18007d2f8`

## pseudocode

```c
__int64 __fastcall SpatialDecParseMps212Config(_DWORD *a1, __int64 a2, int a3, int a4, int a5, int a6)
{
  __int64 v10; // r8
  int v11; // ecx
  __int64 v12; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  char v21; // al
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  __int64 v25; // r8
  char v26; // al
  bool v27; // zf
  int v28; // ecx
  __int64 v29; // rax

  memset_0((void *)a2, 0, 0xC0u);
  *(_BYTE *)(a2 + 164) = a5;
  *(_BYTE *)(a2 + 165) = a6;
  v11 = *((unsigned __int8 *)&freqResTable + (unsigned int)CDKreadBits(a1, 3, v10));
  *(_DWORD *)(a2 + 12) = v11;
  if ( !v11 )
    return 4294966314LL;
  if ( a4 != 42 )
    return 4294966303LL;
  *(_DWORD *)(a2 + 32) = CDKreadBits(a1, 3, v12);
  *(_DWORD *)(a2 + 36) = CDKreadBits(a1, 2, v14);
  v16 = CDKreadBits(a1, 2, v15);
  *(_DWORD *)(a2 + 40) = v16;
  if ( v16 > 2 )
    return 4294966314LL;
  v18 = 64;
  *(_BYTE *)(a2 + 167) = 0;
  if ( a6 != 4 )
    v18 = 32;
  *(_DWORD *)(a2 + 8) = v18;
  *(_BYTE *)(a2 + 166) = CDKreadBits(a1, 1, v17);
  *(_BYTE *)(a2 + 169) = CDKreadBits(a1, 1, v19);
  v21 = CDKreadBits(a1, 1, v20);
  *(_BYTE *)(a2 + 170) = v21;
  if ( v21 )
  {
    v23 = CDKreadBits(a1, 5, v22);
    *(_DWORD *)(a2 + 172) = v23;
    if ( v23 > 28 )
      return 4294966314LL;
  }
  else
  {
    *(_DWORD *)(a2 + 172) = 0;
  }
  if ( a5 <= 1 )
  {
    *(_DWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 80) = 0;
  }
  else
  {
    *(_DWORD *)(a2 + 28) = 1;
    *(_DWORD *)(a2 + 80) = 1;
    v24 = CDKreadBits(a1, 5, v22);
    *(_DWORD *)(a2 + 84) = v24;
    if ( *(_DWORD *)(a2 + 12) < v24 )
      return 4294966314LL;
    if ( *(_DWORD *)(a2 + 172) > v24 )
      v24 = *(_DWORD *)(a2 + 172);
    *(_DWORD *)(a2 + 172) = v24;
    v26 = CDKreadBits(a1, 1, v25);
    v27 = *(_BYTE *)(a2 + 169) == 0;
    *(_BYTE *)(a2 + 168) = v26;
    if ( !v27 )
      *(_BYTE *)(a2 + 169) = 3;
  }
  if ( *(_DWORD *)(a2 + 36) == 2 )
    *(_DWORD *)(a2 + 156) = CDKreadBits(a1, 1, v22);
  *(_DWORD *)(a2 + 4) = a3;
  v28 = 0;
  *(_DWORD *)(a2 + 16) = 7;
  *(_DWORD *)(a2 + 52) = 1;
  *(_DWORD *)(a2 + 44) = 1;
  *(_DWORD *)(a2 + 48) = 2;
  *(_DWORD *)(a2 + 24) = 0;
  do
  {
    v29 = v28++;
    *(_DWORD *)(a2 + 4 * v29 + 56) = 0;
  }
  while ( v28 < *(_DWORD *)(a2 + 52) );
  *(_DWORD *)(a2 + 160) = 42;
  SpatialDecDecodeHelperInfo(a2);
  return 0;
}

```

## disassembly

```asm
0x18007d2f8  push    rbx
0x18007d2fa  push    rbp
0x18007d2fb  push    rsi
0x18007d2fc  push    rdi
0x18007d2fd  push    r14
0x18007d2ff  push    r15
0x18007d301  sub     rsp, 28h
0x18007d305  mov     rbx, rdx
0x18007d308  mov     r15d, r8d
0x18007d30b  mov     rdi, rcx
0x18007d30e  xor     edx, edx; Val
0x18007d310  mov     rcx, rbx; void *
0x18007d313  mov     r8d, 0C0h; Size
0x18007d319  mov     esi, r9d
0x18007d31c  call    memset_0
0x18007d321  mov     ebp, [rsp+58h+arg_20]
0x18007d328  mov     edx, 3
0x18007d32d  mov     r14d, [rsp+58h+arg_28]
0x18007d335  mov     rcx, rdi
0x18007d338  mov     [rbx+0A4h], bpl
0x18007d33f  mov     [rbx+0A5h], r14b
0x18007d346  call    CDKreadBits
0x18007d34b  mov     eax, eax
0x18007d34d  lea     rcx, ?freqResTable@@3QBEB; uchar const near * const freqResTable
0x18007d354  movzx   ecx, byte ptr [rax+rcx]
0x18007d358  mov     [rbx+0Ch], ecx
0x18007d35b  test    ecx, ecx
0x18007d35d  jz      loc_18007D411
0x18007d363  cmp     esi, 2Ah ; '*'
0x18007d366  jz      short loc_18007D372
0x18007d368  mov     eax, 0FFFFFC1Fh
0x18007d36d  jmp     loc_18007D416
0x18007d372  mov     edx, 3
0x18007d377  mov     rcx, rdi
0x18007d37a  call    CDKreadBits
0x18007d37f  mov     edx, 2
0x18007d384  mov     [rbx+20h], eax
0x18007d387  mov     rcx, rdi
0x18007d38a  call    CDKreadBits
0x18007d38f  mov     edx, 2
0x18007d394  mov     [rbx+24h], eax
0x18007d397  mov     rcx, rdi
0x18007d39a  call    CDKreadBits
0x18007d39f  mov     [rbx+28h], eax
0x18007d3a2  cmp     eax, 2
0x18007d3a5  jg      short loc_18007D411
0x18007d3a7  mov     eax, 40h ; '@'
0x18007d3ac  mov     byte ptr [rbx+0A7h], 0
0x18007d3b3  cmp     r14d, 4
0x18007d3b7  lea     ecx, [rax-20h]
0x18007d3ba  lea     esi, [rcx-1Fh]
0x18007d3bd  cmovnz  eax, ecx
0x18007d3c0  mov     edx, esi
0x18007d3c2  mov     [rbx+8], eax
0x18007d3c5  mov     rcx, rdi
0x18007d3c8  call    CDKreadBits
0x18007d3cd  mov     edx, esi
0x18007d3cf  mov     [rbx+0A6h], al
0x18007d3d5  mov     rcx, rdi
0x18007d3d8  call    CDKreadBits
0x18007d3dd  mov     edx, esi
0x18007d3df  mov     [rbx+0A9h], al
0x18007d3e5  mov     rcx, rdi
0x18007d3e8  call    CDKreadBits
0x18007d3ed  mov     [rbx+0AAh], al
0x18007d3f3  lea     r14d, [rsi+4]
0x18007d3f7  test    al, al
0x18007d3f9  jz      short loc_18007D424
0x18007d3fb  mov     edx, r14d
0x18007d3fe  mov     rcx, rdi
0x18007d401  call    CDKreadBits
0x18007d406  mov     [rbx+0ACh], eax
0x18007d40c  cmp     eax, 1Ch
0x18007d40f  jle     short loc_18007D42E
0x18007d411  mov     eax, 0FFFFFC2Ah
0x18007d416  add     rsp, 28h
0x18007d41a  pop     r15
0x18007d41c  pop     r14
0x18007d41e  pop     rdi
0x18007d41f  pop     rsi
0x18007d420  pop     rbp
0x18007d421  pop     rbx
0x18007d422  retn
0x18007d424  mov     dword ptr [rbx+0ACh], 0
0x18007d42e  cmp     ebp, esi
0x18007d430  jle     short loc_18007D47E
0x18007d432  mov     edx, r14d
0x18007d435  mov     [rbx+1Ch], esi
0x18007d438  mov     rcx, rdi
0x18007d43b  mov     [rbx+50h], esi
0x18007d43e  call    CDKreadBits
0x18007d443  mov     [rbx+54h], eax
0x18007d446  cmp     [rbx+0Ch], eax
0x18007d449  jl      short loc_18007D411
0x18007d44b  mov     ecx, [rbx+0ACh]
0x18007d451  mov     edx, esi
0x18007d453  cmp     ecx, eax
0x18007d455  cmovg   eax, ecx
0x18007d458  mov     rcx, rdi
0x18007d45b  mov     [rbx+0ACh], eax
0x18007d461  call    CDKreadBits
0x18007d466  cmp     byte ptr [rbx+0A9h], 0
0x18007d46d  mov     [rbx+0A8h], al
0x18007d473  jz      short loc_18007D48C
0x18007d475  mov     byte ptr [rbx+0A9h], 3
0x18007d47c  jmp     short loc_18007D48C
0x18007d47e  mov     dword ptr [rbx+1Ch], 0
0x18007d485  mov     dword ptr [rbx+50h], 0
0x18007d48c  cmp     dword ptr [rbx+24h], 2
0x18007d490  jnz     short loc_18007D4A2
0x18007d492  mov     edx, esi
0x18007d494  mov     rcx, rdi
0x18007d497  call    CDKreadBits
0x18007d49c  mov     [rbx+9Ch], eax
0x18007d4a2  mov     [rbx+4], r15d
0x18007d4a6  xor     ecx, ecx
0x18007d4a8  mov     dword ptr [rbx+10h], 7
0x18007d4af  mov     [rbx+34h], esi
0x18007d4b2  mov     [rbx+2Ch], esi
0x18007d4b5  mov     dword ptr [rbx+30h], 2
0x18007d4bc  mov     dword ptr [rbx+18h], 0
0x18007d4c3  movsxd  rax, ecx
0x18007d4c6  add     ecx, esi
0x18007d4c8  mov     dword ptr [rbx+rax*4+38h], 0
0x18007d4d0  cmp     ecx, [rbx+34h]
0x18007d4d3  jl      short loc_18007D4C3
0x18007d4d5  mov     rcx, rbx
0x18007d4d8  mov     dword ptr [rbx+0A0h], 2Ah ; '*'
0x18007d4e2  call    SpatialDecDecodeHelperInfo
0x18007d4e7  xor     eax, eax
0x18007d4e9  jmp     loc_18007D416
```

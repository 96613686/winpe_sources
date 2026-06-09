# LibRaw::recycle(void)

- ea: `0x180006bc0`
- end: `0x18000723b`
- name: `?recycle@LibRaw@@QEAAXXZ`
- size: `1659`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `18`
- callee_count: `6`
- tags: ``

## callers

- `0x180006b00`
- `0x18000adf0`
- `0x1800a5344`
- `0x1800a8588`
- `0x1800abf54`
- `0x1800b1490`
- `0x1800b14b8`
- `0x1800b15fc`
- `0x1800b1630`
- `0x1800b1655`
- `0x1800b1780`
- `0x1800b18d0`
- `0x1800b1930`
- `0x1800b1990`
- `0x1800b19b5`
- `0x1800b1ad8`
- `0x1800b1b10`
- `0x1800b1e10`

## callees

- `0x180005cd3`
- `0x180006bc0`
- `0x180009220`
- `0x180009aa0`
- `0x180026310`
- `0x1800b0b00`

## pseudocode

```c
void __fastcall LibRaw::recycle(LibRaw *this)
{
  void *v2; // rdx
  void *v3; // rdx
  void *v4; // rdx
  void *v5; // rdx
  void *v6; // rdx
  void *v7; // rdx
  void *v8; // rdx
  void *v9; // rdx
  void *v10; // rdx
  void *v11; // rdx
  void *v12; // rdx
  void *v13; // rdx
  void *v14; // rdx
  void *v15; // rdx
  __int64 i; // rdi
  void *v17; // rcx
  __int64 v18; // rax

  LibRaw::recycle_datastream(this);
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    LibRaw::free(this, v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 600);
  if ( v3 )
  {
    LibRaw::free(this, v3);
    *((_QWORD *)this + 600) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 603);
  if ( v4 )
  {
    LibRaw::free(this, v4);
    *((_QWORD *)this + 603) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 606);
  if ( v5 )
  {
    LibRaw::free(this, v5);
    *((_QWORD *)this + 606) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 609);
  if ( v6 )
  {
    LibRaw::free(this, v6);
    *((_QWORD *)this + 609) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 24155);
  if ( v7 )
  {
    LibRaw::free(this, v7);
    *((_QWORD *)this + 24155) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 47662);
  if ( v8 )
  {
    LibRaw::free(this, v8);
    *((_QWORD *)this + 47662) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 47669);
  if ( v9 )
  {
    LibRaw::free(this, v9);
    *((_QWORD *)this + 47669) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 47670);
  if ( v10 )
  {
    LibRaw::free(this, v10);
    *((_QWORD *)this + 47670) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 19207);
  if ( v11 )
  {
    LibRaw::free(this, v11);
    *((_QWORD *)this + 19207) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 24196);
  if ( v12 )
  {
    LibRaw::free(this, v12);
    *((_QWORD *)this + 24196) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 24197);
  if ( v13 )
  {
    LibRaw::free(this, v13);
    *((_QWORD *)this + 24197) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 24189);
  if ( v14 )
  {
    LibRaw::free(this, v14);
    *((_QWORD *)this + 24189) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 79);
  if ( v15 )
  {
    LibRaw::free(this, v15);
    *((_QWORD *)this + 79) = 0;
  }
  LibRaw::parseCR3_Free(this);
  memset((char *)this + 16, 0, 0xB8u);
  *(_DWORD *)((char *)this + 190) = -1;
  *(_DWORD *)((char *)this + 182) = -1;
  memset((char *)this + 200, 0, 0x1B8u);
  memset((char *)this + 5392, 0, 0x24358u);
  memset((char *)this + 153706, 0, 0xA6u);
  memset((char *)this + 153874, 0, 0x811Au);
  *(_OWORD *)((char *)this + 186940) = 0;
  memset((char *)this + 186964, 0, 0x1554u);
  memset((char *)this + 640, 0, 0x510u);
  *(_OWORD *)((char *)this + 192424) = 0;
  *(_OWORD *)((char *)this + 192440) = 0;
  *(_OWORD *)((char *)this + 192456) = 0;
  *(_OWORD *)((char *)this + 192472) = 0;
  *(_OWORD *)((char *)this + 192488) = 0;
  *(_OWORD *)((char *)this + 192504) = 0;
  *(_OWORD *)((char *)this + 192520) = 0;
  *(_OWORD *)((char *)this + 192536) = 0;
  *(_OWORD *)((char *)this + 192552) = 0;
  *((_QWORD *)this + 24071) = 0;
  *((_DWORD *)this + 48144) = 0;
  memset((char *)this + 192625, 0, 0x257u);
  memset((char *)this + 193512, 0, 0x2DD60u);
  *(_OWORD *)((char *)this + 4902) = 0;
  *(_OWORD *)((char *)this + 4918) = 0;
  *(_OWORD *)((char *)this + 4934) = 0;
  *(_OWORD *)((char *)this + 4950) = 0;
  *(_OWORD *)((char *)this + 4966) = 0;
  *(_OWORD *)((char *)this + 4982) = 0;
  *(_OWORD *)((char *)this + 4998) = 0;
  *(_OWORD *)((char *)this + 5014) = 0;
  *(_OWORD *)((char *)this + 193224) = 0;
  *((_QWORD *)this + 24155) = 0;
  memset((char *)this + 193248, 0, 0x108u);
  memset((char *)this + 1936, 0, 0xB88u);
  *(_QWORD *)((char *)this + 192604) = 0;
  *((_QWORD *)this + 24074) = 0;
  *(_QWORD *)((char *)this + 192580) = 0;
  *(_QWORD *)((char *)this + 192612) = 0;
  *((_DWORD *)this + 48150) = 0;
  *((_DWORD *)this + 48147) = 0;
  *(_DWORD *)((char *)this + 192621) = 0;
  *((_BYTE *)this + 192620) = 0;
  memset((char *)this + 381272, 0, 0x9C8u);
  *((_WORD *)this + 76936) = -1;
  *((_WORD *)this + 76852) = -1;
  *((_QWORD *)this + 150) = -1;
  *((_QWORD *)this + 611) = -1;
  *((_WORD *)this + 2450) = -1;
  *((_WORD *)this + 964) = 1;
  *((_DWORD *)this + 1224) = -1;
  *((_DWORD *)this + 46739) = -998653952;
  *((_DWORD *)this + 46740) = 1065353216;
  *((_DWORD *)this + 46731) = 1065353216;
  *((_DWORD *)this + 46732) = 1065353216;
  *((_DWORD *)this + 46733) = 1065353216;
  *((_DWORD *)this + 46734) = 1065353216;
  *((_DWORD *)this + 515) = -1;
  *((_DWORD *)this + 511) = 3;
  *((_WORD *)this + 1383) = -1;
  *((_QWORD *)this + 339) = -998653952;
  *((_QWORD *)this + 340) = -1;
  *((_QWORD *)this + 342) = -1;
  *(_QWORD *)((char *)this + 2748) = -1;
  *(_QWORD *)((char *)this + 2756) = -1;
  *((_QWORD *)this + 373) = -998653952;
  *((_DWORD *)this + 745) = -998653952;
  *(_QWORD *)((char *)this + 2596) = -1;
  *((_WORD *)this + 1510) = -1;
  *((_WORD *)this + 1410) = -1;
  *((_QWORD *)this + 371) = -1;
  *((_DWORD *)this + 744) = -1;
  *((_DWORD *)this + 895) = -1;
  *((_DWORD *)this + 954) = 1065353216;
  *((_DWORD *)this + 569) = -1;
  *((_DWORD *)this + 756) = -1;
  *((_WORD *)this + 1664) = -1;
  *((_BYTE *)this + 3330) = -1;
  *((_DWORD *)this + 833) = -2147450880;
  *(_QWORD *)((char *)this + 3340) = -1;
  *((_WORD *)this + 1668) = 0x8000;
  *(_QWORD *)((char *)this + 3348) = -1;
  *((_QWORD *)this + 420) = 0xC08F380000000000uLL;
  *((_DWORD *)this + 839) = -1;
  *((_DWORD *)this + 842) = -1;
  *(_QWORD *)((char *)this + 3372) = -1;
  *((_DWORD *)this + 972) = -1;
  *((_DWORD *)this + 974) = -1;
  *(_DWORD *)((char *)this + 3902) = -1;
  *((_DWORD *)this + 978) = -1;
  *((_BYTE *)this + 3920) = -1;
  *((_WORD *)this + 2188) = -1;
  *((_WORD *)this + 2198) = -1;
  *((_QWORD *)this + 552) = -1;
  *((_DWORD *)this + 1106) = -1;
  *((_QWORD *)this + 554) = 0xC08F380000000000uLL;
  *((_QWORD *)this + 555) = 0xC08F380000000000uLL;
  *((_QWORD *)this + 560) = -1;
  *((_WORD *)this + 1700) = -1;
  *((_WORD *)this + 1733) = 0;
  *(_QWORD *)((char *)this + 3470) = -1;
  *((_WORD *)this + 1744) = -1;
  *((_DWORD *)this + 874) = -1;
  *((_DWORD *)this + 870) = -1;
  *(_DWORD *)((char *)this + 3550) = -1;
  *((_BYTE *)this + 3417) = -1;
  *(_QWORD *)((char *)this + 3418) = -1;
  *((_BYTE *)this + 3438) = -1;
  *((_DWORD *)this + 862) = -8388609;
  *((_DWORD *)this + 864) = -1;
  *((_DWORD *)this + 889) = -1;
  *((_WORD *)this + 1730) = -1;
  *((_WORD *)this + 1777) = -1;
  *((_BYTE *)this + 3452) = -1;
  *((_DWORD *)this + 191806) = 0;
  for ( i = 0; i < 4096; i += 8 )
  {
    v17 = *(void **)(i + *((_QWORD *)this + 95878));
    if ( v17 )
    {
      free_0(v17);
      *(_QWORD *)(i + *((_QWORD *)this + 95878)) = 0;
    }
  }
  *((_DWORD *)this + 48306) = 0;
  *((_DWORD *)this + 95375) = 0;
  *((_DWORD *)this + 1346) = 0;
  *((_QWORD *)this + 95898) = 0;
  v18 = *((_QWORD *)this + 47658);
  *(_QWORD *)v18 = 0;
  *(_DWORD *)(v18 + 8) = 0;
  *(_QWORD *)(v18 + 16) = 0;
  *(_DWORD *)(v18 + 24) = 0;
  *(_DWORD *)(v18 + 16936) = 0;
  *(_DWORD *)(v18 + 21040) = -1073741824;
}

```

## disassembly

```asm
0x180006bc0  mov     [rsp+arg_0], rbx
0x180006bc5  mov     [rsp+arg_8], rbp
0x180006bca  mov     [rsp+arg_10], rsi
0x180006bcf  mov     [rsp+arg_18], rdi
0x180006bd4  push    r14
0x180006bd6  sub     rsp, 20h
0x180006bda  mov     rbx, rcx
0x180006bdd  call    ?recycle_datastream@LibRaw@@QEAAXXZ; LibRaw::recycle_datastream(void)
0x180006be2  mov     rdx, [rbx+8]; void *
0x180006be6  xor     r14d, r14d
0x180006be9  test    rdx, rdx
0x180006bec  jz      short loc_180006BFA
0x180006bee  mov     rcx, rbx; this
0x180006bf1  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006bf6  mov     [rbx+8], r14
0x180006bfa  mov     rdx, [rbx+12C0h]; void *
0x180006c01  test    rdx, rdx
0x180006c04  jz      short loc_180006C15
0x180006c06  mov     rcx, rbx; this
0x180006c09  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006c0e  mov     [rbx+12C0h], r14
0x180006c15  mov     rdx, [rbx+12D8h]; void *
0x180006c1c  test    rdx, rdx
0x180006c1f  jz      short loc_180006C30
0x180006c21  mov     rcx, rbx; this
0x180006c24  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006c29  mov     [rbx+12D8h], r14
0x180006c30  mov     rdx, [rbx+12F0h]; void *
0x180006c37  test    rdx, rdx
0x180006c3a  jz      short loc_180006C4B
0x180006c3c  mov     rcx, rbx; this
0x180006c3f  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006c44  mov     [rbx+12F0h], r14
0x180006c4b  mov     rdx, [rbx+1308h]; void *
0x180006c52  test    rdx, rdx
0x180006c55  jz      short loc_180006C66
0x180006c57  mov     rcx, rbx; this
0x180006c5a  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006c5f  mov     [rbx+1308h], r14
0x180006c66  mov     rdx, [rbx+2F2D8h]; void *
0x180006c6d  test    rdx, rdx
0x180006c70  jz      short loc_180006C81
0x180006c72  mov     rcx, rbx; this
0x180006c75  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006c7a  mov     [rbx+2F2D8h], r14
0x180006c81  mov     rdx, [rbx+5D170h]; void *
0x180006c88  test    rdx, rdx
0x180006c8b  jz      short loc_180006C9C
0x180006c8d  mov     rcx, rbx; this
0x180006c90  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006c95  mov     [rbx+5D170h], r14
0x180006c9c  mov     rdx, [rbx+5D1A8h]; void *
0x180006ca3  test    rdx, rdx
0x180006ca6  jz      short loc_180006CB7
0x180006ca8  mov     rcx, rbx; this
0x180006cab  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006cb0  mov     [rbx+5D1A8h], r14
0x180006cb7  mov     rdx, [rbx+5D1B0h]; void *
0x180006cbe  test    rdx, rdx
0x180006cc1  jz      short loc_180006CD2
0x180006cc3  mov     rcx, rbx; this
0x180006cc6  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006ccb  mov     [rbx+5D1B0h], r14
0x180006cd2  mov     rdx, [rbx+25838h]; void *
0x180006cd9  test    rdx, rdx
0x180006cdc  jz      short loc_180006CED
0x180006cde  mov     rcx, rbx; this
0x180006ce1  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006ce6  mov     [rbx+25838h], r14
0x180006ced  mov     rdx, [rbx+2F420h]; void *
0x180006cf4  test    rdx, rdx
0x180006cf7  jz      short loc_180006D08
0x180006cf9  mov     rcx, rbx; this
0x180006cfc  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006d01  mov     [rbx+2F420h], r14
0x180006d08  mov     rdx, [rbx+2F428h]; void *
0x180006d0f  test    rdx, rdx
0x180006d12  jz      short loc_180006D23
0x180006d14  mov     rcx, rbx; this
0x180006d17  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006d1c  mov     [rbx+2F428h], r14
0x180006d23  mov     rdx, [rbx+2F3E8h]; void *
0x180006d2a  test    rdx, rdx
0x180006d2d  jz      short loc_180006D3E
0x180006d2f  mov     rcx, rbx; this
0x180006d32  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006d37  mov     [rbx+2F3E8h], r14
0x180006d3e  mov     rdx, [rbx+278h]; void *
0x180006d45  test    rdx, rdx
0x180006d48  jz      short loc_180006D59
0x180006d4a  mov     rcx, rbx; this
0x180006d4d  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180006d52  mov     [rbx+278h], r14
0x180006d59  mov     rcx, rbx; this
0x180006d5c  call    ?parseCR3_Free@LibRaw@@IEAAXXZ; LibRaw::parseCR3_Free(void)
0x180006d61  lea     rcx, [rbx+10h]; void *
0x180006d65  xor     edx, edx; Val
0x180006d67  mov     r8d, 0B8h; Size
0x180006d6d  call    memset
0x180006d72  lea     rcx, [rbx+0C8h]; void *
0x180006d79  mov     dword ptr [rbx+0BEh], 0FFFFFFFFh
0x180006d83  xor     edx, edx; Val
0x180006d85  mov     dword ptr [rbx+0B6h], 0FFFFFFFFh
0x180006d8f  mov     r8d, 1B8h; Size
0x180006d95  mov     ebp, 0FFFFh
0x180006d9a  call    memset
0x180006d9f  lea     rcx, [rbx+1510h]; void *
0x180006da6  xor     edx, edx; Val
0x180006da8  mov     r8d, 24358h; Size
0x180006dae  call    memset
0x180006db3  lea     rcx, [rbx+2586Ah]; void *
0x180006dba  xor     edx, edx; Val
0x180006dbc  mov     r8d, 0A6h; Size
0x180006dc2  call    memset
0x180006dc7  lea     rcx, [rbx+25912h]; void *
0x180006dce  xor     edx, edx; Val
0x180006dd0  mov     r8d, 811Ah; Size
0x180006dd6  call    memset
0x180006ddb  xorps   xmm0, xmm0
0x180006dde  lea     rcx, [rbx+2DA54h]; void *
0x180006de5  xor     edx, edx; Val
0x180006de7  mov     r8d, 1554h; Size
0x180006ded  movups  xmmword ptr [rbx+2DA3Ch], xmm0
0x180006df4  call    memset
0x180006df9  lea     rcx, [rbx+280h]; void *
0x180006e00  xor     edx, edx; Val
0x180006e02  mov     r8d, 510h; Size
0x180006e08  call    memset
0x180006e0d  xorps   xmm0, xmm0
0x180006e10  lea     rcx, [rbx+2F071h]; void *
0x180006e17  movups  xmmword ptr [rbx+2EFA8h], xmm0
0x180006e1e  xor     eax, eax
0x180006e20  xor     edx, edx; Val
0x180006e22  movups  xmmword ptr [rbx+2EFB8h], xmm0
0x180006e29  mov     r8d, 257h; Size
0x180006e2f  movups  xmmword ptr [rbx+2EFC8h], xmm0
0x180006e36  movups  xmmword ptr [rbx+2EFD8h], xmm0
0x180006e3d  movups  xmmword ptr [rbx+2EFE8h], xmm0
0x180006e44  movups  xmmword ptr [rbx+2EFF8h], xmm0
0x180006e4b  movups  xmmword ptr [rbx+2F008h], xmm0
0x180006e52  movups  xmmword ptr [rbx+2F018h], xmm0
0x180006e59  movups  xmmword ptr [rbx+2F028h], xmm0
0x180006e60  mov     [rbx+2F038h], rax
0x180006e67  mov     [rbx+2F040h], eax
0x180006e6d  call    memset
0x180006e72  xor     edx, edx; Val
0x180006e74  lea     rcx, [rbx+2F3E8h]; void *
0x180006e7b  mov     r8d, 2DD60h; Size
0x180006e81  call    memset
0x180006e86  xorps   xmm0, xmm0
0x180006e89  lea     rcx, [rbx+2F2E0h]; void *
0x180006e90  movups  xmmword ptr [rbx+1326h], xmm0
0x180006e97  xor     eax, eax
0x180006e99  xor     edx, edx; Val
0x180006e9b  movups  xmmword ptr [rbx+1336h], xmm0
0x180006ea2  mov     r8d, 108h; Size
0x180006ea8  movups  xmmword ptr [rbx+1346h], xmm0
0x180006eaf  movups  xmmword ptr [rbx+1356h], xmm0
0x180006eb6  movups  xmmword ptr [rbx+1366h], xmm0
0x180006ebd  movups  xmmword ptr [rbx+1376h], xmm0
0x180006ec4  movups  xmmword ptr [rbx+1386h], xmm0
0x180006ecb  movups  xmmword ptr [rbx+1396h], xmm0
0x180006ed2  movups  xmmword ptr [rbx+2F2C8h], xmm0
0x180006ed9  mov     [rbx+2F2D8h], rax
0x180006ee0  call    memset
0x180006ee5  lea     rcx, [rbx+790h]; void *
0x180006eec  xor     edx, edx; Val
0x180006eee  mov     r8d, 0B88h; Size
0x180006ef4  call    memset
0x180006ef9  mov     [rbx+2F05Ch], r14
0x180006f00  mov     [rbx+2F050h], r14
0x180006f07  mov     [rbx+2F044h], r14
0x180006f0e  mov     [rbx+2F064h], r14
0x180006f15  mov     [rbx+2F058h], r14d
0x180006f1c  mov     [rbx+2F04Ch], r14d
0x180006f23  lea     rcx, [rbx+5D158h]; void *
0x180006f2a  xor     edx, edx; Val
0x180006f2c  mov     [rbx+2F06Dh], r14d
0x180006f33  mov     r8d, 9C8h; Size
0x180006f39  mov     [rbx+2F06Ch], r14b
0x180006f40  call    memset
0x180006f45  mov     [rbx+25910h], bp
0x180006f4c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006f53  mov     [rbx+25868h], bp
0x180006f5a  mov     eax, 0FFFF8000h
0x180006f5f  mov     [rbx+4B0h], rcx
0x180006f66  mov     [rbx+1318h], rcx
0x180006f6d  mov     [rbx+1324h], cx
0x180006f74  mov     word ptr [rbx+788h], 1
0x180006f7d  mov     dword ptr [rbx+1320h], 0FFFFFFFFh
0x180006f87  mov     dword ptr [rbx+2DA4Ch], 0C479C000h
0x180006f91  mov     dword ptr [rbx+2DA50h], 3F800000h
0x180006f9b  mov     dword ptr [rbx+2DA2Ch], 3F800000h
0x180006fa5  mov     dword ptr [rbx+2DA30h], 3F800000h
0x180006faf  mov     dword ptr [rbx+2DA34h], 3F800000h
0x180006fb9  mov     dword ptr [rbx+2DA38h], 3F800000h
0x180006fc3  mov     dword ptr [rbx+80Ch], 0FFFFFFFFh
0x180006fcd  mov     dword ptr [rbx+7FCh], 3
0x180006fd7  mov     [rbx+0ACEh], bp
0x180006fde  mov     qword ptr [rbx+0A98h], 0FFFFFFFFC479C000h
0x180006fe9  mov     [rbx+0AA0h], rcx
0x180006ff0  mov     [rbx+0AB0h], rcx
0x180006ff7  mov     [rbx+0ABCh], rcx
0x180006ffe  mov     [rbx+0AC4h], rcx
0x180007005  mov     qword ptr [rbx+0BA8h], 0FFFFFFFFC479C000h
0x180007010  mov     dword ptr [rbx+0BA4h], 0C479C000h
0x18000701a  mov     [rbx+0A24h], rcx
0x180007021  mov     [rbx+0BCCh], bp
0x180007028  mov     [rbx+0B04h], cx
0x18000702f  mov     [rbx+0B98h], rcx
0x180007036  mov     [rbx+0BA0h], ecx
0x18000703c  mov     dword ptr [rbx+0DFCh], 0FFFFFFFFh
0x180007046  mov     dword ptr [rbx+0EE8h], 3F800000h
0x180007050  mov     dword ptr [rbx+8E4h], 0FFFFFFFFh
0x18000705a  mov     dword ptr [rbx+0BD0h], 0FFFFFFFFh
0x180007064  mov     [rbx+0D00h], bp
0x18000706b  mov     byte ptr [rbx+0D02h], 0FFh
0x180007072  mov     dword ptr [rbx+0D04h], 80008000h
0x18000707c  mov     [rbx+0D0Ch], rcx
0x180007083  mov     [rbx+0D08h], ax
0x18000708a  mov     rax, 0C08F380000000000h
0x180007094  mov     [rbx+0D14h], rcx
0x18000709b  mov     [rbx+0D20h], rax
0x1800070a2  mov     dword ptr [rbx+0D1Ch], 0FFFFFFFFh
0x1800070ac  mov     dword ptr [rbx+0D28h], 0FFFFFFFFh
0x1800070b6  mov     [rbx+0D2Ch], rcx
0x1800070bd  mov     dword ptr [rbx+0F30h], 0FFFFFFFFh
0x1800070c7  mov     dword ptr [rbx+0F38h], 0FFFFFFFFh
0x1800070d1  mov     dword ptr [rbx+0F3Eh], 0FFFFFFFFh
0x1800070db  mov     dword ptr [rbx+0F48h], 0FFFFFFFFh
0x1800070e5  mov     byte ptr [rbx+0F50h], 0FFh
0x1800070ec  mov     [rbx+1118h], bp
0x1800070f3  mov     [rbx+112Ch], bp
0x1800070fa  mov     [rbx+1140h], rcx
0x180007101  mov     dword ptr [rbx+1148h], 0FFFFFFFFh
0x18000710b  mov     [rbx+1150h], rax
0x180007112  mov     [rbx+1158h], rax
0x180007119  mov     [rbx+1180h], rcx
0x180007120  mov     [rbx+0D48h], bp
0x180007127  mov     [rbx+0D8Ah], r14w
0x18000712f  mov     [rbx+0D8Eh], rcx
0x180007136  mov     [rbx+0DA0h], bp
0x18000713d  mov     dword ptr [rbx+0DA8h], 0FFFFFFFFh
0x180007147  mov     dword ptr [rbx+0D98h], 0FFFFFFFFh
0x180007151  mov     dword ptr [rbx+0DDEh], 0FFFFFFFFh
0x18000715b  mov     byte ptr [rbx+0D59h], 0FFh
0x180007162  mov     [rbx+0D5Ah], rcx
0x180007169  mov     byte ptr [rbx+0D6Eh], 0FFh
0x180007170  mov     dword ptr [rbx+0D78h], 0FF7FFFFFh
0x18000717a  mov     dword ptr [rbx+0D80h], 0FFFFFFFFh
0x180007184  mov     dword ptr [rbx+0DE4h], 0FFFFFFFFh
0x18000718e  mov     [rbx+0D84h], bp
0x180007195  mov     [rbx+0DE2h], bp
0x18000719c  mov     byte ptr [rbx+0D7Ch], 0FFh
0x1800071a3  mov     [rbx+0BB4F8h], r14d
0x1800071aa  mov     rdi, r14
0x1800071ad  nop     dword ptr [rax]
0x1800071b0  mov     rax, [rbx+0BB430h]
0x1800071b7  mov     rcx, [rdi+rax]; Block
0x1800071bb  test    rcx, rcx
0x1800071be  jz      short loc_1800071D0
0x1800071c0  call    free_0
0x1800071c5  mov     rax, [rbx+0BB430h]
0x1800071cc  mov     [rdi+rax], r14
0x1800071d0  add     rdi, 8
0x1800071d4  cmp     rdi, 1000h
0x1800071db  jl      short loc_1800071B0
0x1800071dd  mov     rbp, [rsp+28h+arg_8]
0x1800071e2  mov     rsi, [rsp+28h+arg_10]
0x1800071e7  mov     rdi, [rsp+28h+arg_18]
0x1800071ec  mov     [rbx+2F2C8h], r14d
0x1800071f3  mov     [rbx+5D23Ch], r14d
0x1800071fa  mov     [rbx+1508h], r14d
0x180007201  mov     [rbx+0BB4D0h], r14
0x180007208  mov     rax, [rbx+5D150h]
0x18000720f  mov     rbx, [rsp+28h+arg_0]
0x180007214  mov     [rax], r14
0x180007217  mov     [rax+8], r14d
0x18000721b  mov     [rax+10h], r14
0x18000721f  mov     [rax+18h], r14d
0x180007223  mov     [rax+4228h], r14d
0x18000722a  mov     dword ptr [rax+5230h], 0C0000000h
0x180007234  add     rsp, 20h
0x180007238  pop     r14
0x18000723a  retn
```

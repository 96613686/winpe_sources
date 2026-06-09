# LibRaw::fuji_decode_strip(fuji_compressed_params *,int,__int64,uint,uchar *)

- ea: `0x180013a50`
- end: `0x180013e44`
- name: `?fuji_decode_strip@LibRaw@@IEAAXPEAUfuji_compressed_params@@H_JIPEAE@Z`
- size: `1012`
- prototype: `void __usercall(LibRaw *__hidden this@<rcx>, struct fuji_compressed_params *@<rdx>, int@<r8d>, __int64@<r9>, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180013350`

## callees

- `0x180002a00`
- `0x180009220`
- `0x180009470`
- `0x180012240`
- `0x180012400`
- `0x1800125e0`
- `0x180013a50`
- `0x180014310`
- `0x180014970`
- `0x180014da0`
- `0x1800b0460`
- `0x1800b0b00`

## pseudocode

```c
void __fastcall LibRaw::fuji_decode_strip(
        LibRaw *this,
        struct fuji_compressed_params *a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  struct fuji_compressed_params *v7; // rsi
  int v11; // r15d
  unsigned int v12; // ecx
  int v13; // ebp
  unsigned __int8 *v14; // rax
  unsigned __int8 *v15; // r12
  size_t v16; // r14
  char *v17; // r8
  int v18; // ecx
  __int64 v19; // r9
  char *v20; // rax
  __int64 v21; // rdx
  __int64 i; // rbx
  _WORD *v23; // rbx
  __int64 v24; // rdx
  _WORD *v25; // rbx
  __int64 v26; // rdx
  _WORD *v27; // rbx
  __int64 v28; // rdx
  size_t Size; // [rsp+38h] [rbp-BE0h]
  size_t v31; // [rsp+48h] [rbp-BD0h]
  _OWORD v32[3]; // [rsp+50h] [rbp-BC8h]
  _BYTE v33[24]; // [rsp+80h] [rbp-B98h] BYREF
  void *v34; // [rsp+98h] [rbp-B80h]
  char v35; // [rsp+B4h] [rbp-B64h] BYREF
  void *v36; // [rsp+B30h] [rbp-E8h]
  void *Src; // [rsp+B38h] [rbp-E0h]
  __int64 v38; // [rsp+B40h] [rbp-D8h]
  void *v39; // [rsp+B48h] [rbp-D0h]
  __int64 v40; // [rsp+B68h] [rbp-B0h]
  void *v41; // [rsp+B70h] [rbp-A8h]
  __int64 v42; // [rsp+BA8h] [rbp-70h]
  void *v43; // [rsp+BB0h] [rbp-68h]

  v7 = a2;
  if ( !*((_DWORD *)this + 95396) )
  {
    v7 = (struct fuji_compressed_params *)LibRaw::malloc(this, (2 << *((_DWORD *)this + 95394)) + 152);
    *(_OWORD *)v7 = *(_OWORD *)a2;
    *((_OWORD *)v7 + 1) = *((_OWORD *)a2 + 1);
    *((_OWORD *)v7 + 2) = *((_OWORD *)a2 + 2);
    *((_OWORD *)v7 + 3) = *((_OWORD *)a2 + 3);
    *((_OWORD *)v7 + 4) = *((_OWORD *)a2 + 4);
    *((_OWORD *)v7 + 5) = *((_OWORD *)a2 + 5);
    *((_OWORD *)v7 + 6) = *((_OWORD *)a2 + 6);
    *((_OWORD *)v7 + 7) = *((_OWORD *)a2 + 7);
    *((_OWORD *)v7 + 8) = *((_OWORD *)a2 + 8);
    *((_QWORD *)v7 + 18) = *((_QWORD *)a2 + 18);
    *(_QWORD *)v7 = (char *)v7 + 152;
    *((_DWORD *)v7 + 6) = -1;
  }
  LibRaw::init_fuji_block(this, (struct fuji_compressed_block *)v33, v7, a4, a5);
  v11 = *((_DWORD *)this + 95393);
  v12 = 2 * *((unsigned __int16 *)v7 + 74) + 4;
  if ( a3 + 1 == *((_DWORD *)this + 95392) )
    v11 = *((unsigned __int16 *)this + 9) - a3 * v11;
  v13 = 0;
  v32[0] = _mm_load_si128((const __m128i *)&_xmm);
  v32[2] = _mm_load_si128((const __m128i *)&_xmm);
  v32[1] = _mm_load_si128((const __m128i *)&_xmm);
  if ( *((int *)this + 95391) > 0 )
  {
    Size = 3 * v12;
    v31 = 6 * v12;
    v14 = a6;
    v15 = a6;
    v16 = v12;
    do
    {
      if ( !*((_DWORD *)this + 95396) )
      {
        if ( v14 )
          LODWORD(v14) = *v15;
        if ( !v13 || (_DWORD)v14 != *((_DWORD *)v7 + 6) )
        {
          init_main_qtable(v7, *v15);
          v17 = &v35;
          v18 = (*((_DWORD *)v7 + 3) + 32) >> 6;
          v19 = 3;
          if ( v18 < 2 )
            v18 = 2;
          do
          {
            v20 = v17;
            v21 = 41;
            do
            {
              *((_DWORD *)v20 - 1) = v18;
              *(_DWORD *)v20 = 1;
              *((_DWORD *)v20 + 335) = v18;
              *((_DWORD *)v20 + 336) = 1;
              v20 += 8;
              --v21;
            }
            while ( v21 );
            v17 += 448;
            --v19;
          }
          while ( v19 );
        }
      }
      if ( *((_DWORD *)this + 95395) == 16 )
        LibRaw::xtrans_decode_block(this, (struct fuji_compressed_block *)v33, v7);
      else
        LibRaw::fuji_bayer_decode_block(this, (struct fuji_compressed_block *)v33, v7);
      for ( i = 0; i < 6; ++i )
        memmove(*(&Src + *((int *)v32 + 2 * i)), *(&Src + *((int *)v32 + 2 * i + 1)), v16);
      if ( *((_DWORD *)this + 95395) == 16 )
        LibRaw::copy_line_to_xtrans(this, (struct fuji_compressed_block *)v33, v13, a3, v11);
      else
        LibRaw::copy_line_to_bayer(this, (struct fuji_compressed_block *)v33, v13, a3, v11);
      _mm_lfence();
      v23 = v39;
      memset(v39, 0, Size);
      v24 = v38;
      *v23 = *(_WORD *)(v38 + 2);
      v23[*((unsigned __int16 *)v7 + 74) + 1] = *(_WORD *)(v24 + 2LL * *((unsigned __int16 *)v7 + 74));
      v25 = v41;
      memset(v41, 0, v31);
      v26 = v40;
      *v25 = *(_WORD *)(v40 + 2);
      v25[*((unsigned __int16 *)v7 + 74) + 1] = *(_WORD *)(v26 + 2LL * *((unsigned __int16 *)v7 + 74));
      v27 = v43;
      memset(v43, 0, Size);
      v28 = v42;
      ++v13;
      ++v15;
      *v27 = *(_WORD *)(v42 + 2);
      v27[*((unsigned __int16 *)v7 + 74) + 1] = *(_WORD *)(v28 + 2LL * *((unsigned __int16 *)v7 + 74));
      v14 = a6;
    }
    while ( v13 < *((_DWORD *)this + 95391) );
  }
  if ( !*((_DWORD *)this + 95396) )
    LibRaw::free(this, v7);
  LibRaw::free(this, v36);
  LibRaw::free(this, v34);
}

```

## disassembly

```asm
0x180013a50  mov     r11, rsp
0x180013a53  push    rsi
0x180013a54  push    rdi
0x180013a55  sub     rsp, 0C08h
0x180013a5c  mov     rax, cs:__security_cookie
0x180013a63  xor     rax, rsp
0x180013a66  mov     [rsp+0C18h+var_48], rax
0x180013a6e  cmp     dword ptr [rcx+5D290h], 0
0x180013a75  mov     rdi, rcx
0x180013a78  mov     rax, [rsp+0C18h+arg_28]
0x180013a80  mov     rsi, rdx
0x180013a83  mov     [r11+20h], rbx
0x180013a87  mov     rbx, rdx
0x180013a8a  mov     [r11-18h], rbp
0x180013a8e  mov     rbp, r9
0x180013a91  mov     [r11-28h], r13
0x180013a95  mov     r13d, r8d
0x180013a98  mov     [rsp+0C18h+var_BD8], rax
0x180013a9d  mov     eax, 2
0x180013aa2  mov     [r11-38h], r15
0x180013aa6  mov     [rsp+0C18h+var_BE8], r8d
0x180013aab  jnz     loc_180013B38
0x180013ab1  mov     ecx, [rcx+5D288h]
0x180013ab7  shl     eax, cl
0x180013ab9  mov     rcx, rdi; this
0x180013abc  add     eax, 98h
0x180013ac1  movsxd  rdx, eax; unsigned __int64
0x180013ac4  call    ?malloc@LibRaw@@IEAAPEAX_K@Z; LibRaw::malloc(unsigned __int64)
0x180013ac9  movups  xmm0, xmmword ptr [rbx]
0x180013acc  mov     rsi, rax
0x180013acf  movups  xmmword ptr [rax], xmm0
0x180013ad2  movups  xmm1, xmmword ptr [rbx+10h]
0x180013ad6  movups  xmmword ptr [rax+10h], xmm1
0x180013ada  movups  xmm0, xmmword ptr [rbx+20h]
0x180013ade  movups  xmmword ptr [rax+20h], xmm0
0x180013ae2  movups  xmm1, xmmword ptr [rbx+30h]
0x180013ae6  movups  xmmword ptr [rax+30h], xmm1
0x180013aea  movups  xmm0, xmmword ptr [rbx+40h]
0x180013aee  movups  xmmword ptr [rax+40h], xmm0
0x180013af2  movups  xmm1, xmmword ptr [rbx+50h]
0x180013af6  movups  xmmword ptr [rax+50h], xmm1
0x180013afa  movups  xmm0, xmmword ptr [rbx+60h]
0x180013afe  movups  xmmword ptr [rax+60h], xmm0
0x180013b02  movups  xmm1, xmmword ptr [rbx+70h]
0x180013b06  movups  xmmword ptr [rax+70h], xmm1
0x180013b0a  movups  xmm0, xmmword ptr [rbx+80h]
0x180013b11  movups  xmmword ptr [rax+80h], xmm0
0x180013b18  movsd   xmm1, qword ptr [rbx+90h]
0x180013b20  movsd   qword ptr [rax+90h], xmm1
0x180013b28  add     rax, 98h
0x180013b2e  mov     [rsi], rax
0x180013b31  mov     dword ptr [rsi+18h], 0FFFFFFFFh
0x180013b38  mov     eax, [rsp+0C18h+arg_20]
0x180013b3f  lea     rdx, [rsp+0C18h+var_B98]; struct fuji_compressed_block *
0x180013b47  mov     r9, rbp; __int64
0x180013b4a  mov     [rsp+0C18h+var_BF8], eax; unsigned int
0x180013b4e  mov     r8, rsi; struct fuji_compressed_params *
0x180013b51  mov     rcx, rdi; this
0x180013b54  call    ?init_fuji_block@LibRaw@@IEAAXPEAUfuji_compressed_block@@PEBUfuji_compressed_params@@_JI@Z; LibRaw::init_fuji_block(fuji_compressed_block *,fuji_compressed_params const *,__int64,uint)
0x180013b59  movzx   eax, word ptr [rsi+94h]
0x180013b60  mov     r15d, [rdi+5D284h]
0x180013b67  lea     ecx, ds:4[rax*2]
0x180013b6e  lea     eax, [r13+1]
0x180013b72  cmp     eax, [rdi+5D280h]
0x180013b78  jnz     short loc_180013B89
0x180013b7a  mov     eax, r15d
0x180013b7d  movzx   r15d, word ptr [rdi+12h]
0x180013b82  imul    eax, r13d
0x180013b86  sub     r15d, eax
0x180013b89  movdqa  xmm0, cs:__xmm@00000004000000010000000300000000
0x180013b91  xor     ebp, ebp
0x180013b93  movdqa  xmm1, cs:__xmm@0000000c000000060000000b00000005
0x180013b9b  movdqu  [rsp+0C18h+var_BC8], xmm0
0x180013ba1  movdqa  xmm0, cs:__xmm@000000110000000e000000100000000d
0x180013ba9  movdqu  [rsp+0C18h+var_BA8], xmm0
0x180013baf  movdqu  [rsp+0C18h+var_BB8], xmm1
0x180013bb5  cmp     [rdi+5D27Ch], ebp
0x180013bbb  jle     loc_180013DD6
0x180013bc1  lea     eax, [rcx+rcx*2]
0x180013bc4  mov     [rsp+0C18h+var_20], r12
0x180013bcc  mov     [rsp+0C18h+Size], rax
0x180013bd1  lea     eax, [rcx+rcx*2]
0x180013bd4  add     eax, eax
0x180013bd6  mov     [rsp+0C18h+var_30], r14
0x180013bde  mov     [rsp+0C18h+var_BD0], rax
0x180013be3  mov     rax, [rsp+0C18h+var_BD8]
0x180013be8  mov     r12, rax
0x180013beb  mov     r14d, ecx
0x180013bee  xchg    ax, ax
0x180013bf0  cmp     dword ptr [rdi+5D290h], 0
0x180013bf7  jnz     loc_180013C80
0x180013bfd  test    rax, rax
0x180013c00  jz      short loc_180013C07
0x180013c02  movzx   eax, byte ptr [r12]
0x180013c07  test    ebp, ebp
0x180013c09  jz      short loc_180013C10
0x180013c0b  cmp     eax, [rsi+18h]
0x180013c0e  jz      short loc_180013C80
0x180013c10  movzx   edx, byte ptr [r12]; unsigned __int8
0x180013c15  mov     rcx, rsi; struct fuji_compressed_params *
0x180013c18  call    ?init_main_qtable@@YAXPEAUfuji_compressed_params@@E@Z; init_main_qtable(fuji_compressed_params *,uchar)
0x180013c1d  mov     ecx, [rsi+0Ch]
0x180013c20  lea     r8, [rsp+0C18h+var_B64]
0x180013c28  add     ecx, 20h ; ' '
0x180013c2b  mov     eax, 2
0x180013c30  sar     ecx, 6
0x180013c33  mov     r9d, 3
0x180013c39  cmp     ecx, 2
0x180013c3c  cmovl   ecx, eax
0x180013c3f  nop
0x180013c40  mov     rax, r8
0x180013c43  mov     edx, 29h ; ')'
0x180013c48  nop     dword ptr [rax+rax+00000000h]
0x180013c50  mov     [rax-4], ecx
0x180013c53  mov     dword ptr [rax], 1
0x180013c59  mov     [rax+53Ch], ecx
0x180013c5f  mov     dword ptr [rax+540h], 1
0x180013c69  lea     rax, [rax+8]
0x180013c6d  sub     rdx, 1
0x180013c71  jnz     short loc_180013C50
0x180013c73  add     r8, 1C0h
0x180013c7a  sub     r9, 1
0x180013c7e  jnz     short loc_180013C40
0x180013c80  cmp     dword ptr [rdi+5D28Ch], 10h
0x180013c87  lea     rdx, [rsp+0C18h+var_B98]; struct fuji_compressed_block *
0x180013c8f  mov     r9d, ebp; int
0x180013c92  mov     r8, rsi; struct fuji_compressed_params *
0x180013c95  mov     rcx, rdi; this
0x180013c98  jnz     short loc_180013CA1
0x180013c9a  call    ?xtrans_decode_block@LibRaw@@IEAAXPEAUfuji_compressed_block@@PEBUfuji_compressed_params@@H@Z; LibRaw::xtrans_decode_block(fuji_compressed_block *,fuji_compressed_params const *,int)
0x180013c9f  jmp     short loc_180013CA6
0x180013ca1  call    ?fuji_bayer_decode_block@LibRaw@@IEAAXPEAUfuji_compressed_block@@PEBUfuji_compressed_params@@H@Z; LibRaw::fuji_bayer_decode_block(fuji_compressed_block *,fuji_compressed_params const *,int)
0x180013ca6  xor     ebx, ebx
0x180013ca8  lea     r13, [rsp+0C18h+var_BC8+4]
0x180013cad  nop     dword ptr [rax]
0x180013cb0  movsxd  rdx, dword ptr [r13+rbx*8+0]
0x180013cb5  mov     r8, r14; Size
0x180013cb8  movsxd  rcx, dword ptr [rsp+rbx*8+0C18h+var_BC8]
0x180013cbd  mov     rdx, [rsp+rdx*8+0C18h+Src]; Src
0x180013cc5  mov     rcx, [rsp+rcx*8+0C18h+Src]; void *
0x180013ccd  call    memmove
0x180013cd2  inc     rbx
0x180013cd5  cmp     rbx, 6
0x180013cd9  jl      short loc_180013CB0
0x180013cdb  cmp     dword ptr [rdi+5D28Ch], 10h
0x180013ce2  lea     rdx, [rsp+0C18h+var_B98]; struct fuji_compressed_block *
0x180013cea  mov     r13d, [rsp+0C18h+var_BE8]
0x180013cef  mov     r8d, ebp; int
0x180013cf2  mov     r9d, r13d; int
0x180013cf5  mov     [rsp+0C18h+var_BF8], r15d; int
0x180013cfa  mov     rcx, rdi; this
0x180013cfd  jnz     short loc_180013D06
0x180013cff  call    ?copy_line_to_xtrans@LibRaw@@IEAAXPEAUfuji_compressed_block@@HHH@Z; LibRaw::copy_line_to_xtrans(fuji_compressed_block *,int,int,int)
0x180013d04  jmp     short loc_180013D0B
0x180013d06  call    ?copy_line_to_bayer@LibRaw@@IEAAXPEAUfuji_compressed_block@@HHH@Z; LibRaw::copy_line_to_bayer(fuji_compressed_block *,int,int,int)
0x180013d0b  lfence
0x180013d0e  mov     rbx, [rsp+0C18h+var_D0]
0x180013d16  xor     edx, edx; Val
0x180013d18  mov     r8, [rsp+0C18h+Size]; Size
0x180013d1d  mov     rcx, rbx; void *
0x180013d20  call    memset
0x180013d25  mov     rdx, [rsp+0C18h+var_D8]
0x180013d2d  mov     r8, [rsp+0C18h+var_BD0]; Size
0x180013d32  movzx   eax, word ptr [rdx+2]
0x180013d36  mov     [rbx], ax
0x180013d39  movzx   ecx, word ptr [rsi+94h]
0x180013d40  movzx   eax, word ptr [rdx+rcx*2]
0x180013d44  xor     edx, edx; Val
0x180013d46  mov     [rbx+rcx*2+2], ax
0x180013d4b  mov     rbx, [rsp+0C18h+var_A8]
0x180013d53  mov     rcx, rbx; void *
0x180013d56  call    memset
0x180013d5b  mov     rdx, [rsp+0C18h+var_B0]
0x180013d63  mov     r8, [rsp+0C18h+Size]; Size
0x180013d68  movzx   eax, word ptr [rdx+2]
0x180013d6c  mov     [rbx], ax
0x180013d6f  movzx   ecx, word ptr [rsi+94h]
0x180013d76  movzx   eax, word ptr [rdx+rcx*2]
0x180013d7a  xor     edx, edx; Val
0x180013d7c  mov     [rbx+rcx*2+2], ax
0x180013d81  mov     rbx, [rsp+0C18h+var_68]
0x180013d89  mov     rcx, rbx; void *
0x180013d8c  call    memset
0x180013d91  mov     rdx, [rsp+0C18h+var_70]
0x180013d99  inc     ebp
0x180013d9b  inc     r12
0x180013d9e  movzx   eax, word ptr [rdx+2]
0x180013da2  mov     [rbx], ax
0x180013da5  movzx   ecx, word ptr [rsi+94h]
0x180013dac  movzx   eax, word ptr [rdx+rcx*2]
0x180013db0  mov     [rbx+rcx*2+2], ax
0x180013db5  mov     rax, [rsp+0C18h+var_BD8]
0x180013dba  cmp     ebp, [rdi+5D27Ch]
0x180013dc0  jl      loc_180013BF0
0x180013dc6  mov     r14, [rsp+0C18h+var_30]
0x180013dce  mov     r12, [rsp+0C18h+var_20]
0x180013dd6  cmp     dword ptr [rdi+5D290h], 0
0x180013ddd  mov     r15, [rsp+0C18h+var_38]
0x180013de5  mov     r13, [rsp+0C18h+var_28]
0x180013ded  mov     rbp, [rsp+0C18h+var_18]
0x180013df5  mov     rbx, [rsp+0C18h+arg_18]
0x180013dfd  jnz     short loc_180013E0A
0x180013dff  mov     rdx, rsi; void *
0x180013e02  mov     rcx, rdi; this
0x180013e05  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180013e0a  mov     rdx, [rsp+0C18h+var_E8]; void *
0x180013e12  mov     rcx, rdi; this
0x180013e15  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180013e1a  mov     rdx, [rsp+0C18h+var_B80]; void *
0x180013e22  mov     rcx, rdi; this
0x180013e25  call    ?free@LibRaw@@IEAAXPEAX@Z; LibRaw::free(void *)
0x180013e2a  mov     rcx, [rsp+0C18h+var_48]
0x180013e32  xor     rcx, rsp; StackCookie
0x180013e35  call    __security_check_cookie
0x180013e3a  add     rsp, 0C08h
0x180013e41  pop     rdi
0x180013e42  pop     rsi
0x180013e43  retn
```

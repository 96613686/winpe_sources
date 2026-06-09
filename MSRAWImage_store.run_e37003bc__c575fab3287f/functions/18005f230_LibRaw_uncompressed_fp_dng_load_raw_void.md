# LibRaw::uncompressed_fp_dng_load_raw(void)

- ea: `0x18005f230`
- end: `0x18005f9c8`
- name: `?uncompressed_fp_dng_load_raw@LibRaw@@IEAAXXZ`
- size: `1944`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e18`
- `0x180003e4c`
- `0x180006363`
- `0x180008f30`
- `0x1800091e0`
- `0x180009460`
- `0x18005e790`
- `0x18005e810`
- `0x18005eba0`
- `0x18005ed30`
- `0x18005f230`
- `0x1800a4510`
- `0x1800af370`
- `0x1800b0460`
- `0x1800b0b00`
- `0x1800b4010`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x18005f3cb`
- `WS2_32!__imp_ntohs` at `0x18005f3cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LibRaw::uncompressed_fp_dng_load_raw(LibRaw *this)
{
  int ifd_by_offset; // eax
  char *v3; // r13
  int v4; // ecx
  int v5; // r14d
  unsigned int v6; // r12d
  __int64 v7; // rdi
  __int64 v8; // rdx
  char *v9; // r15
  float v10; // xmm8_4
  unsigned __int64 v11; // rbx
  char *v12; // rdi
  size_t v13; // r8
  __m128i *v14; // rbx
  unsigned __int64 v15; // r11
  unsigned __int64 v16; // rdx
  unsigned __int16 *v17; // rdi
  __m128i si128; // xmm7
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r9
  int v22; // r10d
  unsigned int v23; // edx
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  int v26; // r8d
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // r15
  __m128i *v29; // r8
  unsigned __int64 v30; // rdx
  __int8 v31; // cl
  __int64 v32; // r8
  __int64 v33; // rcx
  __m128i *v34; // rax
  double v35; // xmm0_8
  bool v36; // zf
  int v37; // eax
  int v38; // eax
  int v39; // ecx
  __m128i *v40; // rcx
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // [rsp+38h] [rbp-D0h]
  unsigned __int64 v43; // [rsp+40h] [rbp-C8h]
  char *v44; // [rsp+48h] [rbp-C0h]
  unsigned __int64 v45; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v46; // [rsp+58h] [rbp-B0h]
  __int64 v47; // [rsp+60h] [rbp-A8h]
  char *v48; // [rsp+68h] [rbp-A0h]
  __int64 v49; // [rsp+74h] [rbp-94h] BYREF
  __int64 v50; // [rsp+7Ch] [rbp-8Ch]
  __int64 v51; // [rsp+84h] [rbp-84h]
  int v52; // [rsp+8Ch] [rbp-7Ch]
  __int64 v53; // [rsp+90h] [rbp-78h]
  _OWORD v54[3]; // [rsp+98h] [rbp-70h] BYREF
  size_t Size; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v56; // [rsp+D0h] [rbp-38h]
  __int128 v57; // [rsp+D8h] [rbp-30h]
  char *v58; // [rsp+E8h] [rbp-20h]
  __int64 v59; // [rsp+F0h] [rbp-18h]
  int pExceptionObject; // [rsp+178h] [rbp+70h] BYREF
  int v61; // [rsp+180h] [rbp+78h]
  int v62; // [rsp+188h] [rbp+80h]
  __m128i *v63; // [rsp+190h] [rbp+88h]

  v59 = -2;
  ifd_by_offset = LibRaw::find_ifd_by_offset(this, *((_DWORD *)this + 95360));
  if ( ifd_by_offset < 0 || ifd_by_offset > *((_DWORD *)this + 95348) )
  {
    pExceptionObject = 2;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  v3 = (char *)this + 33408 * ifd_by_offset + 432944;
  v4 = *((_DWORD *)v3 + 7);
  if ( v4 != 1 && (unsigned int)(v4 - 3) > 1 )
  {
    pExceptionObject = 2;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  if ( *((_DWORD *)this + 136) && v4 > 1 )
  {
    pExceptionObject = 2;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  if ( *((_DWORD *)this + 95377) != v4 )
  {
    pExceptionObject = 2;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  v5 = (*((_DWORD *)v3 + 2) + 7) >> 3;
  if ( (unsigned int)(v5 - 1) > 3 )
  {
    pExceptionObject = 2;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  WORD2(v49) = 0;
  v6 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  memset(v54, 0, sizeof(v54));
  tile_stripe_data_t::init(
    (tile_stripe_data_t *)((char *)&v49 + 4),
    (struct tiff_ifd_t *)v3,
    (LibRaw *)((char *)this + 16),
    (LibRaw *)((char *)this + 381408),
    *((_WORD *)this + 190704),
    *((struct LibRaw_abstract_datastream **)this + 47659));
  v7 = HIDWORD(v50);
  v8 = *((int *)v3 + 7);
  v42 = (unsigned int)v51;
  if ( 4 * HIDWORD(v50) * (unsigned int)v51 * (int)v50 * v8 > (__int64)((unsigned __int64)*((unsigned int *)this + 1339) << 20) )
  {
    pExceptionObject = 10;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  if ( *((_DWORD *)v3 + 12) != 3 )
  {
    pExceptionObject = 2;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  v9 = (char *)LibRaw::calloc(this, (unsigned int)(v50 * HIDWORD(v50) * v51 * v8), 4u);
  v44 = v9;
  v61 = *((_WORD *)this + 190704) == 18761;
  pExceptionObject = ntohs(0x1234u) == 4660;
  v10 = 0.0;
  v11 = 4 * v7 * *((int *)v3 + 7);
  v57 = 0;
  v48 = 0;
  v58 = 0;
  if ( v11 )
  {
    if ( v11 > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<unsigned int>::_Xlength();
    v63 = (__m128i *)std::_Allocate<16,std::_Default_allocate_traits>(v11);
    *(_QWORD *)&v57 = v63;
    v12 = &v63->m128i_i8[v11];
    v48 = &v63->m128i_i8[v11];
    v58 = &v63->m128i_i8[v11];
    v13 = v11;
    v14 = v63;
    memset(v63, 0, v13);
    *((_QWORD *)&v57 + 1) = v12;
  }
  else
  {
    v14 = (__m128i *)v57;
    v63 = (__m128i *)v57;
  }
  v15 = 0;
  v43 = 0;
  v16 = 0;
  v47 = 0;
  v17 = (unsigned __int16 *)((char *)this + 16);
  if ( *((_WORD *)this + 8) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v19 = v42;
    do
    {
      if ( *((_WORD *)this + 9) )
      {
        v20 = (unsigned int)v50;
        v56 = (unsigned int)v50;
        do
        {
          if ( v16 >= v20 )
            break;
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 47659) + 24LL))(
            *((_QWORD *)this + 47659),
            *(_QWORD *)(*(_QWORD *)&v54[0] + 8 * v16),
            0);
          v15 = v43;
          v21 = v42;
          if ( v42 + v43 > *v17 )
            v21 = *v17 - v43;
          v46 = v21;
          v22 = HIDWORD(v50);
          v23 = HIDWORD(v50);
          if ( v6 + HIDWORD(v50) > *((unsigned __int16 *)this + 9) )
            v23 = *((unsigned __int16 *)this + 9) - v6;
          v24 = v23 * (__int64)*((int *)v3 + 7);
          v25 = v24 * v5;
          v45 = v25;
          v26 = v5 * HIDWORD(v50) * *((_DWORD *)v3 + 7);
          v62 = v26;
          Size = 4 * v24;
          if ( v21 )
          {
            v27 = v26;
            v28 = v43;
            do
            {
              if ( v27 <= v25 )
                v14 = (__m128i *)&v44[4 * *((int *)v3 + 7) * (v6 + v28 * *((unsigned __int16 *)this + 9))];
              (*(void (__fastcall **)(_QWORD, __m128i *, __int64, unsigned __int64))(**((_QWORD **)this + 47659) + 16LL))(
                *((_QWORD *)this + 47659),
                v14,
                1,
                v27);
              if ( v5 == 2 )
              {
                if ( v61 == pExceptionObject )
                  LibRaw::libraw_swab(this, v14, v27);
              }
              else if ( v5 == 3 )
              {
                if ( *((_WORD *)this + 190704) == 18761 && v62 - 2 > 0 )
                {
                  v29 = v14;
                  v30 = (v62 - 2 - 1LL) / 3uLL + 1;
                  do
                  {
                    v31 = v29->m128i_i8[0];
                    v29->m128i_i8[0] = v29->m128i_i8[2];
                    v29->m128i_i8[2] = v31;
                    v29 = (__m128i *)((char *)v29 + 3);
                    --v30;
                  }
                  while ( v30 );
                }
              }
              else if ( v5 == 4 && v61 == pExceptionObject )
              {
                v32 = v62 / 4;
                v33 = 0;
                if ( (int)v32 >= 2 && _isa_available >= 2 )
                {
                  if ( (unsigned int)v32 < 0x10 )
                    goto LABEL_81;
                  v34 = v14 + 2;
                  do
                  {
                    v34[-2] = _mm_shuffle_epi8(_mm_loadu_si128(v34 - 2), si128);
                    v34[-1] = _mm_shuffle_epi8(_mm_loadu_si128(v34 - 1), si128);
                    *v34 = _mm_shuffle_epi8(_mm_loadu_si128(v34), si128);
                    v34[1] = _mm_shuffle_epi8(_mm_loadu_si128(v34 + 1), si128);
                    v33 += 16;
                    v34 += 4;
                  }
                  while ( v33 < (int)(v32 - (v32 & 0xF)) );
                  if ( ((unsigned __int8)v32 & 0xFu) >= 2 )
                  {
LABEL_81:
                    do
                    {
                      *(__int64 *)((char *)v14->m128i_i64 + 4 * v33) = _mm_shuffle_epi8(
                                                                         _mm_loadl_epi64((__m128i *)((char *)v14 + 4 * v33)),
                                                                         si128).m128i_u64[0];
                      v33 += 2;
                    }
                    while ( v33 < (int)(v32 - (v32 & 1)) );
                  }
                }
                for ( ; v33 < v32; ++v33 )
                  v14->m128i_i32[v33] = _byteswap_ulong(v14->m128i_u32[v33]);
              }
              v35 = expandFloats(v14, (unsigned int)(*((_DWORD *)v3 + 7) * HIDWORD(v50)), (unsigned int)v5);
              v25 = v45;
              if ( v27 > v45 )
              {
                memmove(&v44[4 * *((int *)v3 + 7) * (v6 + v28 * *((unsigned __int16 *)this + 9))], v14, Size);
                v25 = v45;
              }
              v10 = fmaxf(v10, *(float *)&v35);
              ++v28;
              v36 = v46-- == 1;
              v14 = v63;
            }
            while ( !v36 );
            v22 = HIDWORD(v50);
            v15 = v43;
            v17 = (unsigned __int16 *)((char *)this + 16);
          }
          v6 += v22;
          v16 = ++v47;
          v14 = v63;
          v20 = v56;
        }
        while ( v6 < *((unsigned __int16 *)this + 9) );
        v19 = v42;
      }
      v15 += v19;
      v43 = v15;
      v14 = v63;
      v6 = 0;
    }
    while ( v15 < *v17 );
    v9 = v44;
  }
  *((float *)this + 38227) = v10;
  *((_QWORD *)this + 24189) = v9;
  v37 = *((_DWORD *)v3 + 7);
  switch ( v37 )
  {
    case 1:
      *((_QWORD *)this + 24193) = v9;
      v38 = 4 * *((unsigned __int16 *)this + 9);
LABEL_62:
      *((_DWORD *)this + 48510) = v38;
      *((_DWORD *)this + 8) = v38;
      break;
    case 3:
      *((_QWORD *)this + 24194) = v9;
      v39 = 12 * *((unsigned __int16 *)this + 9);
      *((_DWORD *)this + 8) = v39;
      *((_DWORD *)this + 48510) = v39;
      break;
    case 4:
      *((_QWORD *)this + 24195) = v9;
      v38 = 16 * *((unsigned __int16 *)this + 9);
      goto LABEL_62;
  }
  if ( (*((_BYTE *)this + 5344) & 2) != 0 )
    LibRaw::convertFloatToInt(this, 4096.0, 32767.0, 16383.0);
  v40 = v63;
  if ( v63 )
  {
    v41 = v48 - (char *)v63;
    if ( (unsigned __int64)(v48 - (char *)v63) >= 0x1000 )
    {
      v41 += 39LL;
      v40 = (__m128i *)v63[-1].m128i_i64[1];
      if ( (unsigned __int64)((char *)v63 - (char *)v40 - 8) > 0x1F )
        invoke_watson_0(0, 0, 0, 0, 0);
    }
    operator delete(v40, v41);
  }
  std::vector<unsigned __int64>::_Tidy((char *)&v54[1] + 8);
  std::vector<unsigned __int64>::_Tidy(v54);
}

```

## disassembly

```asm
0x18005f230  mov     rax, rsp
0x18005f233  push    rbp
0x18005f234  push    rbx
0x18005f235  push    rsi
0x18005f236  push    rdi
0x18005f237  push    r12
0x18005f239  push    r13
0x18005f23b  push    r14
0x18005f23d  push    r15
0x18005f23f  lea     rbp, [rax-68h]
0x18005f243  sub     rsp, 128h
0x18005f24a  mov     [rbp+60h+var_78], 0FFFFFFFFFFFFFFFEh
0x18005f252  movaps  xmmword ptr [rax-58h], xmm6
0x18005f256  movaps  xmmword ptr [rax-68h], xmm7
0x18005f25a  movaps  xmmword ptr [rax-78h], xmm8
0x18005f25f  mov     rsi, rcx
0x18005f262  mov     edx, [rcx+5D200h]; int
0x18005f268  call    ?find_ifd_by_offset@LibRaw@@IEAAHH@Z; LibRaw::find_ifd_by_offset(int)
0x18005f26d  test    eax, eax
0x18005f26f  js      loc_18005F91D
0x18005f275  cmp     eax, [rsi+5D1D0h]
0x18005f27b  jg      loc_18005F91D
0x18005f281  cdqe
0x18005f283  imul    r13, rax, 8280h
0x18005f28a  add     r13, 69B30h
0x18005f291  add     r13, rsi
0x18005f294  mov     ecx, [r13+1Ch]
0x18005f298  cmp     ecx, 1
0x18005f29b  jz      short loc_18005F2A9
0x18005f29d  lea     eax, [rcx-3]
0x18005f2a0  cmp     eax, 1
0x18005f2a3  ja      loc_18005F935
0x18005f2a9  cmp     dword ptr [rsi+220h], 0
0x18005f2b0  jz      short loc_18005F2BB
0x18005f2b2  cmp     ecx, 1
0x18005f2b5  jg      loc_18005F94D
0x18005f2bb  cmp     [rsi+5D244h], ecx
0x18005f2c1  jnz     loc_18005F965
0x18005f2c7  mov     r14d, [r13+8]
0x18005f2cb  add     r14d, 7
0x18005f2cf  sar     r14d, 3
0x18005f2d3  lea     eax, [r14-1]
0x18005f2d7  cmp     eax, 3
0x18005f2da  ja      loc_18005F905
0x18005f2e0  mov     word ptr [rsp+160h+var_F4+4], 0
0x18005f2e7  xor     r12d, r12d
0x18005f2ea  mov     [rsp+160h+var_EC], r12
0x18005f2ef  mov     [rsp+160h+var_E4], r12
0x18005f2f4  mov     [rbp+60h+var_DC], r12d
0x18005f2f8  mov     [rbp+60h+var_D8], r12
0x18005f2fc  xorps   xmm0, xmm0
0x18005f2ff  movdqu  [rbp+60h+var_D0], xmm0
0x18005f304  xorps   xmm1, xmm1
0x18005f307  movdqu  [rbp+60h+var_C0], xmm1
0x18005f30c  movdqu  [rbp+60h+var_B0], xmm0
0x18005f311  lea     r8, [rsi+10h]; struct libraw_image_sizes_t *
0x18005f315  mov     rax, [rsi+5D158h]
0x18005f31c  mov     [rsp+160h+var_138], rax; struct LibRaw_abstract_datastream *
0x18005f321  movzx   eax, word ptr [rsi+5D1E0h]
0x18005f328  mov     word ptr [rsp+160h+Reserved], ax; __int16
0x18005f32d  lea     r9, [rsi+5D1E0h]; struct unpacker_data_t *
0x18005f334  mov     rdx, r13; struct tiff_ifd_t *
0x18005f337  lea     rcx, [rsp+160h+var_F4+4]; this
0x18005f33c  call    ?init@tile_stripe_data_t@@QEAAXPEAUtiff_ifd_t@@AEBUlibraw_image_sizes_t@@AEBUunpacker_data_t@@FPEAVLibRaw_abstract_datastream@@@Z; tile_stripe_data_t::init(tiff_ifd_t *,libraw_image_sizes_t const &,unpacker_data_t const &,short,LibRaw_abstract_datastream *)
0x18005f341  mov     r9d, dword ptr [rsp+160h+var_EC+4]
0x18005f346  mov     edi, r9d
0x18005f349  movsxd  rdx, dword ptr [r13+1Ch]
0x18005f34d  mov     r8d, dword ptr [rsp+160h+var_E4]
0x18005f352  mov     [rsp+160h+var_130], r8
0x18005f357  mov     rcx, rdx
0x18005f35a  movsxd  r11, dword ptr [rsp+160h+var_EC]
0x18005f35f  imul    rcx, r11
0x18005f363  imul    rcx, r8
0x18005f367  imul    rcx, r9
0x18005f36b  shl     rcx, 2
0x18005f36f  mov     eax, [rsi+14ECh]
0x18005f375  shl     rax, 14h
0x18005f379  cmp     rcx, rax
0x18005f37c  jg      loc_18005F97D
0x18005f382  cmp     dword ptr [r13+30h], 3
0x18005f387  jnz     loc_18005F9B0
0x18005f38d  imul    edx, r8d
0x18005f391  imul    edx, r9d
0x18005f395  imul    edx, r11d; unsigned __int64
0x18005f399  mov     r8d, 4; unsigned __int64
0x18005f39f  mov     rcx, rsi; this
0x18005f3a2  call    ?calloc@LibRaw@@IEAAPEAX_K0@Z; LibRaw::calloc(unsigned __int64,unsigned __int64)
0x18005f3a7  mov     r15, rax
0x18005f3aa  mov     [rsp+160h+var_120], rax
0x18005f3af  mov     ecx, 4949h
0x18005f3b4  mov     eax, r12d
0x18005f3b7  cmp     [rsi+5D1E0h], cx
0x18005f3be  setz    al
0x18005f3c1  mov     [rbp+60h+arg_8], eax
0x18005f3c4  mov     ebx, 1234h
0x18005f3c9  mov     ecx, ebx; netshort
0x18005f3cb  call    cs:__imp_ntohs
0x18005f3d1  mov     ecx, r12d
0x18005f3d4  cmp     ax, bx
0x18005f3d7  setz    cl
0x18005f3da  mov     [rbp+60h+pExceptionObject], ecx
0x18005f3dd  xorps   xmm8, xmm8
0x18005f3e1  movsxd  rbx, dword ptr [r13+1Ch]
0x18005f3e5  imul    rbx, rdi
0x18005f3e9  shl     rbx, 2
0x18005f3ed  xorps   xmm0, xmm0
0x18005f3f0  movdqu  [rbp+60h+var_90], xmm0
0x18005f3f5  mov     edi, r12d
0x18005f3f8  mov     [rsp+160h+var_100], r12
0x18005f3fd  mov     [rbp+60h+var_80], r12
0x18005f401  test    rbx, rbx
0x18005f404  jz      short loc_18005F44F
0x18005f406  mov     rax, 7FFFFFFFFFFFFFFFh
0x18005f410  cmp     rbx, rax
0x18005f413  ja      loc_18005F995
0x18005f419  mov     rcx, rbx
0x18005f41c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005f421  mov     [rbp+60h+arg_18], rax
0x18005f428  mov     qword ptr [rbp+60h+var_90], rax
0x18005f42c  lea     rdi, [rax+rbx]
0x18005f430  mov     [rsp+160h+var_100], rdi
0x18005f435  mov     [rbp+60h+var_80], rdi
0x18005f439  mov     r8, rbx; Size
0x18005f43c  xor     edx, edx; Val
0x18005f43e  mov     rbx, rax
0x18005f441  mov     rcx, rax; void *
0x18005f444  call    memset
0x18005f449  mov     qword ptr [rbp+60h+var_90+8], rdi
0x18005f44d  jmp     short loc_18005F45A
0x18005f44f  mov     rbx, qword ptr [rbp+60h+var_90]
0x18005f453  mov     [rbp+60h+arg_18], rbx
0x18005f45a  mov     r11, r12
0x18005f45d  mov     [rsp+160h+var_128], r12
0x18005f462  mov     rdx, r12
0x18005f465  mov     [rsp+160h+var_108], rdx
0x18005f46a  lea     rdi, [rsi+10h]
0x18005f46e  cmp     r12w, [rdi]
0x18005f472  jnb     loc_18005F7FD
0x18005f478  movdqa  xmm7, cs:__xmm@0c0d0e0f08090a0b0405060700010203
0x18005f480  mov     rcx, [rsp+160h+var_130]
0x18005f485  nop     word ptr [rax+rax+00000000h]
0x18005f490  xor     eax, eax
0x18005f492  cmp     ax, [rsi+12h]
0x18005f496  jnb     loc_18005F7D7
0x18005f49c  mov     eax, dword ptr [rsp+160h+var_EC]
0x18005f4a0  mov     [rbp+60h+var_98], rax
0x18005f4a4  cmp     rdx, rax
0x18005f4a7  jnb     loc_18005F7D2
0x18005f4ad  mov     rcx, [rsi+5D158h]
0x18005f4b4  mov     rax, [rcx]
0x18005f4b7  xor     r8d, r8d
0x18005f4ba  mov     r9, qword ptr [rbp+60h+var_D0]
0x18005f4be  mov     rdx, [r9+rdx*8]
0x18005f4c2  mov     rax, [rax+18h]
0x18005f4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4cb  movzx   edx, word ptr [rdi]
0x18005f4ce  mov     r11, [rsp+160h+var_128]
0x18005f4d3  mov     r8, [rsp+160h+var_130]
0x18005f4d8  lea     rax, [r8+r11]
0x18005f4dc  mov     ecx, edx
0x18005f4de  sub     rcx, r11
0x18005f4e1  mov     r9, r8
0x18005f4e4  cmp     rax, rdx
0x18005f4e7  cmova   r9, rcx
0x18005f4eb  mov     [rsp+160h+var_110], r9
0x18005f4f0  movzx   r8d, word ptr [rsi+12h]
0x18005f4f5  mov     r10d, dword ptr [rsp+160h+var_EC+4]
0x18005f4fa  lea     eax, [r12+r10]
0x18005f4fe  mov     ecx, r8d
0x18005f501  sub     ecx, r12d
0x18005f504  mov     edx, r10d
0x18005f507  cmp     eax, r8d
0x18005f50a  cmova   edx, ecx
0x18005f50d  movsxd  r8, dword ptr [r13+1Ch]
0x18005f511  mov     rcx, r8
0x18005f514  mov     eax, edx
0x18005f516  imul    rcx, rax
0x18005f51a  movsxd  rax, r14d
0x18005f51d  imul    rax, rcx
0x18005f521  mov     [rsp+160h+var_118], rax
0x18005f526  imul    r8d, r10d
0x18005f52a  imul    r8d, r14d
0x18005f52e  mov     [rbp+60h+arg_10], r8d
0x18005f535  lea     rcx, ds:0[rcx*4]
0x18005f53d  mov     [rbp+60h+Size], rcx
0x18005f541  test    r9, r9
0x18005f544  jz      loc_18005F7AA
0x18005f54a  movsxd  rdi, r8d
0x18005f54d  mov     r15, r11
0x18005f550  cmp     rdi, rax
0x18005f553  ja      short loc_18005F574
0x18005f555  movzx   ecx, word ptr [rsi+12h]
0x18005f559  imul    rcx, r15
0x18005f55d  mov     eax, r12d
0x18005f560  add     rcx, rax
0x18005f563  movsxd  rax, dword ptr [r13+1Ch]
0x18005f567  imul    rcx, rax
0x18005f56b  mov     rax, [rsp+160h+var_120]
0x18005f570  lea     rbx, [rax+rcx*4]
0x18005f574  mov     rcx, [rsi+5D158h]
0x18005f57b  mov     rax, [rcx]
0x18005f57e  mov     r9, rdi
0x18005f581  mov     r8d, 1
0x18005f587  mov     rdx, rbx
0x18005f58a  mov     rax, [rax+10h]
0x18005f58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f593  cmp     r14d, 2
0x18005f597  jnz     short loc_18005F5B8
0x18005f599  mov     eax, [rbp+60h+pExceptionObject]
0x18005f59c  cmp     [rbp+60h+arg_8], eax
0x18005f59f  jnz     loc_18005F730
0x18005f5a5  mov     r8, rdi; unsigned __int64
0x18005f5a8  mov     rdx, rbx; void *
0x18005f5ab  mov     rcx, rsi; this
0x18005f5ae  call    ?libraw_swab@LibRaw@@IEAAXPEAX_K@Z; LibRaw::libraw_swab(void *,unsigned __int64)
0x18005f5b3  jmp     loc_18005F730
0x18005f5b8  cmp     r14d, 3
0x18005f5bc  jnz     short loc_18005F61F
0x18005f5be  mov     eax, 4949h
0x18005f5c3  cmp     [rsi+5D1E0h], ax
0x18005f5ca  jnz     loc_18005F730
0x18005f5d0  mov     eax, [rbp+60h+arg_10]
0x18005f5d6  add     eax, 0FFFFFFFEh
0x18005f5d9  movsxd  rcx, eax
0x18005f5dc  test    eax, eax
0x18005f5de  jle     loc_18005F730
0x18005f5e4  mov     r8, rbx
0x18005f5e7  dec     rcx
0x18005f5ea  mov     rax, 0AAAAAAAAAAAAAAABh
0x18005f5f4  mul     rcx
0x18005f5f7  shr     rdx, 1
0x18005f5fa  inc     rdx
0x18005f5fd  nop     dword ptr [rax]
0x18005f600  movzx   ecx, byte ptr [r8]
0x18005f604  movzx   eax, byte ptr [r8+2]
0x18005f609  mov     [r8], al
0x18005f60c  mov     [r8+2], cl
0x18005f610  lea     r8, [r8+3]
0x18005f614  sub     rdx, 1
0x18005f618  jnz     short loc_18005F600
0x18005f61a  jmp     loc_18005F730
0x18005f61f  cmp     r14d, 4
0x18005f623  jnz     loc_18005F730
0x18005f629  mov     eax, [rbp+60h+pExceptionObject]
0x18005f62c  cmp     [rbp+60h+arg_8], eax
0x18005f62f  jnz     loc_18005F730
0x18005f635  mov     eax, [rbp+60h+arg_10]
0x18005f63b  cdq
0x18005f63c  and     edx, 3
0x18005f63f  add     eax, edx
0x18005f641  sar     eax, 2
0x18005f644  movsxd  r8, eax
0x18005f647  xor     eax, eax
0x18005f649  mov     ecx, eax
0x18005f64b  test    r8d, r8d
0x18005f64e  jle     loc_18005F718
0x18005f654  cmp     r8d, 2
0x18005f658  jb      loc_18005F718
0x18005f65e  cmp     cs:__isa_available, 2
0x18005f665  jl      loc_18005F718
0x18005f66b  cmp     r8d, 10h
0x18005f66f  jb      short loc_18005F6E0
0x18005f671  mov     edx, r8d
0x18005f674  and     edx, 8000000Fh
0x18005f67a  jge     short loc_18005F683
0x18005f67c  dec     edx
0x18005f67e  or      edx, 0FFFFFFF0h
0x18005f681  inc     edx
0x18005f683  mov     eax, r8d
0x18005f686  sub     eax, edx
0x18005f688  movsxd  rdx, eax
0x18005f68b  lea     rax, [rbx+20h]
0x18005f68f  nop
0x18005f690  movdqu  xmm0, xmmword ptr [rax-20h]
0x18005f695  pshufb  xmm0, xmm7
0x18005f69a  movdqu  xmmword ptr [rax-20h], xmm0
0x18005f69f  movdqu  xmm0, xmmword ptr [rax-10h]
0x18005f6a4  pshufb  xmm0, xmm7
0x18005f6a9  movdqu  xmmword ptr [rax-10h], xmm0
0x18005f6ae  movdqu  xmm1, xmmword ptr [rax]
0x18005f6b2  pshufb  xmm1, xmm7
0x18005f6b7  movdqu  xmmword ptr [rax], xmm1
0x18005f6bb  movdqu  xmm0, xmmword ptr [rax+10h]
0x18005f6c0  pshufb  xmm0, xmm7
0x18005f6c5  movdqu  xmmword ptr [rax+10h], xmm0
0x18005f6ca  add     rcx, 10h
0x18005f6ce  lea     rax, [rax+40h]
0x18005f6d2  cmp     rcx, rdx
0x18005f6d5  jl      short loc_18005F690
0x18005f6d7  mov     eax, r8d
0x18005f6da  and     al, 0Fh
0x18005f6dc  cmp     al, 2
0x18005f6de  jb      short loc_18005F718
0x18005f6e0  mov     edx, r8d
0x18005f6e3  and     edx, 80000001h
0x18005f6e9  jge     short loc_18005F6F2
0x18005f6eb  dec     edx
0x18005f6ed  or      edx, 0FFFFFFFEh
0x18005f6f0  inc     edx
0x18005f6f2  mov     eax, r8d
  ... truncated ...
```

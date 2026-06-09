# Input::EvenTime::StartCreateStrategy(Input::EvenTime &,Input::DerivativeFilter &,Input::OddFilter<uchar,130,130> &,Input::ActivePixel &)

- ea: `0x18001e120`
- end: `0x18001e7e1`
- name: `?StartCreateStrategy@EvenTime@Input@@SAAEAVEllipticActivity@2@AEAV12@AEAVDerivativeFilter@2@AEAV?$OddFilter@E$0IC@$0IC@@2@AEAVActivePixel@2@@Z`
- size: `1729`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4b0`
- `0x18001bc70`
- `0x18001e120`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall Input::EvenTime::StartCreateStrategy(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // r14d
  __int16 v5; // si
  __int64 epi16; // r9
  char *v8; // r11
  __int16 v9; // r15
  __int16 v10; // bx
  unsigned int v11; // eax
  char v13; // r10
  __m128i v14; // xmm1
  __m128i v15; // xmm2
  __m128i v16; // xmm4
  __m128i v17; // xmm3
  __int16 v18; // di
  __m128i v19; // xmm0
  __m128i v20; // xmm1
  __m128i v21; // xmm4
  __int64 v22; // rcx
  __int64 v23; // rax
  char *v24; // rdx
  unsigned int v25; // r10d
  unsigned int v26; // eax
  _BYTE *v27; // r11
  __m128i v28; // xmm3
  void (__fastcall *MixedProvider)(__int64 (__fastcall *)(), unsigned __int64, __int64); // rax
  __m128i v33; // [rsp+30h] [rbp-48h] BYREF
  _BYTE *retaddr; // [rsp+78h] [rbp+0h]

  v4 = 0;
  v5 = v33.m128i_i16[2];
  epi16 = v33.m128i_u16[7];
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v33.m128i_i32[0] = 0;
  v11 = 0;
  v13 = 1;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
LABEL_2:
  v19 = _mm_loadu_si128(&v33);
  while ( 1 )
  {
    while ( v11 <= 0x16EEEC )
    {
      if ( v11 == 1502956 )
      {
        if ( v5 == v10 )
        {
          v22 = *(int *)(v8 + 1);
          v13 = 1;
          if ( v22 <= 0 )
          {
            if ( v22 < 0 )
            {
              v11 = 2;
              if ( (__int64)&loc_18001BC73 + 2 < (__int64)(0x8000000000000000uLL - v22) )
                goto LABEL_27;
            }
          }
          else if ( (__int64)&loc_18001BC73 + 2 > 0x7FFFFFFFFFFFFFFFLL - v22 )
          {
            v11 = 2;
LABEL_27:
            v8 = (char *)&loc_18001BC73 + v22 + 2;
            goto LABEL_28;
          }
          v11 = 214708;
          goto LABEL_27;
        }
LABEL_28:
        if ( v18 == v10 )
        {
          v23 = v8[1];
          v24 = (char *)Input::EvenTime::FormulateImportantQuality + 2;
          v13 = 1;
          if ( (char)v23 <= 0 )
          {
            if ( (v23 & 0x80u) != 0LL && (__int64)v24 < (__int64)(0x8000000000000000uLL - v23) )
              goto LABEL_31;
          }
          else if ( (__int64)v24 > 0x7FFFFFFFFFFFFFFFLL - v23 )
          {
            goto LABEL_31;
          }
          v8 = &v24[v23];
          v11 = 214708;
        }
        else if ( v11 != 214708 )
        {
          v11 = 1717664;
        }
      }
      else
      {
        if ( v11 <= 0x9D41C )
        {
          if ( v11 == 644124 )
          {
            v5 = 11417;
            v33.m128i_i64[0] = 0x303C2C9904672CFBLL;
            v21 = _mm_cvtsi32_si128(v10);
            v18 = 11515;
            v11 = 858832;
            v16 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v21, v21), 0), v14);
          }
          else if ( v11 )
          {
            if ( v11 == 214708 )
            {
              v10 = -1;
              v33.m128i_i16[6] = 9996;
              v9 = 49 * (unsigned __int8)*v8;
              v11 = 429416;
            }
            else
            {
              v33.m128i_i16[4] = 8330;
              v20 = _mm_cvtsi32_si128(v9);
              v11 = 644124;
              v14 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v20, v20), 0);
            }
          }
          else
          {
            v33.m128i_i16[5] = 12348;
            epi16 = 9212;
            v33.m128i_i16[7] = 9212;
            v11 = 214708;
            v8 = (char *)Input::EvenTime::FormulateImportantQuality;
          }
          goto LABEL_2;
        }
        if ( v11 == 858832 )
        {
          v15 = v19;
          v11 = 1932372;
        }
        else if ( v11 == 1073540 )
        {
          v15 = _mm_and_si128(v15, v14);
          v13 = 0;
          v11 = 1288248;
          v14 = _mm_and_si128(v17, v16);
        }
        else
        {
          v14 = _mm_or_si128(v14, v15);
          v19 = v14;
          v18 = _mm_cvtsi128_si32(v14);
          v33 = v14;
          epi16 = (unsigned int)_mm_extract_epi16(v14, 7);
          v5 = _mm_extract_epi16(v14, 2);
          if ( (unsigned __int16)_mm_extract_epi16(v14, 6) == v10 )
          {
            v13 = 1;
            v11 = 1717664;
          }
          else
          {
            v11 = 1502956;
          }
        }
      }
    }
    if ( v11 == 1717664 )
      break;
    v28 = _mm_cvtsi32_si128(v10);
    v11 = 1073540;
    v17 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v28, v28), 0), v15);
  }
  if ( !v13 )
  {
LABEL_31:
    v25 = IntegralRelation::OddMap;
    goto LABEL_32;
  }
  v25 = ++IntegralRelation::OddMap;
LABEL_32:
  LOBYTE(epi16) = 1;
  v26 = 49732;
  v27 = 0;
  while ( 1 )
  {
    while ( v26 <= 0x1EC1C6 )
    {
      switch ( v26 )
      {
        case 0x1EC1C6u:
          v26 = 2015740;
          if ( (_BYTE)epi16 != 1 )
            v26 = 2065401;
          break;
        case 0xC244u:
          LOBYTE(epi16) = 0;
          v26 = 2015686;
          break;
        case 0xC255u:
          epi16 = (unsigned __int8)epi16;
          v26 = 2015686;
          if ( (v25 ^ 0xFBE5201C) == 0x204C4F )
            v26 = 2116687;
          else
            epi16 = 1;
          break;
        default:
          epi16 = (unsigned __int8)epi16;
          v26 = 2015686;
          if ( *v27 == (unsigned __int8)((v25 ^ v4) / 0x21D1FE) )
            epi16 = 1;
          else
            v26 = 2015740;
          break;
      }
    }
    if ( v26 == 2015740 )
      break;
    if ( v26 == 2065401 )
    {
      v27 = retaddr;
      v26 = 49749;
    }
    else
    {
      v26 = 49803;
      v4 = -516539845;
    }
  }
  if ( (_BYTE)epi16 )
    IntegralRelation::OddMap = v25 + 1;
  MixedProvider = (void (__fastcall *)(__int64 (__fastcall *)(), unsigned __int64, __int64))GenerateMixedProvider(
                                                                                              0xAF6F7FBF60804060uLL,
                                                                                              1104445546,
                                                                                              0x7FFFFFFFFFFFFFFFLL,
                                                                                              epi16);
  MixedProvider(
    Input::EvenTime::StartCreateStrategy,
    (unsigned __int64)Input::EvenTime::StartCreateStrategy ^ 0x1BEF83,
    782195);
  return Input::EvenTime::FormulateImportantQuality(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001e120  mov     [rsp+arg_8], rbx
0x18001e125  push    rbp
0x18001e126  push    rsi
0x18001e127  push    rdi
0x18001e128  push    r12
0x18001e12a  push    r13
0x18001e12c  push    r14
0x18001e12e  push    r15
0x18001e130  sub     rsp, 40h
0x18001e134  movzx   ebp, word ptr [rsp+78h+var_48+6]
0x18001e139  xor     r14d, r14d
0x18001e13c  movzx   esi, word ptr [rsp+78h+var_48+4]
0x18001e141  mov     r12, r9
0x18001e144  movzx   r9d, word ptr [rsp+78h+var_48+0Eh]
0x18001e14a  mov     r11d, r14d
0x18001e14d  mov     [rsp+78h+var_58], r8
0x18001e152  movzx   r15d, r14w
0x18001e156  movzx   ebx, r14w
0x18001e15a  mov     dword ptr [rsp+78h+var_48], r14d
0x18001e15f  mov     eax, r14d
0x18001e162  mov     [rsp+78h+var_50], rcx
0x18001e167  mov     r13, rdx
0x18001e16a  mov     r10b, 1
0x18001e16d  xorps   xmm1, xmm1
0x18001e170  xorps   xmm2, xmm2
0x18001e173  xorps   xmm4, xmm4
0x18001e176  xorps   xmm3, xmm3
0x18001e179  mov     r8, 7FFFFFFFFFFFFFFFh
0x18001e183  mov     edx, 303Ch
0x18001e188  movzx   edi, r14w
0x18001e18c  mov     ecx, 1
0x18001e191  movdqu  xmm0, [rsp+78h+var_48]
0x18001e197  nop     word ptr [rax+rax+00000000h]
0x18001e1a0  cmp     eax, 16EEECh
0x18001e1a5  ja      loc_18001E44D
0x18001e1ab  jz      loc_18001E2F7
0x18001e1b1  cmp     eax, 9D41Ch
0x18001e1b6  ja      loc_18001E26E
0x18001e1bc  jz      short loc_18001E236
0x18001e1be  test    eax, eax
0x18001e1c0  jz      short loc_18001E213
0x18001e1c2  cmp     eax, 346B4h
0x18001e1c7  jz      short loc_18001E1F2
0x18001e1c9  cmp     eax, 68D68h
0x18001e1ce  jnz     short loc_18001E1A0
0x18001e1d0  mov     eax, 208Ah
0x18001e1d5  mov     word ptr [rsp+78h+var_48+8], ax
0x18001e1da  movsx   eax, r15w
0x18001e1de  movd    xmm1, eax
0x18001e1e2  mov     eax, 9D41Ch
0x18001e1e7  punpcklwd xmm1, xmm1
0x18001e1eb  pshufd  xmm1, xmm1, 0
0x18001e1f0  jmp     short loc_18001E191
0x18001e1f2  mov     eax, 270Ch
0x18001e1f7  mov     ebx, 0FFFFh
0x18001e1fc  mov     word ptr [rsp+78h+var_48+0Ch], ax
0x18001e201  movzx   eax, byte ptr [r11]
0x18001e205  imul    r15d, eax, 31h ; '1'
0x18001e209  mov     eax, 68D68h
0x18001e20e  jmp     loc_18001E18C
0x18001e213  mov     eax, 23FCh
0x18001e218  mov     word ptr [rsp+78h+var_48+0Ah], dx
0x18001e21d  mov     r9d, eax
0x18001e220  mov     word ptr [rsp+78h+var_48+0Eh], ax
0x18001e225  mov     eax, 346B4h
0x18001e22a  lea     r11, ?FormulateImportantQuality@EvenTime@Input@@QEAAAEAVEllipticActivity@2@AEAVDerivativeFilter@2@AEAV?$OddFilter@E$0IC@$0IC@@2@AEAVActivePixel@2@@Z; Input::EvenTime::FormulateImportantQuality(Input::DerivativeFilter &,Input::OddFilter<uchar,130,130> &,Input::ActivePixel &)
0x18001e231  jmp     loc_18001E191
0x18001e236  movsx   eax, bx
0x18001e239  mov     esi, 2C99h
0x18001e23e  mov     ebp, edx
0x18001e240  mov     dword ptr [rsp+78h+var_48+4], 303C2C99h
0x18001e248  mov     dword ptr [rsp+78h+var_48], 4672CFBh
0x18001e250  movd    xmm4, eax
0x18001e254  lea     edi, [rsi+62h]
0x18001e257  punpcklwd xmm4, xmm4
0x18001e25b  mov     eax, 0D1AD0h
0x18001e260  pshufd  xmm4, xmm4, 0
0x18001e265  pxor    xmm4, xmm1
0x18001e269  jmp     loc_18001E191
0x18001e26e  cmp     eax, 0D1AD0h
0x18001e273  jz      short loc_18001E2E9
0x18001e275  cmp     eax, 106184h
0x18001e27a  jz      short loc_18001E2D0
0x18001e27c  cmp     eax, 13A838h
0x18001e281  jnz     loc_18001E1A0
0x18001e287  por     xmm1, xmm2
0x18001e28b  mov     ecx, 1
0x18001e290  pextrw  eax, xmm1, 6
0x18001e295  movdqa  xmm0, xmm1
0x18001e299  movd    edi, xmm1
0x18001e29d  movdqu  [rsp+78h+var_48], xmm1
0x18001e2a3  pextrw  r9d, xmm1, 7
0x18001e2a9  pextrw  ebp, xmm1, 3
0x18001e2ae  pextrw  esi, xmm1, 2
0x18001e2b3  cmp     ax, bx
0x18001e2b6  jnz     short loc_18001E2C6
0x18001e2b8  movzx   r10d, cl
0x18001e2bc  mov     eax, 1A35A0h
0x18001e2c1  jmp     loc_18001E1A0
0x18001e2c6  mov     eax, 16EEECh
0x18001e2cb  jmp     loc_18001E1A0
0x18001e2d0  pand    xmm2, xmm1
0x18001e2d4  xor     r10b, r10b
0x18001e2d7  movdqa  xmm1, xmm3
0x18001e2db  mov     eax, 13A838h
0x18001e2e0  pand    xmm1, xmm4
0x18001e2e4  jmp     loc_18001E1A0
0x18001e2e9  movdqa  xmm2, xmm0
0x18001e2ed  mov     eax, 1D7C54h
0x18001e2f2  jmp     loc_18001E1A0
0x18001e2f7  cmp     si, bx
0x18001e2fa  jnz     short loc_18001E351
0x18001e2fc  movsxd  rcx, dword ptr [r11+1]
0x18001e300  lea     rdx, ?FormulateImportantQuality@EvenTime@Input@@QEAAAEAVEllipticActivity@2@AEAVDerivativeFilter@2@AEAV?$OddFilter@E$0IC@$0IC@@2@AEAVActivePixel@2@@Z; Input::EvenTime::FormulateImportantQuality(Input::DerivativeFilter &,Input::OddFilter<uchar,130,130> &,Input::ActivePixel &)
0x18001e307  add     rdx, 5
0x18001e30b  mov     r10b, 1
0x18001e30e  test    rcx, rcx
0x18001e311  jle     short loc_18001E325
0x18001e313  mov     rax, r8
0x18001e316  sub     rax, rcx
0x18001e319  cmp     rdx, rax
0x18001e31c  jle     short loc_18001E33E
0x18001e31e  mov     eax, 2
0x18001e323  jmp     short loc_18001E343
0x18001e325  jns     short loc_18001E33E
0x18001e327  mov     rax, 8000000000000000h
0x18001e331  sub     rax, rcx
0x18001e334  cmp     rdx, rax
0x18001e337  mov     eax, 2
0x18001e33c  jl      short loc_18001E343
0x18001e33e  mov     eax, 346B4h
0x18001e343  lea     r11, [rdx+rcx]
0x18001e347  mov     edx, 303Ch
0x18001e34c  mov     ecx, 1
0x18001e351  cmp     di, bx
0x18001e354  jnz     loc_18001E438
0x18001e35a  movsx   rax, byte ptr [r11+1]
0x18001e35f  lea     rdx, ?FormulateImportantQuality@EvenTime@Input@@QEAAAEAVEllipticActivity@2@AEAVDerivativeFilter@2@AEAV?$OddFilter@E$0IC@$0IC@@2@AEAVActivePixel@2@@Z; Input::EvenTime::FormulateImportantQuality(Input::DerivativeFilter &,Input::OddFilter<uchar,130,130> &,Input::ActivePixel &)
0x18001e366  add     rdx, 2
0x18001e36a  mov     r10b, 1
0x18001e36d  mov     rcx, rax
0x18001e370  test    al, al
0x18001e372  jle     loc_18001E408
0x18001e378  mov     rax, r8
0x18001e37b  sub     rax, rcx
0x18001e37e  cmp     rdx, rax
0x18001e381  jle     loc_18001E420
0x18001e387  mov     r10d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18001e38e  mov     r9b, 1
0x18001e391  mov     eax, 0C244h
0x18001e396  mov     r11, r14
0x18001e399  mov     edi, 1EC1FCh
0x18001e39e  mov     ebx, 204C4Fh
0x18001e3a3  mov     esi, 1F83F9h
0x18001e3a8  mov     ebp, 1
0x18001e3ad  nop     dword ptr [rax]
0x18001e3b0  cmp     eax, 1EC1C6h
0x18001e3b5  ja      loc_18001E742
0x18001e3bb  jz      loc_18001E735
0x18001e3c1  mov     ecx, eax
0x18001e3c3  sub     ecx, 0C244h
0x18001e3c9  jz      loc_18001E728
0x18001e3cf  sub     ecx, 11h
0x18001e3d2  jz      loc_18001E708
0x18001e3d8  cmp     ecx, 36h ; '6'
0x18001e3db  jnz     short loc_18001E3B0
0x18001e3dd  mov     ecx, r14d
0x18001e3e0  movzx   r9d, r9b
0x18001e3e4  xor     ecx, r10d
0x18001e3e7  mov     eax, 0E4716AA7h
0x18001e3ec  mul     ecx
0x18001e3ee  mov     eax, 1EC1C6h
0x18001e3f3  sub     ecx, edx
0x18001e3f5  shr     ecx, 1
0x18001e3f7  add     ecx, edx
0x18001e3f9  shr     ecx, 15h
0x18001e3fc  cmp     [r11], cl
0x18001e3ff  cmovz   r9d, ebp
0x18001e403  cmovnz  eax, edi
0x18001e406  jmp     short loc_18001E3B0
0x18001e408  jns     short loc_18001E420
0x18001e40a  mov     rax, 8000000000000000h
0x18001e414  sub     rax, rcx
0x18001e417  cmp     rdx, rax
0x18001e41a  jl      loc_18001E387
0x18001e420  lea     r11, [rcx+rdx]
0x18001e424  mov     eax, 346B4h
0x18001e429  mov     edx, 303Ch
0x18001e42e  mov     ecx, 1
0x18001e433  jmp     loc_18001E1A0
0x18001e438  cmp     eax, 346B4h
0x18001e43d  jz      loc_18001E1A0
0x18001e443  mov     eax, 1A35A0h
0x18001e448  jmp     loc_18001E1A0
0x18001e44d  cmp     eax, 3AF8A8h
0x18001e452  ja      loc_18001E5A4
0x18001e458  jz      loc_18001E4E9
0x18001e45e  cmp     eax, 1A35A0h
0x18001e463  jz      loc_18001E6E9
0x18001e469  cmp     eax, 1D7C54h
0x18001e46e  jz      short loc_18001E4CB
0x18001e470  cmp     eax, 37B1F4h
0x18001e475  jnz     loc_18001E1A0
0x18001e47b  test    r11, r11
0x18001e47e  jnz     short loc_18001E48A
0x18001e480  mov     eax, 1A35A0h
0x18001e485  jmp     loc_18001E1A0
0x18001e48a  movdqa  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001e492  mov     eax, 208Ah
0x18001e497  mov     word ptr [rsp+78h+var_48+8], ax
0x18001e49c  mov     esi, 31h ; '1'
0x18001e4a1  mov     dword ptr [rsp+78h+var_48+4], 28940031h
0x18001e4a9  mov     ebp, 2894h
0x18001e4ae  movdqu  xmm0, [rsp+78h+var_48]
0x18001e4b4  mov     ebx, 0FFFFh
0x18001e4b9  mov     eax, 3AF8A8h
0x18001e4be  movdqa  xmm2, xmm0
0x18001e4c2  pxor    xmm3, xmm0
0x18001e4c6  jmp     loc_18001E1A0
0x18001e4cb  movsx   eax, bx
0x18001e4ce  movd    xmm3, eax
0x18001e4d2  mov     eax, 106184h
0x18001e4d7  punpcklwd xmm3, xmm3
0x18001e4db  pshufd  xmm3, xmm3, 0
0x18001e4e0  pxor    xmm3, xmm2
0x18001e4e4  jmp     loc_18001E1A0
0x18001e4e9  movzx   r10d, byte ptr [r11]
0x18001e4ed  movzx   r9d, byte ptr [r11+2]
0x18001e4f2  movzx   eax, r10b
0x18001e4f6  movzx   edx, byte ptr [r11+3]
0x18001e4fb  shl     al, 3
0x18001e4fe  movzx   eax, al
0x18001e501  imul    eax, 31h ; '1'
0x18001e504  imul    ecx, edx, 31h ; '1'
0x18001e507  shr     dl, 2
0x18001e50a  mov     word ptr [rsp+78h+var_48], ax
0x18001e50f  movzx   edi, ax
0x18001e512  movzx   eax, byte ptr [r11+1]
0x18001e517  movzx   ebp, cx
0x18001e51a  imul    r8d, eax, 31h ; '1'
0x18001e51e  movzx   eax, r9b
0x18001e522  shr     al, 5
0x18001e525  movzx   eax, al
0x18001e528  imul    eax, 31h ; '1'
0x18001e52b  mov     word ptr [rsp+78h+var_48+6], cx
0x18001e530  imul    ecx, r10d, 31h ; '1'
0x18001e534  mov     word ptr [rsp+78h+var_48+2], r8w
0x18001e53a  mov     word ptr [rsp+78h+var_48+0Ah], r8w
0x18001e540  mov     r8, 7FFFFFFFFFFFFFFFh
0x18001e54a  mov     word ptr [rsp+78h+var_48+4], ax
0x18001e54f  movzx   esi, ax
0x18001e552  movzx   eax, dl
0x18001e555  mov     edx, 303Ch
0x18001e55a  imul    eax, 31h ; '1'
0x18001e55d  mov     word ptr [rsp+78h+var_48+8], cx
0x18001e562  imul    ecx, r9d, 31h ; '1'
0x18001e566  xor     r10b, r10b
0x18001e569  mov     word ptr [rsp+78h+var_48+0Eh], ax
0x18001e56e  movzx   r9d, ax
0x18001e572  movsx   eax, bx
0x18001e575  mov     word ptr [rsp+78h+var_48+0Ch], cx
0x18001e57a  mov     ecx, 1
0x18001e57f  movdqu  xmm0, [rsp+78h+var_48]
0x18001e585  movd    xmm4, eax
0x18001e589  mov     eax, 3E3F5Ch
0x18001e58e  punpcklwd xmm4, xmm4
0x18001e592  movdqa  xmm1, xmm0
0x18001e596  pshufd  xmm4, xmm4, 0
0x18001e59b  pxor    xmm4, xmm0
0x18001e59f  jmp     loc_18001E1A0
0x18001e5a4  cmp     eax, 3E3F5Ch
0x18001e5a9  jz      loc_18001E6AC
0x18001e5af  cmp     eax, 418610h
0x18001e5b4  jz      short loc_18001E5E1
0x18001e5b6  cmp     eax, 44CCC4h
0x18001e5bb  jnz     loc_18001E1A0
0x18001e5c1  mov     eax, 0F5h
0x18001e5c6  mov     dword ptr [rsp+78h+var_48+0Ah], 23FC303Ch
0x18001e5ce  movzx   r9d, ax
0x18001e5d2  mov     word ptr [rsp+78h+var_48+0Eh], ax
0x18001e5d7  mov     eax, 37B1F4h
0x18001e5dc  jmp     loc_18001E191
0x18001e5e1  cmp     bp, bx
0x18001e5e4  jnz     short loc_18001E5F6
0x18001e5e6  cmp     di, bx
0x18001e5e9  jnz     short loc_18001E5F6
0x18001e5eb  cmp     si, bx
0x18001e5ee  movzx   r10d, r10b
0x18001e5f2  cmovz   r10d, ecx
0x18001e5f6  cmp     r9w, bx
0x18001e5fa  jnz     loc_18001E480
0x18001e600  movzx   eax, byte ptr [r11+3]
0x18001e605  and     al, 3
0x18001e607  movzx   r8d, al
0x18001e60b  test    r8b, 2
0x18001e60f  lea     eax, [r8-4]
0x18001e613  movzx   ecx, al
0x18001e616  movzx   eax, byte ptr [r11+2]
0x18001e61b  cmovz   ecx, r8d
0x18001e61f  movsx   edx, cl
  ... truncated ...
```

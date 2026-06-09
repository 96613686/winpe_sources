# Input::ShortTermSource::IgnoreConstructInput<2>(Input::OddFilter<Input::IntegralSink<ushort,13,uint>,65,128> const &,Input::TemporaryArea<Input::IntegralSink<short,11,int>> const &,int)

- ea: `0x1800805c0`
- end: `0x180080c08`
- name: `??$IgnoreConstructInput@$01@ShortTermSource@Input@@QEAA?AV?$IntegralSink@G$07I@1@AEBV?$OddFilter@V?$IntegralSink@G$0N@I@Input@@$0EB@$0IA@@1@AEBV?$TemporaryArea@V?$IntegralSink@F$0L@H@Input@@@1@H@Z`
- size: `1608`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007f8d0`
- `0x18007f940`

## callees

- `0x180003180`
- `0x1800037c0`
- `0x1800805c0`

## pseudocode

```c
unsigned __int16 *__fastcall Input::ShortTermSource::IgnoreConstructInput<2>(
        __int64 a1,
        unsigned __int16 *a2,
        _QWORD *a3,
        __int16 *a4,
        int a5)
{
  int v5; // r15d
  __int16 *v6; // r10
  unsigned __int16 *v7; // r9
  __m128i v9; // xmm8
  __m128i si128; // xmm10
  __int64 v11; // r12
  __m128i v12; // xmm11
  unsigned __int64 v13; // r13
  __m128i v14; // xmm12
  __m128i v15; // xmm13
  __m128i v16; // xmm1
  __m128i v17; // xmm1
  __m128i v18; // xmm3
  __m128i v19; // xmm0
  __m128i v20; // xmm7
  __m128i v21; // xmm2
  __m128i v22; // xmm0
  __m128i v23; // xmm1
  __m128i v24; // xmm7
  __m128i v25; // xmm5
  __m128i v26; // xmm1
  __m128i v27; // xmm7
  __m128i v28; // xmm0
  __m128i v29; // xmm0
  __m128i v30; // xmm6
  __m128i v31; // xmm7
  __m128i v32; // xmm3
  __m128i v33; // xmm4
  __m128i v34; // xmm3
  int v35; // ebp
  int v36; // r11d
  unsigned __int64 v37; // r9
  __int64 v38; // r10
  __int64 v39; // rax
  unsigned __int64 v40; // r8
  __int64 v41; // rcx
  __int16 v42; // bx
  __int64 v43; // rdx
  __int16 v44; // r10
  __int16 v45; // di
  __int16 v46; // si
  __m128i v47; // xmm0
  __m128i v48; // xmm4
  __m128i v49; // xmm2
  __m128i v50; // xmm4
  __m128i v51; // xmm1
  __m128i v52; // xmm4
  __m128i v53; // xmm2
  __m128i v54; // xmm1
  __m128i v55; // xmm7
  __m128i v56; // xmm4
  __m128i v57; // xmm3
  __m128i v58; // xmm0
  __m128i v59; // xmm1
  __m128i v60; // xmm2
  __m128i v61; // xmm0
  __m128i v62; // xmm3
  __m128i v63; // xmm2
  __m128i v64; // xmm7
  __m128i v65; // xmm0
  __m128i v66; // xmm8
  __m128i v67; // xmm1
  unsigned __int16 v68; // r8
  float v69; // xmm1_4
  float v70; // xmm0_4
  __m128i v74; // [rsp+38h] [rbp-120h] BYREF
  __m128i v75; // [rsp+48h] [rbp-110h] BYREF
  __m128i v76; // [rsp+58h] [rbp-100h]
  __m128i v77; // [rsp+68h] [rbp-F0h]
  __m128i v78; // [rsp+78h] [rbp-E0h] BYREF
  __m128i v79; // [rsp+88h] [rbp-D0h] BYREF

  v5 = a5;
  v6 = a4;
  v7 = a2;
  v9 = 0;
  *a2 = 0;
  if ( a5 > 0 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v11 = a1 + 20;
    v12 = _mm_load_si128((const __m128i *)&_xmm_c040c040c040c040c040c040c040c040);
    v13 = 0;
    v14 = _mm_load_si128((const __m128i *)&_xmm);
    v15 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v16 = _mm_cvtsi32_si128(v6[1]);
      v17 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v16, v16), 0);
      v18 = _mm_slli_epi16(_mm_loadu_si128((const __m128i *)&Input::EllipticUnit::IntegralControl[v13 / 8]), 6u);
      v19 = _mm_cvtsi32_si128(*v6);
      v20 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v19, v19), 0);
      v21 = _mm_slli_epi16(_mm_loadu_si128((const __m128i *)&Input::EllipticUnit::CurvedImprovement[v13 / 8]), 6u);
      v22 = _mm_or_si128(_mm_srli_epi16(_mm_mullo_epi16(v17, v18), 0xBu), _mm_slli_epi16(_mm_mulhi_epi16(v17, v18), 5u));
      v23 = _mm_cvtsi32_si128(v6[3]);
      v24 = _mm_add_epi16(
              _mm_or_si128(
                _mm_srli_epi16(_mm_mullo_epi16(v20, v21), 0xBu),
                _mm_slli_epi16(_mm_mulhi_epi16(v20, v21), 5u)),
              v22);
      v25 = _mm_or_si128(_mm_cmpgt_epi16((__m128i)0LL, v24), si128);
      v26 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v23, v23), 0);
      v27 = _mm_mullo_epi16(v24, v25);
      v28 = _mm_cvtsi32_si128(v6[2]);
      v29 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v28, v28), 0);
      *(_WORD *)(v11 - 8) = _mm_cvtsi128_si32(v25);
      v30 = _mm_srai_epi16(v27, 6u);
      *(_DWORD *)(v11 - 16) = (__int16)_mm_cvtsi128_si32(v30);
      v31 = _mm_srli_epi16(_mm_slli_epi16(v27, 0xAu), 1u);
      *(_WORD *)(v11 - 10) = _mm_cvtsi128_si32(v31);
      v32 = _mm_min_epi16(
              _mm_max_epi16(
                _mm_mullo_epi16(
                  _mm_add_epi16(
                    _mm_or_si128(
                      _mm_srli_epi16(_mm_mullo_epi16(v29, v21), 0xBu),
                      _mm_slli_epi16(_mm_mulhi_epi16(v29, v21), 5u)),
                    _mm_or_si128(
                      _mm_srli_epi16(_mm_mullo_epi16(v26, v18), 0xBu),
                      _mm_slli_epi16(_mm_mulhi_epi16(v26, v18), 5u))),
                  v25),
                v12),
              v14);
      v33 = _mm_srai_epi16(v32, 6u);
      v34 = _mm_srli_epi16(_mm_slli_epi16(v32, 0xAu), 1u);
      *(_DWORD *)(v11 - 20) = (__int16)_mm_cvtsi128_si32(v33);
      *(_WORD *)(v11 - 12) = _mm_cvtsi128_si32(v34);
      *(_WORD *)(v11 + 8) = _mm_extract_epi16(v25, 1);
      *(_DWORD *)v11 = (__int16)_mm_extract_epi16(v30, 1);
      *(_WORD *)(v11 + 6) = _mm_extract_epi16(v31, 1);
      *(_DWORD *)(v11 - 4) = (__int16)_mm_extract_epi16(v33, 1);
      v35 = 0;
      v76 = v30;
      *(_WORD *)(v11 + 4) = _mm_extract_epi16(v34, 1);
      v77 = _mm_add_epi16(v15, v33);
      *(_WORD *)(v11 + 24) = _mm_extract_epi16(v25, 2);
      *(_DWORD *)(v11 + 16) = (__int16)_mm_extract_epi16(v30, 2);
      *(_WORD *)(v11 + 22) = _mm_extract_epi16(v31, 2);
      *(_DWORD *)(v11 + 12) = (__int16)_mm_extract_epi16(v33, 2);
      *(_WORD *)(v11 + 20) = _mm_extract_epi16(v34, 2);
      *(_WORD *)(v11 + 40) = _mm_extract_epi16(v25, 3);
      *(_DWORD *)(v11 + 32) = (__int16)_mm_extract_epi16(v30, 3);
      *(_WORD *)(v11 + 38) = _mm_extract_epi16(v31, 3);
      *(_DWORD *)(v11 + 28) = (__int16)_mm_extract_epi16(v33, 3);
      *(_WORD *)(v11 + 36) = _mm_extract_epi16(v34, 3);
      *(_WORD *)(v11 + 56) = _mm_extract_epi16(v25, 4);
      *(_DWORD *)(v11 + 48) = (__int16)_mm_extract_epi16(v30, 4);
      *(_WORD *)(v11 + 54) = _mm_extract_epi16(v31, 4);
      *(_DWORD *)(v11 + 44) = (__int16)_mm_extract_epi16(v33, 4);
      *(_WORD *)(v11 + 52) = _mm_extract_epi16(v34, 4);
      *(_WORD *)(v11 + 72) = _mm_extract_epi16(v25, 5);
      *(_DWORD *)(v11 + 64) = (__int16)_mm_extract_epi16(v30, 5);
      *(_WORD *)(v11 + 70) = _mm_extract_epi16(v31, 5);
      *(_DWORD *)(v11 + 60) = (__int16)_mm_extract_epi16(v33, 5);
      *(_WORD *)(v11 + 68) = _mm_extract_epi16(v34, 5);
      *(_WORD *)(v11 + 88) = _mm_extract_epi16(v25, 6);
      *(_DWORD *)(v11 + 80) = (__int16)_mm_extract_epi16(v30, 6);
      *(_WORD *)(v11 + 86) = _mm_extract_epi16(v31, 6);
      *(_DWORD *)(v11 + 76) = (__int16)_mm_extract_epi16(v33, 6);
      *(_WORD *)(v11 + 84) = _mm_extract_epi16(v34, 6);
      *(_WORD *)(v11 + 104) = _mm_extract_epi16(v25, 7);
      *(_DWORD *)(v11 + 96) = (__int16)_mm_extract_epi16(v30, 7);
      *(_WORD *)(v11 + 102) = _mm_extract_epi16(v31, 7);
      *(_DWORD *)(v11 + 92) = (__int16)_mm_extract_epi16(v33, 7);
      *(_WORD *)(v11 + 100) = _mm_extract_epi16(v34, 7);
      v36 = 0;
      v37 = 0;
      do
      {
        v38 = v76.m128i_u16[v37];
        if ( (unsigned int)v38 >= 0x40 || (v39 = v77.m128i_u16[v37], (unsigned int)v39 >= 0x7F) )
        {
          if ( v37 >= 8 )
            _report_rangecheckfailure();
          ++v35;
          v44 = 0;
          v42 = 0;
          v45 = 0;
          v46 = 0;
        }
        else
        {
          v40 = (unsigned __int64)v76.m128i_u16[v37] << 8;
          v41 = *a3 + 2 * v39;
          v42 = *(_WORD *)(v41 + v40);
          v43 = v38 + 1;
          v44 = *(_WORD *)(v41 + v40 + 2);
          v43 <<= 8;
          v45 = *(_WORD *)(v41 + v43 + 2);
          v46 = *(_WORD *)(v41 + v43);
        }
        ++v36;
        v75.m128i_i16[v37] = v46;
        v74.m128i_i16[v37] = v45;
        v78.m128i_i16[v37] = v42;
        v79.m128i_i16[v37++] = v44;
      }
      while ( v36 < 8 );
      v47 = _mm_loadu_si128(&v78);
      v6 = a4;
      v5 -= v35;
      v48 = _mm_load_si128((const __m128i *)&_xmm);
      v13 += 8LL;
      v49 = _mm_sub_epi16(v48, v31);
      v50 = _mm_sub_epi16(v48, v34);
      v11 += 128;
      v51 = _mm_mulhi_epu16(v49, v50);
      v52 = _mm_mulhi_epu16(v50, v31);
      v53 = _mm_slli_epi16(_mm_mulhi_epu16(v49, v34), 1u);
      v54 = _mm_slli_epi16(v51, 1u);
      v55 = _mm_slli_epi16(_mm_mulhi_epu16(v31, v34), 1u);
      v56 = _mm_slli_epi16(v52, 1u);
      v57 = _mm_or_si128(_mm_srli_epi16(_mm_mullo_epi16(v47, v54), 0xFu), _mm_slli_epi16(_mm_mulhi_epu16(v47, v54), 1u));
      v58 = _mm_loadu_si128(&v79);
      v59 = _mm_mullo_epi16(v53, v58);
      v60 = _mm_mulhi_epu16(v53, v58);
      v61 = _mm_loadu_si128(&v74);
      v62 = _mm_add_epi16(v57, _mm_or_si128(_mm_srli_epi16(v59, 0xFu), _mm_slli_epi16(v60, 1u)));
      v63 = _mm_mullo_epi16(v55, v61);
      v64 = _mm_mulhi_epu16(v55, v61);
      v65 = _mm_loadu_si128(&v75);
      v9 = _mm_add_epi16(
             v9,
             _mm_srli_epi16(
               _mm_add_epi16(
                 v62,
                 _mm_add_epi16(
                   _mm_or_si128(_mm_srli_epi16(v63, 0xFu), _mm_slli_epi16(v64, 1u)),
                   _mm_or_si128(
                     _mm_srli_epi16(_mm_mullo_epi16(v56, v65), 0xFu),
                     _mm_slli_epi16(_mm_mulhi_epu16(v56, v65), 1u)))),
               5u));
    }
    while ( (__int64)v13 < a5 );
    v7 = a2;
  }
  v66 = _mm_madd_epi16(v9, (__m128i)_xmm);
  v67 = _mm_add_epi32(_mm_srli_si128(v66, 8), v66);
  v68 = _mm_cvtsi128_si32(_mm_add_epi32(_mm_srli_si128(v67, 4), v67));
  *v7 = v68;
  if ( (unsigned int)(v5 - 1) <= 0x36 )
  {
    v69 = *(float *)&Input::ShortTermSource::ComprehensiveSolution[v5] * 8192.0;
    if ( v69 >= 0.0 )
      v70 = FLOAT_0_5;
    else
      v70 = FLOAT_N0_5;
    *v7 = (v68 * (unsigned int)(unsigned __int16)(int)(float)(v69 + v70)) >> 13;
  }
  return v7;
}

```

## disassembly

```asm
0x1800805c0  mov     rax, rsp
0x1800805c3  mov     [rax+8], rbx
0x1800805c7  push    rbp
0x1800805c8  push    rsi
0x1800805c9  push    rdi
0x1800805ca  push    r12
0x1800805cc  push    r13
0x1800805ce  push    r14
0x1800805d0  push    r15
0x1800805d2  sub     rsp, 120h
0x1800805d9  movaps  xmmword ptr [rax-48h], xmm6
0x1800805dd  movaps  xmmword ptr [rax-58h], xmm7
0x1800805e1  movaps  xmmword ptr [rax-68h], xmm8
0x1800805e6  movaps  xmmword ptr [rax-78h], xmm9
0x1800805eb  movaps  xmmword ptr [rax-88h], xmm10
0x1800805f3  movaps  xmmword ptr [rax-98h], xmm11
0x1800805fb  movaps  xmmword ptr [rax-0A8h], xmm12
0x180080603  movaps  xmmword ptr [rax-0B8h], xmm13
0x18008060b  mov     rax, cs:__security_cookie
0x180080612  xor     rax, rsp
0x180080615  mov     [rsp+158h+var_C0], rax
0x18008061d  movsxd  r15, [rsp+158h+arg_20]
0x180080625  lea     r11, cs:180000000h
0x18008062c  mov     r10, r9
0x18008062f  mov     [rsp+158h+var_130], r9
0x180080634  mov     r9, rdx
0x180080637  mov     [rsp+158h+var_128], rdx
0x18008063c  xor     edx, edx
0x18008063e  mov     r14, r8
0x180080641  xorps   xmm9, xmm9
0x180080645  xorps   xmm8, xmm8
0x180080649  mov     [r9], dx
0x18008064d  test    r15d, r15d
0x180080650  jle     loc_180080B2D
0x180080656  movdqa  xmm10, cs:__xmm@00010001000100010001000100010001
0x18008065f  lea     r12, [rcx+14h]
0x180080663  movdqa  xmm11, cs:__xmm@c040c040c040c040c040c040c040c040
0x18008066c  mov     r13d, edx
0x18008066f  movdqa  xmm12, cs:__xmm@3fc03fc03fc03fc03fc03fc03fc03fc0
0x180080678  movdqa  xmm13, cs:__xmm@00400040004000400040004000400040
0x180080681  mov     [rsp+158h+var_138], r15
0x180080686  movsx   eax, word ptr [r10+2]
0x18008068b  movdqa  xmm5, xmm9
0x180080690  movdqu  xmm2, ds:rva ?CurvedImprovement@EllipticUnit@Input@@2V?$OneContext@F$0DI@$00$0A@$0HA@@Data@@B[r11+r13*2]; Data::OneContext<short,56,1,0,112> const Input::EllipticUnit::CurvedImprovement ...
0x18008069a  movdqu  xmm3, ds:rva ?IntegralControl@EllipticUnit@Input@@2V?$OneContext@F$0DI@$00$0A@$0HA@@Data@@B[r11+r13*2]; Data::OneContext<short,56,1,0,112> const Input::EllipticUnit::IntegralControl ...
0x1800806a4  movd    xmm1, eax
0x1800806a8  movsx   eax, word ptr [r10]
0x1800806ac  punpcklwd xmm1, xmm1
0x1800806b0  pshufd  xmm1, xmm1, 0
0x1800806b5  psllw   xmm3, 6
0x1800806ba  movd    xmm0, eax
0x1800806be  movsx   eax, word ptr [r10+6]
0x1800806c3  punpcklwd xmm0, xmm0
0x1800806c7  pshufd  xmm0, xmm0, 0
0x1800806cc  movdqa  xmm7, xmm0
0x1800806d0  psllw   xmm2, 6
0x1800806d5  pmulhw  xmm0, xmm2
0x1800806d9  pmullw  xmm7, xmm2
0x1800806dd  psllw   xmm0, 5
0x1800806e2  psrlw   xmm7, 0Bh
0x1800806e7  por     xmm7, xmm0
0x1800806eb  movdqa  xmm0, xmm1
0x1800806ef  pmullw  xmm0, xmm3
0x1800806f3  pmulhw  xmm1, xmm3
0x1800806f7  psrlw   xmm0, 0Bh
0x1800806fc  psllw   xmm1, 5
0x180080701  por     xmm0, xmm1
0x180080705  movd    xmm1, eax
0x180080709  movsx   eax, word ptr [r10+4]
0x18008070e  paddw   xmm7, xmm0
0x180080712  pcmpgtw xmm5, xmm7
0x180080716  punpcklwd xmm1, xmm1
0x18008071a  por     xmm5, xmm10
0x18008071f  pshufd  xmm1, xmm1, 0
0x180080724  pmullw  xmm7, xmm5
0x180080728  movd    xmm0, eax
0x18008072c  punpcklwd xmm0, xmm0
0x180080730  pshufd  xmm0, xmm0, 0
0x180080735  movdqa  xmm4, xmm0
0x180080739  movd    eax, xmm5
0x18008073d  pmullw  xmm4, xmm2
0x180080741  movdqa  xmm6, xmm7
0x180080745  pmulhw  xmm0, xmm2
0x180080749  mov     [r12-8], ax
0x18008074f  psraw   xmm6, 6
0x180080754  movd    eax, xmm6
0x180080758  psrlw   xmm4, 0Bh
0x18008075d  psllw   xmm0, 5
0x180080762  por     xmm4, xmm0
0x180080766  cwde
0x180080767  mov     [r12-10h], eax
0x18008076c  movdqa  xmm0, xmm1
0x180080770  pmullw  xmm0, xmm3
0x180080774  pmulhw  xmm1, xmm3
0x180080778  psllw   xmm7, 0Ah
0x18008077d  psrlw   xmm7, 1
0x180080782  movd    eax, xmm7
0x180080786  psrlw   xmm0, 0Bh
0x18008078b  psllw   xmm1, 5
0x180080790  mov     [r12-0Ah], ax
0x180080796  por     xmm0, xmm1
0x18008079a  paddw   xmm4, xmm0
0x18008079e  pmullw  xmm4, xmm5
0x1800807a2  pmaxsw  xmm4, xmm11
0x1800807a7  pminsw  xmm4, xmm12
0x1800807ac  movdqa  xmm3, xmm4
0x1800807b0  psraw   xmm4, 6
0x1800807b5  movd    eax, xmm4
0x1800807b9  psllw   xmm3, 0Ah
0x1800807be  psrlw   xmm3, 1
0x1800807c3  cwde
0x1800807c4  mov     [r12-14h], eax
0x1800807c9  movd    eax, xmm3
0x1800807cd  mov     [r12-0Ch], ax
0x1800807d3  pextrw  eax, xmm5, 1
0x1800807d8  mov     [r12+8], ax
0x1800807de  pextrw  eax, xmm6, 1
0x1800807e3  movsx   ecx, ax
0x1800807e6  pextrw  eax, xmm7, 1
0x1800807eb  mov     [r12], ecx
0x1800807ef  mov     [r12+6], ax
0x1800807f5  pextrw  eax, xmm4, 1
0x1800807fa  movsx   ecx, ax
0x1800807fd  movdqa  xmm0, xmm13
0x180080802  mov     [r12-4], ecx
0x180080807  paddw   xmm0, xmm4
0x18008080b  pextrw  eax, xmm3, 1
0x180080810  mov     ebp, edx
0x180080812  movdqu  [rsp+158h+var_100], xmm6
0x180080818  mov     [r12+4], ax
0x18008081e  pextrw  eax, xmm5, 2
0x180080823  movdqu  [rsp+158h+var_F0], xmm0
0x180080829  mov     [r12+18h], ax
0x18008082f  pextrw  eax, xmm6, 2
0x180080834  movsx   ecx, ax
0x180080837  mov     [r12+10h], ecx
0x18008083c  pextrw  eax, xmm7, 2
0x180080841  mov     [r12+16h], ax
0x180080847  pextrw  eax, xmm4, 2
0x18008084c  movsx   ecx, ax
0x18008084f  mov     [r12+0Ch], ecx
0x180080854  pextrw  eax, xmm3, 2
0x180080859  mov     [r12+14h], ax
0x18008085f  pextrw  eax, xmm5, 3
0x180080864  mov     [r12+28h], ax
0x18008086a  pextrw  eax, xmm6, 3
0x18008086f  movsx   ecx, ax
0x180080872  mov     [r12+20h], ecx
0x180080877  pextrw  eax, xmm7, 3
0x18008087c  mov     [r12+26h], ax
0x180080882  pextrw  eax, xmm4, 3
0x180080887  movsx   ecx, ax
0x18008088a  mov     [r12+1Ch], ecx
0x18008088f  pextrw  eax, xmm3, 3
0x180080894  mov     [r12+24h], ax
0x18008089a  pextrw  eax, xmm5, 4
0x18008089f  mov     [r12+38h], ax
0x1800808a5  pextrw  eax, xmm6, 4
0x1800808aa  movsx   ecx, ax
0x1800808ad  mov     [r12+30h], ecx
0x1800808b2  pextrw  eax, xmm7, 4
0x1800808b7  mov     [r12+36h], ax
0x1800808bd  pextrw  eax, xmm4, 4
0x1800808c2  movsx   ecx, ax
0x1800808c5  mov     [r12+2Ch], ecx
0x1800808ca  pextrw  eax, xmm3, 4
0x1800808cf  mov     [r12+34h], ax
0x1800808d5  pextrw  eax, xmm5, 5
0x1800808da  mov     [r12+48h], ax
0x1800808e0  pextrw  eax, xmm6, 5
0x1800808e5  movsx   ecx, ax
0x1800808e8  mov     [r12+40h], ecx
0x1800808ed  pextrw  eax, xmm7, 5
0x1800808f2  mov     [r12+46h], ax
0x1800808f8  pextrw  eax, xmm4, 5
0x1800808fd  movsx   ecx, ax
0x180080900  mov     [r12+3Ch], ecx
0x180080905  pextrw  eax, xmm3, 5
0x18008090a  mov     [r12+44h], ax
0x180080910  pextrw  eax, xmm5, 6
0x180080915  mov     [r12+58h], ax
0x18008091b  pextrw  eax, xmm6, 6
0x180080920  movsx   ecx, ax
0x180080923  mov     [r12+50h], ecx
0x180080928  pextrw  eax, xmm7, 6
0x18008092d  mov     [r12+56h], ax
0x180080933  pextrw  eax, xmm4, 6
0x180080938  movsx   ecx, ax
0x18008093b  mov     [r12+4Ch], ecx
0x180080940  pextrw  eax, xmm3, 6
0x180080945  mov     [r12+54h], ax
0x18008094b  pextrw  eax, xmm5, 7
0x180080950  mov     [r12+68h], ax
0x180080956  pextrw  eax, xmm6, 7
0x18008095b  movsx   ecx, ax
0x18008095e  mov     [r12+60h], ecx
0x180080963  pextrw  eax, xmm7, 7
0x180080968  mov     [r12+66h], ax
0x18008096e  pextrw  eax, xmm4, 7
0x180080973  movsx   ecx, ax
0x180080976  pextrw  eax, xmm3, 7
0x18008097b  mov     [r12+5Ch], ecx
0x180080980  mov     [r12+64h], ax
0x180080986  mov     r11d, edx
0x180080989  mov     r9, rdx
0x18008098c  nop     dword ptr [rax+00h]
0x180080990  movzx   r10d, word ptr [rsp+r9+158h+var_100]
0x180080996  cmp     r10d, 40h ; '@'
0x18008099a  jnb     short loc_1800809D7
0x18008099c  movzx   eax, word ptr [rsp+r9+158h+var_F0]
0x1800809a2  cmp     eax, 7Fh
0x1800809a5  jnb     short loc_1800809D7
0x1800809a7  mov     rdx, [r14]
0x1800809aa  mov     r8d, r10d
0x1800809ad  shl     r8, 8
0x1800809b1  lea     rcx, [rdx+rax*2]
0x1800809b5  movzx   ebx, word ptr [rcx+r8]
0x1800809ba  lea     rax, [rdx+rax*2]
0x1800809be  lea     rdx, [r10+1]
0x1800809c2  movzx   r10d, word ptr [rax+r8+2]
0x1800809c8  shl     rdx, 8
0x1800809cc  movzx   edi, word ptr [rax+rdx+2]
0x1800809d1  movzx   esi, word ptr [rcx+rdx]
0x1800809d5  jmp     short loc_1800809EC
0x1800809d7  cmp     r9, 10h
0x1800809db  jnb     loc_180080C02
0x1800809e1  inc     ebp
0x1800809e3  mov     r10d, edx
0x1800809e6  mov     ebx, edx
0x1800809e8  mov     edi, edx
0x1800809ea  mov     esi, edx
0x1800809ec  mov     rdx, r9
0x1800809ef  lea     r8, [rsp+158h+var_110]
0x1800809f4  mov     rax, r9
0x1800809f7  lea     rcx, [rsp+158h+var_120]
0x1800809fc  inc     r11d
0x1800809ff  mov     [r8+rdx], si
0x180080a04  mov     edx, 0
0x180080a09  mov     [rcx+rax], di
0x180080a0d  mov     word ptr [rsp+r9+158h+var_E0], bx
0x180080a13  mov     word ptr [rsp+r9+158h+var_D0], r10w
0x180080a1c  add     r9, 2
0x180080a20  cmp     r11d, 8
0x180080a24  jl      loc_180080990
0x180080a2a  movdqa  xmm2, cs:__xmm@80008000800080008000800080008000
0x180080a32  lea     r11, cs:180000000h
0x180080a39  movdqu  xmm0, [rsp+158h+var_E0]
0x180080a3f  mov     r10, [rsp+158h+var_130]
0x180080a44  sub     r15d, ebp
0x180080a47  movdqa  xmm4, xmm2
0x180080a4b  add     r13, 8
0x180080a4f  psubw   xmm2, xmm7
0x180080a53  psubw   xmm4, xmm3
0x180080a57  movdqa  xmm1, xmm2
0x180080a5b  sub     r12, 0FFFFFFFFFFFFFF80h
0x180080a5f  pmulhuw xmm2, xmm3
0x180080a63  pmulhuw xmm1, xmm4
0x180080a67  pmulhuw xmm4, xmm7
0x180080a6b  pmulhuw xmm7, xmm3
0x180080a6f  movdqa  xmm3, xmm0
0x180080a73  psllw   xmm2, 1
0x180080a78  psllw   xmm1, 1
0x180080a7d  pmullw  xmm3, xmm1
0x180080a81  pmulhuw xmm0, xmm1
0x180080a85  movdqa  xmm1, xmm2
0x180080a89  psllw   xmm7, 1
0x180080a8e  psllw   xmm4, 1
0x180080a93  psrlw   xmm3, 0Fh
0x180080a98  psllw   xmm0, 1
0x180080a9d  por     xmm3, xmm0
0x180080aa1  movdqu  xmm0, [rsp+158h+var_D0]
0x180080aaa  pmullw  xmm1, xmm0
0x180080aae  pmulhuw xmm2, xmm0
0x180080ab2  movdqu  xmm0, [rsp+158h+var_120]
0x180080ab8  psrlw   xmm1, 0Fh
0x180080abd  psllw   xmm2, 1
0x180080ac2  por     xmm1, xmm2
0x180080ac6  movdqa  xmm2, xmm7
0x180080aca  paddw   xmm3, xmm1
0x180080ace  pmullw  xmm2, xmm0
0x180080ad2  movdqa  xmm1, xmm4
0x180080ad6  pmulhuw xmm7, xmm0
0x180080ada  movdqu  xmm0, [rsp+158h+var_110]
0x180080ae0  pmullw  xmm1, xmm0
0x180080ae4  psrlw   xmm2, 0Fh
0x180080ae9  pmulhuw xmm4, xmm0
0x180080aed  psllw   xmm7, 1
0x180080af2  por     xmm2, xmm7
0x180080af6  psrlw   xmm1, 0Fh
0x180080afb  psllw   xmm4, 1
0x180080b00  por     xmm1, xmm4
0x180080b04  paddw   xmm2, xmm1
0x180080b08  paddw   xmm3, xmm2
0x180080b0c  psrlw   xmm3, 5
0x180080b11  paddw   xmm8, xmm3
0x180080b16  cmp     r13, [rsp+158h+var_138]
0x180080b1b  jl      loc_180080686
0x180080b21  mov     r9, [rsp+158h+var_128]
0x180080b26  lea     r11, cs:180000000h
0x180080b2d  pmaddwd xmm8, cs:__xmm@00010001000100010001000100010001
  ... truncated ...
```

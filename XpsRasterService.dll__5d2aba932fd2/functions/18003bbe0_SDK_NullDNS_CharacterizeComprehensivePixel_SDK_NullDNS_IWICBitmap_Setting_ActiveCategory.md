# SDK::NullDNS::CharacterizeComprehensivePixel(SDK::NullDNS &,IWICBitmap &,Setting::ActiveCategory &)

- ea: `0x18003bbe0`
- end: `0x18003c223`
- name: `?CharacterizeComprehensivePixel@NullDNS@SDK@@SAJAEAV12@AEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z`
- size: `1603`
- prototype: `__int64 __fastcall(struct SDK::NullDNS *this, struct IWICBitmap *, struct Setting::ActiveCategory *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x18003bbe0`
- `0x18003ddb0`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall SDK::NullDNS::CharacterizeComprehensivePixel(
        struct SDK::NullDNS *this,
        struct IWICBitmap *a2,
        struct Setting::ActiveCategory *a3,
        __int64 a4)
{
  __int16 epi16; // di
  __int64 (__fastcall *v7)(SDK::NullDNS *__hidden, struct IWICBitmap *, struct Setting::ActiveCategory *); // r10
  __int16 v8; // r14
  __int16 v9; // r11
  unsigned int v10; // ecx
  __m128i v12; // xmm1
  __m128i v13; // xmm2
  __m128i v14; // xmm4
  __m128i v15; // xmm3
  __int16 v16; // bx
  __m128i v17; // xmm0
  __m128i v18; // xmm1
  __int16 v19; // r14
  __m128i v20; // xmm4
  __int64 v21; // rdx
  __int64 v22; // rax
  char *v23; // rdx
  unsigned int v24; // edx
  __int64 v25; // r8
  void (__fastcall *MixedProvider)(__int64 (__fastcall *)(struct SDK::NullDNS *, struct IWICBitmap *, struct Setting::ActiveCategory *), unsigned __int64, __int64); // rax
  __m128i v28; // xmm3
  __m128i v29; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int8 *retaddr; // [rsp+68h] [rbp+0h]

  epi16 = v29.m128i_i16[2];
  v7 = 0;
  v29.m128i_i32[0] = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  LOBYTE(a4) = 1;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
LABEL_2:
  v17 = _mm_loadu_si128(&v29);
  while ( 1 )
  {
    while ( v10 <= 0x13EA1BE )
    {
      if ( v10 == 20881854 )
      {
        if ( epi16 == v9 )
        {
          v21 = *(int *)((char *)v7 + 1);
          LOBYTE(a4) = 1;
          if ( v21 <= 0 )
          {
            if ( v21 < 0 )
            {
              v10 = 2;
              if ( (__int64)&loc_18003DDB5 < (__int64)(0x8000000000000000uLL - v21) )
                goto LABEL_28;
            }
          }
          else if ( (__int64)&loc_18003DDB5 > 0x7FFFFFFFFFFFFFFFLL - v21 )
          {
            v10 = 2;
LABEL_28:
            v7 = (__int64 (__fastcall *)(SDK::NullDNS *__hidden, struct IWICBitmap *, struct Setting::ActiveCategory *))((char *)&loc_18003DDB5 + v21);
            goto LABEL_29;
          }
          v10 = 2983122;
          goto LABEL_28;
        }
LABEL_29:
        if ( v16 == v9 )
        {
          v22 = *((char *)v7 + 1);
          v23 = (char *)SDK::NullDNS::InsertGlobalUnit + 2;
          LOBYTE(a4) = 1;
          if ( (char)v22 <= 0 )
          {
            if ( (v22 & 0x80u) != 0LL && (__int64)v23 < (__int64)(0x8000000000000000uLL - v22) )
              goto LABEL_32;
          }
          else if ( (__int64)v23 > 0x7FFFFFFFFFFFFFFFLL - v22 )
          {
            goto LABEL_32;
          }
          v7 = (__int64 (__fastcall *)(SDK::NullDNS *__hidden, struct IWICBitmap *, struct Setting::ActiveCategory *))&v23[v22];
          v10 = 2983122;
        }
        else if ( v10 != 2983122 )
        {
          v10 = 23864976;
        }
      }
      else
      {
        if ( v10 <= 0x888E76 )
        {
          if ( v10 == 8949366 )
          {
            v10 = 11932488;
            epi16 = 14912;
            v29.m128i_i64[0] = 0x3F003A4005C03AC0LL;
            v16 = 15040;
            v20 = _mm_cvtsi32_si128(v9);
            v14 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v20, v20), 0), v12);
          }
          else if ( v10 )
          {
            if ( v10 == 2983122 )
            {
              v19 = *(unsigned __int8 *)v7;
              v29.m128i_i16[6] = 13056;
              v9 = -1;
              v10 = 5966244;
              v8 = v19 << 6;
            }
            else
            {
              v10 = 8949366;
              v29.m128i_i16[4] = 10880;
              v18 = _mm_cvtsi32_si128(v8);
              v12 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v18, v18), 0);
            }
          }
          else
          {
            v29.m128i_i16[5] = 16128;
            v29.m128i_i16[7] = 12032;
            v10 = 2983122;
            v7 = SDK::NullDNS::InsertGlobalUnit;
          }
          goto LABEL_2;
        }
        if ( v10 == 11932488 )
        {
          v13 = v17;
          v10 = 26848098;
        }
        else if ( v10 == 14915610 )
        {
          v13 = _mm_and_si128(v13, v12);
          LOBYTE(a4) = 0;
          v10 = 17898732;
          v12 = _mm_and_si128(v15, v14);
        }
        else
        {
          v12 = _mm_or_si128(v12, v13);
          v17 = v12;
          v29 = v12;
          if ( (unsigned __int16)_mm_extract_epi16(v12, 6) == v9 )
          {
            LOBYTE(a4) = 1;
            v10 = 23864976;
          }
          else
          {
            v10 = 20881854;
          }
          epi16 = _mm_extract_epi16(v12, 2);
          v16 = _mm_cvtsi128_si32(v12);
        }
      }
    }
    if ( v10 == 23864976 )
      break;
    v10 = 14915610;
    v28 = _mm_cvtsi32_si128(v9);
    v15 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v28, v28), 0), v13);
  }
  if ( !(_BYTE)a4 )
  {
LABEL_32:
    v24 = IntegralRelation::OddMap;
    goto LABEL_33;
  }
  v24 = ++IntegralRelation::OddMap;
LABEL_33:
  v25 = *retaddr;
  if ( (float)(4378375 * v25) > 892476290.0 && (float)(1183359 * v25) < 242531520.0 || (v24 ^ 0xFBD98027) != 0x1CEC74 )
    IntegralRelation::OddMap = v24 + 1;
  MixedProvider = (void (__fastcall *)(__int64 (__fastcall *)(struct SDK::NullDNS *, struct IWICBitmap *, struct Setting::ActiveCategory *), unsigned __int64, __int64))GenerateMixedProvider(0xDFCF7F1F6070C060uLL, 829718730, v25, a4);
  MixedProvider(
    SDK::NullDNS::CharacterizeComprehensivePixel,
    (unsigned __int64)SDK::NullDNS::CharacterizeComprehensivePixel ^ 0x2CED40,
    1895728);
  return SDK::NullDNS::InsertGlobalUnit(this, a2, a3);
}

```

## disassembly

```asm
0x18003bbe0  mov     [rsp+arg_18], rbx
0x18003bbe5  push    rbp
0x18003bbe6  push    rsi
0x18003bbe7  push    rdi
0x18003bbe8  push    r12
0x18003bbea  push    r13
0x18003bbec  push    r14
0x18003bbee  push    r15
0x18003bbf0  sub     rsp, 30h
0x18003bbf4  movzx   esi, word ptr [rsp+68h+var_48+0Eh]
0x18003bbf9  xor     eax, eax
0x18003bbfb  movzx   ebp, word ptr [rsp+68h+var_48+6]
0x18003bc00  mov     r13, r8
0x18003bc03  movzx   edi, word ptr [rsp+68h+var_48+4]
0x18003bc08  mov     r15, rcx
0x18003bc0b  mov     r10d, eax
0x18003bc0e  mov     dword ptr [rsp+68h+var_48], eax
0x18003bc12  movzx   r14d, ax
0x18003bc16  movzx   r11d, ax
0x18003bc1a  mov     ecx, eax
0x18003bc1c  mov     r12, rdx
0x18003bc1f  mov     r9b, 1
0x18003bc22  xorps   xmm1, xmm1
0x18003bc25  xorps   xmm2, xmm2
0x18003bc28  xorps   xmm4, xmm4
0x18003bc2b  xorps   xmm3, xmm3
0x18003bc2e  mov     r8, 8000000000000000h
0x18003bc38  mov     edx, 3F00h
0x18003bc3d  movzx   ebx, ax
0x18003bc40  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003bc4a  movdqu  xmm0, [rsp+68h+var_48]
0x18003bc50  cmp     ecx, 13EA1BEh
0x18003bc56  ja      loc_18003BF3D
0x18003bc5c  jz      loc_18003BDB0
0x18003bc62  cmp     ecx, 888E76h
0x18003bc68  ja      loc_18003BD23
0x18003bc6e  jz      short loc_18003BCE8
0x18003bc70  test    ecx, ecx
0x18003bc72  jz      short loc_18003BCC6
0x18003bc74  cmp     ecx, 2D84D2h
0x18003bc7a  jz      short loc_18003BCA6
0x18003bc7c  cmp     ecx, 5B09A4h
0x18003bc82  jnz     short loc_18003BC50
0x18003bc84  mov     eax, 2A80h
0x18003bc89  mov     ecx, 888E76h
0x18003bc8e  mov     word ptr [rsp+68h+var_48+8], ax
0x18003bc93  movsx   eax, r14w
0x18003bc97  movd    xmm1, eax
0x18003bc9b  punpcklwd xmm1, xmm1
0x18003bc9f  pshufd  xmm1, xmm1, 0
0x18003bca4  jmp     short loc_18003BC40
0x18003bca6  movzx   r14d, byte ptr [r10]
0x18003bcaa  mov     ecx, 3300h
0x18003bcaf  mov     word ptr [rsp+68h+var_48+0Ch], cx
0x18003bcb4  mov     r11d, 0FFFFh
0x18003bcba  mov     ecx, 5B09A4h
0x18003bcbf  shl     r14w, 6
0x18003bcc4  jmp     short loc_18003BC4A
0x18003bcc6  mov     ecx, 2F00h
0x18003bccb  mov     word ptr [rsp+68h+var_48+0Ah], dx
0x18003bcd0  mov     esi, ecx
0x18003bcd2  mov     word ptr [rsp+68h+var_48+0Eh], cx
0x18003bcd7  mov     ecx, 2D84D2h
0x18003bcdc  lea     r10, ?InsertGlobalUnit@NullDNS@SDK@@QEAAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::InsertGlobalUnit(IWICBitmap &,Setting::ActiveCategory &)
0x18003bce3  jmp     loc_18003BC4A
0x18003bce8  movsx   eax, r11w
0x18003bcec  mov     ecx, 0B61348h
0x18003bcf1  mov     ebp, edx
0x18003bcf3  mov     dword ptr [rsp+68h+var_48+4], 3F003A40h
0x18003bcfb  mov     edi, 3A40h
0x18003bd00  mov     dword ptr [rsp+68h+var_48], 5C03AC0h
0x18003bd08  mov     ebx, 3AC0h
0x18003bd0d  movd    xmm4, eax
0x18003bd11  punpcklwd xmm4, xmm4
0x18003bd15  pshufd  xmm4, xmm4, 0
0x18003bd1a  pxor    xmm4, xmm1
0x18003bd1e  jmp     loc_18003BC40
0x18003bd23  cmp     ecx, 0B61348h
0x18003bd29  jz      short loc_18003BDA2
0x18003bd2b  cmp     ecx, 0E3981Ah
0x18003bd31  jz      short loc_18003BD89
0x18003bd33  cmp     ecx, 1111CECh
0x18003bd39  jnz     loc_18003BC50
0x18003bd3f  por     xmm1, xmm2
0x18003bd43  pextrw  eax, xmm1, 6
0x18003bd48  movdqa  xmm0, xmm1
0x18003bd4c  movdqu  [rsp+68h+var_48], xmm1
0x18003bd52  cmp     ax, r11w
0x18003bd56  jnz     short loc_18003BD62
0x18003bd58  mov     r9b, 1
0x18003bd5b  mov     ecx, 16C2690h
0x18003bd60  jmp     short loc_18003BD67
0x18003bd62  mov     ecx, 13EA1BEh
0x18003bd67  pextrw  esi, xmm1, 7
0x18003bd6c  pextrw  ebp, xmm1, 3
0x18003bd71  pextrw  edi, xmm1, 2
0x18003bd76  movd    ebx, xmm1
0x18003bd7a  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003bd84  jmp     loc_18003BC50
0x18003bd89  pand    xmm2, xmm1
0x18003bd8d  xor     r9b, r9b
0x18003bd90  movdqa  xmm1, xmm3
0x18003bd94  mov     ecx, 1111CECh
0x18003bd99  pand    xmm1, xmm4
0x18003bd9d  jmp     loc_18003BC50
0x18003bda2  movdqa  xmm2, xmm0
0x18003bda6  mov     ecx, 199AB62h
0x18003bdab  jmp     loc_18003BC50
0x18003bdb0  cmp     di, r11w
0x18003bdb4  jnz     short loc_18003BE0D
0x18003bdb6  movsxd  rdx, dword ptr [r10+1]
0x18003bdba  lea     r8, ?InsertGlobalUnit@NullDNS@SDK@@QEAAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::InsertGlobalUnit(IWICBitmap &,Setting::ActiveCategory &)
0x18003bdc1  add     r8, 5
0x18003bdc5  mov     r9b, 1
0x18003bdc8  test    rdx, rdx
0x18003bdcb  jle     short loc_18003BDDC
0x18003bdcd  sub     rax, rdx
0x18003bdd0  cmp     r8, rax
0x18003bdd3  jle     short loc_18003BDF5
0x18003bdd5  mov     ecx, 2
0x18003bdda  jmp     short loc_18003BDFA
0x18003bddc  jns     short loc_18003BDF5
0x18003bdde  mov     rax, 8000000000000000h
0x18003bde8  mov     ecx, 2
0x18003bded  sub     rax, rdx
0x18003bdf0  cmp     r8, rax
0x18003bdf3  jl      short loc_18003BDFA
0x18003bdf5  mov     ecx, 2D84D2h
0x18003bdfa  lea     r10, [r8+rdx]
0x18003bdfe  mov     edx, 3F00h
0x18003be03  mov     r8, 8000000000000000h
0x18003be0d  cmp     bx, r11w
0x18003be11  jnz     loc_18003BF1D
0x18003be17  movsx   rax, byte ptr [r10+1]
0x18003be1c  lea     rdx, ?InsertGlobalUnit@NullDNS@SDK@@QEAAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::InsertGlobalUnit(IWICBitmap &,Setting::ActiveCategory &)
0x18003be23  add     rdx, 2
0x18003be27  mov     r9b, 1
0x18003be2a  mov     rcx, rax
0x18003be2d  test    al, al
0x18003be2f  jle     loc_18003BEFE
0x18003be35  mov     r8, 7FFFFFFFFFFFFFFFh
0x18003be3f  sub     r8, rax
0x18003be42  cmp     rdx, r8
0x18003be45  jle     loc_18003BF0F
0x18003be4b  mov     edx, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18003be51  mov     rax, [rsp+68h]
0x18003be56  xorps   xmm0, xmm0
0x18003be59  movzx   r8d, byte ptr [rax]
0x18003be5d  imul    ecx, r8d, 42CF07h
0x18003be64  cvtsi2ss xmm0, rcx
0x18003be69  comiss  xmm0, cs:__real@4e54c86e
0x18003be70  jbe     short loc_18003BE8E
0x18003be72  movss   xmm0, cs:__real@4d674bcc
0x18003be7a  xorps   xmm1, xmm1
0x18003be7d  imul    ecx, r8d, 120E7Fh
0x18003be84  cvtsi2ss xmm1, rcx
0x18003be89  comiss  xmm0, xmm1
0x18003be8c  ja      short loc_18003BE9C
0x18003be8e  mov     eax, edx
0x18003be90  xor     eax, 0FBD98027h
0x18003be95  cmp     eax, 1CEC74h
0x18003be9a  jz      short loc_18003BEA4
0x18003be9c  inc     edx
0x18003be9e  mov     cs:?OddMap@IntegralRelation@@2IA, edx; uint IntegralRelation::OddMap
0x18003bea4  mov     edx, 317480CAh
0x18003bea9  mov     rcx, 0DFCF7F1F6070C060h
0x18003beb3  call    GenerateMixedProvider
0x18003beb8  lea     rdx, ?CharacterizeComprehensivePixel@NullDNS@SDK@@SAJAEAV12@AEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::CharacterizeComprehensivePixel(SDK::NullDNS &,IWICBitmap &,Setting::ActiveCategory &)
0x18003bebf  mov     r8d, 1CED30h
0x18003bec5  xor     rdx, 2CED40h
0x18003becc  lea     rcx, ?CharacterizeComprehensivePixel@NullDNS@SDK@@SAJAEAV12@AEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::CharacterizeComprehensivePixel(SDK::NullDNS &,IWICBitmap &,Setting::ActiveCategory &)
0x18003bed3  call    cs:__guard_dispatch_icall_fptr
0x18003bed9  mov     r8, r13; struct Setting::ActiveCategory *
0x18003bedc  mov     rdx, r12; struct IWICBitmap *
0x18003bedf  mov     rcx, r15; this
0x18003bee2  mov     rbx, [rsp+68h+arg_18]
0x18003beea  add     rsp, 30h
0x18003beee  pop     r15
0x18003bef0  pop     r14
0x18003bef2  pop     r13
0x18003bef4  pop     r12
0x18003bef6  pop     rdi
0x18003bef7  pop     rsi
0x18003bef8  pop     rbp
0x18003bef9  jmp     ?InsertGlobalUnit@NullDNS@SDK@@QEAAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::InsertGlobalUnit(IWICBitmap &,Setting::ActiveCategory &)
0x18003befe  jns     short loc_18003BF0F
0x18003bf00  mov     rax, r8
0x18003bf03  sub     rax, rcx
0x18003bf06  cmp     rdx, rax
0x18003bf09  jl      loc_18003BE4B
0x18003bf0f  lea     r10, [rcx+rdx]
0x18003bf13  mov     ecx, 2D84D2h
0x18003bf18  jmp     loc_18003C094
0x18003bf1d  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003bf27  cmp     ecx, 2D84D2h
0x18003bf2d  jz      loc_18003BC50
0x18003bf33  mov     ecx, 16C2690h
0x18003bf38  jmp     loc_18003BC50
0x18003bf3d  cmp     ecx, 33356C4h
0x18003bf43  ja      loc_18003C0B2
0x18003bf49  jz      loc_18003BFE9
0x18003bf4f  cmp     ecx, 16C2690h
0x18003bf55  jz      loc_18003C207
0x18003bf5b  cmp     ecx, 199AB62h
0x18003bf61  jz      short loc_18003BFC0
0x18003bf63  cmp     ecx, 305D1F2h
0x18003bf69  jnz     loc_18003BC50
0x18003bf6f  test    r10, r10
0x18003bf72  jnz     short loc_18003BF7E
0x18003bf74  mov     ecx, 16C2690h
0x18003bf79  jmp     loc_18003BC50
0x18003bf7e  movdqa  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003bf86  mov     ecx, 2A80h
0x18003bf8b  mov     word ptr [rsp+68h+var_48+8], cx
0x18003bf90  mov     edi, 40h ; '@'
0x18003bf95  mov     dword ptr [rsp+68h+var_48+4], 35000040h
0x18003bf9d  mov     ebp, 3500h
0x18003bfa2  movdqu  xmm0, [rsp+68h+var_48]
0x18003bfa8  mov     r11d, 0FFFFh
0x18003bfae  mov     ecx, 33356C4h
0x18003bfb3  movdqa  xmm2, xmm0
0x18003bfb7  pxor    xmm3, xmm0
0x18003bfbb  jmp     loc_18003BC50
0x18003bfc0  movsx   eax, r11w
0x18003bfc4  mov     ecx, 0E3981Ah
0x18003bfc9  movd    xmm3, eax
0x18003bfcd  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003bfd7  punpcklwd xmm3, xmm3
0x18003bfdb  pshufd  xmm3, xmm3, 0
0x18003bfe0  pxor    xmm3, xmm2
0x18003bfe4  jmp     loc_18003BC50
0x18003bfe9  movzx   r9d, byte ptr [r10]
0x18003bfed  movzx   edx, byte ptr [r10+2]
0x18003bff2  movzx   eax, r9b
0x18003bff6  movzx   r8d, byte ptr [r10+1]
0x18003bffb  shl     al, 3
0x18003bffe  movzx   ecx, al
0x18003c001  movzx   eax, dl
0x18003c004  shl     cx, 6
0x18003c008  shr     al, 5
0x18003c00b  movzx   ebx, cx
0x18003c00e  mov     word ptr [rsp+68h+var_48], cx
0x18003c013  movzx   ecx, al
0x18003c016  shl     cx, 6
0x18003c01a  mov     word ptr [rsp+68h+var_48+4], cx
0x18003c01f  movzx   edi, cx
0x18003c022  movzx   ecx, byte ptr [r10+3]
0x18003c027  movzx   eax, cx
0x18003c02a  shl     r8w, 6
0x18003c02f  shl     ax, 6
0x18003c033  mov     word ptr [rsp+68h+var_48+6], ax
0x18003c038  movzx   ebp, ax
0x18003c03b  shr     cl, 2
0x18003c03e  movzx   eax, cl
0x18003c041  mov     ecx, 360DB96h
0x18003c046  shl     ax, 6
0x18003c04a  mov     word ptr [rsp+68h+var_48+0Eh], ax
0x18003c04f  movzx   esi, ax
0x18003c052  shl     r9w, 6
0x18003c057  shl     dx, 6
0x18003c05b  mov     word ptr [rsp+68h+var_48+8], r9w
0x18003c061  xor     r9b, r9b
0x18003c064  movsx   eax, r11w
0x18003c068  mov     word ptr [rsp+68h+var_48+2], r8w
0x18003c06e  mov     word ptr [rsp+68h+var_48+0Ah], r8w
0x18003c074  mov     word ptr [rsp+68h+var_48+0Ch], dx
0x18003c079  movdqu  xmm0, [rsp+68h+var_48]
0x18003c07f  movd    xmm4, eax
0x18003c083  punpcklwd xmm4, xmm4
0x18003c087  movdqa  xmm1, xmm0
0x18003c08b  pshufd  xmm4, xmm4, 0
0x18003c090  pxor    xmm4, xmm0
0x18003c094  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003c09e  mov     edx, 3F00h
0x18003c0a3  mov     r8, 8000000000000000h
0x18003c0ad  jmp     loc_18003BC50
0x18003c0b2  cmp     ecx, 360DB96h
0x18003c0b8  jz      loc_18003C1C6
0x18003c0be  cmp     ecx, 38E6068h
0x18003c0c4  jz      short loc_18003C0F1
0x18003c0c6  cmp     ecx, 3BBE53Ah
0x18003c0cc  jnz     loc_18003BC50
0x18003c0d2  mov     ecx, 140h
0x18003c0d7  mov     dword ptr [rsp+68h+var_48+0Ah], 2F003F00h
0x18003c0df  movzx   esi, cx
0x18003c0e2  mov     word ptr [rsp+68h+var_48+0Eh], cx
0x18003c0e7  mov     ecx, 305D1F2h
0x18003c0ec  jmp     loc_18003BC4A
0x18003c0f1  cmp     bp, r11w
0x18003c0f5  jnz     short loc_18003C10E
0x18003c0f7  cmp     bx, r11w
0x18003c0fb  jnz     short loc_18003C10E
0x18003c0fd  cmp     di, r11w
0x18003c101  movzx   r9d, r9b
0x18003c105  mov     ecx, 1
0x18003c10a  cmovz   r9d, ecx
0x18003c10e  cmp     si, r11w
0x18003c112  jnz     loc_18003BF74
0x18003c118  movzx   eax, byte ptr [r10+3]
0x18003c11d  and     al, 3
  ... truncated ...
```

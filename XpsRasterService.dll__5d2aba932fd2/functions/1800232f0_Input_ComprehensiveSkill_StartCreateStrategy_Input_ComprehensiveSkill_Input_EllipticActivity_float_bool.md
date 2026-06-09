# Input::ComprehensiveSkill::StartCreateStrategy(Input::ComprehensiveSkill &,Input::EllipticActivity &,float,bool)

- ea: `0x1800232f0`
- end: `0x1800239fa`
- name: `?StartCreateStrategy@ComprehensiveSkill@Input@@SAXAEAV12@AEAVEllipticActivity@2@M_N@Z`
- size: `1802`
- prototype: `void __fastcall(struct Input::ComprehensiveSkill *this, struct Input::EllipticActivity *, float, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x18001fa90`
- `0x1800232f0`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::ComprehensiveSkill::StartCreateStrategy(
        struct Input::ComprehensiveSkill *this,
        struct Input::EllipticActivity *a2,
        float a3,
        char a4)
{
  int v4; // r14d
  __int16 v5; // si
  __int64 epi16; // r9
  void (__fastcall *v8)(Input::ComprehensiveSkill *, struct Input::EllipticActivity *, float, char); // r11
  __int16 v9; // r15
  __int16 v11; // bx
  unsigned int v12; // edx
  __m128i v13; // xmm2
  char v15; // r10
  __m128i v16; // xmm1
  __m128i v17; // xmm4
  __m128i v18; // xmm3
  unsigned __int64 v19; // r8
  __int16 v20; // di
  __m128i v21; // xmm0
  __m128i v22; // xmm1
  __m128i v23; // xmm4
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // r10d
  unsigned int v27; // eax
  _BYTE *v28; // r11
  __m128i v29; // xmm3
  void (__fastcall *MixedProvider)(void (__fastcall *)(struct Input::ComprehensiveSkill *, struct Input::EllipticActivity *, float, bool), unsigned __int64, __int64); // rax
  __m128i v32; // [rsp+28h] [rbp-50h] BYREF
  _BYTE *retaddr; // [rsp+78h] [rbp+0h]

  v4 = 0;
  v5 = v32.m128i_i16[2];
  epi16 = v32.m128i_u16[7];
  v8 = 0;
  v9 = 0;
  v11 = 0;
  v32.m128i_i32[0] = 0;
  v12 = 0;
  v13 = 0;
  v15 = 1;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0x8000000000000000uLL;
  v20 = 0;
LABEL_2:
  v21 = _mm_loadu_si128(&v32);
  while ( 1 )
  {
    while ( v12 <= 0xCFCA2D )
    {
      if ( v12 == 13617709 )
      {
        if ( v5 == v11 )
        {
          v24 = *(int *)((char *)v8 + 1);
          v15 = 1;
          if ( v24 <= 0 )
          {
            if ( v24 < 0 )
            {
              v12 = 2;
              if ( (__int64)&loc_18001FA93 + 2 < (__int64)(0x8000000000000000uLL - v24) )
                goto LABEL_27;
            }
          }
          else if ( (__int64)&loc_18001FA93 + 2 > 0x7FFFFFFFFFFFFFFFLL - v24 )
          {
            v12 = 2;
LABEL_27:
            v8 = (void (__fastcall *)(Input::ComprehensiveSkill *, struct Input::EllipticActivity *, float, char))((char *)&loc_18001FA93 + v24 + 2);
            v19 = 0x8000000000000000uLL;
            goto LABEL_28;
          }
          v12 = 1945387;
          goto LABEL_27;
        }
LABEL_28:
        if ( v20 == v11 )
        {
          v25 = *((char *)v8 + 1);
          v15 = 1;
          if ( (char)v25 <= 0 )
          {
            if ( (v25 & 0x80u) != 0LL && (__int64)&loc_18001FA92 < (__int64)(0x8000000000000000uLL - v25) )
              goto LABEL_31;
          }
          else
          {
            v19 = 0x7FFFFFFFFFFFFFFFLL - v25;
            if ( (__int64)&loc_18001FA92 > 0x7FFFFFFFFFFFFFFFLL - v25 )
              goto LABEL_31;
          }
          v8 = (void (__fastcall *)(Input::ComprehensiveSkill *, struct Input::EllipticActivity *, float, char))((char *)&loc_18001FA92 + v25);
          v12 = 1945387;
          v19 = 0x8000000000000000uLL;
        }
        else if ( v12 != 1945387 )
        {
          v12 = 15563096;
        }
      }
      else
      {
        if ( v12 <= 0x590D81 )
        {
          if ( v12 == 5836161 )
          {
            v5 = 13514;
            v12 = 7781548;
            v32.m128i_i64[0] = 0x391834CA0536353ELL;
            v23 = _mm_cvtsi32_si128(v11);
            v20 = 13630;
            v17 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v23, v23), 0), v16);
          }
          else if ( v12 )
          {
            if ( v12 == 1945387 )
            {
              v11 = -1;
              v32.m128i_i16[6] = 11832;
              v12 = 3890774;
              v9 = 58 * *(unsigned __int8 *)v8;
            }
            else
            {
              v12 = 5836161;
              v32.m128i_i16[4] = 9860;
              v22 = _mm_cvtsi32_si128(v9);
              v16 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v22, v22), 0);
            }
          }
          else
          {
            v8 = Input::ComprehensiveSkill::FormulateImportantQuality;
            epi16 = 10904;
            v32.m128i_i16[7] = 10904;
            v32.m128i_i16[5] = 14616;
            v12 = 1945387;
          }
          goto LABEL_2;
        }
        if ( v12 == 7781548 )
        {
          v13 = v21;
          v12 = 17508483;
        }
        else if ( v12 == 9726935 )
        {
          v13 = _mm_and_si128(v13, v16);
          v15 = 0;
          v12 = 11672322;
          v16 = _mm_and_si128(v18, v17);
        }
        else
        {
          v16 = _mm_or_si128(v16, v13);
          v21 = v16;
          v20 = _mm_cvtsi128_si32(v16);
          v32 = v16;
          epi16 = (unsigned int)_mm_extract_epi16(v16, 7);
          v5 = _mm_extract_epi16(v16, 2);
          if ( (unsigned __int16)_mm_extract_epi16(v16, 6) == v11 )
          {
            v15 = 1;
            v12 = 15563096;
          }
          else
          {
            v12 = 13617709;
          }
        }
      }
    }
    if ( v12 == 15563096 )
      break;
    v12 = 9726935;
    v29 = _mm_cvtsi32_si128(v11);
    v18 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v29, v29), 0), v13);
  }
  if ( !v15 )
  {
LABEL_31:
    v26 = IntegralRelation::OddMap;
    goto LABEL_32;
  }
  v26 = ++IntegralRelation::OddMap;
LABEL_32:
  LOBYTE(epi16) = 1;
  v27 = 1284034;
  v28 = 0;
  while ( 1 )
  {
    while ( v27 <= 0x2A6BA2 )
    {
      switch ( v27 )
      {
        case 0x2A6BA2u:
          v27 = 2780120;
          if ( (_BYTE)epi16 != 1 )
            v27 = 4064083;
          break;
        case 0x1397C2u:
          LOBYTE(epi16) = 0;
          v27 = 2780066;
          break;
        case 0x1397D3u:
          epi16 = (unsigned __int8)epi16;
          v27 = 2780066;
          if ( (v26 ^ 0xFB5864A9) == 0x9D08FA )
            v27 = 10291450;
          else
            epi16 = 1;
          break;
        default:
          epi16 = (unsigned __int8)epi16;
          v27 = 2780066;
          if ( *v28 == (unsigned __int8)((v26 ^ v4) / 0x2C7018) )
            epi16 = 1;
          else
            v27 = 2780120;
          break;
      }
    }
    if ( v27 == 2780120 )
      break;
    if ( v27 == 4064083 )
    {
      v28 = retaddr;
      v27 = 1284051;
    }
    else
    {
      v27 = 1284105;
      v4 = -659800205;
    }
  }
  if ( (_BYTE)epi16 )
    IntegralRelation::OddMap = v26 + 1;
  MixedProvider = (void (__fastcall *)(void (__fastcall *)(struct Input::ComprehensiveSkill *, struct Input::EllipticActivity *, float, bool), unsigned __int64, __int64))GenerateMixedProvider(0x7F9F7F9F20206020LL, 2435088458LL, v19, epi16);
  MixedProvider(
    Input::ComprehensiveSkill::StartCreateStrategy,
    (unsigned __int64)Input::ComprehensiveSkill::StartCreateStrategy ^ 0x1101DC,
    65996);
  Input::ComprehensiveSkill::FormulateImportantQuality(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1800232f0  mov     [rsp+arg_0], rbx
0x1800232f5  mov     [rsp+arg_10], rbp
0x1800232fa  mov     [rsp+arg_18], rsi
0x1800232ff  push    rdi
0x180023300  push    r12
0x180023302  push    r13
0x180023304  push    r14
0x180023306  push    r15
0x180023308  sub     rsp, 50h
0x18002330c  movzx   ebp, word ptr [rsp+78h+var_50+6]
0x180023311  xor     r14d, r14d
0x180023314  movzx   esi, word ptr [rsp+78h+var_50+4]
0x180023319  movzx   r12d, r9b
0x18002331d  movzx   r9d, word ptr [rsp+78h+var_50+0Eh]
0x180023323  mov     r11d, r14d
0x180023326  movaps  [rsp+78h+var_38], xmm6
0x18002332b  movzx   r15d, r14w
0x18002332f  movaps  xmm6, xmm2
0x180023332  mov     [rsp+78h+var_58], rdx
0x180023337  movzx   ebx, r14w
0x18002333b  mov     dword ptr [rsp+78h+var_50], r14d
0x180023340  mov     edx, r14d
0x180023343  xorps   xmm2, xmm2
0x180023346  mov     r13, rcx
0x180023349  mov     r10b, 1
0x18002334c  xorps   xmm1, xmm1
0x18002334f  xorps   xmm4, xmm4
0x180023352  xorps   xmm3, xmm3
0x180023355  mov     r8, 8000000000000000h
0x18002335f  movzx   edi, r14w
0x180023363  mov     ecx, 1
0x180023368  mov     rax, 7FFFFFFFFFFFFFFFh
0x180023372  movdqu  xmm0, [rsp+78h+var_50]
0x180023378  nop     dword ptr [rax+rax+00000000h]
0x180023380  cmp     edx, 0CFCA2Dh
0x180023386  ja      loc_180023641
0x18002338c  jz      loc_1800234EA
0x180023392  cmp     edx, 590D81h
0x180023398  ja      loc_18002345A
0x18002339e  jz      short loc_18002341F
0x1800233a0  test    edx, edx
0x1800233a2  jz      short loc_1800233F7
0x1800233a4  cmp     edx, 1DAF2Bh
0x1800233aa  jz      short loc_1800233D6
0x1800233ac  cmp     edx, 3B5E56h
0x1800233b2  jnz     short loc_180023380
0x1800233b4  mov     eax, 2684h
0x1800233b9  mov     edx, 590D81h
0x1800233be  mov     word ptr [rsp+78h+var_50+8], ax
0x1800233c3  movsx   eax, r15w
0x1800233c7  movd    xmm1, eax
0x1800233cb  punpcklwd xmm1, xmm1
0x1800233cf  pshufd  xmm1, xmm1, 0
0x1800233d4  jmp     short loc_180023368
0x1800233d6  mov     eax, 2E38h
0x1800233db  mov     ebx, 0FFFFh
0x1800233e0  mov     word ptr [rsp+78h+var_50+0Ch], ax
0x1800233e5  mov     edx, 3B5E56h
0x1800233ea  movzx   eax, byte ptr [r11]
0x1800233ee  imul    r15d, eax, 3Ah ; ':'
0x1800233f2  jmp     loc_180023363
0x1800233f7  mov     edx, 2A98h
0x1800233fc  lea     r11, ?FormulateImportantQuality@ComprehensiveSkill@Input@@QEAAXAEAVEllipticActivity@2@M_N@Z; Input::ComprehensiveSkill::FormulateImportantQuality(Input::EllipticActivity &,float,bool)
0x180023403  mov     r9d, edx
0x180023406  mov     word ptr [rsp+78h+var_50+0Eh], dx
0x18002340b  mov     edx, 3918h
0x180023410  mov     word ptr [rsp+78h+var_50+0Ah], dx
0x180023415  mov     edx, 1DAF2Bh
0x18002341a  jmp     loc_180023372
0x18002341f  movsx   eax, bx
0x180023422  mov     esi, 34CAh
0x180023427  mov     edx, 76BCACh
0x18002342c  mov     dword ptr [rsp+78h+var_50+4], 391834CAh
0x180023434  mov     ebp, 3918h
0x180023439  mov     dword ptr [rsp+78h+var_50], 536353Eh
0x180023441  movd    xmm4, eax
0x180023445  lea     edi, [rsi+74h]
0x180023448  punpcklwd xmm4, xmm4
0x18002344c  pshufd  xmm4, xmm4, 0
0x180023451  pxor    xmm4, xmm1
0x180023455  jmp     loc_180023368
0x18002345a  cmp     edx, 76BCACh
0x180023460  jz      short loc_1800234DC
0x180023462  cmp     edx, 946BD7h
0x180023468  jz      short loc_1800234C3
0x18002346a  cmp     edx, 0B21B02h
0x180023470  jnz     loc_180023380
0x180023476  por     xmm1, xmm2
0x18002347a  pextrw  eax, xmm1, 6
0x18002347f  movdqa  xmm0, xmm1
0x180023483  movd    edi, xmm1
0x180023487  movdqu  [rsp+78h+var_50], xmm1
0x18002348d  cmp     ax, bx
0x180023490  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002349a  pextrw  r9d, xmm1, 7
0x1800234a0  pextrw  ebp, xmm1, 3
0x1800234a5  pextrw  esi, xmm1, 2
0x1800234aa  jnz     short loc_1800234B9
0x1800234ac  mov     r10b, 1
0x1800234af  mov     edx, 0ED7958h
0x1800234b4  jmp     loc_180023380
0x1800234b9  mov     edx, 0CFCA2Dh
0x1800234be  jmp     loc_180023380
0x1800234c3  pand    xmm2, xmm1
0x1800234c7  xor     r10b, r10b
0x1800234ca  movdqa  xmm1, xmm3
0x1800234ce  mov     edx, 0B21B02h
0x1800234d3  pand    xmm1, xmm4
0x1800234d7  jmp     loc_180023380
0x1800234dc  movdqa  xmm2, xmm0
0x1800234e0  mov     edx, 10B2883h
0x1800234e5  jmp     loc_180023380
0x1800234ea  cmp     si, bx
0x1800234ed  jnz     short loc_180023546
0x1800234ef  movsxd  rcx, dword ptr [r11+1]
0x1800234f3  lea     r8, ?FormulateImportantQuality@ComprehensiveSkill@Input@@QEAAXAEAVEllipticActivity@2@M_N@Z; Input::ComprehensiveSkill::FormulateImportantQuality(Input::EllipticActivity &,float,bool)
0x1800234fa  add     r8, 5
0x1800234fe  mov     r10b, 1
0x180023501  test    rcx, rcx
0x180023504  jle     short loc_180023515
0x180023506  sub     rax, rcx
0x180023509  cmp     r8, rax
0x18002350c  jle     short loc_18002352E
0x18002350e  mov     edx, 2
0x180023513  jmp     short loc_180023533
0x180023515  jns     short loc_18002352E
0x180023517  mov     rax, 8000000000000000h
0x180023521  mov     edx, 2
0x180023526  sub     rax, rcx
0x180023529  cmp     r8, rax
0x18002352c  jl      short loc_180023533
0x18002352e  mov     edx, 1DAF2Bh
0x180023533  lea     r11, [r8+rcx]
0x180023537  mov     ecx, 1
0x18002353c  mov     r8, 8000000000000000h
0x180023546  cmp     di, bx
0x180023549  jnz     loc_180023621
0x18002354f  movsx   rax, byte ptr [r11+1]
0x180023554  lea     rdx, ?FormulateImportantQuality@ComprehensiveSkill@Input@@QEAAXAEAVEllipticActivity@2@M_N@Z; Input::ComprehensiveSkill::FormulateImportantQuality(Input::EllipticActivity &,float,bool)
0x18002355b  add     rdx, 2
0x18002355f  mov     r10b, 1
0x180023562  mov     rcx, rax
0x180023565  test    al, al
0x180023567  jle     loc_180023602
0x18002356d  mov     r8, 7FFFFFFFFFFFFFFFh
0x180023577  sub     r8, rax
0x18002357a  cmp     rdx, r8
0x18002357d  jle     loc_180023613
0x180023583  mov     r10d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18002358a  mov     r9b, 1
0x18002358d  mov     eax, 1397C2h
0x180023592  mov     r11, r14
0x180023595  mov     edi, 2A6BD8h
0x18002359a  mov     ebx, 9D08FAh
0x18002359f  mov     esi, 3E0353h
0x1800235a4  mov     ebp, 1
0x1800235a9  nop     dword ptr [rax+00000000h]
0x1800235b0  cmp     eax, 2A6BA2h
0x1800235b5  ja      loc_180023951
0x1800235bb  jz      loc_180023944
0x1800235c1  mov     ecx, eax
0x1800235c3  sub     ecx, 1397C2h
0x1800235c9  jz      loc_180023937
0x1800235cf  sub     ecx, 11h
0x1800235d2  jz      loc_180023917
0x1800235d8  cmp     ecx, 36h ; '6'
0x1800235db  jnz     short loc_1800235B0
0x1800235dd  mov     ecx, r14d
0x1800235e0  movzx   r9d, r9b
0x1800235e4  xor     ecx, r10d
0x1800235e7  mov     eax, 0B858E7B1h
0x1800235ec  mul     ecx
0x1800235ee  mov     eax, 2A6BA2h
0x1800235f3  shr     edx, 15h
0x1800235f6  cmp     [r11], dl
0x1800235f9  cmovz   r9d, ebp
0x1800235fd  cmovnz  eax, edi
0x180023600  jmp     short loc_1800235B0
0x180023602  jns     short loc_180023613
0x180023604  mov     rax, r8
0x180023607  sub     rax, rcx
0x18002360a  cmp     rdx, rax
0x18002360d  jl      loc_180023583
0x180023613  lea     r11, [rdx+rcx]
0x180023617  mov     edx, 1DAF2Bh
0x18002361c  jmp     loc_18002378D
0x180023621  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002362b  cmp     edx, 1DAF2Bh
0x180023631  jz      loc_180023380
0x180023637  mov     edx, 0ED7958h
0x18002363c  jmp     loc_180023380
0x180023641  cmp     edx, 2165106h
0x180023647  ja      loc_1800237AB
0x18002364d  jz      loc_1800236EB
0x180023653  cmp     edx, 0ED7958h
0x180023659  jz      loc_1800238F8
0x18002365f  cmp     edx, 10B2883h
0x180023665  jz      short loc_1800236C3
0x180023667  cmp     edx, 1F8A1DBh
0x18002366d  jnz     loc_180023380
0x180023673  test    r11, r11
0x180023676  jnz     short loc_180023682
0x180023678  mov     edx, 0ED7958h
0x18002367d  jmp     loc_180023380
0x180023682  movdqa  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002368a  mov     edx, 2684h
0x18002368f  mov     word ptr [rsp+78h+var_50+8], dx
0x180023694  mov     esi, 3Ah ; ':'
0x180023699  mov     dword ptr [rsp+78h+var_50+4], 3008003Ah
0x1800236a1  mov     ebp, 3008h
0x1800236a6  movdqu  xmm0, [rsp+78h+var_50]
0x1800236ac  mov     ebx, 0FFFFh
0x1800236b1  mov     edx, 2165106h
0x1800236b6  movdqa  xmm2, xmm0
0x1800236ba  pxor    xmm3, xmm0
0x1800236be  jmp     loc_180023380
0x1800236c3  movsx   eax, bx
0x1800236c6  mov     edx, 946BD7h
0x1800236cb  movd    xmm3, eax
0x1800236cf  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800236d9  punpcklwd xmm3, xmm3
0x1800236dd  pshufd  xmm3, xmm3, 0
0x1800236e2  pxor    xmm3, xmm2
0x1800236e6  jmp     loc_180023380
0x1800236eb  movzx   r10d, byte ptr [r11]
0x1800236ef  movzx   r9d, byte ptr [r11+2]
0x1800236f4  movzx   eax, r10b
0x1800236f8  movzx   edx, byte ptr [r11+3]
0x1800236fd  shl     al, 3
0x180023700  movzx   eax, al
0x180023703  imul    eax, 3Ah ; ':'
0x180023706  imul    ecx, edx, 3Ah ; ':'
0x180023709  shr     dl, 2
0x18002370c  mov     word ptr [rsp+78h+var_50], ax
0x180023711  movzx   edi, ax
0x180023714  movzx   eax, byte ptr [r11+1]
0x180023719  movzx   ebp, cx
0x18002371c  imul    r8d, eax, 3Ah ; ':'
0x180023720  movzx   eax, r9b
0x180023724  shr     al, 5
0x180023727  movzx   eax, al
0x18002372a  imul    eax, 3Ah ; ':'
0x18002372d  mov     word ptr [rsp+78h+var_50+6], cx
0x180023732  imul    ecx, r10d, 3Ah ; ':'
0x180023736  mov     word ptr [rsp+78h+var_50+2], r8w
0x18002373c  mov     word ptr [rsp+78h+var_50+0Ah], r8w
0x180023742  mov     word ptr [rsp+78h+var_50+4], ax
0x180023747  movzx   esi, ax
0x18002374a  movzx   eax, dl
0x18002374d  mov     edx, 2340031h
0x180023752  imul    eax, 3Ah ; ':'
0x180023755  mov     word ptr [rsp+78h+var_50+8], cx
0x18002375a  imul    ecx, r9d, 3Ah ; ':'
0x18002375e  xor     r10b, r10b
0x180023761  mov     word ptr [rsp+78h+var_50+0Eh], ax
0x180023766  movzx   r9d, ax
0x18002376a  movsx   eax, bx
0x18002376d  mov     word ptr [rsp+78h+var_50+0Ch], cx
0x180023772  movdqu  xmm0, [rsp+78h+var_50]
0x180023778  movd    xmm4, eax
0x18002377c  punpcklwd xmm4, xmm4
0x180023780  movdqa  xmm1, xmm0
0x180023784  pshufd  xmm4, xmm4, 0
0x180023789  pxor    xmm4, xmm0
0x18002378d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180023797  mov     ecx, 1
0x18002379c  mov     r8, 8000000000000000h
0x1800237a6  jmp     loc_180023380
0x1800237ab  cmp     edx, 2340031h
0x1800237b1  jz      loc_1800238B6
0x1800237b7  cmp     edx, 251AF5Ch
0x1800237bd  jz      short loc_1800237EB
0x1800237bf  cmp     edx, 26F5E87h
0x1800237c5  jnz     loc_180023380
0x1800237cb  mov     edx, 122h
0x1800237d0  mov     dword ptr [rsp+78h+var_50+0Ah], 2A983918h
0x1800237d8  movzx   r9d, dx
0x1800237dc  mov     word ptr [rsp+78h+var_50+0Eh], dx
0x1800237e1  mov     edx, 1F8A1DBh
0x1800237e6  jmp     loc_180023372
0x1800237eb  cmp     bp, bx
0x1800237ee  jnz     short loc_180023800
0x1800237f0  cmp     di, bx
0x1800237f3  jnz     short loc_180023800
0x1800237f5  cmp     si, bx
0x1800237f8  movzx   r10d, r10b
0x1800237fc  cmovz   r10d, ecx
0x180023800  cmp     r9w, bx
0x180023804  jnz     loc_180023678
0x18002380a  movzx   eax, byte ptr [r11+3]
0x18002380f  and     al, 3
0x180023811  movzx   r8d, al
0x180023815  test    r8b, 2
0x180023819  lea     eax, [r8-4]
0x18002381d  movzx   ecx, al
0x180023820  movzx   eax, byte ptr [r11+2]
0x180023825  cmovz   ecx, r8d
0x180023829  movsx   edx, cl
0x18002382c  shl     edx, 8
0x18002382f  add     edx, eax
  ... truncated ...
```

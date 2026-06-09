# SDK::AgileServer::DeriveComprehensiveResource(SDK::AgileServer &,int)

- ea: `0x180013430`
- end: `0x180013a8d`
- name: `?DeriveComprehensiveResource@AgileServer@SDK@@SAXAEAV12@H@Z`
- size: `1629`
- prototype: `void __fastcall(struct SDK::AgileServer *this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x180013310`
- `0x180013430`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall SDK::AgileServer::DeriveComprehensiveResource(struct SDK::AgileServer *this, int a2)
{
  __int16 epi16; // si
  void (__fastcall *v5)(SDK::AgileServer *__hidden, int); // r11
  __int16 v6; // r14
  __int16 v7; // bx
  unsigned int v8; // ecx
  __int16 v9; // di
  char v10; // r9
  __m128i v11; // xmm1
  __m128i v12; // xmm2
  __m128i v13; // xmm4
  __m128i v14; // xmm3
  __m128i v15; // xmm0
  __m128i v16; // xmm1
  __int16 v17; // r14
  __m128i v18; // xmm4
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // edx
  __int64 v22; // r8
  void (__fastcall *MixedProvider)(void (__fastcall *)(struct SDK::AgileServer *, int), unsigned __int64, __int64); // rax
  __m128i v24; // xmm3
  __m128i v25; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int8 *retaddr; // [rsp+68h] [rbp+0h]

  epi16 = v25.m128i_i16[2];
  v5 = 0;
  v25.m128i_i32[0] = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 1;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
LABEL_2:
  v15 = _mm_loadu_si128(&v25);
  while ( 1 )
  {
    while ( v8 <= 0x20C724 )
    {
      if ( v8 == 2148132 )
      {
        if ( epi16 == v7 )
        {
          v19 = *(int *)((char *)v5 + 1);
          v10 = 1;
          if ( v19 <= 0 )
          {
            if ( v19 < 0 )
            {
              v8 = 2;
              if ( (__int64)&loc_180013312 + 3 < (__int64)(0x8000000000000000uLL - v19) )
                goto LABEL_27;
            }
          }
          else if ( (__int64)&loc_180013312 + 3 > 0x7FFFFFFFFFFFFFFFLL - v19 )
          {
            v8 = 2;
LABEL_27:
            v5 = (void (__fastcall *)(SDK::AgileServer *__hidden, int))((char *)&loc_180013312 + v19 + 3);
            goto LABEL_28;
          }
          v8 = 306876;
          goto LABEL_27;
        }
LABEL_28:
        if ( v9 == v7 )
        {
          v20 = *((char *)v5 + 1);
          v10 = 1;
          if ( (char)v20 <= 0 )
          {
            if ( (v20 & 0x80u) != 0LL && (__int64)&loc_180013312 < (__int64)(0x8000000000000000uLL - v20) )
              goto LABEL_31;
          }
          else if ( (__int64)&loc_180013312 > 0x7FFFFFFFFFFFFFFFLL - v20 )
          {
            goto LABEL_31;
          }
          v5 = (void (__fastcall *)(SDK::AgileServer *__hidden, int))((char *)&loc_180013312 + v20);
          v8 = 306876;
        }
        else if ( v8 != 306876 )
        {
          v8 = 2455008;
        }
      }
      else
      {
        if ( v8 <= 0xE0C34 )
        {
          if ( v8 == 920628 )
          {
            epi16 = 1398;
            v8 = 1227504;
            v25.m128i_i64[0] = 0x5E80576008A0582LL;
            v18 = _mm_cvtsi32_si128(v7);
            v9 = 1410;
            v13 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v18, v18), 0), v11);
          }
          else if ( v8 )
          {
            if ( v8 == 306876 )
            {
              v17 = *(unsigned __int8 *)v5;
              v25.m128i_i16[6] = 1224;
              v7 = -1;
              v8 = 613752;
              v6 = 6 * v17;
            }
            else
            {
              v8 = 920628;
              v25.m128i_i16[4] = 1020;
              v16 = _mm_cvtsi32_si128(v6);
              v11 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v16, v16), 0);
            }
          }
          else
          {
            v5 = SDK::AgileServer::BootstrapOptimalData;
            v25.m128i_i16[7] = 1128;
            v25.m128i_i16[5] = 1512;
            v8 = 306876;
          }
          goto LABEL_2;
        }
        if ( v8 == 1227504 )
        {
          v12 = v15;
          v8 = 2761884;
        }
        else if ( v8 == 1534380 )
        {
          v12 = _mm_and_si128(v12, v11);
          v10 = 0;
          v8 = 1841256;
          v11 = _mm_and_si128(v14, v13);
        }
        else
        {
          v11 = _mm_or_si128(v11, v12);
          v15 = v11;
          v9 = _mm_cvtsi128_si32(v11);
          v25 = v11;
          epi16 = _mm_extract_epi16(v11, 2);
          if ( (unsigned __int16)_mm_extract_epi16(v11, 6) == v7 )
          {
            v10 = 1;
            v8 = 2455008;
          }
          else
          {
            v8 = 2148132;
          }
        }
      }
    }
    if ( v8 == 2455008 )
      break;
    v8 = 1534380;
    v24 = _mm_cvtsi32_si128(v7);
    v14 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v24, v24), 0), v12);
  }
  if ( !v10 )
  {
LABEL_31:
    v21 = IntegralRelation::OddMap;
    goto LABEL_32;
  }
  v21 = ++IntegralRelation::OddMap;
LABEL_32:
  v22 = *retaddr;
  if ( (float)(166605 * v22) > 33836148.0 && (float)(137679 * v22) < 28093380.0 || (v21 ^ 0xFBC104EB) != 0x468B8 )
    IntegralRelation::OddMap = v21 + 1;
  MixedProvider = (void (__fastcall *)(void (__fastcall *)(struct SDK::AgileServer *, int), unsigned __int64, __int64))GenerateMixedProvider(0xDF8F9FFFA0206070uLL, 825516074, v22);
  MixedProvider(
    SDK::AgileServer::DeriveComprehensiveResource,
    (unsigned __int64)SDK::AgileServer::DeriveComprehensiveResource ^ 0x1B0D11,
    724225);
  SDK::AgileServer::BootstrapOptimalData(this, a2);
}

```

## disassembly

```asm
0x180013430  mov     [rsp+arg_10], rbx
0x180013435  push    rbp
0x180013436  push    rsi
0x180013437  push    rdi
0x180013438  push    r12
0x18001343a  push    r13
0x18001343c  push    r14
0x18001343e  push    r15
0x180013440  sub     rsp, 30h
0x180013444  movzx   r10d, word ptr [rsp+68h+var_48+0Eh]
0x18001344a  xor     eax, eax
0x18001344c  movzx   ebp, word ptr [rsp+68h+var_48+6]
0x180013451  mov     r12d, edx
0x180013454  movzx   esi, word ptr [rsp+68h+var_48+4]
0x180013459  mov     r15, rcx
0x18001345c  mov     r11d, eax
0x18001345f  mov     dword ptr [rsp+68h+var_48], eax
0x180013463  movzx   r14d, ax
0x180013467  movzx   ebx, ax
0x18001346a  mov     ecx, eax
0x18001346c  movzx   edi, ax
0x18001346f  mov     r9b, 1
0x180013472  xorps   xmm1, xmm1
0x180013475  xorps   xmm2, xmm2
0x180013478  xorps   xmm4, xmm4
0x18001347b  xorps   xmm3, xmm3
0x18001347e  mov     edx, 5E8h
0x180013483  mov     r8d, 468h
0x180013489  mov     r13, 7FFFFFFFFFFFFFFFh
0x180013493  mov     rax, 8000000000000000h
0x18001349d  movdqu  xmm0, [rsp+68h+var_48]
0x1800134a3  cmp     ecx, 20C724h
0x1800134a9  ja      loc_18001378D
0x1800134af  jz      loc_180013610
0x1800134b5  cmp     ecx, 0E0C34h
0x1800134bb  ja      loc_180013580
0x1800134c1  jz      loc_180013548
0x1800134c7  test    ecx, ecx
0x1800134c9  jz      short loc_180013529
0x1800134cb  cmp     ecx, 4AEBCh
0x1800134d1  jz      short loc_1800134FD
0x1800134d3  cmp     ecx, 95D78h
0x1800134d9  jnz     short loc_1800134A3
0x1800134db  mov     eax, 3FCh
0x1800134e0  mov     ecx, 0E0C34h
0x1800134e5  mov     word ptr [rsp+68h+var_48+8], ax
0x1800134ea  movsx   eax, r14w
0x1800134ee  movd    xmm1, eax
0x1800134f2  punpcklwd xmm1, xmm1
0x1800134f6  pshufd  xmm1, xmm1, 0
0x1800134fb  jmp     short loc_180013493
0x1800134fd  movzx   r14d, byte ptr [r11]
0x180013501  mov     eax, 4C8h
0x180013506  mov     word ptr [rsp+68h+var_48+0Ch], ax
0x18001350b  mov     ebx, 0FFFFh
0x180013510  movzx   eax, r14w
0x180013514  mov     ecx, 95D78h
0x180013519  add     ax, ax
0x18001351c  add     r14w, ax
0x180013520  add     r14w, r14w
0x180013524  jmp     loc_180013493
0x180013529  lea     r11, ?BootstrapOptimalData@AgileServer@SDK@@IEAAXH@Z; SDK::AgileServer::BootstrapOptimalData(int)
0x180013530  mov     word ptr [rsp+68h+var_48+0Eh], r8w
0x180013536  mov     r10d, r8d
0x180013539  mov     word ptr [rsp+68h+var_48+0Ah], dx
0x18001353e  mov     ecx, 4AEBCh
0x180013543  jmp     loc_18001349D
0x180013548  movsx   eax, bx
0x18001354b  mov     esi, 576h
0x180013550  mov     ecx, 12BAF0h
0x180013555  mov     dword ptr [rsp+68h+var_48+4], 5E80576h
0x18001355d  mov     ebp, edx
0x18001355f  mov     dword ptr [rsp+68h+var_48], 8A0582h
0x180013567  movd    xmm4, eax
0x18001356b  lea     edi, [rsi+0Ch]
0x18001356e  punpcklwd xmm4, xmm4
0x180013572  pshufd  xmm4, xmm4, 0
0x180013577  pxor    xmm4, xmm1
0x18001357b  jmp     loc_180013493
0x180013580  cmp     ecx, 12BAF0h
0x180013586  jz      short loc_180013602
0x180013588  cmp     ecx, 1769ACh
0x18001358e  jz      short loc_1800135E9
0x180013590  cmp     ecx, 1C1868h
0x180013596  jnz     loc_1800134A3
0x18001359c  por     xmm1, xmm2
0x1800135a0  pextrw  eax, xmm1, 6
0x1800135a5  movdqa  xmm0, xmm1
0x1800135a9  movd    edi, xmm1
0x1800135ad  movdqu  [rsp+68h+var_48], xmm1
0x1800135b3  cmp     ax, bx
0x1800135b6  mov     rax, 8000000000000000h
0x1800135c0  pextrw  r10d, xmm1, 7
0x1800135c6  pextrw  ebp, xmm1, 3
0x1800135cb  pextrw  esi, xmm1, 2
0x1800135d0  jnz     short loc_1800135DF
0x1800135d2  mov     r9b, 1
0x1800135d5  mov     ecx, 2575E0h
0x1800135da  jmp     loc_1800134A3
0x1800135df  mov     ecx, 20C724h
0x1800135e4  jmp     loc_1800134A3
0x1800135e9  pand    xmm2, xmm1
0x1800135ed  xor     r9b, r9b
0x1800135f0  movdqa  xmm1, xmm3
0x1800135f4  mov     ecx, 1C1868h
0x1800135f9  pand    xmm1, xmm4
0x1800135fd  jmp     loc_1800134A3
0x180013602  movdqa  xmm2, xmm0
0x180013606  mov     ecx, 2A249Ch
0x18001360b  jmp     loc_1800134A3
0x180013610  cmp     si, bx
0x180013613  jnz     short loc_180013661
0x180013615  movsxd  rdx, dword ptr [r11+1]
0x180013619  lea     r8, ?BootstrapOptimalData@AgileServer@SDK@@IEAAXH@Z; SDK::AgileServer::BootstrapOptimalData(int)
0x180013620  add     r8, 5
0x180013624  mov     r9b, 1
0x180013627  test    rdx, rdx
0x18001362a  jle     short loc_18001363E
0x18001362c  mov     rax, r13
0x18001362f  sub     rax, rdx
0x180013632  cmp     r8, rax
0x180013635  jle     short loc_18001364D
0x180013637  mov     ecx, 2
0x18001363c  jmp     short loc_180013652
0x18001363e  jns     short loc_18001364D
0x180013640  sub     rax, rdx
0x180013643  mov     ecx, 2
0x180013648  cmp     r8, rax
0x18001364b  jl      short loc_180013652
0x18001364d  mov     ecx, 4AEBCh
0x180013652  lea     r11, [r8+rdx]
0x180013656  mov     edx, 5E8h
0x18001365b  mov     r8d, 468h
0x180013661  cmp     di, bx
0x180013664  jnz     loc_18001376D
0x18001366a  movsx   rax, byte ptr [r11+1]
0x18001366f  lea     rdx, ?BootstrapOptimalData@AgileServer@SDK@@IEAAXH@Z; SDK::AgileServer::BootstrapOptimalData(int)
0x180013676  add     rdx, 2
0x18001367a  mov     r9b, 1
0x18001367d  mov     rcx, rax
0x180013680  test    al, al
0x180013682  jle     loc_180013747
0x180013688  mov     rax, r13
0x18001368b  sub     rax, rcx
0x18001368e  cmp     rdx, rax
0x180013691  jle     loc_18001375F
0x180013697  mov     edx, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18001369d  mov     rax, [rsp+68h]
0x1800136a2  xorps   xmm0, xmm0
0x1800136a5  movzx   r8d, byte ptr [rax]
0x1800136a9  imul    ecx, r8d, 28ACDh
0x1800136b0  cvtsi2ss xmm0, rcx
0x1800136b5  comiss  xmm0, cs:__real@4c01131d
0x1800136bc  jbe     short loc_1800136DA
0x1800136be  movss   xmm0, cs:__real@4bd655e2
0x1800136c6  xorps   xmm1, xmm1
0x1800136c9  imul    ecx, r8d, 219CFh
0x1800136d0  cvtsi2ss xmm1, rcx
0x1800136d5  comiss  xmm0, xmm1
0x1800136d8  ja      short loc_1800136E8
0x1800136da  mov     eax, edx
0x1800136dc  xor     eax, 0FBC104EBh
0x1800136e1  cmp     eax, 468B8h
0x1800136e6  jz      short loc_1800136F0
0x1800136e8  inc     edx
0x1800136ea  mov     cs:?OddMap@IntegralRelation@@2IA, edx; uint IntegralRelation::OddMap
0x1800136f0  mov     edx, 3134602Ah
0x1800136f5  mov     rcx, 0DF8F9FFFA0206070h
0x1800136ff  call    GenerateMixedProvider
0x180013704  lea     rdx, ?DeriveComprehensiveResource@AgileServer@SDK@@SAXAEAV12@H@Z; SDK::AgileServer::DeriveComprehensiveResource(SDK::AgileServer &,int)
0x18001370b  mov     r8d, 0B0D01h
0x180013711  xor     rdx, 1B0D11h
0x180013718  lea     rcx, ?DeriveComprehensiveResource@AgileServer@SDK@@SAXAEAV12@H@Z; SDK::AgileServer::DeriveComprehensiveResource(SDK::AgileServer &,int)
0x18001371f  call    cs:__guard_dispatch_icall_fptr
0x180013725  mov     edx, r12d; int
0x180013728  mov     rcx, r15; this
0x18001372b  mov     rbx, [rsp+68h+arg_10]
0x180013733  add     rsp, 30h
0x180013737  pop     r15
0x180013739  pop     r14
0x18001373b  pop     r13
0x18001373d  pop     r12
0x18001373f  pop     rdi
0x180013740  pop     rsi
0x180013741  pop     rbp
0x180013742  jmp     ?BootstrapOptimalData@AgileServer@SDK@@IEAAXH@Z; SDK::AgileServer::BootstrapOptimalData(int)
0x180013747  jns     short loc_18001375F
0x180013749  mov     r8, 8000000000000000h
0x180013753  sub     r8, rcx
0x180013756  cmp     rdx, r8
0x180013759  jl      loc_180013697
0x18001375f  lea     r11, [rcx+rdx]
0x180013763  mov     ecx, 4AEBCh
0x180013768  jmp     loc_180013920
0x18001376d  mov     rax, 8000000000000000h
0x180013777  cmp     ecx, 4AEBCh
0x18001377d  jz      loc_1800134A3
0x180013783  mov     ecx, 2575E0h
0x180013788  jmp     loc_1800134A3
0x18001378d  cmp     ecx, 544938h
0x180013793  ja      loc_18001393A
0x180013799  jz      loc_180013837
0x18001379f  cmp     ecx, 2575E0h
0x1800137a5  jz      loc_180013A71
0x1800137ab  cmp     ecx, 2A249Ch
0x1800137b1  jz      short loc_18001380F
0x1800137b3  cmp     ecx, 4F9A7Ch
0x1800137b9  jnz     loc_1800134A3
0x1800137bf  test    r11, r11
0x1800137c2  jnz     short loc_1800137CE
0x1800137c4  mov     ecx, 2575E0h
0x1800137c9  jmp     loc_1800134A3
0x1800137ce  movdqa  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800137d6  mov     ecx, 3FCh
0x1800137db  mov     word ptr [rsp+68h+var_48+8], cx
0x1800137e0  mov     esi, 6
0x1800137e5  mov     dword ptr [rsp+68h+var_48+4], 4F80006h
0x1800137ed  mov     ebp, 4F8h
0x1800137f2  movdqu  xmm0, [rsp+68h+var_48]
0x1800137f8  mov     ebx, 0FFFFh
0x1800137fd  mov     ecx, 544938h
0x180013802  movdqa  xmm2, xmm0
0x180013806  pxor    xmm3, xmm0
0x18001380a  jmp     loc_1800134A3
0x18001380f  movsx   eax, bx
0x180013812  mov     ecx, 1769ACh
0x180013817  movd    xmm3, eax
0x18001381b  mov     rax, 8000000000000000h
0x180013825  punpcklwd xmm3, xmm3
0x180013829  pshufd  xmm3, xmm3, 0
0x18001382e  pxor    xmm3, xmm2
0x180013832  jmp     loc_1800134A3
0x180013837  movzx   r10d, byte ptr [r11]
0x18001383b  movzx   r8d, byte ptr [r11+2]
0x180013840  movzx   eax, r10b
0x180013844  movzx   edx, byte ptr [r11+3]
0x180013849  movzx   r9d, byte ptr [r11+1]
0x18001384e  shl     al, 3
0x180013851  movzx   ecx, al
0x180013854  movzx   eax, cx
0x180013857  add     ax, ax
0x18001385a  add     cx, ax
0x18001385d  movzx   eax, r9w
0x180013861  add     ax, ax
0x180013864  add     cx, cx
0x180013867  add     r9w, ax
0x18001386b  mov     word ptr [rsp+68h+var_48], cx
0x180013870  movzx   edi, cx
0x180013873  movzx   eax, r8b
0x180013877  shr     al, 5
0x18001387a  add     r9w, r9w
0x18001387e  movzx   ecx, al
0x180013881  movzx   eax, cx
0x180013884  mov     word ptr [rsp+68h+var_48+2], r9w
0x18001388a  add     ax, ax
0x18001388d  mov     word ptr [rsp+68h+var_48+0Ah], r9w
0x180013893  add     cx, ax
0x180013896  movzx   eax, dx
0x180013899  add     ax, ax
0x18001389c  add     cx, cx
0x18001389f  mov     word ptr [rsp+68h+var_48+4], cx
0x1800138a4  movzx   esi, cx
0x1800138a7  lea     ecx, [rax+rdx]
0x1800138aa  movzx   eax, r10w
0x1800138ae  add     ax, ax
0x1800138b1  shr     dl, 2
0x1800138b4  add     r10w, ax
0x1800138b8  add     cx, cx
0x1800138bb  mov     word ptr [rsp+68h+var_48+6], cx
0x1800138c0  movzx   eax, r8w
0x1800138c4  add     ax, ax
0x1800138c7  movzx   ebp, cx
0x1800138ca  add     r8w, ax
0x1800138ce  movzx   ecx, dl
0x1800138d1  movzx   eax, cx
0x1800138d4  add     r10w, r10w
0x1800138d8  add     ax, ax
0x1800138db  mov     word ptr [rsp+68h+var_48+8], r10w
0x1800138e1  add     cx, ax
0x1800138e4  add     r8w, r8w
0x1800138e8  add     cx, cx
0x1800138eb  movsx   eax, bx
0x1800138ee  mov     word ptr [rsp+68h+var_48+0Eh], cx
0x1800138f3  movzx   r10d, cx
0x1800138f7  mov     word ptr [rsp+68h+var_48+0Ch], r8w
0x1800138fd  xor     r9b, r9b
0x180013900  movdqu  xmm0, [rsp+68h+var_48]
0x180013906  mov     ecx, 58F7F4h
0x18001390b  movd    xmm4, eax
0x18001390f  punpcklwd xmm4, xmm4
0x180013913  movdqa  xmm1, xmm0
0x180013917  pshufd  xmm4, xmm4, 0
0x18001391c  pxor    xmm4, xmm0
0x180013920  mov     rax, 8000000000000000h
0x18001392a  mov     edx, 5E8h
0x18001392f  mov     r8d, 468h
0x180013935  jmp     loc_1800134A3
0x18001393a  cmp     ecx, 58F7F4h
0x180013940  jz      loc_180013A2F
0x180013946  cmp     ecx, 5DA6B0h
  ... truncated ...
```

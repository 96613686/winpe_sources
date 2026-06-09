# Input::VirtualFeature::OrderComprehensiveResolution(Input::VirtualFeature &,Input::GeneralEvent &)

- ea: `0x180038720`
- end: `0x180038cfc`
- name: `?OrderComprehensiveResolution@VirtualFeature@Input@@SAXAEAV12@AEAVGeneralEvent@2@@Z`
- size: `1500`
- prototype: `void __fastcall(struct Input::VirtualFeature *this, struct Input::GeneralEvent *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x180035820`
- `0x180038720`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::VirtualFeature::OrderComprehensiveResolution(
        struct Input::VirtualFeature *this,
        struct Input::GeneralEvent *a2,
        __int64 a3,
        __int64 a4)
{
  __int16 epi16; // di
  void (__fastcall *v6)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *); // r10
  __int16 v7; // r14
  __int16 v8; // r11
  unsigned int v9; // eax
  __int16 v10; // bx
  __m128i v12; // xmm1
  __m128i v13; // xmm2
  __m128i v14; // xmm4
  __m128i v15; // xmm3
  __m128i v16; // xmm0
  __m128i v17; // xmm1
  __int16 v18; // r14
  __m128i v19; // xmm4
  __int64 v20; // rcx
  __int64 v21; // rax
  char *v22; // rdx
  __int64 v23; // r8
  void (__fastcall *MixedProvider)(void (__fastcall *)(struct Input::VirtualFeature *, struct Input::GeneralEvent *), unsigned __int64, __int64); // rax
  __m128i v25; // xmm3
  __m128i v26; // [rsp+20h] [rbp-48h] BYREF
  _BYTE *retaddr; // [rsp+68h] [rbp+0h]

  epi16 = v26.m128i_i16[2];
  v6 = 0;
  v7 = 0;
  v26.m128i_i32[0] = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  LOBYTE(a4) = 1;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
LABEL_2:
  v16 = _mm_loadu_si128(&v26);
  while ( 1 )
  {
    while ( v9 <= 0x188A1E )
    {
      if ( v9 == 1608222 )
      {
        if ( epi16 == v8 )
        {
          v20 = *(int *)((char *)v6 + 1);
          LOBYTE(a4) = 1;
          if ( v20 <= 0 )
          {
            if ( v20 >= 0 || (__int64)&loc_180035825 >= (__int64)(0x8000000000000000uLL - v20) )
            {
LABEL_28:
              v6 = (void (__fastcall *)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *))((char *)&loc_180035825 + v20);
              v9 = 229746;
              goto LABEL_29;
            }
            v9 = 2;
            v6 = (void (__fastcall *)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *))((char *)&loc_180035825 + v20);
          }
          else
          {
            if ( (__int64)&loc_180035825 <= 0x7FFFFFFFFFFFFFFFLL - v20 )
              goto LABEL_28;
            v9 = 2;
            v6 = (void (__fastcall *)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *))((char *)&loc_180035825 + v20);
          }
        }
LABEL_29:
        if ( v10 == v8 )
        {
          v21 = *((char *)v6 + 1);
          v22 = (char *)Input::VirtualFeature::DivideFlatSkill + 2;
          LOBYTE(a4) = 1;
          if ( (char)v21 <= 0 )
          {
            if ( (v21 & 0x80u) != 0LL && (__int64)v22 < (__int64)(0x8000000000000000uLL - v21) )
              goto LABEL_32;
          }
          else if ( (__int64)v22 > 0x7FFFFFFFFFFFFFFFLL - v21 )
          {
            goto LABEL_32;
          }
          v6 = (void (__fastcall *)(Input::VirtualFeature *__hidden, struct Input::GeneralEvent *))&v22[v21];
          v9 = 229746;
        }
        else if ( v9 != 229746 )
        {
          v9 = 1837968;
        }
      }
      else
      {
        if ( v9 <= 0xA8456 )
        {
          if ( v9 == 689238 )
          {
            epi16 = 14912;
            v26.m128i_i64[0] = 0x3F003A4005C03AC0LL;
            v10 = 15040;
            v19 = _mm_cvtsi32_si128(v8);
            v9 = 918984;
            v14 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v19, v19), 0), v12);
          }
          else if ( v9 )
          {
            if ( v9 == 229746 )
            {
              v18 = *(unsigned __int8 *)v6;
              v26.m128i_i16[6] = 13056;
              v8 = -1;
              v9 = 459492;
              v7 = v18 << 6;
            }
            else
            {
              v26.m128i_i16[4] = 10880;
              v17 = _mm_cvtsi32_si128(v7);
              v9 = 689238;
              v12 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v17, v17), 0);
            }
          }
          else
          {
            v6 = Input::VirtualFeature::DivideFlatSkill;
            v26.m128i_i16[7] = 12032;
            v26.m128i_i16[5] = 16128;
            v9 = 229746;
          }
          goto LABEL_2;
        }
        if ( v9 == 918984 )
        {
          v13 = v16;
          v9 = 2067714;
        }
        else if ( v9 == 1148730 )
        {
          v13 = _mm_and_si128(v13, v12);
          LOBYTE(a4) = 0;
          v9 = 1378476;
          v12 = _mm_and_si128(v15, v14);
        }
        else
        {
          v12 = _mm_or_si128(v12, v13);
          v16 = v12;
          v26 = v12;
          if ( (unsigned __int16)_mm_extract_epi16(v12, 6) == v8 )
          {
            LOBYTE(a4) = 1;
            v9 = 1837968;
          }
          else
          {
            v9 = 1608222;
          }
          epi16 = _mm_extract_epi16(v12, 2);
          v10 = _mm_cvtsi128_si32(v12);
        }
      }
    }
    if ( v9 == 1837968 )
      break;
    v25 = _mm_cvtsi32_si128(v8);
    v9 = 1148730;
    v15 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v25, v25), 0), v13);
  }
  if ( !(_BYTE)a4 )
  {
LABEL_32:
    v23 = IntegralRelation::OddMap;
    goto LABEL_33;
  }
  v23 = ++IntegralRelation::OddMap;
LABEL_33:
  if ( *retaddr == (unsigned __int8)(((unsigned int)v23 ^ 0xEF7771BB) / 0x19F89E)
    || ((unsigned int)v23 ^ 0xFBA6C263) != 0x63AE30 )
  {
    v23 = (unsigned int)(v23 + 1);
    IntegralRelation::OddMap = v23;
  }
  MixedProvider = (void (__fastcall *)(void (__fastcall *)(struct Input::VirtualFeature *, struct Input::GeneralEvent *), unsigned __int64, __int64))GenerateMixedProvider(0xF2FBF5F2090A010LL, 3784589450LL, v23, a4);
  MixedProvider(
    Input::VirtualFeature::OrderComprehensiveResolution,
    (unsigned __int64)Input::VirtualFeature::OrderComprehensiveResolution ^ 0x3051B5,
    2118053);
  Input::VirtualFeature::DivideFlatSkill(this, a2);
}

```

## disassembly

```asm
0x180038720  mov     [rsp+arg_10], rbx
0x180038725  push    rbp
0x180038726  push    rsi
0x180038727  push    rdi
0x180038728  push    r12
0x18003872a  push    r13
0x18003872c  push    r14
0x18003872e  push    r15
0x180038730  sub     rsp, 30h
0x180038734  movzx   esi, word ptr [rsp+68h+var_48+0Eh]
0x180038739  mov     r15, rcx
0x18003873c  movzx   ebp, word ptr [rsp+68h+var_48+6]
0x180038741  xor     ecx, ecx
0x180038743  movzx   edi, word ptr [rsp+68h+var_48+4]
0x180038748  mov     r10d, ecx
0x18003874b  movzx   r14d, cx
0x18003874f  mov     dword ptr [rsp+68h+var_48], ecx
0x180038753  movzx   r11d, cx
0x180038757  mov     eax, ecx
0x180038759  movzx   ebx, cx
0x18003875c  mov     r12, rdx
0x18003875f  mov     r9b, 1
0x180038762  xorps   xmm1, xmm1
0x180038765  xorps   xmm2, xmm2
0x180038768  xorps   xmm4, xmm4
0x18003876b  xorps   xmm3, xmm3
0x18003876e  mov     r13, 7FFFFFFFFFFFFFFFh
0x180038778  mov     r8, 8000000000000000h
0x180038782  mov     ecx, 3F00h
0x180038787  mov     edx, 2F00h
0x18003878c  movdqu  xmm0, [rsp+68h+var_48]
0x180038792  cmp     eax, 188A1Eh
0x180038797  ja      loc_180038A47
0x18003879d  jz      loc_1800388E1
0x1800387a3  cmp     eax, 0A8456h
0x1800387a8  ja      loc_18003885C
0x1800387ae  jz      short loc_180038821
0x1800387b0  test    eax, eax
0x1800387b2  jz      short loc_180038804
0x1800387b4  cmp     eax, 38172h
0x1800387b9  jz      short loc_1800387E4
0x1800387bb  cmp     eax, 702E4h
0x1800387c0  jnz     short loc_180038792
0x1800387c2  mov     eax, 2A80h
0x1800387c7  mov     word ptr [rsp+68h+var_48+8], ax
0x1800387cc  movsx   eax, r14w
0x1800387d0  movd    xmm1, eax
0x1800387d4  mov     eax, 0A8456h
0x1800387d9  punpcklwd xmm1, xmm1
0x1800387dd  pshufd  xmm1, xmm1, 0
0x1800387e2  jmp     short loc_18003878C
0x1800387e4  movzx   r14d, byte ptr [r10]
0x1800387e8  mov     eax, 3300h
0x1800387ed  mov     word ptr [rsp+68h+var_48+0Ch], ax
0x1800387f2  mov     r11d, 0FFFFh
0x1800387f8  mov     eax, 702E4h
0x1800387fd  shl     r14w, 6
0x180038802  jmp     short loc_18003878C
0x180038804  lea     r10, ?DivideFlatSkill@VirtualFeature@Input@@QEAAXAEAVGeneralEvent@2@@Z; Input::VirtualFeature::DivideFlatSkill(Input::GeneralEvent &)
0x18003880b  mov     word ptr [rsp+68h+var_48+0Eh], dx
0x180038810  mov     esi, edx
0x180038812  mov     word ptr [rsp+68h+var_48+0Ah], cx
0x180038817  mov     eax, 38172h
0x18003881c  jmp     loc_18003878C
0x180038821  movsx   eax, r11w
0x180038825  mov     ebp, ecx
0x180038827  mov     dword ptr [rsp+68h+var_48+4], 3F003A40h
0x18003882f  mov     edi, 3A40h
0x180038834  mov     dword ptr [rsp+68h+var_48], 5C03AC0h
0x18003883c  mov     ebx, 3AC0h
0x180038841  movd    xmm4, eax
0x180038845  mov     eax, 0E05C8h
0x18003884a  punpcklwd xmm4, xmm4
0x18003884e  pshufd  xmm4, xmm4, 0
0x180038853  pxor    xmm4, xmm1
0x180038857  jmp     loc_18003878C
0x18003885c  cmp     eax, 0E05C8h
0x180038861  jz      short loc_1800388D3
0x180038863  cmp     eax, 11873Ah
0x180038868  jz      short loc_1800388BA
0x18003886a  cmp     eax, 1508ACh
0x18003886f  jnz     loc_180038792
0x180038875  por     xmm1, xmm2
0x180038879  pextrw  eax, xmm1, 6
0x18003887e  movdqa  xmm0, xmm1
0x180038882  movdqu  [rsp+68h+var_48], xmm1
0x180038888  cmp     ax, r11w
0x18003888c  jnz     short loc_180038898
0x18003888e  mov     r9b, 1
0x180038891  mov     eax, 1C0B90h
0x180038896  jmp     short loc_18003889D
0x180038898  mov     eax, 188A1Eh
0x18003889d  pextrw  esi, xmm1, 7
0x1800388a2  pextrw  ebp, xmm1, 3
0x1800388a7  pextrw  edi, xmm1, 2
0x1800388ac  movd    ebx, xmm1
0x1800388b0  mov     ecx, 3F00h
0x1800388b5  jmp     loc_180038792
0x1800388ba  pand    xmm2, xmm1
0x1800388be  xor     r9b, r9b
0x1800388c1  movdqa  xmm1, xmm3
0x1800388c5  mov     eax, 1508ACh
0x1800388ca  pand    xmm1, xmm4
0x1800388ce  jmp     loc_180038792
0x1800388d3  movdqa  xmm2, xmm0
0x1800388d7  mov     eax, 1F8D02h
0x1800388dc  jmp     loc_180038792
0x1800388e1  cmp     di, r11w
0x1800388e5  jnz     short loc_18003893F
0x1800388e7  movsxd  rcx, dword ptr [r10+1]
0x1800388eb  lea     rdx, ?DivideFlatSkill@VirtualFeature@Input@@QEAAXAEAVGeneralEvent@2@@Z; Input::VirtualFeature::DivideFlatSkill(Input::GeneralEvent &)
0x1800388f2  add     rdx, 5
0x1800388f6  mov     r9b, 1
0x1800388f9  test    rcx, rcx
0x1800388fc  jle     short loc_180038914
0x1800388fe  mov     rax, r13
0x180038901  sub     rax, rcx
0x180038904  cmp     rdx, rax
0x180038907  jle     short loc_18003892C
0x180038909  mov     eax, 2
0x18003890e  lea     r10, [rcx+rdx]
0x180038912  jmp     short loc_180038935
0x180038914  jns     short loc_18003892C
0x180038916  mov     rax, r8
0x180038919  sub     rax, rcx
0x18003891c  cmp     rdx, rax
0x18003891f  jge     short loc_18003892C
0x180038921  mov     eax, 2
0x180038926  lea     r10, [rcx+rdx]
0x18003892a  jmp     short loc_180038935
0x18003892c  lea     r10, [rdx+rcx]
0x180038930  mov     eax, 38172h
0x180038935  mov     ecx, 3F00h
0x18003893a  mov     edx, 2F00h
0x18003893f  cmp     bx, r11w
0x180038943  jnz     loc_180038A32
0x180038949  movsx   rax, byte ptr [r10+1]
0x18003894e  lea     rdx, ?DivideFlatSkill@VirtualFeature@Input@@QEAAXAEAVGeneralEvent@2@@Z; Input::VirtualFeature::DivideFlatSkill(Input::GeneralEvent &)
0x180038955  add     rdx, 2
0x180038959  mov     r9b, 1
0x18003895c  mov     rcx, rax
0x18003895f  test    al, al
0x180038961  jle     loc_180038A09
0x180038967  mov     rax, r13
0x18003896a  sub     rax, rcx
0x18003896d  cmp     rdx, rax
0x180038970  jle     loc_180038A1A
0x180038976  mov     r8d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18003897d  mov     eax, 9DB6A12Bh
0x180038982  mov     ecx, r8d
0x180038985  xor     ecx, 0EF7771BBh
0x18003898b  mul     ecx
0x18003898d  mov     rax, [rsp+68h]
0x180038992  shr     edx, 14h
0x180038995  cmp     [rax], dl
0x180038997  jz      short loc_1800389A8
0x180038999  mov     eax, r8d
0x18003899c  xor     eax, 0FBA6C263h
0x1800389a1  cmp     eax, 63AE30h
0x1800389a6  jz      short loc_1800389B2
0x1800389a8  inc     r8d
0x1800389ab  mov     cs:?OddMap@IntegralRelation@@2IA, r8d; uint IntegralRelation::OddMap
0x1800389b2  mov     edx, 0E194408Ah
0x1800389b7  mov     rcx, 0F2FBF5F2090A010h
0x1800389c1  call    GenerateMixedProvider
0x1800389c6  lea     rdx, ?OrderComprehensiveResolution@VirtualFeature@Input@@SAXAEAV12@AEAVGeneralEvent@2@@Z; Input::VirtualFeature::OrderComprehensiveResolution(Input::VirtualFeature &,Input::GeneralEvent &)
0x1800389cd  mov     r8d, 2051A5h
0x1800389d3  xor     rdx, 3051B5h
0x1800389da  lea     rcx, ?OrderComprehensiveResolution@VirtualFeature@Input@@SAXAEAV12@AEAVGeneralEvent@2@@Z; Input::VirtualFeature::OrderComprehensiveResolution(Input::VirtualFeature &,Input::GeneralEvent &)
0x1800389e1  call    cs:__guard_dispatch_icall_fptr
0x1800389e7  mov     rdx, r12; struct Input::GeneralEvent *
0x1800389ea  mov     rcx, r15; this
0x1800389ed  mov     rbx, [rsp+68h+arg_10]
0x1800389f5  add     rsp, 30h
0x1800389f9  pop     r15
0x1800389fb  pop     r14
0x1800389fd  pop     r13
0x1800389ff  pop     r12
0x180038a01  pop     rdi
0x180038a02  pop     rsi
0x180038a03  pop     rbp
0x180038a04  jmp     ?DivideFlatSkill@VirtualFeature@Input@@QEAAXAEAVGeneralEvent@2@@Z; Input::VirtualFeature::DivideFlatSkill(Input::GeneralEvent &)
0x180038a09  jns     short loc_180038A1A
0x180038a0b  mov     rax, r8
0x180038a0e  sub     rax, rcx
0x180038a11  cmp     rdx, rax
0x180038a14  jl      loc_180038976
0x180038a1a  lea     r10, [rcx+rdx]
0x180038a1e  mov     eax, 38172h
0x180038a23  mov     ecx, 3F00h
0x180038a28  mov     edx, 2F00h
0x180038a2d  jmp     loc_180038792
0x180038a32  cmp     eax, 38172h
0x180038a37  jz      loc_180038792
0x180038a3d  mov     eax, 1C0B90h
0x180038a42  jmp     loc_180038792
0x180038a47  cmp     eax, 3F1A04h
0x180038a4c  ja      loc_180038BA9
0x180038a52  jz      loc_180038AE5
0x180038a58  cmp     eax, 1C0B90h
0x180038a5d  jz      loc_180038CDD
0x180038a63  cmp     eax, 1F8D02h
0x180038a68  jz      short loc_180038AC6
0x180038a6a  cmp     eax, 3B9892h
0x180038a6f  jnz     loc_180038792
0x180038a75  test    r10, r10
0x180038a78  jnz     short loc_180038A84
0x180038a7a  mov     eax, 1C0B90h
0x180038a7f  jmp     loc_180038792
0x180038a84  movdqa  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180038a8c  mov     eax, 2A80h
0x180038a91  mov     word ptr [rsp+68h+var_48+8], ax
0x180038a96  mov     edi, 40h ; '@'
0x180038a9b  mov     dword ptr [rsp+68h+var_48+4], 35000040h
0x180038aa3  mov     ebp, 3500h
0x180038aa8  movdqu  xmm0, [rsp+68h+var_48]
0x180038aae  mov     r11d, 0FFFFh
0x180038ab4  mov     eax, 3F1A04h
0x180038ab9  movdqa  xmm2, xmm0
0x180038abd  pxor    xmm3, xmm0
0x180038ac1  jmp     loc_180038792
0x180038ac6  movsx   eax, r11w
0x180038aca  movd    xmm3, eax
0x180038ace  mov     eax, 11873Ah
0x180038ad3  punpcklwd xmm3, xmm3
0x180038ad7  pshufd  xmm3, xmm3, 0
0x180038adc  pxor    xmm3, xmm2
0x180038ae0  jmp     loc_180038792
0x180038ae5  movzx   edx, byte ptr [r10+2]
0x180038aea  movzx   r9d, byte ptr [r10]
0x180038aee  movzx   r8d, byte ptr [r10+1]
0x180038af3  movzx   eax, r9b
0x180038af7  shl     al, 3
0x180038afa  movzx   ecx, al
0x180038afd  movzx   eax, dl
0x180038b00  shl     cx, 6
0x180038b04  shr     al, 5
0x180038b07  movzx   ebx, cx
0x180038b0a  mov     word ptr [rsp+68h+var_48], cx
0x180038b0f  movzx   ecx, al
0x180038b12  shl     cx, 6
0x180038b16  mov     word ptr [rsp+68h+var_48+4], cx
0x180038b1b  movzx   edi, cx
0x180038b1e  movzx   ecx, byte ptr [r10+3]
0x180038b23  movzx   eax, cx
0x180038b26  shl     r8w, 6
0x180038b2b  shl     ax, 6
0x180038b2f  mov     word ptr [rsp+68h+var_48+6], ax
0x180038b34  movzx   ebp, ax
0x180038b37  shr     cl, 2
0x180038b3a  movzx   eax, cl
0x180038b3d  mov     ecx, 3F00h
0x180038b42  shl     ax, 6
0x180038b46  mov     word ptr [rsp+68h+var_48+0Eh], ax
0x180038b4b  movzx   esi, ax
0x180038b4e  shl     dx, 6
0x180038b52  movsx   eax, r11w
0x180038b56  shl     r9w, 6
0x180038b5b  mov     word ptr [rsp+68h+var_48+2], r8w
0x180038b61  mov     word ptr [rsp+68h+var_48+8], r9w
0x180038b67  xor     r9b, r9b
0x180038b6a  movd    xmm4, eax
0x180038b6e  mov     eax, 429B76h
0x180038b73  mov     word ptr [rsp+68h+var_48+0Ah], r8w
0x180038b79  mov     r8, 8000000000000000h
0x180038b83  mov     word ptr [rsp+68h+var_48+0Ch], dx
0x180038b88  mov     edx, 2F00h
0x180038b8d  movdqu  xmm0, [rsp+68h+var_48]
0x180038b93  punpcklwd xmm4, xmm4
0x180038b97  pshufd  xmm4, xmm4, 0
0x180038b9c  movdqa  xmm1, xmm0
0x180038ba0  pxor    xmm4, xmm0
0x180038ba4  jmp     loc_180038792
0x180038ba9  cmp     eax, 429B76h
0x180038bae  jz      loc_180038CA1
0x180038bb4  cmp     eax, 461CE8h
0x180038bb9  jz      short loc_180038BE5
0x180038bbb  cmp     eax, 499E5Ah
0x180038bc0  jnz     loc_180038792
0x180038bc6  mov     eax, 140h
0x180038bcb  mov     dword ptr [rsp+68h+var_48+0Ah], 2F003F00h
0x180038bd3  movzx   esi, ax
0x180038bd6  mov     word ptr [rsp+68h+var_48+0Eh], ax
0x180038bdb  mov     eax, 3B9892h
0x180038be0  jmp     loc_18003878C
0x180038be5  cmp     bp, r11w
0x180038be9  jnz     short loc_180038C02
0x180038beb  cmp     bx, r11w
0x180038bef  jnz     short loc_180038C02
0x180038bf1  cmp     di, r11w
0x180038bf5  movzx   r9d, r9b
0x180038bf9  mov     eax, 1
0x180038bfe  cmovz   r9d, eax
0x180038c02  cmp     si, r11w
0x180038c06  jnz     loc_180038A7A
0x180038c0c  movzx   eax, byte ptr [r10+3]
0x180038c11  and     al, 3
0x180038c13  movzx   r8d, al
0x180038c17  test    r8b, 2
0x180038c1b  lea     eax, [r8-4]
  ... truncated ...
```

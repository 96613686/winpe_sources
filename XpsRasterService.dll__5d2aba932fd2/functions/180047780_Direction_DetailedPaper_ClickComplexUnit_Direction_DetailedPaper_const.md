# Direction::DetailedPaper::ClickComplexUnit(Direction::DetailedPaper const &)

- ea: `0x180047780`
- end: `0x180047d45`
- name: `?ClickComplexUnit@DetailedPaper@Direction@@SAHAEBV12@@Z`
- size: `1477`
- prototype: `__int64 __fastcall(const struct Direction::DetailedPaper *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x180047780`
- `0x180049740`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall Direction::DetailedPaper::ClickComplexUnit(
        const struct Direction::DetailedPaper *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int16 epi16; // si
  __int64 (__fastcall *v6)(Direction::DetailedPaper *__hidden); // r11
  __int16 v7; // r14
  __int16 v8; // bx
  unsigned int v9; // eax
  __int16 v10; // di
  __m128i v11; // xmm1
  __m128i v12; // xmm2
  __m128i v13; // xmm4
  __m128i v14; // xmm3
  __m128i v15; // xmm0
  __m128i v16; // xmm1
  __m128i v17; // xmm4
  __int64 v18; // rcx
  __int64 v19; // rax
  char *v20; // rdx
  __int64 v21; // r8
  void (__fastcall *MixedProvider)(__int64 (__fastcall *)(const struct Direction::DetailedPaper *), unsigned __int64, __int64); // rax
  __m128i v24; // xmm3
  __m128i v25; // [rsp+20h] [rbp-38h] BYREF
  _BYTE *retaddr; // [rsp+58h] [rbp+0h]

  epi16 = v25.m128i_i16[2];
  v6 = 0;
  v7 = 0;
  v25.m128i_i32[0] = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  LOBYTE(a4) = 1;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
LABEL_2:
  v15 = _mm_loadu_si128(&v25);
  while ( 1 )
  {
    while ( v9 <= 0xA652EC )
    {
      if ( v9 == 10900204 )
      {
        if ( epi16 == v8 )
        {
          v18 = *(int *)((char *)v6 + 1);
          LOBYTE(a4) = 1;
          if ( v18 <= 0 )
          {
            if ( v18 >= 0 || (__int64)&algn_180049744[1] >= (__int64)(0x8000000000000000uLL - v18) )
            {
LABEL_27:
              v6 = (__int64 (__fastcall *)(Direction::DetailedPaper *__hidden))&algn_180049744[v18 + 1];
              v9 = 1557172;
              goto LABEL_28;
            }
            v9 = 2;
            v6 = (__int64 (__fastcall *)(Direction::DetailedPaper *__hidden))&algn_180049744[v18 + 1];
          }
          else
          {
            if ( (__int64)&algn_180049744[1] <= 0x7FFFFFFFFFFFFFFFLL - v18 )
              goto LABEL_27;
            v9 = 2;
            v6 = (__int64 (__fastcall *)(Direction::DetailedPaper *__hidden))&algn_180049744[v18 + 1];
          }
        }
LABEL_28:
        if ( v10 == v8 )
        {
          v19 = *((char *)v6 + 1);
          v20 = (char *)Direction::DetailedPaper::RotateStripedSDK + 2;
          LOBYTE(a4) = 1;
          if ( (char)v19 <= 0 )
          {
            if ( (v19 & 0x80u) != 0LL && (__int64)v20 < (__int64)(0x8000000000000000uLL - v19) )
              goto LABEL_31;
          }
          else if ( (__int64)v20 > 0x7FFFFFFFFFFFFFFFLL - v19 )
          {
            goto LABEL_31;
          }
          v6 = (__int64 (__fastcall *)(Direction::DetailedPaper *__hidden))&v20[v19];
          v9 = 1557172;
        }
        else if ( v9 != 1557172 )
        {
          v9 = 12457376;
        }
      }
      else
      {
        if ( v9 <= 0x47481C )
        {
          if ( v9 == 4671516 )
          {
            epi16 = 18407;
            v25.m128i_i64[0] = 0x4DC447E707194885LL;
            v10 = 18565;
            v17 = _mm_cvtsi32_si128(v8);
            v9 = 6228688;
            v13 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v17, v17), 0), v11);
          }
          else if ( v9 )
          {
            if ( v9 == 1557172 )
            {
              v8 = -1;
              v25.m128i_i16[6] = 16116;
              v7 = 79 * *(unsigned __int8 *)v6;
              v9 = 3114344;
            }
            else
            {
              v25.m128i_i16[4] = 13430;
              v16 = _mm_cvtsi32_si128(v7);
              v9 = 4671516;
              v11 = _mm_shuffle_epi32(_mm_unpacklo_epi16(v16, v16), 0);
            }
          }
          else
          {
            v6 = Direction::DetailedPaper::RotateStripedSDK;
            v25.m128i_i16[7] = 14852;
            v25.m128i_i16[5] = 19908;
            v9 = 1557172;
          }
          goto LABEL_2;
        }
        if ( v9 == 6228688 )
        {
          v12 = v15;
          v9 = 14014548;
        }
        else if ( v9 == 7785860 )
        {
          v12 = _mm_and_si128(v12, v11);
          LOBYTE(a4) = 0;
          v9 = 9343032;
          v11 = _mm_and_si128(v14, v13);
        }
        else
        {
          v11 = _mm_or_si128(v11, v12);
          v15 = v11;
          v10 = _mm_cvtsi128_si32(v11);
          v25 = v11;
          epi16 = _mm_extract_epi16(v11, 2);
          if ( (unsigned __int16)_mm_extract_epi16(v11, 6) == v8 )
          {
            LOBYTE(a4) = 1;
            v9 = 12457376;
          }
          else
          {
            v9 = 10900204;
          }
        }
      }
    }
    if ( v9 == 12457376 )
      break;
    v24 = _mm_cvtsi32_si128(v8);
    v9 = 7785860;
    v14 = _mm_xor_si128(_mm_shuffle_epi32(_mm_unpacklo_epi16(v24, v24), 0), v12);
  }
  if ( !(_BYTE)a4 )
  {
LABEL_31:
    v21 = IntegralRelation::OddMap;
    goto LABEL_32;
  }
  v21 = ++IntegralRelation::OddMap;
LABEL_32:
  if ( *retaddr == (unsigned __int8)(((unsigned int)v21 ^ 0xACC51C6B) / 0x6D2DBA)
    || ((unsigned int)v21 ^ 0xFB9C3D32) != 0x595161 )
  {
    v21 = (unsigned int)(v21 + 1);
    IntegralRelation::OddMap = v21;
  }
  MixedProvider = (void (__fastcall *)(__int64 (__fastcall *)(const struct Direction::DetailedPaper *), unsigned __int64, __int64))GenerateMixedProvider(0x6FEF7F1F20F09010LL, 2169798858LL, v21, a4);
  MixedProvider(
    Direction::DetailedPaper::ClickComplexUnit,
    (unsigned __int64)Direction::DetailedPaper::ClickComplexUnit ^ 0x35055F,
    2426191);
  return Direction::DetailedPaper::RotateStripedSDK(this);
}

```

## disassembly

```asm
0x180047780  mov     [rsp+arg_0], rbx
0x180047785  mov     [rsp+arg_8], rbp
0x18004778a  mov     [rsp+arg_10], rsi
0x18004778f  push    rdi
0x180047790  push    r12
0x180047792  push    r13
0x180047794  push    r14
0x180047796  push    r15
0x180047798  sub     rsp, 30h
0x18004779c  movzx   r10d, word ptr [rsp+58h+var_38+0Eh]
0x1800477a2  mov     r15, rcx
0x1800477a5  movzx   ebp, word ptr [rsp+58h+var_38+6]
0x1800477aa  xor     ecx, ecx
0x1800477ac  movzx   esi, word ptr [rsp+58h+var_38+4]
0x1800477b1  mov     r11d, ecx
0x1800477b4  movzx   r14d, cx
0x1800477b8  mov     dword ptr [rsp+58h+var_38], ecx
0x1800477bc  movzx   ebx, cx
0x1800477bf  mov     eax, ecx
0x1800477c1  movzx   edi, cx
0x1800477c4  mov     r9b, 1
0x1800477c7  xorps   xmm1, xmm1
0x1800477ca  xorps   xmm2, xmm2
0x1800477cd  xorps   xmm4, xmm4
0x1800477d0  xorps   xmm3, xmm3
0x1800477d3  mov     edx, 3A04h
0x1800477d8  mov     r8d, 3476h
0x1800477de  mov     r12, 7FFFFFFFFFFFFFFFh
0x1800477e8  mov     r13, 8000000000000000h
0x1800477f2  mov     ecx, 4DC4h
0x1800477f7  movdqu  xmm0, [rsp+58h+var_38]
0x1800477fd  nop     dword ptr [rax]
0x180047800  cmp     eax, 0A652ECh
0x180047805  ja      loc_180047AB2
0x18004780b  jz      loc_18004794C
0x180047811  cmp     eax, 47481Ch
0x180047816  ja      loc_1800478C4
0x18004781c  jz      short loc_18004788A
0x18004781e  test    eax, eax
0x180047820  jz      short loc_18004786C
0x180047822  cmp     eax, 17C2B4h
0x180047827  jz      short loc_18004784E
0x180047829  cmp     eax, 2F8568h
0x18004782e  jnz     short loc_180047800
0x180047830  movsx   eax, r14w
0x180047834  mov     word ptr [rsp+58h+var_38+8], r8w
0x18004783a  movd    xmm1, eax
0x18004783e  mov     eax, 47481Ch
0x180047843  punpcklwd xmm1, xmm1
0x180047847  pshufd  xmm1, xmm1, 0
0x18004784c  jmp     short loc_1800477F7
0x18004784e  mov     eax, 3EF4h
0x180047853  mov     ebx, 0FFFFh
0x180047858  mov     word ptr [rsp+58h+var_38+0Ch], ax
0x18004785d  movzx   eax, byte ptr [r11]
0x180047861  imul    r14d, eax, 4Fh ; 'O'
0x180047865  mov     eax, 2F8568h
0x18004786a  jmp     short loc_1800477F2
0x18004786c  lea     r11, ?RotateStripedSDK@DetailedPaper@Direction@@QEBAHXZ; Direction::DetailedPaper::RotateStripedSDK(void)
0x180047873  mov     word ptr [rsp+58h+var_38+0Eh], dx
0x180047878  mov     r10d, edx
0x18004787b  mov     word ptr [rsp+58h+var_38+0Ah], cx
0x180047880  mov     eax, 17C2B4h
0x180047885  jmp     loc_1800477F7
0x18004788a  movsx   eax, bx
0x18004788d  mov     ebp, ecx
0x18004788f  mov     dword ptr [rsp+58h+var_38+4], 4DC447E7h
0x180047897  mov     esi, 47E7h
0x18004789c  mov     dword ptr [rsp+58h+var_38], 7194885h
0x1800478a4  mov     edi, 4885h
0x1800478a9  movd    xmm4, eax
0x1800478ad  mov     eax, 5F0AD0h
0x1800478b2  punpcklwd xmm4, xmm4
0x1800478b6  pshufd  xmm4, xmm4, 0
0x1800478bb  pxor    xmm4, xmm1
0x1800478bf  jmp     loc_1800477F7
0x1800478c4  cmp     eax, 5F0AD0h
0x1800478c9  jz      short loc_18004793E
0x1800478cb  cmp     eax, 76CD84h
0x1800478d0  jz      short loc_180047925
0x1800478d2  cmp     eax, 8E9038h
0x1800478d7  jnz     loc_180047800
0x1800478dd  por     xmm1, xmm2
0x1800478e1  mov     ecx, 4DC4h
0x1800478e6  pextrw  eax, xmm1, 6
0x1800478eb  movdqa  xmm0, xmm1
0x1800478ef  movd    edi, xmm1
0x1800478f3  movdqu  [rsp+58h+var_38], xmm1
0x1800478f9  pextrw  r10d, xmm1, 7
0x1800478ff  pextrw  ebp, xmm1, 3
0x180047904  pextrw  esi, xmm1, 2
0x180047909  cmp     ax, bx
0x18004790c  jnz     short loc_18004791B
0x18004790e  mov     r9b, 1
0x180047911  mov     eax, 0BE15A0h
0x180047916  jmp     loc_180047800
0x18004791b  mov     eax, 0A652ECh
0x180047920  jmp     loc_180047800
0x180047925  pand    xmm2, xmm1
0x180047929  xor     r9b, r9b
0x18004792c  movdqa  xmm1, xmm3
0x180047930  mov     eax, 8E9038h
0x180047935  pand    xmm1, xmm4
0x180047939  jmp     loc_180047800
0x18004793e  movdqa  xmm2, xmm0
0x180047942  mov     eax, 0D5D854h
0x180047947  jmp     loc_180047800
0x18004794c  cmp     si, bx
0x18004794f  jnz     short loc_1800479A9
0x180047951  movsxd  rcx, dword ptr [r11+1]
0x180047955  lea     rdx, ?RotateStripedSDK@DetailedPaper@Direction@@QEBAHXZ; Direction::DetailedPaper::RotateStripedSDK(void)
0x18004795c  add     rdx, 5
0x180047960  mov     r9b, 1
0x180047963  test    rcx, rcx
0x180047966  jle     short loc_18004797E
0x180047968  mov     rax, r12
0x18004796b  sub     rax, rcx
0x18004796e  cmp     rdx, rax
0x180047971  jle     short loc_180047996
0x180047973  mov     eax, 2
0x180047978  lea     r11, [rcx+rdx]
0x18004797c  jmp     short loc_18004799F
0x18004797e  jns     short loc_180047996
0x180047980  mov     rax, r13
0x180047983  sub     rax, rcx
0x180047986  cmp     rdx, rax
0x180047989  jge     short loc_180047996
0x18004798b  mov     eax, 2
0x180047990  lea     r11, [rcx+rdx]
0x180047994  jmp     short loc_18004799F
0x180047996  lea     r11, [rdx+rcx]
0x18004799a  mov     eax, 17C2B4h
0x18004799f  mov     ecx, 4DC4h
0x1800479a4  mov     edx, 3A04h
0x1800479a9  cmp     di, bx
0x1800479ac  jnz     loc_180047A9D
0x1800479b2  movsx   rax, byte ptr [r11+1]
0x1800479b7  lea     rdx, ?RotateStripedSDK@DetailedPaper@Direction@@QEBAHXZ; Direction::DetailedPaper::RotateStripedSDK(void)
0x1800479be  add     rdx, 2
0x1800479c2  mov     r9b, 1
0x1800479c5  mov     rcx, rax
0x1800479c8  test    al, al
0x1800479ca  jle     loc_180047A74
0x1800479d0  mov     rax, r12
0x1800479d3  sub     rax, rcx
0x1800479d6  cmp     rdx, rax
0x1800479d9  jle     loc_180047A85
0x1800479df  mov     r8d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x1800479e6  mov     eax, 9610E629h
0x1800479eb  mov     ecx, r8d
0x1800479ee  xor     ecx, 0ACC51C6Bh
0x1800479f4  mul     ecx
0x1800479f6  mov     rax, [rsp+58h]
0x1800479fb  shr     edx, 16h
0x1800479fe  cmp     [rax], dl
0x180047a00  jz      short loc_180047A11
0x180047a02  mov     eax, r8d
0x180047a05  xor     eax, 0FB9C3D32h
0x180047a0a  cmp     eax, 595161h
0x180047a0f  jz      short loc_180047A1B
0x180047a11  inc     r8d
0x180047a14  mov     cs:?OddMap@IntegralRelation@@2IA, r8d; uint IntegralRelation::OddMap
0x180047a1b  mov     edx, 815480CAh
0x180047a20  mov     rcx, 6FEF7F1F20F09010h
0x180047a2a  call    GenerateMixedProvider
0x180047a2f  lea     rdx, ?ClickComplexUnit@DetailedPaper@Direction@@SAHAEBV12@@Z; Direction::DetailedPaper::ClickComplexUnit(Direction::DetailedPaper const &)
0x180047a36  mov     r8d, 25054Fh
0x180047a3c  xor     rdx, 35055Fh
0x180047a43  lea     rcx, ?ClickComplexUnit@DetailedPaper@Direction@@SAHAEBV12@@Z; Direction::DetailedPaper::ClickComplexUnit(Direction::DetailedPaper const &)
0x180047a4a  call    cs:__guard_dispatch_icall_fptr
0x180047a50  mov     rcx, r15; this
0x180047a53  mov     rbx, [rsp+58h+arg_0]
0x180047a58  mov     rbp, [rsp+58h+arg_8]
0x180047a5d  mov     rsi, [rsp+58h+arg_10]
0x180047a62  add     rsp, 30h
0x180047a66  pop     r15
0x180047a68  pop     r14
0x180047a6a  pop     r13
0x180047a6c  pop     r12
0x180047a6e  pop     rdi
0x180047a6f  jmp     ?RotateStripedSDK@DetailedPaper@Direction@@QEBAHXZ; Direction::DetailedPaper::RotateStripedSDK(void)
0x180047a74  jns     short loc_180047A85
0x180047a76  mov     rax, r13
0x180047a79  sub     rax, rcx
0x180047a7c  cmp     rdx, rax
0x180047a7f  jl      loc_1800479DF
0x180047a85  lea     r11, [rcx+rdx]
0x180047a89  mov     eax, 17C2B4h
0x180047a8e  mov     ecx, 4DC4h
0x180047a93  mov     edx, 3A04h
0x180047a98  jmp     loc_180047800
0x180047a9d  cmp     eax, 17C2B4h
0x180047aa2  jz      loc_180047800
0x180047aa8  mov     eax, 0BE15A0h
0x180047aad  jmp     loc_180047800
0x180047ab2  cmp     eax, 1ABB0A8h
0x180047ab7  ja      loc_180047C01
0x180047abd  jz      loc_180047B4A
0x180047ac3  cmp     eax, 0BE15A0h
0x180047ac8  jz      loc_180047D26
0x180047ace  cmp     eax, 0D5D854h
0x180047ad3  jz      short loc_180047B2C
0x180047ad5  cmp     eax, 193EDF4h
0x180047ada  jnz     loc_180047800
0x180047ae0  test    r11, r11
0x180047ae3  jnz     short loc_180047AEF
0x180047ae5  mov     eax, 0BE15A0h
0x180047aea  jmp     loc_180047800
0x180047aef  movdqa  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180047af7  mov     esi, 4Fh ; 'O'
0x180047afc  mov     dword ptr [rsp+58h+var_38+4], 416C004Fh
0x180047b04  mov     ebp, 416Ch
0x180047b09  mov     word ptr [rsp+58h+var_38+8], r8w
0x180047b0f  mov     ebx, 0FFFFh
0x180047b14  movdqu  xmm0, [rsp+58h+var_38]
0x180047b1a  mov     eax, 1ABB0A8h
0x180047b1f  movdqa  xmm2, xmm0
0x180047b23  pxor    xmm3, xmm0
0x180047b27  jmp     loc_180047800
0x180047b2c  movsx   eax, bx
0x180047b2f  movd    xmm3, eax
0x180047b33  mov     eax, 76CD84h
0x180047b38  punpcklwd xmm3, xmm3
0x180047b3c  pshufd  xmm3, xmm3, 0
0x180047b41  pxor    xmm3, xmm2
0x180047b45  jmp     loc_180047800
0x180047b4a  movzx   r10d, byte ptr [r11]
0x180047b4e  movzx   r9d, byte ptr [r11+2]
0x180047b53  movzx   eax, r10b
0x180047b57  movzx   edx, byte ptr [r11+3]
0x180047b5c  shl     al, 3
0x180047b5f  movzx   eax, al
0x180047b62  imul    eax, 4Fh ; 'O'
0x180047b65  imul    ecx, edx, 4Fh ; 'O'
0x180047b68  shr     dl, 2
0x180047b6b  mov     word ptr [rsp+58h+var_38], ax
0x180047b70  movzx   edi, ax
0x180047b73  movzx   eax, byte ptr [r11+1]
0x180047b78  movzx   ebp, cx
0x180047b7b  imul    r8d, eax, 4Fh ; 'O'
0x180047b7f  movzx   eax, r9b
0x180047b83  shr     al, 5
0x180047b86  movzx   eax, al
0x180047b89  imul    eax, 4Fh ; 'O'
0x180047b8c  mov     word ptr [rsp+58h+var_38+6], cx
0x180047b91  imul    ecx, r10d, 4Fh ; 'O'
0x180047b95  mov     word ptr [rsp+58h+var_38+2], r8w
0x180047b9b  mov     word ptr [rsp+58h+var_38+0Ah], r8w
0x180047ba1  mov     word ptr [rsp+58h+var_38+4], ax
0x180047ba6  movzx   esi, ax
0x180047ba9  movzx   eax, dl
0x180047bac  imul    eax, 4Fh ; 'O'
0x180047baf  mov     word ptr [rsp+58h+var_38+8], cx
0x180047bb4  imul    ecx, r9d, 4Fh ; 'O'
0x180047bb8  xor     r9b, r9b
0x180047bbb  mov     word ptr [rsp+58h+var_38+0Eh], ax
0x180047bc0  movzx   r10d, ax
0x180047bc4  movsx   eax, bx
0x180047bc7  mov     word ptr [rsp+58h+var_38+0Ch], cx
0x180047bcc  movdqu  xmm0, [rsp+58h+var_38]
0x180047bd2  movd    xmm4, eax
0x180047bd6  mov     eax, 1C3735Ch
0x180047bdb  punpcklwd xmm4, xmm4
0x180047bdf  movdqa  xmm1, xmm0
0x180047be3  pshufd  xmm4, xmm4, 0
0x180047be8  pxor    xmm4, xmm0
0x180047bec  mov     ecx, 4DC4h
0x180047bf1  mov     edx, 3A04h
0x180047bf6  mov     r8d, 3476h
0x180047bfc  jmp     loc_180047800
0x180047c01  cmp     eax, 1C3735Ch
0x180047c06  jz      loc_180047CE9
0x180047c0c  cmp     eax, 1DB3610h
0x180047c11  jz      short loc_180047C3E
0x180047c13  cmp     eax, 1F2F8C4h
0x180047c18  jnz     loc_180047800
0x180047c1e  mov     eax, 18Bh
0x180047c23  mov     dword ptr [rsp+58h+var_38+0Ah], 3A044DC4h
0x180047c2b  movzx   r10d, ax
0x180047c2f  mov     word ptr [rsp+58h+var_38+0Eh], ax
0x180047c34  mov     eax, 193EDF4h
0x180047c39  jmp     loc_1800477F7
0x180047c3e  cmp     bp, bx
0x180047c41  jnz     short loc_180047C58
0x180047c43  cmp     di, bx
0x180047c46  jnz     short loc_180047C58
0x180047c48  cmp     si, bx
0x180047c4b  movzx   r9d, r9b
0x180047c4f  mov     eax, 1
0x180047c54  cmovz   r9d, eax
0x180047c58  cmp     r10w, bx
0x180047c5c  jnz     loc_180047AE5
0x180047c62  movzx   eax, byte ptr [r11+3]
0x180047c67  and     al, 3
0x180047c69  movzx   r8d, al
0x180047c6d  test    r8b, 2
0x180047c71  lea     eax, [r8-4]
0x180047c75  movzx   ecx, al
0x180047c78  movzx   eax, byte ptr [r11+2]
0x180047c7d  cmovz   ecx, r8d
  ... truncated ...
```

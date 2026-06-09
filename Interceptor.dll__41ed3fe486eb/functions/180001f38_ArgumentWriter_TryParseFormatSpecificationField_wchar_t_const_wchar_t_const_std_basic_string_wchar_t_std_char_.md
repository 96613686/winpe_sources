# ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180001f38`
- end: `0x180002298`
- name: `?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z`
- size: `864`
- prototype: ``
- caller_count: `28`
- callee_count: `5`
- tags: ``

## callers

- `0x180001db0`
- `0x180004994`
- `0x180004b58`
- `0x180004d84`
- `0x180004fd0`
- `0x180005858`
- `0x180005eb0`
- `0x180008d34`
- `0x180009244`
- `0x180009468`
- `0x180009c90`
- `0x180022e00`
- `0x180023028`
- `0x180023280`
- `0x1800234a8`
- `0x180023930`
- `0x180023b40`
- `0x180023d00`
- `0x180023f10`
- `0x180024108`
- `0x180024300`
- `0x1800244b0`
- `0x1800246a0`
- `0x180024884`
- `0x180024a58`
- `0x180024c2c`
- `0x180024dec`
- `0x180024fac`

## callees

- `0x180001f38`
- `0x18000410c`
- `0x1800045ec`
- `0x18000465c`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002283`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002283`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001ff7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002228`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000228a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001ff7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002228`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000228a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ArgumentWriter::TryParseFormatSpecificationField(
        unsigned __int64 *a1,
        unsigned __int16 *a2,
        void *a3,
        __int64 a4)
{
  unsigned __int64 v8; // rax
  void *v9; // rcx
  unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int16 *v15; // rax
  unsigned __int16 v16; // ax
  bool v17; // al
  unsigned __int16 *v18; // rax
  _WORD *v19; // rcx
  unsigned int v20; // ecx
  unsigned __int16 *v21; // r8
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  __m128i si128; // xmm6
  unsigned __int64 v33; // rax
  _QWORD *v34; // rcx
  unsigned __int64 v35; // rax
  void *v36; // rcx
  void *Block[2]; // [rsp+38h] [rbp-39h] BYREF
  __m128i v38; // [rsp+48h] [rbp-29h] BYREF
  __int128 v39; // [rsp+58h] [rbp-19h] BYREF
  __int128 v40; // [rsp+68h] [rbp-9h]

  v39 = 0;
  v40 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v39, &Src, 0);
  if ( (__int128 *)a4 == &v39 )
  {
    v8 = *((_QWORD *)&v40 + 1);
  }
  else
  {
    std::wstring::_Tidy_deallocate(a4);
    *(_OWORD *)a4 = v39;
    *(_OWORD *)(a4 + 16) = v40;
    v8 = 7;
    LOWORD(v39) = 0;
  }
  if ( v8 > 7 )
  {
    v9 = (void *)v39;
    if ( 2 * v8 + 2 >= 0x1000 )
    {
      v9 = *(void **)(v39 - 8);
      if ( (unsigned __int64)(v39 - (_QWORD)v9 - 8) > 0x1F )
LABEL_71:
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v9);
  }
  v10 = (unsigned __int16 *)*a1;
  v11 = *a1 - 2;
  if ( *a1 >= (unsigned __int64)a2 )
    goto LABEL_12;
  while ( 1 )
  {
    v12 = *v10;
    if ( (unsigned __int16)v12 > 0x30u )
      goto LABEL_13;
    v13 = 0x1280900000000LL;
    if ( !_bittest64(&v13, v12) )
      break;
    *a1 = (unsigned __int64)++v10;
    if ( v10 >= a2 )
      goto LABEL_12;
  }
  while ( (unsigned __int16)v12 >= 0x30u )
  {
LABEL_13:
    if ( (unsigned __int16)v12 > 0x39u )
      break;
    v15 = v10 + 1;
    v10 = v15;
    *a1 = (unsigned __int64)v15;
    if ( v15 == a2 )
      goto LABEL_12;
    LOWORD(v12) = *v15;
  }
  v16 = *v10;
  if ( *v10 == 46 )
  {
    do
    {
      *a1 = (unsigned __int64)++v10;
      if ( v10 == a2 )
        goto LABEL_12;
      v16 = *v10;
    }
    while ( *v10 >= 0x30u && v16 <= 0x39u );
  }
  if ( v16 != 73 )
  {
    if ( v16 == 104 )
    {
LABEL_25:
      ++v10;
LABEL_26:
      *a1 = (unsigned __int64)v10;
      v17 = v10 < a2;
      goto LABEL_41;
    }
    if ( v16 != 108 )
    {
      if ( v16 != 119 )
        goto LABEL_42;
      goto LABEL_25;
    }
    v18 = v10 + 1;
    *a1 = (unsigned __int64)(v10 + 1);
    if ( v10 + 1 != a2 )
    {
      if ( *v18 == 108 )
      {
        v10 += 2;
        goto LABEL_26;
      }
LABEL_29:
      v10 = v18;
      goto LABEL_42;
    }
    goto LABEL_12;
  }
  v18 = v10 + 1;
  *a1 = (unsigned __int64)(v10 + 1);
  if ( v10 + 1 == a2 )
    goto LABEL_12;
  if ( *v18 != 51 && *v18 != 54 )
    goto LABEL_29;
  v19 = v10 + 2;
  *a1 = (unsigned __int64)(v10 + 2);
  if ( v10 + 2 == a2 )
  {
LABEL_12:
    std::wstring::append(a3);
    return 0;
  }
  if ( *v18 == 51 && *v19 == 50 || *v18 == 54 && *v19 == 52 )
  {
    v10 += 3;
    goto LABEL_26;
  }
  v17 = 0;
  v10 += 2;
LABEL_41:
  if ( !v17 )
    goto LABEL_12;
LABEL_42:
  v20 = *v10;
  v21 = v10 + 1;
  *a1 = (unsigned __int64)(v10 + 1);
  if ( v20 > 0x67 )
  {
    v27 = v20 - 105;
    if ( v27 )
    {
      v28 = v27 - 6;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 3;
          if ( v30 )
          {
            v31 = v30 - 2;
            if ( v31 )
            {
              if ( v31 != 3 )
                goto LABEL_12;
            }
          }
        }
      }
    }
  }
  else if ( v20 != 103 )
  {
    v22 = v20 - 67;
    if ( v22 )
    {
      v23 = v22 - 16;
      if ( v23 )
      {
        v24 = v23 - 5;
        if ( v24 )
        {
          v25 = v24 - 11;
          if ( v25 )
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              if ( v26 != 2 )
                goto LABEL_12;
            }
          }
        }
      }
    }
  }
  *(_OWORD *)Block = 0;
  v38 = 0;
  if ( (unsigned __int16 *)v11 == v21 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v38 = si128;
    LOWORD(Block[0]) = 0;
  }
  else
  {
    _mm_lfence();
    std::wstring::_Construct<1,wchar_t const *>(Block, v11, ((__int64)v21 - v11) >> 1);
    si128 = _mm_loadu_si128(&v38);
  }
  if ( (void **)a4 == Block )
  {
    v35 = v38.m128i_u64[1];
  }
  else
  {
    v33 = *(_QWORD *)(a4 + 24);
    if ( v33 > 7 )
    {
      v34 = *(_QWORD **)a4;
      if ( 2 * v33 + 2 >= 0x1000 )
      {
        if ( (unsigned __int64)v34 - *(v34 - 1) - 8 > 0x1F )
          goto LABEL_71;
        v34 = (_QWORD *)*(v34 - 1);
      }
      free(v34);
    }
    *(_OWORD *)a4 = *(_OWORD *)Block;
    *(__m128i *)(a4 + 16) = si128;
    v35 = 7;
    LOWORD(Block[0]) = 0;
  }
  if ( v35 > 7 )
  {
    v36 = Block[0];
    if ( 2 * v35 + 2 >= 0x1000 )
    {
      v36 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v36 - 8) > 0x1F )
        goto LABEL_71;
    }
    free(v36);
  }
  return 1;
}

```

## disassembly

```asm
0x180001f38  mov     rax, rsp
0x180001f3b  push    rbp
0x180001f3c  push    rbx
0x180001f3d  push    rsi
0x180001f3e  push    rdi
0x180001f3f  push    r13
0x180001f41  push    r14
0x180001f43  push    r15
0x180001f45  lea     rbp, [rax-5Fh]
0x180001f49  sub     rsp, 90h
0x180001f50  movaps  xmmword ptr [rax-48h], xmm6
0x180001f54  mov     rax, cs:__security_cookie
0x180001f5b  xor     rax, rsp
0x180001f5e  mov     [rbp+57h+var_50], rax
0x180001f62  mov     rsi, r9
0x180001f65  mov     r14, r8
0x180001f68  mov     rdi, rdx
0x180001f6b  mov     rbx, rcx
0x180001f6e  xorps   xmm0, xmm0
0x180001f71  movups  [rbp+57h+var_70], xmm0
0x180001f75  xorps   xmm1, xmm1
0x180001f78  movdqu  [rbp+57h+var_60], xmm1
0x180001f7d  xor     r8d, r8d
0x180001f80  lea     rdx, Src
0x180001f87  lea     rcx, [rbp+57h+var_70]
0x180001f8b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001f90  lea     rax, [rbp+57h+var_70]
0x180001f94  xor     r15d, r15d
0x180001f97  cmp     rsi, rax
0x180001f9a  jz      short loc_180001FBE
0x180001f9c  mov     rcx, rsi
0x180001f9f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180001fa4  movups  xmm0, [rbp+57h+var_70]
0x180001fa8  movups  xmmword ptr [rsi], xmm0
0x180001fab  movups  xmm1, [rbp+57h+var_60]
0x180001faf  movups  xmmword ptr [rsi+10h], xmm1
0x180001fb3  lea     eax, [r15+7]
0x180001fb7  mov     word ptr [rbp+57h+var_70], r15w
0x180001fbc  jmp     short loc_180001FC2
0x180001fbe  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180001fc2  mov     r13d, 1000h
0x180001fc8  cmp     rax, 7
0x180001fcc  jbe     short loc_180001FFD
0x180001fce  mov     rcx, qword ptr [rbp+57h+var_70]
0x180001fd2  mov     rdx, rcx
0x180001fd5  lea     rax, ds:2[rax*2]
0x180001fdd  cmp     rax, r13
0x180001fe0  jb      short loc_180001FF7
0x180001fe2  mov     rcx, [rcx-8]; Block
0x180001fe6  sub     rdx, rcx
0x180001fe9  lea     rax, [rdx-8]
0x180001fed  cmp     rax, 1Fh
0x180001ff1  ja      loc_180002274
0x180001ff7  call    cs:__imp_free
0x180001ffd  mov     rdx, [rbx]
0x180002000  lea     r9, [rdx-2]
0x180002004  mov     r11d, 32h ; '2'
0x18000200a  cmp     rdx, rdi
0x18000200d  jnb     short loc_180002039
0x18000200f  mov     r10w, 30h ; '0'
0x180002014  movzx   ecx, word ptr [rdx]
0x180002017  cmp     cx, r10w
0x18000201b  ja      short loc_180002073
0x18000201d  mov     r8, 1280900000000h
0x180002027  bt      r8, rcx
0x18000202b  jnb     short loc_18000208B
0x18000202d  add     rdx, 2
0x180002031  mov     [rbx], rdx
0x180002034  cmp     rdx, rdi
0x180002037  jb      short loc_180002014
0x180002039  mov     r8, r11
0x18000203c  lea     rdx, aFormatErrorInv; "!format error: invalid format specifica"...
0x180002043  mov     rcx, r14; Src
0x180002046  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18000204b  xor     al, al
0x18000204d  mov     rcx, [rbp+57h+var_50]
0x180002051  xor     rcx, rsp; StackCookie
0x180002054  call    __security_check_cookie
0x180002059  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180002061  add     rsp, 90h
0x180002068  pop     r15
0x18000206a  pop     r14
0x18000206c  pop     r13
0x18000206e  pop     rdi
0x18000206f  pop     rsi
0x180002070  pop     rbx
0x180002071  pop     rbp
0x180002072  retn
0x180002073  cmp     cx, 39h ; '9'
0x180002077  ja      short loc_180002091
0x180002079  lea     rax, [rdx+2]
0x18000207d  mov     rdx, rax
0x180002080  mov     [rbx], rax
0x180002083  cmp     rax, rdi
0x180002086  jz      short loc_180002039
0x180002088  movzx   ecx, word ptr [rax]
0x18000208b  cmp     cx, r10w
0x18000208f  jnb     short loc_180002073
0x180002091  movzx   eax, word ptr [rdx]
0x180002094  cmp     ax, 2Eh ; '.'
0x180002098  jnz     short loc_1800020B5
0x18000209a  add     rdx, 2
0x18000209e  mov     [rbx], rdx
0x1800020a1  cmp     rdx, rdi
0x1800020a4  jz      short loc_180002039
0x1800020a6  movzx   eax, word ptr [rdx]
0x1800020a9  cmp     ax, r10w
0x1800020ad  jb      short loc_1800020B5
0x1800020af  cmp     ax, 39h ; '9'
0x1800020b3  jbe     short loc_18000209A
0x1800020b5  cmp     ax, 49h ; 'I'
0x1800020b9  jz      short loc_180002101
0x1800020bb  cmp     ax, 68h ; 'h'
0x1800020bf  jz      short loc_1800020D1
0x1800020c1  cmp     ax, 6Ch ; 'l'
0x1800020c5  jz      short loc_1800020E0
0x1800020c7  cmp     ax, 77h ; 'w'
0x1800020cb  jnz     loc_180002159
0x1800020d1  add     rdx, 2
0x1800020d5  mov     [rbx], rdx
0x1800020d8  cmp     rdx, rdi
0x1800020db  setb    al
0x1800020de  jmp     short loc_180002151
0x1800020e0  lea     rax, [rdx+2]
0x1800020e4  mov     [rbx], rax
0x1800020e7  cmp     rax, rdi
0x1800020ea  jz      loc_180002039
0x1800020f0  cmp     word ptr [rax], 6Ch ; 'l'
0x1800020f4  jz      short loc_1800020FB
0x1800020f6  mov     rdx, rax
0x1800020f9  jmp     short loc_180002159
0x1800020fb  add     rdx, 4
0x1800020ff  jmp     short loc_1800020D5
0x180002101  lea     rax, [rdx+2]
0x180002105  mov     [rbx], rax
0x180002108  cmp     rax, rdi
0x18000210b  jz      loc_180002039
0x180002111  cmp     word ptr [rax], 33h ; '3'
0x180002115  jz      short loc_18000211D
0x180002117  cmp     word ptr [rax], 36h ; '6'
0x18000211b  jnz     short loc_1800020F6
0x18000211d  lea     rcx, [rdx+4]
0x180002121  mov     [rbx], rcx
0x180002124  cmp     rcx, rdi
0x180002127  jz      loc_180002039
0x18000212d  cmp     word ptr [rax], 33h ; '3'
0x180002131  jnz     short loc_180002139
0x180002133  cmp     [rcx], r11w
0x180002137  jz      short loc_180002145
0x180002139  cmp     word ptr [rax], 36h ; '6'
0x18000213d  jnz     short loc_18000214B
0x18000213f  cmp     word ptr [rcx], 34h ; '4'
0x180002143  jnz     short loc_18000214B
0x180002145  add     rdx, 6
0x180002149  jmp     short loc_1800020D5
0x18000214b  mov     al, r15b
0x18000214e  mov     rdx, rcx
0x180002151  test    al, al
0x180002153  jz      loc_180002039
0x180002159  movzx   ecx, word ptr [rdx]
0x18000215c  lea     r8, [rdx+2]
0x180002160  mov     [rbx], r8
0x180002163  cmp     ecx, 67h ; 'g'
0x180002166  ja      short loc_18000218D
0x180002168  jz      short loc_1800021AF
0x18000216a  sub     ecx, 43h ; 'C'
0x18000216d  jz      short loc_1800021AF
0x18000216f  sub     ecx, 10h
0x180002172  jz      short loc_1800021AF
0x180002174  sub     ecx, 5
0x180002177  jz      short loc_1800021AF
0x180002179  sub     ecx, 0Bh
0x18000217c  jz      short loc_1800021AF
0x18000217e  sub     ecx, 1
0x180002181  jz      short loc_1800021AF
0x180002183  cmp     ecx, 2
0x180002186  jz      short loc_1800021AF
0x180002188  jmp     loc_180002039
0x18000218d  sub     ecx, 69h ; 'i'
0x180002190  jz      short loc_1800021AF
0x180002192  sub     ecx, 6
0x180002195  jz      short loc_1800021AF
0x180002197  sub     ecx, 1
0x18000219a  jz      short loc_1800021AF
0x18000219c  sub     ecx, 3
0x18000219f  jz      short loc_1800021AF
0x1800021a1  sub     ecx, 2
0x1800021a4  jz      short loc_1800021AF
0x1800021a6  cmp     ecx, 3
0x1800021a9  jnz     loc_180002039
0x1800021af  xorps   xmm0, xmm0
0x1800021b2  movups  xmmword ptr [rbp+57h+Block], xmm0
0x1800021b6  xorps   xmm1, xmm1
0x1800021b9  movdqu  [rbp+57h+var_80], xmm1
0x1800021be  cmp     r9, r8
0x1800021c1  jnz     short loc_1800021D7
0x1800021c3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800021cb  movdqu  [rbp+57h+var_80], xmm6
0x1800021d0  mov     word ptr [rbp+57h+Block], r15w
0x1800021d5  jmp     short loc_1800021F1
0x1800021d7  lfence
0x1800021da  sub     r8, r9
0x1800021dd  sar     r8, 1
0x1800021e0  mov     rdx, r9
0x1800021e3  lea     rcx, [rbp+57h+Block]
0x1800021e7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800021ec  movdqu  xmm6, [rbp+57h+var_80]
0x1800021f1  lea     rax, [rbp+57h+Block]
0x1800021f5  cmp     rsi, rax
0x1800021f8  jz      short loc_180002245
0x1800021fa  mov     rax, [rsi+18h]
0x1800021fe  cmp     rax, 7
0x180002202  jbe     short loc_18000222E
0x180002204  mov     rcx, [rsi]
0x180002207  lea     rax, ds:2[rax*2]
0x18000220f  cmp     rax, r13
0x180002212  jb      short loc_180002228
0x180002214  mov     rdx, [rcx-8]
0x180002218  sub     rcx, rdx
0x18000221b  lea     rax, [rcx-8]
0x18000221f  cmp     rax, 1Fh
0x180002223  ja      short loc_180002274
0x180002225  mov     rcx, rdx; Block
0x180002228  call    cs:__imp_free
0x18000222e  movups  xmm0, xmmword ptr [rbp+57h+Block]
0x180002232  movups  xmmword ptr [rsi], xmm0
0x180002235  movups  xmmword ptr [rsi+10h], xmm6
0x180002239  mov     eax, 7
0x18000223e  mov     word ptr [rbp+57h+Block], r15w
0x180002243  jmp     short loc_180002249
0x180002245  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180002249  cmp     rax, 7
0x18000224d  jbe     short loc_180002290
0x18000224f  mov     rcx, [rbp+57h+Block]; Block
0x180002253  mov     rdx, rcx
0x180002256  lea     rax, ds:2[rax*2]
0x18000225e  cmp     rax, r13
0x180002261  jb      short loc_18000228A
0x180002263  mov     rcx, [rcx-8]
0x180002267  sub     rdx, rcx
0x18000226a  lea     rax, [rdx-8]
0x18000226e  cmp     rax, 1Fh
0x180002272  jbe     short loc_18000228A
0x180002274  mov     [rsp+20h], r15; Reserved
0x180002279  xor     r9d, r9d; LineNo
0x18000227c  xor     r8d, r8d; FileName
0x18000227f  xor     edx, edx; FunctionName
0x180002281  xor     ecx, ecx; Expression
0x180002283  call    cs:__imp__invoke_watson
0x18000228a  call    cs:__imp_free
0x180002290  mov     al, 1
0x180002292  jmp     loc_18000204D
```

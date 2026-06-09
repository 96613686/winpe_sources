# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180033000`
- end: `0x1800333ee`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1006`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x18002ef5c`
- `0x18002f158`
- `0x180033000`

## callees

- `0x180004410`
- `0x18002f0b4`
- `0x1800329d4`
- `0x180033000`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x180036c6c`
- `0x18003a404`
- `0x18003b984`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180033251`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180033251`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        __int128 *a4,
        __int64 a5)
{
  _BYTE *v5; // rsi
  char v8; // al
  __int128 v9; // xmm0
  int v10; // ecx
  int v11; // edi
  int v12; // eax
  _BYTE *v13; // r12
  unsigned int v14; // eax
  char v15; // r14
  _BYTE *v16; // rcx
  char v17; // cl
  const char *v18; // rcx
  __int64 v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64); // rax
  char *v21; // rax
  int v22; // edx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r9
  char *v25; // r11
  int v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v29; // [rsp+38h] [rbp-C8h] BYREF
  char v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v35; // [rsp+78h] [rbp-88h] BYREF
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v38; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v39; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v40; // [rsp+F8h] [rbp-8h]
  __int128 v41; // [rsp+100h] [rbp+0h] BYREF
  int v42; // [rsp+110h] [rbp+10h]
  _BYTE v43[65]; // [rsp+120h] [rbp+20h] BYREF
  char v44[15]; // [rsp+161h] [rbp+61h] BYREF

  v5 = a4;
  v28 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0x7Fu )
      std::_Throw_format_error("integral cannot be stored in char");
    *((_BYTE *)a4 + 11) = 0;
    v9 = *a4;
    v41 = *a4;
    v42 = *((_DWORD *)a4 + 4);
    v29 = a3;
    v10 = *((_DWORD *)a4 + 2);
    if ( !(_BYTE)v10 || (_BYTE)v10 == 99 )
    {
      *(_QWORD *)&v32 = &v29;
      *((_QWORD *)&v32 + 1) = 1;
      std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, &v32, &v41, a5);
    }
    else
    {
      v32 = v9;
      v33 = *((_DWORD *)a4 + 4);
      std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>(
        a1,
        a2,
        a3,
        (unsigned int)&v32,
        a5);
    }
    return a1;
  }
  v11 = 2;
  if ( !*((_BYTE *)a4 + 10) )
    *((_BYTE *)a4 + 10) = 2;
  if ( v8 != 66 )
  {
    if ( v8 == 88 )
    {
LABEL_16:
      v12 = 16;
      goto LABEL_18;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v12 = 8;
        goto LABEL_18;
      }
      if ( v8 != 120 )
      {
        v12 = 10;
        goto LABEL_18;
      }
      goto LABEL_16;
    }
  }
  v12 = 2;
LABEL_18:
  v27 = v12;
  LOBYTE(a4) = a3;
  v13 = *(_BYTE **)std::to_chars(&v32, v43, v44, a4);
  v35 = v43;
  v14 = (_DWORD)v13 - (unsigned int)v43;
  v31 = v14;
  if ( v5[10] != 2 )
    v31 = ++v14;
  v15 = 1;
  if ( v5[8] == 88 )
  {
    v16 = v43;
    if ( v43 != v13 )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v13 );
      v14 = v31;
    }
  }
  v36 = 0u;
  if ( !v5[11] )
    goto LABEL_42;
  v17 = v5[8];
  switch ( v17 )
  {
    case 'B':
      v18 = "0B";
      goto LABEL_39;
    case 'X':
      v18 = "0X";
      goto LABEL_39;
    case 'b':
      v18 = "0b";
      goto LABEL_39;
    case 'o':
      if ( v28 )
      {
        v18 = "0";
        *((_QWORD *)&v32 + 1) = 1;
        v11 = 1;
LABEL_40:
        *(_QWORD *)&v32 = v18;
        goto LABEL_41;
      }
      break;
    case 'x':
      v18 = "0x";
LABEL_39:
      *((_QWORD *)&v32 + 1) = 2;
      goto LABEL_40;
  }
  v32 = 0u;
  v11 = 0;
LABEL_41:
  v36 = v32;
  v14 += v11;
  v31 = v14;
LABEL_42:
  v34 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 15;
  LOBYTE(v38) = 0;
  if ( v5[12] )
  {
    if ( a5 )
    {
      *((_QWORD *)&v32 + 1) = *(_QWORD *)(a5 + 8);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v32 + 1) + 8LL))(*((_QWORD *)&v32 + 1));
    }
    else
    {
      *((_QWORD *)&v32 + 1) = std::locale::_Init(1);
    }
    v19 = std::use_facet<std::numpunct<char>>(&v32);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 40LL))(v19, &v41);
    std::string::operator=(&v38, &v41);
    std::string::~string(&v41);
    if ( *((_QWORD *)&v32 + 1) )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v32 + 1) + 16LL))(*((_QWORD *)&v32 + 1));
      if ( v20 )
        (**v20)(v20, 1);
    }
    v21 = (char *)&v38;
    if ( v40 > 0xF )
      v21 = (char *)v38;
    v22 = 0;
    if ( v39 )
    {
      v23 = v13 - v35;
      v24 = *v21;
      if ( v13 - v35 > v24 )
      {
        v25 = &v21[v39];
        do
        {
          v23 -= (char)v24;
          ++v22;
          if ( v21 + 1 != v25 )
            ++v21;
          v24 = *v21;
        }
        while ( v23 > v24 );
      }
    }
    v34 = v22;
    v14 = v22 + v31;
    v31 += v22;
  }
  if ( !v5[13] || v5[9] )
    v15 = 0;
  v30 = v15;
  v37[0] = v13;
  v37[1] = v5;
  v37[2] = &v28;
  v37[3] = &v36;
  v37[4] = &v30;
  v37[5] = &v31;
  v37[6] = &v34;
  v37[7] = &v35;
  v37[8] = &v38;
  v37[9] = &a5;
  if ( v15 )
    `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>'::`2'::_lambda_1_::operator()(
      v37,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_D_std___std__U___Basic_format_specs_D_2_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__E_2_YA_AV12_V12_EU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_D_std___0_V10_HAEBU___Basic_format_specs_D_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__E_0_YA_AV10_0EU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v14,
      (_DWORD)v5,
      v27,
      (__int64)v37);
  std::string::~string(&v38);
  return a1;
}

```

## disassembly

```asm
0x180033000  mov     [rsp-8+arg_8], rbx
0x180033005  push    rbp
0x180033006  push    rsi
0x180033007  push    rdi
0x180033008  push    r12
0x18003300a  push    r13
0x18003300c  push    r14
0x18003300e  push    r15
0x180033010  lea     rbp, [rsp-80h]
0x180033015  sub     rsp, 180h
0x18003301c  mov     rax, cs:__security_cookie
0x180033023  xor     rax, rsp
0x180033026  mov     [rbp+0B0h+var_40], rax
0x18003302a  mov     rsi, r9
0x18003302d  mov     rbx, rdx
0x180033030  mov     r15, rcx
0x180033033  mov     [rsp+1B0h+var_180], r8b
0x180033038  xor     r13d, r13d
0x18003303b  mov     al, [r9+8]
0x18003303f  cmp     al, 63h ; 'c'
0x180033041  jnz     loc_1800330D1
0x180033047  cmp     r8b, 7Fh
0x18003304b  ja      loc_1800333E1
0x180033051  mov     [r9+0Bh], r13b
0x180033055  movups  xmm0, xmmword ptr [r9]
0x180033059  movaps  [rbp+0B0h+var_B0], xmm0
0x18003305d  mov     eax, [r9+10h]
0x180033061  mov     [rbp+0B0h+var_A0], eax
0x180033064  mov     rax, [rbp+0B0h+arg_20]
0x18003306b  mov     [rsp+1B0h+var_178], r8b
0x180033070  mov     ecx, [r9+8]
0x180033074  test    cl, cl
0x180033076  jz      short loc_1800330A1
0x180033078  cmp     cl, 63h ; 'c'
0x18003307b  jz      short loc_1800330A1
0x18003307d  movaps  [rsp+1B0h+var_160], xmm0
0x180033082  mov     ecx, [r9+10h]
0x180033086  mov     [rsp+1B0h+var_150], ecx
0x18003308a  mov     [rsp+1B0h+var_190], rax
0x18003308f  lea     r9, [rsp+1B0h+var_160]
0x180033094  mov     rcx, r15
0x180033097  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x18003309c  jmp     loc_1800333B7
0x1800330a1  lea     rcx, [rsp+1B0h+var_178]
0x1800330a6  mov     qword ptr [rsp+1B0h+var_160], rcx
0x1800330ab  mov     r14d, 1
0x1800330b1  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x1800330b6  mov     [rsp+1B0h+var_190], rax
0x1800330bb  lea     r9, [rbp+0B0h+var_B0]
0x1800330bf  lea     r8, [rsp+1B0h+var_160]
0x1800330c4  mov     rcx, r15
0x1800330c7  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x1800330cc  jmp     loc_1800333B7
0x1800330d1  mov     edi, 2
0x1800330d6  cmp     [r9+0Ah], r13b
0x1800330da  jnz     short loc_1800330E0
0x1800330dc  mov     [r9+0Ah], dil
0x1800330e0  cmp     al, 42h ; 'B'
0x1800330e2  jz      short loc_180033109
0x1800330e4  cmp     al, 58h ; 'X'
0x1800330e6  jz      short loc_180033102
0x1800330e8  cmp     al, 62h ; 'b'
0x1800330ea  jz      short loc_180033109
0x1800330ec  cmp     al, 6Fh ; 'o'
0x1800330ee  jz      short loc_1800330FB
0x1800330f0  cmp     al, 78h ; 'x'
0x1800330f2  jz      short loc_180033102
0x1800330f4  mov     eax, 0Ah
0x1800330f9  jmp     short loc_18003310B
0x1800330fb  mov     eax, 8
0x180033100  jmp     short loc_18003310B
0x180033102  mov     eax, 10h
0x180033107  jmp     short loc_18003310B
0x180033109  mov     eax, edi
0x18003310b  mov     dword ptr [rsp+1B0h+var_190], eax
0x18003310f  mov     r9b, r8b
0x180033112  lea     r8, [rbp+0B0h+var_4F]
0x180033116  lea     rdx, [rbp+0B0h+var_90]
0x18003311a  lea     rcx, [rsp+1B0h+var_160]
0x18003311f  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x180033124  mov     r12, [rax]
0x180033127  lea     rcx, [rbp+0B0h+var_90]
0x18003312b  mov     [rsp+1B0h+var_138], rcx
0x180033130  mov     eax, r12d
0x180033133  sub     eax, ecx
0x180033135  mov     [rsp+1B0h+var_16C], eax
0x180033139  cmp     [rsi+0Ah], dil
0x18003313d  jz      short loc_180033145
0x18003313f  inc     eax
0x180033141  mov     [rsp+1B0h+var_16C], eax
0x180033145  mov     r14d, 1
0x18003314b  cmp     byte ptr [rsi+8], 58h ; 'X'
0x18003314f  jnz     short loc_180033178
0x180033151  lea     rcx, [rbp+0B0h+var_90]
0x180033155  lea     rdx, [rbp+0B0h+var_90]
0x180033159  cmp     rdx, r12
0x18003315c  jz      short loc_180033178
0x18003315e  mov     dl, [rcx]
0x180033160  lea     eax, [rdx-61h]
0x180033163  cmp     al, 19h
0x180033165  ja      short loc_18003316C
0x180033167  sub     dl, 20h ; ' '
0x18003316a  mov     [rcx], dl
0x18003316c  add     rcx, r14
0x18003316f  cmp     rcx, r12
0x180033172  jnz     short loc_18003315E
0x180033174  mov     eax, [rsp+1B0h+var_16C]
0x180033178  mov     qword ptr [rbp+0B0h+var_130], r13
0x18003317c  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180033180  cmp     [rsi+0Bh], r13b
0x180033184  jz      short loc_180033205
0x180033186  mov     cl, [rsi+8]
0x180033189  cmp     cl, 42h ; 'B'
0x18003318c  jz      short loc_1800331E4
0x18003318e  cmp     cl, 58h ; 'X'
0x180033191  jz      short loc_1800331DB
0x180033193  cmp     cl, 62h ; 'b'
0x180033196  jz      short loc_1800331D2
0x180033198  cmp     cl, 6Fh ; 'o'
0x18003319b  jz      short loc_1800331AB
0x18003319d  cmp     cl, 78h ; 'x'
0x1800331a0  jnz     short loc_1800331C3
0x1800331a2  lea     rcx, a0x; "0x"
0x1800331a9  jmp     short loc_1800331EB
0x1800331ab  cmp     [rsp+1B0h+var_180], r13b
0x1800331b0  jz      short loc_1800331C3
0x1800331b2  lea     rcx, a0; "0"
0x1800331b9  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x1800331be  mov     edi, r14d
0x1800331c1  jmp     short loc_1800331F0
0x1800331c3  mov     qword ptr [rsp+1B0h+var_160], r13
0x1800331c8  mov     qword ptr [rsp+1B0h+var_160+8], r13
0x1800331cd  mov     edi, r13d
0x1800331d0  jmp     short loc_1800331F5
0x1800331d2  lea     rcx, a0b; "0b"
0x1800331d9  jmp     short loc_1800331EB
0x1800331db  lea     rcx, a0x_0; "0X"
0x1800331e2  jmp     short loc_1800331EB
0x1800331e4  lea     rcx, a0b_0; "0B"
0x1800331eb  mov     qword ptr [rsp+1B0h+var_160+8], rdi
0x1800331f0  mov     qword ptr [rsp+1B0h+var_160], rcx
0x1800331f5  movaps  xmm0, [rsp+1B0h+var_160]
0x1800331fa  movdqa  [rbp+0B0h+var_130], xmm0
0x1800331ff  add     eax, edi
0x180033201  mov     [rsp+1B0h+var_16C], eax
0x180033205  mov     [rsp+1B0h+var_140], r13d
0x18003320a  xorps   xmm0, xmm0
0x18003320d  movups  [rbp+0B0h+var_D0], xmm0
0x180033211  mov     [rbp+0B0h+var_C0], r13
0x180033215  mov     [rbp+0B0h+var_B8], 0Fh
0x18003321d  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180033221  cmp     [rsi+0Ch], r13b
0x180033225  jz      loc_18003331D
0x18003322b  mov     rax, [rbp+0B0h+arg_20]
0x180033232  test    rax, rax
0x180033235  jz      short loc_18003324E
0x180033237  mov     rcx, [rax+8]
0x18003323b  mov     qword ptr [rsp+1B0h+var_160+8], rcx
0x180033240  mov     rax, [rcx]
0x180033243  mov     rax, [rax+8]
0x180033247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003324c  jmp     short loc_18003325C
0x18003324e  mov     cl, r14b
0x180033251  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180033257  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x18003325c  lea     rcx, [rsp+1B0h+var_160]
0x180033261  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180033266  mov     r8, rax
0x180033269  mov     rcx, [rax]
0x18003326c  mov     rax, [rcx+28h]
0x180033270  lea     rdx, [rbp+0B0h+var_B0]
0x180033274  mov     rcx, r8
0x180033277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003327c  lea     rdx, [rbp+0B0h+var_B0]
0x180033280  lea     rcx, [rbp+0B0h+var_D0]
0x180033284  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180033289  lea     rcx, [rbp+0B0h+var_B0]
0x18003328d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033292  nop
0x180033293  mov     rcx, qword ptr [rsp+1B0h+var_160+8]
0x180033298  test    rcx, rcx
0x18003329b  jz      short loc_1800332C2
0x18003329d  mov     rax, [rcx]
0x1800332a0  mov     rax, [rax+10h]
0x1800332a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332a9  mov     r8, rax
0x1800332ac  test    rax, rax
0x1800332af  jz      short loc_1800332C2
0x1800332b1  mov     rcx, [rax]
0x1800332b4  mov     rax, [rcx]
0x1800332b7  mov     edx, r14d
0x1800332ba  mov     rcx, r8
0x1800332bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332c2  lea     rax, [rbp+0B0h+var_D0]
0x1800332c6  cmp     [rbp+0B0h+var_B8], 0Fh
0x1800332cb  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x1800332d0  mov     r10, [rbp+0B0h+var_C0]
0x1800332d4  mov     edx, r13d
0x1800332d7  test    r10, r10
0x1800332da  jz      short loc_18003330F
0x1800332dc  mov     r8, r12
0x1800332df  sub     r8, [rsp+1B0h+var_138]
0x1800332e4  movsx   r9, byte ptr [rax]
0x1800332e8  cmp     r8, r9
0x1800332eb  jbe     short loc_18003330F
0x1800332ed  lea     r11, [r10+rax]
0x1800332f1  movsx   rcx, r9b
0x1800332f5  sub     r8, rcx
0x1800332f8  add     edx, r14d
0x1800332fb  lea     rcx, [rax+1]
0x1800332ff  cmp     rcx, r11
0x180033302  cmovnz  rax, rcx
0x180033306  movsx   r9, byte ptr [rax]
0x18003330a  cmp     r8, r9
0x18003330d  ja      short loc_1800332F1
0x18003330f  mov     [rsp+1B0h+var_140], edx
0x180033313  mov     eax, [rsp+1B0h+var_16C]
0x180033317  add     eax, edx
0x180033319  mov     [rsp+1B0h+var_16C], eax
0x18003331d  cmp     [rsi+0Dh], r13b
0x180033321  jz      short loc_180033329
0x180033323  cmp     [rsi+9], r13b
0x180033327  jz      short loc_18003332C
0x180033329  mov     r14b, r13b
0x18003332c  mov     [rsp+1B0h+var_170], r14b
0x180033331  mov     [rbp+0B0h+var_120], r12
0x180033335  mov     [rbp+0B0h+var_118], rsi
0x180033339  lea     rcx, [rsp+1B0h+var_180]
0x18003333e  mov     [rbp+0B0h+var_110], rcx
0x180033342  lea     rcx, [rbp+0B0h+var_130]
0x180033346  mov     [rbp+0B0h+var_108], rcx
0x18003334a  lea     rcx, [rsp+1B0h+var_170]
0x18003334f  mov     [rbp+0B0h+var_100], rcx
0x180033353  lea     rcx, [rsp+1B0h+var_16C]
0x180033358  mov     [rbp+0B0h+var_F8], rcx
0x18003335c  lea     rcx, [rsp+1B0h+var_140]
0x180033361  mov     [rbp+0B0h+var_F0], rcx
0x180033365  lea     rcx, [rsp+1B0h+var_138]
0x18003336a  mov     [rbp+0B0h+var_E8], rcx
0x18003336e  lea     rcx, [rbp+0B0h+var_D0]
0x180033372  mov     [rbp+0B0h+var_E0], rcx
0x180033376  lea     rcx, [rbp+0B0h+arg_20]
0x18003337d  mov     [rbp+0B0h+var_D8], rcx
0x180033381  lea     rcx, [rbp+0B0h+var_120]
0x180033385  test    r14b, r14b
0x180033388  jz      short loc_180033397
0x18003338a  mov     r8, rbx
0x18003338d  mov     rdx, r15
0x180033390  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180033395  jmp     short loc_1800333AE
0x180033397  mov     [rsp+1B0h+var_188], rcx
0x18003339c  mov     r9, rsi
0x18003339f  mov     r8d, eax
0x1800333a2  mov     rdx, rbx
0x1800333a5  mov     rcx, r15
0x1800333a8  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@2@YA?AV12@V12@EU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@0@YA?AV10@0EU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800333ad  nop
0x1800333ae  lea     rcx, [rbp+0B0h+var_D0]
0x1800333b2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800333b7  mov     rax, r15
0x1800333ba  mov     rcx, [rbp+0B0h+var_40]
0x1800333be  xor     rcx, rsp; StackCookie
0x1800333c1  call    __security_check_cookie
0x1800333c6  mov     rbx, [rsp+1B0h+arg_8]
0x1800333ce  add     rsp, 180h
0x1800333d5  pop     r15
0x1800333d7  pop     r14
0x1800333d9  pop     r13
0x1800333db  pop     r12
0x1800333dd  pop     rdi
0x1800333de  pop     rsi
0x1800333df  pop     rbp
0x1800333e0  retn
0x1800333e1  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x1800333e8  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180052334`
- end: `0x180052722`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1006`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x18004e8bc`
- `0x18004eab8`
- `0x180052334`

## callees

- `0x180005020`
- `0x1800342a8`
- `0x180034450`
- `0x180040fac`
- `0x180042c80`
- `0x18004ea14`
- `0x180051d08`
- `0x180052334`
- `0x180053d44`
- `0x180054914`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180052585`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180052585`

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
0x180052334  mov     [rsp-8+arg_8], rbx
0x180052339  push    rbp
0x18005233a  push    rsi
0x18005233b  push    rdi
0x18005233c  push    r12
0x18005233e  push    r13
0x180052340  push    r14
0x180052342  push    r15
0x180052344  lea     rbp, [rsp-80h]
0x180052349  sub     rsp, 180h
0x180052350  mov     rax, cs:__security_cookie
0x180052357  xor     rax, rsp
0x18005235a  mov     [rbp+0B0h+var_40], rax
0x18005235e  mov     rsi, r9
0x180052361  mov     rbx, rdx
0x180052364  mov     r15, rcx
0x180052367  mov     [rsp+1B0h+var_180], r8b
0x18005236c  xor     r13d, r13d
0x18005236f  mov     al, [r9+8]
0x180052373  cmp     al, 63h ; 'c'
0x180052375  jnz     loc_180052405
0x18005237b  cmp     r8b, 7Fh
0x18005237f  ja      loc_180052715
0x180052385  mov     [r9+0Bh], r13b
0x180052389  movups  xmm0, xmmword ptr [r9]
0x18005238d  movaps  [rbp+0B0h+var_B0], xmm0
0x180052391  mov     eax, [r9+10h]
0x180052395  mov     [rbp+0B0h+var_A0], eax
0x180052398  mov     rax, [rbp+0B0h+arg_20]
0x18005239f  mov     [rsp+1B0h+var_178], r8b
0x1800523a4  mov     ecx, [r9+8]
0x1800523a8  test    cl, cl
0x1800523aa  jz      short loc_1800523D5
0x1800523ac  cmp     cl, 63h ; 'c'
0x1800523af  jz      short loc_1800523D5
0x1800523b1  movaps  [rsp+1B0h+var_160], xmm0
0x1800523b6  mov     ecx, [r9+10h]
0x1800523ba  mov     [rsp+1B0h+var_150], ecx
0x1800523be  mov     [rsp+1B0h+var_190], rax
0x1800523c3  lea     r9, [rsp+1B0h+var_160]
0x1800523c8  mov     rcx, r15
0x1800523cb  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x1800523d0  jmp     loc_1800526EB
0x1800523d5  lea     rcx, [rsp+1B0h+var_178]
0x1800523da  mov     qword ptr [rsp+1B0h+var_160], rcx
0x1800523df  mov     r14d, 1
0x1800523e5  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x1800523ea  mov     [rsp+1B0h+var_190], rax
0x1800523ef  lea     r9, [rbp+0B0h+var_B0]
0x1800523f3  lea     r8, [rsp+1B0h+var_160]
0x1800523f8  mov     rcx, r15
0x1800523fb  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x180052400  jmp     loc_1800526EB
0x180052405  mov     edi, 2
0x18005240a  cmp     [r9+0Ah], r13b
0x18005240e  jnz     short loc_180052414
0x180052410  mov     [r9+0Ah], dil
0x180052414  cmp     al, 42h ; 'B'
0x180052416  jz      short loc_18005243D
0x180052418  cmp     al, 58h ; 'X'
0x18005241a  jz      short loc_180052436
0x18005241c  cmp     al, 62h ; 'b'
0x18005241e  jz      short loc_18005243D
0x180052420  cmp     al, 6Fh ; 'o'
0x180052422  jz      short loc_18005242F
0x180052424  cmp     al, 78h ; 'x'
0x180052426  jz      short loc_180052436
0x180052428  mov     eax, 0Ah
0x18005242d  jmp     short loc_18005243F
0x18005242f  mov     eax, 8
0x180052434  jmp     short loc_18005243F
0x180052436  mov     eax, 10h
0x18005243b  jmp     short loc_18005243F
0x18005243d  mov     eax, edi
0x18005243f  mov     dword ptr [rsp+1B0h+var_190], eax
0x180052443  mov     r9b, r8b
0x180052446  lea     r8, [rbp+0B0h+var_4F]
0x18005244a  lea     rdx, [rbp+0B0h+var_90]
0x18005244e  lea     rcx, [rsp+1B0h+var_160]
0x180052453  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x180052458  mov     r12, [rax]
0x18005245b  lea     rcx, [rbp+0B0h+var_90]
0x18005245f  mov     [rsp+1B0h+var_138], rcx
0x180052464  mov     eax, r12d
0x180052467  sub     eax, ecx
0x180052469  mov     [rsp+1B0h+var_16C], eax
0x18005246d  cmp     [rsi+0Ah], dil
0x180052471  jz      short loc_180052479
0x180052473  inc     eax
0x180052475  mov     [rsp+1B0h+var_16C], eax
0x180052479  mov     r14d, 1
0x18005247f  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180052483  jnz     short loc_1800524AC
0x180052485  lea     rcx, [rbp+0B0h+var_90]
0x180052489  lea     rdx, [rbp+0B0h+var_90]
0x18005248d  cmp     rdx, r12
0x180052490  jz      short loc_1800524AC
0x180052492  mov     dl, [rcx]
0x180052494  lea     eax, [rdx-61h]
0x180052497  cmp     al, 19h
0x180052499  ja      short loc_1800524A0
0x18005249b  sub     dl, 20h ; ' '
0x18005249e  mov     [rcx], dl
0x1800524a0  add     rcx, r14
0x1800524a3  cmp     rcx, r12
0x1800524a6  jnz     short loc_180052492
0x1800524a8  mov     eax, [rsp+1B0h+var_16C]
0x1800524ac  mov     qword ptr [rbp+0B0h+var_130], r13
0x1800524b0  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x1800524b4  cmp     [rsi+0Bh], r13b
0x1800524b8  jz      short loc_180052539
0x1800524ba  mov     cl, [rsi+8]
0x1800524bd  cmp     cl, 42h ; 'B'
0x1800524c0  jz      short loc_180052518
0x1800524c2  cmp     cl, 58h ; 'X'
0x1800524c5  jz      short loc_18005250F
0x1800524c7  cmp     cl, 62h ; 'b'
0x1800524ca  jz      short loc_180052506
0x1800524cc  cmp     cl, 6Fh ; 'o'
0x1800524cf  jz      short loc_1800524DF
0x1800524d1  cmp     cl, 78h ; 'x'
0x1800524d4  jnz     short loc_1800524F7
0x1800524d6  lea     rcx, a0x; "0x"
0x1800524dd  jmp     short loc_18005251F
0x1800524df  cmp     [rsp+1B0h+var_180], r13b
0x1800524e4  jz      short loc_1800524F7
0x1800524e6  lea     rcx, a0; "0"
0x1800524ed  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x1800524f2  mov     edi, r14d
0x1800524f5  jmp     short loc_180052524
0x1800524f7  mov     qword ptr [rsp+1B0h+var_160], r13
0x1800524fc  mov     qword ptr [rsp+1B0h+var_160+8], r13
0x180052501  mov     edi, r13d
0x180052504  jmp     short loc_180052529
0x180052506  lea     rcx, a0b; "0b"
0x18005250d  jmp     short loc_18005251F
0x18005250f  lea     rcx, a0x_0; "0X"
0x180052516  jmp     short loc_18005251F
0x180052518  lea     rcx, a0b_0; "0B"
0x18005251f  mov     qword ptr [rsp+1B0h+var_160+8], rdi
0x180052524  mov     qword ptr [rsp+1B0h+var_160], rcx
0x180052529  movaps  xmm0, [rsp+1B0h+var_160]
0x18005252e  movdqa  [rbp+0B0h+var_130], xmm0
0x180052533  add     eax, edi
0x180052535  mov     [rsp+1B0h+var_16C], eax
0x180052539  mov     [rsp+1B0h+var_140], r13d
0x18005253e  xorps   xmm0, xmm0
0x180052541  movups  [rbp+0B0h+var_D0], xmm0
0x180052545  mov     [rbp+0B0h+var_C0], r13
0x180052549  mov     [rbp+0B0h+var_B8], 0Fh
0x180052551  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180052555  cmp     [rsi+0Ch], r13b
0x180052559  jz      loc_180052651
0x18005255f  mov     rax, [rbp+0B0h+arg_20]
0x180052566  test    rax, rax
0x180052569  jz      short loc_180052582
0x18005256b  mov     rcx, [rax+8]
0x18005256f  mov     qword ptr [rsp+1B0h+var_160+8], rcx
0x180052574  mov     rax, [rcx]
0x180052577  mov     rax, [rax+8]
0x18005257b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052580  jmp     short loc_180052590
0x180052582  mov     cl, r14b
0x180052585  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18005258b  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x180052590  lea     rcx, [rsp+1B0h+var_160]
0x180052595  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18005259a  mov     r8, rax
0x18005259d  mov     rcx, [rax]
0x1800525a0  mov     rax, [rcx+28h]
0x1800525a4  lea     rdx, [rbp+0B0h+var_B0]
0x1800525a8  mov     rcx, r8
0x1800525ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525b0  lea     rdx, [rbp+0B0h+var_B0]
0x1800525b4  lea     rcx, [rbp+0B0h+var_D0]
0x1800525b8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800525bd  lea     rcx, [rbp+0B0h+var_B0]
0x1800525c1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800525c6  nop
0x1800525c7  mov     rcx, qword ptr [rsp+1B0h+var_160+8]
0x1800525cc  test    rcx, rcx
0x1800525cf  jz      short loc_1800525F6
0x1800525d1  mov     rax, [rcx]
0x1800525d4  mov     rax, [rax+10h]
0x1800525d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525dd  mov     r8, rax
0x1800525e0  test    rax, rax
0x1800525e3  jz      short loc_1800525F6
0x1800525e5  mov     rcx, [rax]
0x1800525e8  mov     rax, [rcx]
0x1800525eb  mov     edx, r14d
0x1800525ee  mov     rcx, r8
0x1800525f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525f6  lea     rax, [rbp+0B0h+var_D0]
0x1800525fa  cmp     [rbp+0B0h+var_B8], 0Fh
0x1800525ff  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180052604  mov     r10, [rbp+0B0h+var_C0]
0x180052608  mov     edx, r13d
0x18005260b  test    r10, r10
0x18005260e  jz      short loc_180052643
0x180052610  mov     r8, r12
0x180052613  sub     r8, [rsp+1B0h+var_138]
0x180052618  movsx   r9, byte ptr [rax]
0x18005261c  cmp     r8, r9
0x18005261f  jbe     short loc_180052643
0x180052621  lea     r11, [r10+rax]
0x180052625  movsx   rcx, r9b
0x180052629  sub     r8, rcx
0x18005262c  add     edx, r14d
0x18005262f  lea     rcx, [rax+1]
0x180052633  cmp     rcx, r11
0x180052636  cmovnz  rax, rcx
0x18005263a  movsx   r9, byte ptr [rax]
0x18005263e  cmp     r8, r9
0x180052641  ja      short loc_180052625
0x180052643  mov     [rsp+1B0h+var_140], edx
0x180052647  mov     eax, [rsp+1B0h+var_16C]
0x18005264b  add     eax, edx
0x18005264d  mov     [rsp+1B0h+var_16C], eax
0x180052651  cmp     [rsi+0Dh], r13b
0x180052655  jz      short loc_18005265D
0x180052657  cmp     [rsi+9], r13b
0x18005265b  jz      short loc_180052660
0x18005265d  mov     r14b, r13b
0x180052660  mov     [rsp+1B0h+var_170], r14b
0x180052665  mov     [rbp+0B0h+var_120], r12
0x180052669  mov     [rbp+0B0h+var_118], rsi
0x18005266d  lea     rcx, [rsp+1B0h+var_180]
0x180052672  mov     [rbp+0B0h+var_110], rcx
0x180052676  lea     rcx, [rbp+0B0h+var_130]
0x18005267a  mov     [rbp+0B0h+var_108], rcx
0x18005267e  lea     rcx, [rsp+1B0h+var_170]
0x180052683  mov     [rbp+0B0h+var_100], rcx
0x180052687  lea     rcx, [rsp+1B0h+var_16C]
0x18005268c  mov     [rbp+0B0h+var_F8], rcx
0x180052690  lea     rcx, [rsp+1B0h+var_140]
0x180052695  mov     [rbp+0B0h+var_F0], rcx
0x180052699  lea     rcx, [rsp+1B0h+var_138]
0x18005269e  mov     [rbp+0B0h+var_E8], rcx
0x1800526a2  lea     rcx, [rbp+0B0h+var_D0]
0x1800526a6  mov     [rbp+0B0h+var_E0], rcx
0x1800526aa  lea     rcx, [rbp+0B0h+arg_20]
0x1800526b1  mov     [rbp+0B0h+var_D8], rcx
0x1800526b5  lea     rcx, [rbp+0B0h+var_120]
0x1800526b9  test    r14b, r14b
0x1800526bc  jz      short loc_1800526CB
0x1800526be  mov     r8, rbx
0x1800526c1  mov     rdx, r15
0x1800526c4  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800526c9  jmp     short loc_1800526E2
0x1800526cb  mov     [rsp+1B0h+var_188], rcx
0x1800526d0  mov     r9, rsi
0x1800526d3  mov     r8d, eax
0x1800526d6  mov     rdx, rbx
0x1800526d9  mov     rcx, r15
0x1800526dc  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@2@YA?AV12@V12@EU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@0@YA?AV10@0EU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800526e1  nop
0x1800526e2  lea     rcx, [rbp+0B0h+var_D0]
0x1800526e6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800526eb  mov     rax, r15
0x1800526ee  mov     rcx, [rbp+0B0h+var_40]
0x1800526f2  xor     rcx, rsp; StackCookie
0x1800526f5  call    __security_check_cookie
0x1800526fa  mov     rbx, [rsp+1B0h+arg_8]
0x180052702  add     rsp, 180h
0x180052709  pop     r15
0x18005270b  pop     r14
0x18005270d  pop     r13
0x18005270f  pop     r12
0x180052711  pop     rdi
0x180052712  pop     rsi
0x180052713  pop     rbp
0x180052714  retn
0x180052715  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x18005271c  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

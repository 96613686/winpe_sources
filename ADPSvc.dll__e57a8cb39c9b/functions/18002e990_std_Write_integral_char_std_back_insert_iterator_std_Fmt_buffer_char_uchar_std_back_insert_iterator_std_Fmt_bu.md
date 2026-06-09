# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x18002e990`
- end: `0x18002ed7e`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1006`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, unsigned __int8, __int128 *, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x18002aad0`
- `0x18002accc`
- `0x18002e990`

## callees

- `0x180002250`
- `0x180013830`
- `0x180020b94`
- `0x180021fa4`
- `0x1800235a8`
- `0x18002ac28`
- `0x18002e364`
- `0x18002e990`
- `0x180030078`
- `0x180031240`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002ebe1`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002ebe1`

## pseudocode

```c
_QWORD *__fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>(
        _QWORD *a1,
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
  int v14; // eax
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
  int v31; // [rsp+44h] [rbp-BCh] BYREF
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
      std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, &v32, (int *)&v41);
    }
    else
    {
      v32 = v9;
      v33 = *((_DWORD *)a4 + 4);
      std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>(
        (_DWORD)a1,
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
      (__int64)v5,
      v27,
      (__int64)v37);
  std::string::~string(&v38);
  return a1;
}

```

## disassembly

```asm
0x18002e990  mov     [rsp-8+arg_8], rbx
0x18002e995  push    rbp
0x18002e996  push    rsi
0x18002e997  push    rdi
0x18002e998  push    r12
0x18002e99a  push    r13
0x18002e99c  push    r14
0x18002e99e  push    r15
0x18002e9a0  lea     rbp, [rsp-80h]
0x18002e9a5  sub     rsp, 180h
0x18002e9ac  mov     rax, cs:__security_cookie
0x18002e9b3  xor     rax, rsp
0x18002e9b6  mov     [rbp+0B0h+var_40], rax
0x18002e9ba  mov     rsi, r9
0x18002e9bd  mov     rbx, rdx
0x18002e9c0  mov     r15, rcx
0x18002e9c3  mov     [rsp+1B0h+var_180], r8b
0x18002e9c8  xor     r13d, r13d
0x18002e9cb  mov     al, [r9+8]
0x18002e9cf  cmp     al, 63h ; 'c'
0x18002e9d1  jnz     loc_18002EA61
0x18002e9d7  cmp     r8b, 7Fh
0x18002e9db  ja      loc_18002ED71
0x18002e9e1  mov     [r9+0Bh], r13b
0x18002e9e5  movups  xmm0, xmmword ptr [r9]
0x18002e9e9  movaps  [rbp+0B0h+var_B0], xmm0
0x18002e9ed  mov     eax, [r9+10h]
0x18002e9f1  mov     [rbp+0B0h+var_A0], eax
0x18002e9f4  mov     rax, [rbp+0B0h+arg_20]
0x18002e9fb  mov     [rsp+1B0h+var_178], r8b
0x18002ea00  mov     ecx, [r9+8]
0x18002ea04  test    cl, cl
0x18002ea06  jz      short loc_18002EA31
0x18002ea08  cmp     cl, 63h ; 'c'
0x18002ea0b  jz      short loc_18002EA31
0x18002ea0d  movaps  [rsp+1B0h+var_160], xmm0
0x18002ea12  mov     ecx, [r9+10h]
0x18002ea16  mov     [rsp+1B0h+var_150], ecx
0x18002ea1a  mov     [rsp+1B0h+var_190], rax
0x18002ea1f  lea     r9, [rsp+1B0h+var_160]
0x18002ea24  mov     rcx, r15
0x18002ea27  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x18002ea2c  jmp     loc_18002ED47
0x18002ea31  lea     rcx, [rsp+1B0h+var_178]
0x18002ea36  mov     qword ptr [rsp+1B0h+var_160], rcx
0x18002ea3b  mov     r14d, 1
0x18002ea41  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x18002ea46  mov     [rsp+1B0h+var_190], rax
0x18002ea4b  lea     r9, [rbp+0B0h+var_B0]
0x18002ea4f  lea     r8, [rsp+1B0h+var_160]
0x18002ea54  mov     rcx, r15
0x18002ea57  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x18002ea5c  jmp     loc_18002ED47
0x18002ea61  mov     edi, 2
0x18002ea66  cmp     [r9+0Ah], r13b
0x18002ea6a  jnz     short loc_18002EA70
0x18002ea6c  mov     [r9+0Ah], dil
0x18002ea70  cmp     al, 42h ; 'B'
0x18002ea72  jz      short loc_18002EA99
0x18002ea74  cmp     al, 58h ; 'X'
0x18002ea76  jz      short loc_18002EA92
0x18002ea78  cmp     al, 62h ; 'b'
0x18002ea7a  jz      short loc_18002EA99
0x18002ea7c  cmp     al, 6Fh ; 'o'
0x18002ea7e  jz      short loc_18002EA8B
0x18002ea80  cmp     al, 78h ; 'x'
0x18002ea82  jz      short loc_18002EA92
0x18002ea84  mov     eax, 0Ah
0x18002ea89  jmp     short loc_18002EA9B
0x18002ea8b  mov     eax, 8
0x18002ea90  jmp     short loc_18002EA9B
0x18002ea92  mov     eax, 10h
0x18002ea97  jmp     short loc_18002EA9B
0x18002ea99  mov     eax, edi
0x18002ea9b  mov     dword ptr [rsp+1B0h+var_190], eax
0x18002ea9f  mov     r9b, r8b
0x18002eaa2  lea     r8, [rbp+0B0h+var_4F]
0x18002eaa6  lea     rdx, [rbp+0B0h+var_90]
0x18002eaaa  lea     rcx, [rsp+1B0h+var_160]
0x18002eaaf  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x18002eab4  mov     r12, [rax]
0x18002eab7  lea     rcx, [rbp+0B0h+var_90]
0x18002eabb  mov     [rsp+1B0h+var_138], rcx
0x18002eac0  mov     eax, r12d
0x18002eac3  sub     eax, ecx
0x18002eac5  mov     [rsp+1B0h+var_16C], eax
0x18002eac9  cmp     [rsi+0Ah], dil
0x18002eacd  jz      short loc_18002EAD5
0x18002eacf  inc     eax
0x18002ead1  mov     [rsp+1B0h+var_16C], eax
0x18002ead5  mov     r14d, 1
0x18002eadb  cmp     byte ptr [rsi+8], 58h ; 'X'
0x18002eadf  jnz     short loc_18002EB08
0x18002eae1  lea     rcx, [rbp+0B0h+var_90]
0x18002eae5  lea     rdx, [rbp+0B0h+var_90]
0x18002eae9  cmp     rdx, r12
0x18002eaec  jz      short loc_18002EB08
0x18002eaee  mov     dl, [rcx]
0x18002eaf0  lea     eax, [rdx-61h]
0x18002eaf3  cmp     al, 19h
0x18002eaf5  ja      short loc_18002EAFC
0x18002eaf7  sub     dl, 20h ; ' '
0x18002eafa  mov     [rcx], dl
0x18002eafc  add     rcx, r14
0x18002eaff  cmp     rcx, r12
0x18002eb02  jnz     short loc_18002EAEE
0x18002eb04  mov     eax, [rsp+1B0h+var_16C]
0x18002eb08  mov     qword ptr [rbp+0B0h+var_130], r13
0x18002eb0c  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x18002eb10  cmp     [rsi+0Bh], r13b
0x18002eb14  jz      short loc_18002EB95
0x18002eb16  mov     cl, [rsi+8]
0x18002eb19  cmp     cl, 42h ; 'B'
0x18002eb1c  jz      short loc_18002EB74
0x18002eb1e  cmp     cl, 58h ; 'X'
0x18002eb21  jz      short loc_18002EB6B
0x18002eb23  cmp     cl, 62h ; 'b'
0x18002eb26  jz      short loc_18002EB62
0x18002eb28  cmp     cl, 6Fh ; 'o'
0x18002eb2b  jz      short loc_18002EB3B
0x18002eb2d  cmp     cl, 78h ; 'x'
0x18002eb30  jnz     short loc_18002EB53
0x18002eb32  lea     rcx, a0x; "0x"
0x18002eb39  jmp     short loc_18002EB7B
0x18002eb3b  cmp     [rsp+1B0h+var_180], r13b
0x18002eb40  jz      short loc_18002EB53
0x18002eb42  lea     rcx, a0; "0"
0x18002eb49  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x18002eb4e  mov     edi, r14d
0x18002eb51  jmp     short loc_18002EB80
0x18002eb53  mov     qword ptr [rsp+1B0h+var_160], r13
0x18002eb58  mov     qword ptr [rsp+1B0h+var_160+8], r13
0x18002eb5d  mov     edi, r13d
0x18002eb60  jmp     short loc_18002EB85
0x18002eb62  lea     rcx, a0b; "0b"
0x18002eb69  jmp     short loc_18002EB7B
0x18002eb6b  lea     rcx, a0x_0; "0X"
0x18002eb72  jmp     short loc_18002EB7B
0x18002eb74  lea     rcx, a0b_0; "0B"
0x18002eb7b  mov     qword ptr [rsp+1B0h+var_160+8], rdi
0x18002eb80  mov     qword ptr [rsp+1B0h+var_160], rcx
0x18002eb85  movaps  xmm0, [rsp+1B0h+var_160]
0x18002eb8a  movdqa  [rbp+0B0h+var_130], xmm0
0x18002eb8f  add     eax, edi
0x18002eb91  mov     [rsp+1B0h+var_16C], eax
0x18002eb95  mov     [rsp+1B0h+var_140], r13d
0x18002eb9a  xorps   xmm0, xmm0
0x18002eb9d  movups  [rbp+0B0h+var_D0], xmm0
0x18002eba1  mov     [rbp+0B0h+var_C0], r13
0x18002eba5  mov     [rbp+0B0h+var_B8], 0Fh
0x18002ebad  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x18002ebb1  cmp     [rsi+0Ch], r13b
0x18002ebb5  jz      loc_18002ECAD
0x18002ebbb  mov     rax, [rbp+0B0h+arg_20]
0x18002ebc2  test    rax, rax
0x18002ebc5  jz      short loc_18002EBDE
0x18002ebc7  mov     rcx, [rax+8]
0x18002ebcb  mov     qword ptr [rsp+1B0h+var_160+8], rcx
0x18002ebd0  mov     rax, [rcx]
0x18002ebd3  mov     rax, [rax+8]
0x18002ebd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebdc  jmp     short loc_18002EBEC
0x18002ebde  mov     cl, r14b
0x18002ebe1  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002ebe7  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x18002ebec  lea     rcx, [rsp+1B0h+var_160]
0x18002ebf1  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002ebf6  mov     r8, rax
0x18002ebf9  mov     rcx, [rax]
0x18002ebfc  mov     rax, [rcx+28h]
0x18002ec00  lea     rdx, [rbp+0B0h+var_B0]
0x18002ec04  mov     rcx, r8
0x18002ec07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec0c  lea     rdx, [rbp+0B0h+var_B0]
0x18002ec10  lea     rcx, [rbp+0B0h+var_D0]
0x18002ec14  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002ec19  lea     rcx, [rbp+0B0h+var_B0]
0x18002ec1d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ec22  nop
0x18002ec23  mov     rcx, qword ptr [rsp+1B0h+var_160+8]
0x18002ec28  test    rcx, rcx
0x18002ec2b  jz      short loc_18002EC52
0x18002ec2d  mov     rax, [rcx]
0x18002ec30  mov     rax, [rax+10h]
0x18002ec34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec39  mov     r8, rax
0x18002ec3c  test    rax, rax
0x18002ec3f  jz      short loc_18002EC52
0x18002ec41  mov     rcx, [rax]
0x18002ec44  mov     rax, [rcx]
0x18002ec47  mov     edx, r14d
0x18002ec4a  mov     rcx, r8
0x18002ec4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec52  lea     rax, [rbp+0B0h+var_D0]
0x18002ec56  cmp     [rbp+0B0h+var_B8], 0Fh
0x18002ec5b  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x18002ec60  mov     r10, [rbp+0B0h+var_C0]
0x18002ec64  mov     edx, r13d
0x18002ec67  test    r10, r10
0x18002ec6a  jz      short loc_18002EC9F
0x18002ec6c  mov     r8, r12
0x18002ec6f  sub     r8, [rsp+1B0h+var_138]
0x18002ec74  movsx   r9, byte ptr [rax]
0x18002ec78  cmp     r8, r9
0x18002ec7b  jbe     short loc_18002EC9F
0x18002ec7d  lea     r11, [r10+rax]
0x18002ec81  movsx   rcx, r9b
0x18002ec85  sub     r8, rcx
0x18002ec88  add     edx, r14d
0x18002ec8b  lea     rcx, [rax+1]
0x18002ec8f  cmp     rcx, r11
0x18002ec92  cmovnz  rax, rcx
0x18002ec96  movsx   r9, byte ptr [rax]
0x18002ec9a  cmp     r8, r9
0x18002ec9d  ja      short loc_18002EC81
0x18002ec9f  mov     [rsp+1B0h+var_140], edx
0x18002eca3  mov     eax, [rsp+1B0h+var_16C]
0x18002eca7  add     eax, edx
0x18002eca9  mov     [rsp+1B0h+var_16C], eax
0x18002ecad  cmp     [rsi+0Dh], r13b
0x18002ecb1  jz      short loc_18002ECB9
0x18002ecb3  cmp     [rsi+9], r13b
0x18002ecb7  jz      short loc_18002ECBC
0x18002ecb9  mov     r14b, r13b
0x18002ecbc  mov     [rsp+1B0h+var_170], r14b
0x18002ecc1  mov     [rbp+0B0h+var_120], r12
0x18002ecc5  mov     [rbp+0B0h+var_118], rsi
0x18002ecc9  lea     rcx, [rsp+1B0h+var_180]
0x18002ecce  mov     [rbp+0B0h+var_110], rcx
0x18002ecd2  lea     rcx, [rbp+0B0h+var_130]
0x18002ecd6  mov     [rbp+0B0h+var_108], rcx
0x18002ecda  lea     rcx, [rsp+1B0h+var_170]
0x18002ecdf  mov     [rbp+0B0h+var_100], rcx
0x18002ece3  lea     rcx, [rsp+1B0h+var_16C]
0x18002ece8  mov     [rbp+0B0h+var_F8], rcx
0x18002ecec  lea     rcx, [rsp+1B0h+var_140]
0x18002ecf1  mov     [rbp+0B0h+var_F0], rcx
0x18002ecf5  lea     rcx, [rsp+1B0h+var_138]
0x18002ecfa  mov     [rbp+0B0h+var_E8], rcx
0x18002ecfe  lea     rcx, [rbp+0B0h+var_D0]
0x18002ed02  mov     [rbp+0B0h+var_E0], rcx
0x18002ed06  lea     rcx, [rbp+0B0h+arg_20]
0x18002ed0d  mov     [rbp+0B0h+var_D8], rcx
0x18002ed11  lea     rcx, [rbp+0B0h+var_120]
0x18002ed15  test    r14b, r14b
0x18002ed18  jz      short loc_18002ED27
0x18002ed1a  mov     r8, rbx
0x18002ed1d  mov     rdx, r15
0x18002ed20  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002ed25  jmp     short loc_18002ED3E
0x18002ed27  mov     [rsp+1B0h+var_188], rcx
0x18002ed2c  mov     r9, rsi
0x18002ed2f  mov     r8d, eax
0x18002ed32  mov     rdx, rbx
0x18002ed35  mov     rcx, r15
0x18002ed38  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@2@YA?AV12@V12@EU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@0@YA?AV10@0EU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x18002ed3d  nop
0x18002ed3e  lea     rcx, [rbp+0B0h+var_D0]
0x18002ed42  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ed47  mov     rax, r15
0x18002ed4a  mov     rcx, [rbp+0B0h+var_40]
0x18002ed4e  xor     rcx, rsp; StackCookie
0x18002ed51  call    __security_check_cookie
0x18002ed56  mov     rbx, [rsp+1B0h+arg_8]
0x18002ed5e  add     rsp, 180h
0x18002ed65  pop     r15
0x18002ed67  pop     r14
0x18002ed69  pop     r13
0x18002ed6b  pop     r12
0x18002ed6d  pop     rdi
0x18002ed6e  pop     rsi
0x18002ed6f  pop     rbp
0x18002ed70  retn
0x18002ed71  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x18002ed78  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

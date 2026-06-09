# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x14004dad0`
- end: `0x14004debe`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1006`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, unsigned __int8, __int128 *, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1400498e8`
- `0x140049ae4`
- `0x14004dad0`

## callees

- `0x1400054c0`
- `0x140049a40`
- `0x14004d4a4`
- `0x14004dad0`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x140051414`
- `0x140054144`
- `0x1400556c4`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004dd21`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004dd21`

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
0x14004dad0  mov     [rsp-8+arg_8], rbx
0x14004dad5  push    rbp
0x14004dad6  push    rsi
0x14004dad7  push    rdi
0x14004dad8  push    r12
0x14004dada  push    r13
0x14004dadc  push    r14
0x14004dade  push    r15
0x14004dae0  lea     rbp, [rsp-80h]
0x14004dae5  sub     rsp, 180h
0x14004daec  mov     rax, cs:__security_cookie
0x14004daf3  xor     rax, rsp
0x14004daf6  mov     [rbp+0B0h+var_40], rax
0x14004dafa  mov     rsi, r9
0x14004dafd  mov     rbx, rdx
0x14004db00  mov     r15, rcx
0x14004db03  mov     [rsp+1B0h+var_180], r8b
0x14004db08  xor     r13d, r13d
0x14004db0b  mov     al, [r9+8]
0x14004db0f  cmp     al, 63h ; 'c'
0x14004db11  jnz     loc_14004DBA1
0x14004db17  cmp     r8b, 7Fh
0x14004db1b  ja      loc_14004DEB1
0x14004db21  mov     [r9+0Bh], r13b
0x14004db25  movups  xmm0, xmmword ptr [r9]
0x14004db29  movaps  [rbp+0B0h+var_B0], xmm0
0x14004db2d  mov     eax, [r9+10h]
0x14004db31  mov     [rbp+0B0h+var_A0], eax
0x14004db34  mov     rax, [rbp+0B0h+arg_20]
0x14004db3b  mov     [rsp+1B0h+var_178], r8b
0x14004db40  mov     ecx, [r9+8]
0x14004db44  test    cl, cl
0x14004db46  jz      short loc_14004DB71
0x14004db48  cmp     cl, 63h ; 'c'
0x14004db4b  jz      short loc_14004DB71
0x14004db4d  movaps  [rsp+1B0h+var_160], xmm0
0x14004db52  mov     ecx, [r9+10h]
0x14004db56  mov     [rsp+1B0h+var_150], ecx
0x14004db5a  mov     [rsp+1B0h+var_190], rax
0x14004db5f  lea     r9, [rsp+1B0h+var_160]
0x14004db64  mov     rcx, r15
0x14004db67  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x14004db6c  jmp     loc_14004DE87
0x14004db71  lea     rcx, [rsp+1B0h+var_178]
0x14004db76  mov     qword ptr [rsp+1B0h+var_160], rcx
0x14004db7b  mov     r14d, 1
0x14004db81  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x14004db86  mov     [rsp+1B0h+var_190], rax
0x14004db8b  lea     r9, [rbp+0B0h+var_B0]
0x14004db8f  lea     r8, [rsp+1B0h+var_160]
0x14004db94  mov     rcx, r15
0x14004db97  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x14004db9c  jmp     loc_14004DE87
0x14004dba1  mov     edi, 2
0x14004dba6  cmp     [r9+0Ah], r13b
0x14004dbaa  jnz     short loc_14004DBB0
0x14004dbac  mov     [r9+0Ah], dil
0x14004dbb0  cmp     al, 42h ; 'B'
0x14004dbb2  jz      short loc_14004DBD9
0x14004dbb4  cmp     al, 58h ; 'X'
0x14004dbb6  jz      short loc_14004DBD2
0x14004dbb8  cmp     al, 62h ; 'b'
0x14004dbba  jz      short loc_14004DBD9
0x14004dbbc  cmp     al, 6Fh ; 'o'
0x14004dbbe  jz      short loc_14004DBCB
0x14004dbc0  cmp     al, 78h ; 'x'
0x14004dbc2  jz      short loc_14004DBD2
0x14004dbc4  mov     eax, 0Ah
0x14004dbc9  jmp     short loc_14004DBDB
0x14004dbcb  mov     eax, 8
0x14004dbd0  jmp     short loc_14004DBDB
0x14004dbd2  mov     eax, 10h
0x14004dbd7  jmp     short loc_14004DBDB
0x14004dbd9  mov     eax, edi
0x14004dbdb  mov     dword ptr [rsp+1B0h+var_190], eax
0x14004dbdf  mov     r9b, r8b
0x14004dbe2  lea     r8, [rbp+0B0h+var_4F]
0x14004dbe6  lea     rdx, [rbp+0B0h+var_90]
0x14004dbea  lea     rcx, [rsp+1B0h+var_160]
0x14004dbef  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x14004dbf4  mov     r12, [rax]
0x14004dbf7  lea     rcx, [rbp+0B0h+var_90]
0x14004dbfb  mov     [rsp+1B0h+var_138], rcx
0x14004dc00  mov     eax, r12d
0x14004dc03  sub     eax, ecx
0x14004dc05  mov     [rsp+1B0h+var_16C], eax
0x14004dc09  cmp     [rsi+0Ah], dil
0x14004dc0d  jz      short loc_14004DC15
0x14004dc0f  inc     eax
0x14004dc11  mov     [rsp+1B0h+var_16C], eax
0x14004dc15  mov     r14d, 1
0x14004dc1b  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14004dc1f  jnz     short loc_14004DC48
0x14004dc21  lea     rcx, [rbp+0B0h+var_90]
0x14004dc25  lea     rdx, [rbp+0B0h+var_90]
0x14004dc29  cmp     rdx, r12
0x14004dc2c  jz      short loc_14004DC48
0x14004dc2e  mov     dl, [rcx]
0x14004dc30  lea     eax, [rdx-61h]
0x14004dc33  cmp     al, 19h
0x14004dc35  ja      short loc_14004DC3C
0x14004dc37  sub     dl, 20h ; ' '
0x14004dc3a  mov     [rcx], dl
0x14004dc3c  add     rcx, r14
0x14004dc3f  cmp     rcx, r12
0x14004dc42  jnz     short loc_14004DC2E
0x14004dc44  mov     eax, [rsp+1B0h+var_16C]
0x14004dc48  mov     qword ptr [rbp+0B0h+var_130], r13
0x14004dc4c  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x14004dc50  cmp     [rsi+0Bh], r13b
0x14004dc54  jz      short loc_14004DCD5
0x14004dc56  mov     cl, [rsi+8]
0x14004dc59  cmp     cl, 42h ; 'B'
0x14004dc5c  jz      short loc_14004DCB4
0x14004dc5e  cmp     cl, 58h ; 'X'
0x14004dc61  jz      short loc_14004DCAB
0x14004dc63  cmp     cl, 62h ; 'b'
0x14004dc66  jz      short loc_14004DCA2
0x14004dc68  cmp     cl, 6Fh ; 'o'
0x14004dc6b  jz      short loc_14004DC7B
0x14004dc6d  cmp     cl, 78h ; 'x'
0x14004dc70  jnz     short loc_14004DC93
0x14004dc72  lea     rcx, a0x; "0x"
0x14004dc79  jmp     short loc_14004DCBB
0x14004dc7b  cmp     [rsp+1B0h+var_180], r13b
0x14004dc80  jz      short loc_14004DC93
0x14004dc82  lea     rcx, a0; "0"
0x14004dc89  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x14004dc8e  mov     edi, r14d
0x14004dc91  jmp     short loc_14004DCC0
0x14004dc93  mov     qword ptr [rsp+1B0h+var_160], r13
0x14004dc98  mov     qword ptr [rsp+1B0h+var_160+8], r13
0x14004dc9d  mov     edi, r13d
0x14004dca0  jmp     short loc_14004DCC5
0x14004dca2  lea     rcx, a0b; "0b"
0x14004dca9  jmp     short loc_14004DCBB
0x14004dcab  lea     rcx, a0x_0; "0X"
0x14004dcb2  jmp     short loc_14004DCBB
0x14004dcb4  lea     rcx, a0b_0; "0B"
0x14004dcbb  mov     qword ptr [rsp+1B0h+var_160+8], rdi
0x14004dcc0  mov     qword ptr [rsp+1B0h+var_160], rcx
0x14004dcc5  movaps  xmm0, [rsp+1B0h+var_160]
0x14004dcca  movdqa  [rbp+0B0h+var_130], xmm0
0x14004dccf  add     eax, edi
0x14004dcd1  mov     [rsp+1B0h+var_16C], eax
0x14004dcd5  mov     [rsp+1B0h+var_140], r13d
0x14004dcda  xorps   xmm0, xmm0
0x14004dcdd  movups  [rbp+0B0h+var_D0], xmm0
0x14004dce1  mov     [rbp+0B0h+var_C0], r13
0x14004dce5  mov     [rbp+0B0h+var_B8], 0Fh
0x14004dced  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14004dcf1  cmp     [rsi+0Ch], r13b
0x14004dcf5  jz      loc_14004DDED
0x14004dcfb  mov     rax, [rbp+0B0h+arg_20]
0x14004dd02  test    rax, rax
0x14004dd05  jz      short loc_14004DD1E
0x14004dd07  mov     rcx, [rax+8]
0x14004dd0b  mov     qword ptr [rsp+1B0h+var_160+8], rcx
0x14004dd10  mov     rax, [rcx]
0x14004dd13  mov     rax, [rax+8]
0x14004dd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd1c  jmp     short loc_14004DD2C
0x14004dd1e  mov     cl, r14b
0x14004dd21  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004dd27  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x14004dd2c  lea     rcx, [rsp+1B0h+var_160]
0x14004dd31  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004dd36  mov     r8, rax
0x14004dd39  mov     rcx, [rax]
0x14004dd3c  mov     rax, [rcx+28h]
0x14004dd40  lea     rdx, [rbp+0B0h+var_B0]
0x14004dd44  mov     rcx, r8
0x14004dd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd4c  lea     rdx, [rbp+0B0h+var_B0]
0x14004dd50  lea     rcx, [rbp+0B0h+var_D0]
0x14004dd54  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004dd59  lea     rcx, [rbp+0B0h+var_B0]
0x14004dd5d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004dd62  nop
0x14004dd63  mov     rcx, qword ptr [rsp+1B0h+var_160+8]
0x14004dd68  test    rcx, rcx
0x14004dd6b  jz      short loc_14004DD92
0x14004dd6d  mov     rax, [rcx]
0x14004dd70  mov     rax, [rax+10h]
0x14004dd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd79  mov     r8, rax
0x14004dd7c  test    rax, rax
0x14004dd7f  jz      short loc_14004DD92
0x14004dd81  mov     rcx, [rax]
0x14004dd84  mov     rax, [rcx]
0x14004dd87  mov     edx, r14d
0x14004dd8a  mov     rcx, r8
0x14004dd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd92  lea     rax, [rbp+0B0h+var_D0]
0x14004dd96  cmp     [rbp+0B0h+var_B8], 0Fh
0x14004dd9b  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14004dda0  mov     r10, [rbp+0B0h+var_C0]
0x14004dda4  mov     edx, r13d
0x14004dda7  test    r10, r10
0x14004ddaa  jz      short loc_14004DDDF
0x14004ddac  mov     r8, r12
0x14004ddaf  sub     r8, [rsp+1B0h+var_138]
0x14004ddb4  movsx   r9, byte ptr [rax]
0x14004ddb8  cmp     r8, r9
0x14004ddbb  jbe     short loc_14004DDDF
0x14004ddbd  lea     r11, [r10+rax]
0x14004ddc1  movsx   rcx, r9b
0x14004ddc5  sub     r8, rcx
0x14004ddc8  add     edx, r14d
0x14004ddcb  lea     rcx, [rax+1]
0x14004ddcf  cmp     rcx, r11
0x14004ddd2  cmovnz  rax, rcx
0x14004ddd6  movsx   r9, byte ptr [rax]
0x14004ddda  cmp     r8, r9
0x14004dddd  ja      short loc_14004DDC1
0x14004dddf  mov     [rsp+1B0h+var_140], edx
0x14004dde3  mov     eax, [rsp+1B0h+var_16C]
0x14004dde7  add     eax, edx
0x14004dde9  mov     [rsp+1B0h+var_16C], eax
0x14004dded  cmp     [rsi+0Dh], r13b
0x14004ddf1  jz      short loc_14004DDF9
0x14004ddf3  cmp     [rsi+9], r13b
0x14004ddf7  jz      short loc_14004DDFC
0x14004ddf9  mov     r14b, r13b
0x14004ddfc  mov     [rsp+1B0h+var_170], r14b
0x14004de01  mov     [rbp+0B0h+var_120], r12
0x14004de05  mov     [rbp+0B0h+var_118], rsi
0x14004de09  lea     rcx, [rsp+1B0h+var_180]
0x14004de0e  mov     [rbp+0B0h+var_110], rcx
0x14004de12  lea     rcx, [rbp+0B0h+var_130]
0x14004de16  mov     [rbp+0B0h+var_108], rcx
0x14004de1a  lea     rcx, [rsp+1B0h+var_170]
0x14004de1f  mov     [rbp+0B0h+var_100], rcx
0x14004de23  lea     rcx, [rsp+1B0h+var_16C]
0x14004de28  mov     [rbp+0B0h+var_F8], rcx
0x14004de2c  lea     rcx, [rsp+1B0h+var_140]
0x14004de31  mov     [rbp+0B0h+var_F0], rcx
0x14004de35  lea     rcx, [rsp+1B0h+var_138]
0x14004de3a  mov     [rbp+0B0h+var_E8], rcx
0x14004de3e  lea     rcx, [rbp+0B0h+var_D0]
0x14004de42  mov     [rbp+0B0h+var_E0], rcx
0x14004de46  lea     rcx, [rbp+0B0h+arg_20]
0x14004de4d  mov     [rbp+0B0h+var_D8], rcx
0x14004de51  lea     rcx, [rbp+0B0h+var_120]
0x14004de55  test    r14b, r14b
0x14004de58  jz      short loc_14004DE67
0x14004de5a  mov     r8, rbx
0x14004de5d  mov     rdx, r15
0x14004de60  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x14004de65  jmp     short loc_14004DE7E
0x14004de67  mov     [rsp+1B0h+var_188], rcx
0x14004de6c  mov     r9, rsi
0x14004de6f  mov     r8d, eax
0x14004de72  mov     rdx, rbx
0x14004de75  mov     rcx, r15
0x14004de78  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@2@YA?AV12@V12@EU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@0@YA?AV10@0EU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14004de7d  nop
0x14004de7e  lea     rcx, [rbp+0B0h+var_D0]
0x14004de82  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004de87  mov     rax, r15
0x14004de8a  mov     rcx, [rbp+0B0h+var_40]
0x14004de8e  xor     rcx, rsp; StackCookie
0x14004de91  call    __security_check_cookie
0x14004de96  mov     rbx, [rsp+1B0h+arg_8]
0x14004de9e  add     rsp, 180h
0x14004dea5  pop     r15
0x14004dea7  pop     r14
0x14004dea9  pop     r13
0x14004deab  pop     r12
0x14004dead  pop     rdi
0x14004deae  pop     rsi
0x14004deaf  pop     rbp
0x14004deb0  retn
0x14004deb1  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x14004deb8  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

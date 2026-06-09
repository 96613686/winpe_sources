# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180027d64`
- end: `0x180028152`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1006`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180023e98`
- `0x180024094`
- `0x180027d64`

## callees

- `0x180004180`
- `0x180023ff0`
- `0x180027738`
- `0x180027d64`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b65c`
- `0x18002dd84`
- `0x18002f304`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180027fb5`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180027fb5`

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
0x180027d64  mov     [rsp-8+arg_8], rbx
0x180027d69  push    rbp
0x180027d6a  push    rsi
0x180027d6b  push    rdi
0x180027d6c  push    r12
0x180027d6e  push    r13
0x180027d70  push    r14
0x180027d72  push    r15
0x180027d74  lea     rbp, [rsp-80h]
0x180027d79  sub     rsp, 180h
0x180027d80  mov     rax, cs:__security_cookie
0x180027d87  xor     rax, rsp
0x180027d8a  mov     [rbp+0B0h+var_40], rax
0x180027d8e  mov     rsi, r9
0x180027d91  mov     rbx, rdx
0x180027d94  mov     r15, rcx
0x180027d97  mov     [rsp+1B0h+var_180], r8b
0x180027d9c  xor     r13d, r13d
0x180027d9f  mov     al, [r9+8]
0x180027da3  cmp     al, 63h ; 'c'
0x180027da5  jnz     loc_180027E35
0x180027dab  cmp     r8b, 7Fh
0x180027daf  ja      loc_180028145
0x180027db5  mov     [r9+0Bh], r13b
0x180027db9  movups  xmm0, xmmword ptr [r9]
0x180027dbd  movaps  [rbp+0B0h+var_B0], xmm0
0x180027dc1  mov     eax, [r9+10h]
0x180027dc5  mov     [rbp+0B0h+var_A0], eax
0x180027dc8  mov     rax, [rbp+0B0h+arg_20]
0x180027dcf  mov     [rsp+1B0h+var_178], r8b
0x180027dd4  mov     ecx, [r9+8]
0x180027dd8  test    cl, cl
0x180027dda  jz      short loc_180027E05
0x180027ddc  cmp     cl, 63h ; 'c'
0x180027ddf  jz      short loc_180027E05
0x180027de1  movaps  [rsp+1B0h+var_160], xmm0
0x180027de6  mov     ecx, [r9+10h]
0x180027dea  mov     [rsp+1B0h+var_150], ecx
0x180027dee  mov     [rsp+1B0h+var_190], rax
0x180027df3  lea     r9, [rsp+1B0h+var_160]
0x180027df8  mov     rcx, r15
0x180027dfb  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180027e00  jmp     loc_18002811B
0x180027e05  lea     rcx, [rsp+1B0h+var_178]
0x180027e0a  mov     qword ptr [rsp+1B0h+var_160], rcx
0x180027e0f  mov     r14d, 1
0x180027e15  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x180027e1a  mov     [rsp+1B0h+var_190], rax
0x180027e1f  lea     r9, [rbp+0B0h+var_B0]
0x180027e23  lea     r8, [rsp+1B0h+var_160]
0x180027e28  mov     rcx, r15
0x180027e2b  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x180027e30  jmp     loc_18002811B
0x180027e35  mov     edi, 2
0x180027e3a  cmp     [r9+0Ah], r13b
0x180027e3e  jnz     short loc_180027E44
0x180027e40  mov     [r9+0Ah], dil
0x180027e44  cmp     al, 42h ; 'B'
0x180027e46  jz      short loc_180027E6D
0x180027e48  cmp     al, 58h ; 'X'
0x180027e4a  jz      short loc_180027E66
0x180027e4c  cmp     al, 62h ; 'b'
0x180027e4e  jz      short loc_180027E6D
0x180027e50  cmp     al, 6Fh ; 'o'
0x180027e52  jz      short loc_180027E5F
0x180027e54  cmp     al, 78h ; 'x'
0x180027e56  jz      short loc_180027E66
0x180027e58  mov     eax, 0Ah
0x180027e5d  jmp     short loc_180027E6F
0x180027e5f  mov     eax, 8
0x180027e64  jmp     short loc_180027E6F
0x180027e66  mov     eax, 10h
0x180027e6b  jmp     short loc_180027E6F
0x180027e6d  mov     eax, edi
0x180027e6f  mov     dword ptr [rsp+1B0h+var_190], eax
0x180027e73  mov     r9b, r8b
0x180027e76  lea     r8, [rbp+0B0h+var_4F]
0x180027e7a  lea     rdx, [rbp+0B0h+var_90]
0x180027e7e  lea     rcx, [rsp+1B0h+var_160]
0x180027e83  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x180027e88  mov     r12, [rax]
0x180027e8b  lea     rcx, [rbp+0B0h+var_90]
0x180027e8f  mov     [rsp+1B0h+var_138], rcx
0x180027e94  mov     eax, r12d
0x180027e97  sub     eax, ecx
0x180027e99  mov     [rsp+1B0h+var_16C], eax
0x180027e9d  cmp     [rsi+0Ah], dil
0x180027ea1  jz      short loc_180027EA9
0x180027ea3  inc     eax
0x180027ea5  mov     [rsp+1B0h+var_16C], eax
0x180027ea9  mov     r14d, 1
0x180027eaf  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180027eb3  jnz     short loc_180027EDC
0x180027eb5  lea     rcx, [rbp+0B0h+var_90]
0x180027eb9  lea     rdx, [rbp+0B0h+var_90]
0x180027ebd  cmp     rdx, r12
0x180027ec0  jz      short loc_180027EDC
0x180027ec2  mov     dl, [rcx]
0x180027ec4  lea     eax, [rdx-61h]
0x180027ec7  cmp     al, 19h
0x180027ec9  ja      short loc_180027ED0
0x180027ecb  sub     dl, 20h ; ' '
0x180027ece  mov     [rcx], dl
0x180027ed0  add     rcx, r14
0x180027ed3  cmp     rcx, r12
0x180027ed6  jnz     short loc_180027EC2
0x180027ed8  mov     eax, [rsp+1B0h+var_16C]
0x180027edc  mov     qword ptr [rbp+0B0h+var_130], r13
0x180027ee0  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180027ee4  cmp     [rsi+0Bh], r13b
0x180027ee8  jz      short loc_180027F69
0x180027eea  mov     cl, [rsi+8]
0x180027eed  cmp     cl, 42h ; 'B'
0x180027ef0  jz      short loc_180027F48
0x180027ef2  cmp     cl, 58h ; 'X'
0x180027ef5  jz      short loc_180027F3F
0x180027ef7  cmp     cl, 62h ; 'b'
0x180027efa  jz      short loc_180027F36
0x180027efc  cmp     cl, 6Fh ; 'o'
0x180027eff  jz      short loc_180027F0F
0x180027f01  cmp     cl, 78h ; 'x'
0x180027f04  jnz     short loc_180027F27
0x180027f06  lea     rcx, a0x; "0x"
0x180027f0d  jmp     short loc_180027F4F
0x180027f0f  cmp     [rsp+1B0h+var_180], r13b
0x180027f14  jz      short loc_180027F27
0x180027f16  lea     rcx, a0; "0"
0x180027f1d  mov     qword ptr [rsp+1B0h+var_160+8], r14
0x180027f22  mov     edi, r14d
0x180027f25  jmp     short loc_180027F54
0x180027f27  mov     qword ptr [rsp+1B0h+var_160], r13
0x180027f2c  mov     qword ptr [rsp+1B0h+var_160+8], r13
0x180027f31  mov     edi, r13d
0x180027f34  jmp     short loc_180027F59
0x180027f36  lea     rcx, a0b; "0b"
0x180027f3d  jmp     short loc_180027F4F
0x180027f3f  lea     rcx, a0x_0; "0X"
0x180027f46  jmp     short loc_180027F4F
0x180027f48  lea     rcx, a0b_0; "0B"
0x180027f4f  mov     qword ptr [rsp+1B0h+var_160+8], rdi
0x180027f54  mov     qword ptr [rsp+1B0h+var_160], rcx
0x180027f59  movaps  xmm0, [rsp+1B0h+var_160]
0x180027f5e  movdqa  [rbp+0B0h+var_130], xmm0
0x180027f63  add     eax, edi
0x180027f65  mov     [rsp+1B0h+var_16C], eax
0x180027f69  mov     [rsp+1B0h+var_140], r13d
0x180027f6e  xorps   xmm0, xmm0
0x180027f71  movups  [rbp+0B0h+var_D0], xmm0
0x180027f75  mov     [rbp+0B0h+var_C0], r13
0x180027f79  mov     [rbp+0B0h+var_B8], 0Fh
0x180027f81  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180027f85  cmp     [rsi+0Ch], r13b
0x180027f89  jz      loc_180028081
0x180027f8f  mov     rax, [rbp+0B0h+arg_20]
0x180027f96  test    rax, rax
0x180027f99  jz      short loc_180027FB2
0x180027f9b  mov     rcx, [rax+8]
0x180027f9f  mov     qword ptr [rsp+1B0h+var_160+8], rcx
0x180027fa4  mov     rax, [rcx]
0x180027fa7  mov     rax, [rax+8]
0x180027fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fb0  jmp     short loc_180027FC0
0x180027fb2  mov     cl, r14b
0x180027fb5  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180027fbb  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x180027fc0  lea     rcx, [rsp+1B0h+var_160]
0x180027fc5  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180027fca  mov     r8, rax
0x180027fcd  mov     rcx, [rax]
0x180027fd0  mov     rax, [rcx+28h]
0x180027fd4  lea     rdx, [rbp+0B0h+var_B0]
0x180027fd8  mov     rcx, r8
0x180027fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fe0  lea     rdx, [rbp+0B0h+var_B0]
0x180027fe4  lea     rcx, [rbp+0B0h+var_D0]
0x180027fe8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180027fed  lea     rcx, [rbp+0B0h+var_B0]
0x180027ff1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180027ff6  nop
0x180027ff7  mov     rcx, qword ptr [rsp+1B0h+var_160+8]
0x180027ffc  test    rcx, rcx
0x180027fff  jz      short loc_180028026
0x180028001  mov     rax, [rcx]
0x180028004  mov     rax, [rax+10h]
0x180028008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002800d  mov     r8, rax
0x180028010  test    rax, rax
0x180028013  jz      short loc_180028026
0x180028015  mov     rcx, [rax]
0x180028018  mov     rax, [rcx]
0x18002801b  mov     edx, r14d
0x18002801e  mov     rcx, r8
0x180028021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028026  lea     rax, [rbp+0B0h+var_D0]
0x18002802a  cmp     [rbp+0B0h+var_B8], 0Fh
0x18002802f  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180028034  mov     r10, [rbp+0B0h+var_C0]
0x180028038  mov     edx, r13d
0x18002803b  test    r10, r10
0x18002803e  jz      short loc_180028073
0x180028040  mov     r8, r12
0x180028043  sub     r8, [rsp+1B0h+var_138]
0x180028048  movsx   r9, byte ptr [rax]
0x18002804c  cmp     r8, r9
0x18002804f  jbe     short loc_180028073
0x180028051  lea     r11, [r10+rax]
0x180028055  movsx   rcx, r9b
0x180028059  sub     r8, rcx
0x18002805c  add     edx, r14d
0x18002805f  lea     rcx, [rax+1]
0x180028063  cmp     rcx, r11
0x180028066  cmovnz  rax, rcx
0x18002806a  movsx   r9, byte ptr [rax]
0x18002806e  cmp     r8, r9
0x180028071  ja      short loc_180028055
0x180028073  mov     [rsp+1B0h+var_140], edx
0x180028077  mov     eax, [rsp+1B0h+var_16C]
0x18002807b  add     eax, edx
0x18002807d  mov     [rsp+1B0h+var_16C], eax
0x180028081  cmp     [rsi+0Dh], r13b
0x180028085  jz      short loc_18002808D
0x180028087  cmp     [rsi+9], r13b
0x18002808b  jz      short loc_180028090
0x18002808d  mov     r14b, r13b
0x180028090  mov     [rsp+1B0h+var_170], r14b
0x180028095  mov     [rbp+0B0h+var_120], r12
0x180028099  mov     [rbp+0B0h+var_118], rsi
0x18002809d  lea     rcx, [rsp+1B0h+var_180]
0x1800280a2  mov     [rbp+0B0h+var_110], rcx
0x1800280a6  lea     rcx, [rbp+0B0h+var_130]
0x1800280aa  mov     [rbp+0B0h+var_108], rcx
0x1800280ae  lea     rcx, [rsp+1B0h+var_170]
0x1800280b3  mov     [rbp+0B0h+var_100], rcx
0x1800280b7  lea     rcx, [rsp+1B0h+var_16C]
0x1800280bc  mov     [rbp+0B0h+var_F8], rcx
0x1800280c0  lea     rcx, [rsp+1B0h+var_140]
0x1800280c5  mov     [rbp+0B0h+var_F0], rcx
0x1800280c9  lea     rcx, [rsp+1B0h+var_138]
0x1800280ce  mov     [rbp+0B0h+var_E8], rcx
0x1800280d2  lea     rcx, [rbp+0B0h+var_D0]
0x1800280d6  mov     [rbp+0B0h+var_E0], rcx
0x1800280da  lea     rcx, [rbp+0B0h+arg_20]
0x1800280e1  mov     [rbp+0B0h+var_D8], rcx
0x1800280e5  lea     rcx, [rbp+0B0h+var_120]
0x1800280e9  test    r14b, r14b
0x1800280ec  jz      short loc_1800280FB
0x1800280ee  mov     r8, rbx
0x1800280f1  mov     rdx, r15
0x1800280f4  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800280f9  jmp     short loc_180028112
0x1800280fb  mov     [rsp+1B0h+var_188], rcx
0x180028100  mov     r9, rsi
0x180028103  mov     r8d, eax
0x180028106  mov     rdx, rbx
0x180028109  mov     rcx, r15
0x18002810c  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@2@YA?AV12@V12@EU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@0@YA?AV10@0EU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180028111  nop
0x180028112  lea     rcx, [rbp+0B0h+var_D0]
0x180028116  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002811b  mov     rax, r15
0x18002811e  mov     rcx, [rbp+0B0h+var_40]
0x180028122  xor     rcx, rsp; StackCookie
0x180028125  call    __security_check_cookie
0x18002812a  mov     rbx, [rsp+1B0h+arg_8]
0x180028132  add     rsp, 180h
0x180028139  pop     r15
0x18002813b  pop     r14
0x18002813d  pop     r13
0x18002813f  pop     r12
0x180028141  pop     rdi
0x180028142  pop     rsi
0x180028143  pop     rbp
0x180028144  retn
0x180028145  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x18002814c  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

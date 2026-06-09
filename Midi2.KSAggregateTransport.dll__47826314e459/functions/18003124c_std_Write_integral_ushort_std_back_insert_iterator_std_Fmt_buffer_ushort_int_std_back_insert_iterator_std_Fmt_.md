# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x18003124c`
- end: `0x1800315ff`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002ff18`

## callees

- `0x180005020`
- `0x18002c1a4`
- `0x180030824`
- `0x18003124c`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180035064`
- `0x180040fac`
- `0x180043030`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031460`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031460`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,int>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int128 *a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  char *v11; // r12
  char *v12; // rcx
  unsigned int v13; // eax
  int v14; // edx
  char v15; // r14
  char v16; // cl
  const char *v17; // rcx
  struct std::locale::_Locimp *v18; // rdi
  __int64 v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64); // rax
  char *v21; // rax
  int v22; // edx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r9
  char *v25; // r11
  int v27; // [rsp+20h] [rbp-E0h]
  char v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  char *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+80h] [rbp-80h]
  _QWORD v36[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v39; // [rsp+F8h] [rbp-8h]
  _BYTE v40[32]; // [rsp+100h] [rbp+0h] BYREF
  char v41; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v42[64]; // [rsp+121h] [rbp+21h] BYREF
  char v43[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0xFFFF )
      std::_Throw_format_error("integral cannot be stored in wchar_t");
    *((_BYTE *)a4 + 11) = 0;
    v34 = *a4;
    v35 = *((_DWORD *)a4 + 4);
    std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a1,
      a2,
      a3,
      (unsigned int)&v34,
      a5);
    return a1;
  }
  v9 = 2;
  if ( !*((_BYTE *)a4 + 10) )
    *((_BYTE *)a4 + 10) = 2;
  if ( v8 != 66 )
  {
    if ( v8 == 88 )
    {
LABEL_13:
      v10 = 16;
      goto LABEL_15;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v10 = 8;
        goto LABEL_15;
      }
      if ( v8 != 120 )
      {
        v10 = 10;
        goto LABEL_15;
      }
      goto LABEL_13;
    }
  }
  v10 = 2;
LABEL_15:
  v27 = v10;
  v11 = *(char **)std::to_chars(&v34, &v41, v43, a3);
  v12 = &v41;
  v33 = &v41;
  v13 = (_DWORD)v11 - (unsigned int)&v41;
  v29 = v13;
  v14 = v31;
  if ( v31 < 0 )
  {
    v12 = v42;
    v33 = v42;
  }
  else if ( *((_BYTE *)a4 + 10) != 2 )
  {
    v29 = ++v13;
  }
  v15 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 && v12 != v11 )
  {
    do
    {
      if ( (unsigned __int8)(*v12 - 97) <= 0x19u )
        *v12 -= 32;
      ++v12;
    }
    while ( v12 != v11 );
    v13 = v29;
    v14 = v31;
  }
  v30 = 0u;
  if ( !*((_BYTE *)a4 + 11) )
    goto LABEL_41;
  v16 = *((_BYTE *)a4 + 8);
  switch ( v16 )
  {
    case 'B':
      v17 = "0B";
      goto LABEL_38;
    case 'X':
      v17 = "0X";
      goto LABEL_38;
    case 'b':
      v17 = "0b";
      goto LABEL_38;
    case 'o':
      if ( v14 )
      {
        v17 = "0";
        *((_QWORD *)&v30 + 1) = 1;
        v9 = 1;
LABEL_39:
        *(_QWORD *)&v30 = v17;
        goto LABEL_40;
      }
      break;
    case 'x':
      v17 = "0x";
LABEL_38:
      *((_QWORD *)&v30 + 1) = 2;
      goto LABEL_39;
  }
  v30 = 0u;
  v9 = 0;
LABEL_40:
  v13 += v9;
  v29 = v13;
LABEL_41:
  v32 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 15;
  LOBYTE(v37) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      v18 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v34 + 1) = v18;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 8LL))(v18);
    }
    else
    {
      v18 = std::locale::_Init(1);
      *((_QWORD *)&v34 + 1) = v18;
    }
    v19 = std::use_facet<std::numpunct<unsigned short>>(&v34);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v19 + 40LL))(v19, v40);
    std::string::operator=(&v37, v40);
    std::string::~string(v40);
    if ( v18 )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v20 )
        (**v20)(v20, 1);
    }
    v21 = (char *)&v37;
    if ( v39 > 0xF )
      v21 = (char *)v37;
    v22 = 0;
    if ( v38 )
    {
      v23 = v11 - v33;
      v24 = *v21;
      if ( v11 - v33 > v24 )
      {
        v25 = &v21[v38];
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
    v32 = v22;
    v13 = v22 + v29;
    v29 += v22;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v15 = 0;
  v28 = v15;
  v36[0] = v11;
  v36[1] = a4;
  v36[2] = &v31;
  v36[3] = &v30;
  v36[4] = &v28;
  v36[5] = &v29;
  v36[6] = &v32;
  v36[7] = &v33;
  v36[8] = &v37;
  v36[9] = &a5;
  if ( v15 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,int>'::`2'::_lambda_1_::operator()(
      v36,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__H_2_YA_AV12_V12_HU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__H_0_YA_AV10_0HU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v13,
      (_DWORD)a4,
      v27,
      (__int64)v36);
  std::string::~string(&v37);
  return a1;
}

```

## disassembly

```asm
0x18003124c  mov     [rsp-8+arg_8], rbx
0x180031251  push    rbp
0x180031252  push    rsi
0x180031253  push    rdi
0x180031254  push    r12
0x180031256  push    r13
0x180031258  push    r14
0x18003125a  push    r15
0x18003125c  lea     rbp, [rsp-80h]
0x180031261  sub     rsp, 180h
0x180031268  mov     rax, cs:__security_cookie
0x18003126f  xor     rax, rsp
0x180031272  mov     [rbp+0B0h+var_40], rax
0x180031276  mov     rsi, r9
0x180031279  mov     rbx, rdx
0x18003127c  mov     r15, rcx
0x18003127f  mov     [rsp+1B0h+var_160], r8d
0x180031284  xor     r13d, r13d
0x180031287  mov     al, [r9+8]
0x18003128b  cmp     al, 63h ; 'c'
0x18003128d  jnz     short loc_1800312CE
0x18003128f  cmp     r8d, 0FFFFh
0x180031296  ja      loc_1800315F2
0x18003129c  mov     [r9+0Bh], r13b
0x1800312a0  movaps  xmm0, xmmword ptr [r9]
0x1800312a4  movaps  [rsp+1B0h+var_140], xmm0
0x1800312a9  mov     ecx, [r9+10h]
0x1800312ad  mov     [rbp+0B0h+var_130], ecx
0x1800312b0  mov     rcx, [rbp+0B0h+arg_20]
0x1800312b7  mov     [rsp+1B0h+var_190], rcx
0x1800312bc  lea     r9, [rsp+1B0h+var_140]
0x1800312c1  mov     rcx, r15
0x1800312c4  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x1800312c9  jmp     loc_1800315C8
0x1800312ce  mov     edi, 2
0x1800312d3  cmp     [r9+0Ah], r13b
0x1800312d7  jnz     short loc_1800312DD
0x1800312d9  mov     [r9+0Ah], dil
0x1800312dd  cmp     al, 42h ; 'B'
0x1800312df  jz      short loc_180031306
0x1800312e1  cmp     al, 58h ; 'X'
0x1800312e3  jz      short loc_1800312FF
0x1800312e5  cmp     al, 62h ; 'b'
0x1800312e7  jz      short loc_180031306
0x1800312e9  cmp     al, 6Fh ; 'o'
0x1800312eb  jz      short loc_1800312F8
0x1800312ed  cmp     al, 78h ; 'x'
0x1800312ef  jz      short loc_1800312FF
0x1800312f1  mov     eax, 0Ah
0x1800312f6  jmp     short loc_180031308
0x1800312f8  mov     eax, 8
0x1800312fd  jmp     short loc_180031308
0x1800312ff  mov     eax, 10h
0x180031304  jmp     short loc_180031308
0x180031306  mov     eax, edi
0x180031308  mov     dword ptr [rsp+1B0h+var_190], eax
0x18003130c  mov     r9d, r8d
0x18003130f  lea     r8, [rbp+0B0h+var_4F]
0x180031313  lea     rdx, [rbp+0B0h+var_90]
0x180031317  lea     rcx, [rsp+1B0h+var_140]
0x18003131c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0HH@Z; std::to_chars(char * const,char * const,int,int)
0x180031321  mov     r12, [rax]
0x180031324  lea     rcx, [rbp+0B0h+var_90]
0x180031328  mov     [rsp+1B0h+var_150], rcx
0x18003132d  mov     eax, r12d
0x180031330  sub     eax, ecx
0x180031332  mov     [rsp+1B0h+var_17C], eax
0x180031336  mov     edx, [rsp+1B0h+var_160]
0x18003133a  test    edx, edx
0x18003133c  js      short loc_18003134C
0x18003133e  cmp     [rsi+0Ah], dil
0x180031342  jz      short loc_180031355
0x180031344  inc     eax
0x180031346  mov     [rsp+1B0h+var_17C], eax
0x18003134a  jmp     short loc_180031355
0x18003134c  lea     rcx, [rbp+0B0h+var_8F]
0x180031350  mov     [rsp+1B0h+var_150], rcx
0x180031355  mov     r14d, 1
0x18003135b  cmp     byte ptr [rsi+8], 58h ; 'X'
0x18003135f  jnz     short loc_180031384
0x180031361  cmp     rcx, r12
0x180031364  jz      short loc_180031384
0x180031366  mov     dl, [rcx]
0x180031368  lea     eax, [rdx-61h]
0x18003136b  cmp     al, 19h
0x18003136d  ja      short loc_180031374
0x18003136f  sub     dl, 20h ; ' '
0x180031372  mov     [rcx], dl
0x180031374  add     rcx, r14
0x180031377  cmp     rcx, r12
0x18003137a  jnz     short loc_180031366
0x18003137c  mov     eax, [rsp+1B0h+var_17C]
0x180031380  mov     edx, [rsp+1B0h+var_160]
0x180031384  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031389  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18003138e  cmp     [rsi+0Bh], r13b
0x180031392  jz      short loc_180031411
0x180031394  mov     cl, [rsi+8]
0x180031397  cmp     cl, 42h ; 'B'
0x18003139a  jz      short loc_1800313EF
0x18003139c  cmp     cl, 58h ; 'X'
0x18003139f  jz      short loc_1800313E6
0x1800313a1  cmp     cl, 62h ; 'b'
0x1800313a4  jz      short loc_1800313DD
0x1800313a6  cmp     cl, 6Fh ; 'o'
0x1800313a9  jz      short loc_1800313B9
0x1800313ab  cmp     cl, 78h ; 'x'
0x1800313ae  jnz     short loc_1800313CE
0x1800313b0  lea     rcx, a0x; "0x"
0x1800313b7  jmp     short loc_1800313F6
0x1800313b9  test    edx, edx
0x1800313bb  jz      short loc_1800313CE
0x1800313bd  lea     rcx, a0; "0"
0x1800313c4  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x1800313c9  mov     edi, r14d
0x1800313cc  jmp     short loc_1800313FB
0x1800313ce  mov     qword ptr [rsp+1B0h+var_170], r13
0x1800313d3  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x1800313d8  mov     edi, r13d
0x1800313db  jmp     short loc_180031400
0x1800313dd  lea     rcx, a0b; "0b"
0x1800313e4  jmp     short loc_1800313F6
0x1800313e6  lea     rcx, a0x_0; "0X"
0x1800313ed  jmp     short loc_1800313F6
0x1800313ef  lea     rcx, a0b_0; "0B"
0x1800313f6  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800313fb  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180031400  movaps  xmm0, [rsp+1B0h+var_170]
0x180031405  movdqa  [rsp+1B0h+var_170], xmm0
0x18003140b  add     eax, edi
0x18003140d  mov     [rsp+1B0h+var_17C], eax
0x180031411  mov     [rsp+1B0h+var_158], r13d
0x180031416  xorps   xmm0, xmm0
0x180031419  movups  [rbp+0B0h+var_D0], xmm0
0x18003141d  mov     [rbp+0B0h+var_C0], r13
0x180031421  mov     [rbp+0B0h+var_B8], 0Fh
0x180031429  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x18003142d  cmp     [rsi+0Ch], r13b
0x180031431  jz      loc_18003152D
0x180031437  mov     rax, [rbp+0B0h+arg_20]
0x18003143e  test    rax, rax
0x180031441  jz      short loc_18003145D
0x180031443  mov     rdi, [rax+8]
0x180031447  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x18003144c  mov     rax, [rdi]
0x18003144f  mov     rcx, rdi
0x180031452  mov     rax, [rax+8]
0x180031456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003145b  jmp     short loc_18003146E
0x18003145d  mov     cl, r14b
0x180031460  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180031466  mov     rdi, rax
0x180031469  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x18003146e  lea     rcx, [rsp+1B0h+var_140]
0x180031473  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180031478  mov     r8, rax
0x18003147b  mov     rcx, [rax]
0x18003147e  mov     rax, [rcx+28h]
0x180031482  lea     rdx, [rbp+0B0h+var_B0]
0x180031486  mov     rcx, r8
0x180031489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003148e  lea     rdx, [rbp+0B0h+var_B0]
0x180031492  lea     rcx, [rbp+0B0h+var_D0]
0x180031496  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003149b  lea     rcx, [rbp+0B0h+var_B0]
0x18003149f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800314a4  nop
0x1800314a5  test    rdi, rdi
0x1800314a8  jz      short loc_1800314D2
0x1800314aa  mov     rax, [rdi]
0x1800314ad  mov     rcx, rdi
0x1800314b0  mov     rax, [rax+10h]
0x1800314b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314b9  mov     r8, rax
0x1800314bc  test    rax, rax
0x1800314bf  jz      short loc_1800314D2
0x1800314c1  mov     rcx, [rax]
0x1800314c4  mov     rax, [rcx]
0x1800314c7  mov     edx, r14d
0x1800314ca  mov     rcx, r8
0x1800314cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314d2  lea     rax, [rbp+0B0h+var_D0]
0x1800314d6  cmp     [rbp+0B0h+var_B8], 0Fh
0x1800314db  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x1800314e0  mov     r10, [rbp+0B0h+var_C0]
0x1800314e4  mov     edx, r13d
0x1800314e7  test    r10, r10
0x1800314ea  jz      short loc_18003151F
0x1800314ec  mov     r8, r12
0x1800314ef  sub     r8, [rsp+1B0h+var_150]
0x1800314f4  movsx   r9, byte ptr [rax]
0x1800314f8  cmp     r8, r9
0x1800314fb  jbe     short loc_18003151F
0x1800314fd  lea     r11, [r10+rax]
0x180031501  movsx   rcx, r9b
0x180031505  sub     r8, rcx
0x180031508  add     edx, r14d
0x18003150b  lea     rcx, [rax+1]
0x18003150f  cmp     rcx, r11
0x180031512  cmovnz  rax, rcx
0x180031516  movsx   r9, byte ptr [rax]
0x18003151a  cmp     r8, r9
0x18003151d  ja      short loc_180031501
0x18003151f  mov     [rsp+1B0h+var_158], edx
0x180031523  mov     eax, [rsp+1B0h+var_17C]
0x180031527  add     eax, edx
0x180031529  mov     [rsp+1B0h+var_17C], eax
0x18003152d  cmp     [rsi+0Dh], r13b
0x180031531  jz      short loc_180031539
0x180031533  cmp     [rsi+9], r13b
0x180031537  jz      short loc_18003153C
0x180031539  mov     r14b, r13b
0x18003153c  mov     [rsp+1B0h+var_180], r14b
0x180031541  mov     [rbp+0B0h+var_120], r12
0x180031545  mov     [rbp+0B0h+var_118], rsi
0x180031549  lea     rcx, [rsp+1B0h+var_160]
0x18003154e  mov     [rbp+0B0h+var_110], rcx
0x180031552  lea     rcx, [rsp+1B0h+var_170]
0x180031557  mov     [rbp+0B0h+var_108], rcx
0x18003155b  lea     rcx, [rsp+1B0h+var_180]
0x180031560  mov     [rbp+0B0h+var_100], rcx
0x180031564  lea     rcx, [rsp+1B0h+var_17C]
0x180031569  mov     [rbp+0B0h+var_F8], rcx
0x18003156d  lea     rcx, [rsp+1B0h+var_158]
0x180031572  mov     [rbp+0B0h+var_F0], rcx
0x180031576  lea     rcx, [rsp+1B0h+var_150]
0x18003157b  mov     [rbp+0B0h+var_E8], rcx
0x18003157f  lea     rcx, [rbp+0B0h+var_D0]
0x180031583  mov     [rbp+0B0h+var_E0], rcx
0x180031587  lea     rcx, [rbp+0B0h+arg_20]
0x18003158e  mov     [rbp+0B0h+var_D8], rcx
0x180031592  lea     rcx, [rbp+0B0h+var_120]
0x180031596  test    r14b, r14b
0x180031599  jz      short loc_1800315A8
0x18003159b  mov     r8, rbx
0x18003159e  mov     rdx, r15
0x1800315a1  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@HU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x1800315a6  jmp     short loc_1800315BF
0x1800315a8  mov     [rsp+1B0h+var_188], rcx
0x1800315ad  mov     r9, rsi
0x1800315b0  mov     r8d, eax
0x1800315b3  mov     rdx, rbx
0x1800315b6  mov     rcx, r15
0x1800315b9  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@2@YA?AV12@V12@HU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@0@YA?AV10@0HU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800315be  nop
0x1800315bf  lea     rcx, [rbp+0B0h+var_D0]
0x1800315c3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800315c8  mov     rax, r15
0x1800315cb  mov     rcx, [rbp+0B0h+var_40]
0x1800315cf  xor     rcx, rsp; StackCookie
0x1800315d2  call    __security_check_cookie
0x1800315d7  mov     rbx, [rsp+1B0h+arg_8]
0x1800315df  add     rsp, 180h
0x1800315e6  pop     r15
0x1800315e8  pop     r14
0x1800315ea  pop     r13
0x1800315ec  pop     r12
0x1800315ee  pop     rdi
0x1800315ef  pop     rsi
0x1800315f0  pop     rbp
0x1800315f1  retn
0x1800315f2  lea     rcx, aIntegralCannot_0; "integral cannot be stored in wchar_t"
0x1800315f9  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

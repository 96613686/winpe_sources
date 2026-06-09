# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180052728`
- end: `0x180052ad9`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180051498`

## callees

- `0x180005020`
- `0x1800342a8`
- `0x180034450`
- `0x180040fac`
- `0x180043030`
- `0x18004e8bc`
- `0x180051e38`
- `0x180052728`
- `0x180053d44`
- `0x180054ab4`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18005293c`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18005293c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(
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
  __int64 v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rax
  char *v20; // rax
  int v21; // edx
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r9
  char *v24; // r11
  int v26; // [rsp+20h] [rbp-E0h]
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  char *v33; // [rsp+70h] [rbp-90h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v35[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v38; // [rsp+F8h] [rbp-8h]
  _BYTE v39[32]; // [rsp+100h] [rbp+0h] BYREF
  char v40; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v41[64]; // [rsp+121h] [rbp+21h] BYREF
  char v42[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 + 128 > 0xFF )
      std::_Throw_format_error("integral cannot be stored in char");
    *((_BYTE *)a4 + 11) = 0;
    v29 = *a4;
    v30 = *((_DWORD *)a4 + 4);
    std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, a3, (unsigned int)&v29, a5);
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
  v26 = v10;
  v11 = *(char **)std::to_chars(&v29, &v40, v42, a3);
  v12 = &v40;
  v33 = &v40;
  v13 = (_DWORD)v11 - (unsigned int)&v40;
  v28 = v13;
  v14 = v31;
  if ( v31 < 0 )
  {
    v12 = v41;
    v33 = v41;
  }
  else if ( *((_BYTE *)a4 + 10) != 2 )
  {
    v28 = ++v13;
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
    v13 = v28;
    v14 = v31;
  }
  v34 = 0u;
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
        *((_QWORD *)&v29 + 1) = 1;
        v9 = 1;
LABEL_39:
        *(_QWORD *)&v29 = v17;
        goto LABEL_40;
      }
      break;
    case 'x':
      v17 = "0x";
LABEL_38:
      *((_QWORD *)&v29 + 1) = 2;
      goto LABEL_39;
  }
  v29 = 0u;
  v9 = 0;
LABEL_40:
  v34 = v29;
  v13 += v9;
  v28 = v13;
LABEL_41:
  v32 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 15;
  LOBYTE(v36) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      *((_QWORD *)&v29 + 1) = *(_QWORD *)(a5 + 8);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v29 + 1) + 8LL))(*((_QWORD *)&v29 + 1));
    }
    else
    {
      *((_QWORD *)&v29 + 1) = std::locale::_Init(1);
    }
    v18 = std::use_facet<std::numpunct<char>>(&v29);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 40LL))(v18, v39);
    std::string::operator=(&v36, v39);
    std::string::~string(v39);
    if ( *((_QWORD *)&v29 + 1) )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v29 + 1) + 16LL))(*((_QWORD *)&v29 + 1));
      if ( v19 )
        (**v19)(v19, 1);
    }
    v20 = (char *)&v36;
    if ( v38 > 0xF )
      v20 = (char *)v36;
    v21 = 0;
    if ( v37 )
    {
      v22 = v11 - v33;
      v23 = *v20;
      if ( v11 - v33 > v23 )
      {
        v24 = &v20[v37];
        do
        {
          v22 -= (char)v23;
          ++v21;
          if ( v20 + 1 != v24 )
            ++v20;
          v23 = *v20;
        }
        while ( v22 > v23 );
      }
    }
    v32 = v21;
    v13 = v21 + v28;
    v28 += v21;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v15 = 0;
  v27 = v15;
  v35[0] = v11;
  v35[1] = a4;
  v35[2] = &v31;
  v35[3] = &v34;
  v35[4] = &v27;
  v35[5] = &v28;
  v35[6] = &v32;
  v35[7] = &v33;
  v35[8] = &v36;
  v35[9] = &a5;
  if ( v15 )
    `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>'::`2'::_lambda_1_::operator()(
      v35,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_D_std___std__U___Basic_format_specs_D_2_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__H_2_YA_AV12_V12_HU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_D_std___0_V10_HAEBU___Basic_format_specs_D_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__H_0_YA_AV10_0HU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v13,
      (_DWORD)a4,
      v26,
      (__int64)v35);
  std::string::~string(&v36);
  return a1;
}

```

## disassembly

```asm
0x180052728  mov     [rsp-8+arg_8], rbx
0x18005272d  push    rbp
0x18005272e  push    rsi
0x18005272f  push    rdi
0x180052730  push    r12
0x180052732  push    r13
0x180052734  push    r14
0x180052736  push    r15
0x180052738  lea     rbp, [rsp-80h]
0x18005273d  sub     rsp, 180h
0x180052744  mov     rax, cs:__security_cookie
0x18005274b  xor     rax, rsp
0x18005274e  mov     [rbp+0B0h+var_40], rax
0x180052752  mov     rsi, r9
0x180052755  mov     rbx, rdx
0x180052758  mov     r15, rcx
0x18005275b  mov     [rsp+1B0h+var_150], r8d
0x180052760  xor     r13d, r13d
0x180052763  mov     al, [r9+8]
0x180052767  cmp     al, 63h ; 'c'
0x180052769  jnz     short loc_1800527B0
0x18005276b  lea     eax, [r8+80h]
0x180052772  cmp     eax, 0FFh
0x180052777  ja      loc_180052ACC
0x18005277d  mov     [r9+0Bh], r13b
0x180052781  movaps  xmm0, xmmword ptr [r9]
0x180052785  movaps  [rsp+1B0h+var_170], xmm0
0x18005278a  mov     ecx, [r9+10h]
0x18005278e  mov     [rsp+1B0h+var_160], ecx
0x180052792  mov     rcx, [rbp+0B0h+arg_20]
0x180052799  mov     [rsp+1B0h+var_190], rcx
0x18005279e  lea     r9, [rsp+1B0h+var_170]
0x1800527a3  mov     rcx, r15
0x1800527a6  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x1800527ab  jmp     loc_180052AA2
0x1800527b0  mov     edi, 2
0x1800527b5  cmp     [r9+0Ah], r13b
0x1800527b9  jnz     short loc_1800527BF
0x1800527bb  mov     [r9+0Ah], dil
0x1800527bf  cmp     al, 42h ; 'B'
0x1800527c1  jz      short loc_1800527E8
0x1800527c3  cmp     al, 58h ; 'X'
0x1800527c5  jz      short loc_1800527E1
0x1800527c7  cmp     al, 62h ; 'b'
0x1800527c9  jz      short loc_1800527E8
0x1800527cb  cmp     al, 6Fh ; 'o'
0x1800527cd  jz      short loc_1800527DA
0x1800527cf  cmp     al, 78h ; 'x'
0x1800527d1  jz      short loc_1800527E1
0x1800527d3  mov     eax, 0Ah
0x1800527d8  jmp     short loc_1800527EA
0x1800527da  mov     eax, 8
0x1800527df  jmp     short loc_1800527EA
0x1800527e1  mov     eax, 10h
0x1800527e6  jmp     short loc_1800527EA
0x1800527e8  mov     eax, edi
0x1800527ea  mov     dword ptr [rsp+1B0h+var_190], eax
0x1800527ee  mov     r9d, r8d
0x1800527f1  lea     r8, [rbp+0B0h+var_4F]
0x1800527f5  lea     rdx, [rbp+0B0h+var_90]
0x1800527f9  lea     rcx, [rsp+1B0h+var_170]
0x1800527fe  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0HH@Z; std::to_chars(char * const,char * const,int,int)
0x180052803  mov     r12, [rax]
0x180052806  lea     rcx, [rbp+0B0h+var_90]
0x18005280a  mov     [rsp+1B0h+var_140], rcx
0x18005280f  mov     eax, r12d
0x180052812  sub     eax, ecx
0x180052814  mov     [rsp+1B0h+var_17C], eax
0x180052818  mov     edx, [rsp+1B0h+var_150]
0x18005281c  test    edx, edx
0x18005281e  js      short loc_18005282E
0x180052820  cmp     [rsi+0Ah], dil
0x180052824  jz      short loc_180052837
0x180052826  inc     eax
0x180052828  mov     [rsp+1B0h+var_17C], eax
0x18005282c  jmp     short loc_180052837
0x18005282e  lea     rcx, [rbp+0B0h+var_8F]
0x180052832  mov     [rsp+1B0h+var_140], rcx
0x180052837  mov     r14d, 1
0x18005283d  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180052841  jnz     short loc_180052866
0x180052843  cmp     rcx, r12
0x180052846  jz      short loc_180052866
0x180052848  mov     dl, [rcx]
0x18005284a  lea     eax, [rdx-61h]
0x18005284d  cmp     al, 19h
0x18005284f  ja      short loc_180052856
0x180052851  sub     dl, 20h ; ' '
0x180052854  mov     [rcx], dl
0x180052856  add     rcx, r14
0x180052859  cmp     rcx, r12
0x18005285c  jnz     short loc_180052848
0x18005285e  mov     eax, [rsp+1B0h+var_17C]
0x180052862  mov     edx, [rsp+1B0h+var_150]
0x180052866  mov     qword ptr [rbp+0B0h+var_130], r13
0x18005286a  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x18005286e  cmp     [rsi+0Bh], r13b
0x180052872  jz      short loc_1800528F0
0x180052874  mov     cl, [rsi+8]
0x180052877  cmp     cl, 42h ; 'B'
0x18005287a  jz      short loc_1800528CF
0x18005287c  cmp     cl, 58h ; 'X'
0x18005287f  jz      short loc_1800528C6
0x180052881  cmp     cl, 62h ; 'b'
0x180052884  jz      short loc_1800528BD
0x180052886  cmp     cl, 6Fh ; 'o'
0x180052889  jz      short loc_180052899
0x18005288b  cmp     cl, 78h ; 'x'
0x18005288e  jnz     short loc_1800528AE
0x180052890  lea     rcx, a0x; "0x"
0x180052897  jmp     short loc_1800528D6
0x180052899  test    edx, edx
0x18005289b  jz      short loc_1800528AE
0x18005289d  lea     rcx, a0; "0"
0x1800528a4  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x1800528a9  mov     edi, r14d
0x1800528ac  jmp     short loc_1800528DB
0x1800528ae  mov     qword ptr [rsp+1B0h+var_170], r13
0x1800528b3  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x1800528b8  mov     edi, r13d
0x1800528bb  jmp     short loc_1800528E0
0x1800528bd  lea     rcx, a0b; "0b"
0x1800528c4  jmp     short loc_1800528D6
0x1800528c6  lea     rcx, a0x_0; "0X"
0x1800528cd  jmp     short loc_1800528D6
0x1800528cf  lea     rcx, a0b_0; "0B"
0x1800528d6  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800528db  mov     qword ptr [rsp+1B0h+var_170], rcx
0x1800528e0  movaps  xmm0, [rsp+1B0h+var_170]
0x1800528e5  movdqa  [rbp+0B0h+var_130], xmm0
0x1800528ea  add     eax, edi
0x1800528ec  mov     [rsp+1B0h+var_17C], eax
0x1800528f0  mov     [rsp+1B0h+var_148], r13d
0x1800528f5  xorps   xmm0, xmm0
0x1800528f8  movups  [rbp+0B0h+var_D0], xmm0
0x1800528fc  mov     [rbp+0B0h+var_C0], r13
0x180052900  mov     [rbp+0B0h+var_B8], 0Fh
0x180052908  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x18005290c  cmp     [rsi+0Ch], r13b
0x180052910  jz      loc_180052A08
0x180052916  mov     rax, [rbp+0B0h+arg_20]
0x18005291d  test    rax, rax
0x180052920  jz      short loc_180052939
0x180052922  mov     rcx, [rax+8]
0x180052926  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x18005292b  mov     rax, [rcx]
0x18005292e  mov     rax, [rax+8]
0x180052932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052937  jmp     short loc_180052947
0x180052939  mov     cl, r14b
0x18005293c  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180052942  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180052947  lea     rcx, [rsp+1B0h+var_170]
0x18005294c  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180052951  mov     r8, rax
0x180052954  mov     rcx, [rax]
0x180052957  mov     rax, [rcx+28h]
0x18005295b  lea     rdx, [rbp+0B0h+var_B0]
0x18005295f  mov     rcx, r8
0x180052962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052967  lea     rdx, [rbp+0B0h+var_B0]
0x18005296b  lea     rcx, [rbp+0B0h+var_D0]
0x18005296f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180052974  lea     rcx, [rbp+0B0h+var_B0]
0x180052978  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005297d  nop
0x18005297e  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180052983  test    rcx, rcx
0x180052986  jz      short loc_1800529AD
0x180052988  mov     rax, [rcx]
0x18005298b  mov     rax, [rax+10h]
0x18005298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052994  mov     r8, rax
0x180052997  test    rax, rax
0x18005299a  jz      short loc_1800529AD
0x18005299c  mov     rcx, [rax]
0x18005299f  mov     rax, [rcx]
0x1800529a2  mov     edx, r14d
0x1800529a5  mov     rcx, r8
0x1800529a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529ad  lea     rax, [rbp+0B0h+var_D0]
0x1800529b1  cmp     [rbp+0B0h+var_B8], 0Fh
0x1800529b6  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x1800529bb  mov     r10, [rbp+0B0h+var_C0]
0x1800529bf  mov     edx, r13d
0x1800529c2  test    r10, r10
0x1800529c5  jz      short loc_1800529FA
0x1800529c7  mov     r8, r12
0x1800529ca  sub     r8, [rsp+1B0h+var_140]
0x1800529cf  movsx   r9, byte ptr [rax]
0x1800529d3  cmp     r8, r9
0x1800529d6  jbe     short loc_1800529FA
0x1800529d8  lea     r11, [r10+rax]
0x1800529dc  movsx   rcx, r9b
0x1800529e0  sub     r8, rcx
0x1800529e3  add     edx, r14d
0x1800529e6  lea     rcx, [rax+1]
0x1800529ea  cmp     rcx, r11
0x1800529ed  cmovnz  rax, rcx
0x1800529f1  movsx   r9, byte ptr [rax]
0x1800529f5  cmp     r8, r9
0x1800529f8  ja      short loc_1800529DC
0x1800529fa  mov     [rsp+1B0h+var_148], edx
0x1800529fe  mov     eax, [rsp+1B0h+var_17C]
0x180052a02  add     eax, edx
0x180052a04  mov     [rsp+1B0h+var_17C], eax
0x180052a08  cmp     [rsi+0Dh], r13b
0x180052a0c  jz      short loc_180052A14
0x180052a0e  cmp     [rsi+9], r13b
0x180052a12  jz      short loc_180052A17
0x180052a14  mov     r14b, r13b
0x180052a17  mov     [rsp+1B0h+var_180], r14b
0x180052a1c  mov     [rbp+0B0h+var_120], r12
0x180052a20  mov     [rbp+0B0h+var_118], rsi
0x180052a24  lea     rcx, [rsp+1B0h+var_150]
0x180052a29  mov     [rbp+0B0h+var_110], rcx
0x180052a2d  lea     rcx, [rbp+0B0h+var_130]
0x180052a31  mov     [rbp+0B0h+var_108], rcx
0x180052a35  lea     rcx, [rsp+1B0h+var_180]
0x180052a3a  mov     [rbp+0B0h+var_100], rcx
0x180052a3e  lea     rcx, [rsp+1B0h+var_17C]
0x180052a43  mov     [rbp+0B0h+var_F8], rcx
0x180052a47  lea     rcx, [rsp+1B0h+var_148]
0x180052a4c  mov     [rbp+0B0h+var_F0], rcx
0x180052a50  lea     rcx, [rsp+1B0h+var_140]
0x180052a55  mov     [rbp+0B0h+var_E8], rcx
0x180052a59  lea     rcx, [rbp+0B0h+var_D0]
0x180052a5d  mov     [rbp+0B0h+var_E0], rcx
0x180052a61  lea     rcx, [rbp+0B0h+arg_20]
0x180052a68  mov     [rbp+0B0h+var_D8], rcx
0x180052a6c  lea     rcx, [rbp+0B0h+var_120]
0x180052a70  test    r14b, r14b
0x180052a73  jz      short loc_180052A82
0x180052a75  mov     r8, rbx
0x180052a78  mov     rdx, r15
0x180052a7b  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180052a80  jmp     short loc_180052A99
0x180052a82  mov     [rsp+1B0h+var_188], rcx
0x180052a87  mov     r9, rsi
0x180052a8a  mov     r8d, eax
0x180052a8d  mov     rdx, rbx
0x180052a90  mov     rcx, r15
0x180052a93  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@2@YA?AV12@V12@HU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@0@YA?AV10@0HU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180052a98  nop
0x180052a99  lea     rcx, [rbp+0B0h+var_D0]
0x180052a9d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180052aa2  mov     rax, r15
0x180052aa5  mov     rcx, [rbp+0B0h+var_40]
0x180052aa9  xor     rcx, rsp; StackCookie
0x180052aac  call    __security_check_cookie
0x180052ab1  mov     rbx, [rsp+1B0h+arg_8]
0x180052ab9  add     rsp, 180h
0x180052ac0  pop     r15
0x180052ac2  pop     r14
0x180052ac4  pop     r13
0x180052ac6  pop     r12
0x180052ac8  pop     rdi
0x180052ac9  pop     rsi
0x180052aca  pop     rbp
0x180052acb  retn
0x180052acc  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180052ad3  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

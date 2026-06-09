# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180053244`
- end: `0x1800535e1`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_KU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
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
- `0x180043734`
- `0x18004e8bc`
- `0x180051f68`
- `0x180053244`
- `0x180053d44`
- `0x180054c5c`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180053444`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180053444`

## pseudocode

```c
__int64 __fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int128 *a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  _BYTE *v11; // r12
  unsigned int v12; // eax
  char v13; // r14
  _BYTE *v14; // rcx
  char v15; // cl
  const char *v16; // rcx
  __int64 v17; // rax
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  char *v19; // rax
  int v20; // edx
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // r9
  char *v23; // r11
  int v25; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v32; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v34[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v36; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v37; // [rsp+F8h] [rbp-8h]
  _BYTE v38[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v39[65]; // [rsp+120h] [rbp+20h] BYREF
  char v40[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0x7F )
      std::_Throw_format_error("integral cannot be stored in char");
    *((_BYTE *)a4 + 11) = 0;
    v28 = *a4;
    v29 = *((_DWORD *)a4 + 4);
    std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, a3, (unsigned int)&v28, a5);
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
  v25 = v10;
  v11 = *(_BYTE **)std::to_chars(&v28, v39, v40, a3);
  v32 = v39;
  v12 = (_DWORD)v11 - (unsigned int)v39;
  v27 = v12;
  if ( *((_BYTE *)a4 + 10) != 2 )
    v27 = ++v12;
  v13 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 )
  {
    v14 = v39;
    if ( v39 != v11 )
    {
      do
      {
        if ( (unsigned __int8)(*v14 - 97) <= 0x19u )
          *v14 -= 32;
        ++v14;
      }
      while ( v14 != v11 );
      v12 = v27;
    }
  }
  v33 = 0u;
  if ( !*((_BYTE *)a4 + 11) )
    goto LABEL_39;
  v15 = *((_BYTE *)a4 + 8);
  switch ( v15 )
  {
    case 'B':
      v16 = "0B";
      goto LABEL_36;
    case 'X':
      v16 = "0X";
      goto LABEL_36;
    case 'b':
      v16 = "0b";
      goto LABEL_36;
    case 'o':
      if ( v31 )
      {
        v16 = "0";
        *((_QWORD *)&v28 + 1) = 1;
        v9 = 1;
LABEL_37:
        *(_QWORD *)&v28 = v16;
        goto LABEL_38;
      }
      break;
    case 'x':
      v16 = "0x";
LABEL_36:
      *((_QWORD *)&v28 + 1) = 2;
      goto LABEL_37;
  }
  v28 = 0u;
  v9 = 0;
LABEL_38:
  v33 = v28;
  v12 += v9;
  v27 = v12;
LABEL_39:
  v30 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 15;
  LOBYTE(v35) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      *((_QWORD *)&v28 + 1) = *(_QWORD *)(a5 + 8);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v28 + 1) + 8LL))(*((_QWORD *)&v28 + 1));
    }
    else
    {
      *((_QWORD *)&v28 + 1) = std::locale::_Init(1);
    }
    v17 = std::use_facet<std::numpunct<char>>(&v28);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 40LL))(v17, v38);
    std::string::operator=(&v35, v38);
    std::string::~string(v38);
    if ( *((_QWORD *)&v28 + 1) )
    {
      v18 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v28 + 1) + 16LL))(*((_QWORD *)&v28 + 1));
      if ( v18 )
        (**v18)(v18, 1);
    }
    v19 = (char *)&v35;
    if ( v37 > 0xF )
      v19 = (char *)v35;
    v20 = 0;
    if ( v36 )
    {
      v21 = v11 - v32;
      v22 = *v19;
      if ( v11 - v32 > v22 )
      {
        v23 = &v19[v36];
        do
        {
          v21 -= (char)v22;
          ++v20;
          if ( v19 + 1 != v23 )
            ++v19;
          v22 = *v19;
        }
        while ( v21 > v22 );
      }
    }
    v30 = v20;
    v12 = v20 + v27;
    v27 += v20;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v13 = 0;
  v26 = v13;
  v34[0] = v11;
  v34[1] = a4;
  v34[2] = &v31;
  v34[3] = &v33;
  v34[4] = &v26;
  v34[5] = &v27;
  v34[6] = &v30;
  v34[7] = &v32;
  v34[8] = &v35;
  v34[9] = &a5;
  if ( v13 )
    `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
      v34,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_D_std___std__U___Basic_format_specs_D_2_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__I_2_YA_AV12_V12_IU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_D_std___0_V10_HAEBU___Basic_format_specs_D_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std__I_0_YA_AV10_0IU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v12,
      (_DWORD)a4,
      v25,
      (__int64)v34);
  std::string::~string(&v35);
  return a1;
}

```

## disassembly

```asm
0x180053244  mov     [rsp-8+arg_8], rbx
0x180053249  push    rbp
0x18005324a  push    rsi
0x18005324b  push    rdi
0x18005324c  push    r12
0x18005324e  push    r13
0x180053250  push    r14
0x180053252  push    r15
0x180053254  lea     rbp, [rsp-80h]
0x180053259  sub     rsp, 180h
0x180053260  mov     rax, cs:__security_cookie
0x180053267  xor     rax, rsp
0x18005326a  mov     [rbp+0B0h+var_40], rax
0x18005326e  mov     rsi, r9
0x180053271  mov     rbx, rdx
0x180053274  mov     r15, rcx
0x180053277  mov     [rsp+1B0h+var_148], r8
0x18005327c  xor     r13d, r13d
0x18005327f  mov     al, [r9+8]
0x180053283  cmp     al, 63h ; 'c'
0x180053285  jnz     short loc_1800532C4
0x180053287  cmp     r8, 7Fh
0x18005328b  ja      loc_1800535D4
0x180053291  mov     [r9+0Bh], r13b
0x180053295  movaps  xmm0, xmmword ptr [r9]
0x180053299  movaps  [rsp+1B0h+var_170], xmm0
0x18005329e  mov     ecx, [r9+10h]
0x1800532a2  mov     [rsp+1B0h+var_160], ecx
0x1800532a6  mov     rcx, [rbp+0B0h+arg_20]
0x1800532ad  mov     [rsp+1B0h+var_190], rcx
0x1800532b2  lea     r9, [rsp+1B0h+var_170]
0x1800532b7  mov     rcx, r15
0x1800532ba  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x1800532bf  jmp     loc_1800535AA
0x1800532c4  mov     edi, 2
0x1800532c9  cmp     [r9+0Ah], r13b
0x1800532cd  jnz     short loc_1800532D3
0x1800532cf  mov     [r9+0Ah], dil
0x1800532d3  cmp     al, 42h ; 'B'
0x1800532d5  jz      short loc_1800532FC
0x1800532d7  cmp     al, 58h ; 'X'
0x1800532d9  jz      short loc_1800532F5
0x1800532db  cmp     al, 62h ; 'b'
0x1800532dd  jz      short loc_1800532FC
0x1800532df  cmp     al, 6Fh ; 'o'
0x1800532e1  jz      short loc_1800532EE
0x1800532e3  cmp     al, 78h ; 'x'
0x1800532e5  jz      short loc_1800532F5
0x1800532e7  mov     eax, 0Ah
0x1800532ec  jmp     short loc_1800532FE
0x1800532ee  mov     eax, 8
0x1800532f3  jmp     short loc_1800532FE
0x1800532f5  mov     eax, 10h
0x1800532fa  jmp     short loc_1800532FE
0x1800532fc  mov     eax, edi
0x1800532fe  mov     dword ptr [rsp+1B0h+var_190], eax
0x180053302  mov     r9, r8
0x180053305  lea     r8, [rbp+0B0h+var_4F]
0x180053309  lea     rdx, [rbp+0B0h+var_90]
0x18005330d  lea     rcx, [rsp+1B0h+var_170]
0x180053312  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0_KH@Z; std::to_chars(char * const,char * const,unsigned __int64,int)
0x180053317  mov     r12, [rax]
0x18005331a  lea     rcx, [rbp+0B0h+var_90]
0x18005331e  mov     [rsp+1B0h+var_140], rcx
0x180053323  mov     eax, r12d
0x180053326  sub     eax, ecx
0x180053328  mov     [rsp+1B0h+var_17C], eax
0x18005332c  cmp     [rsi+0Ah], dil
0x180053330  jz      short loc_180053338
0x180053332  inc     eax
0x180053334  mov     [rsp+1B0h+var_17C], eax
0x180053338  mov     r14d, 1
0x18005333e  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180053342  jnz     short loc_18005336B
0x180053344  lea     rcx, [rbp+0B0h+var_90]
0x180053348  lea     rdx, [rbp+0B0h+var_90]
0x18005334c  cmp     rdx, r12
0x18005334f  jz      short loc_18005336B
0x180053351  mov     dl, [rcx]
0x180053353  lea     eax, [rdx-61h]
0x180053356  cmp     al, 19h
0x180053358  ja      short loc_18005335F
0x18005335a  sub     dl, 20h ; ' '
0x18005335d  mov     [rcx], dl
0x18005335f  add     rcx, r14
0x180053362  cmp     rcx, r12
0x180053365  jnz     short loc_180053351
0x180053367  mov     eax, [rsp+1B0h+var_17C]
0x18005336b  mov     qword ptr [rbp+0B0h+var_130], r13
0x18005336f  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180053373  cmp     [rsi+0Bh], r13b
0x180053377  jz      short loc_1800533F8
0x180053379  mov     cl, [rsi+8]
0x18005337c  cmp     cl, 42h ; 'B'
0x18005337f  jz      short loc_1800533D7
0x180053381  cmp     cl, 58h ; 'X'
0x180053384  jz      short loc_1800533CE
0x180053386  cmp     cl, 62h ; 'b'
0x180053389  jz      short loc_1800533C5
0x18005338b  cmp     cl, 6Fh ; 'o'
0x18005338e  jz      short loc_18005339E
0x180053390  cmp     cl, 78h ; 'x'
0x180053393  jnz     short loc_1800533B6
0x180053395  lea     rcx, a0x; "0x"
0x18005339c  jmp     short loc_1800533DE
0x18005339e  cmp     [rsp+1B0h+var_148], r13
0x1800533a3  jz      short loc_1800533B6
0x1800533a5  lea     rcx, a0; "0"
0x1800533ac  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x1800533b1  mov     edi, r14d
0x1800533b4  jmp     short loc_1800533E3
0x1800533b6  mov     qword ptr [rsp+1B0h+var_170], r13
0x1800533bb  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x1800533c0  mov     edi, r13d
0x1800533c3  jmp     short loc_1800533E8
0x1800533c5  lea     rcx, a0b; "0b"
0x1800533cc  jmp     short loc_1800533DE
0x1800533ce  lea     rcx, a0x_0; "0X"
0x1800533d5  jmp     short loc_1800533DE
0x1800533d7  lea     rcx, a0b_0; "0B"
0x1800533de  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800533e3  mov     qword ptr [rsp+1B0h+var_170], rcx
0x1800533e8  movaps  xmm0, [rsp+1B0h+var_170]
0x1800533ed  movdqa  [rbp+0B0h+var_130], xmm0
0x1800533f2  add     eax, edi
0x1800533f4  mov     [rsp+1B0h+var_17C], eax
0x1800533f8  mov     [rsp+1B0h+var_150], r13d
0x1800533fd  xorps   xmm0, xmm0
0x180053400  movups  [rbp+0B0h+var_D0], xmm0
0x180053404  mov     [rbp+0B0h+var_C0], r13
0x180053408  mov     [rbp+0B0h+var_B8], 0Fh
0x180053410  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180053414  cmp     [rsi+0Ch], r13b
0x180053418  jz      loc_180053510
0x18005341e  mov     rax, [rbp+0B0h+arg_20]
0x180053425  test    rax, rax
0x180053428  jz      short loc_180053441
0x18005342a  mov     rcx, [rax+8]
0x18005342e  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x180053433  mov     rax, [rcx]
0x180053436  mov     rax, [rax+8]
0x18005343a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005343f  jmp     short loc_18005344F
0x180053441  mov     cl, r14b
0x180053444  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18005344a  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x18005344f  lea     rcx, [rsp+1B0h+var_170]
0x180053454  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180053459  mov     r8, rax
0x18005345c  mov     rcx, [rax]
0x18005345f  mov     rax, [rcx+28h]
0x180053463  lea     rdx, [rbp+0B0h+var_B0]
0x180053467  mov     rcx, r8
0x18005346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005346f  lea     rdx, [rbp+0B0h+var_B0]
0x180053473  lea     rcx, [rbp+0B0h+var_D0]
0x180053477  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18005347c  lea     rcx, [rbp+0B0h+var_B0]
0x180053480  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180053485  nop
0x180053486  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x18005348b  test    rcx, rcx
0x18005348e  jz      short loc_1800534B5
0x180053490  mov     rax, [rcx]
0x180053493  mov     rax, [rax+10h]
0x180053497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005349c  mov     r8, rax
0x18005349f  test    rax, rax
0x1800534a2  jz      short loc_1800534B5
0x1800534a4  mov     rcx, [rax]
0x1800534a7  mov     rax, [rcx]
0x1800534aa  mov     edx, r14d
0x1800534ad  mov     rcx, r8
0x1800534b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534b5  lea     rax, [rbp+0B0h+var_D0]
0x1800534b9  cmp     [rbp+0B0h+var_B8], 0Fh
0x1800534be  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x1800534c3  mov     r10, [rbp+0B0h+var_C0]
0x1800534c7  mov     edx, r13d
0x1800534ca  test    r10, r10
0x1800534cd  jz      short loc_180053502
0x1800534cf  mov     r8, r12
0x1800534d2  sub     r8, [rsp+1B0h+var_140]
0x1800534d7  movsx   r9, byte ptr [rax]
0x1800534db  cmp     r8, r9
0x1800534de  jbe     short loc_180053502
0x1800534e0  lea     r11, [r10+rax]
0x1800534e4  movsx   rcx, r9b
0x1800534e8  sub     r8, rcx
0x1800534eb  add     edx, r14d
0x1800534ee  lea     rcx, [rax+1]
0x1800534f2  cmp     rcx, r11
0x1800534f5  cmovnz  rax, rcx
0x1800534f9  movsx   r9, byte ptr [rax]
0x1800534fd  cmp     r8, r9
0x180053500  ja      short loc_1800534E4
0x180053502  mov     [rsp+1B0h+var_150], edx
0x180053506  mov     eax, [rsp+1B0h+var_17C]
0x18005350a  add     eax, edx
0x18005350c  mov     [rsp+1B0h+var_17C], eax
0x180053510  cmp     [rsi+0Dh], r13b
0x180053514  jz      short loc_18005351C
0x180053516  cmp     [rsi+9], r13b
0x18005351a  jz      short loc_18005351F
0x18005351c  mov     r14b, r13b
0x18005351f  mov     [rsp+1B0h+var_180], r14b
0x180053524  mov     [rbp+0B0h+var_120], r12
0x180053528  mov     [rbp+0B0h+var_118], rsi
0x18005352c  lea     rcx, [rsp+1B0h+var_148]
0x180053531  mov     [rbp+0B0h+var_110], rcx
0x180053535  lea     rcx, [rbp+0B0h+var_130]
0x180053539  mov     [rbp+0B0h+var_108], rcx
0x18005353d  lea     rcx, [rsp+1B0h+var_180]
0x180053542  mov     [rbp+0B0h+var_100], rcx
0x180053546  lea     rcx, [rsp+1B0h+var_17C]
0x18005354b  mov     [rbp+0B0h+var_F8], rcx
0x18005354f  lea     rcx, [rsp+1B0h+var_150]
0x180053554  mov     [rbp+0B0h+var_F0], rcx
0x180053558  lea     rcx, [rsp+1B0h+var_140]
0x18005355d  mov     [rbp+0B0h+var_E8], rcx
0x180053561  lea     rcx, [rbp+0B0h+var_D0]
0x180053565  mov     [rbp+0B0h+var_E0], rcx
0x180053569  lea     rcx, [rbp+0B0h+arg_20]
0x180053570  mov     [rbp+0B0h+var_D8], rcx
0x180053574  lea     rcx, [rbp+0B0h+var_120]
0x180053578  test    r14b, r14b
0x18005357b  jz      short loc_18005358A
0x18005357d  mov     r8, rbx
0x180053580  mov     rdx, r15
0x180053583  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180053588  jmp     short loc_1800535A1
0x18005358a  mov     [rsp+1B0h+var_188], rcx
0x18005358f  mov     r9, rsi
0x180053592  mov     r8d, eax
0x180053595  mov     rdx, rbx
0x180053598  mov     rcx, r15
0x18005359b  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800535a0  nop
0x1800535a1  lea     rcx, [rbp+0B0h+var_D0]
0x1800535a5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800535aa  mov     rax, r15
0x1800535ad  mov     rcx, [rbp+0B0h+var_40]
0x1800535b1  xor     rcx, rsp; StackCookie
0x1800535b4  call    __security_check_cookie
0x1800535b9  mov     rbx, [rsp+1B0h+arg_8]
0x1800535c1  add     rsp, 180h
0x1800535c8  pop     r15
0x1800535ca  pop     r14
0x1800535cc  pop     r13
0x1800535ce  pop     r12
0x1800535d0  pop     rdi
0x1800535d1  pop     rsi
0x1800535d2  pop     rbp
0x1800535d3  retn
0x1800535d4  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x1800535db  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

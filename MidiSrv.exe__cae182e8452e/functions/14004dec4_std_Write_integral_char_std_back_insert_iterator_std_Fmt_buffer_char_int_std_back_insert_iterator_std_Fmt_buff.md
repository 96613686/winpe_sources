# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x14004dec4`
- end: `0x14004e275`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `945`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x1400498e8`
- `0x14004d5d4`
- `0x14004dec4`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x1400515b4`
- `0x140054144`
- `0x14005588c`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004e0d8`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004e0d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  char *v11; // r12
  char *v12; // rcx
  int v13; // eax
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
  int v28; // [rsp+34h] [rbp-CCh] BYREF
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
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 + 128 > 0xFF )
      std::_Throw_format_error("integral cannot be stored in char");
    *(_BYTE *)(a4 + 11) = 0;
    v29 = *(_OWORD *)a4;
    v30 = *(_DWORD *)(a4 + 16);
    std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>((__int64)a1, a2, a3, &v29, a5);
    return a1;
  }
  v9 = 2;
  if ( !*(_BYTE *)(a4 + 10) )
    *(_BYTE *)(a4 + 10) = 2;
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
  else if ( *(_BYTE *)(a4 + 10) != 2 )
  {
    v28 = ++v13;
  }
  v15 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 && v12 != v11 )
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
  if ( !*(_BYTE *)(a4 + 11) )
    goto LABEL_41;
  v16 = *(_BYTE *)(a4 + 8);
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
  if ( *(_BYTE *)(a4 + 12) )
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
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
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
      a4,
      v26,
      (__int64)v35);
  std::string::~string(&v36);
  return a1;
}

```

## disassembly

```asm
0x14004dec4  mov     [rsp-8+arg_8], rbx
0x14004dec9  push    rbp
0x14004deca  push    rsi
0x14004decb  push    rdi
0x14004decc  push    r12
0x14004dece  push    r13
0x14004ded0  push    r14
0x14004ded2  push    r15
0x14004ded4  lea     rbp, [rsp-80h]
0x14004ded9  sub     rsp, 180h
0x14004dee0  mov     rax, cs:__security_cookie
0x14004dee7  xor     rax, rsp
0x14004deea  mov     [rbp+0B0h+var_40], rax
0x14004deee  mov     rsi, r9
0x14004def1  mov     rbx, rdx
0x14004def4  mov     r15, rcx
0x14004def7  mov     [rsp+1B0h+var_150], r8d
0x14004defc  xor     r13d, r13d
0x14004deff  mov     al, [r9+8]
0x14004df03  cmp     al, 63h ; 'c'
0x14004df05  jnz     short loc_14004DF4C
0x14004df07  lea     eax, [r8+80h]
0x14004df0e  cmp     eax, 0FFh
0x14004df13  ja      loc_14004E268
0x14004df19  mov     [r9+0Bh], r13b
0x14004df1d  movaps  xmm0, xmmword ptr [r9]
0x14004df21  movaps  [rsp+1B0h+var_170], xmm0
0x14004df26  mov     ecx, [r9+10h]
0x14004df2a  mov     [rsp+1B0h+var_160], ecx
0x14004df2e  mov     rcx, [rbp+0B0h+arg_20]
0x14004df35  mov     [rsp+1B0h+var_190], rcx
0x14004df3a  lea     r9, [rsp+1B0h+var_170]
0x14004df3f  mov     rcx, r15
0x14004df42  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x14004df47  jmp     loc_14004E23E
0x14004df4c  mov     edi, 2
0x14004df51  cmp     [r9+0Ah], r13b
0x14004df55  jnz     short loc_14004DF5B
0x14004df57  mov     [r9+0Ah], dil
0x14004df5b  cmp     al, 42h ; 'B'
0x14004df5d  jz      short loc_14004DF84
0x14004df5f  cmp     al, 58h ; 'X'
0x14004df61  jz      short loc_14004DF7D
0x14004df63  cmp     al, 62h ; 'b'
0x14004df65  jz      short loc_14004DF84
0x14004df67  cmp     al, 6Fh ; 'o'
0x14004df69  jz      short loc_14004DF76
0x14004df6b  cmp     al, 78h ; 'x'
0x14004df6d  jz      short loc_14004DF7D
0x14004df6f  mov     eax, 0Ah
0x14004df74  jmp     short loc_14004DF86
0x14004df76  mov     eax, 8
0x14004df7b  jmp     short loc_14004DF86
0x14004df7d  mov     eax, 10h
0x14004df82  jmp     short loc_14004DF86
0x14004df84  mov     eax, edi
0x14004df86  mov     dword ptr [rsp+1B0h+var_190], eax
0x14004df8a  mov     r9d, r8d
0x14004df8d  lea     r8, [rbp+0B0h+var_4F]
0x14004df91  lea     rdx, [rbp+0B0h+var_90]
0x14004df95  lea     rcx, [rsp+1B0h+var_170]
0x14004df9a  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0HH@Z; std::to_chars(char * const,char * const,int,int)
0x14004df9f  mov     r12, [rax]
0x14004dfa2  lea     rcx, [rbp+0B0h+var_90]
0x14004dfa6  mov     [rsp+1B0h+var_140], rcx
0x14004dfab  mov     eax, r12d
0x14004dfae  sub     eax, ecx
0x14004dfb0  mov     [rsp+1B0h+var_17C], eax
0x14004dfb4  mov     edx, [rsp+1B0h+var_150]
0x14004dfb8  test    edx, edx
0x14004dfba  js      short loc_14004DFCA
0x14004dfbc  cmp     [rsi+0Ah], dil
0x14004dfc0  jz      short loc_14004DFD3
0x14004dfc2  inc     eax
0x14004dfc4  mov     [rsp+1B0h+var_17C], eax
0x14004dfc8  jmp     short loc_14004DFD3
0x14004dfca  lea     rcx, [rbp+0B0h+var_8F]
0x14004dfce  mov     [rsp+1B0h+var_140], rcx
0x14004dfd3  mov     r14d, 1
0x14004dfd9  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14004dfdd  jnz     short loc_14004E002
0x14004dfdf  cmp     rcx, r12
0x14004dfe2  jz      short loc_14004E002
0x14004dfe4  mov     dl, [rcx]
0x14004dfe6  lea     eax, [rdx-61h]
0x14004dfe9  cmp     al, 19h
0x14004dfeb  ja      short loc_14004DFF2
0x14004dfed  sub     dl, 20h ; ' '
0x14004dff0  mov     [rcx], dl
0x14004dff2  add     rcx, r14
0x14004dff5  cmp     rcx, r12
0x14004dff8  jnz     short loc_14004DFE4
0x14004dffa  mov     eax, [rsp+1B0h+var_17C]
0x14004dffe  mov     edx, [rsp+1B0h+var_150]
0x14004e002  mov     qword ptr [rbp+0B0h+var_130], r13
0x14004e006  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x14004e00a  cmp     [rsi+0Bh], r13b
0x14004e00e  jz      short loc_14004E08C
0x14004e010  mov     cl, [rsi+8]
0x14004e013  cmp     cl, 42h ; 'B'
0x14004e016  jz      short loc_14004E06B
0x14004e018  cmp     cl, 58h ; 'X'
0x14004e01b  jz      short loc_14004E062
0x14004e01d  cmp     cl, 62h ; 'b'
0x14004e020  jz      short loc_14004E059
0x14004e022  cmp     cl, 6Fh ; 'o'
0x14004e025  jz      short loc_14004E035
0x14004e027  cmp     cl, 78h ; 'x'
0x14004e02a  jnz     short loc_14004E04A
0x14004e02c  lea     rcx, a0x; "0x"
0x14004e033  jmp     short loc_14004E072
0x14004e035  test    edx, edx
0x14004e037  jz      short loc_14004E04A
0x14004e039  lea     rcx, a0; "0"
0x14004e040  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14004e045  mov     edi, r14d
0x14004e048  jmp     short loc_14004E077
0x14004e04a  mov     qword ptr [rsp+1B0h+var_170], r13
0x14004e04f  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14004e054  mov     edi, r13d
0x14004e057  jmp     short loc_14004E07C
0x14004e059  lea     rcx, a0b; "0b"
0x14004e060  jmp     short loc_14004E072
0x14004e062  lea     rcx, a0x_0; "0X"
0x14004e069  jmp     short loc_14004E072
0x14004e06b  lea     rcx, a0b_0; "0B"
0x14004e072  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14004e077  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14004e07c  movaps  xmm0, [rsp+1B0h+var_170]
0x14004e081  movdqa  [rbp+0B0h+var_130], xmm0
0x14004e086  add     eax, edi
0x14004e088  mov     [rsp+1B0h+var_17C], eax
0x14004e08c  mov     [rsp+1B0h+var_148], r13d
0x14004e091  xorps   xmm0, xmm0
0x14004e094  movups  [rbp+0B0h+var_D0], xmm0
0x14004e098  mov     [rbp+0B0h+var_C0], r13
0x14004e09c  mov     [rbp+0B0h+var_B8], 0Fh
0x14004e0a4  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14004e0a8  cmp     [rsi+0Ch], r13b
0x14004e0ac  jz      loc_14004E1A4
0x14004e0b2  mov     rax, [rbp+0B0h+arg_20]
0x14004e0b9  test    rax, rax
0x14004e0bc  jz      short loc_14004E0D5
0x14004e0be  mov     rcx, [rax+8]
0x14004e0c2  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x14004e0c7  mov     rax, [rcx]
0x14004e0ca  mov     rax, [rax+8]
0x14004e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e0d3  jmp     short loc_14004E0E3
0x14004e0d5  mov     cl, r14b
0x14004e0d8  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004e0de  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x14004e0e3  lea     rcx, [rsp+1B0h+var_170]
0x14004e0e8  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004e0ed  mov     r8, rax
0x14004e0f0  mov     rcx, [rax]
0x14004e0f3  mov     rax, [rcx+28h]
0x14004e0f7  lea     rdx, [rbp+0B0h+var_B0]
0x14004e0fb  mov     rcx, r8
0x14004e0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e103  lea     rdx, [rbp+0B0h+var_B0]
0x14004e107  lea     rcx, [rbp+0B0h+var_D0]
0x14004e10b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004e110  lea     rcx, [rbp+0B0h+var_B0]
0x14004e114  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004e119  nop
0x14004e11a  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x14004e11f  test    rcx, rcx
0x14004e122  jz      short loc_14004E149
0x14004e124  mov     rax, [rcx]
0x14004e127  mov     rax, [rax+10h]
0x14004e12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e130  mov     r8, rax
0x14004e133  test    rax, rax
0x14004e136  jz      short loc_14004E149
0x14004e138  mov     rcx, [rax]
0x14004e13b  mov     rax, [rcx]
0x14004e13e  mov     edx, r14d
0x14004e141  mov     rcx, r8
0x14004e144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e149  lea     rax, [rbp+0B0h+var_D0]
0x14004e14d  cmp     [rbp+0B0h+var_B8], 0Fh
0x14004e152  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14004e157  mov     r10, [rbp+0B0h+var_C0]
0x14004e15b  mov     edx, r13d
0x14004e15e  test    r10, r10
0x14004e161  jz      short loc_14004E196
0x14004e163  mov     r8, r12
0x14004e166  sub     r8, [rsp+1B0h+var_140]
0x14004e16b  movsx   r9, byte ptr [rax]
0x14004e16f  cmp     r8, r9
0x14004e172  jbe     short loc_14004E196
0x14004e174  lea     r11, [r10+rax]
0x14004e178  movsx   rcx, r9b
0x14004e17c  sub     r8, rcx
0x14004e17f  add     edx, r14d
0x14004e182  lea     rcx, [rax+1]
0x14004e186  cmp     rcx, r11
0x14004e189  cmovnz  rax, rcx
0x14004e18d  movsx   r9, byte ptr [rax]
0x14004e191  cmp     r8, r9
0x14004e194  ja      short loc_14004E178
0x14004e196  mov     [rsp+1B0h+var_148], edx
0x14004e19a  mov     eax, [rsp+1B0h+var_17C]
0x14004e19e  add     eax, edx
0x14004e1a0  mov     [rsp+1B0h+var_17C], eax
0x14004e1a4  cmp     [rsi+0Dh], r13b
0x14004e1a8  jz      short loc_14004E1B0
0x14004e1aa  cmp     [rsi+9], r13b
0x14004e1ae  jz      short loc_14004E1B3
0x14004e1b0  mov     r14b, r13b
0x14004e1b3  mov     [rsp+1B0h+var_180], r14b
0x14004e1b8  mov     [rbp+0B0h+var_120], r12
0x14004e1bc  mov     [rbp+0B0h+var_118], rsi
0x14004e1c0  lea     rcx, [rsp+1B0h+var_150]
0x14004e1c5  mov     [rbp+0B0h+var_110], rcx
0x14004e1c9  lea     rcx, [rbp+0B0h+var_130]
0x14004e1cd  mov     [rbp+0B0h+var_108], rcx
0x14004e1d1  lea     rcx, [rsp+1B0h+var_180]
0x14004e1d6  mov     [rbp+0B0h+var_100], rcx
0x14004e1da  lea     rcx, [rsp+1B0h+var_17C]
0x14004e1df  mov     [rbp+0B0h+var_F8], rcx
0x14004e1e3  lea     rcx, [rsp+1B0h+var_148]
0x14004e1e8  mov     [rbp+0B0h+var_F0], rcx
0x14004e1ec  lea     rcx, [rsp+1B0h+var_140]
0x14004e1f1  mov     [rbp+0B0h+var_E8], rcx
0x14004e1f5  lea     rcx, [rbp+0B0h+var_D0]
0x14004e1f9  mov     [rbp+0B0h+var_E0], rcx
0x14004e1fd  lea     rcx, [rbp+0B0h+arg_20]
0x14004e204  mov     [rbp+0B0h+var_D8], rcx
0x14004e208  lea     rcx, [rbp+0B0h+var_120]
0x14004e20c  test    r14b, r14b
0x14004e20f  jz      short loc_14004E21E
0x14004e211  mov     r8, rbx
0x14004e214  mov     rdx, r15
0x14004e217  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x14004e21c  jmp     short loc_14004E235
0x14004e21e  mov     [rsp+1B0h+var_188], rcx
0x14004e223  mov     r9, rsi
0x14004e226  mov     r8d, eax
0x14004e229  mov     rdx, rbx
0x14004e22c  mov     rcx, r15
0x14004e22f  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@2@YA?AV12@V12@HU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@0@YA?AV10@0HU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14004e234  nop
0x14004e235  lea     rcx, [rbp+0B0h+var_D0]
0x14004e239  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004e23e  mov     rax, r15
0x14004e241  mov     rcx, [rbp+0B0h+var_40]
0x14004e245  xor     rcx, rsp; StackCookie
0x14004e248  call    __security_check_cookie
0x14004e24d  mov     rbx, [rsp+1B0h+arg_8]
0x14004e255  add     rsp, 180h
0x14004e25c  pop     r15
0x14004e25e  pop     r14
0x14004e260  pop     r13
0x14004e262  pop     r12
0x14004e264  pop     rdi
0x14004e265  pop     rsi
0x14004e266  pop     rbp
0x14004e267  retn
0x14004e268  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x14004e26f  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

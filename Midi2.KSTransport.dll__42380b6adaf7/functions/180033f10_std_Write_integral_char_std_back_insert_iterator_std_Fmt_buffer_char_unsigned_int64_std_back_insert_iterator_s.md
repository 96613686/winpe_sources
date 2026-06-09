# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180033f10`
- end: `0x1800342ad`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_KU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180032164`

## callees

- `0x180004410`
- `0x18002ef5c`
- `0x180032c34`
- `0x180033f10`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x180036fb4`
- `0x18003a404`
- `0x18003c250`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180034110`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180034110`

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
0x180033f10  mov     [rsp-8+arg_8], rbx
0x180033f15  push    rbp
0x180033f16  push    rsi
0x180033f17  push    rdi
0x180033f18  push    r12
0x180033f1a  push    r13
0x180033f1c  push    r14
0x180033f1e  push    r15
0x180033f20  lea     rbp, [rsp-80h]
0x180033f25  sub     rsp, 180h
0x180033f2c  mov     rax, cs:__security_cookie
0x180033f33  xor     rax, rsp
0x180033f36  mov     [rbp+0B0h+var_40], rax
0x180033f3a  mov     rsi, r9
0x180033f3d  mov     rbx, rdx
0x180033f40  mov     r15, rcx
0x180033f43  mov     [rsp+1B0h+var_148], r8
0x180033f48  xor     r13d, r13d
0x180033f4b  mov     al, [r9+8]
0x180033f4f  cmp     al, 63h ; 'c'
0x180033f51  jnz     short loc_180033F90
0x180033f53  cmp     r8, 7Fh
0x180033f57  ja      loc_1800342A0
0x180033f5d  mov     [r9+0Bh], r13b
0x180033f61  movaps  xmm0, xmmword ptr [r9]
0x180033f65  movaps  [rsp+1B0h+var_170], xmm0
0x180033f6a  mov     ecx, [r9+10h]
0x180033f6e  mov     [rsp+1B0h+var_160], ecx
0x180033f72  mov     rcx, [rbp+0B0h+arg_20]
0x180033f79  mov     [rsp+1B0h+var_190], rcx
0x180033f7e  lea     r9, [rsp+1B0h+var_170]
0x180033f83  mov     rcx, r15
0x180033f86  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180033f8b  jmp     loc_180034276
0x180033f90  mov     edi, 2
0x180033f95  cmp     [r9+0Ah], r13b
0x180033f99  jnz     short loc_180033F9F
0x180033f9b  mov     [r9+0Ah], dil
0x180033f9f  cmp     al, 42h ; 'B'
0x180033fa1  jz      short loc_180033FC8
0x180033fa3  cmp     al, 58h ; 'X'
0x180033fa5  jz      short loc_180033FC1
0x180033fa7  cmp     al, 62h ; 'b'
0x180033fa9  jz      short loc_180033FC8
0x180033fab  cmp     al, 6Fh ; 'o'
0x180033fad  jz      short loc_180033FBA
0x180033faf  cmp     al, 78h ; 'x'
0x180033fb1  jz      short loc_180033FC1
0x180033fb3  mov     eax, 0Ah
0x180033fb8  jmp     short loc_180033FCA
0x180033fba  mov     eax, 8
0x180033fbf  jmp     short loc_180033FCA
0x180033fc1  mov     eax, 10h
0x180033fc6  jmp     short loc_180033FCA
0x180033fc8  mov     eax, edi
0x180033fca  mov     dword ptr [rsp+1B0h+var_190], eax
0x180033fce  mov     r9, r8
0x180033fd1  lea     r8, [rbp+0B0h+var_4F]
0x180033fd5  lea     rdx, [rbp+0B0h+var_90]
0x180033fd9  lea     rcx, [rsp+1B0h+var_170]
0x180033fde  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0_KH@Z; std::to_chars(char * const,char * const,unsigned __int64,int)
0x180033fe3  mov     r12, [rax]
0x180033fe6  lea     rcx, [rbp+0B0h+var_90]
0x180033fea  mov     [rsp+1B0h+var_140], rcx
0x180033fef  mov     eax, r12d
0x180033ff2  sub     eax, ecx
0x180033ff4  mov     [rsp+1B0h+var_17C], eax
0x180033ff8  cmp     [rsi+0Ah], dil
0x180033ffc  jz      short loc_180034004
0x180033ffe  inc     eax
0x180034000  mov     [rsp+1B0h+var_17C], eax
0x180034004  mov     r14d, 1
0x18003400a  cmp     byte ptr [rsi+8], 58h ; 'X'
0x18003400e  jnz     short loc_180034037
0x180034010  lea     rcx, [rbp+0B0h+var_90]
0x180034014  lea     rdx, [rbp+0B0h+var_90]
0x180034018  cmp     rdx, r12
0x18003401b  jz      short loc_180034037
0x18003401d  mov     dl, [rcx]
0x18003401f  lea     eax, [rdx-61h]
0x180034022  cmp     al, 19h
0x180034024  ja      short loc_18003402B
0x180034026  sub     dl, 20h ; ' '
0x180034029  mov     [rcx], dl
0x18003402b  add     rcx, r14
0x18003402e  cmp     rcx, r12
0x180034031  jnz     short loc_18003401D
0x180034033  mov     eax, [rsp+1B0h+var_17C]
0x180034037  mov     qword ptr [rbp+0B0h+var_130], r13
0x18003403b  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x18003403f  cmp     [rsi+0Bh], r13b
0x180034043  jz      short loc_1800340C4
0x180034045  mov     cl, [rsi+8]
0x180034048  cmp     cl, 42h ; 'B'
0x18003404b  jz      short loc_1800340A3
0x18003404d  cmp     cl, 58h ; 'X'
0x180034050  jz      short loc_18003409A
0x180034052  cmp     cl, 62h ; 'b'
0x180034055  jz      short loc_180034091
0x180034057  cmp     cl, 6Fh ; 'o'
0x18003405a  jz      short loc_18003406A
0x18003405c  cmp     cl, 78h ; 'x'
0x18003405f  jnz     short loc_180034082
0x180034061  lea     rcx, a0x; "0x"
0x180034068  jmp     short loc_1800340AA
0x18003406a  cmp     [rsp+1B0h+var_148], r13
0x18003406f  jz      short loc_180034082
0x180034071  lea     rcx, a0; "0"
0x180034078  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x18003407d  mov     edi, r14d
0x180034080  jmp     short loc_1800340AF
0x180034082  mov     qword ptr [rsp+1B0h+var_170], r13
0x180034087  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18003408c  mov     edi, r13d
0x18003408f  jmp     short loc_1800340B4
0x180034091  lea     rcx, a0b; "0b"
0x180034098  jmp     short loc_1800340AA
0x18003409a  lea     rcx, a0x_0; "0X"
0x1800340a1  jmp     short loc_1800340AA
0x1800340a3  lea     rcx, a0b_0; "0B"
0x1800340aa  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800340af  mov     qword ptr [rsp+1B0h+var_170], rcx
0x1800340b4  movaps  xmm0, [rsp+1B0h+var_170]
0x1800340b9  movdqa  [rbp+0B0h+var_130], xmm0
0x1800340be  add     eax, edi
0x1800340c0  mov     [rsp+1B0h+var_17C], eax
0x1800340c4  mov     [rsp+1B0h+var_150], r13d
0x1800340c9  xorps   xmm0, xmm0
0x1800340cc  movups  [rbp+0B0h+var_D0], xmm0
0x1800340d0  mov     [rbp+0B0h+var_C0], r13
0x1800340d4  mov     [rbp+0B0h+var_B8], 0Fh
0x1800340dc  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x1800340e0  cmp     [rsi+0Ch], r13b
0x1800340e4  jz      loc_1800341DC
0x1800340ea  mov     rax, [rbp+0B0h+arg_20]
0x1800340f1  test    rax, rax
0x1800340f4  jz      short loc_18003410D
0x1800340f6  mov     rcx, [rax+8]
0x1800340fa  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x1800340ff  mov     rax, [rcx]
0x180034102  mov     rax, [rax+8]
0x180034106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003410b  jmp     short loc_18003411B
0x18003410d  mov     cl, r14b
0x180034110  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180034116  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x18003411b  lea     rcx, [rsp+1B0h+var_170]
0x180034120  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180034125  mov     r8, rax
0x180034128  mov     rcx, [rax]
0x18003412b  mov     rax, [rcx+28h]
0x18003412f  lea     rdx, [rbp+0B0h+var_B0]
0x180034133  mov     rcx, r8
0x180034136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003413b  lea     rdx, [rbp+0B0h+var_B0]
0x18003413f  lea     rcx, [rbp+0B0h+var_D0]
0x180034143  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180034148  lea     rcx, [rbp+0B0h+var_B0]
0x18003414c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180034151  nop
0x180034152  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180034157  test    rcx, rcx
0x18003415a  jz      short loc_180034181
0x18003415c  mov     rax, [rcx]
0x18003415f  mov     rax, [rax+10h]
0x180034163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034168  mov     r8, rax
0x18003416b  test    rax, rax
0x18003416e  jz      short loc_180034181
0x180034170  mov     rcx, [rax]
0x180034173  mov     rax, [rcx]
0x180034176  mov     edx, r14d
0x180034179  mov     rcx, r8
0x18003417c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034181  lea     rax, [rbp+0B0h+var_D0]
0x180034185  cmp     [rbp+0B0h+var_B8], 0Fh
0x18003418a  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x18003418f  mov     r10, [rbp+0B0h+var_C0]
0x180034193  mov     edx, r13d
0x180034196  test    r10, r10
0x180034199  jz      short loc_1800341CE
0x18003419b  mov     r8, r12
0x18003419e  sub     r8, [rsp+1B0h+var_140]
0x1800341a3  movsx   r9, byte ptr [rax]
0x1800341a7  cmp     r8, r9
0x1800341aa  jbe     short loc_1800341CE
0x1800341ac  lea     r11, [r10+rax]
0x1800341b0  movsx   rcx, r9b
0x1800341b4  sub     r8, rcx
0x1800341b7  add     edx, r14d
0x1800341ba  lea     rcx, [rax+1]
0x1800341be  cmp     rcx, r11
0x1800341c1  cmovnz  rax, rcx
0x1800341c5  movsx   r9, byte ptr [rax]
0x1800341c9  cmp     r8, r9
0x1800341cc  ja      short loc_1800341B0
0x1800341ce  mov     [rsp+1B0h+var_150], edx
0x1800341d2  mov     eax, [rsp+1B0h+var_17C]
0x1800341d6  add     eax, edx
0x1800341d8  mov     [rsp+1B0h+var_17C], eax
0x1800341dc  cmp     [rsi+0Dh], r13b
0x1800341e0  jz      short loc_1800341E8
0x1800341e2  cmp     [rsi+9], r13b
0x1800341e6  jz      short loc_1800341EB
0x1800341e8  mov     r14b, r13b
0x1800341eb  mov     [rsp+1B0h+var_180], r14b
0x1800341f0  mov     [rbp+0B0h+var_120], r12
0x1800341f4  mov     [rbp+0B0h+var_118], rsi
0x1800341f8  lea     rcx, [rsp+1B0h+var_148]
0x1800341fd  mov     [rbp+0B0h+var_110], rcx
0x180034201  lea     rcx, [rbp+0B0h+var_130]
0x180034205  mov     [rbp+0B0h+var_108], rcx
0x180034209  lea     rcx, [rsp+1B0h+var_180]
0x18003420e  mov     [rbp+0B0h+var_100], rcx
0x180034212  lea     rcx, [rsp+1B0h+var_17C]
0x180034217  mov     [rbp+0B0h+var_F8], rcx
0x18003421b  lea     rcx, [rsp+1B0h+var_150]
0x180034220  mov     [rbp+0B0h+var_F0], rcx
0x180034224  lea     rcx, [rsp+1B0h+var_140]
0x180034229  mov     [rbp+0B0h+var_E8], rcx
0x18003422d  lea     rcx, [rbp+0B0h+var_D0]
0x180034231  mov     [rbp+0B0h+var_E0], rcx
0x180034235  lea     rcx, [rbp+0B0h+arg_20]
0x18003423c  mov     [rbp+0B0h+var_D8], rcx
0x180034240  lea     rcx, [rbp+0B0h+var_120]
0x180034244  test    r14b, r14b
0x180034247  jz      short loc_180034256
0x180034249  mov     r8, rbx
0x18003424c  mov     rdx, r15
0x18003424f  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180034254  jmp     short loc_18003426D
0x180034256  mov     [rsp+1B0h+var_188], rcx
0x18003425b  mov     r9, rsi
0x18003425e  mov     r8d, eax
0x180034261  mov     rdx, rbx
0x180034264  mov     rcx, r15
0x180034267  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x18003426c  nop
0x18003426d  lea     rcx, [rbp+0B0h+var_D0]
0x180034271  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180034276  mov     rax, r15
0x180034279  mov     rcx, [rbp+0B0h+var_40]
0x18003427d  xor     rcx, rsp; StackCookie
0x180034280  call    __security_check_cookie
0x180034285  mov     rbx, [rsp+1B0h+arg_8]
0x18003428d  add     rsp, 180h
0x180034294  pop     r15
0x180034296  pop     r14
0x180034298  pop     r13
0x18003429a  pop     r12
0x18003429c  pop     rdi
0x18003429d  pop     rsi
0x18003429e  pop     rbp
0x18003429f  retn
0x1800342a0  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x1800342a7  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

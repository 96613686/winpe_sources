# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x1800337ac`
- end: `0x180033b49`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@IU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
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
- `0x1800337ac`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x180036fb4`
- `0x18003a404`
- `0x18003bd38`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800339ac`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800339ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned int>(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
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
  unsigned int v31; // [rsp+68h] [rbp-98h] BYREF
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
0x1800337ac  mov     [rsp-8+arg_8], rbx
0x1800337b1  push    rbp
0x1800337b2  push    rsi
0x1800337b3  push    rdi
0x1800337b4  push    r12
0x1800337b6  push    r13
0x1800337b8  push    r14
0x1800337ba  push    r15
0x1800337bc  lea     rbp, [rsp-80h]
0x1800337c1  sub     rsp, 180h
0x1800337c8  mov     rax, cs:__security_cookie
0x1800337cf  xor     rax, rsp
0x1800337d2  mov     [rbp+0B0h+var_40], rax
0x1800337d6  mov     rsi, r9
0x1800337d9  mov     rbx, rdx
0x1800337dc  mov     r15, rcx
0x1800337df  mov     [rsp+1B0h+var_148], r8d
0x1800337e4  xor     r13d, r13d
0x1800337e7  mov     al, [r9+8]
0x1800337eb  cmp     al, 63h ; 'c'
0x1800337ed  jnz     short loc_18003382C
0x1800337ef  cmp     r8d, 7Fh
0x1800337f3  ja      loc_180033B3C
0x1800337f9  mov     [r9+0Bh], r13b
0x1800337fd  movaps  xmm0, xmmword ptr [r9]
0x180033801  movaps  [rsp+1B0h+var_170], xmm0
0x180033806  mov     ecx, [r9+10h]
0x18003380a  mov     [rsp+1B0h+var_160], ecx
0x18003380e  mov     rcx, [rbp+0B0h+arg_20]
0x180033815  mov     [rsp+1B0h+var_190], rcx
0x18003381a  lea     r9, [rsp+1B0h+var_170]
0x18003381f  mov     rcx, r15
0x180033822  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180033827  jmp     loc_180033B12
0x18003382c  mov     edi, 2
0x180033831  cmp     [r9+0Ah], r13b
0x180033835  jnz     short loc_18003383B
0x180033837  mov     [r9+0Ah], dil
0x18003383b  cmp     al, 42h ; 'B'
0x18003383d  jz      short loc_180033864
0x18003383f  cmp     al, 58h ; 'X'
0x180033841  jz      short loc_18003385D
0x180033843  cmp     al, 62h ; 'b'
0x180033845  jz      short loc_180033864
0x180033847  cmp     al, 6Fh ; 'o'
0x180033849  jz      short loc_180033856
0x18003384b  cmp     al, 78h ; 'x'
0x18003384d  jz      short loc_18003385D
0x18003384f  mov     eax, 0Ah
0x180033854  jmp     short loc_180033866
0x180033856  mov     eax, 8
0x18003385b  jmp     short loc_180033866
0x18003385d  mov     eax, 10h
0x180033862  jmp     short loc_180033866
0x180033864  mov     eax, edi
0x180033866  mov     dword ptr [rsp+1B0h+var_190], eax
0x18003386a  mov     r9d, r8d
0x18003386d  lea     r8, [rbp+0B0h+var_4F]
0x180033871  lea     rdx, [rbp+0B0h+var_90]
0x180033875  lea     rcx, [rsp+1B0h+var_170]
0x18003387a  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0IH@Z; std::to_chars(char * const,char * const,uint,int)
0x18003387f  mov     r12, [rax]
0x180033882  lea     rcx, [rbp+0B0h+var_90]
0x180033886  mov     [rsp+1B0h+var_140], rcx
0x18003388b  mov     eax, r12d
0x18003388e  sub     eax, ecx
0x180033890  mov     [rsp+1B0h+var_17C], eax
0x180033894  cmp     [rsi+0Ah], dil
0x180033898  jz      short loc_1800338A0
0x18003389a  inc     eax
0x18003389c  mov     [rsp+1B0h+var_17C], eax
0x1800338a0  mov     r14d, 1
0x1800338a6  cmp     byte ptr [rsi+8], 58h ; 'X'
0x1800338aa  jnz     short loc_1800338D3
0x1800338ac  lea     rcx, [rbp+0B0h+var_90]
0x1800338b0  lea     rdx, [rbp+0B0h+var_90]
0x1800338b4  cmp     rdx, r12
0x1800338b7  jz      short loc_1800338D3
0x1800338b9  mov     dl, [rcx]
0x1800338bb  lea     eax, [rdx-61h]
0x1800338be  cmp     al, 19h
0x1800338c0  ja      short loc_1800338C7
0x1800338c2  sub     dl, 20h ; ' '
0x1800338c5  mov     [rcx], dl
0x1800338c7  add     rcx, r14
0x1800338ca  cmp     rcx, r12
0x1800338cd  jnz     short loc_1800338B9
0x1800338cf  mov     eax, [rsp+1B0h+var_17C]
0x1800338d3  mov     qword ptr [rbp+0B0h+var_130], r13
0x1800338d7  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x1800338db  cmp     [rsi+0Bh], r13b
0x1800338df  jz      short loc_180033960
0x1800338e1  mov     cl, [rsi+8]
0x1800338e4  cmp     cl, 42h ; 'B'
0x1800338e7  jz      short loc_18003393F
0x1800338e9  cmp     cl, 58h ; 'X'
0x1800338ec  jz      short loc_180033936
0x1800338ee  cmp     cl, 62h ; 'b'
0x1800338f1  jz      short loc_18003392D
0x1800338f3  cmp     cl, 6Fh ; 'o'
0x1800338f6  jz      short loc_180033906
0x1800338f8  cmp     cl, 78h ; 'x'
0x1800338fb  jnz     short loc_18003391E
0x1800338fd  lea     rcx, a0x; "0x"
0x180033904  jmp     short loc_180033946
0x180033906  cmp     [rsp+1B0h+var_148], r13d
0x18003390b  jz      short loc_18003391E
0x18003390d  lea     rcx, a0; "0"
0x180033914  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180033919  mov     edi, r14d
0x18003391c  jmp     short loc_18003394B
0x18003391e  mov     qword ptr [rsp+1B0h+var_170], r13
0x180033923  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180033928  mov     edi, r13d
0x18003392b  jmp     short loc_180033950
0x18003392d  lea     rcx, a0b; "0b"
0x180033934  jmp     short loc_180033946
0x180033936  lea     rcx, a0x_0; "0X"
0x18003393d  jmp     short loc_180033946
0x18003393f  lea     rcx, a0b_0; "0B"
0x180033946  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x18003394b  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180033950  movaps  xmm0, [rsp+1B0h+var_170]
0x180033955  movdqa  [rbp+0B0h+var_130], xmm0
0x18003395a  add     eax, edi
0x18003395c  mov     [rsp+1B0h+var_17C], eax
0x180033960  mov     [rsp+1B0h+var_150], r13d
0x180033965  xorps   xmm0, xmm0
0x180033968  movups  [rbp+0B0h+var_D0], xmm0
0x18003396c  mov     [rbp+0B0h+var_C0], r13
0x180033970  mov     [rbp+0B0h+var_B8], 0Fh
0x180033978  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x18003397c  cmp     [rsi+0Ch], r13b
0x180033980  jz      loc_180033A78
0x180033986  mov     rax, [rbp+0B0h+arg_20]
0x18003398d  test    rax, rax
0x180033990  jz      short loc_1800339A9
0x180033992  mov     rcx, [rax+8]
0x180033996  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x18003399b  mov     rax, [rcx]
0x18003399e  mov     rax, [rax+8]
0x1800339a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339a7  jmp     short loc_1800339B7
0x1800339a9  mov     cl, r14b
0x1800339ac  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1800339b2  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x1800339b7  lea     rcx, [rsp+1B0h+var_170]
0x1800339bc  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x1800339c1  mov     r8, rax
0x1800339c4  mov     rcx, [rax]
0x1800339c7  mov     rax, [rcx+28h]
0x1800339cb  lea     rdx, [rbp+0B0h+var_B0]
0x1800339cf  mov     rcx, r8
0x1800339d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339d7  lea     rdx, [rbp+0B0h+var_B0]
0x1800339db  lea     rcx, [rbp+0B0h+var_D0]
0x1800339df  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800339e4  lea     rcx, [rbp+0B0h+var_B0]
0x1800339e8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800339ed  nop
0x1800339ee  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x1800339f3  test    rcx, rcx
0x1800339f6  jz      short loc_180033A1D
0x1800339f8  mov     rax, [rcx]
0x1800339fb  mov     rax, [rax+10h]
0x1800339ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a04  mov     r8, rax
0x180033a07  test    rax, rax
0x180033a0a  jz      short loc_180033A1D
0x180033a0c  mov     rcx, [rax]
0x180033a0f  mov     rax, [rcx]
0x180033a12  mov     edx, r14d
0x180033a15  mov     rcx, r8
0x180033a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a1d  lea     rax, [rbp+0B0h+var_D0]
0x180033a21  cmp     [rbp+0B0h+var_B8], 0Fh
0x180033a26  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180033a2b  mov     r10, [rbp+0B0h+var_C0]
0x180033a2f  mov     edx, r13d
0x180033a32  test    r10, r10
0x180033a35  jz      short loc_180033A6A
0x180033a37  mov     r8, r12
0x180033a3a  sub     r8, [rsp+1B0h+var_140]
0x180033a3f  movsx   r9, byte ptr [rax]
0x180033a43  cmp     r8, r9
0x180033a46  jbe     short loc_180033A6A
0x180033a48  lea     r11, [r10+rax]
0x180033a4c  movsx   rcx, r9b
0x180033a50  sub     r8, rcx
0x180033a53  add     edx, r14d
0x180033a56  lea     rcx, [rax+1]
0x180033a5a  cmp     rcx, r11
0x180033a5d  cmovnz  rax, rcx
0x180033a61  movsx   r9, byte ptr [rax]
0x180033a65  cmp     r8, r9
0x180033a68  ja      short loc_180033A4C
0x180033a6a  mov     [rsp+1B0h+var_150], edx
0x180033a6e  mov     eax, [rsp+1B0h+var_17C]
0x180033a72  add     eax, edx
0x180033a74  mov     [rsp+1B0h+var_17C], eax
0x180033a78  cmp     [rsi+0Dh], r13b
0x180033a7c  jz      short loc_180033A84
0x180033a7e  cmp     [rsi+9], r13b
0x180033a82  jz      short loc_180033A87
0x180033a84  mov     r14b, r13b
0x180033a87  mov     [rsp+1B0h+var_180], r14b
0x180033a8c  mov     [rbp+0B0h+var_120], r12
0x180033a90  mov     [rbp+0B0h+var_118], rsi
0x180033a94  lea     rcx, [rsp+1B0h+var_148]
0x180033a99  mov     [rbp+0B0h+var_110], rcx
0x180033a9d  lea     rcx, [rbp+0B0h+var_130]
0x180033aa1  mov     [rbp+0B0h+var_108], rcx
0x180033aa5  lea     rcx, [rsp+1B0h+var_180]
0x180033aaa  mov     [rbp+0B0h+var_100], rcx
0x180033aae  lea     rcx, [rsp+1B0h+var_17C]
0x180033ab3  mov     [rbp+0B0h+var_F8], rcx
0x180033ab7  lea     rcx, [rsp+1B0h+var_150]
0x180033abc  mov     [rbp+0B0h+var_F0], rcx
0x180033ac0  lea     rcx, [rsp+1B0h+var_140]
0x180033ac5  mov     [rbp+0B0h+var_E8], rcx
0x180033ac9  lea     rcx, [rbp+0B0h+var_D0]
0x180033acd  mov     [rbp+0B0h+var_E0], rcx
0x180033ad1  lea     rcx, [rbp+0B0h+arg_20]
0x180033ad8  mov     [rbp+0B0h+var_D8], rcx
0x180033adc  lea     rcx, [rbp+0B0h+var_120]
0x180033ae0  test    r14b, r14b
0x180033ae3  jz      short loc_180033AF2
0x180033ae5  mov     r8, rbx
0x180033ae8  mov     rdx, r15
0x180033aeb  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180033af0  jmp     short loc_180033B09
0x180033af2  mov     [rsp+1B0h+var_188], rcx
0x180033af7  mov     r9, rsi
0x180033afa  mov     r8d, eax
0x180033afd  mov     rdx, rbx
0x180033b00  mov     rcx, r15
0x180033b03  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180033b08  nop
0x180033b09  lea     rcx, [rbp+0B0h+var_D0]
0x180033b0d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033b12  mov     rax, r15
0x180033b15  mov     rcx, [rbp+0B0h+var_40]
0x180033b19  xor     rcx, rsp; StackCookie
0x180033b1c  call    __security_check_cookie
0x180033b21  mov     rbx, [rsp+1B0h+arg_8]
0x180033b29  add     rsp, 180h
0x180033b30  pop     r15
0x180033b32  pop     r14
0x180033b34  pop     r13
0x180033b36  pop     r12
0x180033b38  pop     rdi
0x180033b39  pop     rsi
0x180033b3a  pop     rbp
0x180033b3b  retn
0x180033b3c  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180033b43  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x14004e9e0`
- end: `0x14004ed7d`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_KU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, unsigned __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x1400498e8`
- `0x14004d704`
- `0x14004e9e0`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x14005175c`
- `0x140054144`
- `0x140055f90`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004ebe0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004ebe0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  _BYTE *v11; // r12
  int v12; // eax
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
  int v27; // [rsp+34h] [rbp-CCh] BYREF
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
  v8 = *(_BYTE *)(a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0x7F )
      std::_Throw_format_error("integral cannot be stored in char");
    *(_BYTE *)(a4 + 11) = 0;
    v28 = *(_OWORD *)a4;
    v29 = *(_DWORD *)(a4 + 16);
    std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>((__int64)a1, a2, a3, &v28, a5);
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
  v25 = v10;
  v11 = *(_BYTE **)std::to_chars(&v28, v39, v40, a3);
  v32 = v39;
  v12 = (_DWORD)v11 - (unsigned int)v39;
  v27 = v12;
  if ( *(_BYTE *)(a4 + 10) != 2 )
    v27 = ++v12;
  v13 = 1;
  if ( *(_BYTE *)(a4 + 8) == 88 )
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
  if ( !*(_BYTE *)(a4 + 11) )
    goto LABEL_39;
  v15 = *(_BYTE *)(a4 + 8);
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
  if ( *(_BYTE *)(a4 + 12) )
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
  if ( !*(_BYTE *)(a4 + 13) || *(_BYTE *)(a4 + 9) )
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
      a4,
      v25,
      (__int64)v34);
  std::string::~string(&v35);
  return a1;
}

```

## disassembly

```asm
0x14004e9e0  mov     [rsp-8+arg_8], rbx
0x14004e9e5  push    rbp
0x14004e9e6  push    rsi
0x14004e9e7  push    rdi
0x14004e9e8  push    r12
0x14004e9ea  push    r13
0x14004e9ec  push    r14
0x14004e9ee  push    r15
0x14004e9f0  lea     rbp, [rsp-80h]
0x14004e9f5  sub     rsp, 180h
0x14004e9fc  mov     rax, cs:__security_cookie
0x14004ea03  xor     rax, rsp
0x14004ea06  mov     [rbp+0B0h+var_40], rax
0x14004ea0a  mov     rsi, r9
0x14004ea0d  mov     rbx, rdx
0x14004ea10  mov     r15, rcx
0x14004ea13  mov     [rsp+1B0h+var_148], r8
0x14004ea18  xor     r13d, r13d
0x14004ea1b  mov     al, [r9+8]
0x14004ea1f  cmp     al, 63h ; 'c'
0x14004ea21  jnz     short loc_14004EA60
0x14004ea23  cmp     r8, 7Fh
0x14004ea27  ja      loc_14004ED70
0x14004ea2d  mov     [r9+0Bh], r13b
0x14004ea31  movaps  xmm0, xmmword ptr [r9]
0x14004ea35  movaps  [rsp+1B0h+var_170], xmm0
0x14004ea3a  mov     ecx, [r9+10h]
0x14004ea3e  mov     [rsp+1B0h+var_160], ecx
0x14004ea42  mov     rcx, [rbp+0B0h+arg_20]
0x14004ea49  mov     [rsp+1B0h+var_190], rcx
0x14004ea4e  lea     r9, [rsp+1B0h+var_170]
0x14004ea53  mov     rcx, r15
0x14004ea56  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x14004ea5b  jmp     loc_14004ED46
0x14004ea60  mov     edi, 2
0x14004ea65  cmp     [r9+0Ah], r13b
0x14004ea69  jnz     short loc_14004EA6F
0x14004ea6b  mov     [r9+0Ah], dil
0x14004ea6f  cmp     al, 42h ; 'B'
0x14004ea71  jz      short loc_14004EA98
0x14004ea73  cmp     al, 58h ; 'X'
0x14004ea75  jz      short loc_14004EA91
0x14004ea77  cmp     al, 62h ; 'b'
0x14004ea79  jz      short loc_14004EA98
0x14004ea7b  cmp     al, 6Fh ; 'o'
0x14004ea7d  jz      short loc_14004EA8A
0x14004ea7f  cmp     al, 78h ; 'x'
0x14004ea81  jz      short loc_14004EA91
0x14004ea83  mov     eax, 0Ah
0x14004ea88  jmp     short loc_14004EA9A
0x14004ea8a  mov     eax, 8
0x14004ea8f  jmp     short loc_14004EA9A
0x14004ea91  mov     eax, 10h
0x14004ea96  jmp     short loc_14004EA9A
0x14004ea98  mov     eax, edi
0x14004ea9a  mov     dword ptr [rsp+1B0h+var_190], eax
0x14004ea9e  mov     r9, r8
0x14004eaa1  lea     r8, [rbp+0B0h+var_4F]
0x14004eaa5  lea     rdx, [rbp+0B0h+var_90]
0x14004eaa9  lea     rcx, [rsp+1B0h+var_170]
0x14004eaae  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0_KH@Z; std::to_chars(char * const,char * const,unsigned __int64,int)
0x14004eab3  mov     r12, [rax]
0x14004eab6  lea     rcx, [rbp+0B0h+var_90]
0x14004eaba  mov     [rsp+1B0h+var_140], rcx
0x14004eabf  mov     eax, r12d
0x14004eac2  sub     eax, ecx
0x14004eac4  mov     [rsp+1B0h+var_17C], eax
0x14004eac8  cmp     [rsi+0Ah], dil
0x14004eacc  jz      short loc_14004EAD4
0x14004eace  inc     eax
0x14004ead0  mov     [rsp+1B0h+var_17C], eax
0x14004ead4  mov     r14d, 1
0x14004eada  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14004eade  jnz     short loc_14004EB07
0x14004eae0  lea     rcx, [rbp+0B0h+var_90]
0x14004eae4  lea     rdx, [rbp+0B0h+var_90]
0x14004eae8  cmp     rdx, r12
0x14004eaeb  jz      short loc_14004EB07
0x14004eaed  mov     dl, [rcx]
0x14004eaef  lea     eax, [rdx-61h]
0x14004eaf2  cmp     al, 19h
0x14004eaf4  ja      short loc_14004EAFB
0x14004eaf6  sub     dl, 20h ; ' '
0x14004eaf9  mov     [rcx], dl
0x14004eafb  add     rcx, r14
0x14004eafe  cmp     rcx, r12
0x14004eb01  jnz     short loc_14004EAED
0x14004eb03  mov     eax, [rsp+1B0h+var_17C]
0x14004eb07  mov     qword ptr [rbp+0B0h+var_130], r13
0x14004eb0b  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x14004eb0f  cmp     [rsi+0Bh], r13b
0x14004eb13  jz      short loc_14004EB94
0x14004eb15  mov     cl, [rsi+8]
0x14004eb18  cmp     cl, 42h ; 'B'
0x14004eb1b  jz      short loc_14004EB73
0x14004eb1d  cmp     cl, 58h ; 'X'
0x14004eb20  jz      short loc_14004EB6A
0x14004eb22  cmp     cl, 62h ; 'b'
0x14004eb25  jz      short loc_14004EB61
0x14004eb27  cmp     cl, 6Fh ; 'o'
0x14004eb2a  jz      short loc_14004EB3A
0x14004eb2c  cmp     cl, 78h ; 'x'
0x14004eb2f  jnz     short loc_14004EB52
0x14004eb31  lea     rcx, a0x; "0x"
0x14004eb38  jmp     short loc_14004EB7A
0x14004eb3a  cmp     [rsp+1B0h+var_148], r13
0x14004eb3f  jz      short loc_14004EB52
0x14004eb41  lea     rcx, a0; "0"
0x14004eb48  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14004eb4d  mov     edi, r14d
0x14004eb50  jmp     short loc_14004EB7F
0x14004eb52  mov     qword ptr [rsp+1B0h+var_170], r13
0x14004eb57  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14004eb5c  mov     edi, r13d
0x14004eb5f  jmp     short loc_14004EB84
0x14004eb61  lea     rcx, a0b; "0b"
0x14004eb68  jmp     short loc_14004EB7A
0x14004eb6a  lea     rcx, a0x_0; "0X"
0x14004eb71  jmp     short loc_14004EB7A
0x14004eb73  lea     rcx, a0b_0; "0B"
0x14004eb7a  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14004eb7f  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14004eb84  movaps  xmm0, [rsp+1B0h+var_170]
0x14004eb89  movdqa  [rbp+0B0h+var_130], xmm0
0x14004eb8e  add     eax, edi
0x14004eb90  mov     [rsp+1B0h+var_17C], eax
0x14004eb94  mov     [rsp+1B0h+var_150], r13d
0x14004eb99  xorps   xmm0, xmm0
0x14004eb9c  movups  [rbp+0B0h+var_D0], xmm0
0x14004eba0  mov     [rbp+0B0h+var_C0], r13
0x14004eba4  mov     [rbp+0B0h+var_B8], 0Fh
0x14004ebac  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14004ebb0  cmp     [rsi+0Ch], r13b
0x14004ebb4  jz      loc_14004ECAC
0x14004ebba  mov     rax, [rbp+0B0h+arg_20]
0x14004ebc1  test    rax, rax
0x14004ebc4  jz      short loc_14004EBDD
0x14004ebc6  mov     rcx, [rax+8]
0x14004ebca  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x14004ebcf  mov     rax, [rcx]
0x14004ebd2  mov     rax, [rax+8]
0x14004ebd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ebdb  jmp     short loc_14004EBEB
0x14004ebdd  mov     cl, r14b
0x14004ebe0  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004ebe6  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x14004ebeb  lea     rcx, [rsp+1B0h+var_170]
0x14004ebf0  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004ebf5  mov     r8, rax
0x14004ebf8  mov     rcx, [rax]
0x14004ebfb  mov     rax, [rcx+28h]
0x14004ebff  lea     rdx, [rbp+0B0h+var_B0]
0x14004ec03  mov     rcx, r8
0x14004ec06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec0b  lea     rdx, [rbp+0B0h+var_B0]
0x14004ec0f  lea     rcx, [rbp+0B0h+var_D0]
0x14004ec13  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004ec18  lea     rcx, [rbp+0B0h+var_B0]
0x14004ec1c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004ec21  nop
0x14004ec22  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x14004ec27  test    rcx, rcx
0x14004ec2a  jz      short loc_14004EC51
0x14004ec2c  mov     rax, [rcx]
0x14004ec2f  mov     rax, [rax+10h]
0x14004ec33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec38  mov     r8, rax
0x14004ec3b  test    rax, rax
0x14004ec3e  jz      short loc_14004EC51
0x14004ec40  mov     rcx, [rax]
0x14004ec43  mov     rax, [rcx]
0x14004ec46  mov     edx, r14d
0x14004ec49  mov     rcx, r8
0x14004ec4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec51  lea     rax, [rbp+0B0h+var_D0]
0x14004ec55  cmp     [rbp+0B0h+var_B8], 0Fh
0x14004ec5a  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14004ec5f  mov     r10, [rbp+0B0h+var_C0]
0x14004ec63  mov     edx, r13d
0x14004ec66  test    r10, r10
0x14004ec69  jz      short loc_14004EC9E
0x14004ec6b  mov     r8, r12
0x14004ec6e  sub     r8, [rsp+1B0h+var_140]
0x14004ec73  movsx   r9, byte ptr [rax]
0x14004ec77  cmp     r8, r9
0x14004ec7a  jbe     short loc_14004EC9E
0x14004ec7c  lea     r11, [r10+rax]
0x14004ec80  movsx   rcx, r9b
0x14004ec84  sub     r8, rcx
0x14004ec87  add     edx, r14d
0x14004ec8a  lea     rcx, [rax+1]
0x14004ec8e  cmp     rcx, r11
0x14004ec91  cmovnz  rax, rcx
0x14004ec95  movsx   r9, byte ptr [rax]
0x14004ec99  cmp     r8, r9
0x14004ec9c  ja      short loc_14004EC80
0x14004ec9e  mov     [rsp+1B0h+var_150], edx
0x14004eca2  mov     eax, [rsp+1B0h+var_17C]
0x14004eca6  add     eax, edx
0x14004eca8  mov     [rsp+1B0h+var_17C], eax
0x14004ecac  cmp     [rsi+0Dh], r13b
0x14004ecb0  jz      short loc_14004ECB8
0x14004ecb2  cmp     [rsi+9], r13b
0x14004ecb6  jz      short loc_14004ECBB
0x14004ecb8  mov     r14b, r13b
0x14004ecbb  mov     [rsp+1B0h+var_180], r14b
0x14004ecc0  mov     [rbp+0B0h+var_120], r12
0x14004ecc4  mov     [rbp+0B0h+var_118], rsi
0x14004ecc8  lea     rcx, [rsp+1B0h+var_148]
0x14004eccd  mov     [rbp+0B0h+var_110], rcx
0x14004ecd1  lea     rcx, [rbp+0B0h+var_130]
0x14004ecd5  mov     [rbp+0B0h+var_108], rcx
0x14004ecd9  lea     rcx, [rsp+1B0h+var_180]
0x14004ecde  mov     [rbp+0B0h+var_100], rcx
0x14004ece2  lea     rcx, [rsp+1B0h+var_17C]
0x14004ece7  mov     [rbp+0B0h+var_F8], rcx
0x14004eceb  lea     rcx, [rsp+1B0h+var_150]
0x14004ecf0  mov     [rbp+0B0h+var_F0], rcx
0x14004ecf4  lea     rcx, [rsp+1B0h+var_140]
0x14004ecf9  mov     [rbp+0B0h+var_E8], rcx
0x14004ecfd  lea     rcx, [rbp+0B0h+var_D0]
0x14004ed01  mov     [rbp+0B0h+var_E0], rcx
0x14004ed05  lea     rcx, [rbp+0B0h+arg_20]
0x14004ed0c  mov     [rbp+0B0h+var_D8], rcx
0x14004ed10  lea     rcx, [rbp+0B0h+var_120]
0x14004ed14  test    r14b, r14b
0x14004ed17  jz      short loc_14004ED26
0x14004ed19  mov     r8, rbx
0x14004ed1c  mov     rdx, r15
0x14004ed1f  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x14004ed24  jmp     short loc_14004ED3D
0x14004ed26  mov     [rsp+1B0h+var_188], rcx
0x14004ed2b  mov     r9, rsi
0x14004ed2e  mov     r8d, eax
0x14004ed31  mov     rdx, rbx
0x14004ed34  mov     rcx, r15
0x14004ed37  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14004ed3c  nop
0x14004ed3d  lea     rcx, [rbp+0B0h+var_D0]
0x14004ed41  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004ed46  mov     rax, r15
0x14004ed49  mov     rcx, [rbp+0B0h+var_40]
0x14004ed4d  xor     rcx, rsp; StackCookie
0x14004ed50  call    __security_check_cookie
0x14004ed55  mov     rbx, [rsp+1B0h+arg_8]
0x14004ed5d  add     rsp, 180h
0x14004ed64  pop     r15
0x14004ed66  pop     r14
0x14004ed68  pop     r13
0x14004ed6a  pop     r12
0x14004ed6c  pop     rdi
0x14004ed6d  pop     rsi
0x14004ed6e  pop     rbp
0x14004ed6f  retn
0x14004ed70  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x14004ed77  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

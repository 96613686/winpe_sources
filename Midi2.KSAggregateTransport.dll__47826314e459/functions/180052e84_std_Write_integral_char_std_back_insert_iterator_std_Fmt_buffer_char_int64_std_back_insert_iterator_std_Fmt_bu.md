# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180052e84`
- end: `0x18005323c`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_JU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180051498`

## callees

- `0x180005020`
- `0x18002e200`
- `0x1800342a8`
- `0x180034450`
- `0x180040fac`
- `0x18004e8bc`
- `0x180052098`
- `0x180052e84`
- `0x180053d44`
- `0x180054dfc`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18005309f`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18005309f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        __int64 a5)
{
  char v8; // al
  int v9; // edi
  int v10; // eax
  char *v11; // rcx
  char *v12; // r12
  int v13; // eax
  __int64 v14; // rdx
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
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
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

  v32 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( (unsigned __int64)(a3 + 128) > 0xFF )
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
  std::_Integer_to_chars<__int64>(&v29, &v40, v42, a3);
  v11 = &v40;
  v33 = &v40;
  v12 = (char *)v29;
  v13 = v29 - (unsigned int)&v40;
  v28 = v13;
  v14 = v32;
  if ( v32 < 0 )
  {
    v11 = v41;
    v33 = v41;
  }
  else if ( *((_BYTE *)a4 + 10) != 2 )
  {
    v28 = ++v13;
  }
  v15 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 && v11 != (char *)v29 )
  {
    do
    {
      if ( (unsigned __int8)(*v11 - 97) <= 0x19u )
        *v11 -= 32;
      ++v11;
    }
    while ( v11 != v12 );
    v13 = v28;
    v14 = v32;
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
  v31 = 0;
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
      v22 = v12 - v33;
      v23 = *v20;
      if ( v12 - v33 > v23 )
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
    v31 = v21;
    v13 = v21 + v28;
    v28 += v21;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v15 = 0;
  v27 = v15;
  v35[0] = v12;
  v35[1] = a4;
  v35[2] = &v32;
  v35[3] = &v34;
  v35[4] = &v27;
  v35[5] = &v28;
  v35[6] = &v31;
  v35[7] = &v33;
  v35[8] = &v36;
  v35[9] = &a5;
  if ( v15 )
    `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>'::`2'::_lambda_1_::operator()(
      v35,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_D_std___std__U___Basic_format_specs_D_2_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std___J_2_YA_AV12_V12__JU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_D_std___0_V10_HAEBU___Basic_format_specs_D_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_DV__back_insert_iterator_V___Fmt_buffer_D_std___std___J_0_YA_AV10_0_JU20_V_Lazy_locale_0__Z__Z(
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
0x180052e84  mov     [rsp-8+arg_8], rbx
0x180052e89  push    rbp
0x180052e8a  push    rsi
0x180052e8b  push    rdi
0x180052e8c  push    r12
0x180052e8e  push    r13
0x180052e90  push    r14
0x180052e92  push    r15
0x180052e94  lea     rbp, [rsp-80h]
0x180052e99  sub     rsp, 180h
0x180052ea0  mov     rax, cs:__security_cookie
0x180052ea7  xor     rax, rsp
0x180052eaa  mov     [rbp+0B0h+var_40], rax
0x180052eae  mov     rsi, r9
0x180052eb1  mov     rbx, rdx
0x180052eb4  mov     r15, rcx
0x180052eb7  mov     [rsp+1B0h+var_148], r8
0x180052ebc  xor     r13d, r13d
0x180052ebf  mov     al, [r9+8]
0x180052ec3  cmp     al, 63h ; 'c'
0x180052ec5  jnz     short loc_180052F0D
0x180052ec7  lea     rax, [r8+80h]
0x180052ece  cmp     rax, 0FFh
0x180052ed4  ja      loc_18005322F
0x180052eda  mov     [r9+0Bh], r13b
0x180052ede  movaps  xmm0, xmmword ptr [r9]
0x180052ee2  movaps  [rsp+1B0h+var_170], xmm0
0x180052ee7  mov     ecx, [r9+10h]
0x180052eeb  mov     [rsp+1B0h+var_160], ecx
0x180052eef  mov     rcx, [rbp+0B0h+arg_20]
0x180052ef6  mov     [rsp+1B0h+var_190], rcx
0x180052efb  lea     r9, [rsp+1B0h+var_170]
0x180052f00  mov     rcx, r15
0x180052f03  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180052f08  jmp     loc_180053205
0x180052f0d  mov     edi, 2
0x180052f12  cmp     [r9+0Ah], r13b
0x180052f16  jnz     short loc_180052F1C
0x180052f18  mov     [r9+0Ah], dil
0x180052f1c  cmp     al, 42h ; 'B'
0x180052f1e  jz      short loc_180052F45
0x180052f20  cmp     al, 58h ; 'X'
0x180052f22  jz      short loc_180052F3E
0x180052f24  cmp     al, 62h ; 'b'
0x180052f26  jz      short loc_180052F45
0x180052f28  cmp     al, 6Fh ; 'o'
0x180052f2a  jz      short loc_180052F37
0x180052f2c  cmp     al, 78h ; 'x'
0x180052f2e  jz      short loc_180052F3E
0x180052f30  mov     eax, 0Ah
0x180052f35  jmp     short loc_180052F47
0x180052f37  mov     eax, 8
0x180052f3c  jmp     short loc_180052F47
0x180052f3e  mov     eax, 10h
0x180052f43  jmp     short loc_180052F47
0x180052f45  mov     eax, edi
0x180052f47  mov     dword ptr [rsp+1B0h+var_190], eax
0x180052f4b  mov     r9, r8
0x180052f4e  lea     r8, [rbp+0B0h+var_4F]
0x180052f52  lea     rdx, [rbp+0B0h+var_90]
0x180052f56  lea     rcx, [rsp+1B0h+var_170]
0x180052f5b  call    ??$_Integer_to_chars@_J@std@@YA?AUto_chars_result@0@PEADQEAD_JH@Z; std::_Integer_to_chars<__int64>(char *,char * const,__int64,int)
0x180052f60  lea     rcx, [rbp+0B0h+var_90]
0x180052f64  mov     [rsp+1B0h+var_140], rcx
0x180052f69  mov     r12, qword ptr [rsp+1B0h+var_170]
0x180052f6e  mov     eax, r12d
0x180052f71  sub     eax, ecx
0x180052f73  mov     [rsp+1B0h+var_17C], eax
0x180052f77  mov     rdx, [rsp+1B0h+var_148]
0x180052f7c  test    rdx, rdx
0x180052f7f  js      short loc_180052F8F
0x180052f81  cmp     [rsi+0Ah], dil
0x180052f85  jz      short loc_180052F98
0x180052f87  inc     eax
0x180052f89  mov     [rsp+1B0h+var_17C], eax
0x180052f8d  jmp     short loc_180052F98
0x180052f8f  lea     rcx, [rbp+0B0h+var_8F]
0x180052f93  mov     [rsp+1B0h+var_140], rcx
0x180052f98  mov     r14d, 1
0x180052f9e  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180052fa2  jnz     short loc_180052FC8
0x180052fa4  cmp     rcx, r12
0x180052fa7  jz      short loc_180052FC8
0x180052fa9  mov     dl, [rcx]
0x180052fab  lea     eax, [rdx-61h]
0x180052fae  cmp     al, 19h
0x180052fb0  ja      short loc_180052FB7
0x180052fb2  sub     dl, 20h ; ' '
0x180052fb5  mov     [rcx], dl
0x180052fb7  add     rcx, r14
0x180052fba  cmp     rcx, r12
0x180052fbd  jnz     short loc_180052FA9
0x180052fbf  mov     eax, [rsp+1B0h+var_17C]
0x180052fc3  mov     rdx, [rsp+1B0h+var_148]
0x180052fc8  mov     qword ptr [rbp+0B0h+var_130], r13
0x180052fcc  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180052fd0  cmp     [rsi+0Bh], r13b
0x180052fd4  jz      short loc_180053053
0x180052fd6  mov     cl, [rsi+8]
0x180052fd9  cmp     cl, 42h ; 'B'
0x180052fdc  jz      short loc_180053032
0x180052fde  cmp     cl, 58h ; 'X'
0x180052fe1  jz      short loc_180053029
0x180052fe3  cmp     cl, 62h ; 'b'
0x180052fe6  jz      short loc_180053020
0x180052fe8  cmp     cl, 6Fh ; 'o'
0x180052feb  jz      short loc_180052FFB
0x180052fed  cmp     cl, 78h ; 'x'
0x180052ff0  jnz     short loc_180053011
0x180052ff2  lea     rcx, a0x; "0x"
0x180052ff9  jmp     short loc_180053039
0x180052ffb  test    rdx, rdx
0x180052ffe  jz      short loc_180053011
0x180053000  lea     rcx, a0; "0"
0x180053007  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x18005300c  mov     edi, r14d
0x18005300f  jmp     short loc_18005303E
0x180053011  mov     qword ptr [rsp+1B0h+var_170], r13
0x180053016  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18005301b  mov     edi, r13d
0x18005301e  jmp     short loc_180053043
0x180053020  lea     rcx, a0b; "0b"
0x180053027  jmp     short loc_180053039
0x180053029  lea     rcx, a0x_0; "0X"
0x180053030  jmp     short loc_180053039
0x180053032  lea     rcx, a0b_0; "0B"
0x180053039  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x18005303e  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180053043  movaps  xmm0, [rsp+1B0h+var_170]
0x180053048  movdqa  [rbp+0B0h+var_130], xmm0
0x18005304d  add     eax, edi
0x18005304f  mov     [rsp+1B0h+var_17C], eax
0x180053053  mov     [rsp+1B0h+var_150], r13d
0x180053058  xorps   xmm0, xmm0
0x18005305b  movups  [rbp+0B0h+var_D0], xmm0
0x18005305f  mov     [rbp+0B0h+var_C0], r13
0x180053063  mov     [rbp+0B0h+var_B8], 0Fh
0x18005306b  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x18005306f  cmp     [rsi+0Ch], r13b
0x180053073  jz      loc_18005316B
0x180053079  mov     rax, [rbp+0B0h+arg_20]
0x180053080  test    rax, rax
0x180053083  jz      short loc_18005309C
0x180053085  mov     rcx, [rax+8]
0x180053089  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x18005308e  mov     rax, [rcx]
0x180053091  mov     rax, [rax+8]
0x180053095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005309a  jmp     short loc_1800530AA
0x18005309c  mov     cl, r14b
0x18005309f  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1800530a5  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x1800530aa  lea     rcx, [rsp+1B0h+var_170]
0x1800530af  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x1800530b4  mov     r8, rax
0x1800530b7  mov     rcx, [rax]
0x1800530ba  mov     rax, [rcx+28h]
0x1800530be  lea     rdx, [rbp+0B0h+var_B0]
0x1800530c2  mov     rcx, r8
0x1800530c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530ca  lea     rdx, [rbp+0B0h+var_B0]
0x1800530ce  lea     rcx, [rbp+0B0h+var_D0]
0x1800530d2  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800530d7  lea     rcx, [rbp+0B0h+var_B0]
0x1800530db  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800530e0  nop
0x1800530e1  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x1800530e6  test    rcx, rcx
0x1800530e9  jz      short loc_180053110
0x1800530eb  mov     rax, [rcx]
0x1800530ee  mov     rax, [rax+10h]
0x1800530f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530f7  mov     r8, rax
0x1800530fa  test    rax, rax
0x1800530fd  jz      short loc_180053110
0x1800530ff  mov     rcx, [rax]
0x180053102  mov     rax, [rcx]
0x180053105  mov     edx, r14d
0x180053108  mov     rcx, r8
0x18005310b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053110  lea     rax, [rbp+0B0h+var_D0]
0x180053114  cmp     [rbp+0B0h+var_B8], 0Fh
0x180053119  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x18005311e  mov     r10, [rbp+0B0h+var_C0]
0x180053122  mov     edx, r13d
0x180053125  test    r10, r10
0x180053128  jz      short loc_18005315D
0x18005312a  mov     r8, r12
0x18005312d  sub     r8, [rsp+1B0h+var_140]
0x180053132  movsx   r9, byte ptr [rax]
0x180053136  cmp     r8, r9
0x180053139  jbe     short loc_18005315D
0x18005313b  lea     r11, [r10+rax]
0x18005313f  movsx   rcx, r9b
0x180053143  sub     r8, rcx
0x180053146  add     edx, r14d
0x180053149  lea     rcx, [rax+1]
0x18005314d  cmp     rcx, r11
0x180053150  cmovnz  rax, rcx
0x180053154  movsx   r9, byte ptr [rax]
0x180053158  cmp     r8, r9
0x18005315b  ja      short loc_18005313F
0x18005315d  mov     [rsp+1B0h+var_150], edx
0x180053161  mov     eax, [rsp+1B0h+var_17C]
0x180053165  add     eax, edx
0x180053167  mov     [rsp+1B0h+var_17C], eax
0x18005316b  cmp     [rsi+0Dh], r13b
0x18005316f  jz      short loc_180053177
0x180053171  cmp     [rsi+9], r13b
0x180053175  jz      short loc_18005317A
0x180053177  mov     r14b, r13b
0x18005317a  mov     [rsp+1B0h+var_180], r14b
0x18005317f  mov     [rbp+0B0h+var_120], r12
0x180053183  mov     [rbp+0B0h+var_118], rsi
0x180053187  lea     rcx, [rsp+1B0h+var_148]
0x18005318c  mov     [rbp+0B0h+var_110], rcx
0x180053190  lea     rcx, [rbp+0B0h+var_130]
0x180053194  mov     [rbp+0B0h+var_108], rcx
0x180053198  lea     rcx, [rsp+1B0h+var_180]
0x18005319d  mov     [rbp+0B0h+var_100], rcx
0x1800531a1  lea     rcx, [rsp+1B0h+var_17C]
0x1800531a6  mov     [rbp+0B0h+var_F8], rcx
0x1800531aa  lea     rcx, [rsp+1B0h+var_150]
0x1800531af  mov     [rbp+0B0h+var_F0], rcx
0x1800531b3  lea     rcx, [rsp+1B0h+var_140]
0x1800531b8  mov     [rbp+0B0h+var_E8], rcx
0x1800531bc  lea     rcx, [rbp+0B0h+var_D0]
0x1800531c0  mov     [rbp+0B0h+var_E0], rcx
0x1800531c4  lea     rcx, [rbp+0B0h+arg_20]
0x1800531cb  mov     [rbp+0B0h+var_D8], rcx
0x1800531cf  lea     rcx, [rbp+0B0h+var_120]
0x1800531d3  test    r14b, r14b
0x1800531d6  jz      short loc_1800531E5
0x1800531d8  mov     r8, rbx
0x1800531db  mov     rdx, r15
0x1800531de  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800531e3  jmp     short loc_1800531FC
0x1800531e5  mov     [rsp+1B0h+var_188], rcx
0x1800531ea  mov     r9, rsi
0x1800531ed  mov     r8d, eax
0x1800531f0  mov     rdx, rbx
0x1800531f3  mov     rcx, r15
0x1800531f6  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@2@YA?AV12@V12@_JU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@0@YA?AV10@0_JU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800531fb  nop
0x1800531fc  lea     rcx, [rbp+0B0h+var_D0]
0x180053200  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180053205  mov     rax, r15
0x180053208  mov     rcx, [rbp+0B0h+var_40]
0x18005320c  xor     rcx, rsp; StackCookie
0x18005320f  call    __security_check_cookie
0x180053214  mov     rbx, [rsp+1B0h+arg_8]
0x18005321c  add     rsp, 180h
0x180053223  pop     r15
0x180053225  pop     r14
0x180053227  pop     r13
0x180053229  pop     r12
0x18005322b  pop     rdi
0x18005322c  pop     rsi
0x18005322d  pop     rbp
0x18005322e  retn
0x18005322f  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180053236  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

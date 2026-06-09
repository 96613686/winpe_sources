# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x1800288b4`
- end: `0x180028c6c`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_JU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180023e98`
- `0x180025a14`
- `0x180027ac8`
- `0x1800288b4`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002bb44`
- `0x18002dd84`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180028acf`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180028acf`

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
0x1800288b4  mov     [rsp-8+arg_8], rbx
0x1800288b9  push    rbp
0x1800288ba  push    rsi
0x1800288bb  push    rdi
0x1800288bc  push    r12
0x1800288be  push    r13
0x1800288c0  push    r14
0x1800288c2  push    r15
0x1800288c4  lea     rbp, [rsp-80h]
0x1800288c9  sub     rsp, 180h
0x1800288d0  mov     rax, cs:__security_cookie
0x1800288d7  xor     rax, rsp
0x1800288da  mov     [rbp+0B0h+var_40], rax
0x1800288de  mov     rsi, r9
0x1800288e1  mov     rbx, rdx
0x1800288e4  mov     r15, rcx
0x1800288e7  mov     [rsp+1B0h+var_148], r8
0x1800288ec  xor     r13d, r13d
0x1800288ef  mov     al, [r9+8]
0x1800288f3  cmp     al, 63h ; 'c'
0x1800288f5  jnz     short loc_18002893D
0x1800288f7  lea     rax, [r8+80h]
0x1800288fe  cmp     rax, 0FFh
0x180028904  ja      loc_180028C5F
0x18002890a  mov     [r9+0Bh], r13b
0x18002890e  movaps  xmm0, xmmword ptr [r9]
0x180028912  movaps  [rsp+1B0h+var_170], xmm0
0x180028917  mov     ecx, [r9+10h]
0x18002891b  mov     [rsp+1B0h+var_160], ecx
0x18002891f  mov     rcx, [rbp+0B0h+arg_20]
0x180028926  mov     [rsp+1B0h+var_190], rcx
0x18002892b  lea     r9, [rsp+1B0h+var_170]
0x180028930  mov     rcx, r15
0x180028933  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180028938  jmp     loc_180028C35
0x18002893d  mov     edi, 2
0x180028942  cmp     [r9+0Ah], r13b
0x180028946  jnz     short loc_18002894C
0x180028948  mov     [r9+0Ah], dil
0x18002894c  cmp     al, 42h ; 'B'
0x18002894e  jz      short loc_180028975
0x180028950  cmp     al, 58h ; 'X'
0x180028952  jz      short loc_18002896E
0x180028954  cmp     al, 62h ; 'b'
0x180028956  jz      short loc_180028975
0x180028958  cmp     al, 6Fh ; 'o'
0x18002895a  jz      short loc_180028967
0x18002895c  cmp     al, 78h ; 'x'
0x18002895e  jz      short loc_18002896E
0x180028960  mov     eax, 0Ah
0x180028965  jmp     short loc_180028977
0x180028967  mov     eax, 8
0x18002896c  jmp     short loc_180028977
0x18002896e  mov     eax, 10h
0x180028973  jmp     short loc_180028977
0x180028975  mov     eax, edi
0x180028977  mov     dword ptr [rsp+1B0h+var_190], eax
0x18002897b  mov     r9, r8
0x18002897e  lea     r8, [rbp+0B0h+var_4F]
0x180028982  lea     rdx, [rbp+0B0h+var_90]
0x180028986  lea     rcx, [rsp+1B0h+var_170]
0x18002898b  call    ??$_Integer_to_chars@_J@std@@YA?AUto_chars_result@0@PEADQEAD_JH@Z; std::_Integer_to_chars<__int64>(char *,char * const,__int64,int)
0x180028990  lea     rcx, [rbp+0B0h+var_90]
0x180028994  mov     [rsp+1B0h+var_140], rcx
0x180028999  mov     r12, qword ptr [rsp+1B0h+var_170]
0x18002899e  mov     eax, r12d
0x1800289a1  sub     eax, ecx
0x1800289a3  mov     [rsp+1B0h+var_17C], eax
0x1800289a7  mov     rdx, [rsp+1B0h+var_148]
0x1800289ac  test    rdx, rdx
0x1800289af  js      short loc_1800289BF
0x1800289b1  cmp     [rsi+0Ah], dil
0x1800289b5  jz      short loc_1800289C8
0x1800289b7  inc     eax
0x1800289b9  mov     [rsp+1B0h+var_17C], eax
0x1800289bd  jmp     short loc_1800289C8
0x1800289bf  lea     rcx, [rbp+0B0h+var_8F]
0x1800289c3  mov     [rsp+1B0h+var_140], rcx
0x1800289c8  mov     r14d, 1
0x1800289ce  cmp     byte ptr [rsi+8], 58h ; 'X'
0x1800289d2  jnz     short loc_1800289F8
0x1800289d4  cmp     rcx, r12
0x1800289d7  jz      short loc_1800289F8
0x1800289d9  mov     dl, [rcx]
0x1800289db  lea     eax, [rdx-61h]
0x1800289de  cmp     al, 19h
0x1800289e0  ja      short loc_1800289E7
0x1800289e2  sub     dl, 20h ; ' '
0x1800289e5  mov     [rcx], dl
0x1800289e7  add     rcx, r14
0x1800289ea  cmp     rcx, r12
0x1800289ed  jnz     short loc_1800289D9
0x1800289ef  mov     eax, [rsp+1B0h+var_17C]
0x1800289f3  mov     rdx, [rsp+1B0h+var_148]
0x1800289f8  mov     qword ptr [rbp+0B0h+var_130], r13
0x1800289fc  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180028a00  cmp     [rsi+0Bh], r13b
0x180028a04  jz      short loc_180028A83
0x180028a06  mov     cl, [rsi+8]
0x180028a09  cmp     cl, 42h ; 'B'
0x180028a0c  jz      short loc_180028A62
0x180028a0e  cmp     cl, 58h ; 'X'
0x180028a11  jz      short loc_180028A59
0x180028a13  cmp     cl, 62h ; 'b'
0x180028a16  jz      short loc_180028A50
0x180028a18  cmp     cl, 6Fh ; 'o'
0x180028a1b  jz      short loc_180028A2B
0x180028a1d  cmp     cl, 78h ; 'x'
0x180028a20  jnz     short loc_180028A41
0x180028a22  lea     rcx, a0x; "0x"
0x180028a29  jmp     short loc_180028A69
0x180028a2b  test    rdx, rdx
0x180028a2e  jz      short loc_180028A41
0x180028a30  lea     rcx, a0; "0"
0x180028a37  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180028a3c  mov     edi, r14d
0x180028a3f  jmp     short loc_180028A6E
0x180028a41  mov     qword ptr [rsp+1B0h+var_170], r13
0x180028a46  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180028a4b  mov     edi, r13d
0x180028a4e  jmp     short loc_180028A73
0x180028a50  lea     rcx, a0b; "0b"
0x180028a57  jmp     short loc_180028A69
0x180028a59  lea     rcx, a0x_0; "0X"
0x180028a60  jmp     short loc_180028A69
0x180028a62  lea     rcx, a0b_0; "0B"
0x180028a69  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x180028a6e  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180028a73  movaps  xmm0, [rsp+1B0h+var_170]
0x180028a78  movdqa  [rbp+0B0h+var_130], xmm0
0x180028a7d  add     eax, edi
0x180028a7f  mov     [rsp+1B0h+var_17C], eax
0x180028a83  mov     [rsp+1B0h+var_150], r13d
0x180028a88  xorps   xmm0, xmm0
0x180028a8b  movups  [rbp+0B0h+var_D0], xmm0
0x180028a8f  mov     [rbp+0B0h+var_C0], r13
0x180028a93  mov     [rbp+0B0h+var_B8], 0Fh
0x180028a9b  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180028a9f  cmp     [rsi+0Ch], r13b
0x180028aa3  jz      loc_180028B9B
0x180028aa9  mov     rax, [rbp+0B0h+arg_20]
0x180028ab0  test    rax, rax
0x180028ab3  jz      short loc_180028ACC
0x180028ab5  mov     rcx, [rax+8]
0x180028ab9  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x180028abe  mov     rax, [rcx]
0x180028ac1  mov     rax, [rax+8]
0x180028ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028aca  jmp     short loc_180028ADA
0x180028acc  mov     cl, r14b
0x180028acf  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180028ad5  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180028ada  lea     rcx, [rsp+1B0h+var_170]
0x180028adf  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180028ae4  mov     r8, rax
0x180028ae7  mov     rcx, [rax]
0x180028aea  mov     rax, [rcx+28h]
0x180028aee  lea     rdx, [rbp+0B0h+var_B0]
0x180028af2  mov     rcx, r8
0x180028af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028afa  lea     rdx, [rbp+0B0h+var_B0]
0x180028afe  lea     rcx, [rbp+0B0h+var_D0]
0x180028b02  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180028b07  lea     rcx, [rbp+0B0h+var_B0]
0x180028b0b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028b10  nop
0x180028b11  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180028b16  test    rcx, rcx
0x180028b19  jz      short loc_180028B40
0x180028b1b  mov     rax, [rcx]
0x180028b1e  mov     rax, [rax+10h]
0x180028b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b27  mov     r8, rax
0x180028b2a  test    rax, rax
0x180028b2d  jz      short loc_180028B40
0x180028b2f  mov     rcx, [rax]
0x180028b32  mov     rax, [rcx]
0x180028b35  mov     edx, r14d
0x180028b38  mov     rcx, r8
0x180028b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b40  lea     rax, [rbp+0B0h+var_D0]
0x180028b44  cmp     [rbp+0B0h+var_B8], 0Fh
0x180028b49  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180028b4e  mov     r10, [rbp+0B0h+var_C0]
0x180028b52  mov     edx, r13d
0x180028b55  test    r10, r10
0x180028b58  jz      short loc_180028B8D
0x180028b5a  mov     r8, r12
0x180028b5d  sub     r8, [rsp+1B0h+var_140]
0x180028b62  movsx   r9, byte ptr [rax]
0x180028b66  cmp     r8, r9
0x180028b69  jbe     short loc_180028B8D
0x180028b6b  lea     r11, [r10+rax]
0x180028b6f  movsx   rcx, r9b
0x180028b73  sub     r8, rcx
0x180028b76  add     edx, r14d
0x180028b79  lea     rcx, [rax+1]
0x180028b7d  cmp     rcx, r11
0x180028b80  cmovnz  rax, rcx
0x180028b84  movsx   r9, byte ptr [rax]
0x180028b88  cmp     r8, r9
0x180028b8b  ja      short loc_180028B6F
0x180028b8d  mov     [rsp+1B0h+var_150], edx
0x180028b91  mov     eax, [rsp+1B0h+var_17C]
0x180028b95  add     eax, edx
0x180028b97  mov     [rsp+1B0h+var_17C], eax
0x180028b9b  cmp     [rsi+0Dh], r13b
0x180028b9f  jz      short loc_180028BA7
0x180028ba1  cmp     [rsi+9], r13b
0x180028ba5  jz      short loc_180028BAA
0x180028ba7  mov     r14b, r13b
0x180028baa  mov     [rsp+1B0h+var_180], r14b
0x180028baf  mov     [rbp+0B0h+var_120], r12
0x180028bb3  mov     [rbp+0B0h+var_118], rsi
0x180028bb7  lea     rcx, [rsp+1B0h+var_148]
0x180028bbc  mov     [rbp+0B0h+var_110], rcx
0x180028bc0  lea     rcx, [rbp+0B0h+var_130]
0x180028bc4  mov     [rbp+0B0h+var_108], rcx
0x180028bc8  lea     rcx, [rsp+1B0h+var_180]
0x180028bcd  mov     [rbp+0B0h+var_100], rcx
0x180028bd1  lea     rcx, [rsp+1B0h+var_17C]
0x180028bd6  mov     [rbp+0B0h+var_F8], rcx
0x180028bda  lea     rcx, [rsp+1B0h+var_150]
0x180028bdf  mov     [rbp+0B0h+var_F0], rcx
0x180028be3  lea     rcx, [rsp+1B0h+var_140]
0x180028be8  mov     [rbp+0B0h+var_E8], rcx
0x180028bec  lea     rcx, [rbp+0B0h+var_D0]
0x180028bf0  mov     [rbp+0B0h+var_E0], rcx
0x180028bf4  lea     rcx, [rbp+0B0h+arg_20]
0x180028bfb  mov     [rbp+0B0h+var_D8], rcx
0x180028bff  lea     rcx, [rbp+0B0h+var_120]
0x180028c03  test    r14b, r14b
0x180028c06  jz      short loc_180028C15
0x180028c08  mov     r8, rbx
0x180028c0b  mov     rdx, r15
0x180028c0e  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180028c13  jmp     short loc_180028C2C
0x180028c15  mov     [rsp+1B0h+var_188], rcx
0x180028c1a  mov     r9, rsi
0x180028c1d  mov     r8d, eax
0x180028c20  mov     rdx, rbx
0x180028c23  mov     rcx, r15
0x180028c26  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@2@YA?AV12@V12@_JU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@0@YA?AV10@0_JU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180028c2b  nop
0x180028c2c  lea     rcx, [rbp+0B0h+var_D0]
0x180028c30  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028c35  mov     rax, r15
0x180028c38  mov     rcx, [rbp+0B0h+var_40]
0x180028c3c  xor     rcx, rsp; StackCookie
0x180028c3f  call    __security_check_cookie
0x180028c44  mov     rbx, [rsp+1B0h+arg_8]
0x180028c4c  add     rsp, 180h
0x180028c53  pop     r15
0x180028c55  pop     r14
0x180028c57  pop     r13
0x180028c59  pop     r12
0x180028c5b  pop     rdi
0x180028c5c  pop     rsi
0x180028c5d  pop     rbp
0x180028c5e  retn
0x180028c5f  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180028c66  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x14004e27c`
- end: `0x14004e619`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@IU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x1400498e8`
- `0x14004d704`
- `0x14004e27c`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x14005175c`
- `0x140054144`
- `0x140055a78`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004e47c`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004e47c`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned int>(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
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
0x14004e27c  mov     [rsp-8+arg_8], rbx
0x14004e281  push    rbp
0x14004e282  push    rsi
0x14004e283  push    rdi
0x14004e284  push    r12
0x14004e286  push    r13
0x14004e288  push    r14
0x14004e28a  push    r15
0x14004e28c  lea     rbp, [rsp-80h]
0x14004e291  sub     rsp, 180h
0x14004e298  mov     rax, cs:__security_cookie
0x14004e29f  xor     rax, rsp
0x14004e2a2  mov     [rbp+0B0h+var_40], rax
0x14004e2a6  mov     rsi, r9
0x14004e2a9  mov     rbx, rdx
0x14004e2ac  mov     r15, rcx
0x14004e2af  mov     [rsp+1B0h+var_148], r8d
0x14004e2b4  xor     r13d, r13d
0x14004e2b7  mov     al, [r9+8]
0x14004e2bb  cmp     al, 63h ; 'c'
0x14004e2bd  jnz     short loc_14004E2FC
0x14004e2bf  cmp     r8d, 7Fh
0x14004e2c3  ja      loc_14004E60C
0x14004e2c9  mov     [r9+0Bh], r13b
0x14004e2cd  movaps  xmm0, xmmword ptr [r9]
0x14004e2d1  movaps  [rsp+1B0h+var_170], xmm0
0x14004e2d6  mov     ecx, [r9+10h]
0x14004e2da  mov     [rsp+1B0h+var_160], ecx
0x14004e2de  mov     rcx, [rbp+0B0h+arg_20]
0x14004e2e5  mov     [rsp+1B0h+var_190], rcx
0x14004e2ea  lea     r9, [rsp+1B0h+var_170]
0x14004e2ef  mov     rcx, r15
0x14004e2f2  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x14004e2f7  jmp     loc_14004E5E2
0x14004e2fc  mov     edi, 2
0x14004e301  cmp     [r9+0Ah], r13b
0x14004e305  jnz     short loc_14004E30B
0x14004e307  mov     [r9+0Ah], dil
0x14004e30b  cmp     al, 42h ; 'B'
0x14004e30d  jz      short loc_14004E334
0x14004e30f  cmp     al, 58h ; 'X'
0x14004e311  jz      short loc_14004E32D
0x14004e313  cmp     al, 62h ; 'b'
0x14004e315  jz      short loc_14004E334
0x14004e317  cmp     al, 6Fh ; 'o'
0x14004e319  jz      short loc_14004E326
0x14004e31b  cmp     al, 78h ; 'x'
0x14004e31d  jz      short loc_14004E32D
0x14004e31f  mov     eax, 0Ah
0x14004e324  jmp     short loc_14004E336
0x14004e326  mov     eax, 8
0x14004e32b  jmp     short loc_14004E336
0x14004e32d  mov     eax, 10h
0x14004e332  jmp     short loc_14004E336
0x14004e334  mov     eax, edi
0x14004e336  mov     dword ptr [rsp+1B0h+var_190], eax
0x14004e33a  mov     r9d, r8d
0x14004e33d  lea     r8, [rbp+0B0h+var_4F]
0x14004e341  lea     rdx, [rbp+0B0h+var_90]
0x14004e345  lea     rcx, [rsp+1B0h+var_170]
0x14004e34a  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0IH@Z; std::to_chars(char * const,char * const,uint,int)
0x14004e34f  mov     r12, [rax]
0x14004e352  lea     rcx, [rbp+0B0h+var_90]
0x14004e356  mov     [rsp+1B0h+var_140], rcx
0x14004e35b  mov     eax, r12d
0x14004e35e  sub     eax, ecx
0x14004e360  mov     [rsp+1B0h+var_17C], eax
0x14004e364  cmp     [rsi+0Ah], dil
0x14004e368  jz      short loc_14004E370
0x14004e36a  inc     eax
0x14004e36c  mov     [rsp+1B0h+var_17C], eax
0x14004e370  mov     r14d, 1
0x14004e376  cmp     byte ptr [rsi+8], 58h ; 'X'
0x14004e37a  jnz     short loc_14004E3A3
0x14004e37c  lea     rcx, [rbp+0B0h+var_90]
0x14004e380  lea     rdx, [rbp+0B0h+var_90]
0x14004e384  cmp     rdx, r12
0x14004e387  jz      short loc_14004E3A3
0x14004e389  mov     dl, [rcx]
0x14004e38b  lea     eax, [rdx-61h]
0x14004e38e  cmp     al, 19h
0x14004e390  ja      short loc_14004E397
0x14004e392  sub     dl, 20h ; ' '
0x14004e395  mov     [rcx], dl
0x14004e397  add     rcx, r14
0x14004e39a  cmp     rcx, r12
0x14004e39d  jnz     short loc_14004E389
0x14004e39f  mov     eax, [rsp+1B0h+var_17C]
0x14004e3a3  mov     qword ptr [rbp+0B0h+var_130], r13
0x14004e3a7  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x14004e3ab  cmp     [rsi+0Bh], r13b
0x14004e3af  jz      short loc_14004E430
0x14004e3b1  mov     cl, [rsi+8]
0x14004e3b4  cmp     cl, 42h ; 'B'
0x14004e3b7  jz      short loc_14004E40F
0x14004e3b9  cmp     cl, 58h ; 'X'
0x14004e3bc  jz      short loc_14004E406
0x14004e3be  cmp     cl, 62h ; 'b'
0x14004e3c1  jz      short loc_14004E3FD
0x14004e3c3  cmp     cl, 6Fh ; 'o'
0x14004e3c6  jz      short loc_14004E3D6
0x14004e3c8  cmp     cl, 78h ; 'x'
0x14004e3cb  jnz     short loc_14004E3EE
0x14004e3cd  lea     rcx, a0x; "0x"
0x14004e3d4  jmp     short loc_14004E416
0x14004e3d6  cmp     [rsp+1B0h+var_148], r13d
0x14004e3db  jz      short loc_14004E3EE
0x14004e3dd  lea     rcx, a0; "0"
0x14004e3e4  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x14004e3e9  mov     edi, r14d
0x14004e3ec  jmp     short loc_14004E41B
0x14004e3ee  mov     qword ptr [rsp+1B0h+var_170], r13
0x14004e3f3  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x14004e3f8  mov     edi, r13d
0x14004e3fb  jmp     short loc_14004E420
0x14004e3fd  lea     rcx, a0b; "0b"
0x14004e404  jmp     short loc_14004E416
0x14004e406  lea     rcx, a0x_0; "0X"
0x14004e40d  jmp     short loc_14004E416
0x14004e40f  lea     rcx, a0b_0; "0B"
0x14004e416  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x14004e41b  mov     qword ptr [rsp+1B0h+var_170], rcx
0x14004e420  movaps  xmm0, [rsp+1B0h+var_170]
0x14004e425  movdqa  [rbp+0B0h+var_130], xmm0
0x14004e42a  add     eax, edi
0x14004e42c  mov     [rsp+1B0h+var_17C], eax
0x14004e430  mov     [rsp+1B0h+var_150], r13d
0x14004e435  xorps   xmm0, xmm0
0x14004e438  movups  [rbp+0B0h+var_D0], xmm0
0x14004e43c  mov     [rbp+0B0h+var_C0], r13
0x14004e440  mov     [rbp+0B0h+var_B8], 0Fh
0x14004e448  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x14004e44c  cmp     [rsi+0Ch], r13b
0x14004e450  jz      loc_14004E548
0x14004e456  mov     rax, [rbp+0B0h+arg_20]
0x14004e45d  test    rax, rax
0x14004e460  jz      short loc_14004E479
0x14004e462  mov     rcx, [rax+8]
0x14004e466  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x14004e46b  mov     rax, [rcx]
0x14004e46e  mov     rax, [rax+8]
0x14004e472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e477  jmp     short loc_14004E487
0x14004e479  mov     cl, r14b
0x14004e47c  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004e482  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x14004e487  lea     rcx, [rsp+1B0h+var_170]
0x14004e48c  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004e491  mov     r8, rax
0x14004e494  mov     rcx, [rax]
0x14004e497  mov     rax, [rcx+28h]
0x14004e49b  lea     rdx, [rbp+0B0h+var_B0]
0x14004e49f  mov     rcx, r8
0x14004e4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e4a7  lea     rdx, [rbp+0B0h+var_B0]
0x14004e4ab  lea     rcx, [rbp+0B0h+var_D0]
0x14004e4af  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004e4b4  lea     rcx, [rbp+0B0h+var_B0]
0x14004e4b8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004e4bd  nop
0x14004e4be  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x14004e4c3  test    rcx, rcx
0x14004e4c6  jz      short loc_14004E4ED
0x14004e4c8  mov     rax, [rcx]
0x14004e4cb  mov     rax, [rax+10h]
0x14004e4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e4d4  mov     r8, rax
0x14004e4d7  test    rax, rax
0x14004e4da  jz      short loc_14004E4ED
0x14004e4dc  mov     rcx, [rax]
0x14004e4df  mov     rax, [rcx]
0x14004e4e2  mov     edx, r14d
0x14004e4e5  mov     rcx, r8
0x14004e4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e4ed  lea     rax, [rbp+0B0h+var_D0]
0x14004e4f1  cmp     [rbp+0B0h+var_B8], 0Fh
0x14004e4f6  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x14004e4fb  mov     r10, [rbp+0B0h+var_C0]
0x14004e4ff  mov     edx, r13d
0x14004e502  test    r10, r10
0x14004e505  jz      short loc_14004E53A
0x14004e507  mov     r8, r12
0x14004e50a  sub     r8, [rsp+1B0h+var_140]
0x14004e50f  movsx   r9, byte ptr [rax]
0x14004e513  cmp     r8, r9
0x14004e516  jbe     short loc_14004E53A
0x14004e518  lea     r11, [r10+rax]
0x14004e51c  movsx   rcx, r9b
0x14004e520  sub     r8, rcx
0x14004e523  add     edx, r14d
0x14004e526  lea     rcx, [rax+1]
0x14004e52a  cmp     rcx, r11
0x14004e52d  cmovnz  rax, rcx
0x14004e531  movsx   r9, byte ptr [rax]
0x14004e535  cmp     r8, r9
0x14004e538  ja      short loc_14004E51C
0x14004e53a  mov     [rsp+1B0h+var_150], edx
0x14004e53e  mov     eax, [rsp+1B0h+var_17C]
0x14004e542  add     eax, edx
0x14004e544  mov     [rsp+1B0h+var_17C], eax
0x14004e548  cmp     [rsi+0Dh], r13b
0x14004e54c  jz      short loc_14004E554
0x14004e54e  cmp     [rsi+9], r13b
0x14004e552  jz      short loc_14004E557
0x14004e554  mov     r14b, r13b
0x14004e557  mov     [rsp+1B0h+var_180], r14b
0x14004e55c  mov     [rbp+0B0h+var_120], r12
0x14004e560  mov     [rbp+0B0h+var_118], rsi
0x14004e564  lea     rcx, [rsp+1B0h+var_148]
0x14004e569  mov     [rbp+0B0h+var_110], rcx
0x14004e56d  lea     rcx, [rbp+0B0h+var_130]
0x14004e571  mov     [rbp+0B0h+var_108], rcx
0x14004e575  lea     rcx, [rsp+1B0h+var_180]
0x14004e57a  mov     [rbp+0B0h+var_100], rcx
0x14004e57e  lea     rcx, [rsp+1B0h+var_17C]
0x14004e583  mov     [rbp+0B0h+var_F8], rcx
0x14004e587  lea     rcx, [rsp+1B0h+var_150]
0x14004e58c  mov     [rbp+0B0h+var_F0], rcx
0x14004e590  lea     rcx, [rsp+1B0h+var_140]
0x14004e595  mov     [rbp+0B0h+var_E8], rcx
0x14004e599  lea     rcx, [rbp+0B0h+var_D0]
0x14004e59d  mov     [rbp+0B0h+var_E0], rcx
0x14004e5a1  lea     rcx, [rbp+0B0h+arg_20]
0x14004e5a8  mov     [rbp+0B0h+var_D8], rcx
0x14004e5ac  lea     rcx, [rbp+0B0h+var_120]
0x14004e5b0  test    r14b, r14b
0x14004e5b3  jz      short loc_14004E5C2
0x14004e5b5  mov     r8, rbx
0x14004e5b8  mov     rdx, r15
0x14004e5bb  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x14004e5c0  jmp     short loc_14004E5D9
0x14004e5c2  mov     [rsp+1B0h+var_188], rcx
0x14004e5c7  mov     r9, rsi
0x14004e5ca  mov     r8d, eax
0x14004e5cd  mov     rdx, rbx
0x14004e5d0  mov     rcx, r15
0x14004e5d3  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x14004e5d8  nop
0x14004e5d9  lea     rcx, [rbp+0B0h+var_D0]
0x14004e5dd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004e5e2  mov     rax, r15
0x14004e5e5  mov     rcx, [rbp+0B0h+var_40]
0x14004e5e9  xor     rcx, rsp; StackCookie
0x14004e5ec  call    __security_check_cookie
0x14004e5f1  mov     rbx, [rsp+1B0h+arg_8]
0x14004e5f9  add     rsp, 180h
0x14004e600  pop     r15
0x14004e602  pop     r14
0x14004e604  pop     r13
0x14004e606  pop     r12
0x14004e608  pop     rdi
0x14004e609  pop     rsi
0x14004e60a  pop     rbp
0x14004e60b  retn
0x14004e60c  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x14004e613  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

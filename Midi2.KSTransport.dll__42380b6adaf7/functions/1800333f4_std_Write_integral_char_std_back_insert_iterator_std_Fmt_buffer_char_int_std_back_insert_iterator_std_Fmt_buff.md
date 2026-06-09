# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x1800333f4`
- end: `0x1800337a5`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180032164`

## callees

- `0x180004410`
- `0x18002ef5c`
- `0x180032b04`
- `0x1800333f4`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x180036e0c`
- `0x18003a404`
- `0x18003bb4c`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180033608`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180033608`

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
0x1800333f4  mov     [rsp-8+arg_8], rbx
0x1800333f9  push    rbp
0x1800333fa  push    rsi
0x1800333fb  push    rdi
0x1800333fc  push    r12
0x1800333fe  push    r13
0x180033400  push    r14
0x180033402  push    r15
0x180033404  lea     rbp, [rsp-80h]
0x180033409  sub     rsp, 180h
0x180033410  mov     rax, cs:__security_cookie
0x180033417  xor     rax, rsp
0x18003341a  mov     [rbp+0B0h+var_40], rax
0x18003341e  mov     rsi, r9
0x180033421  mov     rbx, rdx
0x180033424  mov     r15, rcx
0x180033427  mov     [rsp+1B0h+var_150], r8d
0x18003342c  xor     r13d, r13d
0x18003342f  mov     al, [r9+8]
0x180033433  cmp     al, 63h ; 'c'
0x180033435  jnz     short loc_18003347C
0x180033437  lea     eax, [r8+80h]
0x18003343e  cmp     eax, 0FFh
0x180033443  ja      loc_180033798
0x180033449  mov     [r9+0Bh], r13b
0x18003344d  movaps  xmm0, xmmword ptr [r9]
0x180033451  movaps  [rsp+1B0h+var_170], xmm0
0x180033456  mov     ecx, [r9+10h]
0x18003345a  mov     [rsp+1B0h+var_160], ecx
0x18003345e  mov     rcx, [rbp+0B0h+arg_20]
0x180033465  mov     [rsp+1B0h+var_190], rcx
0x18003346a  lea     r9, [rsp+1B0h+var_170]
0x18003346f  mov     rcx, r15
0x180033472  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180033477  jmp     loc_18003376E
0x18003347c  mov     edi, 2
0x180033481  cmp     [r9+0Ah], r13b
0x180033485  jnz     short loc_18003348B
0x180033487  mov     [r9+0Ah], dil
0x18003348b  cmp     al, 42h ; 'B'
0x18003348d  jz      short loc_1800334B4
0x18003348f  cmp     al, 58h ; 'X'
0x180033491  jz      short loc_1800334AD
0x180033493  cmp     al, 62h ; 'b'
0x180033495  jz      short loc_1800334B4
0x180033497  cmp     al, 6Fh ; 'o'
0x180033499  jz      short loc_1800334A6
0x18003349b  cmp     al, 78h ; 'x'
0x18003349d  jz      short loc_1800334AD
0x18003349f  mov     eax, 0Ah
0x1800334a4  jmp     short loc_1800334B6
0x1800334a6  mov     eax, 8
0x1800334ab  jmp     short loc_1800334B6
0x1800334ad  mov     eax, 10h
0x1800334b2  jmp     short loc_1800334B6
0x1800334b4  mov     eax, edi
0x1800334b6  mov     dword ptr [rsp+1B0h+var_190], eax
0x1800334ba  mov     r9d, r8d
0x1800334bd  lea     r8, [rbp+0B0h+var_4F]
0x1800334c1  lea     rdx, [rbp+0B0h+var_90]
0x1800334c5  lea     rcx, [rsp+1B0h+var_170]
0x1800334ca  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0HH@Z; std::to_chars(char * const,char * const,int,int)
0x1800334cf  mov     r12, [rax]
0x1800334d2  lea     rcx, [rbp+0B0h+var_90]
0x1800334d6  mov     [rsp+1B0h+var_140], rcx
0x1800334db  mov     eax, r12d
0x1800334de  sub     eax, ecx
0x1800334e0  mov     [rsp+1B0h+var_17C], eax
0x1800334e4  mov     edx, [rsp+1B0h+var_150]
0x1800334e8  test    edx, edx
0x1800334ea  js      short loc_1800334FA
0x1800334ec  cmp     [rsi+0Ah], dil
0x1800334f0  jz      short loc_180033503
0x1800334f2  inc     eax
0x1800334f4  mov     [rsp+1B0h+var_17C], eax
0x1800334f8  jmp     short loc_180033503
0x1800334fa  lea     rcx, [rbp+0B0h+var_8F]
0x1800334fe  mov     [rsp+1B0h+var_140], rcx
0x180033503  mov     r14d, 1
0x180033509  cmp     byte ptr [rsi+8], 58h ; 'X'
0x18003350d  jnz     short loc_180033532
0x18003350f  cmp     rcx, r12
0x180033512  jz      short loc_180033532
0x180033514  mov     dl, [rcx]
0x180033516  lea     eax, [rdx-61h]
0x180033519  cmp     al, 19h
0x18003351b  ja      short loc_180033522
0x18003351d  sub     dl, 20h ; ' '
0x180033520  mov     [rcx], dl
0x180033522  add     rcx, r14
0x180033525  cmp     rcx, r12
0x180033528  jnz     short loc_180033514
0x18003352a  mov     eax, [rsp+1B0h+var_17C]
0x18003352e  mov     edx, [rsp+1B0h+var_150]
0x180033532  mov     qword ptr [rbp+0B0h+var_130], r13
0x180033536  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x18003353a  cmp     [rsi+0Bh], r13b
0x18003353e  jz      short loc_1800335BC
0x180033540  mov     cl, [rsi+8]
0x180033543  cmp     cl, 42h ; 'B'
0x180033546  jz      short loc_18003359B
0x180033548  cmp     cl, 58h ; 'X'
0x18003354b  jz      short loc_180033592
0x18003354d  cmp     cl, 62h ; 'b'
0x180033550  jz      short loc_180033589
0x180033552  cmp     cl, 6Fh ; 'o'
0x180033555  jz      short loc_180033565
0x180033557  cmp     cl, 78h ; 'x'
0x18003355a  jnz     short loc_18003357A
0x18003355c  lea     rcx, a0x; "0x"
0x180033563  jmp     short loc_1800335A2
0x180033565  test    edx, edx
0x180033567  jz      short loc_18003357A
0x180033569  lea     rcx, a0; "0"
0x180033570  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180033575  mov     edi, r14d
0x180033578  jmp     short loc_1800335A7
0x18003357a  mov     qword ptr [rsp+1B0h+var_170], r13
0x18003357f  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180033584  mov     edi, r13d
0x180033587  jmp     short loc_1800335AC
0x180033589  lea     rcx, a0b; "0b"
0x180033590  jmp     short loc_1800335A2
0x180033592  lea     rcx, a0x_0; "0X"
0x180033599  jmp     short loc_1800335A2
0x18003359b  lea     rcx, a0b_0; "0B"
0x1800335a2  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800335a7  mov     qword ptr [rsp+1B0h+var_170], rcx
0x1800335ac  movaps  xmm0, [rsp+1B0h+var_170]
0x1800335b1  movdqa  [rbp+0B0h+var_130], xmm0
0x1800335b6  add     eax, edi
0x1800335b8  mov     [rsp+1B0h+var_17C], eax
0x1800335bc  mov     [rsp+1B0h+var_148], r13d
0x1800335c1  xorps   xmm0, xmm0
0x1800335c4  movups  [rbp+0B0h+var_D0], xmm0
0x1800335c8  mov     [rbp+0B0h+var_C0], r13
0x1800335cc  mov     [rbp+0B0h+var_B8], 0Fh
0x1800335d4  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x1800335d8  cmp     [rsi+0Ch], r13b
0x1800335dc  jz      loc_1800336D4
0x1800335e2  mov     rax, [rbp+0B0h+arg_20]
0x1800335e9  test    rax, rax
0x1800335ec  jz      short loc_180033605
0x1800335ee  mov     rcx, [rax+8]
0x1800335f2  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x1800335f7  mov     rax, [rcx]
0x1800335fa  mov     rax, [rax+8]
0x1800335fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033603  jmp     short loc_180033613
0x180033605  mov     cl, r14b
0x180033608  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18003360e  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180033613  lea     rcx, [rsp+1B0h+var_170]
0x180033618  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18003361d  mov     r8, rax
0x180033620  mov     rcx, [rax]
0x180033623  mov     rax, [rcx+28h]
0x180033627  lea     rdx, [rbp+0B0h+var_B0]
0x18003362b  mov     rcx, r8
0x18003362e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033633  lea     rdx, [rbp+0B0h+var_B0]
0x180033637  lea     rcx, [rbp+0B0h+var_D0]
0x18003363b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180033640  lea     rcx, [rbp+0B0h+var_B0]
0x180033644  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033649  nop
0x18003364a  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x18003364f  test    rcx, rcx
0x180033652  jz      short loc_180033679
0x180033654  mov     rax, [rcx]
0x180033657  mov     rax, [rax+10h]
0x18003365b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033660  mov     r8, rax
0x180033663  test    rax, rax
0x180033666  jz      short loc_180033679
0x180033668  mov     rcx, [rax]
0x18003366b  mov     rax, [rcx]
0x18003366e  mov     edx, r14d
0x180033671  mov     rcx, r8
0x180033674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033679  lea     rax, [rbp+0B0h+var_D0]
0x18003367d  cmp     [rbp+0B0h+var_B8], 0Fh
0x180033682  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180033687  mov     r10, [rbp+0B0h+var_C0]
0x18003368b  mov     edx, r13d
0x18003368e  test    r10, r10
0x180033691  jz      short loc_1800336C6
0x180033693  mov     r8, r12
0x180033696  sub     r8, [rsp+1B0h+var_140]
0x18003369b  movsx   r9, byte ptr [rax]
0x18003369f  cmp     r8, r9
0x1800336a2  jbe     short loc_1800336C6
0x1800336a4  lea     r11, [r10+rax]
0x1800336a8  movsx   rcx, r9b
0x1800336ac  sub     r8, rcx
0x1800336af  add     edx, r14d
0x1800336b2  lea     rcx, [rax+1]
0x1800336b6  cmp     rcx, r11
0x1800336b9  cmovnz  rax, rcx
0x1800336bd  movsx   r9, byte ptr [rax]
0x1800336c1  cmp     r8, r9
0x1800336c4  ja      short loc_1800336A8
0x1800336c6  mov     [rsp+1B0h+var_148], edx
0x1800336ca  mov     eax, [rsp+1B0h+var_17C]
0x1800336ce  add     eax, edx
0x1800336d0  mov     [rsp+1B0h+var_17C], eax
0x1800336d4  cmp     [rsi+0Dh], r13b
0x1800336d8  jz      short loc_1800336E0
0x1800336da  cmp     [rsi+9], r13b
0x1800336de  jz      short loc_1800336E3
0x1800336e0  mov     r14b, r13b
0x1800336e3  mov     [rsp+1B0h+var_180], r14b
0x1800336e8  mov     [rbp+0B0h+var_120], r12
0x1800336ec  mov     [rbp+0B0h+var_118], rsi
0x1800336f0  lea     rcx, [rsp+1B0h+var_150]
0x1800336f5  mov     [rbp+0B0h+var_110], rcx
0x1800336f9  lea     rcx, [rbp+0B0h+var_130]
0x1800336fd  mov     [rbp+0B0h+var_108], rcx
0x180033701  lea     rcx, [rsp+1B0h+var_180]
0x180033706  mov     [rbp+0B0h+var_100], rcx
0x18003370a  lea     rcx, [rsp+1B0h+var_17C]
0x18003370f  mov     [rbp+0B0h+var_F8], rcx
0x180033713  lea     rcx, [rsp+1B0h+var_148]
0x180033718  mov     [rbp+0B0h+var_F0], rcx
0x18003371c  lea     rcx, [rsp+1B0h+var_140]
0x180033721  mov     [rbp+0B0h+var_E8], rcx
0x180033725  lea     rcx, [rbp+0B0h+var_D0]
0x180033729  mov     [rbp+0B0h+var_E0], rcx
0x18003372d  lea     rcx, [rbp+0B0h+arg_20]
0x180033734  mov     [rbp+0B0h+var_D8], rcx
0x180033738  lea     rcx, [rbp+0B0h+var_120]
0x18003373c  test    r14b, r14b
0x18003373f  jz      short loc_18003374E
0x180033741  mov     r8, rbx
0x180033744  mov     rdx, r15
0x180033747  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18003374c  jmp     short loc_180033765
0x18003374e  mov     [rsp+1B0h+var_188], rcx
0x180033753  mov     r9, rsi
0x180033756  mov     r8d, eax
0x180033759  mov     rdx, rbx
0x18003375c  mov     rcx, r15
0x18003375f  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@2@YA?AV12@V12@HU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@0@YA?AV10@0HU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180033764  nop
0x180033765  lea     rcx, [rbp+0B0h+var_D0]
0x180033769  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003376e  mov     rax, r15
0x180033771  mov     rcx, [rbp+0B0h+var_40]
0x180033775  xor     rcx, rsp; StackCookie
0x180033778  call    __security_check_cookie
0x18003377d  mov     rbx, [rsp+1B0h+arg_8]
0x180033785  add     rsp, 180h
0x18003378c  pop     r15
0x18003378e  pop     r14
0x180033790  pop     r13
0x180033792  pop     r12
0x180033794  pop     rdi
0x180033795  pop     rsi
0x180033796  pop     rbp
0x180033797  retn
0x180033798  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x18003379f  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

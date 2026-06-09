# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180028510`
- end: `0x1800288ad`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@IU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180023e98`
- `0x180027998`
- `0x180028510`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b9a4`
- `0x18002dd84`
- `0x18002f6b8`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180028710`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180028710`

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
0x180028510  mov     [rsp-8+arg_8], rbx
0x180028515  push    rbp
0x180028516  push    rsi
0x180028517  push    rdi
0x180028518  push    r12
0x18002851a  push    r13
0x18002851c  push    r14
0x18002851e  push    r15
0x180028520  lea     rbp, [rsp-80h]
0x180028525  sub     rsp, 180h
0x18002852c  mov     rax, cs:__security_cookie
0x180028533  xor     rax, rsp
0x180028536  mov     [rbp+0B0h+var_40], rax
0x18002853a  mov     rsi, r9
0x18002853d  mov     rbx, rdx
0x180028540  mov     r15, rcx
0x180028543  mov     [rsp+1B0h+var_148], r8d
0x180028548  xor     r13d, r13d
0x18002854b  mov     al, [r9+8]
0x18002854f  cmp     al, 63h ; 'c'
0x180028551  jnz     short loc_180028590
0x180028553  cmp     r8d, 7Fh
0x180028557  ja      loc_1800288A0
0x18002855d  mov     [r9+0Bh], r13b
0x180028561  movaps  xmm0, xmmword ptr [r9]
0x180028565  movaps  [rsp+1B0h+var_170], xmm0
0x18002856a  mov     ecx, [r9+10h]
0x18002856e  mov     [rsp+1B0h+var_160], ecx
0x180028572  mov     rcx, [rbp+0B0h+arg_20]
0x180028579  mov     [rsp+1B0h+var_190], rcx
0x18002857e  lea     r9, [rsp+1B0h+var_170]
0x180028583  mov     rcx, r15
0x180028586  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x18002858b  jmp     loc_180028876
0x180028590  mov     edi, 2
0x180028595  cmp     [r9+0Ah], r13b
0x180028599  jnz     short loc_18002859F
0x18002859b  mov     [r9+0Ah], dil
0x18002859f  cmp     al, 42h ; 'B'
0x1800285a1  jz      short loc_1800285C8
0x1800285a3  cmp     al, 58h ; 'X'
0x1800285a5  jz      short loc_1800285C1
0x1800285a7  cmp     al, 62h ; 'b'
0x1800285a9  jz      short loc_1800285C8
0x1800285ab  cmp     al, 6Fh ; 'o'
0x1800285ad  jz      short loc_1800285BA
0x1800285af  cmp     al, 78h ; 'x'
0x1800285b1  jz      short loc_1800285C1
0x1800285b3  mov     eax, 0Ah
0x1800285b8  jmp     short loc_1800285CA
0x1800285ba  mov     eax, 8
0x1800285bf  jmp     short loc_1800285CA
0x1800285c1  mov     eax, 10h
0x1800285c6  jmp     short loc_1800285CA
0x1800285c8  mov     eax, edi
0x1800285ca  mov     dword ptr [rsp+1B0h+var_190], eax
0x1800285ce  mov     r9d, r8d
0x1800285d1  lea     r8, [rbp+0B0h+var_4F]
0x1800285d5  lea     rdx, [rbp+0B0h+var_90]
0x1800285d9  lea     rcx, [rsp+1B0h+var_170]
0x1800285de  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0IH@Z; std::to_chars(char * const,char * const,uint,int)
0x1800285e3  mov     r12, [rax]
0x1800285e6  lea     rcx, [rbp+0B0h+var_90]
0x1800285ea  mov     [rsp+1B0h+var_140], rcx
0x1800285ef  mov     eax, r12d
0x1800285f2  sub     eax, ecx
0x1800285f4  mov     [rsp+1B0h+var_17C], eax
0x1800285f8  cmp     [rsi+0Ah], dil
0x1800285fc  jz      short loc_180028604
0x1800285fe  inc     eax
0x180028600  mov     [rsp+1B0h+var_17C], eax
0x180028604  mov     r14d, 1
0x18002860a  cmp     byte ptr [rsi+8], 58h ; 'X'
0x18002860e  jnz     short loc_180028637
0x180028610  lea     rcx, [rbp+0B0h+var_90]
0x180028614  lea     rdx, [rbp+0B0h+var_90]
0x180028618  cmp     rdx, r12
0x18002861b  jz      short loc_180028637
0x18002861d  mov     dl, [rcx]
0x18002861f  lea     eax, [rdx-61h]
0x180028622  cmp     al, 19h
0x180028624  ja      short loc_18002862B
0x180028626  sub     dl, 20h ; ' '
0x180028629  mov     [rcx], dl
0x18002862b  add     rcx, r14
0x18002862e  cmp     rcx, r12
0x180028631  jnz     short loc_18002861D
0x180028633  mov     eax, [rsp+1B0h+var_17C]
0x180028637  mov     qword ptr [rbp+0B0h+var_130], r13
0x18002863b  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x18002863f  cmp     [rsi+0Bh], r13b
0x180028643  jz      short loc_1800286C4
0x180028645  mov     cl, [rsi+8]
0x180028648  cmp     cl, 42h ; 'B'
0x18002864b  jz      short loc_1800286A3
0x18002864d  cmp     cl, 58h ; 'X'
0x180028650  jz      short loc_18002869A
0x180028652  cmp     cl, 62h ; 'b'
0x180028655  jz      short loc_180028691
0x180028657  cmp     cl, 6Fh ; 'o'
0x18002865a  jz      short loc_18002866A
0x18002865c  cmp     cl, 78h ; 'x'
0x18002865f  jnz     short loc_180028682
0x180028661  lea     rcx, a0x; "0x"
0x180028668  jmp     short loc_1800286AA
0x18002866a  cmp     [rsp+1B0h+var_148], r13d
0x18002866f  jz      short loc_180028682
0x180028671  lea     rcx, a0; "0"
0x180028678  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x18002867d  mov     edi, r14d
0x180028680  jmp     short loc_1800286AF
0x180028682  mov     qword ptr [rsp+1B0h+var_170], r13
0x180028687  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18002868c  mov     edi, r13d
0x18002868f  jmp     short loc_1800286B4
0x180028691  lea     rcx, a0b; "0b"
0x180028698  jmp     short loc_1800286AA
0x18002869a  lea     rcx, a0x_0; "0X"
0x1800286a1  jmp     short loc_1800286AA
0x1800286a3  lea     rcx, a0b_0; "0B"
0x1800286aa  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800286af  mov     qword ptr [rsp+1B0h+var_170], rcx
0x1800286b4  movaps  xmm0, [rsp+1B0h+var_170]
0x1800286b9  movdqa  [rbp+0B0h+var_130], xmm0
0x1800286be  add     eax, edi
0x1800286c0  mov     [rsp+1B0h+var_17C], eax
0x1800286c4  mov     [rsp+1B0h+var_150], r13d
0x1800286c9  xorps   xmm0, xmm0
0x1800286cc  movups  [rbp+0B0h+var_D0], xmm0
0x1800286d0  mov     [rbp+0B0h+var_C0], r13
0x1800286d4  mov     [rbp+0B0h+var_B8], 0Fh
0x1800286dc  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x1800286e0  cmp     [rsi+0Ch], r13b
0x1800286e4  jz      loc_1800287DC
0x1800286ea  mov     rax, [rbp+0B0h+arg_20]
0x1800286f1  test    rax, rax
0x1800286f4  jz      short loc_18002870D
0x1800286f6  mov     rcx, [rax+8]
0x1800286fa  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x1800286ff  mov     rax, [rcx]
0x180028702  mov     rax, [rax+8]
0x180028706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002870b  jmp     short loc_18002871B
0x18002870d  mov     cl, r14b
0x180028710  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180028716  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x18002871b  lea     rcx, [rsp+1B0h+var_170]
0x180028720  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180028725  mov     r8, rax
0x180028728  mov     rcx, [rax]
0x18002872b  mov     rax, [rcx+28h]
0x18002872f  lea     rdx, [rbp+0B0h+var_B0]
0x180028733  mov     rcx, r8
0x180028736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002873b  lea     rdx, [rbp+0B0h+var_B0]
0x18002873f  lea     rcx, [rbp+0B0h+var_D0]
0x180028743  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180028748  lea     rcx, [rbp+0B0h+var_B0]
0x18002874c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028751  nop
0x180028752  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180028757  test    rcx, rcx
0x18002875a  jz      short loc_180028781
0x18002875c  mov     rax, [rcx]
0x18002875f  mov     rax, [rax+10h]
0x180028763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028768  mov     r8, rax
0x18002876b  test    rax, rax
0x18002876e  jz      short loc_180028781
0x180028770  mov     rcx, [rax]
0x180028773  mov     rax, [rcx]
0x180028776  mov     edx, r14d
0x180028779  mov     rcx, r8
0x18002877c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028781  lea     rax, [rbp+0B0h+var_D0]
0x180028785  cmp     [rbp+0B0h+var_B8], 0Fh
0x18002878a  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x18002878f  mov     r10, [rbp+0B0h+var_C0]
0x180028793  mov     edx, r13d
0x180028796  test    r10, r10
0x180028799  jz      short loc_1800287CE
0x18002879b  mov     r8, r12
0x18002879e  sub     r8, [rsp+1B0h+var_140]
0x1800287a3  movsx   r9, byte ptr [rax]
0x1800287a7  cmp     r8, r9
0x1800287aa  jbe     short loc_1800287CE
0x1800287ac  lea     r11, [r10+rax]
0x1800287b0  movsx   rcx, r9b
0x1800287b4  sub     r8, rcx
0x1800287b7  add     edx, r14d
0x1800287ba  lea     rcx, [rax+1]
0x1800287be  cmp     rcx, r11
0x1800287c1  cmovnz  rax, rcx
0x1800287c5  movsx   r9, byte ptr [rax]
0x1800287c9  cmp     r8, r9
0x1800287cc  ja      short loc_1800287B0
0x1800287ce  mov     [rsp+1B0h+var_150], edx
0x1800287d2  mov     eax, [rsp+1B0h+var_17C]
0x1800287d6  add     eax, edx
0x1800287d8  mov     [rsp+1B0h+var_17C], eax
0x1800287dc  cmp     [rsi+0Dh], r13b
0x1800287e0  jz      short loc_1800287E8
0x1800287e2  cmp     [rsi+9], r13b
0x1800287e6  jz      short loc_1800287EB
0x1800287e8  mov     r14b, r13b
0x1800287eb  mov     [rsp+1B0h+var_180], r14b
0x1800287f0  mov     [rbp+0B0h+var_120], r12
0x1800287f4  mov     [rbp+0B0h+var_118], rsi
0x1800287f8  lea     rcx, [rsp+1B0h+var_148]
0x1800287fd  mov     [rbp+0B0h+var_110], rcx
0x180028801  lea     rcx, [rbp+0B0h+var_130]
0x180028805  mov     [rbp+0B0h+var_108], rcx
0x180028809  lea     rcx, [rsp+1B0h+var_180]
0x18002880e  mov     [rbp+0B0h+var_100], rcx
0x180028812  lea     rcx, [rsp+1B0h+var_17C]
0x180028817  mov     [rbp+0B0h+var_F8], rcx
0x18002881b  lea     rcx, [rsp+1B0h+var_150]
0x180028820  mov     [rbp+0B0h+var_F0], rcx
0x180028824  lea     rcx, [rsp+1B0h+var_140]
0x180028829  mov     [rbp+0B0h+var_E8], rcx
0x18002882d  lea     rcx, [rbp+0B0h+var_D0]
0x180028831  mov     [rbp+0B0h+var_E0], rcx
0x180028835  lea     rcx, [rbp+0B0h+arg_20]
0x18002883c  mov     [rbp+0B0h+var_D8], rcx
0x180028840  lea     rcx, [rbp+0B0h+var_120]
0x180028844  test    r14b, r14b
0x180028847  jz      short loc_180028856
0x180028849  mov     r8, rbx
0x18002884c  mov     rdx, r15
0x18002884f  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180028854  jmp     short loc_18002886D
0x180028856  mov     [rsp+1B0h+var_188], rcx
0x18002885b  mov     r9, rsi
0x18002885e  mov     r8d, eax
0x180028861  mov     rdx, rbx
0x180028864  mov     rcx, r15
0x180028867  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x18002886c  nop
0x18002886d  lea     rcx, [rbp+0B0h+var_D0]
0x180028871  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028876  mov     rax, r15
0x180028879  mov     rcx, [rbp+0B0h+var_40]
0x18002887d  xor     rcx, rsp; StackCookie
0x180028880  call    __security_check_cookie
0x180028885  mov     rbx, [rsp+1B0h+arg_8]
0x18002888d  add     rsp, 180h
0x180028894  pop     r15
0x180028896  pop     r14
0x180028898  pop     r13
0x18002889a  pop     r12
0x18002889c  pop     rdi
0x18002889d  pop     rsi
0x18002889e  pop     rbp
0x18002889f  retn
0x1800288a0  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x1800288a7  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x180031608`
- end: `0x1800319b3`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@IU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `939`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002ff18`

## callees

- `0x180005020`
- `0x18002c1a4`
- `0x180030748`
- `0x180031608`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034ea8`
- `0x180040fac`
- `0x18004321c`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031814`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031814`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned int>(
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
  struct std::locale::_Locimp *v17; // rdi
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
  int v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+80h] [rbp-80h]
  _QWORD v35[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v38; // [rsp+F8h] [rbp-8h]
  _BYTE v39[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v40[65]; // [rsp+120h] [rbp+20h] BYREF
  char v41[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0xFFFF )
      std::_Throw_format_error("integral cannot be stored in wchar_t");
    *((_BYTE *)a4 + 11) = 0;
    v33 = *a4;
    v34 = *((_DWORD *)a4 + 4);
    std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a1,
      a2,
      a3,
      (unsigned int)&v33,
      a5);
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
  v11 = *(_BYTE **)std::to_chars(&v33, v40, v41, a3);
  v32 = v40;
  v12 = (_DWORD)v11 - (unsigned int)v40;
  v28 = v12;
  if ( *((_BYTE *)a4 + 10) != 2 )
    v28 = ++v12;
  v13 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 )
  {
    v14 = v40;
    if ( v40 != v11 )
    {
      do
      {
        if ( (unsigned __int8)(*v14 - 97) <= 0x19u )
          *v14 -= 32;
        ++v14;
      }
      while ( v14 != v11 );
      v12 = v28;
    }
  }
  v29 = 0u;
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
        *((_QWORD *)&v29 + 1) = 1;
        v9 = 1;
LABEL_37:
        *(_QWORD *)&v29 = v16;
        goto LABEL_38;
      }
      break;
    case 'x':
      v16 = "0x";
LABEL_36:
      *((_QWORD *)&v29 + 1) = 2;
      goto LABEL_37;
  }
  v29 = 0u;
  v9 = 0;
LABEL_38:
  v12 += v9;
  v28 = v12;
LABEL_39:
  v30 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 15;
  LOBYTE(v36) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      v17 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v33 + 1) = v17;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v17 + 8LL))(v17);
    }
    else
    {
      v17 = std::locale::_Init(1);
      *((_QWORD *)&v33 + 1) = v17;
    }
    v18 = std::use_facet<std::numpunct<unsigned short>>(&v33);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 40LL))(v18, v39);
    std::string::operator=(&v36, v39);
    std::string::~string(v39);
    if ( v17 )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v19 )
        (**v19)(v19, 1);
    }
    v20 = (char *)&v36;
    if ( v38 > 0xF )
      v20 = (char *)v36;
    v21 = 0;
    if ( v37 )
    {
      v22 = v11 - v32;
      v23 = *v20;
      if ( v11 - v32 > v23 )
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
    v30 = v21;
    v12 = v21 + v28;
    v28 += v21;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v13 = 0;
  v27 = v13;
  v35[0] = v11;
  v35[1] = a4;
  v35[2] = &v31;
  v35[3] = &v29;
  v35[4] = &v27;
  v35[5] = &v28;
  v35[6] = &v30;
  v35[7] = &v32;
  v35[8] = &v36;
  v35[9] = &a5;
  if ( v13 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
      v35,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_2_YA_AV12_V12_IU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_0_YA_AV10_0IU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v12,
      (_DWORD)a4,
      v26,
      (__int64)v35);
  std::string::~string(&v36);
  return a1;
}

```

## disassembly

```asm
0x180031608  mov     [rsp-8+arg_8], rbx
0x18003160d  push    rbp
0x18003160e  push    rsi
0x18003160f  push    rdi
0x180031610  push    r12
0x180031612  push    r13
0x180031614  push    r14
0x180031616  push    r15
0x180031618  lea     rbp, [rsp-80h]
0x18003161d  sub     rsp, 180h
0x180031624  mov     rax, cs:__security_cookie
0x18003162b  xor     rax, rsp
0x18003162e  mov     [rbp+0B0h+var_40], rax
0x180031632  mov     rsi, r9
0x180031635  mov     rbx, rdx
0x180031638  mov     r15, rcx
0x18003163b  mov     [rsp+1B0h+var_158], r8d
0x180031640  xor     r13d, r13d
0x180031643  mov     al, [r9+8]
0x180031647  cmp     al, 63h ; 'c'
0x180031649  jnz     short loc_18003168A
0x18003164b  cmp     r8d, 0FFFFh
0x180031652  ja      loc_1800319A6
0x180031658  mov     [r9+0Bh], r13b
0x18003165c  movaps  xmm0, xmmword ptr [r9]
0x180031660  movaps  [rsp+1B0h+var_140], xmm0
0x180031665  mov     ecx, [r9+10h]
0x180031669  mov     [rbp+0B0h+var_130], ecx
0x18003166c  mov     rcx, [rbp+0B0h+arg_20]
0x180031673  mov     [rsp+1B0h+var_190], rcx
0x180031678  lea     r9, [rsp+1B0h+var_140]
0x18003167d  mov     rcx, r15
0x180031680  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x180031685  jmp     loc_18003197C
0x18003168a  mov     edi, 2
0x18003168f  cmp     [r9+0Ah], r13b
0x180031693  jnz     short loc_180031699
0x180031695  mov     [r9+0Ah], dil
0x180031699  cmp     al, 42h ; 'B'
0x18003169b  jz      short loc_1800316C2
0x18003169d  cmp     al, 58h ; 'X'
0x18003169f  jz      short loc_1800316BB
0x1800316a1  cmp     al, 62h ; 'b'
0x1800316a3  jz      short loc_1800316C2
0x1800316a5  cmp     al, 6Fh ; 'o'
0x1800316a7  jz      short loc_1800316B4
0x1800316a9  cmp     al, 78h ; 'x'
0x1800316ab  jz      short loc_1800316BB
0x1800316ad  mov     eax, 0Ah
0x1800316b2  jmp     short loc_1800316C4
0x1800316b4  mov     eax, 8
0x1800316b9  jmp     short loc_1800316C4
0x1800316bb  mov     eax, 10h
0x1800316c0  jmp     short loc_1800316C4
0x1800316c2  mov     eax, edi
0x1800316c4  mov     dword ptr [rsp+1B0h+var_190], eax
0x1800316c8  mov     r9d, r8d
0x1800316cb  lea     r8, [rbp+0B0h+var_4F]
0x1800316cf  lea     rdx, [rbp+0B0h+var_90]
0x1800316d3  lea     rcx, [rsp+1B0h+var_140]
0x1800316d8  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0IH@Z; std::to_chars(char * const,char * const,uint,int)
0x1800316dd  mov     r12, [rax]
0x1800316e0  lea     rcx, [rbp+0B0h+var_90]
0x1800316e4  mov     [rsp+1B0h+var_150], rcx
0x1800316e9  mov     eax, r12d
0x1800316ec  sub     eax, ecx
0x1800316ee  mov     [rsp+1B0h+var_17C], eax
0x1800316f2  cmp     [rsi+0Ah], dil
0x1800316f6  jz      short loc_1800316FE
0x1800316f8  inc     eax
0x1800316fa  mov     [rsp+1B0h+var_17C], eax
0x1800316fe  mov     r14d, 1
0x180031704  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180031708  jnz     short loc_180031731
0x18003170a  lea     rcx, [rbp+0B0h+var_90]
0x18003170e  lea     rdx, [rbp+0B0h+var_90]
0x180031712  cmp     rdx, r12
0x180031715  jz      short loc_180031731
0x180031717  mov     dl, [rcx]
0x180031719  lea     eax, [rdx-61h]
0x18003171c  cmp     al, 19h
0x18003171e  ja      short loc_180031725
0x180031720  sub     dl, 20h ; ' '
0x180031723  mov     [rcx], dl
0x180031725  add     rcx, r14
0x180031728  cmp     rcx, r12
0x18003172b  jnz     short loc_180031717
0x18003172d  mov     eax, [rsp+1B0h+var_17C]
0x180031731  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031736  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18003173b  cmp     [rsi+0Bh], r13b
0x18003173f  jz      loc_1800317C5
0x180031745  mov     cl, [rsi+8]
0x180031748  cmp     cl, 42h ; 'B'
0x18003174b  jz      short loc_1800317A3
0x18003174d  cmp     cl, 58h ; 'X'
0x180031750  jz      short loc_18003179A
0x180031752  cmp     cl, 62h ; 'b'
0x180031755  jz      short loc_180031791
0x180031757  cmp     cl, 6Fh ; 'o'
0x18003175a  jz      short loc_18003176A
0x18003175c  cmp     cl, 78h ; 'x'
0x18003175f  jnz     short loc_180031782
0x180031761  lea     rcx, a0x; "0x"
0x180031768  jmp     short loc_1800317AA
0x18003176a  cmp     [rsp+1B0h+var_158], r13d
0x18003176f  jz      short loc_180031782
0x180031771  lea     rcx, a0; "0"
0x180031778  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x18003177d  mov     edi, r14d
0x180031780  jmp     short loc_1800317AF
0x180031782  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031787  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18003178c  mov     edi, r13d
0x18003178f  jmp     short loc_1800317B4
0x180031791  lea     rcx, a0b; "0b"
0x180031798  jmp     short loc_1800317AA
0x18003179a  lea     rcx, a0x_0; "0X"
0x1800317a1  jmp     short loc_1800317AA
0x1800317a3  lea     rcx, a0b_0; "0B"
0x1800317aa  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x1800317af  mov     qword ptr [rsp+1B0h+var_170], rcx
0x1800317b4  movaps  xmm0, [rsp+1B0h+var_170]
0x1800317b9  movdqa  [rsp+1B0h+var_170], xmm0
0x1800317bf  add     eax, edi
0x1800317c1  mov     [rsp+1B0h+var_17C], eax
0x1800317c5  mov     [rsp+1B0h+var_160], r13d
0x1800317ca  xorps   xmm0, xmm0
0x1800317cd  movups  [rbp+0B0h+var_D0], xmm0
0x1800317d1  mov     [rbp+0B0h+var_C0], r13
0x1800317d5  mov     [rbp+0B0h+var_B8], 0Fh
0x1800317dd  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x1800317e1  cmp     [rsi+0Ch], r13b
0x1800317e5  jz      loc_1800318E1
0x1800317eb  mov     rax, [rbp+0B0h+arg_20]
0x1800317f2  test    rax, rax
0x1800317f5  jz      short loc_180031811
0x1800317f7  mov     rdi, [rax+8]
0x1800317fb  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x180031800  mov     rax, [rdi]
0x180031803  mov     rcx, rdi
0x180031806  mov     rax, [rax+8]
0x18003180a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003180f  jmp     short loc_180031822
0x180031811  mov     cl, r14b
0x180031814  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18003181a  mov     rdi, rax
0x18003181d  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x180031822  lea     rcx, [rsp+1B0h+var_140]
0x180031827  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x18003182c  mov     r8, rax
0x18003182f  mov     rcx, [rax]
0x180031832  mov     rax, [rcx+28h]
0x180031836  lea     rdx, [rbp+0B0h+var_B0]
0x18003183a  mov     rcx, r8
0x18003183d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031842  lea     rdx, [rbp+0B0h+var_B0]
0x180031846  lea     rcx, [rbp+0B0h+var_D0]
0x18003184a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18003184f  lea     rcx, [rbp+0B0h+var_B0]
0x180031853  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180031858  nop
0x180031859  test    rdi, rdi
0x18003185c  jz      short loc_180031886
0x18003185e  mov     rax, [rdi]
0x180031861  mov     rcx, rdi
0x180031864  mov     rax, [rax+10h]
0x180031868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003186d  mov     r8, rax
0x180031870  test    rax, rax
0x180031873  jz      short loc_180031886
0x180031875  mov     rcx, [rax]
0x180031878  mov     rax, [rcx]
0x18003187b  mov     edx, r14d
0x18003187e  mov     rcx, r8
0x180031881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031886  lea     rax, [rbp+0B0h+var_D0]
0x18003188a  cmp     [rbp+0B0h+var_B8], 0Fh
0x18003188f  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180031894  mov     r10, [rbp+0B0h+var_C0]
0x180031898  mov     edx, r13d
0x18003189b  test    r10, r10
0x18003189e  jz      short loc_1800318D3
0x1800318a0  mov     r8, r12
0x1800318a3  sub     r8, [rsp+1B0h+var_150]
0x1800318a8  movsx   r9, byte ptr [rax]
0x1800318ac  cmp     r8, r9
0x1800318af  jbe     short loc_1800318D3
0x1800318b1  lea     r11, [r10+rax]
0x1800318b5  movsx   rcx, r9b
0x1800318b9  sub     r8, rcx
0x1800318bc  add     edx, r14d
0x1800318bf  lea     rcx, [rax+1]
0x1800318c3  cmp     rcx, r11
0x1800318c6  cmovnz  rax, rcx
0x1800318ca  movsx   r9, byte ptr [rax]
0x1800318ce  cmp     r8, r9
0x1800318d1  ja      short loc_1800318B5
0x1800318d3  mov     [rsp+1B0h+var_160], edx
0x1800318d7  mov     eax, [rsp+1B0h+var_17C]
0x1800318db  add     eax, edx
0x1800318dd  mov     [rsp+1B0h+var_17C], eax
0x1800318e1  cmp     [rsi+0Dh], r13b
0x1800318e5  jz      short loc_1800318ED
0x1800318e7  cmp     [rsi+9], r13b
0x1800318eb  jz      short loc_1800318F0
0x1800318ed  mov     r14b, r13b
0x1800318f0  mov     [rsp+1B0h+var_180], r14b
0x1800318f5  mov     [rbp+0B0h+var_120], r12
0x1800318f9  mov     [rbp+0B0h+var_118], rsi
0x1800318fd  lea     rcx, [rsp+1B0h+var_158]
0x180031902  mov     [rbp+0B0h+var_110], rcx
0x180031906  lea     rcx, [rsp+1B0h+var_170]
0x18003190b  mov     [rbp+0B0h+var_108], rcx
0x18003190f  lea     rcx, [rsp+1B0h+var_180]
0x180031914  mov     [rbp+0B0h+var_100], rcx
0x180031918  lea     rcx, [rsp+1B0h+var_17C]
0x18003191d  mov     [rbp+0B0h+var_F8], rcx
0x180031921  lea     rcx, [rsp+1B0h+var_160]
0x180031926  mov     [rbp+0B0h+var_F0], rcx
0x18003192a  lea     rcx, [rsp+1B0h+var_150]
0x18003192f  mov     [rbp+0B0h+var_E8], rcx
0x180031933  lea     rcx, [rbp+0B0h+var_D0]
0x180031937  mov     [rbp+0B0h+var_E0], rcx
0x18003193b  lea     rcx, [rbp+0B0h+arg_20]
0x180031942  mov     [rbp+0B0h+var_D8], rcx
0x180031946  lea     rcx, [rbp+0B0h+var_120]
0x18003194a  test    r14b, r14b
0x18003194d  jz      short loc_18003195C
0x18003194f  mov     r8, rbx
0x180031952  mov     rdx, r15
0x180031955  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x18003195a  jmp     short loc_180031973
0x18003195c  mov     [rsp+1B0h+var_188], rcx
0x180031961  mov     r9, rsi
0x180031964  mov     r8d, eax
0x180031967  mov     rdx, rbx
0x18003196a  mov     rcx, r15
0x18003196d  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180031972  nop
0x180031973  lea     rcx, [rbp+0B0h+var_D0]
0x180031977  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003197c  mov     rax, r15
0x18003197f  mov     rcx, [rbp+0B0h+var_40]
0x180031983  xor     rcx, rsp; StackCookie
0x180031986  call    __security_check_cookie
0x18003198b  mov     rbx, [rsp+1B0h+arg_8]
0x180031993  add     rsp, 180h
0x18003199a  pop     r15
0x18003199c  pop     r14
0x18003199e  pop     r13
0x1800319a0  pop     r12
0x1800319a2  pop     rdi
0x1800319a3  pop     rsi
0x1800319a4  pop     rbp
0x1800319a5  retn
0x1800319a6  lea     rcx, aIntegralCannot_0; "integral cannot be stored in wchar_t"
0x1800319ad  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

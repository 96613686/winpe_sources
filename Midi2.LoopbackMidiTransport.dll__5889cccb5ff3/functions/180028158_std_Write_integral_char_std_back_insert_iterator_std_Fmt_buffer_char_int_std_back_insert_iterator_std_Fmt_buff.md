# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180028158`
- end: `0x180028509`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180023e98`
- `0x180027868`
- `0x180028158`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b7fc`
- `0x18002dd84`
- `0x18002f4cc`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002836c`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002836c`

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
0x180028158  mov     [rsp-8+arg_8], rbx
0x18002815d  push    rbp
0x18002815e  push    rsi
0x18002815f  push    rdi
0x180028160  push    r12
0x180028162  push    r13
0x180028164  push    r14
0x180028166  push    r15
0x180028168  lea     rbp, [rsp-80h]
0x18002816d  sub     rsp, 180h
0x180028174  mov     rax, cs:__security_cookie
0x18002817b  xor     rax, rsp
0x18002817e  mov     [rbp+0B0h+var_40], rax
0x180028182  mov     rsi, r9
0x180028185  mov     rbx, rdx
0x180028188  mov     r15, rcx
0x18002818b  mov     [rsp+1B0h+var_150], r8d
0x180028190  xor     r13d, r13d
0x180028193  mov     al, [r9+8]
0x180028197  cmp     al, 63h ; 'c'
0x180028199  jnz     short loc_1800281E0
0x18002819b  lea     eax, [r8+80h]
0x1800281a2  cmp     eax, 0FFh
0x1800281a7  ja      loc_1800284FC
0x1800281ad  mov     [r9+0Bh], r13b
0x1800281b1  movaps  xmm0, xmmword ptr [r9]
0x1800281b5  movaps  [rsp+1B0h+var_170], xmm0
0x1800281ba  mov     ecx, [r9+10h]
0x1800281be  mov     [rsp+1B0h+var_160], ecx
0x1800281c2  mov     rcx, [rbp+0B0h+arg_20]
0x1800281c9  mov     [rsp+1B0h+var_190], rcx
0x1800281ce  lea     r9, [rsp+1B0h+var_170]
0x1800281d3  mov     rcx, r15
0x1800281d6  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x1800281db  jmp     loc_1800284D2
0x1800281e0  mov     edi, 2
0x1800281e5  cmp     [r9+0Ah], r13b
0x1800281e9  jnz     short loc_1800281EF
0x1800281eb  mov     [r9+0Ah], dil
0x1800281ef  cmp     al, 42h ; 'B'
0x1800281f1  jz      short loc_180028218
0x1800281f3  cmp     al, 58h ; 'X'
0x1800281f5  jz      short loc_180028211
0x1800281f7  cmp     al, 62h ; 'b'
0x1800281f9  jz      short loc_180028218
0x1800281fb  cmp     al, 6Fh ; 'o'
0x1800281fd  jz      short loc_18002820A
0x1800281ff  cmp     al, 78h ; 'x'
0x180028201  jz      short loc_180028211
0x180028203  mov     eax, 0Ah
0x180028208  jmp     short loc_18002821A
0x18002820a  mov     eax, 8
0x18002820f  jmp     short loc_18002821A
0x180028211  mov     eax, 10h
0x180028216  jmp     short loc_18002821A
0x180028218  mov     eax, edi
0x18002821a  mov     dword ptr [rsp+1B0h+var_190], eax
0x18002821e  mov     r9d, r8d
0x180028221  lea     r8, [rbp+0B0h+var_4F]
0x180028225  lea     rdx, [rbp+0B0h+var_90]
0x180028229  lea     rcx, [rsp+1B0h+var_170]
0x18002822e  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0HH@Z; std::to_chars(char * const,char * const,int,int)
0x180028233  mov     r12, [rax]
0x180028236  lea     rcx, [rbp+0B0h+var_90]
0x18002823a  mov     [rsp+1B0h+var_140], rcx
0x18002823f  mov     eax, r12d
0x180028242  sub     eax, ecx
0x180028244  mov     [rsp+1B0h+var_17C], eax
0x180028248  mov     edx, [rsp+1B0h+var_150]
0x18002824c  test    edx, edx
0x18002824e  js      short loc_18002825E
0x180028250  cmp     [rsi+0Ah], dil
0x180028254  jz      short loc_180028267
0x180028256  inc     eax
0x180028258  mov     [rsp+1B0h+var_17C], eax
0x18002825c  jmp     short loc_180028267
0x18002825e  lea     rcx, [rbp+0B0h+var_8F]
0x180028262  mov     [rsp+1B0h+var_140], rcx
0x180028267  mov     r14d, 1
0x18002826d  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180028271  jnz     short loc_180028296
0x180028273  cmp     rcx, r12
0x180028276  jz      short loc_180028296
0x180028278  mov     dl, [rcx]
0x18002827a  lea     eax, [rdx-61h]
0x18002827d  cmp     al, 19h
0x18002827f  ja      short loc_180028286
0x180028281  sub     dl, 20h ; ' '
0x180028284  mov     [rcx], dl
0x180028286  add     rcx, r14
0x180028289  cmp     rcx, r12
0x18002828c  jnz     short loc_180028278
0x18002828e  mov     eax, [rsp+1B0h+var_17C]
0x180028292  mov     edx, [rsp+1B0h+var_150]
0x180028296  mov     qword ptr [rbp+0B0h+var_130], r13
0x18002829a  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x18002829e  cmp     [rsi+0Bh], r13b
0x1800282a2  jz      short loc_180028320
0x1800282a4  mov     cl, [rsi+8]
0x1800282a7  cmp     cl, 42h ; 'B'
0x1800282aa  jz      short loc_1800282FF
0x1800282ac  cmp     cl, 58h ; 'X'
0x1800282af  jz      short loc_1800282F6
0x1800282b1  cmp     cl, 62h ; 'b'
0x1800282b4  jz      short loc_1800282ED
0x1800282b6  cmp     cl, 6Fh ; 'o'
0x1800282b9  jz      short loc_1800282C9
0x1800282bb  cmp     cl, 78h ; 'x'
0x1800282be  jnz     short loc_1800282DE
0x1800282c0  lea     rcx, a0x; "0x"
0x1800282c7  jmp     short loc_180028306
0x1800282c9  test    edx, edx
0x1800282cb  jz      short loc_1800282DE
0x1800282cd  lea     rcx, a0; "0"
0x1800282d4  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x1800282d9  mov     edi, r14d
0x1800282dc  jmp     short loc_18002830B
0x1800282de  mov     qword ptr [rsp+1B0h+var_170], r13
0x1800282e3  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x1800282e8  mov     edi, r13d
0x1800282eb  jmp     short loc_180028310
0x1800282ed  lea     rcx, a0b; "0b"
0x1800282f4  jmp     short loc_180028306
0x1800282f6  lea     rcx, a0x_0; "0X"
0x1800282fd  jmp     short loc_180028306
0x1800282ff  lea     rcx, a0b_0; "0B"
0x180028306  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x18002830b  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180028310  movaps  xmm0, [rsp+1B0h+var_170]
0x180028315  movdqa  [rbp+0B0h+var_130], xmm0
0x18002831a  add     eax, edi
0x18002831c  mov     [rsp+1B0h+var_17C], eax
0x180028320  mov     [rsp+1B0h+var_148], r13d
0x180028325  xorps   xmm0, xmm0
0x180028328  movups  [rbp+0B0h+var_D0], xmm0
0x18002832c  mov     [rbp+0B0h+var_C0], r13
0x180028330  mov     [rbp+0B0h+var_B8], 0Fh
0x180028338  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x18002833c  cmp     [rsi+0Ch], r13b
0x180028340  jz      loc_180028438
0x180028346  mov     rax, [rbp+0B0h+arg_20]
0x18002834d  test    rax, rax
0x180028350  jz      short loc_180028369
0x180028352  mov     rcx, [rax+8]
0x180028356  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x18002835b  mov     rax, [rcx]
0x18002835e  mov     rax, [rax+8]
0x180028362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028367  jmp     short loc_180028377
0x180028369  mov     cl, r14b
0x18002836c  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180028372  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180028377  lea     rcx, [rsp+1B0h+var_170]
0x18002837c  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180028381  mov     r8, rax
0x180028384  mov     rcx, [rax]
0x180028387  mov     rax, [rcx+28h]
0x18002838b  lea     rdx, [rbp+0B0h+var_B0]
0x18002838f  mov     rcx, r8
0x180028392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028397  lea     rdx, [rbp+0B0h+var_B0]
0x18002839b  lea     rcx, [rbp+0B0h+var_D0]
0x18002839f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800283a4  lea     rcx, [rbp+0B0h+var_B0]
0x1800283a8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800283ad  nop
0x1800283ae  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x1800283b3  test    rcx, rcx
0x1800283b6  jz      short loc_1800283DD
0x1800283b8  mov     rax, [rcx]
0x1800283bb  mov     rax, [rax+10h]
0x1800283bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283c4  mov     r8, rax
0x1800283c7  test    rax, rax
0x1800283ca  jz      short loc_1800283DD
0x1800283cc  mov     rcx, [rax]
0x1800283cf  mov     rax, [rcx]
0x1800283d2  mov     edx, r14d
0x1800283d5  mov     rcx, r8
0x1800283d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283dd  lea     rax, [rbp+0B0h+var_D0]
0x1800283e1  cmp     [rbp+0B0h+var_B8], 0Fh
0x1800283e6  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x1800283eb  mov     r10, [rbp+0B0h+var_C0]
0x1800283ef  mov     edx, r13d
0x1800283f2  test    r10, r10
0x1800283f5  jz      short loc_18002842A
0x1800283f7  mov     r8, r12
0x1800283fa  sub     r8, [rsp+1B0h+var_140]
0x1800283ff  movsx   r9, byte ptr [rax]
0x180028403  cmp     r8, r9
0x180028406  jbe     short loc_18002842A
0x180028408  lea     r11, [r10+rax]
0x18002840c  movsx   rcx, r9b
0x180028410  sub     r8, rcx
0x180028413  add     edx, r14d
0x180028416  lea     rcx, [rax+1]
0x18002841a  cmp     rcx, r11
0x18002841d  cmovnz  rax, rcx
0x180028421  movsx   r9, byte ptr [rax]
0x180028425  cmp     r8, r9
0x180028428  ja      short loc_18002840C
0x18002842a  mov     [rsp+1B0h+var_148], edx
0x18002842e  mov     eax, [rsp+1B0h+var_17C]
0x180028432  add     eax, edx
0x180028434  mov     [rsp+1B0h+var_17C], eax
0x180028438  cmp     [rsi+0Dh], r13b
0x18002843c  jz      short loc_180028444
0x18002843e  cmp     [rsi+9], r13b
0x180028442  jz      short loc_180028447
0x180028444  mov     r14b, r13b
0x180028447  mov     [rsp+1B0h+var_180], r14b
0x18002844c  mov     [rbp+0B0h+var_120], r12
0x180028450  mov     [rbp+0B0h+var_118], rsi
0x180028454  lea     rcx, [rsp+1B0h+var_150]
0x180028459  mov     [rbp+0B0h+var_110], rcx
0x18002845d  lea     rcx, [rbp+0B0h+var_130]
0x180028461  mov     [rbp+0B0h+var_108], rcx
0x180028465  lea     rcx, [rsp+1B0h+var_180]
0x18002846a  mov     [rbp+0B0h+var_100], rcx
0x18002846e  lea     rcx, [rsp+1B0h+var_17C]
0x180028473  mov     [rbp+0B0h+var_F8], rcx
0x180028477  lea     rcx, [rsp+1B0h+var_148]
0x18002847c  mov     [rbp+0B0h+var_F0], rcx
0x180028480  lea     rcx, [rsp+1B0h+var_140]
0x180028485  mov     [rbp+0B0h+var_E8], rcx
0x180028489  lea     rcx, [rbp+0B0h+var_D0]
0x18002848d  mov     [rbp+0B0h+var_E0], rcx
0x180028491  lea     rcx, [rbp+0B0h+arg_20]
0x180028498  mov     [rbp+0B0h+var_D8], rcx
0x18002849c  lea     rcx, [rbp+0B0h+var_120]
0x1800284a0  test    r14b, r14b
0x1800284a3  jz      short loc_1800284B2
0x1800284a5  mov     r8, rbx
0x1800284a8  mov     rdx, r15
0x1800284ab  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800284b0  jmp     short loc_1800284C9
0x1800284b2  mov     [rsp+1B0h+var_188], rcx
0x1800284b7  mov     r9, rsi
0x1800284ba  mov     r8d, eax
0x1800284bd  mov     rdx, rbx
0x1800284c0  mov     rcx, r15
0x1800284c3  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@2@YA?AV12@V12@HU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@0@YA?AV10@0HU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800284c8  nop
0x1800284c9  lea     rcx, [rbp+0B0h+var_D0]
0x1800284cd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800284d2  mov     rax, r15
0x1800284d5  mov     rcx, [rbp+0B0h+var_40]
0x1800284d9  xor     rcx, rsp; StackCookie
0x1800284dc  call    __security_check_cookie
0x1800284e1  mov     rbx, [rsp+1B0h+arg_8]
0x1800284e9  add     rsp, 180h
0x1800284f0  pop     r15
0x1800284f2  pop     r14
0x1800284f4  pop     r13
0x1800284f6  pop     r12
0x1800284f8  pop     rdi
0x1800284f9  pop     rsi
0x1800284fa  pop     rbp
0x1800284fb  retn
0x1800284fc  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180028503  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x180031d7c`
- end: `0x180032127`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@_KU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
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
- `0x180031d7c`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034ea8`
- `0x180040fac`
- `0x180043734`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031f88`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031f88`

## pseudocode

```c
__int64 __fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>(
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
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
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
0x180031d7c  mov     [rsp-8+arg_8], rbx
0x180031d81  push    rbp
0x180031d82  push    rsi
0x180031d83  push    rdi
0x180031d84  push    r12
0x180031d86  push    r13
0x180031d88  push    r14
0x180031d8a  push    r15
0x180031d8c  lea     rbp, [rsp-80h]
0x180031d91  sub     rsp, 180h
0x180031d98  mov     rax, cs:__security_cookie
0x180031d9f  xor     rax, rsp
0x180031da2  mov     [rbp+0B0h+var_40], rax
0x180031da6  mov     rsi, r9
0x180031da9  mov     rbx, rdx
0x180031dac  mov     r15, rcx
0x180031daf  mov     [rsp+1B0h+var_158], r8
0x180031db4  xor     r13d, r13d
0x180031db7  mov     al, [r9+8]
0x180031dbb  cmp     al, 63h ; 'c'
0x180031dbd  jnz     short loc_180031DFE
0x180031dbf  cmp     r8, 0FFFFh
0x180031dc6  ja      loc_18003211A
0x180031dcc  mov     [r9+0Bh], r13b
0x180031dd0  movaps  xmm0, xmmword ptr [r9]
0x180031dd4  movaps  [rsp+1B0h+var_140], xmm0
0x180031dd9  mov     ecx, [r9+10h]
0x180031ddd  mov     [rbp+0B0h+var_130], ecx
0x180031de0  mov     rcx, [rbp+0B0h+arg_20]
0x180031de7  mov     [rsp+1B0h+var_190], rcx
0x180031dec  lea     r9, [rsp+1B0h+var_140]
0x180031df1  mov     rcx, r15
0x180031df4  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x180031df9  jmp     loc_1800320F0
0x180031dfe  mov     edi, 2
0x180031e03  cmp     [r9+0Ah], r13b
0x180031e07  jnz     short loc_180031E0D
0x180031e09  mov     [r9+0Ah], dil
0x180031e0d  cmp     al, 42h ; 'B'
0x180031e0f  jz      short loc_180031E36
0x180031e11  cmp     al, 58h ; 'X'
0x180031e13  jz      short loc_180031E2F
0x180031e15  cmp     al, 62h ; 'b'
0x180031e17  jz      short loc_180031E36
0x180031e19  cmp     al, 6Fh ; 'o'
0x180031e1b  jz      short loc_180031E28
0x180031e1d  cmp     al, 78h ; 'x'
0x180031e1f  jz      short loc_180031E2F
0x180031e21  mov     eax, 0Ah
0x180031e26  jmp     short loc_180031E38
0x180031e28  mov     eax, 8
0x180031e2d  jmp     short loc_180031E38
0x180031e2f  mov     eax, 10h
0x180031e34  jmp     short loc_180031E38
0x180031e36  mov     eax, edi
0x180031e38  mov     dword ptr [rsp+1B0h+var_190], eax
0x180031e3c  mov     r9, r8
0x180031e3f  lea     r8, [rbp+0B0h+var_4F]
0x180031e43  lea     rdx, [rbp+0B0h+var_90]
0x180031e47  lea     rcx, [rsp+1B0h+var_140]
0x180031e4c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0_KH@Z; std::to_chars(char * const,char * const,unsigned __int64,int)
0x180031e51  mov     r12, [rax]
0x180031e54  lea     rcx, [rbp+0B0h+var_90]
0x180031e58  mov     [rsp+1B0h+var_150], rcx
0x180031e5d  mov     eax, r12d
0x180031e60  sub     eax, ecx
0x180031e62  mov     [rsp+1B0h+var_17C], eax
0x180031e66  cmp     [rsi+0Ah], dil
0x180031e6a  jz      short loc_180031E72
0x180031e6c  inc     eax
0x180031e6e  mov     [rsp+1B0h+var_17C], eax
0x180031e72  mov     r14d, 1
0x180031e78  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180031e7c  jnz     short loc_180031EA5
0x180031e7e  lea     rcx, [rbp+0B0h+var_90]
0x180031e82  lea     rdx, [rbp+0B0h+var_90]
0x180031e86  cmp     rdx, r12
0x180031e89  jz      short loc_180031EA5
0x180031e8b  mov     dl, [rcx]
0x180031e8d  lea     eax, [rdx-61h]
0x180031e90  cmp     al, 19h
0x180031e92  ja      short loc_180031E99
0x180031e94  sub     dl, 20h ; ' '
0x180031e97  mov     [rcx], dl
0x180031e99  add     rcx, r14
0x180031e9c  cmp     rcx, r12
0x180031e9f  jnz     short loc_180031E8B
0x180031ea1  mov     eax, [rsp+1B0h+var_17C]
0x180031ea5  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031eaa  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180031eaf  cmp     [rsi+0Bh], r13b
0x180031eb3  jz      loc_180031F39
0x180031eb9  mov     cl, [rsi+8]
0x180031ebc  cmp     cl, 42h ; 'B'
0x180031ebf  jz      short loc_180031F17
0x180031ec1  cmp     cl, 58h ; 'X'
0x180031ec4  jz      short loc_180031F0E
0x180031ec6  cmp     cl, 62h ; 'b'
0x180031ec9  jz      short loc_180031F05
0x180031ecb  cmp     cl, 6Fh ; 'o'
0x180031ece  jz      short loc_180031EDE
0x180031ed0  cmp     cl, 78h ; 'x'
0x180031ed3  jnz     short loc_180031EF6
0x180031ed5  lea     rcx, a0x; "0x"
0x180031edc  jmp     short loc_180031F1E
0x180031ede  cmp     [rsp+1B0h+var_158], r13
0x180031ee3  jz      short loc_180031EF6
0x180031ee5  lea     rcx, a0; "0"
0x180031eec  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180031ef1  mov     edi, r14d
0x180031ef4  jmp     short loc_180031F23
0x180031ef6  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031efb  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180031f00  mov     edi, r13d
0x180031f03  jmp     short loc_180031F28
0x180031f05  lea     rcx, a0b; "0b"
0x180031f0c  jmp     short loc_180031F1E
0x180031f0e  lea     rcx, a0x_0; "0X"
0x180031f15  jmp     short loc_180031F1E
0x180031f17  lea     rcx, a0b_0; "0B"
0x180031f1e  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x180031f23  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180031f28  movaps  xmm0, [rsp+1B0h+var_170]
0x180031f2d  movdqa  [rsp+1B0h+var_170], xmm0
0x180031f33  add     eax, edi
0x180031f35  mov     [rsp+1B0h+var_17C], eax
0x180031f39  mov     [rsp+1B0h+var_160], r13d
0x180031f3e  xorps   xmm0, xmm0
0x180031f41  movups  [rbp+0B0h+var_D0], xmm0
0x180031f45  mov     [rbp+0B0h+var_C0], r13
0x180031f49  mov     [rbp+0B0h+var_B8], 0Fh
0x180031f51  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180031f55  cmp     [rsi+0Ch], r13b
0x180031f59  jz      loc_180032055
0x180031f5f  mov     rax, [rbp+0B0h+arg_20]
0x180031f66  test    rax, rax
0x180031f69  jz      short loc_180031F85
0x180031f6b  mov     rdi, [rax+8]
0x180031f6f  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x180031f74  mov     rax, [rdi]
0x180031f77  mov     rcx, rdi
0x180031f7a  mov     rax, [rax+8]
0x180031f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f83  jmp     short loc_180031F96
0x180031f85  mov     cl, r14b
0x180031f88  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180031f8e  mov     rdi, rax
0x180031f91  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x180031f96  lea     rcx, [rsp+1B0h+var_140]
0x180031f9b  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180031fa0  mov     r8, rax
0x180031fa3  mov     rcx, [rax]
0x180031fa6  mov     rax, [rcx+28h]
0x180031faa  lea     rdx, [rbp+0B0h+var_B0]
0x180031fae  mov     rcx, r8
0x180031fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fb6  lea     rdx, [rbp+0B0h+var_B0]
0x180031fba  lea     rcx, [rbp+0B0h+var_D0]
0x180031fbe  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180031fc3  lea     rcx, [rbp+0B0h+var_B0]
0x180031fc7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180031fcc  nop
0x180031fcd  test    rdi, rdi
0x180031fd0  jz      short loc_180031FFA
0x180031fd2  mov     rax, [rdi]
0x180031fd5  mov     rcx, rdi
0x180031fd8  mov     rax, [rax+10h]
0x180031fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fe1  mov     r8, rax
0x180031fe4  test    rax, rax
0x180031fe7  jz      short loc_180031FFA
0x180031fe9  mov     rcx, [rax]
0x180031fec  mov     rax, [rcx]
0x180031fef  mov     edx, r14d
0x180031ff2  mov     rcx, r8
0x180031ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ffa  lea     rax, [rbp+0B0h+var_D0]
0x180031ffe  cmp     [rbp+0B0h+var_B8], 0Fh
0x180032003  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180032008  mov     r10, [rbp+0B0h+var_C0]
0x18003200c  mov     edx, r13d
0x18003200f  test    r10, r10
0x180032012  jz      short loc_180032047
0x180032014  mov     r8, r12
0x180032017  sub     r8, [rsp+1B0h+var_150]
0x18003201c  movsx   r9, byte ptr [rax]
0x180032020  cmp     r8, r9
0x180032023  jbe     short loc_180032047
0x180032025  lea     r11, [r10+rax]
0x180032029  movsx   rcx, r9b
0x18003202d  sub     r8, rcx
0x180032030  add     edx, r14d
0x180032033  lea     rcx, [rax+1]
0x180032037  cmp     rcx, r11
0x18003203a  cmovnz  rax, rcx
0x18003203e  movsx   r9, byte ptr [rax]
0x180032042  cmp     r8, r9
0x180032045  ja      short loc_180032029
0x180032047  mov     [rsp+1B0h+var_160], edx
0x18003204b  mov     eax, [rsp+1B0h+var_17C]
0x18003204f  add     eax, edx
0x180032051  mov     [rsp+1B0h+var_17C], eax
0x180032055  cmp     [rsi+0Dh], r13b
0x180032059  jz      short loc_180032061
0x18003205b  cmp     [rsi+9], r13b
0x18003205f  jz      short loc_180032064
0x180032061  mov     r14b, r13b
0x180032064  mov     [rsp+1B0h+var_180], r14b
0x180032069  mov     [rbp+0B0h+var_120], r12
0x18003206d  mov     [rbp+0B0h+var_118], rsi
0x180032071  lea     rcx, [rsp+1B0h+var_158]
0x180032076  mov     [rbp+0B0h+var_110], rcx
0x18003207a  lea     rcx, [rsp+1B0h+var_170]
0x18003207f  mov     [rbp+0B0h+var_108], rcx
0x180032083  lea     rcx, [rsp+1B0h+var_180]
0x180032088  mov     [rbp+0B0h+var_100], rcx
0x18003208c  lea     rcx, [rsp+1B0h+var_17C]
0x180032091  mov     [rbp+0B0h+var_F8], rcx
0x180032095  lea     rcx, [rsp+1B0h+var_160]
0x18003209a  mov     [rbp+0B0h+var_F0], rcx
0x18003209e  lea     rcx, [rsp+1B0h+var_150]
0x1800320a3  mov     [rbp+0B0h+var_E8], rcx
0x1800320a7  lea     rcx, [rbp+0B0h+var_D0]
0x1800320ab  mov     [rbp+0B0h+var_E0], rcx
0x1800320af  lea     rcx, [rbp+0B0h+arg_20]
0x1800320b6  mov     [rbp+0B0h+var_D8], rcx
0x1800320ba  lea     rcx, [rbp+0B0h+var_120]
0x1800320be  test    r14b, r14b
0x1800320c1  jz      short loc_1800320D0
0x1800320c3  mov     r8, rbx
0x1800320c6  mov     rdx, r15
0x1800320c9  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x1800320ce  jmp     short loc_1800320E7
0x1800320d0  mov     [rsp+1B0h+var_188], rcx
0x1800320d5  mov     r9, rsi
0x1800320d8  mov     r8d, eax
0x1800320db  mov     rdx, rbx
0x1800320de  mov     rcx, r15
0x1800320e1  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x1800320e6  nop
0x1800320e7  lea     rcx, [rbp+0B0h+var_D0]
0x1800320eb  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800320f0  mov     rax, r15
0x1800320f3  mov     rcx, [rbp+0B0h+var_40]
0x1800320f7  xor     rcx, rsp; StackCookie
0x1800320fa  call    __security_check_cookie
0x1800320ff  mov     rbx, [rsp+1B0h+arg_8]
0x180032107  add     rsp, 180h
0x18003210e  pop     r15
0x180032110  pop     r14
0x180032112  pop     r13
0x180032114  pop     r12
0x180032116  pop     rdi
0x180032117  pop     rsi
0x180032118  pop     rbp
0x180032119  retn
0x18003211a  lea     rcx, aIntegralCannot_0; "integral cannot be stored in wchar_t"
0x180032121  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

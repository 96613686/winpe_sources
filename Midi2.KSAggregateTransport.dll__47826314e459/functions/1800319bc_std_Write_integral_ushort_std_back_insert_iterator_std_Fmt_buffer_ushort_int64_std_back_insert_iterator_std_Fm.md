# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x1800319bc`
- end: `0x180031d75`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@_JU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002ff18`

## callees

- `0x180005020`
- `0x18002c1a4`
- `0x18002e200`
- `0x180030900`
- `0x1800319bc`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180035228`
- `0x180040fac`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031bd6`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180031bd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,__int64>(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
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
  struct std::locale::_Locimp *v18; // rdi
  __int64 v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64); // rax
  char *v21; // rax
  int v22; // edx
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r9
  char *v25; // r11
  int v27; // [rsp+20h] [rbp-E0h]
  char v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  char *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+80h] [rbp-80h]
  _QWORD v36[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v39; // [rsp+F8h] [rbp-8h]
  _BYTE v40[32]; // [rsp+100h] [rbp+0h] BYREF
  char v41; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v42[64]; // [rsp+121h] [rbp+21h] BYREF
  char v43[15]; // [rsp+161h] [rbp+61h] BYREF

  v32 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    if ( a3 > 0xFFFF )
      std::_Throw_format_error("integral cannot be stored in wchar_t");
    *((_BYTE *)a4 + 11) = 0;
    v34 = *a4;
    v35 = *((_DWORD *)a4 + 4);
    std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a1,
      a2,
      a3,
      (unsigned int)&v34,
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
  v27 = v10;
  std::_Integer_to_chars<__int64>(&v34, &v41, v43, a3);
  v11 = &v41;
  v33 = &v41;
  v12 = (char *)v34;
  v13 = v34 - (unsigned int)&v41;
  v29 = v13;
  v14 = v32;
  if ( v32 < 0 )
  {
    v11 = v42;
    v33 = v42;
  }
  else if ( *((_BYTE *)a4 + 10) != 2 )
  {
    v29 = ++v13;
  }
  v15 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 && v11 != (char *)v34 )
  {
    do
    {
      if ( (unsigned __int8)(*v11 - 97) <= 0x19u )
        *v11 -= 32;
      ++v11;
    }
    while ( v11 != v12 );
    v13 = v29;
    v14 = v32;
  }
  v30 = 0u;
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
        *((_QWORD *)&v30 + 1) = 1;
        v9 = 1;
LABEL_39:
        *(_QWORD *)&v30 = v17;
        goto LABEL_40;
      }
      break;
    case 'x':
      v17 = "0x";
LABEL_38:
      *((_QWORD *)&v30 + 1) = 2;
      goto LABEL_39;
  }
  v30 = 0u;
  v9 = 0;
LABEL_40:
  v13 += v9;
  v29 = v13;
LABEL_41:
  v31 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 15;
  LOBYTE(v37) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      v18 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v34 + 1) = v18;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 8LL))(v18);
    }
    else
    {
      v18 = std::locale::_Init(1);
      *((_QWORD *)&v34 + 1) = v18;
    }
    v19 = std::use_facet<std::numpunct<unsigned short>>(&v34);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v19 + 40LL))(v19, v40);
    std::string::operator=(&v37, v40);
    std::string::~string(v40);
    if ( v18 )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v20 )
        (**v20)(v20, 1);
    }
    v21 = (char *)&v37;
    if ( v39 > 0xF )
      v21 = (char *)v37;
    v22 = 0;
    if ( v38 )
    {
      v23 = v12 - v33;
      v24 = *v21;
      if ( v12 - v33 > v24 )
      {
        v25 = &v21[v38];
        do
        {
          v23 -= (char)v24;
          ++v22;
          if ( v21 + 1 != v25 )
            ++v21;
          v24 = *v21;
        }
        while ( v23 > v24 );
      }
    }
    v31 = v22;
    v13 = v22 + v29;
    v29 += v22;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v15 = 0;
  v28 = v15;
  v36[0] = v12;
  v36[1] = a4;
  v36[2] = &v32;
  v36[3] = &v30;
  v36[4] = &v28;
  v36[5] = &v29;
  v36[6] = &v31;
  v36[7] = &v33;
  v36[8] = &v37;
  v36[9] = &a5;
  if ( v15 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,__int64>'::`2'::_lambda_1_::operator()(
      v36,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std___J_2_YA_AV12_V12__JU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std___J_0_YA_AV10_0_JU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v13,
      (_DWORD)a4,
      v27,
      (__int64)v36);
  std::string::~string(&v37);
  return a1;
}

```

## disassembly

```asm
0x1800319bc  mov     [rsp-8+arg_8], rbx
0x1800319c1  push    rbp
0x1800319c2  push    rsi
0x1800319c3  push    rdi
0x1800319c4  push    r12
0x1800319c6  push    r13
0x1800319c8  push    r14
0x1800319ca  push    r15
0x1800319cc  lea     rbp, [rsp-80h]
0x1800319d1  sub     rsp, 180h
0x1800319d8  mov     rax, cs:__security_cookie
0x1800319df  xor     rax, rsp
0x1800319e2  mov     [rbp+0B0h+var_40], rax
0x1800319e6  mov     rsi, r9
0x1800319e9  mov     rbx, rdx
0x1800319ec  mov     r15, rcx
0x1800319ef  mov     [rsp+1B0h+var_158], r8
0x1800319f4  xor     r13d, r13d
0x1800319f7  mov     al, [r9+8]
0x1800319fb  cmp     al, 63h ; 'c'
0x1800319fd  jnz     short loc_180031A3E
0x1800319ff  cmp     r8, 0FFFFh
0x180031a06  ja      loc_180031D68
0x180031a0c  mov     [r9+0Bh], r13b
0x180031a10  movaps  xmm0, xmmword ptr [r9]
0x180031a14  movaps  [rsp+1B0h+var_140], xmm0
0x180031a19  mov     ecx, [r9+10h]
0x180031a1d  mov     [rbp+0B0h+var_130], ecx
0x180031a20  mov     rcx, [rbp+0B0h+arg_20]
0x180031a27  mov     [rsp+1B0h+var_190], rcx
0x180031a2c  lea     r9, [rsp+1B0h+var_140]
0x180031a31  mov     rcx, r15
0x180031a34  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x180031a39  jmp     loc_180031D3E
0x180031a3e  mov     edi, 2
0x180031a43  cmp     [r9+0Ah], r13b
0x180031a47  jnz     short loc_180031A4D
0x180031a49  mov     [r9+0Ah], dil
0x180031a4d  cmp     al, 42h ; 'B'
0x180031a4f  jz      short loc_180031A76
0x180031a51  cmp     al, 58h ; 'X'
0x180031a53  jz      short loc_180031A6F
0x180031a55  cmp     al, 62h ; 'b'
0x180031a57  jz      short loc_180031A76
0x180031a59  cmp     al, 6Fh ; 'o'
0x180031a5b  jz      short loc_180031A68
0x180031a5d  cmp     al, 78h ; 'x'
0x180031a5f  jz      short loc_180031A6F
0x180031a61  mov     eax, 0Ah
0x180031a66  jmp     short loc_180031A78
0x180031a68  mov     eax, 8
0x180031a6d  jmp     short loc_180031A78
0x180031a6f  mov     eax, 10h
0x180031a74  jmp     short loc_180031A78
0x180031a76  mov     eax, edi
0x180031a78  mov     dword ptr [rsp+1B0h+var_190], eax
0x180031a7c  mov     r9, r8
0x180031a7f  lea     r8, [rbp+0B0h+var_4F]
0x180031a83  lea     rdx, [rbp+0B0h+var_90]
0x180031a87  lea     rcx, [rsp+1B0h+var_140]
0x180031a8c  call    ??$_Integer_to_chars@_J@std@@YA?AUto_chars_result@0@PEADQEAD_JH@Z; std::_Integer_to_chars<__int64>(char *,char * const,__int64,int)
0x180031a91  lea     rcx, [rbp+0B0h+var_90]
0x180031a95  mov     [rsp+1B0h+var_150], rcx
0x180031a9a  mov     r12, qword ptr [rsp+1B0h+var_140]
0x180031a9f  mov     eax, r12d
0x180031aa2  sub     eax, ecx
0x180031aa4  mov     [rsp+1B0h+var_17C], eax
0x180031aa8  mov     rdx, [rsp+1B0h+var_158]
0x180031aad  test    rdx, rdx
0x180031ab0  js      short loc_180031AC0
0x180031ab2  cmp     [rsi+0Ah], dil
0x180031ab6  jz      short loc_180031AC9
0x180031ab8  inc     eax
0x180031aba  mov     [rsp+1B0h+var_17C], eax
0x180031abe  jmp     short loc_180031AC9
0x180031ac0  lea     rcx, [rbp+0B0h+var_8F]
0x180031ac4  mov     [rsp+1B0h+var_150], rcx
0x180031ac9  mov     r14d, 1
0x180031acf  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180031ad3  jnz     short loc_180031AF9
0x180031ad5  cmp     rcx, r12
0x180031ad8  jz      short loc_180031AF9
0x180031ada  mov     dl, [rcx]
0x180031adc  lea     eax, [rdx-61h]
0x180031adf  cmp     al, 19h
0x180031ae1  ja      short loc_180031AE8
0x180031ae3  sub     dl, 20h ; ' '
0x180031ae6  mov     [rcx], dl
0x180031ae8  add     rcx, r14
0x180031aeb  cmp     rcx, r12
0x180031aee  jnz     short loc_180031ADA
0x180031af0  mov     eax, [rsp+1B0h+var_17C]
0x180031af4  mov     rdx, [rsp+1B0h+var_158]
0x180031af9  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031afe  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180031b03  cmp     [rsi+0Bh], r13b
0x180031b07  jz      short loc_180031B87
0x180031b09  mov     cl, [rsi+8]
0x180031b0c  cmp     cl, 42h ; 'B'
0x180031b0f  jz      short loc_180031B65
0x180031b11  cmp     cl, 58h ; 'X'
0x180031b14  jz      short loc_180031B5C
0x180031b16  cmp     cl, 62h ; 'b'
0x180031b19  jz      short loc_180031B53
0x180031b1b  cmp     cl, 6Fh ; 'o'
0x180031b1e  jz      short loc_180031B2E
0x180031b20  cmp     cl, 78h ; 'x'
0x180031b23  jnz     short loc_180031B44
0x180031b25  lea     rcx, a0x; "0x"
0x180031b2c  jmp     short loc_180031B6C
0x180031b2e  test    rdx, rdx
0x180031b31  jz      short loc_180031B44
0x180031b33  lea     rcx, a0; "0"
0x180031b3a  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180031b3f  mov     edi, r14d
0x180031b42  jmp     short loc_180031B71
0x180031b44  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031b49  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180031b4e  mov     edi, r13d
0x180031b51  jmp     short loc_180031B76
0x180031b53  lea     rcx, a0b; "0b"
0x180031b5a  jmp     short loc_180031B6C
0x180031b5c  lea     rcx, a0x_0; "0X"
0x180031b63  jmp     short loc_180031B6C
0x180031b65  lea     rcx, a0b_0; "0B"
0x180031b6c  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x180031b71  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180031b76  movaps  xmm0, [rsp+1B0h+var_170]
0x180031b7b  movdqa  [rsp+1B0h+var_170], xmm0
0x180031b81  add     eax, edi
0x180031b83  mov     [rsp+1B0h+var_17C], eax
0x180031b87  mov     [rsp+1B0h+var_160], r13d
0x180031b8c  xorps   xmm0, xmm0
0x180031b8f  movups  [rbp+0B0h+var_D0], xmm0
0x180031b93  mov     [rbp+0B0h+var_C0], r13
0x180031b97  mov     [rbp+0B0h+var_B8], 0Fh
0x180031b9f  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180031ba3  cmp     [rsi+0Ch], r13b
0x180031ba7  jz      loc_180031CA3
0x180031bad  mov     rax, [rbp+0B0h+arg_20]
0x180031bb4  test    rax, rax
0x180031bb7  jz      short loc_180031BD3
0x180031bb9  mov     rdi, [rax+8]
0x180031bbd  mov     qword ptr [rsp+1B0h+var_140+8], rdi
0x180031bc2  mov     rax, [rdi]
0x180031bc5  mov     rcx, rdi
0x180031bc8  mov     rax, [rax+8]
0x180031bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bd1  jmp     short loc_180031BE4
0x180031bd3  mov     cl, r14b
0x180031bd6  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180031bdc  mov     rdi, rax
0x180031bdf  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x180031be4  lea     rcx, [rsp+1B0h+var_140]
0x180031be9  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180031bee  mov     r8, rax
0x180031bf1  mov     rcx, [rax]
0x180031bf4  mov     rax, [rcx+28h]
0x180031bf8  lea     rdx, [rbp+0B0h+var_B0]
0x180031bfc  mov     rcx, r8
0x180031bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c04  lea     rdx, [rbp+0B0h+var_B0]
0x180031c08  lea     rcx, [rbp+0B0h+var_D0]
0x180031c0c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180031c11  lea     rcx, [rbp+0B0h+var_B0]
0x180031c15  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180031c1a  nop
0x180031c1b  test    rdi, rdi
0x180031c1e  jz      short loc_180031C48
0x180031c20  mov     rax, [rdi]
0x180031c23  mov     rcx, rdi
0x180031c26  mov     rax, [rax+10h]
0x180031c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c2f  mov     r8, rax
0x180031c32  test    rax, rax
0x180031c35  jz      short loc_180031C48
0x180031c37  mov     rcx, [rax]
0x180031c3a  mov     rax, [rcx]
0x180031c3d  mov     edx, r14d
0x180031c40  mov     rcx, r8
0x180031c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c48  lea     rax, [rbp+0B0h+var_D0]
0x180031c4c  cmp     [rbp+0B0h+var_B8], 0Fh
0x180031c51  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180031c56  mov     r10, [rbp+0B0h+var_C0]
0x180031c5a  mov     edx, r13d
0x180031c5d  test    r10, r10
0x180031c60  jz      short loc_180031C95
0x180031c62  mov     r8, r12
0x180031c65  sub     r8, [rsp+1B0h+var_150]
0x180031c6a  movsx   r9, byte ptr [rax]
0x180031c6e  cmp     r8, r9
0x180031c71  jbe     short loc_180031C95
0x180031c73  lea     r11, [r10+rax]
0x180031c77  movsx   rcx, r9b
0x180031c7b  sub     r8, rcx
0x180031c7e  add     edx, r14d
0x180031c81  lea     rcx, [rax+1]
0x180031c85  cmp     rcx, r11
0x180031c88  cmovnz  rax, rcx
0x180031c8c  movsx   r9, byte ptr [rax]
0x180031c90  cmp     r8, r9
0x180031c93  ja      short loc_180031C77
0x180031c95  mov     [rsp+1B0h+var_160], edx
0x180031c99  mov     eax, [rsp+1B0h+var_17C]
0x180031c9d  add     eax, edx
0x180031c9f  mov     [rsp+1B0h+var_17C], eax
0x180031ca3  cmp     [rsi+0Dh], r13b
0x180031ca7  jz      short loc_180031CAF
0x180031ca9  cmp     [rsi+9], r13b
0x180031cad  jz      short loc_180031CB2
0x180031caf  mov     r14b, r13b
0x180031cb2  mov     [rsp+1B0h+var_180], r14b
0x180031cb7  mov     [rbp+0B0h+var_120], r12
0x180031cbb  mov     [rbp+0B0h+var_118], rsi
0x180031cbf  lea     rcx, [rsp+1B0h+var_158]
0x180031cc4  mov     [rbp+0B0h+var_110], rcx
0x180031cc8  lea     rcx, [rsp+1B0h+var_170]
0x180031ccd  mov     [rbp+0B0h+var_108], rcx
0x180031cd1  lea     rcx, [rsp+1B0h+var_180]
0x180031cd6  mov     [rbp+0B0h+var_100], rcx
0x180031cda  lea     rcx, [rsp+1B0h+var_17C]
0x180031cdf  mov     [rbp+0B0h+var_F8], rcx
0x180031ce3  lea     rcx, [rsp+1B0h+var_160]
0x180031ce8  mov     [rbp+0B0h+var_F0], rcx
0x180031cec  lea     rcx, [rsp+1B0h+var_150]
0x180031cf1  mov     [rbp+0B0h+var_E8], rcx
0x180031cf5  lea     rcx, [rbp+0B0h+var_D0]
0x180031cf9  mov     [rbp+0B0h+var_E0], rcx
0x180031cfd  lea     rcx, [rbp+0B0h+arg_20]
0x180031d04  mov     [rbp+0B0h+var_D8], rcx
0x180031d08  lea     rcx, [rbp+0B0h+var_120]
0x180031d0c  test    r14b, r14b
0x180031d0f  jz      short loc_180031D1E
0x180031d11  mov     r8, rbx
0x180031d14  mov     rdx, r15
0x180031d17  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_JU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180031d1c  jmp     short loc_180031D35
0x180031d1e  mov     [rsp+1B0h+var_188], rcx
0x180031d23  mov     r9, rsi
0x180031d26  mov     r8d, eax
0x180031d29  mov     rdx, rbx
0x180031d2c  mov     rcx, r15
0x180031d2f  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@2@YA?AV12@V12@_JU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@0@YA?AV10@0_JU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180031d34  nop
0x180031d35  lea     rcx, [rbp+0B0h+var_D0]
0x180031d39  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180031d3e  mov     rax, r15
0x180031d41  mov     rcx, [rbp+0B0h+var_40]
0x180031d45  xor     rcx, rsp; StackCookie
0x180031d48  call    __security_check_cookie
0x180031d4d  mov     rbx, [rsp+1B0h+arg_8]
0x180031d55  add     rsp, 180h
0x180031d5c  pop     r15
0x180031d5e  pop     r14
0x180031d60  pop     r13
0x180031d62  pop     r12
0x180031d64  pop     rdi
0x180031d65  pop     rsi
0x180031d66  pop     rbp
0x180031d67  retn
0x180031d68  lea     rcx, aIntegralCannot_0; "integral cannot be stored in wchar_t"
0x180031d6f  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

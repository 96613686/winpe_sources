# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x180030e60`
- end: `0x180031244`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@G@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `996`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002c1a4`
- `0x180030e60`

## callees

- `0x180005020`
- `0x18002c298`
- `0x180030748`
- `0x180030e60`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034ea8`
- `0x180042e48`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800310b4`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800310b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned short>(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        __int128 *a4,
        __int64 a5)
{
  char v8; // al
  __int128 v9; // xmm0
  int v10; // ecx
  int v11; // edi
  int v12; // eax
  _BYTE *v13; // r12
  unsigned int v14; // eax
  char v15; // r14
  _BYTE *v16; // rcx
  char v17; // cl
  const char *v18; // rcx
  struct std::locale::_Locimp *v19; // rdi
  __int64 v20; // rax
  void (__fastcall ***v21)(_QWORD, __int64); // rax
  char *v22; // rax
  int v23; // edx
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r9
  char *v26; // r11
  int v28; // [rsp+20h] [rbp-E0h]
  char v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  _BYTE *v37; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v38[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v41; // [rsp+F8h] [rbp-8h]
  __int128 v42; // [rsp+100h] [rbp+0h] BYREF
  int v43; // [rsp+110h] [rbp+10h]
  _BYTE v44[65]; // [rsp+120h] [rbp+20h] BYREF
  char v45[15]; // [rsp+161h] [rbp+61h] BYREF

  v31 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
    *((_BYTE *)a4 + 11) = 0;
    v9 = *a4;
    v42 = *a4;
    v43 = *((_DWORD *)a4 + 4);
    v33 = a3;
    v10 = *((_DWORD *)a4 + 2);
    if ( !(_BYTE)v10 || (_BYTE)v10 == 99 )
    {
      *(_QWORD *)&v35 = &v33;
      *((_QWORD *)&v35 + 1) = 1;
      std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
        a1,
        a2,
        &v35,
        &v42,
        a5);
    }
    else
    {
      v35 = v9;
      v36 = *((_DWORD *)a4 + 4);
      std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned short>(
        a1,
        a2,
        a3,
        (unsigned int)&v35,
        a5);
    }
    return a1;
  }
  v11 = 2;
  if ( !*((_BYTE *)a4 + 10) )
    *((_BYTE *)a4 + 10) = 2;
  if ( v8 != 66 )
  {
    if ( v8 == 88 )
    {
LABEL_15:
      v12 = 16;
      goto LABEL_17;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v12 = 8;
        goto LABEL_17;
      }
      if ( v8 != 120 )
      {
        v12 = 10;
        goto LABEL_17;
      }
      goto LABEL_15;
    }
  }
  v12 = 2;
LABEL_17:
  v28 = v12;
  v13 = *(_BYTE **)std::to_chars(&v35, v44, v45, a3);
  v37 = v44;
  v14 = (_DWORD)v13 - (unsigned int)v44;
  v30 = v14;
  if ( *((_BYTE *)a4 + 10) != 2 )
    v30 = ++v14;
  v15 = 1;
  if ( *((_BYTE *)a4 + 8) == 88 )
  {
    v16 = v44;
    if ( v44 != v13 )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v13 );
      v14 = v30;
    }
  }
  v32 = 0u;
  if ( !*((_BYTE *)a4 + 11) )
    goto LABEL_41;
  v17 = *((_BYTE *)a4 + 8);
  switch ( v17 )
  {
    case 'B':
      v18 = "0B";
      goto LABEL_38;
    case 'X':
      v18 = "0X";
      goto LABEL_38;
    case 'b':
      v18 = "0b";
      goto LABEL_38;
    case 'o':
      if ( v31 )
      {
        v18 = "0";
        *((_QWORD *)&v32 + 1) = 1;
        v11 = 1;
LABEL_39:
        *(_QWORD *)&v32 = v18;
        goto LABEL_40;
      }
      break;
    case 'x':
      v18 = "0x";
LABEL_38:
      *((_QWORD *)&v32 + 1) = 2;
      goto LABEL_39;
  }
  v32 = 0u;
  v11 = 0;
LABEL_40:
  v14 += v11;
  v30 = v14;
LABEL_41:
  v34 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 15;
  LOBYTE(v39) = 0;
  if ( *((_BYTE *)a4 + 12) )
  {
    if ( a5 )
    {
      v19 = *(struct std::locale::_Locimp **)(a5 + 8);
      *((_QWORD *)&v35 + 1) = v19;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v19 + 8LL))(v19);
    }
    else
    {
      v19 = std::locale::_Init(1);
      *((_QWORD *)&v35 + 1) = v19;
    }
    v20 = std::use_facet<std::numpunct<unsigned short>>(&v35);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v20 + 40LL))(v20, &v42);
    std::string::operator=(&v39, &v42);
    std::string::~string(&v42);
    if ( v19 )
    {
      v21 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v21 )
        (**v21)(v21, 1);
    }
    v22 = (char *)&v39;
    if ( v41 > 0xF )
      v22 = (char *)v39;
    v23 = 0;
    if ( v40 )
    {
      v24 = v13 - v37;
      v25 = *v22;
      if ( v13 - v37 > v25 )
      {
        v26 = &v22[v40];
        do
        {
          v24 -= (char)v25;
          ++v23;
          if ( v22 + 1 != v26 )
            ++v22;
          v25 = *v22;
        }
        while ( v24 > v25 );
      }
    }
    v34 = v23;
    v14 = v23 + v30;
    v30 += v23;
  }
  if ( !*((_BYTE *)a4 + 13) || *((_BYTE *)a4 + 9) )
    v15 = 0;
  v29 = v15;
  v38[0] = v13;
  v38[1] = a4;
  v38[2] = &v31;
  v38[3] = &v32;
  v38[4] = &v29;
  v38[5] = &v30;
  v38[6] = &v34;
  v38[7] = &v37;
  v38[8] = &v39;
  v38[9] = &a5;
  if ( v15 )
    `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
      v38,
      a1,
      a2);
  else
    ____Write_aligned_V__back_insert_iterator_V___Fmt_buffer_G_std___std__U___Basic_format_specs_G_2_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_2_YA_AV12_V12_IU32_V_Lazy_locale_2__Z__std__YA_AV__back_insert_iterator_V___Fmt_buffer_G_std___0_V10_HAEBU___Basic_format_specs_G_0_W4_Fmt_align_0_AEAV_lambda_1___1_____Write_integral_GV__back_insert_iterator_V___Fmt_buffer_G_std___std__I_0_YA_AV10_0IU20_V_Lazy_locale_0__Z__Z(
      a1,
      a2,
      v14,
      (_DWORD)a4,
      v28,
      (__int64)v38);
  std::string::~string(&v39);
  return a1;
}

```

## disassembly

```asm
0x180030e60  mov     [rsp-8+arg_8], rbx
0x180030e65  push    rbp
0x180030e66  push    rsi
0x180030e67  push    rdi
0x180030e68  push    r12
0x180030e6a  push    r13
0x180030e6c  push    r14
0x180030e6e  push    r15
0x180030e70  lea     rbp, [rsp-80h]
0x180030e75  sub     rsp, 180h
0x180030e7c  mov     rax, cs:__security_cookie
0x180030e83  xor     rax, rsp
0x180030e86  mov     [rbp+0B0h+var_40], rax
0x180030e8a  mov     rsi, r9
0x180030e8d  mov     rbx, rdx
0x180030e90  mov     r15, rcx
0x180030e93  mov     [rsp+1B0h+var_178], r8w
0x180030e99  xor     r13d, r13d
0x180030e9c  mov     al, [r9+8]
0x180030ea0  cmp     al, 63h ; 'c'
0x180030ea2  jnz     loc_180030F29
0x180030ea8  mov     [r9+0Bh], r13b
0x180030eac  movups  xmm0, xmmword ptr [r9]
0x180030eb0  movaps  [rbp+0B0h+var_B0], xmm0
0x180030eb4  mov     eax, [r9+10h]
0x180030eb8  mov     [rbp+0B0h+var_A0], eax
0x180030ebb  mov     rax, [rbp+0B0h+arg_20]
0x180030ec2  mov     [rsp+1B0h+var_160], r8w
0x180030ec8  mov     ecx, [r9+8]
0x180030ecc  test    cl, cl
0x180030ece  jz      short loc_180030EF9
0x180030ed0  cmp     cl, 63h ; 'c'
0x180030ed3  jz      short loc_180030EF9
0x180030ed5  movaps  [rsp+1B0h+var_150], xmm0
0x180030eda  mov     ecx, [r9+10h]
0x180030ede  mov     [rsp+1B0h+var_140], ecx
0x180030ee2  mov     [rsp+1B0h+var_190], rax
0x180030ee7  lea     r9, [rsp+1B0h+var_150]
0x180030eec  mov     rcx, r15
0x180030eef  call    ??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@G@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x180030ef4  jmp     loc_18003121A
0x180030ef9  lea     rcx, [rsp+1B0h+var_160]
0x180030efe  mov     qword ptr [rsp+1B0h+var_150], rcx
0x180030f03  mov     r14d, 1
0x180030f09  mov     qword ptr [rsp+1B0h+var_150+8], r14
0x180030f0e  mov     [rsp+1B0h+var_190], rax
0x180030f13  lea     r9, [rbp+0B0h+var_B0]
0x180030f17  lea     r8, [rsp+1B0h+var_150]
0x180030f1c  mov     rcx, r15
0x180030f1f  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@V?$basic_string_view@GU?$char_traits@G@std@@@0@AEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::basic_string_view<ushort>,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)
0x180030f24  jmp     loc_18003121A
0x180030f29  mov     edi, 2
0x180030f2e  cmp     [r9+0Ah], r13b
0x180030f32  jnz     short loc_180030F38
0x180030f34  mov     [r9+0Ah], dil
0x180030f38  cmp     al, 42h ; 'B'
0x180030f3a  jz      short loc_180030F61
0x180030f3c  cmp     al, 58h ; 'X'
0x180030f3e  jz      short loc_180030F5A
0x180030f40  cmp     al, 62h ; 'b'
0x180030f42  jz      short loc_180030F61
0x180030f44  cmp     al, 6Fh ; 'o'
0x180030f46  jz      short loc_180030F53
0x180030f48  cmp     al, 78h ; 'x'
0x180030f4a  jz      short loc_180030F5A
0x180030f4c  mov     eax, 0Ah
0x180030f51  jmp     short loc_180030F63
0x180030f53  mov     eax, 8
0x180030f58  jmp     short loc_180030F63
0x180030f5a  mov     eax, 10h
0x180030f5f  jmp     short loc_180030F63
0x180030f61  mov     eax, edi
0x180030f63  mov     dword ptr [rsp+1B0h+var_190], eax
0x180030f67  movzx   r9d, r8w
0x180030f6b  lea     r8, [rbp+0B0h+var_4F]
0x180030f6f  lea     rdx, [rbp+0B0h+var_90]
0x180030f73  lea     rcx, [rsp+1B0h+var_150]
0x180030f78  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0GH@Z; std::to_chars(char * const,char * const,ushort,int)
0x180030f7d  mov     r12, [rax]
0x180030f80  lea     rcx, [rbp+0B0h+var_90]
0x180030f84  mov     [rbp+0B0h+var_130], rcx
0x180030f88  mov     eax, r12d
0x180030f8b  sub     eax, ecx
0x180030f8d  mov     [rsp+1B0h+var_17C], eax
0x180030f91  cmp     [rsi+0Ah], dil
0x180030f95  jz      short loc_180030F9D
0x180030f97  inc     eax
0x180030f99  mov     [rsp+1B0h+var_17C], eax
0x180030f9d  mov     r14d, 1
0x180030fa3  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180030fa7  jnz     short loc_180030FD0
0x180030fa9  lea     rcx, [rbp+0B0h+var_90]
0x180030fad  lea     rdx, [rbp+0B0h+var_90]
0x180030fb1  cmp     rdx, r12
0x180030fb4  jz      short loc_180030FD0
0x180030fb6  mov     dl, [rcx]
0x180030fb8  lea     eax, [rdx-61h]
0x180030fbb  cmp     al, 19h
0x180030fbd  ja      short loc_180030FC4
0x180030fbf  sub     dl, 20h ; ' '
0x180030fc2  mov     [rcx], dl
0x180030fc4  add     rcx, r14
0x180030fc7  cmp     rcx, r12
0x180030fca  jnz     short loc_180030FB6
0x180030fcc  mov     eax, [rsp+1B0h+var_17C]
0x180030fd0  mov     qword ptr [rsp+1B0h+var_170], r13
0x180030fd5  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180030fda  cmp     [rsi+0Bh], r13b
0x180030fde  jz      loc_180031065
0x180030fe4  mov     cl, [rsi+8]
0x180030fe7  cmp     cl, 42h ; 'B'
0x180030fea  jz      short loc_180031043
0x180030fec  cmp     cl, 58h ; 'X'
0x180030fef  jz      short loc_18003103A
0x180030ff1  cmp     cl, 62h ; 'b'
0x180030ff4  jz      short loc_180031031
0x180030ff6  cmp     cl, 6Fh ; 'o'
0x180030ff9  jz      short loc_180031009
0x180030ffb  cmp     cl, 78h ; 'x'
0x180030ffe  jnz     short loc_180031022
0x180031000  lea     rcx, a0x; "0x"
0x180031007  jmp     short loc_18003104A
0x180031009  cmp     [rsp+1B0h+var_178], r13w
0x18003100f  jz      short loc_180031022
0x180031011  lea     rcx, a0; "0"
0x180031018  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x18003101d  mov     edi, r14d
0x180031020  jmp     short loc_18003104F
0x180031022  mov     qword ptr [rsp+1B0h+var_170], r13
0x180031027  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x18003102c  mov     edi, r13d
0x18003102f  jmp     short loc_180031054
0x180031031  lea     rcx, a0b; "0b"
0x180031038  jmp     short loc_18003104A
0x18003103a  lea     rcx, a0x_0; "0X"
0x180031041  jmp     short loc_18003104A
0x180031043  lea     rcx, a0b_0; "0B"
0x18003104a  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x18003104f  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180031054  movaps  xmm0, [rsp+1B0h+var_170]
0x180031059  movdqa  [rsp+1B0h+var_170], xmm0
0x18003105f  add     eax, edi
0x180031061  mov     [rsp+1B0h+var_17C], eax
0x180031065  mov     [rsp+1B0h+var_158], r13d
0x18003106a  xorps   xmm0, xmm0
0x18003106d  movups  [rbp+0B0h+var_D0], xmm0
0x180031071  mov     [rbp+0B0h+var_C0], r13
0x180031075  mov     [rbp+0B0h+var_B8], 0Fh
0x18003107d  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180031081  cmp     [rsi+0Ch], r13b
0x180031085  jz      loc_180031180
0x18003108b  mov     rax, [rbp+0B0h+arg_20]
0x180031092  test    rax, rax
0x180031095  jz      short loc_1800310B1
0x180031097  mov     rdi, [rax+8]
0x18003109b  mov     qword ptr [rsp+1B0h+var_150+8], rdi
0x1800310a0  mov     rax, [rdi]
0x1800310a3  mov     rcx, rdi
0x1800310a6  mov     rax, [rax+8]
0x1800310aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310af  jmp     short loc_1800310C2
0x1800310b1  mov     cl, r14b
0x1800310b4  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1800310ba  mov     rdi, rax
0x1800310bd  mov     qword ptr [rsp+1B0h+var_150+8], rax
0x1800310c2  lea     rcx, [rsp+1B0h+var_150]
0x1800310c7  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x1800310cc  mov     r8, rax
0x1800310cf  mov     rcx, [rax]
0x1800310d2  mov     rax, [rcx+28h]
0x1800310d6  lea     rdx, [rbp+0B0h+var_B0]
0x1800310da  mov     rcx, r8
0x1800310dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310e2  lea     rdx, [rbp+0B0h+var_B0]
0x1800310e6  lea     rcx, [rbp+0B0h+var_D0]
0x1800310ea  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800310ef  lea     rcx, [rbp+0B0h+var_B0]
0x1800310f3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800310f8  nop
0x1800310f9  test    rdi, rdi
0x1800310fc  jz      short loc_180031126
0x1800310fe  mov     rax, [rdi]
0x180031101  mov     rcx, rdi
0x180031104  mov     rax, [rax+10h]
0x180031108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003110d  mov     r8, rax
0x180031110  test    rax, rax
0x180031113  jz      short loc_180031126
0x180031115  mov     rcx, [rax]
0x180031118  mov     rax, [rcx]
0x18003111b  mov     edx, r14d
0x18003111e  mov     rcx, r8
0x180031121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031126  lea     rax, [rbp+0B0h+var_D0]
0x18003112a  cmp     [rbp+0B0h+var_B8], 0Fh
0x18003112f  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180031134  mov     r10, [rbp+0B0h+var_C0]
0x180031138  mov     edx, r13d
0x18003113b  test    r10, r10
0x18003113e  jz      short loc_180031172
0x180031140  mov     r8, r12
0x180031143  sub     r8, [rbp+0B0h+var_130]
0x180031147  movsx   r9, byte ptr [rax]
0x18003114b  cmp     r8, r9
0x18003114e  jbe     short loc_180031172
0x180031150  lea     r11, [r10+rax]
0x180031154  movsx   rcx, r9b
0x180031158  sub     r8, rcx
0x18003115b  add     edx, r14d
0x18003115e  lea     rcx, [rax+1]
0x180031162  cmp     rcx, r11
0x180031165  cmovnz  rax, rcx
0x180031169  movsx   r9, byte ptr [rax]
0x18003116d  cmp     r8, r9
0x180031170  ja      short loc_180031154
0x180031172  mov     [rsp+1B0h+var_158], edx
0x180031176  mov     eax, [rsp+1B0h+var_17C]
0x18003117a  add     eax, edx
0x18003117c  mov     [rsp+1B0h+var_17C], eax
0x180031180  cmp     [rsi+0Dh], r13b
0x180031184  jz      short loc_18003118C
0x180031186  cmp     [rsi+9], r13b
0x18003118a  jz      short loc_18003118F
0x18003118c  mov     r14b, r13b
0x18003118f  mov     [rsp+1B0h+var_180], r14b
0x180031194  mov     [rbp+0B0h+var_120], r12
0x180031198  mov     [rbp+0B0h+var_118], rsi
0x18003119c  lea     rcx, [rsp+1B0h+var_178]
0x1800311a1  mov     [rbp+0B0h+var_110], rcx
0x1800311a5  lea     rcx, [rsp+1B0h+var_170]
0x1800311aa  mov     [rbp+0B0h+var_108], rcx
0x1800311ae  lea     rcx, [rsp+1B0h+var_180]
0x1800311b3  mov     [rbp+0B0h+var_100], rcx
0x1800311b7  lea     rcx, [rsp+1B0h+var_17C]
0x1800311bc  mov     [rbp+0B0h+var_F8], rcx
0x1800311c0  lea     rcx, [rsp+1B0h+var_158]
0x1800311c5  mov     [rbp+0B0h+var_F0], rcx
0x1800311c9  lea     rcx, [rbp+0B0h+var_130]
0x1800311cd  mov     [rbp+0B0h+var_E8], rcx
0x1800311d1  lea     rcx, [rbp+0B0h+var_D0]
0x1800311d5  mov     [rbp+0B0h+var_E0], rcx
0x1800311d9  lea     rcx, [rbp+0B0h+arg_20]
0x1800311e0  mov     [rbp+0B0h+var_D8], rcx
0x1800311e4  lea     rcx, [rbp+0B0h+var_120]
0x1800311e8  test    r14b, r14b
0x1800311eb  jz      short loc_1800311FA
0x1800311ed  mov     r8, rbx
0x1800311f0  mov     rdx, r15
0x1800311f3  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x1800311f8  jmp     short loc_180031211
0x1800311fa  mov     [rsp+1B0h+var_188], rcx
0x1800311ff  mov     r9, rsi
0x180031202  mov     r8d, eax
0x180031205  mov     rdx, rbx
0x180031208  mov     rcx, r15
0x18003120b  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180031210  nop
0x180031211  lea     rcx, [rbp+0B0h+var_D0]
0x180031215  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003121a  mov     rax, r15
0x18003121d  mov     rcx, [rbp+0B0h+var_40]
0x180031221  xor     rcx, rsp; StackCookie
0x180031224  call    __security_check_cookie
0x180031229  mov     rbx, [rsp+1B0h+arg_8]
0x180031231  add     rsp, 180h
0x180031238  pop     r15
0x18003123a  pop     r14
0x18003123c  pop     r13
0x18003123e  pop     r12
0x180031240  pop     rdi
0x180031241  pop     rsi
0x180031242  pop     rbp
0x180031243  retn
```

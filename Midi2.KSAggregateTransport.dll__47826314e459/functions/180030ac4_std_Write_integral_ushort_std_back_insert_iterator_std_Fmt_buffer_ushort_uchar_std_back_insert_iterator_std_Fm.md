# std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x180030ac4`
- end: `0x180030e5a`
- name: `??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@EU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002c354`

## callees

- `0x180005020`
- `0x18002c1a4`
- `0x180030748`
- `0x180030ac4`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034ea8`
- `0x180042c80`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180030cc8`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180030cc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned char>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        __int128 *a4,
        __int64 a5)
{
  _BYTE *v5; // rsi
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
  unsigned __int8 v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v29; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v32; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  _QWORD v35[10]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v37; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v38; // [rsp+E8h] [rbp-18h]
  _BYTE v39[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v40[65]; // [rsp+110h] [rbp+10h] BYREF
  char v41[15]; // [rsp+151h] [rbp+51h] BYREF

  v5 = a4;
  v27 = a3;
  v8 = *((_BYTE *)a4 + 8);
  if ( v8 == 99 )
  {
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
LABEL_12:
      v10 = 16;
      goto LABEL_14;
    }
    if ( v8 != 98 )
    {
      if ( v8 == 111 )
      {
        v10 = 8;
        goto LABEL_14;
      }
      if ( v8 != 120 )
      {
        v10 = 10;
        goto LABEL_14;
      }
      goto LABEL_12;
    }
  }
  v10 = 2;
LABEL_14:
  v26 = v10;
  LOBYTE(a4) = a3;
  v11 = *(_BYTE **)std::to_chars(&v33, v40, v41, a4);
  v32 = v40;
  v12 = (_DWORD)v11 - (unsigned int)v40;
  v29 = v12;
  if ( v5[10] != 2 )
    v29 = ++v12;
  v13 = 1;
  if ( v5[8] == 88 )
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
      v12 = v29;
    }
  }
  v30 = 0u;
  if ( !v5[11] )
    goto LABEL_38;
  v15 = v5[8];
  switch ( v15 )
  {
    case 'B':
      v16 = "0B";
      goto LABEL_35;
    case 'X':
      v16 = "0X";
      goto LABEL_35;
    case 'b':
      v16 = "0b";
      goto LABEL_35;
    case 'o':
      if ( v27 )
      {
        v16 = "0";
        *((_QWORD *)&v30 + 1) = 1;
        v9 = 1;
LABEL_36:
        *(_QWORD *)&v30 = v16;
        goto LABEL_37;
      }
      break;
    case 'x':
      v16 = "0x";
LABEL_35:
      *((_QWORD *)&v30 + 1) = 2;
      goto LABEL_36;
  }
  v30 = 0u;
  v9 = 0;
LABEL_37:
  v12 += v9;
  v29 = v12;
LABEL_38:
  v31 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 15;
  LOBYTE(v36) = 0;
  if ( v5[12] )
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
    v31 = v21;
    v12 = v21 + v29;
    v29 += v21;
  }
  if ( !v5[13] || v5[9] )
    v13 = 0;
  v28 = v13;
  v35[0] = v11;
  v35[1] = v5;
  v35[2] = &v27;
  v35[3] = &v30;
  v35[4] = &v28;
  v35[5] = &v29;
  v35[6] = &v31;
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
      (_DWORD)v5,
      v26,
      (__int64)v35);
  std::string::~string(&v36);
  return a1;
}

```

## disassembly

```asm
0x180030ac4  mov     [rsp-8+arg_8], rbx
0x180030ac9  push    rbp
0x180030aca  push    rsi
0x180030acb  push    rdi
0x180030acc  push    r12
0x180030ace  push    r13
0x180030ad0  push    r14
0x180030ad2  push    r15
0x180030ad4  lea     rbp, [rsp-70h]
0x180030ad9  sub     rsp, 170h
0x180030ae0  mov     rax, cs:__security_cookie
0x180030ae7  xor     rax, rsp
0x180030aea  mov     [rbp+0A0h+var_40], rax
0x180030aee  mov     rsi, r9
0x180030af1  mov     rbx, rdx
0x180030af4  mov     r15, rcx
0x180030af7  mov     [rsp+1A0h+var_170], r8b
0x180030afc  xor     r13d, r13d
0x180030aff  mov     al, [r9+8]
0x180030b03  cmp     al, 63h ; 'c'
0x180030b05  jnz     short loc_180030B3E
0x180030b07  mov     [r9+0Bh], r13b
0x180030b0b  movaps  xmm0, xmmword ptr [r9]
0x180030b0f  movaps  [rsp+1A0h+var_140], xmm0
0x180030b14  mov     ecx, [r9+10h]
0x180030b18  mov     [rsp+1A0h+var_130], ecx
0x180030b1c  movzx   r8d, r8b
0x180030b20  mov     rcx, [rbp+0A0h+arg_20]
0x180030b27  mov     [rsp+1A0h+var_180], rcx
0x180030b2c  lea     r9, [rsp+1A0h+var_140]
0x180030b31  mov     rcx, r15
0x180030b34  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@GU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x180030b39  jmp     loc_180030E30
0x180030b3e  mov     edi, 2
0x180030b43  cmp     [r9+0Ah], r13b
0x180030b47  jnz     short loc_180030B4D
0x180030b49  mov     [r9+0Ah], dil
0x180030b4d  cmp     al, 42h ; 'B'
0x180030b4f  jz      short loc_180030B76
0x180030b51  cmp     al, 58h ; 'X'
0x180030b53  jz      short loc_180030B6F
0x180030b55  cmp     al, 62h ; 'b'
0x180030b57  jz      short loc_180030B76
0x180030b59  cmp     al, 6Fh ; 'o'
0x180030b5b  jz      short loc_180030B68
0x180030b5d  cmp     al, 78h ; 'x'
0x180030b5f  jz      short loc_180030B6F
0x180030b61  mov     eax, 0Ah
0x180030b66  jmp     short loc_180030B78
0x180030b68  mov     eax, 8
0x180030b6d  jmp     short loc_180030B78
0x180030b6f  mov     eax, 10h
0x180030b74  jmp     short loc_180030B78
0x180030b76  mov     eax, edi
0x180030b78  mov     dword ptr [rsp+1A0h+var_180], eax
0x180030b7c  mov     r9b, r8b
0x180030b7f  lea     r8, [rbp+0A0h+var_4F]
0x180030b83  lea     rdx, [rbp+0A0h+var_90]
0x180030b87  lea     rcx, [rsp+1A0h+var_140]
0x180030b8c  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0EH@Z; std::to_chars(char * const,char * const,uchar,int)
0x180030b91  mov     r12, [rax]
0x180030b94  lea     rcx, [rbp+0A0h+var_90]
0x180030b98  mov     [rsp+1A0h+var_148], rcx
0x180030b9d  mov     eax, r12d
0x180030ba0  sub     eax, ecx
0x180030ba2  mov     [rsp+1A0h+var_164], eax
0x180030ba6  cmp     [rsi+0Ah], dil
0x180030baa  jz      short loc_180030BB2
0x180030bac  inc     eax
0x180030bae  mov     [rsp+1A0h+var_164], eax
0x180030bb2  mov     r14d, 1
0x180030bb8  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180030bbc  jnz     short loc_180030BE5
0x180030bbe  lea     rcx, [rbp+0A0h+var_90]
0x180030bc2  lea     rdx, [rbp+0A0h+var_90]
0x180030bc6  cmp     rdx, r12
0x180030bc9  jz      short loc_180030BE5
0x180030bcb  mov     dl, [rcx]
0x180030bcd  lea     eax, [rdx-61h]
0x180030bd0  cmp     al, 19h
0x180030bd2  ja      short loc_180030BD9
0x180030bd4  sub     dl, 20h ; ' '
0x180030bd7  mov     [rcx], dl
0x180030bd9  add     rcx, r14
0x180030bdc  cmp     rcx, r12
0x180030bdf  jnz     short loc_180030BCB
0x180030be1  mov     eax, [rsp+1A0h+var_164]
0x180030be5  mov     qword ptr [rsp+1A0h+var_160], r13
0x180030bea  mov     qword ptr [rsp+1A0h+var_160+8], r13
0x180030bef  cmp     [rsi+0Bh], r13b
0x180030bf3  jz      loc_180030C79
0x180030bf9  mov     cl, [rsi+8]
0x180030bfc  cmp     cl, 42h ; 'B'
0x180030bff  jz      short loc_180030C57
0x180030c01  cmp     cl, 58h ; 'X'
0x180030c04  jz      short loc_180030C4E
0x180030c06  cmp     cl, 62h ; 'b'
0x180030c09  jz      short loc_180030C45
0x180030c0b  cmp     cl, 6Fh ; 'o'
0x180030c0e  jz      short loc_180030C1E
0x180030c10  cmp     cl, 78h ; 'x'
0x180030c13  jnz     short loc_180030C36
0x180030c15  lea     rcx, a0x; "0x"
0x180030c1c  jmp     short loc_180030C5E
0x180030c1e  cmp     [rsp+1A0h+var_170], r13b
0x180030c23  jz      short loc_180030C36
0x180030c25  lea     rcx, a0; "0"
0x180030c2c  mov     qword ptr [rsp+1A0h+var_160+8], r14
0x180030c31  mov     edi, r14d
0x180030c34  jmp     short loc_180030C63
0x180030c36  mov     qword ptr [rsp+1A0h+var_160], r13
0x180030c3b  mov     qword ptr [rsp+1A0h+var_160+8], r13
0x180030c40  mov     edi, r13d
0x180030c43  jmp     short loc_180030C68
0x180030c45  lea     rcx, a0b; "0b"
0x180030c4c  jmp     short loc_180030C5E
0x180030c4e  lea     rcx, a0x_0; "0X"
0x180030c55  jmp     short loc_180030C5E
0x180030c57  lea     rcx, a0b_0; "0B"
0x180030c5e  mov     qword ptr [rsp+1A0h+var_160+8], rdi
0x180030c63  mov     qword ptr [rsp+1A0h+var_160], rcx
0x180030c68  movaps  xmm0, [rsp+1A0h+var_160]
0x180030c6d  movdqa  [rsp+1A0h+var_160], xmm0
0x180030c73  add     eax, edi
0x180030c75  mov     [rsp+1A0h+var_164], eax
0x180030c79  mov     [rsp+1A0h+var_150], r13d
0x180030c7e  xorps   xmm0, xmm0
0x180030c81  movups  [rbp+0A0h+var_D0], xmm0
0x180030c85  mov     [rbp+0A0h+var_C0], r13
0x180030c89  mov     [rbp+0A0h+var_B8], 0Fh
0x180030c91  mov     byte ptr [rbp+0A0h+var_D0], r13b
0x180030c95  cmp     [rsi+0Ch], r13b
0x180030c99  jz      loc_180030D95
0x180030c9f  mov     rax, [rbp+0A0h+arg_20]
0x180030ca6  test    rax, rax
0x180030ca9  jz      short loc_180030CC5
0x180030cab  mov     rdi, [rax+8]
0x180030caf  mov     qword ptr [rsp+1A0h+var_140+8], rdi
0x180030cb4  mov     rax, [rdi]
0x180030cb7  mov     rcx, rdi
0x180030cba  mov     rax, [rax+8]
0x180030cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cc3  jmp     short loc_180030CD6
0x180030cc5  mov     cl, r14b
0x180030cc8  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180030cce  mov     rdi, rax
0x180030cd1  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x180030cd6  lea     rcx, [rsp+1A0h+var_140]
0x180030cdb  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180030ce0  mov     r8, rax
0x180030ce3  mov     rcx, [rax]
0x180030ce6  mov     rax, [rcx+28h]
0x180030cea  lea     rdx, [rbp+0A0h+var_B0]
0x180030cee  mov     rcx, r8
0x180030cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cf6  lea     rdx, [rbp+0A0h+var_B0]
0x180030cfa  lea     rcx, [rbp+0A0h+var_D0]
0x180030cfe  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180030d03  lea     rcx, [rbp+0A0h+var_B0]
0x180030d07  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180030d0c  nop
0x180030d0d  test    rdi, rdi
0x180030d10  jz      short loc_180030D3A
0x180030d12  mov     rax, [rdi]
0x180030d15  mov     rcx, rdi
0x180030d18  mov     rax, [rax+10h]
0x180030d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d21  mov     r8, rax
0x180030d24  test    rax, rax
0x180030d27  jz      short loc_180030D3A
0x180030d29  mov     rcx, [rax]
0x180030d2c  mov     rax, [rcx]
0x180030d2f  mov     edx, r14d
0x180030d32  mov     rcx, r8
0x180030d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d3a  lea     rax, [rbp+0A0h+var_D0]
0x180030d3e  cmp     [rbp+0A0h+var_B8], 0Fh
0x180030d43  cmova   rax, qword ptr [rbp+0A0h+var_D0]
0x180030d48  mov     r10, [rbp+0A0h+var_C0]
0x180030d4c  mov     edx, r13d
0x180030d4f  test    r10, r10
0x180030d52  jz      short loc_180030D87
0x180030d54  mov     r8, r12
0x180030d57  sub     r8, [rsp+1A0h+var_148]
0x180030d5c  movsx   r9, byte ptr [rax]
0x180030d60  cmp     r8, r9
0x180030d63  jbe     short loc_180030D87
0x180030d65  lea     r11, [r10+rax]
0x180030d69  movsx   rcx, r9b
0x180030d6d  sub     r8, rcx
0x180030d70  add     edx, r14d
0x180030d73  lea     rcx, [rax+1]
0x180030d77  cmp     rcx, r11
0x180030d7a  cmovnz  rax, rcx
0x180030d7e  movsx   r9, byte ptr [rax]
0x180030d82  cmp     r8, r9
0x180030d85  ja      short loc_180030D69
0x180030d87  mov     [rsp+1A0h+var_150], edx
0x180030d8b  mov     eax, [rsp+1A0h+var_164]
0x180030d8f  add     eax, edx
0x180030d91  mov     [rsp+1A0h+var_164], eax
0x180030d95  cmp     [rsi+0Dh], r13b
0x180030d99  jz      short loc_180030DA1
0x180030d9b  cmp     [rsi+9], r13b
0x180030d9f  jz      short loc_180030DA4
0x180030da1  mov     r14b, r13b
0x180030da4  mov     [rsp+1A0h+var_168], r14b
0x180030da9  mov     [rbp+0A0h+var_120], r12
0x180030dad  mov     [rbp+0A0h+var_118], rsi
0x180030db1  lea     rcx, [rsp+1A0h+var_170]
0x180030db6  mov     [rbp+0A0h+var_110], rcx
0x180030dba  lea     rcx, [rsp+1A0h+var_160]
0x180030dbf  mov     [rbp+0A0h+var_108], rcx
0x180030dc3  lea     rcx, [rsp+1A0h+var_168]
0x180030dc8  mov     [rbp+0A0h+var_100], rcx
0x180030dcc  lea     rcx, [rsp+1A0h+var_164]
0x180030dd1  mov     [rbp+0A0h+var_F8], rcx
0x180030dd5  lea     rcx, [rsp+1A0h+var_150]
0x180030dda  mov     [rbp+0A0h+var_F0], rcx
0x180030dde  lea     rcx, [rsp+1A0h+var_148]
0x180030de3  mov     [rbp+0A0h+var_E8], rcx
0x180030de7  lea     rcx, [rbp+0A0h+var_D0]
0x180030deb  mov     [rbp+0A0h+var_E0], rcx
0x180030def  lea     rcx, [rbp+0A0h+arg_20]
0x180030df6  mov     [rbp+0A0h+var_D8], rcx
0x180030dfa  lea     rcx, [rbp+0A0h+var_120]
0x180030dfe  test    r14b, r14b
0x180030e01  jz      short loc_180030E10
0x180030e03  mov     r8, rbx
0x180030e06  mov     rdx, r15
0x180030e09  call    ??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180030e0e  jmp     short loc_180030E27
0x180030e10  mov     [rsp+1A0h+var_178], rcx
0x180030e15  mov     r9, rsi
0x180030e18  mov     r8d, eax
0x180030e1b  mov     rdx, rbx
0x180030e1e  mov     rcx, r15
0x180030e21  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@U?$_Basic_format_specs@G@2@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@HAEBU?$_Basic_format_specs@G@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Basic_format_specs<ushort>,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort> const &,std::_Fmt_align,`std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uint,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180030e26  nop
0x180030e27  lea     rcx, [rbp+0A0h+var_D0]
0x180030e2b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180030e30  mov     rax, r15
0x180030e33  mov     rcx, [rbp+0A0h+var_40]
0x180030e37  xor     rcx, rsp; StackCookie
0x180030e3a  call    __security_check_cookie
0x180030e3f  mov     rbx, [rsp+1A0h+arg_8]
0x180030e47  add     rsp, 170h
0x180030e4e  pop     r15
0x180030e50  pop     r14
0x180030e52  pop     r13
0x180030e54  pop     r12
0x180030e56  pop     rdi
0x180030e57  pop     rsi
0x180030e58  pop     rbp
0x180030e59  retn
```

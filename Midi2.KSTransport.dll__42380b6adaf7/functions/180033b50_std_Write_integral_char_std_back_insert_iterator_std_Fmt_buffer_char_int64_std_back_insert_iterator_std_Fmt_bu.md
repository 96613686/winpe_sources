# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180033b50`
- end: `0x180033f08`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_JU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180032164`

## callees

- `0x180004410`
- `0x18002ef5c`
- `0x180030ad8`
- `0x180032d64`
- `0x180033b50`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x180037154`
- `0x18003a404`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180033d6b`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180033d6b`

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
0x180033b50  mov     [rsp-8+arg_8], rbx
0x180033b55  push    rbp
0x180033b56  push    rsi
0x180033b57  push    rdi
0x180033b58  push    r12
0x180033b5a  push    r13
0x180033b5c  push    r14
0x180033b5e  push    r15
0x180033b60  lea     rbp, [rsp-80h]
0x180033b65  sub     rsp, 180h
0x180033b6c  mov     rax, cs:__security_cookie
0x180033b73  xor     rax, rsp
0x180033b76  mov     [rbp+0B0h+var_40], rax
0x180033b7a  mov     rsi, r9
0x180033b7d  mov     rbx, rdx
0x180033b80  mov     r15, rcx
0x180033b83  mov     [rsp+1B0h+var_148], r8
0x180033b88  xor     r13d, r13d
0x180033b8b  mov     al, [r9+8]
0x180033b8f  cmp     al, 63h ; 'c'
0x180033b91  jnz     short loc_180033BD9
0x180033b93  lea     rax, [r8+80h]
0x180033b9a  cmp     rax, 0FFh
0x180033ba0  ja      loc_180033EFB
0x180033ba6  mov     [r9+0Bh], r13b
0x180033baa  movaps  xmm0, xmmword ptr [r9]
0x180033bae  movaps  [rsp+1B0h+var_170], xmm0
0x180033bb3  mov     ecx, [r9+10h]
0x180033bb7  mov     [rsp+1B0h+var_160], ecx
0x180033bbb  mov     rcx, [rbp+0B0h+arg_20]
0x180033bc2  mov     [rsp+1B0h+var_190], rcx
0x180033bc7  lea     r9, [rsp+1B0h+var_170]
0x180033bcc  mov     rcx, r15
0x180033bcf  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180033bd4  jmp     loc_180033ED1
0x180033bd9  mov     edi, 2
0x180033bde  cmp     [r9+0Ah], r13b
0x180033be2  jnz     short loc_180033BE8
0x180033be4  mov     [r9+0Ah], dil
0x180033be8  cmp     al, 42h ; 'B'
0x180033bea  jz      short loc_180033C11
0x180033bec  cmp     al, 58h ; 'X'
0x180033bee  jz      short loc_180033C0A
0x180033bf0  cmp     al, 62h ; 'b'
0x180033bf2  jz      short loc_180033C11
0x180033bf4  cmp     al, 6Fh ; 'o'
0x180033bf6  jz      short loc_180033C03
0x180033bf8  cmp     al, 78h ; 'x'
0x180033bfa  jz      short loc_180033C0A
0x180033bfc  mov     eax, 0Ah
0x180033c01  jmp     short loc_180033C13
0x180033c03  mov     eax, 8
0x180033c08  jmp     short loc_180033C13
0x180033c0a  mov     eax, 10h
0x180033c0f  jmp     short loc_180033C13
0x180033c11  mov     eax, edi
0x180033c13  mov     dword ptr [rsp+1B0h+var_190], eax
0x180033c17  mov     r9, r8
0x180033c1a  lea     r8, [rbp+0B0h+var_4F]
0x180033c1e  lea     rdx, [rbp+0B0h+var_90]
0x180033c22  lea     rcx, [rsp+1B0h+var_170]
0x180033c27  call    ??$_Integer_to_chars@_J@std@@YA?AUto_chars_result@0@PEADQEAD_JH@Z; std::_Integer_to_chars<__int64>(char *,char * const,__int64,int)
0x180033c2c  lea     rcx, [rbp+0B0h+var_90]
0x180033c30  mov     [rsp+1B0h+var_140], rcx
0x180033c35  mov     r12, qword ptr [rsp+1B0h+var_170]
0x180033c3a  mov     eax, r12d
0x180033c3d  sub     eax, ecx
0x180033c3f  mov     [rsp+1B0h+var_17C], eax
0x180033c43  mov     rdx, [rsp+1B0h+var_148]
0x180033c48  test    rdx, rdx
0x180033c4b  js      short loc_180033C5B
0x180033c4d  cmp     [rsi+0Ah], dil
0x180033c51  jz      short loc_180033C64
0x180033c53  inc     eax
0x180033c55  mov     [rsp+1B0h+var_17C], eax
0x180033c59  jmp     short loc_180033C64
0x180033c5b  lea     rcx, [rbp+0B0h+var_8F]
0x180033c5f  mov     [rsp+1B0h+var_140], rcx
0x180033c64  mov     r14d, 1
0x180033c6a  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180033c6e  jnz     short loc_180033C94
0x180033c70  cmp     rcx, r12
0x180033c73  jz      short loc_180033C94
0x180033c75  mov     dl, [rcx]
0x180033c77  lea     eax, [rdx-61h]
0x180033c7a  cmp     al, 19h
0x180033c7c  ja      short loc_180033C83
0x180033c7e  sub     dl, 20h ; ' '
0x180033c81  mov     [rcx], dl
0x180033c83  add     rcx, r14
0x180033c86  cmp     rcx, r12
0x180033c89  jnz     short loc_180033C75
0x180033c8b  mov     eax, [rsp+1B0h+var_17C]
0x180033c8f  mov     rdx, [rsp+1B0h+var_148]
0x180033c94  mov     qword ptr [rbp+0B0h+var_130], r13
0x180033c98  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180033c9c  cmp     [rsi+0Bh], r13b
0x180033ca0  jz      short loc_180033D1F
0x180033ca2  mov     cl, [rsi+8]
0x180033ca5  cmp     cl, 42h ; 'B'
0x180033ca8  jz      short loc_180033CFE
0x180033caa  cmp     cl, 58h ; 'X'
0x180033cad  jz      short loc_180033CF5
0x180033caf  cmp     cl, 62h ; 'b'
0x180033cb2  jz      short loc_180033CEC
0x180033cb4  cmp     cl, 6Fh ; 'o'
0x180033cb7  jz      short loc_180033CC7
0x180033cb9  cmp     cl, 78h ; 'x'
0x180033cbc  jnz     short loc_180033CDD
0x180033cbe  lea     rcx, a0x; "0x"
0x180033cc5  jmp     short loc_180033D05
0x180033cc7  test    rdx, rdx
0x180033cca  jz      short loc_180033CDD
0x180033ccc  lea     rcx, a0; "0"
0x180033cd3  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180033cd8  mov     edi, r14d
0x180033cdb  jmp     short loc_180033D0A
0x180033cdd  mov     qword ptr [rsp+1B0h+var_170], r13
0x180033ce2  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180033ce7  mov     edi, r13d
0x180033cea  jmp     short loc_180033D0F
0x180033cec  lea     rcx, a0b; "0b"
0x180033cf3  jmp     short loc_180033D05
0x180033cf5  lea     rcx, a0x_0; "0X"
0x180033cfc  jmp     short loc_180033D05
0x180033cfe  lea     rcx, a0b_0; "0B"
0x180033d05  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x180033d0a  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180033d0f  movaps  xmm0, [rsp+1B0h+var_170]
0x180033d14  movdqa  [rbp+0B0h+var_130], xmm0
0x180033d19  add     eax, edi
0x180033d1b  mov     [rsp+1B0h+var_17C], eax
0x180033d1f  mov     [rsp+1B0h+var_150], r13d
0x180033d24  xorps   xmm0, xmm0
0x180033d27  movups  [rbp+0B0h+var_D0], xmm0
0x180033d2b  mov     [rbp+0B0h+var_C0], r13
0x180033d2f  mov     [rbp+0B0h+var_B8], 0Fh
0x180033d37  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180033d3b  cmp     [rsi+0Ch], r13b
0x180033d3f  jz      loc_180033E37
0x180033d45  mov     rax, [rbp+0B0h+arg_20]
0x180033d4c  test    rax, rax
0x180033d4f  jz      short loc_180033D68
0x180033d51  mov     rcx, [rax+8]
0x180033d55  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x180033d5a  mov     rax, [rcx]
0x180033d5d  mov     rax, [rax+8]
0x180033d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d66  jmp     short loc_180033D76
0x180033d68  mov     cl, r14b
0x180033d6b  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180033d71  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180033d76  lea     rcx, [rsp+1B0h+var_170]
0x180033d7b  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180033d80  mov     r8, rax
0x180033d83  mov     rcx, [rax]
0x180033d86  mov     rax, [rcx+28h]
0x180033d8a  lea     rdx, [rbp+0B0h+var_B0]
0x180033d8e  mov     rcx, r8
0x180033d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d96  lea     rdx, [rbp+0B0h+var_B0]
0x180033d9a  lea     rcx, [rbp+0B0h+var_D0]
0x180033d9e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180033da3  lea     rcx, [rbp+0B0h+var_B0]
0x180033da7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033dac  nop
0x180033dad  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180033db2  test    rcx, rcx
0x180033db5  jz      short loc_180033DDC
0x180033db7  mov     rax, [rcx]
0x180033dba  mov     rax, [rax+10h]
0x180033dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dc3  mov     r8, rax
0x180033dc6  test    rax, rax
0x180033dc9  jz      short loc_180033DDC
0x180033dcb  mov     rcx, [rax]
0x180033dce  mov     rax, [rcx]
0x180033dd1  mov     edx, r14d
0x180033dd4  mov     rcx, r8
0x180033dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ddc  lea     rax, [rbp+0B0h+var_D0]
0x180033de0  cmp     [rbp+0B0h+var_B8], 0Fh
0x180033de5  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180033dea  mov     r10, [rbp+0B0h+var_C0]
0x180033dee  mov     edx, r13d
0x180033df1  test    r10, r10
0x180033df4  jz      short loc_180033E29
0x180033df6  mov     r8, r12
0x180033df9  sub     r8, [rsp+1B0h+var_140]
0x180033dfe  movsx   r9, byte ptr [rax]
0x180033e02  cmp     r8, r9
0x180033e05  jbe     short loc_180033E29
0x180033e07  lea     r11, [r10+rax]
0x180033e0b  movsx   rcx, r9b
0x180033e0f  sub     r8, rcx
0x180033e12  add     edx, r14d
0x180033e15  lea     rcx, [rax+1]
0x180033e19  cmp     rcx, r11
0x180033e1c  cmovnz  rax, rcx
0x180033e20  movsx   r9, byte ptr [rax]
0x180033e24  cmp     r8, r9
0x180033e27  ja      short loc_180033E0B
0x180033e29  mov     [rsp+1B0h+var_150], edx
0x180033e2d  mov     eax, [rsp+1B0h+var_17C]
0x180033e31  add     eax, edx
0x180033e33  mov     [rsp+1B0h+var_17C], eax
0x180033e37  cmp     [rsi+0Dh], r13b
0x180033e3b  jz      short loc_180033E43
0x180033e3d  cmp     [rsi+9], r13b
0x180033e41  jz      short loc_180033E46
0x180033e43  mov     r14b, r13b
0x180033e46  mov     [rsp+1B0h+var_180], r14b
0x180033e4b  mov     [rbp+0B0h+var_120], r12
0x180033e4f  mov     [rbp+0B0h+var_118], rsi
0x180033e53  lea     rcx, [rsp+1B0h+var_148]
0x180033e58  mov     [rbp+0B0h+var_110], rcx
0x180033e5c  lea     rcx, [rbp+0B0h+var_130]
0x180033e60  mov     [rbp+0B0h+var_108], rcx
0x180033e64  lea     rcx, [rsp+1B0h+var_180]
0x180033e69  mov     [rbp+0B0h+var_100], rcx
0x180033e6d  lea     rcx, [rsp+1B0h+var_17C]
0x180033e72  mov     [rbp+0B0h+var_F8], rcx
0x180033e76  lea     rcx, [rsp+1B0h+var_150]
0x180033e7b  mov     [rbp+0B0h+var_F0], rcx
0x180033e7f  lea     rcx, [rsp+1B0h+var_140]
0x180033e84  mov     [rbp+0B0h+var_E8], rcx
0x180033e88  lea     rcx, [rbp+0B0h+var_D0]
0x180033e8c  mov     [rbp+0B0h+var_E0], rcx
0x180033e90  lea     rcx, [rbp+0B0h+arg_20]
0x180033e97  mov     [rbp+0B0h+var_D8], rcx
0x180033e9b  lea     rcx, [rbp+0B0h+var_120]
0x180033e9f  test    r14b, r14b
0x180033ea2  jz      short loc_180033EB1
0x180033ea4  mov     r8, rbx
0x180033ea7  mov     rdx, r15
0x180033eaa  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180033eaf  jmp     short loc_180033EC8
0x180033eb1  mov     [rsp+1B0h+var_188], rcx
0x180033eb6  mov     r9, rsi
0x180033eb9  mov     r8d, eax
0x180033ebc  mov     rdx, rbx
0x180033ebf  mov     rcx, r15
0x180033ec2  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@2@YA?AV12@V12@_JU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@0@YA?AV10@0_JU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180033ec7  nop
0x180033ec8  lea     rcx, [rbp+0B0h+var_D0]
0x180033ecc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033ed1  mov     rax, r15
0x180033ed4  mov     rcx, [rbp+0B0h+var_40]
0x180033ed8  xor     rcx, rsp; StackCookie
0x180033edb  call    __security_check_cookie
0x180033ee0  mov     rbx, [rsp+1B0h+arg_8]
0x180033ee8  add     rsp, 180h
0x180033eef  pop     r15
0x180033ef1  pop     r14
0x180033ef3  pop     r13
0x180033ef5  pop     r12
0x180033ef7  pop     rdi
0x180033ef8  pop     rsi
0x180033ef9  pop     rbp
0x180033efa  retn
0x180033efb  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180033f02  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

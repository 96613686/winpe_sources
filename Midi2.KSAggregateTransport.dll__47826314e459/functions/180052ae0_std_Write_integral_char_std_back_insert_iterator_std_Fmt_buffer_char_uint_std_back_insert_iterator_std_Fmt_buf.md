# std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180052ae0`
- end: `0x180052e7d`
- name: `??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@IU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180051498`

## callees

- `0x180005020`
- `0x1800342a8`
- `0x180034450`
- `0x180040fac`
- `0x18004321c`
- `0x18004e8bc`
- `0x180051f68`
- `0x180052ae0`
- `0x180053d44`
- `0x180054c5c`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180052ce0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180052ce0`

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
0x180052ae0  mov     [rsp-8+arg_8], rbx
0x180052ae5  push    rbp
0x180052ae6  push    rsi
0x180052ae7  push    rdi
0x180052ae8  push    r12
0x180052aea  push    r13
0x180052aec  push    r14
0x180052aee  push    r15
0x180052af0  lea     rbp, [rsp-80h]
0x180052af5  sub     rsp, 180h
0x180052afc  mov     rax, cs:__security_cookie
0x180052b03  xor     rax, rsp
0x180052b06  mov     [rbp+0B0h+var_40], rax
0x180052b0a  mov     rsi, r9
0x180052b0d  mov     rbx, rdx
0x180052b10  mov     r15, rcx
0x180052b13  mov     [rsp+1B0h+var_148], r8d
0x180052b18  xor     r13d, r13d
0x180052b1b  mov     al, [r9+8]
0x180052b1f  cmp     al, 63h ; 'c'
0x180052b21  jnz     short loc_180052B60
0x180052b23  cmp     r8d, 7Fh
0x180052b27  ja      loc_180052E70
0x180052b2d  mov     [r9+0Bh], r13b
0x180052b31  movaps  xmm0, xmmword ptr [r9]
0x180052b35  movaps  [rsp+1B0h+var_170], xmm0
0x180052b3a  mov     ecx, [r9+10h]
0x180052b3e  mov     [rsp+1B0h+var_160], ecx
0x180052b42  mov     rcx, [rbp+0B0h+arg_20]
0x180052b49  mov     [rsp+1B0h+var_190], rcx
0x180052b4e  lea     r9, [rsp+1B0h+var_170]
0x180052b53  mov     rcx, r15
0x180052b56  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@DU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,char,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x180052b5b  jmp     loc_180052E46
0x180052b60  mov     edi, 2
0x180052b65  cmp     [r9+0Ah], r13b
0x180052b69  jnz     short loc_180052B6F
0x180052b6b  mov     [r9+0Ah], dil
0x180052b6f  cmp     al, 42h ; 'B'
0x180052b71  jz      short loc_180052B98
0x180052b73  cmp     al, 58h ; 'X'
0x180052b75  jz      short loc_180052B91
0x180052b77  cmp     al, 62h ; 'b'
0x180052b79  jz      short loc_180052B98
0x180052b7b  cmp     al, 6Fh ; 'o'
0x180052b7d  jz      short loc_180052B8A
0x180052b7f  cmp     al, 78h ; 'x'
0x180052b81  jz      short loc_180052B91
0x180052b83  mov     eax, 0Ah
0x180052b88  jmp     short loc_180052B9A
0x180052b8a  mov     eax, 8
0x180052b8f  jmp     short loc_180052B9A
0x180052b91  mov     eax, 10h
0x180052b96  jmp     short loc_180052B9A
0x180052b98  mov     eax, edi
0x180052b9a  mov     dword ptr [rsp+1B0h+var_190], eax
0x180052b9e  mov     r9d, r8d
0x180052ba1  lea     r8, [rbp+0B0h+var_4F]
0x180052ba5  lea     rdx, [rbp+0B0h+var_90]
0x180052ba9  lea     rcx, [rsp+1B0h+var_170]
0x180052bae  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0IH@Z; std::to_chars(char * const,char * const,uint,int)
0x180052bb3  mov     r12, [rax]
0x180052bb6  lea     rcx, [rbp+0B0h+var_90]
0x180052bba  mov     [rsp+1B0h+var_140], rcx
0x180052bbf  mov     eax, r12d
0x180052bc2  sub     eax, ecx
0x180052bc4  mov     [rsp+1B0h+var_17C], eax
0x180052bc8  cmp     [rsi+0Ah], dil
0x180052bcc  jz      short loc_180052BD4
0x180052bce  inc     eax
0x180052bd0  mov     [rsp+1B0h+var_17C], eax
0x180052bd4  mov     r14d, 1
0x180052bda  cmp     byte ptr [rsi+8], 58h ; 'X'
0x180052bde  jnz     short loc_180052C07
0x180052be0  lea     rcx, [rbp+0B0h+var_90]
0x180052be4  lea     rdx, [rbp+0B0h+var_90]
0x180052be8  cmp     rdx, r12
0x180052beb  jz      short loc_180052C07
0x180052bed  mov     dl, [rcx]
0x180052bef  lea     eax, [rdx-61h]
0x180052bf2  cmp     al, 19h
0x180052bf4  ja      short loc_180052BFB
0x180052bf6  sub     dl, 20h ; ' '
0x180052bf9  mov     [rcx], dl
0x180052bfb  add     rcx, r14
0x180052bfe  cmp     rcx, r12
0x180052c01  jnz     short loc_180052BED
0x180052c03  mov     eax, [rsp+1B0h+var_17C]
0x180052c07  mov     qword ptr [rbp+0B0h+var_130], r13
0x180052c0b  mov     qword ptr [rbp+0B0h+var_130+8], r13
0x180052c0f  cmp     [rsi+0Bh], r13b
0x180052c13  jz      short loc_180052C94
0x180052c15  mov     cl, [rsi+8]
0x180052c18  cmp     cl, 42h ; 'B'
0x180052c1b  jz      short loc_180052C73
0x180052c1d  cmp     cl, 58h ; 'X'
0x180052c20  jz      short loc_180052C6A
0x180052c22  cmp     cl, 62h ; 'b'
0x180052c25  jz      short loc_180052C61
0x180052c27  cmp     cl, 6Fh ; 'o'
0x180052c2a  jz      short loc_180052C3A
0x180052c2c  cmp     cl, 78h ; 'x'
0x180052c2f  jnz     short loc_180052C52
0x180052c31  lea     rcx, a0x; "0x"
0x180052c38  jmp     short loc_180052C7A
0x180052c3a  cmp     [rsp+1B0h+var_148], r13d
0x180052c3f  jz      short loc_180052C52
0x180052c41  lea     rcx, a0; "0"
0x180052c48  mov     qword ptr [rsp+1B0h+var_170+8], r14
0x180052c4d  mov     edi, r14d
0x180052c50  jmp     short loc_180052C7F
0x180052c52  mov     qword ptr [rsp+1B0h+var_170], r13
0x180052c57  mov     qword ptr [rsp+1B0h+var_170+8], r13
0x180052c5c  mov     edi, r13d
0x180052c5f  jmp     short loc_180052C84
0x180052c61  lea     rcx, a0b; "0b"
0x180052c68  jmp     short loc_180052C7A
0x180052c6a  lea     rcx, a0x_0; "0X"
0x180052c71  jmp     short loc_180052C7A
0x180052c73  lea     rcx, a0b_0; "0B"
0x180052c7a  mov     qword ptr [rsp+1B0h+var_170+8], rdi
0x180052c7f  mov     qword ptr [rsp+1B0h+var_170], rcx
0x180052c84  movaps  xmm0, [rsp+1B0h+var_170]
0x180052c89  movdqa  [rbp+0B0h+var_130], xmm0
0x180052c8e  add     eax, edi
0x180052c90  mov     [rsp+1B0h+var_17C], eax
0x180052c94  mov     [rsp+1B0h+var_150], r13d
0x180052c99  xorps   xmm0, xmm0
0x180052c9c  movups  [rbp+0B0h+var_D0], xmm0
0x180052ca0  mov     [rbp+0B0h+var_C0], r13
0x180052ca4  mov     [rbp+0B0h+var_B8], 0Fh
0x180052cac  mov     byte ptr [rbp+0B0h+var_D0], r13b
0x180052cb0  cmp     [rsi+0Ch], r13b
0x180052cb4  jz      loc_180052DAC
0x180052cba  mov     rax, [rbp+0B0h+arg_20]
0x180052cc1  test    rax, rax
0x180052cc4  jz      short loc_180052CDD
0x180052cc6  mov     rcx, [rax+8]
0x180052cca  mov     qword ptr [rsp+1B0h+var_170+8], rcx
0x180052ccf  mov     rax, [rcx]
0x180052cd2  mov     rax, [rax+8]
0x180052cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cdb  jmp     short loc_180052CEB
0x180052cdd  mov     cl, r14b
0x180052ce0  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180052ce6  mov     qword ptr [rsp+1B0h+var_170+8], rax
0x180052ceb  lea     rcx, [rsp+1B0h+var_170]
0x180052cf0  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180052cf5  mov     r8, rax
0x180052cf8  mov     rcx, [rax]
0x180052cfb  mov     rax, [rcx+28h]
0x180052cff  lea     rdx, [rbp+0B0h+var_B0]
0x180052d03  mov     rcx, r8
0x180052d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d0b  lea     rdx, [rbp+0B0h+var_B0]
0x180052d0f  lea     rcx, [rbp+0B0h+var_D0]
0x180052d13  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180052d18  lea     rcx, [rbp+0B0h+var_B0]
0x180052d1c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180052d21  nop
0x180052d22  mov     rcx, qword ptr [rsp+1B0h+var_170+8]
0x180052d27  test    rcx, rcx
0x180052d2a  jz      short loc_180052D51
0x180052d2c  mov     rax, [rcx]
0x180052d2f  mov     rax, [rax+10h]
0x180052d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d38  mov     r8, rax
0x180052d3b  test    rax, rax
0x180052d3e  jz      short loc_180052D51
0x180052d40  mov     rcx, [rax]
0x180052d43  mov     rax, [rcx]
0x180052d46  mov     edx, r14d
0x180052d49  mov     rcx, r8
0x180052d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d51  lea     rax, [rbp+0B0h+var_D0]
0x180052d55  cmp     [rbp+0B0h+var_B8], 0Fh
0x180052d5a  cmova   rax, qword ptr [rbp+0B0h+var_D0]
0x180052d5f  mov     r10, [rbp+0B0h+var_C0]
0x180052d63  mov     edx, r13d
0x180052d66  test    r10, r10
0x180052d69  jz      short loc_180052D9E
0x180052d6b  mov     r8, r12
0x180052d6e  sub     r8, [rsp+1B0h+var_140]
0x180052d73  movsx   r9, byte ptr [rax]
0x180052d77  cmp     r8, r9
0x180052d7a  jbe     short loc_180052D9E
0x180052d7c  lea     r11, [r10+rax]
0x180052d80  movsx   rcx, r9b
0x180052d84  sub     r8, rcx
0x180052d87  add     edx, r14d
0x180052d8a  lea     rcx, [rax+1]
0x180052d8e  cmp     rcx, r11
0x180052d91  cmovnz  rax, rcx
0x180052d95  movsx   r9, byte ptr [rax]
0x180052d99  cmp     r8, r9
0x180052d9c  ja      short loc_180052D80
0x180052d9e  mov     [rsp+1B0h+var_150], edx
0x180052da2  mov     eax, [rsp+1B0h+var_17C]
0x180052da6  add     eax, edx
0x180052da8  mov     [rsp+1B0h+var_17C], eax
0x180052dac  cmp     [rsi+0Dh], r13b
0x180052db0  jz      short loc_180052DB8
0x180052db2  cmp     [rsi+9], r13b
0x180052db6  jz      short loc_180052DBB
0x180052db8  mov     r14b, r13b
0x180052dbb  mov     [rsp+1B0h+var_180], r14b
0x180052dc0  mov     [rbp+0B0h+var_120], r12
0x180052dc4  mov     [rbp+0B0h+var_118], rsi
0x180052dc8  lea     rcx, [rsp+1B0h+var_148]
0x180052dcd  mov     [rbp+0B0h+var_110], rcx
0x180052dd1  lea     rcx, [rbp+0B0h+var_130]
0x180052dd5  mov     [rbp+0B0h+var_108], rcx
0x180052dd9  lea     rcx, [rsp+1B0h+var_180]
0x180052dde  mov     [rbp+0B0h+var_100], rcx
0x180052de2  lea     rcx, [rsp+1B0h+var_17C]
0x180052de7  mov     [rbp+0B0h+var_F8], rcx
0x180052deb  lea     rcx, [rsp+1B0h+var_150]
0x180052df0  mov     [rbp+0B0h+var_F0], rcx
0x180052df4  lea     rcx, [rsp+1B0h+var_140]
0x180052df9  mov     [rbp+0B0h+var_E8], rcx
0x180052dfd  lea     rcx, [rbp+0B0h+var_D0]
0x180052e01  mov     [rbp+0B0h+var_E0], rcx
0x180052e05  lea     rcx, [rbp+0B0h+arg_20]
0x180052e0c  mov     [rbp+0B0h+var_D8], rcx
0x180052e10  lea     rcx, [rbp+0B0h+var_120]
0x180052e14  test    r14b, r14b
0x180052e17  jz      short loc_180052E26
0x180052e19  mov     r8, rbx
0x180052e1c  mov     rdx, r15
0x180052e1f  call    ??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z; `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180052e24  jmp     short loc_180052E3D
0x180052e26  mov     [rsp+1B0h+var_188], rcx
0x180052e2b  mov     r9, rsi
0x180052e2e  mov     r8d, eax
0x180052e31  mov     rdx, rbx
0x180052e34  mov     rcx, r15
0x180052e37  call    ??$_Write_aligned@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@U?$_Basic_format_specs@D@2@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@2@YA?AV12@V12@IU32@V_Lazy_locale@2@@Z@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@HAEBU?$_Basic_format_specs@D@0@W4_Fmt_align@0@AEAV_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@I@0@YA?AV10@0IU20@V_Lazy_locale@0@@Z@@Z; std::_Write_aligned<std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Basic_format_specs<char>,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char> const &,std::_Fmt_align,`std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uint>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uint,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_ &)
0x180052e3c  nop
0x180052e3d  lea     rcx, [rbp+0B0h+var_D0]
0x180052e41  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180052e46  mov     rax, r15
0x180052e49  mov     rcx, [rbp+0B0h+var_40]
0x180052e4d  xor     rcx, rsp; StackCookie
0x180052e50  call    __security_check_cookie
0x180052e55  mov     rbx, [rsp+1B0h+arg_8]
0x180052e5d  add     rsp, 180h
0x180052e64  pop     r15
0x180052e66  pop     r14
0x180052e68  pop     r13
0x180052e6a  pop     r12
0x180052e6c  pop     rdi
0x180052e6d  pop     rsi
0x180052e6e  pop     rbp
0x180052e6f  retn
0x180052e70  lea     rcx, aIntegralCannot; "integral cannot be stored in char"
0x180052e77  call    ?_Throw_format_error@std@@YAXPEBD@Z; std::_Throw_format_error(char const *)
```

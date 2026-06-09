# OPath::Combine(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180002b40`
- end: `0x180003123`
- name: `?Combine@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z`
- size: `1507`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800033e0`
- `0x1800052dc`
- `0x1800054f0`
- `0x180021610`

## callees

- `0x1800025a8`
- `0x180002820`
- `0x180002b40`
- `0x180003124`
- `0x180003e90`
- `0x180004044`
- `0x18000410c`
- `0x1800045ec`
- `0x18000465c`
- `0x180004b44`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002d05`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002ec0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180003002`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000303a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180003099`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800030e5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002d05`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002ec0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180003002`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000303a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180003099`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800030e5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002c53`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002d0c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002d4a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002f4f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003009`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003041`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800030a0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800030ec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002c53`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002d0c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002d4a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180002f4f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003009`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003041`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800030a0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800030ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall OPath::Combine(__int64 a1, __int64 a2, void *a3)
{
  bool v5; // di
  char v6; // bl
  char PathSeperator; // r14
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rax
  _BYTE *v11; // rcx
  _BYTE *v12; // rdx
  __int16 v13; // r14
  __int64 v14; // rbx
  void **v15; // rdi
  unsigned __int64 v16; // rsi
  void **v17; // rax
  void **v18; // rdx
  void **v19; // rax
  void *v20; // rcx
  bool v21; // di
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  int v26; // [rsp+30h] [rbp-89h] BYREF
  void *v27[2]; // [rsp+38h] [rbp-81h] BYREF
  __m128i v28; // [rsp+48h] [rbp-71h]
  void *v29[2]; // [rsp+58h] [rbp-61h] BYREF
  __m128i v30; // [rsp+68h] [rbp-51h]
  void *Block[2]; // [rsp+78h] [rbp-41h] BYREF
  __int128 v32; // [rsp+88h] [rbp-31h]
  void *v33[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v35; // [rsp+B0h] [rbp-9h]
  void *Src[2]; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v37; // [rsp+C8h] [rbp+Fh]
  unsigned __int64 v38; // [rsp+D0h] [rbp+17h]

  v5 = 0;
  v6 = 0;
  v26 = 0;
  *(_OWORD *)Src = 0;
  v37 = 0;
  v38 = 7;
  LOWORD(Src[0]) = 0;
  *(_OWORD *)v29 = 0;
  v30.m128i_i64[0] = 0;
  v30.m128i_i64[1] = 7;
  LOWORD(v29[0]) = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v35 = 7;
  LOWORD(v33[0]) = 0;
  PathSeperator = OPath::GetPathSeperator(a1, v33, &v26);
  std::wstring::operator=(v29);
  if ( !PathSeperator )
  {
    *(_OWORD *)Block = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>(Block, L"/", 1);
    v6 = 1;
    v5 = std::wstring::find(a2, Block, 0) != -1;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    if ( *((_QWORD *)&v32 + 1) > 7u )
    {
      v8 = Block[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v32 + 1) + 2) >= 0x1000 )
      {
        v8 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v8 - 8) > 0x1F )
          goto LABEL_54;
      }
      free(v8);
    }
  }
  if ( v5 )
  {
    *(_OWORD *)v27 = 0;
    v28 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v27, L"\\", 1);
    *(_OWORD *)Block = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>(Block, L"/", 1);
    OString::Replace(v29, Block, v27);
    if ( *((_QWORD *)&v32 + 1) > 7u )
    {
      v9 = Block[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v32 + 1) + 2) >= 0x1000 )
      {
        v9 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v9);
    }
    v10 = v28.m128i_i64[1];
    if ( v28.m128i_i64[1] > 7uLL )
    {
      v11 = v27[0];
LABEL_16:
      v12 = v11;
      if ( (unsigned __int64)(2 * v10 + 2) < 0x1000
        || (v11 = (_BYTE *)*((_QWORD *)v11 - 1), (unsigned __int64)(v12 - v11 - 8) <= 0x1F) )
      {
        free(v11);
        goto LABEL_19;
      }
LABEL_54:
      _invoke_watson(0, 0, 0, 0, 0);
    }
  }
  else
  {
    v21 = 0;
    if ( PathSeperator )
    {
      *(_OWORD *)v27 = 0;
      v28 = 0;
      std::wstring::_Construct<1,wchar_t const *>(v27, L"\\", 1);
      v6 |= 2u;
      if ( std::wstring::find(a2, v27, 0) != -1 )
        v21 = 1;
    }
    if ( (v6 & 2) != 0 && v28.m128i_i64[1] > 7uLL )
    {
      v22 = v27[0];
      if ( (unsigned __int64)(2 * v28.m128i_i64[1] + 2) >= 0x1000 )
      {
        v22 = (void *)*((_QWORD *)v27[0] - 1);
        if ( (unsigned __int64)((char *)v27[0] - (char *)v22 - 8) > 0x1F )
          goto LABEL_54;
      }
      free(v22);
    }
    if ( v21 )
    {
      *(_OWORD *)Block = 0;
      v32 = 0;
      std::wstring::_Construct<1,wchar_t const *>(Block, L"/", 1);
      *(_OWORD *)v27 = 0;
      v28 = 0;
      std::wstring::_Construct<1,wchar_t const *>(v27, L"\\", 1);
      OString::Replace(v29, v27, Block);
      if ( v28.m128i_i64[1] > 7uLL )
      {
        v23 = v27[0];
        if ( (unsigned __int64)(2 * v28.m128i_i64[1] + 2) >= 0x1000 )
        {
          v23 = (void *)*((_QWORD *)v27[0] - 1);
          if ( (unsigned __int64)((char *)v27[0] - (char *)v23 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v23);
      }
      v10 = *((_QWORD *)&v32 + 1);
      if ( *((_QWORD *)&v32 + 1) > 7u )
      {
        v11 = Block[0];
        goto LABEL_16;
      }
    }
  }
LABEL_19:
  v13 = v26;
  v14 = v30.m128i_i64[0];
  v15 = (void **)v29[0];
  v16 = v30.m128i_u64[1];
  if ( v30.m128i_i64[0] )
  {
    v17 = v29;
    if ( v30.m128i_i64[1] > 7uLL )
      v17 = (void **)v29[0];
    if ( *(_WORD *)v17 == (_WORD)v26 )
    {
      *(_OWORD *)v27 = 0;
      v28 = 0;
      _mm_lfence();
      v18 = v29;
      if ( v30.m128i_i64[1] > 7uLL )
        v18 = (void **)v29[0];
      std::wstring::_Construct<1,wchar_t const *>(v27, (char *)v18 + 2, v30.m128i_i64[0] - 1);
      std::wstring::_Tidy_deallocate(v29);
      *(_OWORD *)v29 = *(_OWORD *)v27;
      v30 = v28;
      v16 = _mm_srli_si128(v28, 8).m128i_u64[0];
      v14 = v28.m128i_i64[0];
      v15 = (void **)v27[0];
    }
  }
  std::wstring::operator=(Src);
  if ( !OString::EndsWith(Src, (__int64 *)v33) && v14 )
  {
    v19 = v29;
    if ( v16 > 7 )
      v19 = v15;
    if ( v13 != *(_WORD *)v19 && v37 )
      std::wstring::append(Src);
  }
  std::wstring::append(Src);
  std::wstring::operator=(a3);
  if ( v35 > 7 )
  {
    v20 = v33[0];
    if ( 2 * v35 + 2 >= 0x1000 )
    {
      v20 = (void *)*((_QWORD *)v33[0] - 1);
      if ( (unsigned __int64)((char *)v33[0] - (char *)v20 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v20);
  }
  v33[0] = (void *)19937;
  v34 = 0;
  v35 = 15;
  if ( v30.m128i_i64[1] > 7uLL )
  {
    v24 = v29[0];
    if ( (unsigned __int64)(2 * v30.m128i_i64[1] + 2) >= 0x1000 )
    {
      v24 = (void *)*((_QWORD *)v29[0] - 1);
      if ( (unsigned __int64)((char *)v29[0] - (char *)v24 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v24);
  }
  if ( v38 > 7 )
  {
    v25 = Src[0];
    if ( 2 * v38 + 2 >= 0x1000 )
    {
      v25 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v25 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v25);
  }
}

```

## disassembly

```asm
0x180002b40  mov     [rsp-8+arg_18], rbx
0x180002b45  push    rbp
0x180002b46  push    rsi
0x180002b47  push    rdi
0x180002b48  push    r12
0x180002b4a  push    r13
0x180002b4c  push    r14
0x180002b4e  push    r15
0x180002b50  lea     rbp, [rsp-27h]
0x180002b55  sub     rsp, 0E0h
0x180002b5c  mov     rax, cs:__security_cookie
0x180002b63  xor     rax, rsp
0x180002b66  mov     [rbp+57h+var_38], rax
0x180002b6a  mov     r13, r8
0x180002b6d  mov     rsi, rdx
0x180002b70  mov     r12, rcx
0x180002b73  xor     edi, edi
0x180002b75  mov     ebx, edi
0x180002b77  mov     [rsp+110h+var_E0], ebx
0x180002b7b  xorps   xmm0, xmm0
0x180002b7e  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180002b82  mov     [rbp+57h+var_48], rdi
0x180002b86  lea     eax, [rdi+7]
0x180002b89  mov     [rbp+57h+var_40], rax
0x180002b8d  mov     word ptr [rbp+57h+Src], di
0x180002b91  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x180002b95  mov     qword ptr [rbp+57h+var_A8], rdi
0x180002b99  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180002b9d  mov     word ptr [rbp+57h+var_B8], di
0x180002ba1  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x180002ba5  mov     [rbp+57h+var_68], rdi
0x180002ba9  mov     [rbp+57h+var_60], rax
0x180002bad  mov     word ptr [rbp+57h+var_78], di
0x180002bb1  lea     r8, [rsp+110h+var_E0]
0x180002bb6  lea     rdx, [rbp+57h+var_78]
0x180002bba  call    ?GetPathSeperator@OPath@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@AEA_W@Z; OPath::GetPathSeperator(std::wstring const &,std::wstring &,wchar_t &)
0x180002bbf  mov     r14b, al
0x180002bc2  mov     rdx, rsi
0x180002bc5  lea     rcx, [rbp+57h+var_B8]; void *
0x180002bc9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180002bce  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002bd2  test    r14b, r14b
0x180002bd5  jnz     short loc_180002C15
0x180002bd7  xorps   xmm0, xmm0
0x180002bda  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180002bde  xorps   xmm1, xmm1
0x180002be1  movdqu  [rbp+57h+var_88], xmm1
0x180002be6  lea     r8d, [rdi+1]
0x180002bea  lea     rdx, asc_18002F444; "/"
0x180002bf1  lea     rcx, [rbp+57h+Block]
0x180002bf5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002bfa  nop
0x180002bfb  lea     ebx, [rdi+1]
0x180002bfe  xor     r8d, r8d
0x180002c01  lea     rdx, [rbp+57h+Block]
0x180002c05  mov     rcx, rsi
0x180002c08  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180002c0d  cmp     rax, r15
0x180002c10  jz      short loc_180002C15
0x180002c12  mov     dil, bl
0x180002c15  test    bl, 1
0x180002c18  jz      short loc_180002C59
0x180002c1a  and     ebx, 0FFFFFFFEh
0x180002c1d  mov     rax, qword ptr [rbp+57h+var_88+8]
0x180002c21  cmp     rax, 7
0x180002c25  jbe     short loc_180002C59
0x180002c27  mov     rcx, [rbp+57h+Block]
0x180002c2b  mov     rdx, rcx
0x180002c2e  lea     rax, ds:2[rax*2]
0x180002c36  cmp     rax, 1000h
0x180002c3c  jb      short loc_180002C53
0x180002c3e  mov     rcx, [rcx-8]; Block
0x180002c42  sub     rdx, rcx
0x180002c45  lea     rax, [rdx-8]
0x180002c49  cmp     rax, 1Fh
0x180002c4d  ja      loc_180003027
0x180002c53  call    cs:__imp_free
0x180002c59  test    dil, dil
0x180002c5c  jz      loc_180002EC7
0x180002c62  xorps   xmm0, xmm0
0x180002c65  movups  xmmword ptr [rsp+110h+var_D8], xmm0
0x180002c6a  xorps   xmm1, xmm1
0x180002c6d  movdqu  [rbp+57h+var_C8], xmm1
0x180002c72  mov     r8d, 1
0x180002c78  lea     rdx, asc_18002F1F4; "\\"
0x180002c7f  lea     rcx, [rsp+110h+var_D8]
0x180002c84  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002c89  xorps   xmm0, xmm0
0x180002c8c  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180002c90  xorps   xmm1, xmm1
0x180002c93  movdqu  [rbp+57h+var_88], xmm1
0x180002c98  mov     r8d, 1
0x180002c9e  lea     rdx, asc_18002F444; "/"
0x180002ca5  lea     rcx, [rbp+57h+Block]
0x180002ca9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002cae  lea     r8, [rsp+110h+var_D8]
0x180002cb3  lea     rdx, [rbp+57h+Block]
0x180002cb7  lea     rcx, [rbp+57h+var_B8]
0x180002cbb  call    ?Replace@OString@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@1_K@Z; OString::Replace(std::wstring &,std::wstring const &,std::wstring const &,unsigned __int64)
0x180002cc0  mov     rax, qword ptr [rbp+57h+var_88+8]
0x180002cc4  cmp     rax, 7
0x180002cc8  jbe     short loc_180002D13
0x180002cca  mov     rcx, [rbp+57h+Block]; Block
0x180002cce  mov     rdx, rcx
0x180002cd1  lea     rax, ds:2[rax*2]
0x180002cd9  cmp     rax, 1000h
0x180002cdf  jb      short loc_180002D0C
0x180002ce1  mov     rcx, [rcx-8]
0x180002ce5  sub     rdx, rcx
0x180002ce8  lea     rax, [rdx-8]
0x180002cec  cmp     rax, 1Fh
0x180002cf0  jbe     short loc_180002D0C
0x180002cf2  mov     [rsp+110h+Reserved], 0; Reserved
0x180002cfb  xor     r9d, r9d; LineNo
0x180002cfe  xor     r8d, r8d; FileName
0x180002d01  xor     edx, edx; FunctionName
0x180002d03  xor     ecx, ecx; Expression
0x180002d05  call    cs:__imp__invoke_watson
0x180002d0c  call    cs:__imp_free
0x180002d12  nop
0x180002d13  mov     rax, qword ptr [rbp+57h+var_C8+8]
0x180002d17  cmp     rax, 7
0x180002d1b  jbe     short loc_180002D50
0x180002d1d  mov     rcx, [rsp+110h+var_D8]
0x180002d22  lea     rax, ds:2[rax*2]
0x180002d2a  cmp     rax, 1000h
0x180002d30  mov     rdx, rcx
0x180002d33  jb      short loc_180002D4A
0x180002d35  mov     rcx, [rcx-8]; Block
0x180002d39  sub     rdx, rcx
0x180002d3c  lea     rax, [rdx-8]
0x180002d40  cmp     rax, 1Fh
0x180002d44  ja      loc_180003027
0x180002d4a  call    cs:__imp_free
0x180002d50  movzx   r14d, word ptr [rsp+110h+var_E0]
0x180002d56  mov     rbx, qword ptr [rbp+57h+var_A8]
0x180002d5a  mov     rdi, [rbp+57h+var_B8]
0x180002d5e  mov     rsi, qword ptr [rbp+57h+var_A8+8]
0x180002d62  test    rbx, rbx
0x180002d65  jz      loc_180002DF4
0x180002d6b  lea     rax, [rbp+57h+var_B8]
0x180002d6f  cmp     rsi, 7
0x180002d73  cmova   rax, rdi
0x180002d77  cmp     [rax], r14w
0x180002d7b  jnz     short loc_180002DF4
0x180002d7d  xorps   xmm0, xmm0
0x180002d80  movups  xmmword ptr [rsp+110h+var_D8], xmm0
0x180002d85  xorps   xmm1, xmm1
0x180002d88  movdqu  [rbp+57h+var_C8], xmm1
0x180002d8d  cmp     rbx, 1
0x180002d91  jb      loc_180003119
0x180002d97  lfence
0x180002d9a  lea     rax, [rbx-1]
0x180002d9e  cmp     rax, r15
0x180002da1  cmovb   r15, rax
0x180002da5  lea     rdx, [rbp+57h+var_B8]
0x180002da9  cmp     rsi, 7
0x180002dad  cmova   rdx, rdi
0x180002db1  add     rdx, 2
0x180002db5  mov     r8, r15
0x180002db8  lea     rcx, [rsp+110h+var_D8]
0x180002dbd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002dc2  lea     rcx, [rbp+57h+var_B8]
0x180002dc6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002dcb  movups  xmm2, xmmword ptr [rsp+110h+var_D8]
0x180002dd0  movups  xmmword ptr [rbp+57h+var_B8], xmm2
0x180002dd4  movups  xmm1, [rbp+57h+var_C8]
0x180002dd8  movups  [rbp+57h+var_A8], xmm1
0x180002ddc  movdqa  xmm0, xmm1
0x180002de0  psrldq  xmm0, 8
0x180002de5  movq    rsi, xmm0
0x180002dea  movq    rbx, xmm1
0x180002def  movq    rdi, xmm2
0x180002df4  mov     rdx, r12
0x180002df7  lea     rcx, [rbp+57h+Src]; void *
0x180002dfb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180002e00  lea     rdx, [rbp+57h+var_78]
0x180002e04  lea     rcx, [rbp+57h+Src]
0x180002e08  call    ?EndsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z; OString::EndsWith(std::wstring const &,std::wstring const &,bool)
0x180002e0d  xor     r15d, r15d
0x180002e10  test    al, al
0x180002e12  jnz     short loc_180002E4C
0x180002e14  test    rbx, rbx
0x180002e17  jz      short loc_180002E4C
0x180002e19  lea     rax, [rbp+57h+var_B8]
0x180002e1d  cmp     rsi, 7
0x180002e21  cmova   rax, rdi
0x180002e25  cmp     r14w, [rax]
0x180002e29  jz      short loc_180002E4C
0x180002e2b  cmp     [rbp+57h+var_48], r15
0x180002e2f  jz      short loc_180002E4C
0x180002e31  lea     rdx, [rbp+57h+var_78]
0x180002e35  cmp     [rbp+57h+var_60], 7
0x180002e3a  cmova   rdx, [rbp+57h+var_78]
0x180002e3f  mov     r8, [rbp+57h+var_68]
0x180002e43  lea     rcx, [rbp+57h+Src]; Src
0x180002e47  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180002e4c  lea     rdx, [rbp+57h+var_B8]
0x180002e50  cmp     rsi, 7
0x180002e54  cmova   rdx, rdi
0x180002e58  mov     r8, rbx
0x180002e5b  lea     rcx, [rbp+57h+Src]; Src
0x180002e5f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180002e64  lea     rdx, [rbp+57h+Src]
0x180002e68  mov     rcx, r13; void *
0x180002e6b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180002e70  nop
0x180002e71  mov     rax, [rbp+57h+var_60]
0x180002e75  mov     ebx, 1000h
0x180002e7a  cmp     rax, 7
0x180002e7e  jbe     loc_180003047
0x180002e84  mov     rcx, [rbp+57h+var_78]; Block
0x180002e88  mov     rdx, rcx
0x180002e8b  lea     rax, ds:2[rax*2]
0x180002e93  cmp     rax, rbx
0x180002e96  jb      loc_180003041
0x180002e9c  mov     rcx, [rcx-8]
0x180002ea0  sub     rdx, rcx
0x180002ea3  lea     rax, [rdx-8]
0x180002ea7  cmp     rax, 1Fh
0x180002eab  jbe     loc_180003041
0x180002eb1  mov     [rsp+110h+Reserved], r15; Reserved
0x180002eb6  xor     r9d, r9d; LineNo
0x180002eb9  xor     r8d, r8d; FileName
0x180002ebc  xor     edx, edx; FunctionName
0x180002ebe  xor     ecx, ecx; Expression
0x180002ec0  call    cs:__imp__invoke_watson
0x180002ec7  test    r14b, r14b
0x180002eca  jz      short loc_180002F10
0x180002ecc  xorps   xmm0, xmm0
0x180002ecf  movups  xmmword ptr [rsp+110h+var_D8], xmm0
0x180002ed4  xorps   xmm1, xmm1
0x180002ed7  movdqu  [rbp+57h+var_C8], xmm1
0x180002edc  mov     r8d, 1
0x180002ee2  lea     rdx, asc_18002F1F4; "\\"
0x180002ee9  lea     rcx, [rsp+110h+var_D8]
0x180002eee  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002ef3  or      ebx, 2
0x180002ef6  xor     r8d, r8d
0x180002ef9  lea     rdx, [rsp+110h+var_D8]
0x180002efe  mov     rcx, rsi
0x180002f01  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180002f06  cmp     rax, r15
0x180002f09  jz      short loc_180002F10
0x180002f0b  mov     dil, 1
0x180002f0e  jmp     short loc_180002F13
0x180002f10  xor     dil, dil
0x180002f13  test    bl, 2
0x180002f16  jz      short loc_180002F55
0x180002f18  mov     rax, qword ptr [rbp+57h+var_C8+8]
0x180002f1c  cmp     rax, 7
0x180002f20  jbe     short loc_180002F55
0x180002f22  mov     rcx, [rsp+110h+var_D8]
0x180002f27  mov     rdx, rcx
0x180002f2a  lea     rax, ds:2[rax*2]
0x180002f32  cmp     rax, 1000h
0x180002f38  jb      short loc_180002F4F
0x180002f3a  mov     rcx, [rcx-8]; Block
0x180002f3e  sub     rdx, rcx
0x180002f41  lea     rax, [rdx-8]
0x180002f45  cmp     rax, 1Fh
0x180002f49  ja      loc_180003027
0x180002f4f  call    cs:__imp_free
0x180002f55  test    dil, dil
0x180002f58  jz      loc_180002D50
0x180002f5e  xorps   xmm0, xmm0
0x180002f61  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180002f65  xorps   xmm1, xmm1
0x180002f68  movdqu  [rbp+57h+var_88], xmm1
0x180002f6d  mov     r8d, 1
0x180002f73  lea     rdx, asc_18002F444; "/"
0x180002f7a  lea     rcx, [rbp+57h+Block]
0x180002f7e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002f83  xorps   xmm0, xmm0
0x180002f86  movups  xmmword ptr [rsp+110h+var_D8], xmm0
0x180002f8b  xorps   xmm1, xmm1
0x180002f8e  movdqu  [rbp+57h+var_C8], xmm1
0x180002f93  mov     r8d, 1
0x180002f99  lea     rdx, asc_18002F1F4; "\\"
0x180002fa0  lea     rcx, [rsp+110h+var_D8]
0x180002fa5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002faa  lea     r8, [rbp+57h+Block]
0x180002fae  lea     rdx, [rsp+110h+var_D8]
0x180002fb3  lea     rcx, [rbp+57h+var_B8]
0x180002fb7  call    ?Replace@OString@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@1_K@Z; OString::Replace(std::wstring &,std::wstring const &,std::wstring const &,unsigned __int64)
0x180002fbc  mov     rax, qword ptr [rbp+57h+var_C8+8]
0x180002fc0  cmp     rax, 7
0x180002fc4  jbe     short loc_180003010
0x180002fc6  mov     rcx, [rsp+110h+var_D8]; Block
0x180002fcb  mov     rdx, rcx
0x180002fce  lea     rax, ds:2[rax*2]
0x180002fd6  cmp     rax, 1000h
0x180002fdc  jb      short loc_180003009
0x180002fde  mov     rcx, [rcx-8]
0x180002fe2  sub     rdx, rcx
0x180002fe5  lea     rax, [rdx-8]
0x180002fe9  cmp     rax, 1Fh
0x180002fed  jbe     short loc_180003009
0x180002fef  mov     [rsp+110h+Reserved], 0; Reserved
0x180002ff8  xor     r9d, r9d; LineNo
  ... truncated ...
```

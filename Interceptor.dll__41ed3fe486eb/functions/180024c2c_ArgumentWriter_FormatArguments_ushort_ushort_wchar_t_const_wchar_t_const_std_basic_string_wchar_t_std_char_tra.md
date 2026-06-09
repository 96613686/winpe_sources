# ArgumentWriter::FormatArguments<ushort,ushort>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &)

- ea: `0x180024c2c`
- end: `0x180024deb`
- name: `??$FormatArguments@GG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180024884`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180024c2c`
- `0x180024fac`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024dd8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024dd8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024ddf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024ddf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4)
{
  unsigned __int16 *v6; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // r15
  __int64 v11; // r8
  void *v13; // rcx
  unsigned __int16 *v14[3]; // [rsp+30h] [rbp-50h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-38h] BYREF
  __m128i v16; // [rsp+58h] [rbp-28h]

  v6 = a2;
  v14[2] = (unsigned __int16 *)a1;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v11 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v11);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v16 = si128;
    LOWORD(Block[0]) = 0;
    v9 = *v6;
    v10 = v6 + 1;
    v6 = v10;
    v14[0] = v10;
    if ( v9 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v10 == a3 || *v10 != 37 )
      break;
    std::wstring::append(a4);
    v6 = v10 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v6 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)v14, a3, a4, (__int64)Block) )
  {
    v6 = v14[0];
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,>(a1, v14[0], a3, a4);
  if ( v16.m128i_i64[1] > 7uLL )
  {
    v13 = Block[0];
    if ( (unsigned __int64)(2 * v16.m128i_i64[1] + 2) >= 0x1000 )
    {
      v13 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v13);
  }
  return a1;
}

```

## disassembly

```asm
0x180024c2c  mov     [rsp-38h+arg_10], rbx
0x180024c31  push    rbp
0x180024c32  push    rsi
0x180024c33  push    rdi
0x180024c34  push    r12
0x180024c36  push    r13
0x180024c38  push    r14
0x180024c3a  push    r15
0x180024c3c  mov     rbp, rsp
0x180024c3f  sub     rsp, 80h
0x180024c46  movaps  [rsp+80h+var_10], xmm6
0x180024c4b  mov     rax, cs:__security_cookie
0x180024c52  xor     rax, rsp
0x180024c55  mov     [rbp+var_18], rax
0x180024c59  mov     rbx, r9
0x180024c5c  mov     r14, r8
0x180024c5f  mov     rsi, rdx
0x180024c62  mov     rdi, rcx
0x180024c65  mov     [rbp+var_40], rcx
0x180024c69  mov     r12, [rbp+arg_20]
0x180024c6d  mov     r13, [rbp+arg_28]
0x180024c71  xor     r15d, r15d
0x180024c74  cmp     rdx, r8
0x180024c77  jnb     loc_180024D14
0x180024c7d  lfence
0x180024c80  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180024c88  mov     eax, 25h ; '%'
0x180024c8d  xorps   xmm0, xmm0
0x180024c90  movups  xmmword ptr [rbp+Block], xmm0
0x180024c94  movdqu  [rbp+var_28], xmm6
0x180024c99  mov     word ptr [rbp+Block], r15w
0x180024c9e  movzx   r8d, word ptr [rsi]
0x180024ca2  lea     r15, [rsi+2]
0x180024ca6  mov     rsi, r15
0x180024ca9  mov     [rbp+var_50], r15
0x180024cad  cmp     r8w, ax
0x180024cb1  jz      short loc_180024CC3
0x180024cb3  lea     edx, [rax-24h]
0x180024cb6  mov     rcx, rbx; Src
0x180024cb9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024cbe  xor     r15d, r15d
0x180024cc1  jmp     short loc_180024D02
0x180024cc3  cmp     r15, r14
0x180024cc6  jz      short loc_180024CE4
0x180024cc8  cmp     [r15], ax
0x180024ccc  jnz     short loc_180024CE4
0x180024cce  mov     r8d, eax
0x180024cd1  mov     edx, 1
0x180024cd6  mov     rcx, rbx; Src
0x180024cd9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024cde  lea     rsi, [r15+2]
0x180024ce2  jmp     short loc_180024CBE
0x180024ce4  lea     r9, [rbp+Block]
0x180024ce8  mov     r8, rbx
0x180024ceb  mov     rdx, r14
0x180024cee  lea     rcx, [rbp+var_50]
0x180024cf2  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180024cf7  xor     r15d, r15d
0x180024cfa  test    al, al
0x180024cfc  jnz     short loc_180024D6B
0x180024cfe  mov     rsi, [rbp+var_50]
0x180024d02  lea     rcx, [rbp+Block]
0x180024d06  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024d0b  cmp     rsi, r14
0x180024d0e  jb      loc_180024C88
0x180024d14  xorps   xmm0, xmm0
0x180024d17  movups  xmmword ptr [rdi], xmm0
0x180024d1a  mov     [rdi+10h], r15
0x180024d1e  mov     [rdi+18h], r15
0x180024d22  mov     r8, [rbx+10h]
0x180024d26  cmp     qword ptr [rbx+18h], 7
0x180024d2b  jbe     short loc_180024D30
0x180024d2d  mov     rbx, [rbx]
0x180024d30  mov     rdx, rbx
0x180024d33  mov     rcx, rdi
0x180024d36  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180024d3b  nop
0x180024d3c  mov     rax, rdi
0x180024d3f  mov     rcx, [rbp+var_18]
0x180024d43  xor     rcx, rsp; StackCookie
0x180024d46  call    __security_check_cookie
0x180024d4b  mov     rbx, [rsp+80h+arg_10]
0x180024d53  movaps  xmm6, [rsp+80h+var_10]
0x180024d58  add     rsp, 80h
0x180024d5f  pop     r15
0x180024d61  pop     r14
0x180024d63  pop     r13
0x180024d65  pop     r12
0x180024d67  pop     rdi
0x180024d68  pop     rsi
0x180024d69  pop     rbp
0x180024d6a  retn
0x180024d6b  lfence
0x180024d6e  movzx   r8d, word ptr [r12]
0x180024d73  lea     rdx, [rbp+Block]; Format
0x180024d77  mov     rcx, rbx; Src
0x180024d7a  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024d7f  mov     [rsp+80h+Reserved], r13
0x180024d84  mov     r9, rbx
0x180024d87  mov     r8, r14
0x180024d8a  mov     rdx, [rbp+var_50]
0x180024d8e  mov     rcx, rdi
0x180024d91  call    ??$FormatArguments@G$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG@Z; ArgumentWriter::FormatArguments<ushort,>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &)
0x180024d96  nop
0x180024d97  mov     rax, qword ptr [rbp+var_28+8]
0x180024d9b  cmp     rax, 7
0x180024d9f  jbe     short loc_180024D3C
0x180024da1  mov     rcx, [rbp+Block]; Block
0x180024da5  mov     rdx, rcx
0x180024da8  lea     rax, ds:2[rax*2]
0x180024db0  cmp     rax, 1000h
0x180024db6  jb      short loc_180024DDF
0x180024db8  mov     rcx, [rcx-8]
0x180024dbc  sub     rdx, rcx
0x180024dbf  lea     rax, [rdx-8]
0x180024dc3  cmp     rax, 1Fh
0x180024dc7  jbe     short loc_180024DDF
0x180024dc9  mov     [rsp+80h+Reserved], r15; Reserved
0x180024dce  xor     r9d, r9d; LineNo
0x180024dd1  xor     r8d, r8d; FileName
0x180024dd4  xor     edx, edx; FunctionName
0x180024dd6  xor     ecx, ecx; Expression
0x180024dd8  call    cs:__imp__invoke_watson
0x180024ddf  call    cs:__imp_free
0x180024de5  jmp     loc_180024D3C
```

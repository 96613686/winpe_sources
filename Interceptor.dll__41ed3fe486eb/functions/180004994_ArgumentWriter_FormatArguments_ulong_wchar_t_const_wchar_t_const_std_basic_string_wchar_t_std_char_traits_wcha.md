# ArgumentWriter::FormatArguments<ulong,>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ulong const &)

- ea: `0x180004994`
- end: `0x180004b43`
- name: `??$FormatArguments@K$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBK@Z`
- size: `431`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180004d84`
- `0x180005858`
- `0x180024dec`

## callees

- `0x180001bc0`
- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180004994`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004b30`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004b30`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004b37`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004b37`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned long,>(
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
LABEL_11:
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
    if ( v9 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v6 >= a3 )
      goto LABEL_11;
  }
  if ( v10 != a3 && *v10 == 37 )
  {
    std::wstring::append(a4);
    v6 = v10 + 1;
    goto LABEL_10;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)v14, a3, a4, (__int64)Block) )
  {
    v6 = v14[0];
    goto LABEL_10;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments(a1, v14[0], a3, a4);
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
0x180004994  mov     [rsp-38h+arg_10], rbx
0x180004999  push    rbp
0x18000499a  push    rsi
0x18000499b  push    rdi
0x18000499c  push    r12
0x18000499e  push    r13
0x1800049a0  push    r14
0x1800049a2  push    r15
0x1800049a4  mov     rbp, rsp
0x1800049a7  sub     rsp, 80h
0x1800049ae  movaps  [rsp+80h+var_10], xmm6
0x1800049b3  mov     rax, cs:__security_cookie
0x1800049ba  xor     rax, rsp
0x1800049bd  mov     [rbp+var_18], rax
0x1800049c1  mov     rbx, r9
0x1800049c4  mov     r14, r8
0x1800049c7  mov     rsi, rdx
0x1800049ca  mov     rdi, rcx
0x1800049cd  mov     [rbp+var_40], rcx
0x1800049d1  mov     r12, [rbp+arg_20]
0x1800049d5  xor     r13d, r13d
0x1800049d8  cmp     rdx, r8
0x1800049db  jnb     loc_180004A72
0x1800049e1  lfence
0x1800049e4  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800049ec  mov     eax, 25h ; '%'
0x1800049f1  xorps   xmm0, xmm0
0x1800049f4  movups  xmmword ptr [rbp+Block], xmm0
0x1800049f8  movdqu  [rbp+var_28], xmm6
0x1800049fd  mov     word ptr [rbp+Block], r13w
0x180004a02  movzx   r8d, word ptr [rsi]
0x180004a06  lea     r15, [rsi+2]
0x180004a0a  mov     rsi, r15
0x180004a0d  mov     [rbp+var_50], r15
0x180004a11  cmp     r8w, ax
0x180004a15  jz      short loc_180004A24
0x180004a17  lea     edx, [rax-24h]
0x180004a1a  mov     rcx, rbx; Src
0x180004a1d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180004a22  jmp     short loc_180004A60
0x180004a24  cmp     r15, r14
0x180004a27  jz      short loc_180004A45
0x180004a29  cmp     [r15], ax
0x180004a2d  jnz     short loc_180004A45
0x180004a2f  mov     r8d, eax
0x180004a32  mov     edx, 1
0x180004a37  mov     rcx, rbx; Src
0x180004a3a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180004a3f  lea     rsi, [r15+2]
0x180004a43  jmp     short loc_180004A60
0x180004a45  lea     r9, [rbp+Block]
0x180004a49  mov     r8, rbx
0x180004a4c  mov     rdx, r14
0x180004a4f  lea     rcx, [rbp+var_50]
0x180004a53  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180004a58  test    al, al
0x180004a5a  jnz     short loc_180004AC9
0x180004a5c  mov     rsi, [rbp+var_50]
0x180004a60  lea     rcx, [rbp+Block]
0x180004a64  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180004a69  cmp     rsi, r14
0x180004a6c  jb      loc_1800049EC
0x180004a72  xorps   xmm0, xmm0
0x180004a75  movups  xmmword ptr [rdi], xmm0
0x180004a78  mov     [rdi+10h], r13
0x180004a7c  mov     [rdi+18h], r13
0x180004a80  mov     r8, [rbx+10h]
0x180004a84  cmp     qword ptr [rbx+18h], 7
0x180004a89  jbe     short loc_180004A8E
0x180004a8b  mov     rbx, [rbx]
0x180004a8e  mov     rdx, rbx
0x180004a91  mov     rcx, rdi
0x180004a94  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004a99  nop
0x180004a9a  mov     rax, rdi
0x180004a9d  mov     rcx, [rbp+var_18]
0x180004aa1  xor     rcx, rsp; StackCookie
0x180004aa4  call    __security_check_cookie
0x180004aa9  mov     rbx, [rsp+80h+arg_10]
0x180004ab1  movaps  xmm6, [rsp+80h+var_10]
0x180004ab6  add     rsp, 80h
0x180004abd  pop     r15
0x180004abf  pop     r14
0x180004ac1  pop     r13
0x180004ac3  pop     r12
0x180004ac5  pop     rdi
0x180004ac6  pop     rsi
0x180004ac7  pop     rbp
0x180004ac8  retn
0x180004ac9  lfence
0x180004acc  mov     r8d, [r12]
0x180004ad0  lea     rdx, [rbp+Block]; Format
0x180004ad4  mov     rcx, rbx; Src
0x180004ad7  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180004adc  mov     r9, rbx
0x180004adf  mov     r8, r14
0x180004ae2  mov     rdx, [rbp+var_50]
0x180004ae6  mov     rcx, rdi
0x180004ae9  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x180004aee  nop
0x180004aef  mov     rax, qword ptr [rbp+var_28+8]
0x180004af3  cmp     rax, 7
0x180004af7  jbe     short loc_180004A9A
0x180004af9  mov     rcx, [rbp+Block]; Block
0x180004afd  mov     rdx, rcx
0x180004b00  lea     rax, ds:2[rax*2]
0x180004b08  cmp     rax, 1000h
0x180004b0e  jb      short loc_180004B37
0x180004b10  mov     rcx, [rcx-8]
0x180004b14  sub     rdx, rcx
0x180004b17  lea     rax, [rdx-8]
0x180004b1b  cmp     rax, 1Fh
0x180004b1f  jbe     short loc_180004B37
0x180004b21  mov     [rsp+80h+Reserved], r13; Reserved
0x180004b26  xor     r9d, r9d; LineNo
0x180004b29  xor     r8d, r8d; FileName
0x180004b2c  xor     edx, edx; FunctionName
0x180004b2e  xor     ecx, ecx; Expression
0x180004b30  call    cs:__imp__invoke_watson
0x180004b37  call    cs:__imp_free
0x180004b3d  jmp     loc_180004A9A
```

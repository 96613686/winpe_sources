# ArgumentWriter::FormatArguments<ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ulong const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180023b40`
- end: `0x180023cfe`
- name: `??$FormatArguments@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBKAEBV12@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023028`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180004b58`
- `0x180023b40`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023ceb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023ceb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023cf2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023cf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned long,std::wstring>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned __int16 *v8; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v11; // r8
  unsigned __int16 *v12; // r15
  __int64 v13; // r8
  void *v15; // rcx
  unsigned __int16 *v16[3]; // [rsp+30h] [rbp-50h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-38h] BYREF
  __m128i v18; // [rsp+58h] [rbp-28h]

  v8 = a2;
  v16[2] = (unsigned __int16 *)a1;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v13 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v13);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v18 = si128;
    LOWORD(Block[0]) = 0;
    v11 = *v8;
    v12 = v8 + 1;
    v8 = v12;
    v16[0] = v12;
    if ( v11 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v12 == a3 || *v12 != 37 )
      break;
    std::wstring::append(a4);
    v8 = v12 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v8 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)v16, a3, a4, (__int64)Block) )
  {
    v8 = v16[0];
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<std::wstring,>(a1, v16[0], a3, a4, a6);
  if ( v18.m128i_i64[1] > 7uLL )
  {
    v15 = Block[0];
    if ( (unsigned __int64)(2 * v18.m128i_i64[1] + 2) >= 0x1000 )
    {
      v15 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v15 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v15);
  }
  return a1;
}

```

## disassembly

```asm
0x180023b40  mov     [rsp-38h+arg_10], rbx
0x180023b45  push    rbp
0x180023b46  push    rsi
0x180023b47  push    rdi
0x180023b48  push    r12
0x180023b4a  push    r13
0x180023b4c  push    r14
0x180023b4e  push    r15
0x180023b50  mov     rbp, rsp
0x180023b53  sub     rsp, 80h
0x180023b5a  movaps  [rsp+80h+var_10], xmm6
0x180023b5f  mov     rax, cs:__security_cookie
0x180023b66  xor     rax, rsp
0x180023b69  mov     [rbp+var_18], rax
0x180023b6d  mov     rbx, r9
0x180023b70  mov     r14, r8
0x180023b73  mov     rsi, rdx
0x180023b76  mov     rdi, rcx
0x180023b79  mov     [rbp+var_40], rcx
0x180023b7d  mov     r12, [rbp+arg_20]
0x180023b81  mov     r13, [rbp+arg_28]
0x180023b85  xor     r15d, r15d
0x180023b88  cmp     rdx, r8
0x180023b8b  jnb     loc_180023C28
0x180023b91  lfence
0x180023b94  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180023b9c  mov     eax, 25h ; '%'
0x180023ba1  xorps   xmm0, xmm0
0x180023ba4  movups  xmmword ptr [rbp+Block], xmm0
0x180023ba8  movdqu  [rbp+var_28], xmm6
0x180023bad  mov     word ptr [rbp+Block], r15w
0x180023bb2  movzx   r8d, word ptr [rsi]
0x180023bb6  lea     r15, [rsi+2]
0x180023bba  mov     rsi, r15
0x180023bbd  mov     [rbp+var_50], r15
0x180023bc1  cmp     r8w, ax
0x180023bc5  jz      short loc_180023BD7
0x180023bc7  lea     edx, [rax-24h]
0x180023bca  mov     rcx, rbx; Src
0x180023bcd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023bd2  xor     r15d, r15d
0x180023bd5  jmp     short loc_180023C16
0x180023bd7  cmp     r15, r14
0x180023bda  jz      short loc_180023BF8
0x180023bdc  cmp     [r15], ax
0x180023be0  jnz     short loc_180023BF8
0x180023be2  mov     r8d, eax
0x180023be5  mov     edx, 1
0x180023bea  mov     rcx, rbx; Src
0x180023bed  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023bf2  lea     rsi, [r15+2]
0x180023bf6  jmp     short loc_180023BD2
0x180023bf8  lea     r9, [rbp+Block]
0x180023bfc  mov     r8, rbx
0x180023bff  mov     rdx, r14
0x180023c02  lea     rcx, [rbp+var_50]
0x180023c06  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180023c0b  xor     r15d, r15d
0x180023c0e  test    al, al
0x180023c10  jnz     short loc_180023C7F
0x180023c12  mov     rsi, [rbp+var_50]
0x180023c16  lea     rcx, [rbp+Block]
0x180023c1a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023c1f  cmp     rsi, r14
0x180023c22  jb      loc_180023B9C
0x180023c28  xorps   xmm0, xmm0
0x180023c2b  movups  xmmword ptr [rdi], xmm0
0x180023c2e  mov     [rdi+10h], r15
0x180023c32  mov     [rdi+18h], r15
0x180023c36  mov     r8, [rbx+10h]
0x180023c3a  cmp     qword ptr [rbx+18h], 7
0x180023c3f  jbe     short loc_180023C44
0x180023c41  mov     rbx, [rbx]
0x180023c44  mov     rdx, rbx
0x180023c47  mov     rcx, rdi
0x180023c4a  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180023c4f  nop
0x180023c50  mov     rax, rdi
0x180023c53  mov     rcx, [rbp+var_18]
0x180023c57  xor     rcx, rsp; StackCookie
0x180023c5a  call    __security_check_cookie
0x180023c5f  mov     rbx, [rsp+80h+arg_10]
0x180023c67  movaps  xmm6, [rsp+80h+var_10]
0x180023c6c  add     rsp, 80h
0x180023c73  pop     r15
0x180023c75  pop     r14
0x180023c77  pop     r13
0x180023c79  pop     r12
0x180023c7b  pop     rdi
0x180023c7c  pop     rsi
0x180023c7d  pop     rbp
0x180023c7e  retn
0x180023c7f  lfence
0x180023c82  mov     r8d, [r12]
0x180023c86  lea     rdx, [rbp+Block]; Format
0x180023c8a  mov     rcx, rbx; Src
0x180023c8d  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180023c92  mov     [rsp+80h+Reserved], r13
0x180023c97  mov     r9, rbx
0x180023c9a  mov     r8, r14
0x180023c9d  mov     rdx, [rbp+var_50]
0x180023ca1  mov     rcx, rdi
0x180023ca4  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@@Z; ArgumentWriter::FormatArguments<std::wstring,>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &)
0x180023ca9  nop
0x180023caa  mov     rax, qword ptr [rbp+var_28+8]
0x180023cae  cmp     rax, 7
0x180023cb2  jbe     short loc_180023C50
0x180023cb4  mov     rcx, [rbp+Block]; Block
0x180023cb8  mov     rdx, rcx
0x180023cbb  lea     rax, ds:2[rax*2]
0x180023cc3  cmp     rax, 1000h
0x180023cc9  jb      short loc_180023CF2
0x180023ccb  mov     rcx, [rcx-8]
0x180023ccf  sub     rdx, rcx
0x180023cd2  lea     rax, [rdx-8]
0x180023cd6  cmp     rax, 1Fh
0x180023cda  jbe     short loc_180023CF2
0x180023cdc  mov     [rsp+80h+Reserved], r15; Reserved
0x180023ce1  xor     r9d, r9d; LineNo
0x180023ce4  xor     r8d, r8d; FileName
0x180023ce7  xor     edx, edx; FunctionName
0x180023ce9  xor     ecx, ecx; Expression
0x180023ceb  call    cs:__imp__invoke_watson
0x180023cf2  call    cs:__imp_free
0x180023cf8  jmp     loc_180023C50
```

# ArgumentWriter::FormatArguments<ushort,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ulong const &)

- ea: `0x180024dec`
- end: `0x180024fab`
- name: `??$FormatArguments@GK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBGAEBK@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180024a58`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180004994`
- `0x180024dec`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024f98`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024f98`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024f9f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024f9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned long>(
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
  ArgumentWriter::FormatArguments<unsigned long,>(a1, v14[0], a3, a4);
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
0x180024dec  mov     [rsp-38h+arg_10], rbx
0x180024df1  push    rbp
0x180024df2  push    rsi
0x180024df3  push    rdi
0x180024df4  push    r12
0x180024df6  push    r13
0x180024df8  push    r14
0x180024dfa  push    r15
0x180024dfc  mov     rbp, rsp
0x180024dff  sub     rsp, 80h
0x180024e06  movaps  [rsp+80h+var_10], xmm6
0x180024e0b  mov     rax, cs:__security_cookie
0x180024e12  xor     rax, rsp
0x180024e15  mov     [rbp+var_18], rax
0x180024e19  mov     rbx, r9
0x180024e1c  mov     r14, r8
0x180024e1f  mov     rsi, rdx
0x180024e22  mov     rdi, rcx
0x180024e25  mov     [rbp+var_40], rcx
0x180024e29  mov     r12, [rbp+arg_20]
0x180024e2d  mov     r13, [rbp+arg_28]
0x180024e31  xor     r15d, r15d
0x180024e34  cmp     rdx, r8
0x180024e37  jnb     loc_180024ED4
0x180024e3d  lfence
0x180024e40  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180024e48  mov     eax, 25h ; '%'
0x180024e4d  xorps   xmm0, xmm0
0x180024e50  movups  xmmword ptr [rbp+Block], xmm0
0x180024e54  movdqu  [rbp+var_28], xmm6
0x180024e59  mov     word ptr [rbp+Block], r15w
0x180024e5e  movzx   r8d, word ptr [rsi]
0x180024e62  lea     r15, [rsi+2]
0x180024e66  mov     rsi, r15
0x180024e69  mov     [rbp+var_50], r15
0x180024e6d  cmp     r8w, ax
0x180024e71  jz      short loc_180024E83
0x180024e73  lea     edx, [rax-24h]
0x180024e76  mov     rcx, rbx; Src
0x180024e79  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024e7e  xor     r15d, r15d
0x180024e81  jmp     short loc_180024EC2
0x180024e83  cmp     r15, r14
0x180024e86  jz      short loc_180024EA4
0x180024e88  cmp     [r15], ax
0x180024e8c  jnz     short loc_180024EA4
0x180024e8e  mov     r8d, eax
0x180024e91  mov     edx, 1
0x180024e96  mov     rcx, rbx; Src
0x180024e99  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024e9e  lea     rsi, [r15+2]
0x180024ea2  jmp     short loc_180024E7E
0x180024ea4  lea     r9, [rbp+Block]
0x180024ea8  mov     r8, rbx
0x180024eab  mov     rdx, r14
0x180024eae  lea     rcx, [rbp+var_50]
0x180024eb2  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180024eb7  xor     r15d, r15d
0x180024eba  test    al, al
0x180024ebc  jnz     short loc_180024F2B
0x180024ebe  mov     rsi, [rbp+var_50]
0x180024ec2  lea     rcx, [rbp+Block]
0x180024ec6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024ecb  cmp     rsi, r14
0x180024ece  jb      loc_180024E48
0x180024ed4  xorps   xmm0, xmm0
0x180024ed7  movups  xmmword ptr [rdi], xmm0
0x180024eda  mov     [rdi+10h], r15
0x180024ede  mov     [rdi+18h], r15
0x180024ee2  mov     r8, [rbx+10h]
0x180024ee6  cmp     qword ptr [rbx+18h], 7
0x180024eeb  jbe     short loc_180024EF0
0x180024eed  mov     rbx, [rbx]
0x180024ef0  mov     rdx, rbx
0x180024ef3  mov     rcx, rdi
0x180024ef6  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180024efb  nop
0x180024efc  mov     rax, rdi
0x180024eff  mov     rcx, [rbp+var_18]
0x180024f03  xor     rcx, rsp; StackCookie
0x180024f06  call    __security_check_cookie
0x180024f0b  mov     rbx, [rsp+80h+arg_10]
0x180024f13  movaps  xmm6, [rsp+80h+var_10]
0x180024f18  add     rsp, 80h
0x180024f1f  pop     r15
0x180024f21  pop     r14
0x180024f23  pop     r13
0x180024f25  pop     r12
0x180024f27  pop     rdi
0x180024f28  pop     rsi
0x180024f29  pop     rbp
0x180024f2a  retn
0x180024f2b  lfence
0x180024f2e  movzx   r8d, word ptr [r12]
0x180024f33  lea     rdx, [rbp+Block]; Format
0x180024f37  mov     rcx, rbx; Src
0x180024f3a  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024f3f  mov     [rsp+80h+Reserved], r13
0x180024f44  mov     r9, rbx
0x180024f47  mov     r8, r14
0x180024f4a  mov     rdx, [rbp+var_50]
0x180024f4e  mov     rcx, rdi
0x180024f51  call    ??$FormatArguments@K$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBK@Z; ArgumentWriter::FormatArguments<ulong,>(wchar_t const *,wchar_t const *,std::wstring &,ulong const &)
0x180024f56  nop
0x180024f57  mov     rax, qword ptr [rbp+var_28+8]
0x180024f5b  cmp     rax, 7
0x180024f5f  jbe     short loc_180024EFC
0x180024f61  mov     rcx, [rbp+Block]; Block
0x180024f65  mov     rdx, rcx
0x180024f68  lea     rax, ds:2[rax*2]
0x180024f70  cmp     rax, 1000h
0x180024f76  jb      short loc_180024F9F
0x180024f78  mov     rcx, [rcx-8]
0x180024f7c  sub     rdx, rcx
0x180024f7f  lea     rax, [rdx-8]
0x180024f83  cmp     rax, 1Fh
0x180024f87  jbe     short loc_180024F9F
0x180024f89  mov     [rsp+80h+Reserved], r15; Reserved
0x180024f8e  xor     r9d, r9d; LineNo
0x180024f91  xor     r8d, r8d; FileName
0x180024f94  xor     edx, edx; FunctionName
0x180024f96  xor     ecx, ecx; Expression
0x180024f98  call    cs:__imp__invoke_watson
0x180024f9f  call    cs:__imp_free
0x180024fa5  jmp     loc_180024EFC
```

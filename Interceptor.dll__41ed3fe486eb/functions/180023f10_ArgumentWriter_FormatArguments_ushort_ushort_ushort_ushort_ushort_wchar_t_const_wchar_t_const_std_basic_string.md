# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)

- ea: `0x180023f10`
- end: `0x180024107`
- name: `??$FormatArguments@GGGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2222@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023930`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180023f10`
- `0x1800244b0`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800240f4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800240f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800240fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800240fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned __int16 *a9)
{
  unsigned __int16 *v11; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v14; // r8
  unsigned __int16 *v15; // r15
  __int64 v16; // r8
  void *v18; // rcx
  unsigned __int16 *v19; // [rsp+48h] [rbp-69h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-59h]
  __int64 v21; // [rsp+60h] [rbp-51h]
  __int64 v22; // [rsp+68h] [rbp-49h]
  unsigned __int64 v23; // [rsp+70h] [rbp-41h]
  void *Block[2]; // [rsp+78h] [rbp-39h] BYREF
  __m128i v25; // [rsp+88h] [rbp-29h]

  v11 = a2;
  v23 = a1;
  v22 = a7;
  v21 = a8;
  v20 = a9;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v16 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v16);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v25 = si128;
    LOWORD(Block[0]) = 0;
    v14 = *v11;
    v15 = v11 + 1;
    v11 = v15;
    v19 = v15;
    if ( v14 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v15 == a3 || *v15 != 37 )
      break;
    std::wstring::append(a4);
    v11 = v15 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v11 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v19, a3, a4, (__int64)Block) )
  {
    v11 = v19;
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short>(
    a1,
    v19,
    a3,
    a4,
    a6,
    v22,
    v21,
    v20);
  if ( v25.m128i_i64[1] > 7uLL )
  {
    v18 = Block[0];
    if ( (unsigned __int64)(2 * v25.m128i_i64[1] + 2) >= 0x1000 )
    {
      v18 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v18 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v18);
  }
  return a1;
}

```

## disassembly

```asm
0x180023f10  mov     rax, rsp
0x180023f13  mov     [rax+18h], rbx
0x180023f17  push    rbp
0x180023f18  push    rsi
0x180023f19  push    rdi
0x180023f1a  push    r12
0x180023f1c  push    r13
0x180023f1e  push    r14
0x180023f20  push    r15
0x180023f22  lea     rbp, [rax-3Fh]
0x180023f26  sub     rsp, 0B0h
0x180023f2d  movaps  xmmword ptr [rax-48h], xmm6
0x180023f31  mov     rax, cs:__security_cookie
0x180023f38  xor     rax, rsp
0x180023f3b  mov     [rbp+37h+var_50], rax
0x180023f3f  mov     rbx, r9
0x180023f42  mov     r14, r8
0x180023f45  mov     rsi, rdx
0x180023f48  mov     rdi, rcx
0x180023f4b  mov     [rbp+37h+var_78], rcx
0x180023f4f  mov     r12, [rbp+37h+arg_20]
0x180023f53  mov     r13, [rbp+37h+arg_28]
0x180023f57  mov     rax, [rbp+37h+arg_30]
0x180023f5b  mov     [rbp+37h+var_80], rax
0x180023f5f  mov     rax, [rbp+37h+arg_38]
0x180023f63  mov     [rbp+37h+var_88], rax
0x180023f67  mov     rax, [rbp+37h+arg_40]
0x180023f6e  mov     [rbp+37h+var_90], rax
0x180023f72  xor     r15d, r15d
0x180023f75  cmp     rdx, r8
0x180023f78  jnb     loc_180024015
0x180023f7e  lfence
0x180023f81  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180023f89  mov     eax, 25h ; '%'
0x180023f8e  xorps   xmm0, xmm0
0x180023f91  movups  xmmword ptr [rbp+37h+Block], xmm0
0x180023f95  movdqu  [rbp+37h+var_60], xmm6
0x180023f9a  mov     word ptr [rbp+37h+Block], r15w
0x180023f9f  movzx   r8d, word ptr [rsi]
0x180023fa3  lea     r15, [rsi+2]
0x180023fa7  mov     rsi, r15
0x180023faa  mov     [rbp+37h+var_A0], r15
0x180023fae  cmp     r8w, ax
0x180023fb2  jz      short loc_180023FC4
0x180023fb4  lea     edx, [rax-24h]
0x180023fb7  mov     rcx, rbx; Src
0x180023fba  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023fbf  xor     r15d, r15d
0x180023fc2  jmp     short loc_180024003
0x180023fc4  cmp     r15, r14
0x180023fc7  jz      short loc_180023FE5
0x180023fc9  cmp     [r15], ax
0x180023fcd  jnz     short loc_180023FE5
0x180023fcf  mov     r8d, eax
0x180023fd2  mov     edx, 1
0x180023fd7  mov     rcx, rbx; Src
0x180023fda  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023fdf  lea     rsi, [r15+2]
0x180023fe3  jmp     short loc_180023FBF
0x180023fe5  lea     r9, [rbp+37h+Block]
0x180023fe9  mov     r8, rbx
0x180023fec  mov     rdx, r14
0x180023fef  lea     rcx, [rbp+37h+var_A0]
0x180023ff3  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180023ff8  xor     r15d, r15d
0x180023ffb  test    al, al
0x180023ffd  jnz     short loc_18002406C
0x180023fff  mov     rsi, [rbp+37h+var_A0]
0x180024003  lea     rcx, [rbp+37h+Block]
0x180024007  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002400c  cmp     rsi, r14
0x18002400f  jb      loc_180023F89
0x180024015  xorps   xmm0, xmm0
0x180024018  movups  xmmword ptr [rdi], xmm0
0x18002401b  mov     [rdi+10h], r15
0x18002401f  mov     [rdi+18h], r15
0x180024023  mov     r8, [rbx+10h]
0x180024027  cmp     qword ptr [rbx+18h], 7
0x18002402c  jbe     short loc_180024031
0x18002402e  mov     rbx, [rbx]
0x180024031  mov     rdx, rbx
0x180024034  mov     rcx, rdi
0x180024037  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002403c  nop
0x18002403d  mov     rax, rdi
0x180024040  mov     rcx, [rbp+37h+var_50]
0x180024044  xor     rcx, rsp; StackCookie
0x180024047  call    __security_check_cookie
0x18002404c  lea     r11, [rsp+0E0h+var_30]
0x180024054  mov     rbx, [r11+50h]
0x180024058  movaps  xmm6, xmmword ptr [r11-10h]
0x18002405d  mov     rsp, r11
0x180024060  pop     r15
0x180024062  pop     r14
0x180024064  pop     r13
0x180024066  pop     r12
0x180024068  pop     rdi
0x180024069  pop     rsi
0x18002406a  pop     rbp
0x18002406b  retn
0x18002406c  lfence
0x18002406f  movzx   r8d, word ptr [r12]
0x180024074  lea     rdx, [rbp+37h+Block]; Format
0x180024078  mov     rcx, rbx; Src
0x18002407b  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024080  mov     rax, [rbp+37h+var_90]
0x180024084  mov     [rsp+0E0h+var_A8], rax
0x180024089  mov     rax, [rbp+37h+var_88]
0x18002408d  mov     [rsp+0E0h+var_B0], rax
0x180024092  mov     rax, [rbp+37h+var_80]
0x180024096  mov     [rsp+0E0h+var_B8], rax
0x18002409b  mov     [rsp+0E0h+Reserved], r13
0x1800240a0  mov     r9, rbx
0x1800240a3  mov     r8, r14
0x1800240a6  mov     rdx, [rbp+37h+var_A0]
0x1800240aa  mov     rcx, rdi
0x1800240ad  call    ??$FormatArguments@GGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG222@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &)
0x1800240b2  nop
0x1800240b3  mov     rax, qword ptr [rbp+37h+var_60+8]
0x1800240b7  cmp     rax, 7
0x1800240bb  jbe     short loc_18002403D
0x1800240bd  mov     rcx, [rbp+37h+Block]; Block
0x1800240c1  mov     rdx, rcx
0x1800240c4  lea     rax, ds:2[rax*2]
0x1800240cc  cmp     rax, 1000h
0x1800240d2  jb      short loc_1800240FB
0x1800240d4  mov     rcx, [rcx-8]
0x1800240d8  sub     rdx, rcx
0x1800240db  lea     rax, [rdx-8]
0x1800240df  cmp     rax, 1Fh
0x1800240e3  jbe     short loc_1800240FB
0x1800240e5  mov     [rsp+0E0h+Reserved], r15; Reserved
0x1800240ea  xor     r9d, r9d; LineNo
0x1800240ed  xor     r8d, r8d; FileName
0x1800240f0  xor     edx, edx; FunctionName
0x1800240f2  xor     ecx, ecx; Expression
0x1800240f4  call    cs:__imp__invoke_watson
0x1800240fb  call    cs:__imp_free
0x180024101  jmp     loc_18002403D
```

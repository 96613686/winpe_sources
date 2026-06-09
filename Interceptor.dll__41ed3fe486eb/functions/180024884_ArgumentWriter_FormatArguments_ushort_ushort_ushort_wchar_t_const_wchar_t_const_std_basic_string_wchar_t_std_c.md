# ArgumentWriter::FormatArguments<ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &)

- ea: `0x180024884`
- end: `0x180024a56`
- name: `??$FormatArguments@GGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800244b0`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180024884`
- `0x180024c2c`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024a43`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024a43`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024a4a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024a4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        unsigned __int16 *a7)
{
  unsigned __int16 *v9; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v12; // r8
  unsigned __int16 *v13; // r15
  __int64 v14; // r8
  void *v16; // rcx
  unsigned __int16 *v17[4]; // [rsp+38h] [rbp-51h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-31h] BYREF
  __m128i v19; // [rsp+68h] [rbp-21h]

  v9 = a2;
  v17[3] = (unsigned __int16 *)a1;
  v17[2] = a7;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v14 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v14);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v19 = si128;
    LOWORD(Block[0]) = 0;
    v12 = *v9;
    v13 = v9 + 1;
    v9 = v13;
    v17[0] = v13;
    if ( v12 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v13 == a3 || *v13 != 37 )
      break;
    std::wstring::append(a4);
    v9 = v13 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v9 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)v17, a3, a4, (__int64)Block) )
  {
    v9 = v17[0];
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned short>(a1, v17[0], a3, a4);
  if ( v19.m128i_i64[1] > 7uLL )
  {
    v16 = Block[0];
    if ( (unsigned __int64)(2 * v19.m128i_i64[1] + 2) >= 0x1000 )
    {
      v16 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v16 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v16);
  }
  return a1;
}

```

## disassembly

```asm
0x180024884  mov     rax, rsp
0x180024887  mov     [rax+18h], rbx
0x18002488b  push    rbp
0x18002488c  push    rsi
0x18002488d  push    rdi
0x18002488e  push    r12
0x180024890  push    r13
0x180024892  push    r14
0x180024894  push    r15
0x180024896  lea     rbp, [rax-47h]
0x18002489a  sub     rsp, 90h
0x1800248a1  movaps  xmmword ptr [rax-48h], xmm6
0x1800248a5  mov     rax, cs:__security_cookie
0x1800248ac  xor     rax, rsp
0x1800248af  mov     [rbp+3Fh+var_50], rax
0x1800248b3  mov     rbx, r9
0x1800248b6  mov     r14, r8
0x1800248b9  mov     rsi, rdx
0x1800248bc  mov     rdi, rcx
0x1800248bf  mov     [rbp+3Fh+var_78], rcx
0x1800248c3  mov     r12, [rbp+3Fh+arg_20]
0x1800248c7  mov     r13, [rbp+3Fh+arg_28]
0x1800248cb  mov     rax, [rbp+3Fh+arg_30]
0x1800248cf  mov     [rbp+3Fh+var_80], rax
0x1800248d3  xor     r15d, r15d
0x1800248d6  cmp     rdx, r8
0x1800248d9  jnb     loc_180024976
0x1800248df  lfence
0x1800248e2  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800248ea  mov     eax, 25h ; '%'
0x1800248ef  xorps   xmm0, xmm0
0x1800248f2  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x1800248f6  movdqu  [rbp+3Fh+var_60], xmm6
0x1800248fb  mov     word ptr [rbp+3Fh+Block], r15w
0x180024900  movzx   r8d, word ptr [rsi]
0x180024904  lea     r15, [rsi+2]
0x180024908  mov     rsi, r15
0x18002490b  mov     [rbp+3Fh+var_90], r15
0x18002490f  cmp     r8w, ax
0x180024913  jz      short loc_180024925
0x180024915  lea     edx, [rax-24h]
0x180024918  mov     rcx, rbx; Src
0x18002491b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024920  xor     r15d, r15d
0x180024923  jmp     short loc_180024964
0x180024925  cmp     r15, r14
0x180024928  jz      short loc_180024946
0x18002492a  cmp     [r15], ax
0x18002492e  jnz     short loc_180024946
0x180024930  mov     r8d, eax
0x180024933  mov     edx, 1
0x180024938  mov     rcx, rbx; Src
0x18002493b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024940  lea     rsi, [r15+2]
0x180024944  jmp     short loc_180024920
0x180024946  lea     r9, [rbp+3Fh+Block]
0x18002494a  mov     r8, rbx
0x18002494d  mov     rdx, r14
0x180024950  lea     rcx, [rbp+3Fh+var_90]
0x180024954  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180024959  xor     r15d, r15d
0x18002495c  test    al, al
0x18002495e  jnz     short loc_1800249CD
0x180024960  mov     rsi, [rbp+3Fh+var_90]
0x180024964  lea     rcx, [rbp+3Fh+Block]
0x180024968  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002496d  cmp     rsi, r14
0x180024970  jb      loc_1800248EA
0x180024976  xorps   xmm0, xmm0
0x180024979  movups  xmmword ptr [rdi], xmm0
0x18002497c  mov     [rdi+10h], r15
0x180024980  mov     [rdi+18h], r15
0x180024984  mov     r8, [rbx+10h]
0x180024988  cmp     qword ptr [rbx+18h], 7
0x18002498d  jbe     short loc_180024992
0x18002498f  mov     rbx, [rbx]
0x180024992  mov     rdx, rbx
0x180024995  mov     rcx, rdi
0x180024998  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002499d  nop
0x18002499e  mov     rax, rdi
0x1800249a1  mov     rcx, [rbp+3Fh+var_50]
0x1800249a5  xor     rcx, rsp; StackCookie
0x1800249a8  call    __security_check_cookie
0x1800249ad  lea     r11, [rsp+0C0h+var_30]
0x1800249b5  mov     rbx, [r11+50h]
0x1800249b9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800249be  mov     rsp, r11
0x1800249c1  pop     r15
0x1800249c3  pop     r14
0x1800249c5  pop     r13
0x1800249c7  pop     r12
0x1800249c9  pop     rdi
0x1800249ca  pop     rsi
0x1800249cb  pop     rbp
0x1800249cc  retn
0x1800249cd  lfence
0x1800249d0  movzx   r8d, word ptr [r12]
0x1800249d5  lea     rdx, [rbp+3Fh+Block]; Format
0x1800249d9  mov     rcx, rbx; Src
0x1800249dc  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x1800249e1  mov     rax, [rbp+3Fh+var_80]
0x1800249e5  mov     [rsp+0C0h+var_98], rax
0x1800249ea  mov     [rsp+0C0h+Reserved], r13
0x1800249ef  mov     r9, rbx
0x1800249f2  mov     r8, r14
0x1800249f5  mov     rdx, [rbp+3Fh+var_90]
0x1800249f9  mov     rcx, rdi
0x1800249fc  call    ??$FormatArguments@GG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2@Z; ArgumentWriter::FormatArguments<ushort,ushort>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &)
0x180024a01  nop
0x180024a02  mov     rax, qword ptr [rbp+3Fh+var_60+8]
0x180024a06  cmp     rax, 7
0x180024a0a  jbe     short loc_18002499E
0x180024a0c  mov     rcx, [rbp+3Fh+Block]; Block
0x180024a10  mov     rdx, rcx
0x180024a13  lea     rax, ds:2[rax*2]
0x180024a1b  cmp     rax, 1000h
0x180024a21  jb      short loc_180024A4A
0x180024a23  mov     rcx, [rcx-8]
0x180024a27  sub     rdx, rcx
0x180024a2a  lea     rax, [rdx-8]
0x180024a2e  cmp     rax, 1Fh
0x180024a32  jbe     short loc_180024A4A
0x180024a34  mov     [rsp+0C0h+Reserved], r15; Reserved
0x180024a39  xor     r9d, r9d; LineNo
0x180024a3c  xor     r8d, r8d; FileName
0x180024a3f  xor     edx, edx; FunctionName
0x180024a41  xor     ecx, ecx; Expression
0x180024a43  call    cs:__imp__invoke_watson
0x180024a4a  call    cs:__imp_free
0x180024a50  jmp     loc_18002499E
```

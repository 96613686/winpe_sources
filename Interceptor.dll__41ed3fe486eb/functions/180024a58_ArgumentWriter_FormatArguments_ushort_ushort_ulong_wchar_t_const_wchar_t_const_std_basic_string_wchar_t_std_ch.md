# ArgumentWriter::FormatArguments<ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ulong const &)

- ea: `0x180024a58`
- end: `0x180024c2a`
- name: `??$FormatArguments@GGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2AEBK@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800246a0`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180024a58`
- `0x180024dec`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024c17`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024c17`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024c1e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024c1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned long>(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned __int16 *v9; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v12; // r8
  unsigned __int16 *v13; // r15
  __int64 v14; // r8
  void *v16; // rcx
  unsigned __int16 *v17; // [rsp+38h] [rbp-51h] BYREF
  __int64 v18; // [rsp+48h] [rbp-41h]
  __int64 v19; // [rsp+50h] [rbp-39h]
  void *Block[2]; // [rsp+58h] [rbp-31h] BYREF
  __m128i v21; // [rsp+68h] [rbp-21h]

  v9 = a2;
  v19 = a1;
  v18 = a7;
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
    v21 = si128;
    LOWORD(Block[0]) = 0;
    v12 = *v9;
    v13 = v9 + 1;
    v9 = v13;
    v17 = v13;
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
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v17, a3, a4, (__int64)Block) )
  {
    v9 = v17;
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned long>(a1, v17, a3, a4, a6, v18);
  if ( v21.m128i_i64[1] > 7uLL )
  {
    v16 = Block[0];
    if ( (unsigned __int64)(2 * v21.m128i_i64[1] + 2) >= 0x1000 )
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
0x180024a58  mov     rax, rsp
0x180024a5b  mov     [rax+18h], rbx
0x180024a5f  push    rbp
0x180024a60  push    rsi
0x180024a61  push    rdi
0x180024a62  push    r12
0x180024a64  push    r13
0x180024a66  push    r14
0x180024a68  push    r15
0x180024a6a  lea     rbp, [rax-47h]
0x180024a6e  sub     rsp, 90h
0x180024a75  movaps  xmmword ptr [rax-48h], xmm6
0x180024a79  mov     rax, cs:__security_cookie
0x180024a80  xor     rax, rsp
0x180024a83  mov     [rbp+3Fh+var_50], rax
0x180024a87  mov     rbx, r9
0x180024a8a  mov     r14, r8
0x180024a8d  mov     rsi, rdx
0x180024a90  mov     rdi, rcx
0x180024a93  mov     [rbp+3Fh+var_78], rcx
0x180024a97  mov     r12, [rbp+3Fh+arg_20]
0x180024a9b  mov     r13, [rbp+3Fh+arg_28]
0x180024a9f  mov     rax, [rbp+3Fh+arg_30]
0x180024aa3  mov     [rbp+3Fh+var_80], rax
0x180024aa7  xor     r15d, r15d
0x180024aaa  cmp     rdx, r8
0x180024aad  jnb     loc_180024B4A
0x180024ab3  lfence
0x180024ab6  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180024abe  mov     eax, 25h ; '%'
0x180024ac3  xorps   xmm0, xmm0
0x180024ac6  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x180024aca  movdqu  [rbp+3Fh+var_60], xmm6
0x180024acf  mov     word ptr [rbp+3Fh+Block], r15w
0x180024ad4  movzx   r8d, word ptr [rsi]
0x180024ad8  lea     r15, [rsi+2]
0x180024adc  mov     rsi, r15
0x180024adf  mov     [rbp+3Fh+var_90], r15
0x180024ae3  cmp     r8w, ax
0x180024ae7  jz      short loc_180024AF9
0x180024ae9  lea     edx, [rax-24h]
0x180024aec  mov     rcx, rbx; Src
0x180024aef  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024af4  xor     r15d, r15d
0x180024af7  jmp     short loc_180024B38
0x180024af9  cmp     r15, r14
0x180024afc  jz      short loc_180024B1A
0x180024afe  cmp     [r15], ax
0x180024b02  jnz     short loc_180024B1A
0x180024b04  mov     r8d, eax
0x180024b07  mov     edx, 1
0x180024b0c  mov     rcx, rbx; Src
0x180024b0f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024b14  lea     rsi, [r15+2]
0x180024b18  jmp     short loc_180024AF4
0x180024b1a  lea     r9, [rbp+3Fh+Block]
0x180024b1e  mov     r8, rbx
0x180024b21  mov     rdx, r14
0x180024b24  lea     rcx, [rbp+3Fh+var_90]
0x180024b28  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180024b2d  xor     r15d, r15d
0x180024b30  test    al, al
0x180024b32  jnz     short loc_180024BA1
0x180024b34  mov     rsi, [rbp+3Fh+var_90]
0x180024b38  lea     rcx, [rbp+3Fh+Block]
0x180024b3c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024b41  cmp     rsi, r14
0x180024b44  jb      loc_180024ABE
0x180024b4a  xorps   xmm0, xmm0
0x180024b4d  movups  xmmword ptr [rdi], xmm0
0x180024b50  mov     [rdi+10h], r15
0x180024b54  mov     [rdi+18h], r15
0x180024b58  mov     r8, [rbx+10h]
0x180024b5c  cmp     qword ptr [rbx+18h], 7
0x180024b61  jbe     short loc_180024B66
0x180024b63  mov     rbx, [rbx]
0x180024b66  mov     rdx, rbx
0x180024b69  mov     rcx, rdi
0x180024b6c  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180024b71  nop
0x180024b72  mov     rax, rdi
0x180024b75  mov     rcx, [rbp+3Fh+var_50]
0x180024b79  xor     rcx, rsp; StackCookie
0x180024b7c  call    __security_check_cookie
0x180024b81  lea     r11, [rsp+0C0h+var_30]
0x180024b89  mov     rbx, [r11+50h]
0x180024b8d  movaps  xmm6, xmmword ptr [r11-10h]
0x180024b92  mov     rsp, r11
0x180024b95  pop     r15
0x180024b97  pop     r14
0x180024b99  pop     r13
0x180024b9b  pop     r12
0x180024b9d  pop     rdi
0x180024b9e  pop     rsi
0x180024b9f  pop     rbp
0x180024ba0  retn
0x180024ba1  lfence
0x180024ba4  movzx   r8d, word ptr [r12]
0x180024ba9  lea     rdx, [rbp+3Fh+Block]; Format
0x180024bad  mov     rcx, rbx; Src
0x180024bb0  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024bb5  mov     rax, [rbp+3Fh+var_80]
0x180024bb9  mov     [rsp+0C0h+var_98], rax
0x180024bbe  mov     [rsp+0C0h+Reserved], r13
0x180024bc3  mov     r9, rbx
0x180024bc6  mov     r8, r14
0x180024bc9  mov     rdx, [rbp+3Fh+var_90]
0x180024bcd  mov     rcx, rdi
0x180024bd0  call    ??$FormatArguments@GK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBGAEBK@Z; ArgumentWriter::FormatArguments<ushort,ulong>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ulong const &)
0x180024bd5  nop
0x180024bd6  mov     rax, qword ptr [rbp+3Fh+var_60+8]
0x180024bda  cmp     rax, 7
0x180024bde  jbe     short loc_180024B72
0x180024be0  mov     rcx, [rbp+3Fh+Block]; Block
0x180024be4  mov     rdx, rcx
0x180024be7  lea     rax, ds:2[rax*2]
0x180024bef  cmp     rax, 1000h
0x180024bf5  jb      short loc_180024C1E
0x180024bf7  mov     rcx, [rcx-8]
0x180024bfb  sub     rdx, rcx
0x180024bfe  lea     rax, [rdx-8]
0x180024c02  cmp     rax, 1Fh
0x180024c06  jbe     short loc_180024C1E
0x180024c08  mov     [rsp+0C0h+Reserved], r15; Reserved
0x180024c0d  xor     r9d, r9d; LineNo
0x180024c10  xor     r8d, r8d; FileName
0x180024c13  xor     edx, edx; FunctionName
0x180024c15  xor     ecx, ecx; Expression
0x180024c17  call    cs:__imp__invoke_watson
0x180024c1e  call    cs:__imp_free
0x180024c24  jmp     loc_180024B72
```

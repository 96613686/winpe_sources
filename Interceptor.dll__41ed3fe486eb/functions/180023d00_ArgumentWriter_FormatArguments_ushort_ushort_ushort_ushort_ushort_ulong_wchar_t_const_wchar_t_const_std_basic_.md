# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)

- ea: `0x180023d00`
- end: `0x180023f0f`
- name: `??$FormatArguments@GGGGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2222AEBK@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023280`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180023d00`
- `0x180024108`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023efc`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023efc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023f03`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023f03`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  unsigned __int16 *v12; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v15; // r8
  unsigned __int16 *v16; // r15
  __int64 v17; // r8
  void *v19; // rcx
  unsigned __int16 *v20; // [rsp+58h] [rbp-69h] BYREF
  __int64 v21; // [rsp+68h] [rbp-59h]
  __int64 v22; // [rsp+70h] [rbp-51h]
  __int64 v23; // [rsp+78h] [rbp-49h]
  __int64 v24; // [rsp+80h] [rbp-41h]
  __int64 v25; // [rsp+88h] [rbp-39h]
  void *Block[2]; // [rsp+90h] [rbp-31h] BYREF
  __m128i v27; // [rsp+A0h] [rbp-21h]

  v12 = a2;
  v25 = a1;
  v24 = a7;
  v23 = a8;
  v22 = a9;
  v21 = a10;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v17 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v17);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v27 = si128;
    LOWORD(Block[0]) = 0;
    v15 = *v12;
    v16 = v12 + 1;
    v12 = v16;
    v20 = v16;
    if ( v15 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v16 == a3 || *v16 != 37 )
      break;
    std::wstring::append(a4);
    v12 = v16 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v12 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v20, a3, a4, (__int64)Block) )
  {
    v12 = v20;
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
    a1,
    v20,
    a3,
    a4,
    a6,
    v24,
    v23,
    v22,
    v21);
  if ( v27.m128i_i64[1] > 7uLL )
  {
    v19 = Block[0];
    if ( (unsigned __int64)(2 * v27.m128i_i64[1] + 2) >= 0x1000 )
    {
      v19 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v19 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v19);
  }
  return a1;
}

```

## disassembly

```asm
0x180023d00  mov     rax, rsp
0x180023d03  mov     [rax+18h], rbx
0x180023d07  push    rbp
0x180023d08  push    rsi
0x180023d09  push    rdi
0x180023d0a  push    r12
0x180023d0c  push    r13
0x180023d0e  push    r14
0x180023d10  push    r15
0x180023d12  lea     rbp, [rax-3Fh]
0x180023d16  sub     rsp, 0C0h
0x180023d1d  movaps  xmmword ptr [rax-48h], xmm6
0x180023d21  mov     rax, cs:__security_cookie
0x180023d28  xor     rax, rsp
0x180023d2b  mov     [rbp+37h+var_48], rax
0x180023d2f  mov     rbx, r9
0x180023d32  mov     r14, r8
0x180023d35  mov     rsi, rdx
0x180023d38  mov     rdi, rcx
0x180023d3b  mov     [rbp+37h+var_70], rcx
0x180023d3f  mov     r12, [rbp+37h+arg_20]
0x180023d43  mov     r13, [rbp+37h+arg_28]
0x180023d47  mov     rax, [rbp+37h+arg_30]
0x180023d4b  mov     [rbp+37h+var_78], rax
0x180023d4f  mov     rax, [rbp+37h+arg_38]
0x180023d53  mov     [rbp+37h+var_80], rax
0x180023d57  mov     rax, [rbp+37h+arg_40]
0x180023d5e  mov     [rbp+37h+var_88], rax
0x180023d62  mov     rax, [rbp+37h+arg_48]
0x180023d69  mov     [rbp+37h+var_90], rax
0x180023d6d  xor     r15d, r15d
0x180023d70  cmp     rdx, r8
0x180023d73  jnb     loc_180023E10
0x180023d79  lfence
0x180023d7c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180023d84  mov     eax, 25h ; '%'
0x180023d89  xorps   xmm0, xmm0
0x180023d8c  movups  xmmword ptr [rbp+37h+Block], xmm0
0x180023d90  movdqu  [rbp+37h+var_58], xmm6
0x180023d95  mov     word ptr [rbp+37h+Block], r15w
0x180023d9a  movzx   r8d, word ptr [rsi]
0x180023d9e  lea     r15, [rsi+2]
0x180023da2  mov     rsi, r15
0x180023da5  mov     [rbp+37h+var_A0], r15
0x180023da9  cmp     r8w, ax
0x180023dad  jz      short loc_180023DBF
0x180023daf  lea     edx, [rax-24h]
0x180023db2  mov     rcx, rbx; Src
0x180023db5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023dba  xor     r15d, r15d
0x180023dbd  jmp     short loc_180023DFE
0x180023dbf  cmp     r15, r14
0x180023dc2  jz      short loc_180023DE0
0x180023dc4  cmp     [r15], ax
0x180023dc8  jnz     short loc_180023DE0
0x180023dca  mov     r8d, eax
0x180023dcd  mov     edx, 1
0x180023dd2  mov     rcx, rbx; Src
0x180023dd5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023dda  lea     rsi, [r15+2]
0x180023dde  jmp     short loc_180023DBA
0x180023de0  lea     r9, [rbp+37h+Block]
0x180023de4  mov     r8, rbx
0x180023de7  mov     rdx, r14
0x180023dea  lea     rcx, [rbp+37h+var_A0]
0x180023dee  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180023df3  xor     r15d, r15d
0x180023df6  test    al, al
0x180023df8  jnz     short loc_180023E67
0x180023dfa  mov     rsi, [rbp+37h+var_A0]
0x180023dfe  lea     rcx, [rbp+37h+Block]
0x180023e02  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023e07  cmp     rsi, r14
0x180023e0a  jb      loc_180023D84
0x180023e10  xorps   xmm0, xmm0
0x180023e13  movups  xmmword ptr [rdi], xmm0
0x180023e16  mov     [rdi+10h], r15
0x180023e1a  mov     [rdi+18h], r15
0x180023e1e  mov     r8, [rbx+10h]
0x180023e22  cmp     qword ptr [rbx+18h], 7
0x180023e27  jbe     short loc_180023E2C
0x180023e29  mov     rbx, [rbx]
0x180023e2c  mov     rdx, rbx
0x180023e2f  mov     rcx, rdi
0x180023e32  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180023e37  nop
0x180023e38  mov     rax, rdi
0x180023e3b  mov     rcx, [rbp+37h+var_48]
0x180023e3f  xor     rcx, rsp; StackCookie
0x180023e42  call    __security_check_cookie
0x180023e47  lea     r11, [rsp+0F0h+var_30]
0x180023e4f  mov     rbx, [r11+50h]
0x180023e53  movaps  xmm6, xmmword ptr [r11-10h]
0x180023e58  mov     rsp, r11
0x180023e5b  pop     r15
0x180023e5d  pop     r14
0x180023e5f  pop     r13
0x180023e61  pop     r12
0x180023e63  pop     rdi
0x180023e64  pop     rsi
0x180023e65  pop     rbp
0x180023e66  retn
0x180023e67  lfence
0x180023e6a  movzx   r8d, word ptr [r12]
0x180023e6f  lea     rdx, [rbp+37h+Block]; Format
0x180023e73  mov     rcx, rbx; Src
0x180023e76  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180023e7b  mov     rax, [rbp+37h+var_90]
0x180023e7f  mov     [rsp+0F0h+var_B0], rax
0x180023e84  mov     rax, [rbp+37h+var_88]
0x180023e88  mov     [rsp+0F0h+var_B8], rax
0x180023e8d  mov     rax, [rbp+37h+var_80]
0x180023e91  mov     [rsp+0F0h+var_C0], rax
0x180023e96  mov     rax, [rbp+37h+var_78]
0x180023e9a  mov     [rsp+0F0h+var_C8], rax
0x180023e9f  mov     [rsp+0F0h+Reserved], r13
0x180023ea4  mov     r9, rbx
0x180023ea7  mov     r8, r14
0x180023eaa  mov     rdx, [rbp+37h+var_A0]
0x180023eae  mov     rcx, rdi
0x180023eb1  call    ??$FormatArguments@GGGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG222AEBK@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)
0x180023eb6  nop
0x180023eb7  mov     rax, qword ptr [rbp+37h+var_58+8]
0x180023ebb  cmp     rax, 7
0x180023ebf  jbe     loc_180023E38
0x180023ec5  mov     rcx, [rbp+37h+Block]; Block
0x180023ec9  mov     rdx, rcx
0x180023ecc  lea     rax, ds:2[rax*2]
0x180023ed4  cmp     rax, 1000h
0x180023eda  jb      short loc_180023F03
0x180023edc  mov     rcx, [rcx-8]
0x180023ee0  sub     rdx, rcx
0x180023ee3  lea     rax, [rdx-8]
0x180023ee7  cmp     rax, 1Fh
0x180023eeb  jbe     short loc_180023F03
0x180023eed  mov     [rsp+0F0h+Reserved], r15; Reserved
0x180023ef2  xor     r9d, r9d; LineNo
0x180023ef5  xor     r8d, r8d; FileName
0x180023ef8  xor     edx, edx; FunctionName
0x180023efa  xor     ecx, ecx; Expression
0x180023efc  call    cs:__imp__invoke_watson
0x180023f03  call    cs:__imp_free
0x180023f09  jmp     loc_180023E38
```

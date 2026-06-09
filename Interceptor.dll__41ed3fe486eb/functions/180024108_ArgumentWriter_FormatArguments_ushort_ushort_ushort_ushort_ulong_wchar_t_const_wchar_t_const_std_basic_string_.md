# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)

- ea: `0x180024108`
- end: `0x1800242ff`
- name: `??$FormatArguments@GGGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG222AEBK@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023d00`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180024108`
- `0x1800246a0`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800242ec`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800242ec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800242f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800242f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  unsigned __int16 *v11; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v14; // r8
  unsigned __int16 *v15; // r15
  __int64 v16; // r8
  void *v18; // rcx
  unsigned __int16 *v19; // [rsp+48h] [rbp-69h] BYREF
  __int64 v20; // [rsp+58h] [rbp-59h]
  __int64 v21; // [rsp+60h] [rbp-51h]
  __int64 v22; // [rsp+68h] [rbp-49h]
  __int64 v23; // [rsp+70h] [rbp-41h]
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
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned long>(
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
0x180024108  mov     rax, rsp
0x18002410b  mov     [rax+18h], rbx
0x18002410f  push    rbp
0x180024110  push    rsi
0x180024111  push    rdi
0x180024112  push    r12
0x180024114  push    r13
0x180024116  push    r14
0x180024118  push    r15
0x18002411a  lea     rbp, [rax-3Fh]
0x18002411e  sub     rsp, 0B0h
0x180024125  movaps  xmmword ptr [rax-48h], xmm6
0x180024129  mov     rax, cs:__security_cookie
0x180024130  xor     rax, rsp
0x180024133  mov     [rbp+37h+var_50], rax
0x180024137  mov     rbx, r9
0x18002413a  mov     r14, r8
0x18002413d  mov     rsi, rdx
0x180024140  mov     rdi, rcx
0x180024143  mov     [rbp+37h+var_78], rcx
0x180024147  mov     r12, [rbp+37h+arg_20]
0x18002414b  mov     r13, [rbp+37h+arg_28]
0x18002414f  mov     rax, [rbp+37h+arg_30]
0x180024153  mov     [rbp+37h+var_80], rax
0x180024157  mov     rax, [rbp+37h+arg_38]
0x18002415b  mov     [rbp+37h+var_88], rax
0x18002415f  mov     rax, [rbp+37h+arg_40]
0x180024166  mov     [rbp+37h+var_90], rax
0x18002416a  xor     r15d, r15d
0x18002416d  cmp     rdx, r8
0x180024170  jnb     loc_18002420D
0x180024176  lfence
0x180024179  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180024181  mov     eax, 25h ; '%'
0x180024186  xorps   xmm0, xmm0
0x180024189  movups  xmmword ptr [rbp+37h+Block], xmm0
0x18002418d  movdqu  [rbp+37h+var_60], xmm6
0x180024192  mov     word ptr [rbp+37h+Block], r15w
0x180024197  movzx   r8d, word ptr [rsi]
0x18002419b  lea     r15, [rsi+2]
0x18002419f  mov     rsi, r15
0x1800241a2  mov     [rbp+37h+var_A0], r15
0x1800241a6  cmp     r8w, ax
0x1800241aa  jz      short loc_1800241BC
0x1800241ac  lea     edx, [rax-24h]
0x1800241af  mov     rcx, rbx; Src
0x1800241b2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800241b7  xor     r15d, r15d
0x1800241ba  jmp     short loc_1800241FB
0x1800241bc  cmp     r15, r14
0x1800241bf  jz      short loc_1800241DD
0x1800241c1  cmp     [r15], ax
0x1800241c5  jnz     short loc_1800241DD
0x1800241c7  mov     r8d, eax
0x1800241ca  mov     edx, 1
0x1800241cf  mov     rcx, rbx; Src
0x1800241d2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800241d7  lea     rsi, [r15+2]
0x1800241db  jmp     short loc_1800241B7
0x1800241dd  lea     r9, [rbp+37h+Block]
0x1800241e1  mov     r8, rbx
0x1800241e4  mov     rdx, r14
0x1800241e7  lea     rcx, [rbp+37h+var_A0]
0x1800241eb  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x1800241f0  xor     r15d, r15d
0x1800241f3  test    al, al
0x1800241f5  jnz     short loc_180024264
0x1800241f7  mov     rsi, [rbp+37h+var_A0]
0x1800241fb  lea     rcx, [rbp+37h+Block]
0x1800241ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024204  cmp     rsi, r14
0x180024207  jb      loc_180024181
0x18002420d  xorps   xmm0, xmm0
0x180024210  movups  xmmword ptr [rdi], xmm0
0x180024213  mov     [rdi+10h], r15
0x180024217  mov     [rdi+18h], r15
0x18002421b  mov     r8, [rbx+10h]
0x18002421f  cmp     qword ptr [rbx+18h], 7
0x180024224  jbe     short loc_180024229
0x180024226  mov     rbx, [rbx]
0x180024229  mov     rdx, rbx
0x18002422c  mov     rcx, rdi
0x18002422f  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180024234  nop
0x180024235  mov     rax, rdi
0x180024238  mov     rcx, [rbp+37h+var_50]
0x18002423c  xor     rcx, rsp; StackCookie
0x18002423f  call    __security_check_cookie
0x180024244  lea     r11, [rsp+0E0h+var_30]
0x18002424c  mov     rbx, [r11+50h]
0x180024250  movaps  xmm6, xmmword ptr [r11-10h]
0x180024255  mov     rsp, r11
0x180024258  pop     r15
0x18002425a  pop     r14
0x18002425c  pop     r13
0x18002425e  pop     r12
0x180024260  pop     rdi
0x180024261  pop     rsi
0x180024262  pop     rbp
0x180024263  retn
0x180024264  lfence
0x180024267  movzx   r8d, word ptr [r12]
0x18002426c  lea     rdx, [rbp+37h+Block]; Format
0x180024270  mov     rcx, rbx; Src
0x180024273  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024278  mov     rax, [rbp+37h+var_90]
0x18002427c  mov     [rsp+0E0h+var_A8], rax
0x180024281  mov     rax, [rbp+37h+var_88]
0x180024285  mov     [rsp+0E0h+var_B0], rax
0x18002428a  mov     rax, [rbp+37h+var_80]
0x18002428e  mov     [rsp+0E0h+var_B8], rax
0x180024293  mov     [rsp+0E0h+Reserved], r13
0x180024298  mov     r9, rbx
0x18002429b  mov     r8, r14
0x18002429e  mov     rdx, [rbp+37h+var_A0]
0x1800242a2  mov     rcx, rdi
0x1800242a5  call    ??$FormatArguments@GGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22AEBK@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ulong const &)
0x1800242aa  nop
0x1800242ab  mov     rax, qword ptr [rbp+37h+var_60+8]
0x1800242af  cmp     rax, 7
0x1800242b3  jbe     short loc_180024235
0x1800242b5  mov     rcx, [rbp+37h+Block]; Block
0x1800242b9  mov     rdx, rcx
0x1800242bc  lea     rax, ds:2[rax*2]
0x1800242c4  cmp     rax, 1000h
0x1800242ca  jb      short loc_1800242F3
0x1800242cc  mov     rcx, [rcx-8]
0x1800242d0  sub     rdx, rcx
0x1800242d3  lea     rax, [rdx-8]
0x1800242d7  cmp     rax, 1Fh
0x1800242db  jbe     short loc_1800242F3
0x1800242dd  mov     [rsp+0E0h+Reserved], r15; Reserved
0x1800242e2  xor     r9d, r9d; LineNo
0x1800242e5  xor     r8d, r8d; FileName
0x1800242e8  xor     edx, edx; FunctionName
0x1800242ea  xor     ecx, ecx; Expression
0x1800242ec  call    cs:__imp__invoke_watson
0x1800242f3  call    cs:__imp_free
0x1800242f9  jmp     loc_180024235
```

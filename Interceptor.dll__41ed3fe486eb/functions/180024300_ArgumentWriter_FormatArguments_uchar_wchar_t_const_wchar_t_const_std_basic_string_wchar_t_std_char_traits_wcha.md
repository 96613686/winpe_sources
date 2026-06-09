# ArgumentWriter::FormatArguments<uchar,>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,uchar const &)

- ea: `0x180024300`
- end: `0x1800244b0`
- name: `??$FormatArguments@E$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBE@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800234a8`

## callees

- `0x180001bc0`
- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180024300`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002449d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002449d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800244a4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800244a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned char,>(
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
0x180024300  mov     [rsp-38h+arg_10], rbx
0x180024305  push    rbp
0x180024306  push    rsi
0x180024307  push    rdi
0x180024308  push    r12
0x18002430a  push    r13
0x18002430c  push    r14
0x18002430e  push    r15
0x180024310  mov     rbp, rsp
0x180024313  sub     rsp, 80h
0x18002431a  movaps  [rsp+80h+var_10], xmm6
0x18002431f  mov     rax, cs:__security_cookie
0x180024326  xor     rax, rsp
0x180024329  mov     [rbp+var_18], rax
0x18002432d  mov     rbx, r9
0x180024330  mov     r14, r8
0x180024333  mov     rsi, rdx
0x180024336  mov     rdi, rcx
0x180024339  mov     [rbp+var_40], rcx
0x18002433d  mov     r12, [rbp+arg_20]
0x180024341  xor     r13d, r13d
0x180024344  cmp     rdx, r8
0x180024347  jnb     loc_1800243DE
0x18002434d  lfence
0x180024350  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180024358  mov     eax, 25h ; '%'
0x18002435d  xorps   xmm0, xmm0
0x180024360  movups  xmmword ptr [rbp+Block], xmm0
0x180024364  movdqu  [rbp+var_28], xmm6
0x180024369  mov     word ptr [rbp+Block], r13w
0x18002436e  movzx   r8d, word ptr [rsi]
0x180024372  lea     r15, [rsi+2]
0x180024376  mov     rsi, r15
0x180024379  mov     [rbp+var_50], r15
0x18002437d  cmp     r8w, ax
0x180024381  jz      short loc_180024390
0x180024383  lea     edx, [rax-24h]
0x180024386  mov     rcx, rbx; Src
0x180024389  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18002438e  jmp     short loc_1800243CC
0x180024390  cmp     r15, r14
0x180024393  jz      short loc_1800243B1
0x180024395  cmp     [r15], ax
0x180024399  jnz     short loc_1800243B1
0x18002439b  mov     r8d, eax
0x18002439e  mov     edx, 1
0x1800243a3  mov     rcx, rbx; Src
0x1800243a6  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800243ab  lea     rsi, [r15+2]
0x1800243af  jmp     short loc_1800243CC
0x1800243b1  lea     r9, [rbp+Block]
0x1800243b5  mov     r8, rbx
0x1800243b8  mov     rdx, r14
0x1800243bb  lea     rcx, [rbp+var_50]
0x1800243bf  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x1800243c4  test    al, al
0x1800243c6  jnz     short loc_180024435
0x1800243c8  mov     rsi, [rbp+var_50]
0x1800243cc  lea     rcx, [rbp+Block]
0x1800243d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800243d5  cmp     rsi, r14
0x1800243d8  jb      loc_180024358
0x1800243de  xorps   xmm0, xmm0
0x1800243e1  movups  xmmword ptr [rdi], xmm0
0x1800243e4  mov     [rdi+10h], r13
0x1800243e8  mov     [rdi+18h], r13
0x1800243ec  mov     r8, [rbx+10h]
0x1800243f0  cmp     qword ptr [rbx+18h], 7
0x1800243f5  jbe     short loc_1800243FA
0x1800243f7  mov     rbx, [rbx]
0x1800243fa  mov     rdx, rbx
0x1800243fd  mov     rcx, rdi
0x180024400  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180024405  nop
0x180024406  mov     rax, rdi
0x180024409  mov     rcx, [rbp+var_18]
0x18002440d  xor     rcx, rsp; StackCookie
0x180024410  call    __security_check_cookie
0x180024415  mov     rbx, [rsp+80h+arg_10]
0x18002441d  movaps  xmm6, [rsp+80h+var_10]
0x180024422  add     rsp, 80h
0x180024429  pop     r15
0x18002442b  pop     r14
0x18002442d  pop     r13
0x18002442f  pop     r12
0x180024431  pop     rdi
0x180024432  pop     rsi
0x180024433  pop     rbp
0x180024434  retn
0x180024435  lfence
0x180024438  movzx   r8d, byte ptr [r12]
0x18002443d  lea     rdx, [rbp+Block]; Format
0x180024441  mov     rcx, rbx; Src
0x180024444  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024449  mov     r9, rbx
0x18002444c  mov     r8, r14
0x18002444f  mov     rdx, [rbp+var_50]
0x180024453  mov     rcx, rdi
0x180024456  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x18002445b  nop
0x18002445c  mov     rax, qword ptr [rbp+var_28+8]
0x180024460  cmp     rax, 7
0x180024464  jbe     short loc_180024406
0x180024466  mov     rcx, [rbp+Block]; Block
0x18002446a  mov     rdx, rcx
0x18002446d  lea     rax, ds:2[rax*2]
0x180024475  cmp     rax, 1000h
0x18002447b  jb      short loc_1800244A4
0x18002447d  mov     rcx, [rcx-8]
0x180024481  sub     rdx, rcx
0x180024484  lea     rax, [rdx-8]
0x180024488  cmp     rax, 1Fh
0x18002448c  jbe     short loc_1800244A4
0x18002448e  mov     [rsp+80h+Reserved], r13; Reserved
0x180024493  xor     r9d, r9d; LineNo
0x180024496  xor     r8d, r8d; FileName
0x180024499  xor     edx, edx; FunctionName
0x18002449b  xor     ecx, ecx; Expression
0x18002449d  call    cs:__imp__invoke_watson
0x1800244a4  call    cs:__imp_free
0x1800244aa  jmp     loc_180024406
```

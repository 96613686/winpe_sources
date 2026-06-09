# ArgumentWriter::FormatArguments<ushort,>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &)

- ea: `0x180024fac`
- end: `0x18002515c`
- name: `??$FormatArguments@G$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180024c2c`

## callees

- `0x180001bc0`
- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180024fac`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180025149`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180025149`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180025150`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180025150`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,>(
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
0x180024fac  mov     [rsp-38h+arg_10], rbx
0x180024fb1  push    rbp
0x180024fb2  push    rsi
0x180024fb3  push    rdi
0x180024fb4  push    r12
0x180024fb6  push    r13
0x180024fb8  push    r14
0x180024fba  push    r15
0x180024fbc  mov     rbp, rsp
0x180024fbf  sub     rsp, 80h
0x180024fc6  movaps  [rsp+80h+var_10], xmm6
0x180024fcb  mov     rax, cs:__security_cookie
0x180024fd2  xor     rax, rsp
0x180024fd5  mov     [rbp+var_18], rax
0x180024fd9  mov     rbx, r9
0x180024fdc  mov     r14, r8
0x180024fdf  mov     rsi, rdx
0x180024fe2  mov     rdi, rcx
0x180024fe5  mov     [rbp+var_40], rcx
0x180024fe9  mov     r12, [rbp+arg_20]
0x180024fed  xor     r13d, r13d
0x180024ff0  cmp     rdx, r8
0x180024ff3  jnb     loc_18002508A
0x180024ff9  lfence
0x180024ffc  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180025004  mov     eax, 25h ; '%'
0x180025009  xorps   xmm0, xmm0
0x18002500c  movups  xmmword ptr [rbp+Block], xmm0
0x180025010  movdqu  [rbp+var_28], xmm6
0x180025015  mov     word ptr [rbp+Block], r13w
0x18002501a  movzx   r8d, word ptr [rsi]
0x18002501e  lea     r15, [rsi+2]
0x180025022  mov     rsi, r15
0x180025025  mov     [rbp+var_50], r15
0x180025029  cmp     r8w, ax
0x18002502d  jz      short loc_18002503C
0x18002502f  lea     edx, [rax-24h]
0x180025032  mov     rcx, rbx; Src
0x180025035  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18002503a  jmp     short loc_180025078
0x18002503c  cmp     r15, r14
0x18002503f  jz      short loc_18002505D
0x180025041  cmp     [r15], ax
0x180025045  jnz     short loc_18002505D
0x180025047  mov     r8d, eax
0x18002504a  mov     edx, 1
0x18002504f  mov     rcx, rbx; Src
0x180025052  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180025057  lea     rsi, [r15+2]
0x18002505b  jmp     short loc_180025078
0x18002505d  lea     r9, [rbp+Block]
0x180025061  mov     r8, rbx
0x180025064  mov     rdx, r14
0x180025067  lea     rcx, [rbp+var_50]
0x18002506b  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180025070  test    al, al
0x180025072  jnz     short loc_1800250E1
0x180025074  mov     rsi, [rbp+var_50]
0x180025078  lea     rcx, [rbp+Block]
0x18002507c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025081  cmp     rsi, r14
0x180025084  jb      loc_180025004
0x18002508a  xorps   xmm0, xmm0
0x18002508d  movups  xmmword ptr [rdi], xmm0
0x180025090  mov     [rdi+10h], r13
0x180025094  mov     [rdi+18h], r13
0x180025098  mov     r8, [rbx+10h]
0x18002509c  cmp     qword ptr [rbx+18h], 7
0x1800250a1  jbe     short loc_1800250A6
0x1800250a3  mov     rbx, [rbx]
0x1800250a6  mov     rdx, rbx
0x1800250a9  mov     rcx, rdi
0x1800250ac  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800250b1  nop
0x1800250b2  mov     rax, rdi
0x1800250b5  mov     rcx, [rbp+var_18]
0x1800250b9  xor     rcx, rsp; StackCookie
0x1800250bc  call    __security_check_cookie
0x1800250c1  mov     rbx, [rsp+80h+arg_10]
0x1800250c9  movaps  xmm6, [rsp+80h+var_10]
0x1800250ce  add     rsp, 80h
0x1800250d5  pop     r15
0x1800250d7  pop     r14
0x1800250d9  pop     r13
0x1800250db  pop     r12
0x1800250dd  pop     rdi
0x1800250de  pop     rsi
0x1800250df  pop     rbp
0x1800250e0  retn
0x1800250e1  lfence
0x1800250e4  movzx   r8d, word ptr [r12]
0x1800250e9  lea     rdx, [rbp+Block]; Format
0x1800250ed  mov     rcx, rbx; Src
0x1800250f0  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x1800250f5  mov     r9, rbx
0x1800250f8  mov     r8, r14
0x1800250fb  mov     rdx, [rbp+var_50]
0x1800250ff  mov     rcx, rdi
0x180025102  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x180025107  nop
0x180025108  mov     rax, qword ptr [rbp+var_28+8]
0x18002510c  cmp     rax, 7
0x180025110  jbe     short loc_1800250B2
0x180025112  mov     rcx, [rbp+Block]; Block
0x180025116  mov     rdx, rcx
0x180025119  lea     rax, ds:2[rax*2]
0x180025121  cmp     rax, 1000h
0x180025127  jb      short loc_180025150
0x180025129  mov     rcx, [rcx-8]
0x18002512d  sub     rdx, rcx
0x180025130  lea     rax, [rdx-8]
0x180025134  cmp     rax, 1Fh
0x180025138  jbe     short loc_180025150
0x18002513a  mov     [rsp+80h+Reserved], r13; Reserved
0x18002513f  xor     r9d, r9d; LineNo
0x180025142  xor     r8d, r8d; FileName
0x180025145  xor     edx, edx; FunctionName
0x180025147  xor     ecx, ecx; Expression
0x180025149  call    cs:__imp__invoke_watson
0x180025150  call    cs:__imp_free
0x180025156  jmp     loc_1800250B2
```

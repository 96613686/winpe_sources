# ArgumentWriter::FormatArguments<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180004b58`
- end: `0x180004d84`
- name: `??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@@Z`
- size: `556`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1800048a8`
- `0x180005eb0`
- `0x180023b40`

## callees

- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180004b58`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004cb4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004d6e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004cb4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004d6e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004d78`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004d78`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<std::wstring,>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  unsigned __int16 *v7; // r15
  _QWORD *v9; // rsi
  unsigned __int16 v10; // r8
  unsigned __int16 *v11; // r13
  __int64 v12; // r8
  void **v14; // rax
  char *v15; // r15
  unsigned __int64 v16; // r12
  __int64 v17; // r14
  char *v18; // rcx
  unsigned __int16 *v19; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-40h]
  unsigned __int64 v21; // [rsp+48h] [rbp-38h]
  void *Block[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+60h] [rbp-20h]
  unsigned __int64 v24; // [rsp+68h] [rbp-18h]

  v20 = a3;
  v7 = a2;
  v9 = a5;
  v21 = a1;
  if ( a2 >= a3 )
  {
LABEL_11:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v12 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v12);
    return a1;
  }
  _mm_lfence();
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v23 = 0;
    v24 = 7;
    LOWORD(Block[0]) = 0;
    v10 = *v7;
    v11 = v7 + 1;
    v7 = v11;
    v19 = v11;
    if ( v10 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v7 >= a3 )
      goto LABEL_11;
  }
  if ( v11 != a3 && *v11 == 37 )
  {
    std::wstring::append(a4);
    v7 = v11 + 1;
    goto LABEL_10;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v19, a3, a4, (__int64)Block) )
  {
    v7 = v19;
    goto LABEL_10;
  }
  if ( a5[3] > 7u )
    v9 = (_QWORD *)*a5;
  if ( !v23 )
    _invoke_watson(0, 0, 0, 0, 0);
  _mm_lfence();
  v14 = Block;
  v15 = (char *)Block[0];
  v16 = v24;
  if ( v24 > 7 )
    v14 = (void **)Block[0];
  if ( ((*((_WORD *)v14 + v23 - 1) - 83) & 0xFFDF) == 0 && v9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v9 + v17) );
  }
  std::wstring::append(a4);
  ArgumentWriter::FormatArguments(a1, v19, v20, a4);
  if ( v16 > 7 )
  {
    v18 = v15;
    if ( 2 * v16 + 2 >= 0x1000 )
    {
      v15 = (char *)*((_QWORD *)v15 - 1);
      if ( (unsigned __int64)(v18 - v15 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v15);
  }
  return a1;
}

```

## disassembly

```asm
0x180004b58  mov     [rsp-38h+arg_10], rbx
0x180004b5d  push    rbp
0x180004b5e  push    rsi
0x180004b5f  push    rdi
0x180004b60  push    r12
0x180004b62  push    r13
0x180004b64  push    r14
0x180004b66  push    r15
0x180004b68  mov     rbp, rsp
0x180004b6b  sub     rsp, 80h
0x180004b72  mov     rax, cs:__security_cookie
0x180004b79  xor     rax, rsp
0x180004b7c  mov     [rbp+var_10], rax
0x180004b80  mov     rbx, r9
0x180004b83  mov     r12, r8
0x180004b86  mov     [rbp+var_40], r8
0x180004b8a  mov     r15, rdx
0x180004b8d  mov     rdi, rcx
0x180004b90  mov     rsi, [rbp+arg_20]
0x180004b94  mov     [rbp+var_38], rcx
0x180004b98  xor     r13d, r13d
0x180004b9b  cmp     rdx, r8
0x180004b9e  jnb     loc_180004C3C
0x180004ba4  lfence
0x180004ba7  lea     r14d, [r13+25h]
0x180004bab  xorps   xmm0, xmm0
0x180004bae  movups  xmmword ptr [rbp+Block], xmm0
0x180004bb2  mov     [rbp+var_20], r13
0x180004bb6  mov     [rbp+var_18], 7
0x180004bbe  mov     word ptr [rbp+Block], r13w
0x180004bc3  movzx   r8d, word ptr [r15]
0x180004bc7  lea     r13, [r15+2]
0x180004bcb  mov     r15, r13
0x180004bce  mov     [rbp+var_50], r13
0x180004bd2  cmp     r8w, r14w
0x180004bd6  jz      short loc_180004BEA
0x180004bd8  mov     edx, 1
0x180004bdd  mov     rcx, rbx; Src
0x180004be0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180004be5  xor     r13d, r13d
0x180004be8  jmp     short loc_180004C2A
0x180004bea  cmp     r13, r12
0x180004bed  jz      short loc_180004C0C
0x180004bef  cmp     [r13+0], r14w
0x180004bf4  jnz     short loc_180004C0C
0x180004bf6  mov     r8d, r14d
0x180004bf9  mov     edx, 1
0x180004bfe  mov     rcx, rbx; Src
0x180004c01  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180004c06  lea     r15, [r13+2]
0x180004c0a  jmp     short loc_180004BE5
0x180004c0c  lea     r9, [rbp+Block]
0x180004c10  mov     r8, rbx
0x180004c13  mov     rdx, r12
0x180004c16  lea     rcx, [rbp+var_50]
0x180004c1a  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180004c1f  xor     r13d, r13d
0x180004c22  test    al, al
0x180004c24  jnz     short loc_180004C8E
0x180004c26  mov     r15, [rbp+var_50]
0x180004c2a  lea     rcx, [rbp+Block]
0x180004c2e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180004c33  cmp     r15, r12
0x180004c36  jb      loc_180004BAB
0x180004c3c  xorps   xmm0, xmm0
0x180004c3f  movups  xmmword ptr [rdi], xmm0
0x180004c42  mov     [rdi+10h], r13
0x180004c46  mov     [rdi+18h], r13
0x180004c4a  mov     r8, [rbx+10h]
0x180004c4e  cmp     qword ptr [rbx+18h], 7
0x180004c53  jbe     short loc_180004C58
0x180004c55  mov     rbx, [rbx]
0x180004c58  mov     rdx, rbx
0x180004c5b  mov     rcx, rdi
0x180004c5e  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004c63  nop
0x180004c64  mov     rax, rdi
0x180004c67  mov     rcx, [rbp+var_10]
0x180004c6b  xor     rcx, rsp; StackCookie
0x180004c6e  call    __security_check_cookie
0x180004c73  mov     rbx, [rsp+80h+arg_10]
0x180004c7b  add     rsp, 80h
0x180004c82  pop     r15
0x180004c84  pop     r14
0x180004c86  pop     r13
0x180004c88  pop     r12
0x180004c8a  pop     rdi
0x180004c8b  pop     rsi
0x180004c8c  pop     rbp
0x180004c8d  retn
0x180004c8e  cmp     qword ptr [rsi+18h], 7
0x180004c93  jbe     short loc_180004C98
0x180004c95  mov     rsi, [rsi]
0x180004c98  mov     rax, [rbp+var_20]
0x180004c9c  lea     rcx, [rax-1]
0x180004ca0  cmp     rcx, rax
0x180004ca3  jbe     short loc_180004CBB
0x180004ca5  mov     [rsp+80h+Reserved], r13; Reserved
0x180004caa  xor     r9d, r9d; LineNo
0x180004cad  xor     r8d, r8d; FileName
0x180004cb0  xor     edx, edx; FunctionName
0x180004cb2  xor     ecx, ecx; Expression
0x180004cb4  call    cs:__imp__invoke_watson
0x180004cbb  lfence
0x180004cbe  lea     rax, [rbp+Block]
0x180004cc2  mov     r15, [rbp+Block]
0x180004cc6  mov     r12, [rbp+var_18]
0x180004cca  cmp     r12, 7
0x180004cce  cmova   rax, r15
0x180004cd2  movzx   eax, word ptr [rax+rcx*2]
0x180004cd6  sub     ax, 53h ; 'S'
0x180004cda  mov     ecx, 0FFDFh
0x180004cdf  test    cx, ax
0x180004ce2  jz      short loc_180004CED
0x180004ce4  lea     rsi, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x180004ceb  jmp     short loc_180004D0F
0x180004ced  test    rsi, rsi
0x180004cf0  jnz     short loc_180004D01
0x180004cf2  lea     rsi, aNull_1; "<NULL>"
0x180004cf9  mov     r14d, 6
0x180004cff  jmp     short loc_180004D0F
0x180004d01  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004d05  inc     r14
0x180004d08  cmp     [rsi+r14*2], r13w
0x180004d0d  jnz     short loc_180004D05
0x180004d0f  mov     r8, r14
0x180004d12  mov     rdx, rsi
0x180004d15  mov     rcx, rbx; Src
0x180004d18  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180004d1d  mov     r9, rbx
0x180004d20  mov     r8, [rbp+var_40]
0x180004d24  mov     rdx, [rbp+var_50]
0x180004d28  mov     rcx, rdi
0x180004d2b  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x180004d30  nop
0x180004d31  cmp     r12, 7
0x180004d35  jbe     loc_180004C64
0x180004d3b  mov     rcx, r15
0x180004d3e  lea     rax, ds:2[r12*2]
0x180004d46  cmp     rax, 1000h
0x180004d4c  jb      short loc_180004D75
0x180004d4e  mov     r15, [r15-8]
0x180004d52  sub     rcx, r15
0x180004d55  lea     rax, [rcx-8]
0x180004d59  cmp     rax, 1Fh
0x180004d5d  jbe     short loc_180004D75
0x180004d5f  mov     [rsp+80h+Reserved], r13; Reserved
0x180004d64  xor     r9d, r9d; LineNo
0x180004d67  xor     r8d, r8d; FileName
0x180004d6a  xor     edx, edx; FunctionName
0x180004d6c  xor     ecx, ecx; Expression
0x180004d6e  call    cs:__imp__invoke_watson
0x180004d75  mov     rcx, r15; Block
0x180004d78  call    cs:__imp_free
0x180004d7e  jmp     loc_180004C64
```

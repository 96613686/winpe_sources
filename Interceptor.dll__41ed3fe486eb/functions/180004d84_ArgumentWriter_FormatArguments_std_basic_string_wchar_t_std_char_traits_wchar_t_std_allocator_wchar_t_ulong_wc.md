# ArgumentWriter::FormatArguments<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &)

- ea: `0x180004d84`
- end: `0x180004fc1`
- name: `??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@AEBK@Z`
- size: `573`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180004fd0`
- `0x180021f80`

## callees

- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180004994`
- `0x180004d84`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004ee8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004fab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004ee8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004fab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004fb5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<std::wstring,unsigned long>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        _QWORD *a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v8; // r15
  _QWORD *v10; // rsi
  unsigned __int16 v11; // r8
  unsigned __int16 *v12; // r13
  __int64 v13; // r8
  void **v15; // rax
  char *v16; // r15
  unsigned __int64 v17; // r12
  __int64 v18; // r14
  char *v19; // rcx
  unsigned __int16 *v20[3]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-38h]
  unsigned __int64 v22; // [rsp+50h] [rbp-30h]
  void *Block[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+68h] [rbp-18h]
  unsigned __int64 v25; // [rsp+70h] [rbp-10h]

  v21 = a3;
  v8 = a2;
  v10 = a5;
  v22 = a1;
  v20[2] = a6;
  if ( a2 >= a3 )
  {
LABEL_11:
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
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v24 = 0;
    v25 = 7;
    LOWORD(Block[0]) = 0;
    v11 = *v8;
    v12 = v8 + 1;
    v8 = v12;
    v20[0] = v12;
    if ( v11 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v8 >= a3 )
      goto LABEL_11;
  }
  if ( v12 != a3 && *v12 == 37 )
  {
    std::wstring::append(a4);
    v8 = v12 + 1;
    goto LABEL_10;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)v20, a3, a4, (__int64)Block) )
  {
    v8 = v20[0];
    goto LABEL_10;
  }
  if ( a5[3] > 7u )
    v10 = (_QWORD *)*a5;
  if ( !v24 )
    _invoke_watson(0, 0, 0, 0, 0);
  _mm_lfence();
  v15 = Block;
  v16 = (char *)Block[0];
  v17 = v25;
  if ( v25 > 7 )
    v15 = (void **)Block[0];
  if ( ((*((_WORD *)v15 + v24 - 1) - 83) & 0xFFDF) == 0 && v10 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v10 + v18) );
  }
  std::wstring::append(a4);
  ArgumentWriter::FormatArguments<unsigned long,>(a1, v20[0], v21, a4);
  if ( v17 > 7 )
  {
    v19 = v16;
    if ( 2 * v17 + 2 >= 0x1000 )
    {
      v16 = (char *)*((_QWORD *)v16 - 1);
      if ( (unsigned __int64)(v19 - v16 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v16);
  }
  return a1;
}

```

## disassembly

```asm
0x180004d84  mov     [rsp-38h+arg_10], rbx
0x180004d89  push    rbp
0x180004d8a  push    rsi
0x180004d8b  push    rdi
0x180004d8c  push    r12
0x180004d8e  push    r13
0x180004d90  push    r14
0x180004d92  push    r15
0x180004d94  mov     rbp, rsp
0x180004d97  sub     rsp, 80h
0x180004d9e  mov     rax, cs:__security_cookie
0x180004da5  xor     rax, rsp
0x180004da8  mov     [rbp+var_8], rax
0x180004dac  mov     rbx, r9
0x180004daf  mov     r12, r8
0x180004db2  mov     [rbp+var_38], r8
0x180004db6  mov     r15, rdx
0x180004db9  mov     rdi, rcx
0x180004dbc  mov     rsi, [rbp+arg_20]
0x180004dc0  mov     [rbp+var_30], rcx
0x180004dc4  mov     rax, [rbp+arg_28]
0x180004dc8  mov     [rbp+var_40], rax
0x180004dcc  xor     r13d, r13d
0x180004dcf  cmp     rdx, r8
0x180004dd2  jnb     loc_180004E70
0x180004dd8  lfence
0x180004ddb  lea     r14d, [r13+25h]
0x180004ddf  xorps   xmm0, xmm0
0x180004de2  movups  xmmword ptr [rbp+Block], xmm0
0x180004de6  mov     [rbp+var_18], r13
0x180004dea  mov     [rbp+var_10], 7
0x180004df2  mov     word ptr [rbp+Block], r13w
0x180004df7  movzx   r8d, word ptr [r15]
0x180004dfb  lea     r13, [r15+2]
0x180004dff  mov     r15, r13
0x180004e02  mov     [rbp+var_50], r13
0x180004e06  cmp     r8w, r14w
0x180004e0a  jz      short loc_180004E1E
0x180004e0c  mov     edx, 1
0x180004e11  mov     rcx, rbx; Src
0x180004e14  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180004e19  xor     r13d, r13d
0x180004e1c  jmp     short loc_180004E5E
0x180004e1e  cmp     r13, r12
0x180004e21  jz      short loc_180004E40
0x180004e23  cmp     [r13+0], r14w
0x180004e28  jnz     short loc_180004E40
0x180004e2a  mov     r8d, r14d
0x180004e2d  mov     edx, 1
0x180004e32  mov     rcx, rbx; Src
0x180004e35  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180004e3a  lea     r15, [r13+2]
0x180004e3e  jmp     short loc_180004E19
0x180004e40  lea     r9, [rbp+Block]
0x180004e44  mov     r8, rbx
0x180004e47  mov     rdx, r12
0x180004e4a  lea     rcx, [rbp+var_50]
0x180004e4e  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180004e53  xor     r13d, r13d
0x180004e56  test    al, al
0x180004e58  jnz     short loc_180004EC2
0x180004e5a  mov     r15, [rbp+var_50]
0x180004e5e  lea     rcx, [rbp+Block]
0x180004e62  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180004e67  cmp     r15, r12
0x180004e6a  jb      loc_180004DDF
0x180004e70  xorps   xmm0, xmm0
0x180004e73  movups  xmmword ptr [rdi], xmm0
0x180004e76  mov     [rdi+10h], r13
0x180004e7a  mov     [rdi+18h], r13
0x180004e7e  mov     r8, [rbx+10h]
0x180004e82  cmp     qword ptr [rbx+18h], 7
0x180004e87  jbe     short loc_180004E8C
0x180004e89  mov     rbx, [rbx]
0x180004e8c  mov     rdx, rbx
0x180004e8f  mov     rcx, rdi
0x180004e92  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004e97  nop
0x180004e98  mov     rax, rdi
0x180004e9b  mov     rcx, [rbp+var_8]
0x180004e9f  xor     rcx, rsp; StackCookie
0x180004ea2  call    __security_check_cookie
0x180004ea7  mov     rbx, [rsp+80h+arg_10]
0x180004eaf  add     rsp, 80h
0x180004eb6  pop     r15
0x180004eb8  pop     r14
0x180004eba  pop     r13
0x180004ebc  pop     r12
0x180004ebe  pop     rdi
0x180004ebf  pop     rsi
0x180004ec0  pop     rbp
0x180004ec1  retn
0x180004ec2  cmp     qword ptr [rsi+18h], 7
0x180004ec7  jbe     short loc_180004ECC
0x180004ec9  mov     rsi, [rsi]
0x180004ecc  mov     rax, [rbp+var_18]
0x180004ed0  lea     rcx, [rax-1]
0x180004ed4  cmp     rcx, rax
0x180004ed7  jbe     short loc_180004EEF
0x180004ed9  mov     [rsp+80h+Reserved], r13; Reserved
0x180004ede  xor     r9d, r9d; LineNo
0x180004ee1  xor     r8d, r8d; FileName
0x180004ee4  xor     edx, edx; FunctionName
0x180004ee6  xor     ecx, ecx; Expression
0x180004ee8  call    cs:__imp__invoke_watson
0x180004eef  lfence
0x180004ef2  lea     rax, [rbp+Block]
0x180004ef6  mov     r15, [rbp+Block]
0x180004efa  mov     r12, [rbp+var_10]
0x180004efe  cmp     r12, 7
0x180004f02  cmova   rax, r15
0x180004f06  movzx   eax, word ptr [rax+rcx*2]
0x180004f0a  sub     ax, 53h ; 'S'
0x180004f0e  mov     ecx, 0FFDFh
0x180004f13  test    cx, ax
0x180004f16  jz      short loc_180004F21
0x180004f18  lea     rsi, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x180004f1f  jmp     short loc_180004F43
0x180004f21  test    rsi, rsi
0x180004f24  jnz     short loc_180004F35
0x180004f26  lea     rsi, aNull_1; "<NULL>"
0x180004f2d  mov     r14d, 6
0x180004f33  jmp     short loc_180004F43
0x180004f35  or      r14, 0FFFFFFFFFFFFFFFFh
0x180004f39  inc     r14
0x180004f3c  cmp     [rsi+r14*2], r13w
0x180004f41  jnz     short loc_180004F39
0x180004f43  mov     r8, r14
0x180004f46  mov     rdx, rsi
0x180004f49  mov     rcx, rbx; Src
0x180004f4c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180004f51  mov     rax, [rbp+var_40]
0x180004f55  mov     [rsp+80h+Reserved], rax
0x180004f5a  mov     r9, rbx
0x180004f5d  mov     r8, [rbp+var_38]
0x180004f61  mov     rdx, [rbp+var_50]
0x180004f65  mov     rcx, rdi
0x180004f68  call    ??$FormatArguments@K$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBK@Z; ArgumentWriter::FormatArguments<ulong,>(wchar_t const *,wchar_t const *,std::wstring &,ulong const &)
0x180004f6d  nop
0x180004f6e  cmp     r12, 7
0x180004f72  jbe     loc_180004E98
0x180004f78  mov     rcx, r15
0x180004f7b  lea     rax, ds:2[r12*2]
0x180004f83  cmp     rax, 1000h
0x180004f89  jb      short loc_180004FB2
0x180004f8b  mov     r15, [r15-8]
0x180004f8f  sub     rcx, r15
0x180004f92  lea     rax, [rcx-8]
0x180004f96  cmp     rax, 1Fh
0x180004f9a  jbe     short loc_180004FB2
0x180004f9c  mov     [rsp+80h+Reserved], r13; Reserved
0x180004fa1  xor     r9d, r9d; LineNo
0x180004fa4  xor     r8d, r8d; FileName
0x180004fa7  xor     edx, edx; FunctionName
0x180004fa9  xor     ecx, ecx; Expression
0x180004fab  call    cs:__imp__invoke_watson
0x180004fb2  mov     rcx, r15; Block
0x180004fb5  call    cs:__imp_free
0x180004fbb  jmp     loc_180004E98
```

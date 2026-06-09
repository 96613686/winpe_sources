# ArgumentWriter::FormatArguments<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180005eb0`
- end: `0x1800060f3`
- name: `??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@2@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800060f4`

## callees

- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x18000465c`
- `0x180004b58`
- `0x180005eb0`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000601a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800060dd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000601a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800060dd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800060e7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800060e7`

## string_xrefs

- `0x180005efa`: `ORegistryKey.GetValue failure: Cannot get registry %s value %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<std::wstring,std::wstring>(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6)
{
  _QWORD *v9; // rsi
  const wchar_t *v10; // r15
  wchar_t v11; // r8
  const wchar_t *v12; // r13
  __int64 v13; // r8
  void **v15; // rax
  char *v16; // r15
  unsigned __int64 v17; // r12
  __int64 v18; // r14
  char *v19; // rcx
  const wchar_t *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+48h] [rbp-31h]
  const wchar_t *v22; // [rsp+50h] [rbp-29h]
  __int64 v23; // [rsp+58h] [rbp-21h]
  void *Block[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v25; // [rsp+70h] [rbp-9h]
  unsigned __int64 v26; // [rsp+78h] [rbp-1h]

  v22 = a3;
  v9 = a5;
  v23 = a1;
  v21 = a6;
  v10 = L"ORegistryKey.GetValue failure: Cannot get registry %s value %s";
  if ( L"ORegistryKey.GetValue failure: Cannot get registry %s value %s" >= a3 )
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
    v25 = 0;
    v26 = 7;
    LOWORD(Block[0]) = 0;
    v11 = *v10;
    v12 = v10 + 1;
    v10 = v12;
    v20 = v12;
    if ( v11 == 37 )
      break;
    std::wstring::append(a4);
LABEL_10:
    std::wstring::_Tidy_deallocate(Block);
    if ( v10 >= a3 )
      goto LABEL_11;
  }
  if ( v12 != a3 && *v12 == 37 )
  {
    std::wstring::append(a4);
    v10 = v12 + 1;
    goto LABEL_10;
  }
  if ( !(unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(&v20, a3, a4, Block) )
  {
    v10 = v20;
    goto LABEL_10;
  }
  if ( a5[3] > 7u )
    v9 = (_QWORD *)*a5;
  if ( !v25 )
    _invoke_watson(0, 0, 0, 0, 0);
  _mm_lfence();
  v15 = Block;
  v16 = (char *)Block[0];
  v17 = v26;
  if ( v26 > 7 )
    v15 = (void **)Block[0];
  if ( ((*((_WORD *)v15 + v25 - 1) - 83) & 0xFFDF) == 0 && v9 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v9 + v18) );
  }
  std::wstring::append(a4);
  ArgumentWriter::FormatArguments<std::wstring,>(a1, v20, v22, a4, v21);
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
0x180005eb0  mov     [rsp-8+arg_8], rbx
0x180005eb5  push    rbp
0x180005eb6  push    rsi
0x180005eb7  push    rdi
0x180005eb8  push    r12
0x180005eba  push    r13
0x180005ebc  push    r14
0x180005ebe  push    r15
0x180005ec0  lea     rbp, [rsp-17h]
0x180005ec5  sub     rsp, 90h
0x180005ecc  mov     rax, cs:__security_cookie
0x180005ed3  xor     rax, rsp
0x180005ed6  mov     [rbp+47h+var_40], rax
0x180005eda  mov     rbx, r9
0x180005edd  mov     r12, r8
0x180005ee0  mov     [rbp+47h+var_70], r8
0x180005ee4  mov     rdi, rcx
0x180005ee7  mov     rsi, [rbp+47h+arg_20]
0x180005eeb  mov     [rbp+47h+var_68], rcx
0x180005eef  mov     rax, [rbp+47h+arg_28]
0x180005ef3  mov     [rbp+47h+var_78], rax
0x180005ef7  xor     r13d, r13d
0x180005efa  lea     r15, aOregistrykeyGe; "ORegistryKey.GetValue failure: Cannot g"...
0x180005f01  cmp     r15, r8
0x180005f04  jnb     loc_180005FA2
0x180005f0a  lfence
0x180005f0d  lea     r14d, [r13+25h]
0x180005f11  xorps   xmm0, xmm0
0x180005f14  movups  xmmword ptr [rbp+47h+Block], xmm0
0x180005f18  mov     [rbp+47h+var_50], r13
0x180005f1c  mov     [rbp+47h+var_48], 7
0x180005f24  mov     word ptr [rbp+47h+Block], r13w
0x180005f29  movzx   r8d, word ptr [r15]
0x180005f2d  lea     r13, [r15+2]
0x180005f31  mov     r15, r13
0x180005f34  mov     [rbp+47h+var_90], r13
0x180005f38  cmp     r8w, r14w
0x180005f3c  jz      short loc_180005F50
0x180005f3e  mov     edx, 1
0x180005f43  mov     rcx, rbx; Src
0x180005f46  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180005f4b  xor     r13d, r13d
0x180005f4e  jmp     short loc_180005F90
0x180005f50  cmp     r13, r12
0x180005f53  jz      short loc_180005F72
0x180005f55  cmp     [r13+0], r14w
0x180005f5a  jnz     short loc_180005F72
0x180005f5c  mov     r8d, r14d
0x180005f5f  mov     edx, 1
0x180005f64  mov     rcx, rbx; Src
0x180005f67  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180005f6c  lea     r15, [r13+2]
0x180005f70  jmp     short loc_180005F4B
0x180005f72  lea     r9, [rbp+47h+Block]
0x180005f76  mov     r8, rbx
0x180005f79  mov     rdx, r12
0x180005f7c  lea     rcx, [rbp+47h+var_90]
0x180005f80  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180005f85  xor     r13d, r13d
0x180005f88  test    al, al
0x180005f8a  jnz     short loc_180005FF4
0x180005f8c  mov     r15, [rbp+47h+var_90]
0x180005f90  lea     rcx, [rbp+47h+Block]
0x180005f94  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005f99  cmp     r15, r12
0x180005f9c  jb      loc_180005F11
0x180005fa2  xorps   xmm0, xmm0
0x180005fa5  movups  xmmword ptr [rdi], xmm0
0x180005fa8  mov     [rdi+10h], r13
0x180005fac  mov     [rdi+18h], r13
0x180005fb0  mov     r8, [rbx+10h]
0x180005fb4  cmp     qword ptr [rbx+18h], 7
0x180005fb9  jbe     short loc_180005FBE
0x180005fbb  mov     rbx, [rbx]
0x180005fbe  mov     rdx, rbx
0x180005fc1  mov     rcx, rdi
0x180005fc4  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005fc9  nop
0x180005fca  mov     rax, rdi
0x180005fcd  mov     rcx, [rbp+47h+var_40]
0x180005fd1  xor     rcx, rsp; StackCookie
0x180005fd4  call    __security_check_cookie
0x180005fd9  mov     rbx, [rsp+0C0h+arg_8]
0x180005fe1  add     rsp, 90h
0x180005fe8  pop     r15
0x180005fea  pop     r14
0x180005fec  pop     r13
0x180005fee  pop     r12
0x180005ff0  pop     rdi
0x180005ff1  pop     rsi
0x180005ff2  pop     rbp
0x180005ff3  retn
0x180005ff4  cmp     qword ptr [rsi+18h], 7
0x180005ff9  jbe     short loc_180005FFE
0x180005ffb  mov     rsi, [rsi]
0x180005ffe  mov     rax, [rbp+47h+var_50]
0x180006002  lea     rcx, [rax-1]
0x180006006  cmp     rcx, rax
0x180006009  jbe     short loc_180006021
0x18000600b  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180006010  xor     r9d, r9d; LineNo
0x180006013  xor     r8d, r8d; FileName
0x180006016  xor     edx, edx; FunctionName
0x180006018  xor     ecx, ecx; Expression
0x18000601a  call    cs:__imp__invoke_watson
0x180006021  lfence
0x180006024  lea     rax, [rbp+47h+Block]
0x180006028  mov     r15, [rbp+47h+Block]
0x18000602c  mov     r12, [rbp+47h+var_48]
0x180006030  cmp     r12, 7
0x180006034  cmova   rax, r15
0x180006038  movzx   eax, word ptr [rax+rcx*2]
0x18000603c  sub     ax, 53h ; 'S'
0x180006040  mov     ecx, 0FFDFh
0x180006045  test    cx, ax
0x180006048  jz      short loc_180006053
0x18000604a  lea     rsi, aErrorWrongForm_0; "!error: wrong format for wide string!"
0x180006051  jmp     short loc_180006075
0x180006053  test    rsi, rsi
0x180006056  jnz     short loc_180006067
0x180006058  lea     rsi, aNull_1; "<NULL>"
0x18000605f  mov     r14d, 6
0x180006065  jmp     short loc_180006075
0x180006067  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000606b  inc     r14
0x18000606e  cmp     [rsi+r14*2], r13w
0x180006073  jnz     short loc_18000606B
0x180006075  mov     r8, r14
0x180006078  mov     rdx, rsi
0x18000607b  mov     rcx, rbx; Src
0x18000607e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180006083  mov     rax, [rbp+47h+var_78]
0x180006087  mov     [rsp+0C0h+Reserved], rax
0x18000608c  mov     r9, rbx
0x18000608f  mov     r8, [rbp+47h+var_70]
0x180006093  mov     rdx, [rbp+47h+var_90]
0x180006097  mov     rcx, rdi
0x18000609a  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@@Z; ArgumentWriter::FormatArguments<std::wstring,>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &)
0x18000609f  nop
0x1800060a0  cmp     r12, 7
0x1800060a4  jbe     loc_180005FCA
0x1800060aa  mov     rcx, r15
0x1800060ad  lea     rax, ds:2[r12*2]
0x1800060b5  cmp     rax, 1000h
0x1800060bb  jb      short loc_1800060E4
0x1800060bd  mov     r15, [r15-8]
0x1800060c1  sub     rcx, r15
0x1800060c4  lea     rax, [rcx-8]
0x1800060c8  cmp     rax, 1Fh
0x1800060cc  jbe     short loc_1800060E4
0x1800060ce  mov     [rsp+0C0h+Reserved], r13; Reserved
0x1800060d3  xor     r9d, r9d; LineNo
0x1800060d6  xor     r8d, r8d; FileName
0x1800060d9  xor     edx, edx; FunctionName
0x1800060db  xor     ecx, ecx; Expression
0x1800060dd  call    cs:__imp__invoke_watson
0x1800060e4  mov     rcx, r15; Block
0x1800060e7  call    cs:__imp_free
0x1800060ed  jmp     loc_180005FCA
```

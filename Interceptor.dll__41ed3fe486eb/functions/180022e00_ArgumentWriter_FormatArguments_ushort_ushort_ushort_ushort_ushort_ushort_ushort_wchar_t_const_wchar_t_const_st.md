# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)

- ea: `0x180022e00`
- end: `0x180023027`
- name: `??$FormatArguments@GGGGGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG222222@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800226d0`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180022e00`
- `0x180023930`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023014`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023014`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002301b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002301b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  const wchar_t *v14; // rsi
  __m128i si128; // xmm6
  wchar_t v16; // r8
  unsigned __int16 *v17; // r15
  __int64 v18; // r8
  void *v20; // rcx
  unsigned __int16 *v21; // [rsp+58h] [rbp-79h] BYREF
  __int64 v22; // [rsp+70h] [rbp-61h]
  __int64 v23; // [rsp+78h] [rbp-59h]
  __int64 v24; // [rsp+80h] [rbp-51h]
  __int64 v25; // [rsp+88h] [rbp-49h]
  __int64 v26; // [rsp+90h] [rbp-41h]
  __int64 v27; // [rsp+98h] [rbp-39h]
  void *Block[2]; // [rsp+A0h] [rbp-31h] BYREF
  __m128i v29; // [rsp+B0h] [rbp-21h]

  v27 = a1;
  v26 = a7;
  v25 = a8;
  v24 = a9;
  v23 = a10;
  v22 = a11;
  v14 = L"%04d/%02d/%02d %02d:%02d:%02d:%03d";
  if ( L"%04d/%02d/%02d %02d:%02d:%02d:%03d" >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v18 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v18);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v29 = si128;
    LOWORD(Block[0]) = 0;
    v16 = *v14;
    v17 = (unsigned __int16 *)(v14 + 1);
    v14 = v17;
    v21 = v17;
    if ( v16 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v17 == a3 || *v17 != 37 )
      break;
    std::wstring::append(a4);
    v14 = v17 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v14 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v21, a3, a4, (__int64)Block) )
  {
    v14 = v21;
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    a1,
    v21,
    a3,
    a4,
    a6,
    v26,
    v25,
    v24,
    v23,
    v22);
  if ( v29.m128i_i64[1] > 7uLL )
  {
    v20 = Block[0];
    if ( (unsigned __int64)(2 * v29.m128i_i64[1] + 2) >= 0x1000 )
    {
      v20 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v20);
  }
  return a1;
}

```

## disassembly

```asm
0x180022e00  mov     rax, rsp
0x180022e03  mov     [rax+10h], rbx
0x180022e07  push    rbp
0x180022e08  push    rsi
0x180022e09  push    rdi
0x180022e0a  push    r12
0x180022e0c  push    r13
0x180022e0e  push    r14
0x180022e10  push    r15
0x180022e12  lea     rbp, [rax-3Fh]
0x180022e16  sub     rsp, 0D0h
0x180022e1d  movaps  xmmword ptr [rax-48h], xmm6
0x180022e21  mov     rax, cs:__security_cookie
0x180022e28  xor     rax, rsp
0x180022e2b  mov     [rbp+37h+var_48], rax
0x180022e2f  mov     rbx, r9
0x180022e32  mov     r14, r8
0x180022e35  mov     rdi, rcx
0x180022e38  mov     [rbp+37h+var_70], rcx
0x180022e3c  mov     r12, [rbp+37h+arg_20]
0x180022e40  mov     r13, [rbp+37h+arg_28]
0x180022e44  mov     rax, [rbp+37h+arg_30]
0x180022e48  mov     [rbp+37h+var_78], rax
0x180022e4c  mov     rax, [rbp+37h+arg_38]
0x180022e50  mov     [rbp+37h+var_80], rax
0x180022e54  mov     rax, [rbp+37h+arg_40]
0x180022e5b  mov     [rbp+37h+var_88], rax
0x180022e5f  mov     rax, [rbp+37h+arg_48]
0x180022e66  mov     [rbp+37h+var_90], rax
0x180022e6a  mov     rax, [rbp+37h+arg_50]
0x180022e71  mov     [rbp+37h+var_98], rax
0x180022e75  xor     r15d, r15d
0x180022e78  lea     rsi, a04d02d02d02d02; "%04d/%02d/%02d %02d:%02d:%02d:%03d"
0x180022e7f  cmp     rsi, r8
0x180022e82  jnb     loc_180022F1F
0x180022e88  lfence
0x180022e8b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180022e93  mov     eax, 25h ; '%'
0x180022e98  xorps   xmm0, xmm0
0x180022e9b  movups  xmmword ptr [rbp+37h+Block], xmm0
0x180022e9f  movdqu  [rbp+37h+var_58], xmm6
0x180022ea4  mov     word ptr [rbp+37h+Block], r15w
0x180022ea9  movzx   r8d, word ptr [rsi]
0x180022ead  lea     r15, [rsi+2]
0x180022eb1  mov     rsi, r15
0x180022eb4  mov     [rbp+37h+var_B0], r15
0x180022eb8  cmp     r8w, ax
0x180022ebc  jz      short loc_180022ECE
0x180022ebe  lea     edx, [rax-24h]
0x180022ec1  mov     rcx, rbx; Src
0x180022ec4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180022ec9  xor     r15d, r15d
0x180022ecc  jmp     short loc_180022F0D
0x180022ece  cmp     r15, r14
0x180022ed1  jz      short loc_180022EEF
0x180022ed3  cmp     [r15], ax
0x180022ed7  jnz     short loc_180022EEF
0x180022ed9  mov     r8d, eax
0x180022edc  mov     edx, 1
0x180022ee1  mov     rcx, rbx; Src
0x180022ee4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180022ee9  lea     rsi, [r15+2]
0x180022eed  jmp     short loc_180022EC9
0x180022eef  lea     r9, [rbp+37h+Block]
0x180022ef3  mov     r8, rbx
0x180022ef6  mov     rdx, r14
0x180022ef9  lea     rcx, [rbp+37h+var_B0]
0x180022efd  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180022f02  xor     r15d, r15d
0x180022f05  test    al, al
0x180022f07  jnz     short loc_180022F76
0x180022f09  mov     rsi, [rbp+37h+var_B0]
0x180022f0d  lea     rcx, [rbp+37h+Block]
0x180022f11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022f16  cmp     rsi, r14
0x180022f19  jb      loc_180022E93
0x180022f1f  xorps   xmm0, xmm0
0x180022f22  movups  xmmword ptr [rdi], xmm0
0x180022f25  mov     [rdi+10h], r15
0x180022f29  mov     [rdi+18h], r15
0x180022f2d  mov     r8, [rbx+10h]
0x180022f31  cmp     qword ptr [rbx+18h], 7
0x180022f36  jbe     short loc_180022F3B
0x180022f38  mov     rbx, [rbx]
0x180022f3b  mov     rdx, rbx
0x180022f3e  mov     rcx, rdi
0x180022f41  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180022f46  nop
0x180022f47  mov     rax, rdi
0x180022f4a  mov     rcx, [rbp+37h+var_48]
0x180022f4e  xor     rcx, rsp; StackCookie
0x180022f51  call    __security_check_cookie
0x180022f56  lea     r11, [rsp+100h+var_30]
0x180022f5e  mov     rbx, [r11+48h]
0x180022f62  movaps  xmm6, xmmword ptr [r11-10h]
0x180022f67  mov     rsp, r11
0x180022f6a  pop     r15
0x180022f6c  pop     r14
0x180022f6e  pop     r13
0x180022f70  pop     r12
0x180022f72  pop     rdi
0x180022f73  pop     rsi
0x180022f74  pop     rbp
0x180022f75  retn
0x180022f76  lfence
0x180022f79  movzx   r8d, word ptr [r12]
0x180022f7e  lea     rdx, [rbp+37h+Block]; Format
0x180022f82  mov     rcx, rbx; Src
0x180022f85  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180022f8a  mov     rax, [rbp+37h+var_98]
0x180022f8e  mov     [rsp+100h+var_B8], rax
0x180022f93  mov     rax, [rbp+37h+var_90]
0x180022f97  mov     [rsp+100h+var_C0], rax
0x180022f9c  mov     rax, [rbp+37h+var_88]
0x180022fa0  mov     [rsp+100h+var_C8], rax
0x180022fa5  mov     rax, [rbp+37h+var_80]
0x180022fa9  mov     [rsp+100h+var_D0], rax
0x180022fae  mov     rax, [rbp+37h+var_78]
0x180022fb2  mov     [rsp+100h+var_D8], rax
0x180022fb7  mov     [rsp+100h+Reserved], r13
0x180022fbc  mov     r9, rbx
0x180022fbf  mov     r8, r14
0x180022fc2  mov     rdx, [rbp+37h+var_B0]
0x180022fc6  mov     rcx, rdi
0x180022fc9  call    ??$FormatArguments@GGGGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22222@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)
0x180022fce  nop
0x180022fcf  mov     rax, qword ptr [rbp+37h+var_58+8]
0x180022fd3  cmp     rax, 7
0x180022fd7  jbe     loc_180022F47
0x180022fdd  mov     rcx, [rbp+37h+Block]; Block
0x180022fe1  mov     rdx, rcx
0x180022fe4  lea     rax, ds:2[rax*2]
0x180022fec  cmp     rax, 1000h
0x180022ff2  jb      short loc_18002301B
0x180022ff4  mov     rcx, [rcx-8]
0x180022ff8  sub     rdx, rcx
0x180022ffb  lea     rax, [rdx-8]
0x180022fff  cmp     rax, 1Fh
0x180023003  jbe     short loc_18002301B
0x180023005  mov     [rsp+100h+Reserved], r15; Reserved
0x18002300a  xor     r9d, r9d; LineNo
0x18002300d  xor     r8d, r8d; FileName
0x180023010  xor     edx, edx; FunctionName
0x180023012  xor     ecx, ecx; Expression
0x180023014  call    cs:__imp__invoke_watson
0x18002301b  call    cs:__imp_free
0x180023021  jmp     loc_180022F47
```

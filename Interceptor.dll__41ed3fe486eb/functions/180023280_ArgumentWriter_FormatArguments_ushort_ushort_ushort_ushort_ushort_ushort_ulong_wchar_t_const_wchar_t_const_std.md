# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)

- ea: `0x180023280`
- end: `0x1800234a7`
- name: `??$FormatArguments@GGGGGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22222AEBK@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002291c`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180023280`
- `0x180023d00`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023494`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023494`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002349b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002349b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
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
  const wchar_t *v21; // [rsp+58h] [rbp-79h] BYREF
  __int64 v22; // [rsp+68h] [rbp-69h]
  __int64 v23; // [rsp+70h] [rbp-61h]
  __int64 v24; // [rsp+78h] [rbp-59h]
  __int64 v25; // [rsp+80h] [rbp-51h]
  __int64 v26; // [rsp+88h] [rbp-49h]
  __int64 v27; // [rsp+90h] [rbp-41h]
  void *Block[2]; // [rsp+98h] [rbp-39h] BYREF
  __m128i v29; // [rsp+A8h] [rbp-29h]

  v27 = a1;
  v26 = a7;
  v25 = a8;
  v24 = a9;
  v23 = a10;
  v22 = a11;
  v14 = L"%04d%02d%02d%02d%02d%02d%X";
  if ( L"%04d%02d%02d%02d%02d%02d%X" >= a3 )
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
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned long>(
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
0x180023280  mov     rax, rsp
0x180023283  mov     [rax+10h], rbx
0x180023287  push    rbp
0x180023288  push    rsi
0x180023289  push    rdi
0x18002328a  push    r12
0x18002328c  push    r13
0x18002328e  push    r14
0x180023290  push    r15
0x180023292  lea     rbp, [rax-3Fh]
0x180023296  sub     rsp, 0D0h
0x18002329d  movaps  xmmword ptr [rax-48h], xmm6
0x1800232a1  mov     rax, cs:__security_cookie
0x1800232a8  xor     rax, rsp
0x1800232ab  mov     [rbp+37h+var_50], rax
0x1800232af  mov     rbx, r9
0x1800232b2  mov     r14, r8
0x1800232b5  mov     rdi, rcx
0x1800232b8  mov     [rbp+37h+var_78], rcx
0x1800232bc  mov     r12, [rbp+37h+arg_20]
0x1800232c0  mov     r13, [rbp+37h+arg_28]
0x1800232c4  mov     rax, [rbp+37h+arg_30]
0x1800232c8  mov     [rbp+37h+var_80], rax
0x1800232cc  mov     rax, [rbp+37h+arg_38]
0x1800232d0  mov     [rbp+37h+var_88], rax
0x1800232d4  mov     rax, [rbp+37h+arg_40]
0x1800232db  mov     [rbp+37h+var_90], rax
0x1800232df  mov     rax, [rbp+37h+arg_48]
0x1800232e6  mov     [rbp+37h+var_98], rax
0x1800232ea  mov     rax, [rbp+37h+arg_50]
0x1800232f1  mov     [rbp+37h+var_A0], rax
0x1800232f5  xor     r15d, r15d
0x1800232f8  lea     rsi, a04d02d02d02d02_0; "%04d%02d%02d%02d%02d%02d%X"
0x1800232ff  cmp     rsi, r8
0x180023302  jnb     loc_18002339F
0x180023308  lfence
0x18002330b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180023313  mov     eax, 25h ; '%'
0x180023318  xorps   xmm0, xmm0
0x18002331b  movups  xmmword ptr [rbp+37h+Block], xmm0
0x18002331f  movdqu  [rbp+37h+var_60], xmm6
0x180023324  mov     word ptr [rbp+37h+Block], r15w
0x180023329  movzx   r8d, word ptr [rsi]
0x18002332d  lea     r15, [rsi+2]
0x180023331  mov     rsi, r15
0x180023334  mov     [rbp+37h+var_B0], r15
0x180023338  cmp     r8w, ax
0x18002333c  jz      short loc_18002334E
0x18002333e  lea     edx, [rax-24h]
0x180023341  mov     rcx, rbx; Src
0x180023344  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023349  xor     r15d, r15d
0x18002334c  jmp     short loc_18002338D
0x18002334e  cmp     r15, r14
0x180023351  jz      short loc_18002336F
0x180023353  cmp     [r15], ax
0x180023357  jnz     short loc_18002336F
0x180023359  mov     r8d, eax
0x18002335c  mov     edx, 1
0x180023361  mov     rcx, rbx; Src
0x180023364  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023369  lea     rsi, [r15+2]
0x18002336d  jmp     short loc_180023349
0x18002336f  lea     r9, [rbp+37h+Block]
0x180023373  mov     r8, rbx
0x180023376  mov     rdx, r14
0x180023379  lea     rcx, [rbp+37h+var_B0]
0x18002337d  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180023382  xor     r15d, r15d
0x180023385  test    al, al
0x180023387  jnz     short loc_1800233F6
0x180023389  mov     rsi, [rbp+37h+var_B0]
0x18002338d  lea     rcx, [rbp+37h+Block]
0x180023391  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023396  cmp     rsi, r14
0x180023399  jb      loc_180023313
0x18002339f  xorps   xmm0, xmm0
0x1800233a2  movups  xmmword ptr [rdi], xmm0
0x1800233a5  mov     [rdi+10h], r15
0x1800233a9  mov     [rdi+18h], r15
0x1800233ad  mov     r8, [rbx+10h]
0x1800233b1  cmp     qword ptr [rbx+18h], 7
0x1800233b6  jbe     short loc_1800233BB
0x1800233b8  mov     rbx, [rbx]
0x1800233bb  mov     rdx, rbx
0x1800233be  mov     rcx, rdi
0x1800233c1  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800233c6  nop
0x1800233c7  mov     rax, rdi
0x1800233ca  mov     rcx, [rbp+37h+var_50]
0x1800233ce  xor     rcx, rsp; StackCookie
0x1800233d1  call    __security_check_cookie
0x1800233d6  lea     r11, [rsp+100h+var_30]
0x1800233de  mov     rbx, [r11+48h]
0x1800233e2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800233e7  mov     rsp, r11
0x1800233ea  pop     r15
0x1800233ec  pop     r14
0x1800233ee  pop     r13
0x1800233f0  pop     r12
0x1800233f2  pop     rdi
0x1800233f3  pop     rsi
0x1800233f4  pop     rbp
0x1800233f5  retn
0x1800233f6  lfence
0x1800233f9  movzx   r8d, word ptr [r12]
0x1800233fe  lea     rdx, [rbp+37h+Block]; Format
0x180023402  mov     rcx, rbx; Src
0x180023405  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x18002340a  mov     rax, [rbp+37h+var_A0]
0x18002340e  mov     [rsp+100h+var_B8], rax
0x180023413  mov     rax, [rbp+37h+var_98]
0x180023417  mov     [rsp+100h+var_C0], rax
0x18002341c  mov     rax, [rbp+37h+var_90]
0x180023420  mov     [rsp+100h+var_C8], rax
0x180023425  mov     rax, [rbp+37h+var_88]
0x180023429  mov     [rsp+100h+var_D0], rax
0x18002342e  mov     rax, [rbp+37h+var_80]
0x180023432  mov     [rsp+100h+var_D8], rax
0x180023437  mov     [rsp+100h+Reserved], r13
0x18002343c  mov     r9, rbx
0x18002343f  mov     r8, r14
0x180023442  mov     rdx, [rbp+37h+var_B0]
0x180023446  mov     rcx, rdi
0x180023449  call    ??$FormatArguments@GGGGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2222AEBK@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ulong const &)
0x18002344e  nop
0x18002344f  mov     rax, qword ptr [rbp+37h+var_60+8]
0x180023453  cmp     rax, 7
0x180023457  jbe     loc_1800233C7
0x18002345d  mov     rcx, [rbp+37h+Block]; Block
0x180023461  mov     rdx, rcx
0x180023464  lea     rax, ds:2[rax*2]
0x18002346c  cmp     rax, 1000h
0x180023472  jb      short loc_18002349B
0x180023474  mov     rcx, [rcx-8]
0x180023478  sub     rdx, rcx
0x18002347b  lea     rax, [rdx-8]
0x18002347f  cmp     rax, 1Fh
0x180023483  jbe     short loc_18002349B
0x180023485  mov     [rsp+100h+Reserved], r15; Reserved
0x18002348a  xor     r9d, r9d; LineNo
0x18002348d  xor     r8d, r8d; FileName
0x180023490  xor     edx, edx; FunctionName
0x180023492  xor     ecx, ecx; Expression
0x180023494  call    cs:__imp__invoke_watson
0x18002349b  call    cs:__imp_free
0x1800234a1  jmp     loc_1800233C7
```

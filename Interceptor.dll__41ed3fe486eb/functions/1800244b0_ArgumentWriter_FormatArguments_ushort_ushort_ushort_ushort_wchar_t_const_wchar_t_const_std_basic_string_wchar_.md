# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &)

- ea: `0x1800244b0`
- end: `0x180024693`
- name: `??$FormatArguments@GGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG222@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023f10`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x1800244b0`
- `0x180024884`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024680`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024680`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024687`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024687`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned __int16 *a8)
{
  unsigned __int16 *v10; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v13; // r8
  unsigned __int16 *v14; // r15
  __int64 v15; // r8
  void *v17; // rcx
  unsigned __int16 *v18; // [rsp+48h] [rbp-59h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp-49h]
  __int64 v20; // [rsp+60h] [rbp-41h]
  unsigned __int64 v21; // [rsp+68h] [rbp-39h]
  void *Block[2]; // [rsp+70h] [rbp-31h] BYREF
  __m128i v23; // [rsp+80h] [rbp-21h]

  v10 = a2;
  v21 = a1;
  v20 = a7;
  v19 = a8;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v15 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v15);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v23 = si128;
    LOWORD(Block[0]) = 0;
    v13 = *v10;
    v14 = v10 + 1;
    v10 = v14;
    v18 = v14;
    if ( v13 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v14 == a3 || *v14 != 37 )
      break;
    std::wstring::append(a4);
    v10 = v14 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v10 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v18, a3, a4, (__int64)Block) )
  {
    v10 = v18;
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short>(a1, v18, a3, a4, a6, v20, v19);
  if ( v23.m128i_i64[1] > 7uLL )
  {
    v17 = Block[0];
    if ( (unsigned __int64)(2 * v23.m128i_i64[1] + 2) >= 0x1000 )
    {
      v17 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  return a1;
}

```

## disassembly

```asm
0x1800244b0  mov     rax, rsp
0x1800244b3  mov     [rax+18h], rbx
0x1800244b7  push    rbp
0x1800244b8  push    rsi
0x1800244b9  push    rdi
0x1800244ba  push    r12
0x1800244bc  push    r13
0x1800244be  push    r14
0x1800244c0  push    r15
0x1800244c2  lea     rbp, [rax-3Fh]
0x1800244c6  sub     rsp, 0A0h
0x1800244cd  movaps  xmmword ptr [rax-48h], xmm6
0x1800244d1  mov     rax, cs:__security_cookie
0x1800244d8  xor     rax, rsp
0x1800244db  mov     [rbp+37h+var_48], rax
0x1800244df  mov     rbx, r9
0x1800244e2  mov     r14, r8
0x1800244e5  mov     rsi, rdx
0x1800244e8  mov     rdi, rcx
0x1800244eb  mov     [rbp+37h+var_70], rcx
0x1800244ef  mov     r12, [rbp+37h+arg_20]
0x1800244f3  mov     r13, [rbp+37h+arg_28]
0x1800244f7  mov     rax, [rbp+37h+arg_30]
0x1800244fb  mov     [rbp+37h+var_78], rax
0x1800244ff  mov     rax, [rbp+37h+arg_38]
0x180024503  mov     [rbp+37h+var_80], rax
0x180024507  xor     r15d, r15d
0x18002450a  cmp     rdx, r8
0x18002450d  jnb     loc_1800245AA
0x180024513  lfence
0x180024516  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002451e  mov     eax, 25h ; '%'
0x180024523  xorps   xmm0, xmm0
0x180024526  movups  xmmword ptr [rbp+37h+Block], xmm0
0x18002452a  movdqu  [rbp+37h+var_58], xmm6
0x18002452f  mov     word ptr [rbp+37h+Block], r15w
0x180024534  movzx   r8d, word ptr [rsi]
0x180024538  lea     r15, [rsi+2]
0x18002453c  mov     rsi, r15
0x18002453f  mov     [rbp+37h+var_90], r15
0x180024543  cmp     r8w, ax
0x180024547  jz      short loc_180024559
0x180024549  lea     edx, [rax-24h]
0x18002454c  mov     rcx, rbx; Src
0x18002454f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024554  xor     r15d, r15d
0x180024557  jmp     short loc_180024598
0x180024559  cmp     r15, r14
0x18002455c  jz      short loc_18002457A
0x18002455e  cmp     [r15], ax
0x180024562  jnz     short loc_18002457A
0x180024564  mov     r8d, eax
0x180024567  mov     edx, 1
0x18002456c  mov     rcx, rbx; Src
0x18002456f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024574  lea     rsi, [r15+2]
0x180024578  jmp     short loc_180024554
0x18002457a  lea     r9, [rbp+37h+Block]
0x18002457e  mov     r8, rbx
0x180024581  mov     rdx, r14
0x180024584  lea     rcx, [rbp+37h+var_90]
0x180024588  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x18002458d  xor     r15d, r15d
0x180024590  test    al, al
0x180024592  jnz     short loc_180024601
0x180024594  mov     rsi, [rbp+37h+var_90]
0x180024598  lea     rcx, [rbp+37h+Block]
0x18002459c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800245a1  cmp     rsi, r14
0x1800245a4  jb      loc_18002451E
0x1800245aa  xorps   xmm0, xmm0
0x1800245ad  movups  xmmword ptr [rdi], xmm0
0x1800245b0  mov     [rdi+10h], r15
0x1800245b4  mov     [rdi+18h], r15
0x1800245b8  mov     r8, [rbx+10h]
0x1800245bc  cmp     qword ptr [rbx+18h], 7
0x1800245c1  jbe     short loc_1800245C6
0x1800245c3  mov     rbx, [rbx]
0x1800245c6  mov     rdx, rbx
0x1800245c9  mov     rcx, rdi
0x1800245cc  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800245d1  nop
0x1800245d2  mov     rax, rdi
0x1800245d5  mov     rcx, [rbp+37h+var_48]
0x1800245d9  xor     rcx, rsp; StackCookie
0x1800245dc  call    __security_check_cookie
0x1800245e1  lea     r11, [rsp+0D0h+var_30]
0x1800245e9  mov     rbx, [r11+50h]
0x1800245ed  movaps  xmm6, xmmword ptr [r11-10h]
0x1800245f2  mov     rsp, r11
0x1800245f5  pop     r15
0x1800245f7  pop     r14
0x1800245f9  pop     r13
0x1800245fb  pop     r12
0x1800245fd  pop     rdi
0x1800245fe  pop     rsi
0x1800245ff  pop     rbp
0x180024600  retn
0x180024601  lfence
0x180024604  movzx   r8d, word ptr [r12]
0x180024609  lea     rdx, [rbp+37h+Block]; Format
0x18002460d  mov     rcx, rbx; Src
0x180024610  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024615  mov     rax, [rbp+37h+var_80]
0x180024619  mov     [rsp+0D0h+var_A0], rax
0x18002461e  mov     rax, [rbp+37h+var_78]
0x180024622  mov     [rsp+0D0h+var_A8], rax
0x180024627  mov     [rsp+0D0h+Reserved], r13
0x18002462c  mov     r9, rbx
0x18002462f  mov     r8, r14
0x180024632  mov     rdx, [rbp+37h+var_90]
0x180024636  mov     rcx, rdi
0x180024639  call    ??$FormatArguments@GGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &)
0x18002463e  nop
0x18002463f  mov     rax, qword ptr [rbp+37h+var_58+8]
0x180024643  cmp     rax, 7
0x180024647  jbe     short loc_1800245D2
0x180024649  mov     rcx, [rbp+37h+Block]; Block
0x18002464d  mov     rdx, rcx
0x180024650  lea     rax, ds:2[rax*2]
0x180024658  cmp     rax, 1000h
0x18002465e  jb      short loc_180024687
0x180024660  mov     rcx, [rcx-8]
0x180024664  sub     rdx, rcx
0x180024667  lea     rax, [rdx-8]
0x18002466b  cmp     rax, 1Fh
0x18002466f  jbe     short loc_180024687
0x180024671  mov     [rsp+0D0h+Reserved], r15; Reserved
0x180024676  xor     r9d, r9d; LineNo
0x180024679  xor     r8d, r8d; FileName
0x18002467c  xor     edx, edx; FunctionName
0x18002467e  xor     ecx, ecx; Expression
0x180024680  call    cs:__imp__invoke_watson
0x180024687  call    cs:__imp_free
0x18002468d  jmp     loc_1800245D2
```

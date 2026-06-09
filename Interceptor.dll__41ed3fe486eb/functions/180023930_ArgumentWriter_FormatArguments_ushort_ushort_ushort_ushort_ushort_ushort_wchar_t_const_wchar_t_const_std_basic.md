# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)

- ea: `0x180023930`
- end: `0x180023b3f`
- name: `??$FormatArguments@GGGGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22222@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180022e00`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x180023930`
- `0x180023f10`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023b2c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023b2c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023b33`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023b33`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
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
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
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
0x180023930  mov     rax, rsp
0x180023933  mov     [rax+18h], rbx
0x180023937  push    rbp
0x180023938  push    rsi
0x180023939  push    rdi
0x18002393a  push    r12
0x18002393c  push    r13
0x18002393e  push    r14
0x180023940  push    r15
0x180023942  lea     rbp, [rax-3Fh]
0x180023946  sub     rsp, 0C0h
0x18002394d  movaps  xmmword ptr [rax-48h], xmm6
0x180023951  mov     rax, cs:__security_cookie
0x180023958  xor     rax, rsp
0x18002395b  mov     [rbp+37h+var_48], rax
0x18002395f  mov     rbx, r9
0x180023962  mov     r14, r8
0x180023965  mov     rsi, rdx
0x180023968  mov     rdi, rcx
0x18002396b  mov     [rbp+37h+var_70], rcx
0x18002396f  mov     r12, [rbp+37h+arg_20]
0x180023973  mov     r13, [rbp+37h+arg_28]
0x180023977  mov     rax, [rbp+37h+arg_30]
0x18002397b  mov     [rbp+37h+var_78], rax
0x18002397f  mov     rax, [rbp+37h+arg_38]
0x180023983  mov     [rbp+37h+var_80], rax
0x180023987  mov     rax, [rbp+37h+arg_40]
0x18002398e  mov     [rbp+37h+var_88], rax
0x180023992  mov     rax, [rbp+37h+arg_48]
0x180023999  mov     [rbp+37h+var_90], rax
0x18002399d  xor     r15d, r15d
0x1800239a0  cmp     rdx, r8
0x1800239a3  jnb     loc_180023A40
0x1800239a9  lfence
0x1800239ac  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800239b4  mov     eax, 25h ; '%'
0x1800239b9  xorps   xmm0, xmm0
0x1800239bc  movups  xmmword ptr [rbp+37h+Block], xmm0
0x1800239c0  movdqu  [rbp+37h+var_58], xmm6
0x1800239c5  mov     word ptr [rbp+37h+Block], r15w
0x1800239ca  movzx   r8d, word ptr [rsi]
0x1800239ce  lea     r15, [rsi+2]
0x1800239d2  mov     rsi, r15
0x1800239d5  mov     [rbp+37h+var_A0], r15
0x1800239d9  cmp     r8w, ax
0x1800239dd  jz      short loc_1800239EF
0x1800239df  lea     edx, [rax-24h]
0x1800239e2  mov     rcx, rbx; Src
0x1800239e5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x1800239ea  xor     r15d, r15d
0x1800239ed  jmp     short loc_180023A2E
0x1800239ef  cmp     r15, r14
0x1800239f2  jz      short loc_180023A10
0x1800239f4  cmp     [r15], ax
0x1800239f8  jnz     short loc_180023A10
0x1800239fa  mov     r8d, eax
0x1800239fd  mov     edx, 1
0x180023a02  mov     rcx, rbx; Src
0x180023a05  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023a0a  lea     rsi, [r15+2]
0x180023a0e  jmp     short loc_1800239EA
0x180023a10  lea     r9, [rbp+37h+Block]
0x180023a14  mov     r8, rbx
0x180023a17  mov     rdx, r14
0x180023a1a  lea     rcx, [rbp+37h+var_A0]
0x180023a1e  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180023a23  xor     r15d, r15d
0x180023a26  test    al, al
0x180023a28  jnz     short loc_180023A97
0x180023a2a  mov     rsi, [rbp+37h+var_A0]
0x180023a2e  lea     rcx, [rbp+37h+Block]
0x180023a32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023a37  cmp     rsi, r14
0x180023a3a  jb      loc_1800239B4
0x180023a40  xorps   xmm0, xmm0
0x180023a43  movups  xmmword ptr [rdi], xmm0
0x180023a46  mov     [rdi+10h], r15
0x180023a4a  mov     [rdi+18h], r15
0x180023a4e  mov     r8, [rbx+10h]
0x180023a52  cmp     qword ptr [rbx+18h], 7
0x180023a57  jbe     short loc_180023A5C
0x180023a59  mov     rbx, [rbx]
0x180023a5c  mov     rdx, rbx
0x180023a5f  mov     rcx, rdi
0x180023a62  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180023a67  nop
0x180023a68  mov     rax, rdi
0x180023a6b  mov     rcx, [rbp+37h+var_48]
0x180023a6f  xor     rcx, rsp; StackCookie
0x180023a72  call    __security_check_cookie
0x180023a77  lea     r11, [rsp+0F0h+var_30]
0x180023a7f  mov     rbx, [r11+50h]
0x180023a83  movaps  xmm6, xmmword ptr [r11-10h]
0x180023a88  mov     rsp, r11
0x180023a8b  pop     r15
0x180023a8d  pop     r14
0x180023a8f  pop     r13
0x180023a91  pop     r12
0x180023a93  pop     rdi
0x180023a94  pop     rsi
0x180023a95  pop     rbp
0x180023a96  retn
0x180023a97  lfence
0x180023a9a  movzx   r8d, word ptr [r12]
0x180023a9f  lea     rdx, [rbp+37h+Block]; Format
0x180023aa3  mov     rcx, rbx; Src
0x180023aa6  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180023aab  mov     rax, [rbp+37h+var_90]
0x180023aaf  mov     [rsp+0F0h+var_B0], rax
0x180023ab4  mov     rax, [rbp+37h+var_88]
0x180023ab8  mov     [rsp+0F0h+var_B8], rax
0x180023abd  mov     rax, [rbp+37h+var_80]
0x180023ac1  mov     [rsp+0F0h+var_C0], rax
0x180023ac6  mov     rax, [rbp+37h+var_78]
0x180023aca  mov     [rsp+0F0h+var_C8], rax
0x180023acf  mov     [rsp+0F0h+Reserved], r13
0x180023ad4  mov     r9, rbx
0x180023ad7  mov     r8, r14
0x180023ada  mov     rdx, [rbp+37h+var_A0]
0x180023ade  mov     rcx, rdi
0x180023ae1  call    ??$FormatArguments@GGGGG@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2222@Z; ArgumentWriter::FormatArguments<ushort,ushort,ushort,ushort,ushort>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ushort const &,ushort const &,ushort const &)
0x180023ae6  nop
0x180023ae7  mov     rax, qword ptr [rbp+37h+var_58+8]
0x180023aeb  cmp     rax, 7
0x180023aef  jbe     loc_180023A68
0x180023af5  mov     rcx, [rbp+37h+Block]; Block
0x180023af9  mov     rdx, rcx
0x180023afc  lea     rax, ds:2[rax*2]
0x180023b04  cmp     rax, 1000h
0x180023b0a  jb      short loc_180023B33
0x180023b0c  mov     rcx, [rcx-8]
0x180023b10  sub     rdx, rcx
0x180023b13  lea     rax, [rdx-8]
0x180023b17  cmp     rax, 1Fh
0x180023b1b  jbe     short loc_180023B33
0x180023b1d  mov     [rsp+0F0h+Reserved], r15; Reserved
0x180023b22  xor     r9d, r9d; LineNo
0x180023b25  xor     r8d, r8d; FileName
0x180023b28  xor     edx, edx; FunctionName
0x180023b2a  xor     ecx, ecx; Expression
0x180023b2c  call    cs:__imp__invoke_watson
0x180023b33  call    cs:__imp_free
0x180023b39  jmp     loc_180023A68
```

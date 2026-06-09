# ArgumentWriter::Format<char [255],ulong>(wchar_t const *,unsigned __int64,char const (&)[255],ulong const &)

- ea: `0x180005858`
- end: `0x180005b07`
- name: `??$Format@$$BY0PP@DK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEAY0PP@$$CBDAEBK@Z`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180005804`

## callees

- `0x180001bac`
- `0x180001f38`
- `0x180003f4c`
- `0x1800041d4`
- `0x1800045ec`
- `0x1800046d8`
- `0x180004994`
- `0x180005858`
- `0x180005b0c`
- `0x1800266e0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005a77`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005ac5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005a77`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180005ac5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005a7e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005acc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005a7e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180005acc`

## string_xrefs

- `0x1800058c1`: `Begin Interceptor.dll log for %s (PID=%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ArgumentWriter::Format<char [255],unsigned long>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  const wchar_t *v6; // rdi
  __m128i si128; // xmm6
  wchar_t v8; // r8
  wchar_t *v9; // rsi
  unsigned __int64 v10; // rdi
  void **v11; // rsi
  __int64 v12; // rcx
  void *v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  _QWORD v17[3]; // [rsp+30h] [rbp-51h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp-29h]
  unsigned __int64 v20; // [rsp+60h] [rbp-21h]
  void *Block[2]; // [rsp+68h] [rbp-19h] BYREF
  __m128i v22; // [rsp+78h] [rbp-9h]

  v17[2] = a1;
  *(_OWORD *)Src = 0;
  v19 = 0;
  v20 = 7;
  LOWORD(Src[0]) = 0;
  ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
  v19 = 0;
  v6 = L"Begin Interceptor.dll log for %s (PID=%d)";
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v22 = si128;
    LOWORD(Block[0]) = 0;
    v8 = *v6;
    v9 = (wchar_t *)(v6 + 1);
    v6 = v9;
    v17[0] = v9;
    if ( v8 == 37 )
      break;
    std::wstring::append(Src);
LABEL_9:
    std::wstring::_Tidy_deallocate(Block);
    if ( v6 >= L"" )
    {
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v10 = v19;
      v11 = Src;
      if ( v20 > 7 )
        v11 = (void **)Src[0];
      v12 = 0x7FFFFFFFFFFFFFFELL;
      if ( v19 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v19 > 7 )
      {
        if ( (v19 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          v12 = v19 | 7;
          if ( (v19 | 7) < 0xA )
            v12 = 10;
        }
        v17[0] = v12;
        v13 = (void *)std::wstring::_Allocate_for_capacity<0>(a1, v17);
        *(_QWORD *)a1 = v13;
        *(_QWORD *)(a1 + 16) = v10;
        *(_QWORD *)(a1 + 24) = v17[0];
        memmove(v13, v11, 2 * v10 + 2);
      }
      else
      {
        *(_QWORD *)(a1 + 16) = v19;
        *(_QWORD *)(a1 + 24) = 7;
        *(_OWORD *)a1 = *(_OWORD *)v11;
      }
      goto LABEL_24;
    }
  }
  if ( v9 != L"" && *v9 == 37 )
  {
    std::wstring::append(Src);
    v6 = v9 + 1;
    goto LABEL_9;
  }
  if ( !(unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", Src, Block) )
  {
    v6 = (const wchar_t *)v17[0];
    goto LABEL_9;
  }
  _mm_lfence();
  OFormat::ValueFormatter<char [255]>::FormatValue(Src);
  ArgumentWriter::FormatArguments<unsigned long,>(a1, v17[0], L"", Src, a5);
  if ( v22.m128i_i64[1] > 7uLL )
  {
    v14 = Block[0];
    if ( (unsigned __int64)(2 * v22.m128i_i64[1] + 2) >= 0x1000 )
    {
      v14 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v14);
  }
LABEL_24:
  if ( v20 > 7 )
  {
    v15 = Src[0];
    if ( 2 * v20 + 2 >= 0x1000 )
    {
      v15 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v15 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v15);
  }
  return a1;
}

```

## disassembly

```asm
0x180005858  mov     rax, rsp
0x18000585b  mov     [rax+10h], rbx
0x18000585f  push    rbp
0x180005860  push    rsi
0x180005861  push    rdi
0x180005862  push    r12
0x180005864  push    r13
0x180005866  push    r14
0x180005868  push    r15
0x18000586a  lea     rbp, [rax-57h]
0x18000586e  sub     rsp, 0A0h
0x180005875  movaps  xmmword ptr [rax-48h], xmm6
0x180005879  mov     rax, cs:__security_cookie
0x180005880  xor     rax, rsp
0x180005883  mov     [rbp+4Fh+var_48], rax
0x180005887  mov     r14, r9
0x18000588a  mov     rbx, rcx
0x18000588d  mov     [rbp+4Fh+var_90], rcx
0x180005891  mov     r15, [rbp+4Fh+arg_20]
0x180005895  xor     r13d, r13d
0x180005898  xorps   xmm0, xmm0
0x18000589b  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x18000589f  mov     [rbp+4Fh+var_78], r13
0x1800058a3  lea     r12d, [r13+7]
0x1800058a7  mov     [rbp+4Fh+var_70], r12
0x1800058ab  mov     word ptr [rbp+4Fh+Src], r13w
0x1800058b0  lea     edx, [r13+52h]
0x1800058b4  lea     rcx, [rbp+4Fh+Src]; Src
0x1800058b8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x1800058bd  mov     [rbp+4Fh+var_78], r13
0x1800058c1  lea     rdi, aBeginIntercept; "Begin Interceptor.dll log for %s (PID=%"...
0x1800058c8  lea     ecx, [r13+25h]
0x1800058cc  lea     rax, aBeginIntercept+52h; ""
0x1800058d3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800058db  xorps   xmm0, xmm0
0x1800058de  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x1800058e2  movdqu  [rbp+4Fh+var_58], xmm6
0x1800058e7  mov     word ptr [rbp+4Fh+Block], r13w
0x1800058ec  movzx   r8d, word ptr [rdi]
0x1800058f0  lea     rsi, [rdi+2]
0x1800058f4  mov     rdi, rsi
0x1800058f7  mov     [rbp+4Fh+var_A0], rsi
0x1800058fb  cmp     r8w, cx
0x1800058ff  jz      short loc_180005911
0x180005901  mov     edx, 1
0x180005906  lea     rcx, [rbp+4Fh+Src]; Src
0x18000590a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18000590f  jmp     short loc_180005952
0x180005911  cmp     rsi, rax
0x180005914  jz      short loc_180005932
0x180005916  cmp     [rsi], cx
0x180005919  jnz     short loc_180005932
0x18000591b  mov     r8d, ecx
0x18000591e  mov     edx, 1
0x180005923  lea     rcx, [rbp+4Fh+Src]; Src
0x180005927  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18000592c  lea     rdi, [rsi+2]
0x180005930  jmp     short loc_180005952
0x180005932  lea     r9, [rbp+4Fh+Block]
0x180005936  lea     r8, [rbp+4Fh+Src]
0x18000593a  mov     rdx, rax
0x18000593d  lea     rcx, [rbp+4Fh+var_A0]
0x180005941  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180005946  test    al, al
0x180005948  jnz     loc_180005A07
0x18000594e  mov     rdi, [rbp+4Fh+var_A0]
0x180005952  lea     rcx, [rbp+4Fh+Block]
0x180005956  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000595b  lea     rax, aBeginIntercept+52h; ""
0x180005962  cmp     rdi, rax
0x180005965  mov     ecx, 25h ; '%'
0x18000596a  jb      loc_1800058DB
0x180005970  xorps   xmm0, xmm0
0x180005973  movups  xmmword ptr [rbx], xmm0
0x180005976  mov     [rbx+10h], r13
0x18000597a  mov     [rbx+18h], r13
0x18000597e  mov     rdi, [rbp+4Fh+var_78]
0x180005982  lea     rsi, [rbp+4Fh+Src]
0x180005986  cmp     [rbp+4Fh+var_70], r12
0x18000598a  cmova   rsi, [rbp+4Fh+Src]
0x18000598f  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180005999  cmp     rdi, rcx
0x18000599c  ja      loc_180005B01
0x1800059a2  cmp     rdi, r12
0x1800059a5  ja      short loc_1800059B8
0x1800059a7  mov     [rbx+10h], rdi
0x1800059ab  mov     [rbx+18h], r12
0x1800059af  movups  xmm0, xmmword ptr [rsi]
0x1800059b2  movdqu  xmmword ptr [rbx], xmm0
0x1800059b6  jmp     short loc_180005A05
0x1800059b8  mov     rax, rdi
0x1800059bb  or      rax, r12
0x1800059be  cmp     rax, rcx
0x1800059c1  ja      short loc_1800059D2
0x1800059c3  mov     rcx, rax
0x1800059c6  mov     edx, 0Ah
0x1800059cb  cmp     rax, rdx
0x1800059ce  cmovb   rcx, rdx
0x1800059d2  mov     [rbp+4Fh+var_A0], rcx
0x1800059d6  lea     rdx, [rbp+4Fh+var_A0]
0x1800059da  mov     rcx, rbx
0x1800059dd  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x1800059e2  mov     [rbx], rax
0x1800059e5  mov     [rbx+10h], rdi
0x1800059e9  mov     rcx, [rbp+4Fh+var_A0]
0x1800059ed  mov     [rbx+18h], rcx
0x1800059f1  lea     r8, ds:2[rdi*2]; Size
0x1800059f9  mov     rdx, rsi; Src
0x1800059fc  mov     rcx, rax; void *
0x1800059ff  call    memmove
0x180005a04  nop
0x180005a05  jmp     short loc_180005A85
0x180005a07  lfence
0x180005a0a  mov     r8, r14
0x180005a0d  lea     rdx, [rbp+4Fh+Block]
0x180005a11  lea     rcx, [rbp+4Fh+Src]; Src
0x180005a15  call    ?FormatValue@?$ValueFormatter@$$BY0PP@D@OFormat@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@PEBD@Z; OFormat::ValueFormatter<char [255]>::FormatValue(std::wstring &,std::wstring const &,char const *)
0x180005a1a  mov     [rsp+0D0h+Reserved], r15
0x180005a1f  lea     r9, [rbp+4Fh+Src]
0x180005a23  lea     r8, aBeginIntercept+52h; ""
0x180005a2a  mov     rdx, [rbp+4Fh+var_A0]
0x180005a2e  mov     rcx, rbx
0x180005a31  call    ??$FormatArguments@K$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBK@Z; ArgumentWriter::FormatArguments<ulong,>(wchar_t const *,wchar_t const *,std::wstring &,ulong const &)
0x180005a36  nop
0x180005a37  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x180005a3b  cmp     rax, r12
0x180005a3e  jbe     short loc_180005A85
0x180005a40  mov     rcx, [rbp+4Fh+Block]; Block
0x180005a44  mov     rdx, rcx
0x180005a47  lea     rax, ds:2[rax*2]
0x180005a4f  cmp     rax, 1000h
0x180005a55  jb      short loc_180005A7E
0x180005a57  mov     rcx, [rcx-8]
0x180005a5b  sub     rdx, rcx
0x180005a5e  lea     rax, [rdx-8]
0x180005a62  cmp     rax, 1Fh
0x180005a66  jbe     short loc_180005A7E
0x180005a68  mov     [rsp+0D0h+Reserved], r13; Reserved
0x180005a6d  xor     r9d, r9d; LineNo
0x180005a70  xor     r8d, r8d; FileName
0x180005a73  xor     edx, edx; FunctionName
0x180005a75  xor     ecx, ecx; Expression
0x180005a77  call    cs:__imp__invoke_watson
0x180005a7e  call    cs:__imp_free
0x180005a84  nop
0x180005a85  mov     rax, [rbp+4Fh+var_70]
0x180005a89  cmp     rax, r12
0x180005a8c  jbe     short loc_180005AD2
0x180005a8e  mov     rcx, [rbp+4Fh+Src]; Block
0x180005a92  mov     rdx, rcx
0x180005a95  lea     rax, ds:2[rax*2]
0x180005a9d  cmp     rax, 1000h
0x180005aa3  jb      short loc_180005ACC
0x180005aa5  mov     rcx, [rcx-8]
0x180005aa9  sub     rdx, rcx
0x180005aac  lea     rax, [rdx-8]
0x180005ab0  cmp     rax, 1Fh
0x180005ab4  jbe     short loc_180005ACC
0x180005ab6  mov     [rsp+0D0h+Reserved], r13; Reserved
0x180005abb  xor     r9d, r9d; LineNo
0x180005abe  xor     r8d, r8d; FileName
0x180005ac1  xor     edx, edx; FunctionName
0x180005ac3  xor     ecx, ecx; Expression
0x180005ac5  call    cs:__imp__invoke_watson
0x180005acc  call    cs:__imp_free
0x180005ad2  mov     rax, rbx
0x180005ad5  mov     rcx, [rbp+4Fh+var_48]
0x180005ad9  xor     rcx, rsp; StackCookie
0x180005adc  call    __security_check_cookie
0x180005ae1  lea     r11, [rsp+0D0h+var_30]
0x180005ae9  mov     rbx, [r11+48h]
0x180005aed  movaps  xmm6, xmmword ptr [r11-10h]
0x180005af2  mov     rsp, r11
0x180005af5  pop     r15
0x180005af7  pop     r14
0x180005af9  pop     r13
0x180005afb  pop     r12
0x180005afd  pop     rdi
0x180005afe  pop     rsi
0x180005aff  pop     rbp
0x180005b00  retn
0x180005b01  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```

# ArgumentWriter::Format<long>(wchar_t const *,unsigned __int64,long const &)

- ea: `0x180009c90`
- end: `0x180009f3e`
- name: `??$Format@J@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBJ@Z`
- size: `686`
- prototype: ``
- caller_count: `10`
- callee_count: `11`
- tags: ``

## callers

- `0x180007f80`
- `0x180007fdc`
- `0x180008094`
- `0x1800080e8`
- `0x18000813c`
- `0x1800081f4`
- `0x180008430`
- `0x18000848c`
- `0x180008540`
- `0x18000859c`

## callees

- `0x180001bac`
- `0x180001bc0`
- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x1800041d4`
- `0x1800045ec`
- `0x1800046d8`
- `0x180009c90`
- `0x1800266e0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009e64`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009f00`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009e64`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180009f00`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009e6b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009f07`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009e6b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180009f07`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 __fastcall ArgumentWriter::Format<long>(unsigned __int64 a1, unsigned __int16 *a2, __int64 a3)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // r14
  unsigned __int16 *v7; // r14
  __m128i si128; // xmm6
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // rbx
  void **v11; // rdi
  __int64 v12; // rcx
  void *v13; // rcx
  void *v14; // rax
  void *v15; // rcx
  unsigned __int64 v17[3]; // [rsp+30h] [rbp-59h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp-31h]
  unsigned __int64 v20; // [rsp+60h] [rbp-29h]
  void *Block[2]; // [rsp+68h] [rbp-21h] BYREF
  __m128i v22; // [rsp+78h] [rbp-11h]

  v17[2] = a1;
  *(_OWORD *)Src = 0;
  v5 = 0;
  v19 = 0;
  v20 = 7;
  LOWORD(Src[0]) = 0;
  v6 = a3;
  if ( (unsigned __int64)(2 * a3) > 7 )
  {
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
    v19 = 0;
  }
  v7 = &a2[v6];
  if ( a2 >= v7 )
  {
LABEL_14:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v11 = Src;
    if ( v20 > 7 )
      v11 = (void **)Src[0];
    v12 = 0x7FFFFFFFFFFFFFFELL;
    if ( v5 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v5 > 7 )
    {
      if ( (v5 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v12 = v5 | 7;
        if ( (v5 | 7) < 0xA )
          v12 = 10;
      }
      v17[0] = v12;
      v14 = (void *)std::wstring::_Allocate_for_capacity<0>(a1, v17);
      *(_QWORD *)a1 = v14;
      *(_QWORD *)(a1 + 16) = v5;
      *(_QWORD *)(a1 + 24) = v17[0];
      memmove(v14, v11, 2 * v5 + 2);
    }
    else
    {
      *(_QWORD *)(a1 + 16) = v5;
      *(_QWORD *)(a1 + 24) = 7;
      *(_OWORD *)a1 = *(_OWORD *)v11;
    }
    goto LABEL_28;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v22 = si128;
    LOWORD(Block[0]) = 0;
    v9 = *a2;
    v10 = a2 + 1;
    a2 = v10;
    v17[0] = (unsigned __int64)v10;
    if ( v9 == 37 )
      break;
    std::wstring::append(Src);
LABEL_12:
    std::wstring::_Tidy_deallocate(Block);
    if ( a2 >= v7 )
    {
      v5 = v19;
      goto LABEL_14;
    }
  }
  if ( v10 != v7 && *v10 == 37 )
  {
    std::wstring::append(Src);
    a2 = v10 + 1;
    goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField(v17, v7, Src, (__int64)Block) )
  {
    a2 = (unsigned __int16 *)v17[0];
    goto LABEL_12;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(Src, (wchar_t *)Block);
  ArgumentWriter::FormatArguments(a1, v17[0], v7, Src);
  if ( v22.m128i_i64[1] > 7uLL )
  {
    v13 = Block[0];
    if ( (unsigned __int64)(2 * v22.m128i_i64[1] + 2) >= 0x1000 )
    {
      v13 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v13);
  }
LABEL_28:
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
0x180009c90  mov     rax, rsp
0x180009c93  push    rbp
0x180009c94  push    rbx
0x180009c95  push    rsi
0x180009c96  push    rdi
0x180009c97  push    r12
0x180009c99  push    r13
0x180009c9b  push    r14
0x180009c9d  push    r15
0x180009c9f  lea     rbp, [rax-5Fh]
0x180009ca3  sub     rsp, 0A8h
0x180009caa  movaps  xmmword ptr [rax-58h], xmm6
0x180009cae  mov     rax, cs:__security_cookie
0x180009cb5  xor     rax, rsp
0x180009cb8  mov     qword ptr [rbp+57h+var_58], rax
0x180009cbc  mov     r15, r9
0x180009cbf  mov     rdi, rdx
0x180009cc2  mov     rsi, rcx
0x180009cc5  mov     [rbp+57h+var_A0], rcx
0x180009cc9  xor     r12d, r12d
0x180009ccc  xorps   xmm0, xmm0
0x180009ccf  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180009cd3  mov     ebx, r12d
0x180009cd6  mov     [rbp+57h+var_88], rbx
0x180009cda  lea     r13d, [r12+7]
0x180009cdf  mov     [rbp+57h+var_80], r13
0x180009ce3  mov     word ptr [rbp+57h+Src], r12w
0x180009ce8  lea     r14, [r8+r8]
0x180009cec  cmp     r14, r13
0x180009cef  jbe     short loc_180009D04
0x180009cf1  lfence
0x180009cf4  mov     rdx, r14
0x180009cf7  lea     rcx, [rbp+57h+Src]; Src
0x180009cfb  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180009d00  mov     [rbp+57h+var_88], rbx
0x180009d04  add     r14, rdi
0x180009d07  cmp     rdi, r14
0x180009d0a  jnb     loc_180009DAE
0x180009d10  lfence
0x180009d13  mov     eax, 25h ; '%'
0x180009d18  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180009d20  xorps   xmm0, xmm0
0x180009d23  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180009d27  movdqu  [rbp+57h+var_68], xmm6
0x180009d2c  mov     word ptr [rbp+57h+Block], r12w
0x180009d31  movzx   r8d, word ptr [rdi]
0x180009d35  lea     rbx, [rdi+2]
0x180009d39  mov     rdi, rbx
0x180009d3c  mov     [rbp+57h+var_B0], rbx
0x180009d40  cmp     r8w, ax
0x180009d44  jz      short loc_180009D56
0x180009d46  mov     edx, 1
0x180009d4b  lea     rcx, [rbp+57h+Src]; Src
0x180009d4f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180009d54  jmp     short loc_180009D93
0x180009d56  cmp     rbx, r14
0x180009d59  jz      short loc_180009D77
0x180009d5b  cmp     [rbx], ax
0x180009d5e  jnz     short loc_180009D77
0x180009d60  mov     r8d, eax
0x180009d63  mov     edx, 1
0x180009d68  lea     rcx, [rbp+57h+Src]; Src
0x180009d6c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180009d71  lea     rdi, [rbx+2]
0x180009d75  jmp     short loc_180009D93
0x180009d77  lea     r9, [rbp+57h+Block]
0x180009d7b  lea     r8, [rbp+57h+Src]
0x180009d7f  mov     rdx, r14
0x180009d82  lea     rcx, [rbp+57h+var_B0]
0x180009d86  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180009d8b  test    al, al
0x180009d8d  jnz     short loc_180009DF9
0x180009d8f  mov     rdi, [rbp+57h+var_B0]
0x180009d93  lea     rcx, [rbp+57h+Block]
0x180009d97  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009d9c  cmp     rdi, r14
0x180009d9f  mov     eax, 25h ; '%'
0x180009da4  jb      loc_180009D20
0x180009daa  mov     rbx, [rbp+57h+var_88]
0x180009dae  xorps   xmm0, xmm0
0x180009db1  movups  xmmword ptr [rsi], xmm0
0x180009db4  mov     [rsi+10h], r12
0x180009db8  mov     [rsi+18h], r12
0x180009dbc  lea     rdi, [rbp+57h+Src]
0x180009dc0  cmp     [rbp+57h+var_80], r13
0x180009dc4  cmova   rdi, [rbp+57h+Src]
0x180009dc9  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180009dd3  cmp     rbx, rcx
0x180009dd6  ja      loc_180009F38
0x180009ddc  cmp     rbx, r13
0x180009ddf  ja      loc_180009E73
0x180009de5  mov     [rsi+10h], rbx
0x180009de9  mov     [rsi+18h], r13
0x180009ded  movups  xmm0, xmmword ptr [rdi]
0x180009df0  movdqu  xmmword ptr [rsi], xmm0
0x180009df4  jmp     loc_180009EC0
0x180009df9  lfence
0x180009dfc  movsxd  r8, dword ptr [r15]
0x180009dff  lea     rdx, [rbp+57h+Block]; Format
0x180009e03  lea     rcx, [rbp+57h+Src]; Src
0x180009e07  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180009e0c  lea     r9, [rbp+57h+Src]
0x180009e10  mov     r8, r14
0x180009e13  mov     rdx, [rbp+57h+var_B0]
0x180009e17  mov     rcx, rsi
0x180009e1a  call    ?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z; ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::wstring &)
0x180009e1f  nop
0x180009e20  mov     rax, qword ptr [rbp+57h+var_68+8]
0x180009e24  cmp     rax, r13
0x180009e27  jbe     loc_180009EC0
0x180009e2d  mov     rcx, [rbp+57h+Block]; Block
0x180009e31  mov     rdx, rcx
0x180009e34  lea     rax, ds:2[rax*2]
0x180009e3c  cmp     rax, 1000h
0x180009e42  jb      short loc_180009E6B
0x180009e44  mov     rcx, [rcx-8]
0x180009e48  sub     rdx, rcx
0x180009e4b  lea     rax, [rdx-8]
0x180009e4f  cmp     rax, 1Fh
0x180009e53  jbe     short loc_180009E6B
0x180009e55  mov     [rsp+0E0h+Reserved], r12; Reserved
0x180009e5a  xor     r9d, r9d; LineNo
0x180009e5d  xor     r8d, r8d; FileName
0x180009e60  xor     edx, edx; FunctionName
0x180009e62  xor     ecx, ecx; Expression
0x180009e64  call    cs:__imp__invoke_watson
0x180009e6b  call    cs:__imp_free
0x180009e71  jmp     short loc_180009EC0
0x180009e73  mov     rax, rbx
0x180009e76  or      rax, r13
0x180009e79  cmp     rax, rcx
0x180009e7c  ja      short loc_180009E8D
0x180009e7e  mov     rcx, rax
0x180009e81  mov     edx, 0Ah
0x180009e86  cmp     rax, rdx
0x180009e89  cmovb   rcx, rdx
0x180009e8d  mov     [rbp+57h+var_B0], rcx
0x180009e91  lea     rdx, [rbp+57h+var_B0]
0x180009e95  mov     rcx, rsi
0x180009e98  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180009e9d  mov     [rsi], rax
0x180009ea0  mov     [rsi+10h], rbx
0x180009ea4  mov     rcx, [rbp+57h+var_B0]
0x180009ea8  mov     [rsi+18h], rcx
0x180009eac  lea     r8, ds:2[rbx*2]; Size
0x180009eb4  mov     rdx, rdi; Src
0x180009eb7  mov     rcx, rax; void *
0x180009eba  call    memmove
0x180009ebf  nop
0x180009ec0  mov     rax, [rbp+57h+var_80]
0x180009ec4  cmp     rax, r13
0x180009ec7  jbe     short loc_180009F0D
0x180009ec9  mov     rcx, [rbp+57h+Src]; Block
0x180009ecd  mov     rdx, rcx
0x180009ed0  lea     rax, ds:2[rax*2]
0x180009ed8  cmp     rax, 1000h
0x180009ede  jb      short loc_180009F07
0x180009ee0  mov     rcx, [rcx-8]
0x180009ee4  sub     rdx, rcx
0x180009ee7  lea     rax, [rdx-8]
0x180009eeb  cmp     rax, 1Fh
0x180009eef  jbe     short loc_180009F07
0x180009ef1  mov     [rsp+0E0h+Reserved], r12; Reserved
0x180009ef6  xor     r9d, r9d; LineNo
0x180009ef9  xor     r8d, r8d; FileName
0x180009efc  xor     edx, edx; FunctionName
0x180009efe  xor     ecx, ecx; Expression
0x180009f00  call    cs:__imp__invoke_watson
0x180009f07  call    cs:__imp_free
0x180009f0d  mov     rax, rsi
0x180009f10  mov     rcx, qword ptr [rbp+57h+var_58]
0x180009f14  xor     rcx, rsp; StackCookie
0x180009f17  call    __security_check_cookie
0x180009f1c  movaps  xmm6, [rsp+0E0h+var_58+8]
0x180009f24  add     rsp, 0A8h
0x180009f2b  pop     r15
0x180009f2d  pop     r14
0x180009f2f  pop     r13
0x180009f31  pop     r12
0x180009f33  pop     rdi
0x180009f34  pop     rsi
0x180009f35  pop     rbx
0x180009f36  pop     rbp
0x180009f37  retn
0x180009f38  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```

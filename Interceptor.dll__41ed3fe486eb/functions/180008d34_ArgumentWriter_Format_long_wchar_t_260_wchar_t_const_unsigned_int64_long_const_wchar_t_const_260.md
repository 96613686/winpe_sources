# ArgumentWriter::Format<long,wchar_t [260]>(wchar_t const *,unsigned __int64,long const &,wchar_t const (&)[260])

- ea: `0x180008d34`
- end: `0x180008ff4`
- name: `??$Format@J$$BY0BAE@_W@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBJAEAY0BAE@$$CB_W@Z`
- size: `704`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x180008250`
- `0x1800082b0`
- `0x180008310`
- `0x180008370`
- `0x1800083d0`

## callees

- `0x180001bac`
- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x1800041d4`
- `0x1800045ec`
- `0x1800046d8`
- `0x180008d34`
- `0x180009244`
- `0x1800266e0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008f18`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008fb6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008f18`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008fb6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180008f1f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180008fbd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180008f1f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180008fbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 __fastcall ArgumentWriter::Format<long,wchar_t [260]>(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v7; // rbx
  __int64 v8; // r14
  unsigned __int16 *v9; // r14
  __m128i si128; // xmm6
  unsigned __int16 v11; // r8
  unsigned __int16 *v12; // rbx
  void **v13; // rsi
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rax
  void *v17; // rcx
  unsigned __int64 v19[3]; // [rsp+30h] [rbp-61h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-39h]
  unsigned __int64 v22; // [rsp+60h] [rbp-31h]
  void *Block[2]; // [rsp+68h] [rbp-29h] BYREF
  __m128i v24; // [rsp+78h] [rbp-19h]

  v19[2] = a1;
  *(_OWORD *)Src = 0;
  v7 = 0;
  v21 = 0;
  v22 = 7;
  LOWORD(Src[0]) = 0;
  v8 = a3;
  if ( (unsigned __int64)(2 * a3) > 7 )
  {
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
    v21 = 0;
  }
  v9 = &a2[v8];
  if ( a2 >= v9 )
  {
LABEL_14:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v13 = Src;
    if ( v22 > 7 )
      v13 = (void **)Src[0];
    v14 = 0x7FFFFFFFFFFFFFFELL;
    if ( v7 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v7 > 7 )
    {
      if ( (v7 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v14 = v7 | 7;
        if ( (v7 | 7) < 0xA )
          v14 = 10;
      }
      v19[0] = v14;
      v16 = (void *)std::wstring::_Allocate_for_capacity<0>(a1, v19);
      *(_QWORD *)a1 = v16;
      *(_QWORD *)(a1 + 16) = v7;
      *(_QWORD *)(a1 + 24) = v19[0];
      memmove(v16, v13, 2 * v7 + 2);
    }
    else
    {
      *(_QWORD *)(a1 + 16) = v7;
      *(_QWORD *)(a1 + 24) = 7;
      *(_OWORD *)a1 = *(_OWORD *)v13;
    }
    goto LABEL_28;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v24 = si128;
    LOWORD(Block[0]) = 0;
    v11 = *a2;
    v12 = a2 + 1;
    a2 = v12;
    v19[0] = (unsigned __int64)v12;
    if ( v11 == 37 )
      break;
    std::wstring::append(Src);
LABEL_12:
    std::wstring::_Tidy_deallocate(Block);
    if ( a2 >= v9 )
    {
      v7 = v21;
      goto LABEL_14;
    }
  }
  if ( v12 != v9 && *v12 == 37 )
  {
    std::wstring::append(Src);
    a2 = v12 + 1;
    goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField(v19, v9, Src, (__int64)Block) )
  {
    a2 = (unsigned __int16 *)v19[0];
    goto LABEL_12;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(Src, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<wchar_t [64],>(a1, v19[0], v9, Src, a5);
  if ( v24.m128i_i64[1] > 7uLL )
  {
    v15 = Block[0];
    if ( (unsigned __int64)(2 * v24.m128i_i64[1] + 2) >= 0x1000 )
    {
      v15 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v15 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v15);
  }
LABEL_28:
  if ( v22 > 7 )
  {
    v17 = Src[0];
    if ( 2 * v22 + 2 >= 0x1000 )
    {
      v17 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  return a1;
}

```

## disassembly

```asm
0x180008d34  mov     rax, rsp
0x180008d37  push    rbp
0x180008d38  push    rbx
0x180008d39  push    rsi
0x180008d3a  push    rdi
0x180008d3b  push    r12
0x180008d3d  push    r13
0x180008d3f  push    r14
0x180008d41  push    r15
0x180008d43  lea     rbp, [rax-57h]
0x180008d47  sub     rsp, 0A8h
0x180008d4e  movaps  xmmword ptr [rax-58h], xmm6
0x180008d52  mov     rax, cs:__security_cookie
0x180008d59  xor     rax, rsp
0x180008d5c  mov     qword ptr [rbp+4Fh+var_58], rax
0x180008d60  mov     r15, r9
0x180008d63  mov     rsi, rdx
0x180008d66  mov     rdi, rcx
0x180008d69  mov     [rbp+4Fh+var_A0], rcx
0x180008d6d  mov     r12, [rbp+4Fh+arg_20]
0x180008d71  xor     r13d, r13d
0x180008d74  xorps   xmm0, xmm0
0x180008d77  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x180008d7b  mov     ebx, r13d
0x180008d7e  mov     [rbp+4Fh+var_88], rbx
0x180008d82  mov     [rbp+4Fh+var_80], 7
0x180008d8a  mov     word ptr [rbp+4Fh+Src], r13w
0x180008d8f  lea     r14, [r8+r8]
0x180008d93  cmp     r14, 7
0x180008d97  jbe     short loc_180008DAC
0x180008d99  lfence
0x180008d9c  mov     rdx, r14
0x180008d9f  lea     rcx, [rbp+4Fh+Src]; Src
0x180008da3  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180008da8  mov     [rbp+4Fh+var_88], rbx
0x180008dac  add     r14, rsi
0x180008daf  cmp     rsi, r14
0x180008db2  jnb     loc_180008E56
0x180008db8  lfence
0x180008dbb  mov     eax, 25h ; '%'
0x180008dc0  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180008dc8  xorps   xmm0, xmm0
0x180008dcb  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x180008dcf  movdqu  [rbp+4Fh+var_68], xmm6
0x180008dd4  mov     word ptr [rbp+4Fh+Block], r13w
0x180008dd9  movzx   r8d, word ptr [rsi]
0x180008ddd  lea     rbx, [rsi+2]
0x180008de1  mov     rsi, rbx
0x180008de4  mov     [rbp+4Fh+var_B0], rbx
0x180008de8  cmp     r8w, ax
0x180008dec  jz      short loc_180008DFE
0x180008dee  mov     edx, 1
0x180008df3  lea     rcx, [rbp+4Fh+Src]; Src
0x180008df7  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180008dfc  jmp     short loc_180008E3B
0x180008dfe  cmp     rbx, r14
0x180008e01  jz      short loc_180008E1F
0x180008e03  cmp     [rbx], ax
0x180008e06  jnz     short loc_180008E1F
0x180008e08  mov     r8d, eax
0x180008e0b  mov     edx, 1
0x180008e10  lea     rcx, [rbp+4Fh+Src]; Src
0x180008e14  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180008e19  lea     rsi, [rbx+2]
0x180008e1d  jmp     short loc_180008E3B
0x180008e1f  lea     r9, [rbp+4Fh+Block]
0x180008e23  lea     r8, [rbp+4Fh+Src]
0x180008e27  mov     rdx, r14
0x180008e2a  lea     rcx, [rbp+4Fh+var_B0]
0x180008e2e  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180008e33  test    al, al
0x180008e35  jnz     short loc_180008EA7
0x180008e37  mov     rsi, [rbp+4Fh+var_B0]
0x180008e3b  lea     rcx, [rbp+4Fh+Block]
0x180008e3f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008e44  cmp     rsi, r14
0x180008e47  mov     eax, 25h ; '%'
0x180008e4c  jb      loc_180008DC8
0x180008e52  mov     rbx, [rbp+4Fh+var_88]
0x180008e56  xorps   xmm0, xmm0
0x180008e59  movups  xmmword ptr [rdi], xmm0
0x180008e5c  mov     [rdi+10h], r13
0x180008e60  mov     [rdi+18h], r13
0x180008e64  lea     rsi, [rbp+4Fh+Src]
0x180008e68  cmp     [rbp+4Fh+var_80], 7
0x180008e6d  cmova   rsi, [rbp+4Fh+Src]
0x180008e72  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180008e7c  cmp     rbx, rcx
0x180008e7f  ja      loc_180008FEE
0x180008e85  cmp     rbx, 7
0x180008e89  ja      loc_180008F27
0x180008e8f  mov     [rdi+10h], rbx
0x180008e93  mov     qword ptr [rdi+18h], 7
0x180008e9b  movups  xmm0, xmmword ptr [rsi]
0x180008e9e  movdqu  xmmword ptr [rdi], xmm0
0x180008ea2  jmp     loc_180008F75
0x180008ea7  lfence
0x180008eaa  movsxd  r8, dword ptr [r15]
0x180008ead  lea     rdx, [rbp+4Fh+Block]; Format
0x180008eb1  lea     rcx, [rbp+4Fh+Src]; Src
0x180008eb5  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180008eba  mov     [rsp+0E0h+Reserved], r12
0x180008ebf  lea     r9, [rbp+4Fh+Src]
0x180008ec3  mov     r8, r14
0x180008ec6  mov     rdx, [rbp+4Fh+var_B0]
0x180008eca  mov     rcx, rdi
0x180008ecd  call    ??$FormatArguments@$$BY0EA@_W$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEAY0EA@$$CB_W@Z; ArgumentWriter::FormatArguments<wchar_t [64],>(wchar_t const *,wchar_t const *,std::wstring &,wchar_t const (&)[64])
0x180008ed2  nop
0x180008ed3  mov     rax, qword ptr [rbp+4Fh+var_68+8]
0x180008ed7  cmp     rax, 7
0x180008edb  jbe     loc_180008F75
0x180008ee1  mov     rcx, [rbp+4Fh+Block]; Block
0x180008ee5  mov     rdx, rcx
0x180008ee8  lea     rax, ds:2[rax*2]
0x180008ef0  cmp     rax, 1000h
0x180008ef6  jb      short loc_180008F1F
0x180008ef8  mov     rcx, [rcx-8]
0x180008efc  sub     rdx, rcx
0x180008eff  lea     rax, [rdx-8]
0x180008f03  cmp     rax, 1Fh
0x180008f07  jbe     short loc_180008F1F
0x180008f09  mov     [rsp+0E0h+Reserved], r13; Reserved
0x180008f0e  xor     r9d, r9d; LineNo
0x180008f11  xor     r8d, r8d; FileName
0x180008f14  xor     edx, edx; FunctionName
0x180008f16  xor     ecx, ecx; Expression
0x180008f18  call    cs:__imp__invoke_watson
0x180008f1f  call    cs:__imp_free
0x180008f25  jmp     short loc_180008F75
0x180008f27  mov     rax, rbx
0x180008f2a  or      rax, 7
0x180008f2e  cmp     rax, rcx
0x180008f31  ja      short loc_180008F42
0x180008f33  mov     rcx, rax
0x180008f36  mov     edx, 0Ah
0x180008f3b  cmp     rax, rdx
0x180008f3e  cmovb   rcx, rdx
0x180008f42  mov     [rbp+4Fh+var_B0], rcx
0x180008f46  lea     rdx, [rbp+4Fh+var_B0]
0x180008f4a  mov     rcx, rdi
0x180008f4d  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180008f52  mov     [rdi], rax
0x180008f55  mov     [rdi+10h], rbx
0x180008f59  mov     rcx, [rbp+4Fh+var_B0]
0x180008f5d  mov     [rdi+18h], rcx
0x180008f61  lea     r8, ds:2[rbx*2]; Size
0x180008f69  mov     rdx, rsi; Src
0x180008f6c  mov     rcx, rax; void *
0x180008f6f  call    memmove
0x180008f74  nop
0x180008f75  mov     rax, [rbp+4Fh+var_80]
0x180008f79  cmp     rax, 7
0x180008f7d  jbe     short loc_180008FC3
0x180008f7f  mov     rcx, [rbp+4Fh+Src]; Block
0x180008f83  mov     rdx, rcx
0x180008f86  lea     rax, ds:2[rax*2]
0x180008f8e  cmp     rax, 1000h
0x180008f94  jb      short loc_180008FBD
0x180008f96  mov     rcx, [rcx-8]
0x180008f9a  sub     rdx, rcx
0x180008f9d  lea     rax, [rdx-8]
0x180008fa1  cmp     rax, 1Fh
0x180008fa5  jbe     short loc_180008FBD
0x180008fa7  mov     [rsp+0E0h+Reserved], r13; Reserved
0x180008fac  xor     r9d, r9d; LineNo
0x180008faf  xor     r8d, r8d; FileName
0x180008fb2  xor     edx, edx; FunctionName
0x180008fb4  xor     ecx, ecx; Expression
0x180008fb6  call    cs:__imp__invoke_watson
0x180008fbd  call    cs:__imp_free
0x180008fc3  mov     rax, rdi
0x180008fc6  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x180008fca  xor     rcx, rsp; StackCookie
0x180008fcd  call    __security_check_cookie
0x180008fd2  movaps  xmm6, [rsp+0E0h+var_58+8]
0x180008fda  add     rsp, 0A8h
0x180008fe1  pop     r15
0x180008fe3  pop     r14
0x180008fe5  pop     r13
0x180008fe7  pop     r12
0x180008fe9  pop     rdi
0x180008fea  pop     rsi
0x180008feb  pop     rbx
0x180008fec  pop     rbp
0x180008fed  retn
0x180008fee  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```

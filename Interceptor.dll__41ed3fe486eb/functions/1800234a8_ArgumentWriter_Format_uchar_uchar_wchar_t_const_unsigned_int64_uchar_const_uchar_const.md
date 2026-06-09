# ArgumentWriter::Format<uchar,uchar>(wchar_t const *,unsigned __int64,uchar const &,uchar const &)

- ea: `0x1800234a8`
- end: `0x180023774`
- name: `??$Format@EE@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_KAEBE2@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180022a70`

## callees

- `0x180001bac`
- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x1800041d4`
- `0x1800045ec`
- `0x1800046d8`
- `0x1800234a8`
- `0x180024300`
- `0x1800266e0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023694`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023732`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023694`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180023732`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002369b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023739`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002369b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180023739`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 __fastcall ArgumentWriter::Format<unsigned char,unsigned char>(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v6; // rbx
  __int64 v7; // r14
  const wchar_t *v8; // rsi
  unsigned __int16 *v9; // r14
  __m128i si128; // xmm6
  wchar_t v11; // r8
  unsigned __int16 *v12; // rbx
  void **v13; // rsi
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rax
  void *v17; // rcx
  unsigned __int64 v19[3]; // [rsp+30h] [rbp-51h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-39h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-29h]
  unsigned __int64 v22; // [rsp+60h] [rbp-21h]
  void *Block[2]; // [rsp+68h] [rbp-19h] BYREF
  __m128i v24; // [rsp+78h] [rbp-9h]

  v19[2] = a1;
  *(_OWORD *)Src = 0;
  v6 = 0;
  v21 = 0;
  v22 = 7;
  LOWORD(Src[0]) = 0;
  v7 = a3;
  if ( (unsigned __int64)(2 * a3) > 7 )
  {
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
    v21 = 0;
  }
  v8 = L"Log level changed from: %u to: %u";
  v9 = &aLogLevelChange[v7];
  if ( L"Log level changed from: %u to: %u" >= v9 )
  {
LABEL_14:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v13 = Src;
    if ( v22 > 7 )
      v13 = (void **)Src[0];
    v14 = 0x7FFFFFFFFFFFFFFELL;
    if ( v6 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v6 > 7 )
    {
      if ( (v6 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v14 = v6 | 7;
        if ( (v6 | 7) < 0xA )
          v14 = 10;
      }
      v19[0] = v14;
      v16 = (void *)std::wstring::_Allocate_for_capacity<0>(a1, v19);
      *(_QWORD *)a1 = v16;
      *(_QWORD *)(a1 + 16) = v6;
      *(_QWORD *)(a1 + 24) = v19[0];
      memmove(v16, v13, 2 * v6 + 2);
    }
    else
    {
      *(_QWORD *)(a1 + 16) = v6;
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
    v11 = *v8;
    v12 = (unsigned __int16 *)(v8 + 1);
    v8 = v12;
    v19[0] = (unsigned __int64)v12;
    if ( v11 == 37 )
      break;
    std::wstring::append(Src);
LABEL_12:
    std::wstring::_Tidy_deallocate(Block);
    if ( v8 >= v9 )
    {
      v6 = v21;
      goto LABEL_14;
    }
  }
  if ( v12 != v9 && *v12 == 37 )
  {
    std::wstring::append(Src);
    v8 = v12 + 1;
    goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField(v19, v9, Src, (__int64)Block) )
  {
    v8 = (const wchar_t *)v19[0];
    goto LABEL_12;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(Src, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned char,>(a1, v19[0], v9, Src, a5);
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
0x1800234a8  mov     rax, rsp
0x1800234ab  mov     [rax+10h], rbx
0x1800234af  push    rbp
0x1800234b0  push    rsi
0x1800234b1  push    rdi
0x1800234b2  push    r12
0x1800234b4  push    r13
0x1800234b6  push    r14
0x1800234b8  push    r15
0x1800234ba  lea     rbp, [rax-57h]
0x1800234be  sub     rsp, 0A0h
0x1800234c5  movaps  xmmword ptr [rax-48h], xmm6
0x1800234c9  mov     rax, cs:__security_cookie
0x1800234d0  xor     rax, rsp
0x1800234d3  mov     [rbp+4Fh+var_48], rax
0x1800234d7  mov     r15, r9
0x1800234da  mov     rdi, rcx
0x1800234dd  mov     [rbp+4Fh+var_90], rcx
0x1800234e1  mov     r12, [rbp+4Fh+arg_20]
0x1800234e5  xor     r13d, r13d
0x1800234e8  xorps   xmm0, xmm0
0x1800234eb  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x1800234ef  mov     ebx, r13d
0x1800234f2  mov     [rbp+4Fh+var_78], rbx
0x1800234f6  mov     [rbp+4Fh+var_70], 7
0x1800234fe  mov     word ptr [rbp+4Fh+Src], r13w
0x180023503  lea     r14, [r8+r8]
0x180023507  cmp     r14, 7
0x18002350b  jbe     short loc_180023520
0x18002350d  lfence
0x180023510  mov     rdx, r14
0x180023513  lea     rcx, [rbp+4Fh+Src]; Src
0x180023517  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18002351c  mov     [rbp+4Fh+var_78], rbx
0x180023520  lea     rsi, aLogLevelChange; "Log level changed from: %u to: %u"
0x180023527  add     r14, rsi
0x18002352a  cmp     rsi, r14
0x18002352d  jnb     loc_1800235D1
0x180023533  lfence
0x180023536  mov     eax, 25h ; '%'
0x18002353b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180023543  xorps   xmm0, xmm0
0x180023546  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x18002354a  movdqu  [rbp+4Fh+var_58], xmm6
0x18002354f  mov     word ptr [rbp+4Fh+Block], r13w
0x180023554  movzx   r8d, word ptr [rsi]
0x180023558  lea     rbx, [rsi+2]
0x18002355c  mov     rsi, rbx
0x18002355f  mov     [rbp+4Fh+var_A0], rbx
0x180023563  cmp     r8w, ax
0x180023567  jz      short loc_180023579
0x180023569  mov     edx, 1
0x18002356e  lea     rcx, [rbp+4Fh+Src]; Src
0x180023572  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023577  jmp     short loc_1800235B6
0x180023579  cmp     rbx, r14
0x18002357c  jz      short loc_18002359A
0x18002357e  cmp     [rbx], ax
0x180023581  jnz     short loc_18002359A
0x180023583  mov     r8d, eax
0x180023586  mov     edx, 1
0x18002358b  lea     rcx, [rbp+4Fh+Src]; Src
0x18002358f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180023594  lea     rsi, [rbx+2]
0x180023598  jmp     short loc_1800235B6
0x18002359a  lea     r9, [rbp+4Fh+Block]
0x18002359e  lea     r8, [rbp+4Fh+Src]
0x1800235a2  mov     rdx, r14
0x1800235a5  lea     rcx, [rbp+4Fh+var_A0]
0x1800235a9  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x1800235ae  test    al, al
0x1800235b0  jnz     short loc_180023622
0x1800235b2  mov     rsi, [rbp+4Fh+var_A0]
0x1800235b6  lea     rcx, [rbp+4Fh+Block]
0x1800235ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800235bf  cmp     rsi, r14
0x1800235c2  mov     eax, 25h ; '%'
0x1800235c7  jb      loc_180023543
0x1800235cd  mov     rbx, [rbp+4Fh+var_78]
0x1800235d1  xorps   xmm0, xmm0
0x1800235d4  movups  xmmword ptr [rdi], xmm0
0x1800235d7  mov     [rdi+10h], r13
0x1800235db  mov     [rdi+18h], r13
0x1800235df  lea     rsi, [rbp+4Fh+Src]
0x1800235e3  cmp     [rbp+4Fh+var_70], 7
0x1800235e8  cmova   rsi, [rbp+4Fh+Src]
0x1800235ed  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800235f7  cmp     rbx, rcx
0x1800235fa  ja      loc_18002376E
0x180023600  cmp     rbx, 7
0x180023604  ja      loc_1800236A3
0x18002360a  mov     [rdi+10h], rbx
0x18002360e  mov     qword ptr [rdi+18h], 7
0x180023616  movups  xmm0, xmmword ptr [rsi]
0x180023619  movdqu  xmmword ptr [rdi], xmm0
0x18002361d  jmp     loc_1800236F1
0x180023622  lfence
0x180023625  movzx   r8d, byte ptr [r15]
0x180023629  lea     rdx, [rbp+4Fh+Block]; Format
0x18002362d  lea     rcx, [rbp+4Fh+Src]; Src
0x180023631  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180023636  mov     [rsp+0D0h+Reserved], r12
0x18002363b  lea     r9, [rbp+4Fh+Src]
0x18002363f  mov     r8, r14
0x180023642  mov     rdx, [rbp+4Fh+var_A0]
0x180023646  mov     rcx, rdi
0x180023649  call    ??$FormatArguments@E$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBE@Z; ArgumentWriter::FormatArguments<uchar,>(wchar_t const *,wchar_t const *,std::wstring &,uchar const &)
0x18002364e  nop
0x18002364f  mov     rax, qword ptr [rbp+4Fh+var_58+8]
0x180023653  cmp     rax, 7
0x180023657  jbe     loc_1800236F1
0x18002365d  mov     rcx, [rbp+4Fh+Block]; Block
0x180023661  mov     rdx, rcx
0x180023664  lea     rax, ds:2[rax*2]
0x18002366c  cmp     rax, 1000h
0x180023672  jb      short loc_18002369B
0x180023674  mov     rcx, [rcx-8]
0x180023678  sub     rdx, rcx
0x18002367b  lea     rax, [rdx-8]
0x18002367f  cmp     rax, 1Fh
0x180023683  jbe     short loc_18002369B
0x180023685  mov     [rsp+0D0h+Reserved], r13; Reserved
0x18002368a  xor     r9d, r9d; LineNo
0x18002368d  xor     r8d, r8d; FileName
0x180023690  xor     edx, edx; FunctionName
0x180023692  xor     ecx, ecx; Expression
0x180023694  call    cs:__imp__invoke_watson
0x18002369b  call    cs:__imp_free
0x1800236a1  jmp     short loc_1800236F1
0x1800236a3  mov     rax, rbx
0x1800236a6  or      rax, 7
0x1800236aa  cmp     rax, rcx
0x1800236ad  ja      short loc_1800236BE
0x1800236af  mov     rcx, rax
0x1800236b2  mov     edx, 0Ah
0x1800236b7  cmp     rax, rdx
0x1800236ba  cmovb   rcx, rdx
0x1800236be  mov     [rbp+4Fh+var_A0], rcx
0x1800236c2  lea     rdx, [rbp+4Fh+var_A0]
0x1800236c6  mov     rcx, rdi
0x1800236c9  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x1800236ce  mov     [rdi], rax
0x1800236d1  mov     [rdi+10h], rbx
0x1800236d5  mov     rcx, [rbp+4Fh+var_A0]
0x1800236d9  mov     [rdi+18h], rcx
0x1800236dd  lea     r8, ds:2[rbx*2]; Size
0x1800236e5  mov     rdx, rsi; Src
0x1800236e8  mov     rcx, rax; void *
0x1800236eb  call    memmove
0x1800236f0  nop
0x1800236f1  mov     rax, [rbp+4Fh+var_70]
0x1800236f5  cmp     rax, 7
0x1800236f9  jbe     short loc_18002373F
0x1800236fb  mov     rcx, [rbp+4Fh+Src]; Block
0x1800236ff  mov     rdx, rcx
0x180023702  lea     rax, ds:2[rax*2]
0x18002370a  cmp     rax, 1000h
0x180023710  jb      short loc_180023739
0x180023712  mov     rcx, [rcx-8]
0x180023716  sub     rdx, rcx
0x180023719  lea     rax, [rdx-8]
0x18002371d  cmp     rax, 1Fh
0x180023721  jbe     short loc_180023739
0x180023723  mov     [rsp+0D0h+Reserved], r13; Reserved
0x180023728  xor     r9d, r9d; LineNo
0x18002372b  xor     r8d, r8d; FileName
0x18002372e  xor     edx, edx; FunctionName
0x180023730  xor     ecx, ecx; Expression
0x180023732  call    cs:__imp__invoke_watson
0x180023739  call    cs:__imp_free
0x18002373f  mov     rax, rdi
0x180023742  mov     rcx, [rbp+4Fh+var_48]
0x180023746  xor     rcx, rsp; StackCookie
0x180023749  call    __security_check_cookie
0x18002374e  lea     r11, [rsp+0D0h+var_30]
0x180023756  mov     rbx, [r11+48h]
0x18002375a  movaps  xmm6, xmmword ptr [r11-10h]
0x18002375f  mov     rsp, r11
0x180023762  pop     r15
0x180023764  pop     r14
0x180023766  pop     r13
0x180023768  pop     r12
0x18002376a  pop     rdi
0x18002376b  pop     rsi
0x18002376c  pop     rbp
0x18002376d  retn
0x18002376e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```

# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)

- ea: `0x180067b60`
- end: `0x180067e4c`
- name: `?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(__int64, std::filesystem *)`
- caller_count: `9`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009cd0`
- `0x180027080`
- `0x180027580`
- `0x18003c3f0`
- `0x180050d20`
- `0x1800510f0`
- `0x1800567e0`
- `0x180230600`
- `0x18023a270`

## callees

- `0x180007830`
- `0x180007de0`
- `0x1800449a0`
- `0x1800476d0`
- `0x180067b60`
- `0x180068310`
- `0x1801d39e0`
- `0x1801f7110`
- `0x1801f7160`
- `0x180206ec0`
- `0x1802421a0`

## string_xrefs

- `0x180067bac`: `.sidb`
- `0x180067d8d`: `.sidb`
- `0x180067dac`: `.sidb`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(
        __int64 a1,
        std::filesystem *a2)
{
  const wchar_t *v4; // r8
  std::filesystem *v5; // rcx
  const wchar_t *v6; // rsi
  const wchar_t *v7; // rbx
  const wchar_t *root_name_end; // rax
  const wchar_t *v9; // rdx
  __int16 v10; // cx
  __int64 trivial_2; // rax
  const wchar_t *i; // rdx
  int v13; // ebx
  void *v14; // r8
  void *v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  __int64 v18; // rsi
  std::filesystem *v19; // rbx
  __int128 v21; // [rsp+60h] [rbp-19h] BYREF
  __int64 v22; // [rsp+70h] [rbp-9h]
  unsigned __int64 v23; // [rsp+78h] [rbp-1h]
  void *Block[2]; // [rsp+80h] [rbp+7h] BYREF
  __m128i si128; // [rsp+90h] [rbp+17h]

  v21 = 0;
  v22 = 0;
  v23 = 0;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(&v21);
  v5 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v5 = *(std::filesystem **)a2;
  v6 = (const wchar_t *)((char *)v5 + 2 * *((_QWORD *)a2 + 2));
  v7 = v6;
  root_name_end = std::filesystem::_Find_root_name_end(v5, v6, v4);
  if ( root_name_end != v6 )
  {
    do
    {
      if ( *root_name_end != 92 && *root_name_end != 47 )
        break;
      ++root_name_end;
    }
    while ( root_name_end != v6 );
    if ( root_name_end != v6 )
    {
      do
      {
        v9 = v7 - 1;
        v10 = *(v7 - 1);
        if ( v10 == 92 )
          break;
        if ( v10 == 47 )
          break;
        --v7;
      }
      while ( root_name_end != v9 );
    }
  }
  trivial_2 = _std_find_trivial_2(v7, v6, 58);
  if ( v7 != (const wchar_t *)trivial_2 && v7 != (const wchar_t *)(trivial_2 - 2) && *(_WORD *)(trivial_2 - 2) != 46 )
  {
    for ( i = (const wchar_t *)(trivial_2 - 4); v7 != i; --i )
    {
      if ( *i == 46 )
        break;
    }
  }
  *(_OWORD *)Block = 0;
  si128 = 0u;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(Block);
  v13 = std::filesystem::path::compare((std::filesystem *)Block);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v14 = Block[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v14 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v14);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  if ( v23 > 7 )
  {
    v15 = (void *)v21;
    if ( 2 * v23 + 2 >= 0x1000 )
    {
      v15 = *(void **)(v21 - 8);
      if ( (unsigned __int64)(v21 - (_QWORD)v15 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v15);
  }
  if ( v13 )
  {
    v16 = *((_QWORD *)a2 + 2);
    v17 = *((_QWORD *)a2 + 3);
    if ( v17 - v16 < 5 )
    {
      _mm_lfence();
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
        a2,
        5);
    }
    else
    {
      v18 = v16 + 5;
      *((_QWORD *)a2 + 2) = v16 + 5;
      v19 = a2;
      if ( v17 > 7 )
        v19 = *(std::filesystem **)a2;
      memmove((char *)v19 + 2 * v16, L".sidb", 0xAu);
      *((_WORD *)v19 + v18) = 0;
    }
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *((_OWORD *)a2 + 1);
  *(_WORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  *((_QWORD *)a2 + 3) = 7;
  std::basic_string<char16_t>::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x180067b60  mov     [rsp-8+arg_10], rbx
0x180067b65  push    rbp
0x180067b66  push    rsi
0x180067b67  push    rdi
0x180067b68  push    r14
0x180067b6a  push    r15
0x180067b6c  lea     rbp, [rsp-37h]
0x180067b71  sub     rsp, 0B0h
0x180067b78  mov     rax, cs:__security_cookie
0x180067b7f  xor     rax, rsp
0x180067b82  mov     [rbp+57h+var_30], rax
0x180067b86  mov     rdi, rdx
0x180067b89  mov     r14, rcx
0x180067b8c  mov     [rbp+57h+var_78], rcx
0x180067b90  mov     [rbp+57h+var_78], rdx
0x180067b94  xor     r15d, r15d
0x180067b97  xorps   xmm0, xmm0
0x180067b9a  movups  [rbp+57h+var_70], xmm0
0x180067b9e  mov     [rbp+57h+var_60], r15
0x180067ba2  mov     [rbp+57h+var_58], r15
0x180067ba6  mov     r8d, 5
0x180067bac  lea     rdx, aSidb; ".sidb"
0x180067bb3  lea     rcx, [rbp+57h+var_70]
0x180067bb7  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x180067bbc  nop
0x180067bbd  mov     rcx, rdi
0x180067bc0  cmp     qword ptr [rdi+18h], 7
0x180067bc5  jbe     short loc_180067BCA
0x180067bc7  mov     rcx, [rdi]; this
0x180067bca  mov     rax, [rdi+10h]
0x180067bce  lea     rsi, [rcx+rax*2]
0x180067bd2  mov     rbx, rsi
0x180067bd5  mov     rdx, rsi; wchar_t *
0x180067bd8  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180067bdd  cmp     rax, rsi
0x180067be0  jz      short loc_180067C1B
0x180067be2  movzx   ecx, word ptr [rax]
0x180067be5  cmp     cx, 5Ch ; '\'
0x180067be9  jz      short loc_180067BF1
0x180067beb  cmp     cx, 2Fh ; '/'
0x180067bef  jnz     short loc_180067BFA
0x180067bf1  add     rax, 2
0x180067bf5  cmp     rax, rsi
0x180067bf8  jnz     short loc_180067BE2
0x180067bfa  cmp     rax, rsi
0x180067bfd  jz      short loc_180067C1B
0x180067bff  nop
0x180067c00  lea     rdx, [rbx-2]
0x180067c04  movzx   ecx, word ptr [rdx]
0x180067c07  cmp     cx, 5Ch ; '\'
0x180067c0b  jz      short loc_180067C1B
0x180067c0d  cmp     cx, 2Fh ; '/'
0x180067c11  jz      short loc_180067C1B
0x180067c13  mov     rbx, rdx
0x180067c16  cmp     rax, rdx
0x180067c19  jnz     short loc_180067C00
0x180067c1b  mov     r8d, 3Ah ; ':'
0x180067c21  mov     rdx, rsi
0x180067c24  mov     rcx, rbx
0x180067c27  call    __std_find_trivial_2
0x180067c2c  cmp     rbx, rax
0x180067c2f  jz      short loc_180067C6F
0x180067c31  lea     rdx, [rax-2]
0x180067c35  cmp     rbx, rdx
0x180067c38  jz      short loc_180067C6F
0x180067c3a  cmp     word ptr [rdx], 2Eh ; '.'
0x180067c3e  jnz     short loc_180067C51
0x180067c40  lea     rcx, [rdx-2]
0x180067c44  cmp     rbx, rcx
0x180067c47  jnz     short loc_180067C72
0x180067c49  cmp     word ptr [rcx], 2Eh ; '.'
0x180067c4d  jnz     short loc_180067C72
0x180067c4f  jmp     short loc_180067C6F
0x180067c51  sub     rdx, 2
0x180067c55  cmp     rbx, rdx
0x180067c58  jz      short loc_180067C6F
0x180067c5a  nop     word ptr [rax+rax+00h]
0x180067c60  cmp     word ptr [rdx], 2Eh ; '.'
0x180067c64  jz      short loc_180067C72
0x180067c66  sub     rdx, 2
0x180067c6a  cmp     rbx, rdx
0x180067c6d  jnz     short loc_180067C60
0x180067c6f  mov     rdx, rax
0x180067c72  sub     rax, rdx
0x180067c75  sar     rax, 1
0x180067c78  xorps   xmm0, xmm0
0x180067c7b  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180067c7f  mov     qword ptr [rbp+57h+var_40], r15
0x180067c83  mov     qword ptr [rbp+57h+var_40+8], r15
0x180067c87  mov     r8, rax
0x180067c8a  lea     rcx, [rbp+57h+Block]
0x180067c8e  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x180067c93  lea     rax, [rbp+57h+var_70]
0x180067c97  cmp     [rbp+57h+var_58], 7
0x180067c9c  cmova   rax, qword ptr [rbp+57h+var_70]
0x180067ca1  mov     [rbp+57h+var_90], rax
0x180067ca5  mov     rax, [rbp+57h+var_60]
0x180067ca9  mov     [rbp+57h+var_88], rax
0x180067cad  lea     rdx, [rbp+57h+var_90]
0x180067cb1  lea     rcx, [rbp+57h+Block]; this
0x180067cb5  call    ?compare@path@filesystem@std@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; std::filesystem::path::compare(std::wstring_view)
0x180067cba  mov     ebx, eax
0x180067cbc  mov     rdx, qword ptr [rbp+57h+var_40+8]
0x180067cc0  cmp     rdx, 7
0x180067cc4  jbe     short loc_180067D02
0x180067cc6  lea     rdx, ds:2[rdx*2]
0x180067cce  mov     r8, [rbp+57h+Block]
0x180067cd2  mov     rcx, r8
0x180067cd5  cmp     rdx, 1000h
0x180067cdc  jb      short loc_180067CF7
0x180067cde  add     rdx, 27h ; '''
0x180067ce2  mov     r8, [r8-8]
0x180067ce6  sub     rcx, r8
0x180067ce9  sub     rcx, 8
0x180067ced  cmp     rcx, 1Fh
0x180067cf1  ja      loc_180067E37
0x180067cf7  lfence
0x180067cfa  mov     rcx, r8; Block
0x180067cfd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180067d02  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180067d0a  movdqu  [rbp+57h+var_40], xmm0
0x180067d0f  mov     word ptr [rbp+57h+Block], r15w
0x180067d14  mov     rdx, [rbp+57h+var_58]
0x180067d18  cmp     rdx, 7
0x180067d1c  jbe     short loc_180067D57
0x180067d1e  lea     rdx, ds:2[rdx*2]
0x180067d26  mov     rcx, qword ptr [rbp+57h+var_70]
0x180067d2a  mov     rax, rcx
0x180067d2d  cmp     rdx, 1000h
0x180067d34  jb      short loc_180067D4F
0x180067d36  add     rdx, 27h ; '''
0x180067d3a  mov     rcx, [rcx-8]; Block
0x180067d3e  sub     rax, rcx
0x180067d41  sub     rax, 8
0x180067d45  cmp     rax, 1Fh
0x180067d49  ja      loc_180067E22
0x180067d4f  lfence
0x180067d52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180067d57  test    ebx, ebx
0x180067d59  jz      short loc_180067DC5
0x180067d5b  mov     rcx, [rdi+10h]
0x180067d5f  mov     r8, [rdi+18h]
0x180067d63  mov     rax, r8
0x180067d66  sub     rax, rcx
0x180067d69  cmp     rax, 5
0x180067d6d  jb      short loc_180067DA0
0x180067d6f  lea     rsi, [rcx+5]
0x180067d73  mov     [rdi+10h], rsi
0x180067d77  mov     rbx, rdi
0x180067d7a  cmp     r8, 7
0x180067d7e  jbe     short loc_180067D83
0x180067d80  mov     rbx, [rdi]
0x180067d83  lea     rcx, [rbx+rcx*2]; void *
0x180067d87  mov     r8d, 0Ah; Size
0x180067d8d  lea     rdx, aSidb; ".sidb"
0x180067d94  call    memmove
0x180067d99  mov     [rbx+rsi*2], r15w
0x180067d9e  jmp     short loc_180067DC5
0x180067da0  lfence
0x180067da3  mov     [rsp+0D0h+Reserved], 5; __int64
0x180067dac  lea     r9, aSidb; ".sidb"
0x180067db3  movzx   r8d, [rbp+57h+var_A0]
0x180067db8  mov     edx, 5
0x180067dbd  mov     rcx, rdi; Src
0x180067dc0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x180067dc5  xorps   xmm0, xmm0
0x180067dc8  movups  xmmword ptr [r14], xmm0
0x180067dcc  mov     [r14+10h], r15
0x180067dd0  mov     [r14+18h], r15
0x180067dd4  movups  xmm0, xmmword ptr [rdi]
0x180067dd7  movups  xmmword ptr [r14], xmm0
0x180067ddb  movups  xmm1, xmmword ptr [rdi+10h]
0x180067ddf  movups  xmmword ptr [r14+10h], xmm1
0x180067de4  mov     [rdi], r15w
0x180067de8  mov     [rdi+10h], r15
0x180067dec  mov     qword ptr [rdi+18h], 7
0x180067df4  mov     rcx, rdi
0x180067df7  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180067dfc  mov     rax, r14
0x180067dff  mov     rcx, [rbp+57h+var_30]
0x180067e03  xor     rcx, rsp; StackCookie
0x180067e06  call    __security_check_cookie
0x180067e0b  mov     rbx, [rsp+0D0h+arg_10]
0x180067e13  add     rsp, 0B0h
0x180067e1a  pop     r15
0x180067e1c  pop     r14
0x180067e1e  pop     rdi
0x180067e1f  pop     rsi
0x180067e20  pop     rbp
0x180067e21  retn
0x180067e22  mov     [rsp+0D0h+Reserved], r15; Reserved
0x180067e27  xor     r9d, r9d; LineNo
0x180067e2a  xor     r8d, r8d; FileName
0x180067e2d  xor     edx, edx; FunctionName
0x180067e2f  xor     ecx, ecx; Expression
0x180067e31  call    _invoke_watson
0x180067e37  mov     [rsp+0D0h+Reserved], r15; Reserved
0x180067e3c  xor     r9d, r9d; LineNo
0x180067e3f  xor     r8d, r8d; FileName
0x180067e42  xor     edx, edx; FunctionName
0x180067e44  xor     ecx, ecx; Expression
0x180067e46  call    _invoke_watson
```

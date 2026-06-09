# wil::AdaptFixedSizeToAllocatedResult<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,128>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180006aec`
- end: `0x180006cf5`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000aa84`

## callees

- `0x180002200`
- `0x180002f7c`
- `0x180005984`
- `0x180006aec`
- `0x180008f20`
- `0x180009168`
- `0x1800094c0`
- `0x18000b394`
- `0x18000b4e8`

## string_xrefs

- `0x180006ba7`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x180006cae`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(__int64 a1, __int64 a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  int v6; // eax
  unsigned __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  __int128 *v10; // rdx
  int v11; // eax
  bool v12; // cc
  __int128 *v13; // rcx
  int v15[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v16; // [rsp+28h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+38h] [rbp-C8h]
  _OWORD v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v16 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16) = 0;
  memset_0(v19, 0, sizeof(v19));
  *(_QWORD *)v15 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v19, 128, v15);
  if ( v4 < 0 )
  {
LABEL_17:
    std::wstring::~wstring(&v16);
    return (unsigned int)v4;
  }
  v5 = *(_QWORD *)v15;
  if ( *(_QWORD *)v15 <= 0x80u )
  {
    v6 = wil::details::string_maker<std::wstring>::make(&v16, v19, *(_QWORD *)v15 - 1LL);
    v4 = v6;
    if ( v6 >= 0 )
    {
LABEL_15:
      v18[0] = v16;
      v18[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v16) = 0;
      std::wstring::operator=(a1, v18);
      std::wstring::~wstring(v18);
      std::wstring::~wstring(&v16);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)(unsigned int)v6,
      v15[0]);
    goto LABEL_17;
  }
  while ( 1 )
  {
    v7 = v5;
    v8 = wil::details::string_maker<std::wstring>::make(&v16, 0, v5 - 1);
    v9 = v8;
    if ( v8 < 0 )
      break;
    v10 = &v16;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = (__int128 *)v16;
    v11 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v10, v7, v15);
    if ( v11 < 0 )
    {
      v4 = v11;
      goto LABEL_17;
    }
    v5 = *(_QWORD *)v15;
    v12 = *(_QWORD *)v15 <= v7;
    if ( *(_QWORD *)v15 < v7 )
    {
      if ( si128.m128i_i64[0] < (unsigned __int64)(*(_QWORD *)v15 - 1LL) )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      si128.m128i_i64[0] = *(_QWORD *)v15 - 1LL;
      v13 = &v16;
      if ( si128.m128i_i64[1] > 7uLL )
        v13 = (__int128 *)v16;
      *((_WORD *)v13 + *(_QWORD *)v15 - 1) = 0;
      v5 = *(_QWORD *)v15;
      v12 = *(_QWORD *)v15 <= v7;
    }
    if ( v12 )
      goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17A,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
    (const char *)(unsigned int)v8,
    v15[0]);
  std::wstring::~wstring(&v16);
  return v9;
}

```

## disassembly

```asm
0x180006aec  mov     [rsp-8+arg_10], rbx
0x180006af1  mov     [rsp-8+arg_18], rsi
0x180006af6  push    rbp
0x180006af7  push    rdi
0x180006af8  push    r14
0x180006afa  lea     rbp, [rsp-80h]
0x180006aff  sub     rsp, 180h
0x180006b06  mov     rax, cs:__security_cookie
0x180006b0d  xor     rax, rsp
0x180006b10  mov     [rbp+90h+var_20], rax
0x180006b14  mov     rsi, rdx
0x180006b17  mov     r14, rcx
0x180006b1a  xorps   xmm0, xmm0
0x180006b1d  movups  [rsp+190h+var_168], xmm0
0x180006b22  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180006b2a  movdqu  [rsp+190h+var_158], xmm1
0x180006b30  xor     eax, eax
0x180006b32  mov     word ptr [rsp+190h+var_168], ax
0x180006b37  xor     edx, edx; Val
0x180006b39  mov     r8d, 100h; Size
0x180006b3f  lea     rcx, [rsp+190h+var_120]; void *
0x180006b44  call    memset_0
0x180006b49  mov     qword ptr [rsp+190h+var_170], 0; int
0x180006b52  lea     r9, [rsp+190h+var_170]
0x180006b57  mov     edi, 80h
0x180006b5c  mov     r8d, edi
0x180006b5f  lea     rdx, [rsp+190h+var_120]
0x180006b64  mov     rcx, rsi
0x180006b67  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006b6c  mov     ebx, eax
0x180006b6e  test    eax, eax
0x180006b70  js      loc_180006C96
0x180006b76  mov     rax, qword ptr [rsp+190h+var_170]
0x180006b7b  cmp     rax, rdi
0x180006b7e  ja      short loc_180006BBD
0x180006b80  lea     r8, [rax-1]
0x180006b84  lea     rdx, [rsp+190h+var_120]
0x180006b89  lea     rcx, [rsp+190h+var_168]
0x180006b8e  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x180006b93  mov     ebx, eax
0x180006b95  test    eax, eax
0x180006b97  jns     loc_180006C46
0x180006b9d  mov     rcx, [rbp+98h]; this
0x180006ba4  mov     r9d, eax; char *
0x180006ba7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006bae  mov     edx, 16Fh; void *
0x180006bb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bb8  jmp     loc_180006C96
0x180006bbd  mov     rbx, rax
0x180006bc0  lea     r8, [rax-1]
0x180006bc4  xor     edx, edx
0x180006bc6  lea     rcx, [rsp+190h+var_168]
0x180006bcb  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x180006bd0  mov     edi, eax
0x180006bd2  test    eax, eax
0x180006bd4  js      loc_180006CA4
0x180006bda  lea     rdx, [rsp+190h+var_168]
0x180006bdf  cmp     qword ptr [rsp+190h+var_158+8], 7
0x180006be5  cmova   rdx, qword ptr [rsp+190h+var_168]
0x180006beb  lea     r9, [rsp+190h+var_170]
0x180006bf0  mov     r8, rbx
0x180006bf3  mov     rcx, rsi
0x180006bf6  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006bfb  test    eax, eax
0x180006bfd  js      loc_180006C94
0x180006c03  mov     rax, qword ptr [rsp+190h+var_170]
0x180006c08  cmp     rax, rbx
0x180006c0b  jnb     short loc_180006C40
0x180006c0d  lea     rdx, [rax-1]
0x180006c11  cmp     qword ptr [rsp+190h+var_158], rdx
0x180006c16  jb      loc_180006CEF
0x180006c1c  mov     qword ptr [rsp+190h+var_158], rdx
0x180006c21  lea     rcx, [rsp+190h+var_168]
0x180006c26  cmp     qword ptr [rsp+190h+var_158+8], 7
0x180006c2c  cmova   rcx, qword ptr [rsp+190h+var_168]
0x180006c32  xor     eax, eax
0x180006c34  mov     [rcx+rdx*2], ax
0x180006c38  mov     rax, qword ptr [rsp+190h+var_170]
0x180006c3d  cmp     rax, rbx
0x180006c40  ja      loc_180006BBD
0x180006c46  movups  xmm0, [rsp+190h+var_168]
0x180006c4b  movups  [rsp+190h+var_148], xmm0
0x180006c50  movups  xmm1, [rsp+190h+var_158]
0x180006c55  movups  [rsp+190h+var_138], xmm1
0x180006c5a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180006c62  movdqu  [rsp+190h+var_158], xmm0
0x180006c68  xor     eax, eax
0x180006c6a  mov     word ptr [rsp+190h+var_168], ax
0x180006c6f  lea     rdx, [rsp+190h+var_148]
0x180006c74  mov     rcx, r14
0x180006c77  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180006c7c  lea     rcx, [rsp+190h+var_148]
0x180006c81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006c86  lea     rcx, [rsp+190h+var_168]
0x180006c8b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006c90  xor     eax, eax
0x180006c92  jmp     short loc_180006CCB
0x180006c94  mov     ebx, eax
0x180006c96  lea     rcx, [rsp+190h+var_168]
0x180006c9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006ca0  mov     eax, ebx
0x180006ca2  jmp     short loc_180006CCB
0x180006ca4  mov     rcx, [rbp+98h]; this
0x180006cab  mov     r9d, edi; char *
0x180006cae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006cb5  mov     edx, 17Ah; void *
0x180006cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cbf  lea     rcx, [rsp+190h+var_168]
0x180006cc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006cc9  mov     eax, edi
0x180006ccb  mov     rcx, [rbp+90h+var_20]
0x180006ccf  xor     rcx, rsp; StackCookie
0x180006cd2  call    __security_check_cookie
0x180006cd7  lea     r11, [rsp+190h+var_10]
0x180006cdf  mov     rbx, [r11+30h]
0x180006ce3  mov     rsi, [r11+38h]
0x180006ce7  mov     rsp, r11
0x180006cea  pop     r14
0x180006cec  pop     rdi
0x180006ced  pop     rbp
0x180006cee  retn
0x180006cef  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```

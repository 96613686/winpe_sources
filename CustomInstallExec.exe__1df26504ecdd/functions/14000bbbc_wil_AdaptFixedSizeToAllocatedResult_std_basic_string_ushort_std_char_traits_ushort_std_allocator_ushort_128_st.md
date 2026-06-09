# wil::AdaptFixedSizeToAllocatedResult<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,128>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x14000bbbc`
- end: `0x14000bdc5`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000be3c`

## callees

- `0x1400033b0`
- `0x140003f8c`
- `0x140006c24`
- `0x14000bbbc`
- `0x14000c6f0`
- `0x14000c838`
- `0x14000d5d8`
- `0x14000d65c`
- `0x14000d75c`

## string_xrefs

- `0x14000bc77`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x14000bd7e`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

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
    std::wstring::_Tidy_deallocate(&v16);
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
      std::wstring::_Tidy_deallocate(v18);
      std::wstring::_Tidy_deallocate(&v16);
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
  std::wstring::_Tidy_deallocate(&v16);
  return v9;
}

```

## disassembly

```asm
0x14000bbbc  mov     [rsp-8+arg_10], rbx
0x14000bbc1  mov     [rsp-8+arg_18], rsi
0x14000bbc6  push    rbp
0x14000bbc7  push    rdi
0x14000bbc8  push    r14
0x14000bbca  lea     rbp, [rsp-80h]
0x14000bbcf  sub     rsp, 180h
0x14000bbd6  mov     rax, cs:__security_cookie
0x14000bbdd  xor     rax, rsp
0x14000bbe0  mov     [rbp+90h+var_20], rax
0x14000bbe4  mov     rsi, rdx
0x14000bbe7  mov     r14, rcx
0x14000bbea  xorps   xmm0, xmm0
0x14000bbed  movups  [rsp+190h+var_168], xmm0
0x14000bbf2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14000bbfa  movdqu  [rsp+190h+var_158], xmm1
0x14000bc00  xor     eax, eax
0x14000bc02  mov     word ptr [rsp+190h+var_168], ax
0x14000bc07  xor     edx, edx; Val
0x14000bc09  mov     r8d, 100h; Size
0x14000bc0f  lea     rcx, [rsp+190h+var_120]; void *
0x14000bc14  call    memset_0
0x14000bc19  mov     qword ptr [rsp+190h+var_170], 0; int
0x14000bc22  lea     r9, [rsp+190h+var_170]
0x14000bc27  mov     edi, 80h
0x14000bc2c  mov     r8d, edi
0x14000bc2f  lea     rdx, [rsp+190h+var_120]
0x14000bc34  mov     rcx, rsi
0x14000bc37  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000bc3c  mov     ebx, eax
0x14000bc3e  test    eax, eax
0x14000bc40  js      loc_14000BD66
0x14000bc46  mov     rax, qword ptr [rsp+190h+var_170]
0x14000bc4b  cmp     rax, rdi
0x14000bc4e  ja      short loc_14000BC8D
0x14000bc50  lea     r8, [rax-1]
0x14000bc54  lea     rdx, [rsp+190h+var_120]
0x14000bc59  lea     rcx, [rsp+190h+var_168]
0x14000bc5e  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x14000bc63  mov     ebx, eax
0x14000bc65  test    eax, eax
0x14000bc67  jns     loc_14000BD16
0x14000bc6d  mov     rcx, [rbp+98h]; this
0x14000bc74  mov     r9d, eax; char *
0x14000bc77  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000bc7e  mov     edx, 16Fh; void *
0x14000bc83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bc88  jmp     loc_14000BD66
0x14000bc8d  mov     rbx, rax
0x14000bc90  lea     r8, [rax-1]
0x14000bc94  xor     edx, edx
0x14000bc96  lea     rcx, [rsp+190h+var_168]
0x14000bc9b  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x14000bca0  mov     edi, eax
0x14000bca2  test    eax, eax
0x14000bca4  js      loc_14000BD74
0x14000bcaa  lea     rdx, [rsp+190h+var_168]
0x14000bcaf  cmp     qword ptr [rsp+190h+var_158+8], 7
0x14000bcb5  cmova   rdx, qword ptr [rsp+190h+var_168]
0x14000bcbb  lea     r9, [rsp+190h+var_170]
0x14000bcc0  mov     r8, rbx
0x14000bcc3  mov     rcx, rsi
0x14000bcc6  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000bccb  test    eax, eax
0x14000bccd  js      loc_14000BD64
0x14000bcd3  mov     rax, qword ptr [rsp+190h+var_170]
0x14000bcd8  cmp     rax, rbx
0x14000bcdb  jnb     short loc_14000BD10
0x14000bcdd  lea     rdx, [rax-1]
0x14000bce1  cmp     qword ptr [rsp+190h+var_158], rdx
0x14000bce6  jb      loc_14000BDBF
0x14000bcec  mov     qword ptr [rsp+190h+var_158], rdx
0x14000bcf1  lea     rcx, [rsp+190h+var_168]
0x14000bcf6  cmp     qword ptr [rsp+190h+var_158+8], 7
0x14000bcfc  cmova   rcx, qword ptr [rsp+190h+var_168]
0x14000bd02  xor     eax, eax
0x14000bd04  mov     [rcx+rdx*2], ax
0x14000bd08  mov     rax, qword ptr [rsp+190h+var_170]
0x14000bd0d  cmp     rax, rbx
0x14000bd10  ja      loc_14000BC8D
0x14000bd16  movups  xmm0, [rsp+190h+var_168]
0x14000bd1b  movups  [rsp+190h+var_148], xmm0
0x14000bd20  movups  xmm1, [rsp+190h+var_158]
0x14000bd25  movups  [rsp+190h+var_138], xmm1
0x14000bd2a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14000bd32  movdqu  [rsp+190h+var_158], xmm0
0x14000bd38  xor     eax, eax
0x14000bd3a  mov     word ptr [rsp+190h+var_168], ax
0x14000bd3f  lea     rdx, [rsp+190h+var_148]
0x14000bd44  mov     rcx, r14
0x14000bd47  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000bd4c  lea     rcx, [rsp+190h+var_148]
0x14000bd51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bd56  lea     rcx, [rsp+190h+var_168]
0x14000bd5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bd60  xor     eax, eax
0x14000bd62  jmp     short loc_14000BD9B
0x14000bd64  mov     ebx, eax
0x14000bd66  lea     rcx, [rsp+190h+var_168]
0x14000bd6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bd70  mov     eax, ebx
0x14000bd72  jmp     short loc_14000BD9B
0x14000bd74  mov     rcx, [rbp+98h]; this
0x14000bd7b  mov     r9d, edi; char *
0x14000bd7e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000bd85  mov     edx, 17Ah; void *
0x14000bd8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bd8f  lea     rcx, [rsp+190h+var_168]
0x14000bd94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bd99  mov     eax, edi
0x14000bd9b  mov     rcx, [rbp+90h+var_20]
0x14000bd9f  xor     rcx, rsp; StackCookie
0x14000bda2  call    __security_check_cookie
0x14000bda7  lea     r11, [rsp+190h+var_10]
0x14000bdaf  mov     rbx, [r11+30h]
0x14000bdb3  mov     rsi, [r11+38h]
0x14000bdb7  mov     rsp, r11
0x14000bdba  pop     r14
0x14000bdbc  pop     rdi
0x14000bdbd  pop     rbp
0x14000bdbe  retn
0x14000bdbf  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```

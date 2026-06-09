# wil::details::str_vprintf_nothrow<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ushort const *,char * &)

- ea: `0x18002eb8c`
- end: `0x18002ed05`
- name: `??$str_vprintf_nothrow@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAPEAD@Z`
- size: `377`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002eb00`

## callees

- `0x18001bbe0`
- `0x18001c69c`
- `0x18001c6f0`
- `0x180025a34`
- `0x18002eb8c`
- `0x18002ee54`
- `0x18002f0c0`
- `0x18002f12c`

## string_xrefs

- `0x18002ebf3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002ecc9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<std::wstring>(__int64 a1, const wchar_t *a2, va_list *a3)
{
  size_t v6; // rbx
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // edi
  wchar_t *v10; // rdi
  unsigned __int64 v11; // rsi
  unsigned int v12; // ebx
  int v13; // eax
  __int128 v14; // xmm0
  __m128i v15; // xmm1
  wchar_t *Buffer[2]; // [rsp+20h] [rbp-50h] BYREF
  __m128i si128; // [rsp+30h] [rbp-40h]
  _OWORD v19[2]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v6 = vscwprintf(a2, *a3);
  *(_OWORD *)Buffer = 0;
  LOWORD(Buffer[0]) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v8 = wil::details::string_maker<std::wstring>::make(Buffer, v7, v6);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      (int)Buffer[0]);
    goto LABEL_18;
  }
  v10 = (wchar_t *)Buffer;
  v11 = v6 + 1;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = Buffer[0];
  if ( v6 == -1 )
  {
    v12 = -2147024809;
    goto LABEL_17;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    v12 = -2147024809;
LABEL_16:
    *v10 = 0;
    goto LABEL_17;
  }
  v13 = vsnwprintf(v10, v6, a2, *a3);
  if ( v13 < 0 || v13 > v6 )
  {
    v10[v6] = 0;
    v12 = -2147024774;
    if ( (v11 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_16;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v12,
      (int)Buffer[0]);
    v9 = v12;
    goto LABEL_18;
  }
  if ( v13 == v6 )
    v10[v6] = 0;
  v14 = *(_OWORD *)Buffer;
  v15 = si128;
  LOWORD(Buffer[0]) = 0;
  v19[0] = v14;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v19[1] = v15;
  std::wstring::operator=(a1, v19);
  std::wstring::_Tidy_deallocate(v19);
  v9 = 0;
LABEL_18:
  std::wstring::_Tidy_deallocate(Buffer);
  return v9;
}

```

## disassembly

```asm
0x18002eb8c  push    rbp
0x18002eb8e  push    rbx
0x18002eb8f  push    rsi
0x18002eb90  push    rdi
0x18002eb91  push    r12
0x18002eb93  push    r14
0x18002eb95  push    r15
0x18002eb97  mov     rbp, rsp
0x18002eb9a  sub     rsp, 70h
0x18002eb9e  mov     rax, cs:__security_cookie
0x18002eba5  xor     rax, rsp
0x18002eba8  mov     [rbp+var_10], rax
0x18002ebac  mov     r14, rdx
0x18002ebaf  mov     r12, rcx
0x18002ebb2  mov     rdx, [r8]; ArgList
0x18002ebb5  mov     rcx, r14; Format
0x18002ebb8  mov     r15, r8
0x18002ebbb  call    _vscwprintf
0x18002ebc0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002ebc8  lea     rcx, [rbp+Buffer]
0x18002ebcc  movsxd  rbx, eax
0x18002ebcf  xorps   xmm0, xmm0
0x18002ebd2  xor     eax, eax
0x18002ebd4  mov     r8, rbx
0x18002ebd7  movups  xmmword ptr [rbp+Buffer], xmm0
0x18002ebdb  mov     word ptr [rbp+Buffer], ax
0x18002ebdf  movdqu  [rbp+var_40], xmm1
0x18002ebe4  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x18002ebe9  mov     edi, eax
0x18002ebeb  test    eax, eax
0x18002ebed  jns     short loc_18002EC0C
0x18002ebef  mov     rcx, [rbp+38h]; this
0x18002ebf3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ebfa  mov     r9d, eax; char *
0x18002ebfd  mov     edx, 7CDh; void *
0x18002ec02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec07  jmp     loc_18002ECDF
0x18002ec0c  cmp     qword ptr [rbp+var_40+8], 7
0x18002ec11  lea     rdi, [rbp+Buffer]
0x18002ec15  lea     rsi, [rbx+1]
0x18002ec19  cmova   rdi, [rbp+Buffer]
0x18002ec1e  test    rsi, rsi
0x18002ec21  jz      loc_18002ECB6
0x18002ec27  cmp     rsi, 7FFFFFFFh
0x18002ec2e  jbe     short loc_18002EC3A
0x18002ec30  mov     ebx, 80070057h
0x18002ec35  jmp     loc_18002ECC0
0x18002ec3a  mov     r9, [r15]; Args
0x18002ec3d  mov     r8, r14; Format
0x18002ec40  mov     rdx, rbx; BufferCount
0x18002ec43  mov     rcx, rdi; Buffer
0x18002ec46  call    _vsnwprintf
0x18002ec4b  test    eax, eax
0x18002ec4d  js      short loc_18002EC9A
0x18002ec4f  cdqe
0x18002ec51  cmp     rax, rbx
0x18002ec54  ja      short loc_18002EC9A
0x18002ec56  jnz     short loc_18002EC5E
0x18002ec58  xor     eax, eax
0x18002ec5a  mov     [rdi+rbx*2], ax
0x18002ec5e  movups  xmm0, xmmword ptr [rbp+Buffer]
0x18002ec62  xor     eax, eax
0x18002ec64  lea     rdx, [rbp+var_30]
0x18002ec68  movups  xmm1, [rbp+var_40]
0x18002ec6c  mov     rcx, r12
0x18002ec6f  mov     word ptr [rbp+Buffer], ax
0x18002ec73  movups  [rbp+var_30], xmm0
0x18002ec77  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002ec7f  movdqu  [rbp+var_40], xmm0
0x18002ec84  movups  [rbp+var_20], xmm1
0x18002ec88  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002ec8d  lea     rcx, [rbp+var_30]
0x18002ec91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ec96  xor     edi, edi
0x18002ec98  jmp     short loc_18002ECDF
0x18002ec9a  xor     eax, eax
0x18002ec9c  mov     [rdi+rbx*2], ax
0x18002eca0  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002ecaa  mov     ebx, 8007007Ah
0x18002ecaf  test    rax, rsi
0x18002ecb2  jbe     short loc_18002ECC5
0x18002ecb4  jmp     short loc_18002ECC0
0x18002ecb6  mov     ebx, 80070057h
0x18002ecbb  test    rsi, rsi
0x18002ecbe  jz      short loc_18002ECC5
0x18002ecc0  xor     eax, eax
0x18002ecc2  mov     [rdi], ax
0x18002ecc5  mov     rcx, [rbp+38h]; this
0x18002ecc9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ecd0  mov     r9d, ebx; char *
0x18002ecd3  mov     edx, 7D1h; void *
0x18002ecd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ecdd  mov     edi, ebx
0x18002ecdf  lea     rcx, [rbp+Buffer]
0x18002ece3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ece8  mov     eax, edi
0x18002ecea  mov     rcx, [rbp+var_10]
0x18002ecee  xor     rcx, rsp; StackCookie
0x18002ecf1  call    __security_check_cookie
0x18002ecf6  add     rsp, 70h
0x18002ecfa  pop     r15
0x18002ecfc  pop     r14
0x18002ecfe  pop     r12
0x18002ed00  pop     rdi
0x18002ed01  pop     rsi
0x18002ed02  pop     rbx
0x18002ed03  pop     rbp
0x18002ed04  retn
```

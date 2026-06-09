# GetProxyVectorFromList(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *)

- ea: `0x180047988`
- end: `0x180047c8d`
- name: `?GetProxyVectorFromList@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBG@Z`
- size: `773`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046eac`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000d630`
- `0x18000d640`
- `0x18000dc5b`
- `0x18002d674`
- `0x180030a68`
- `0x180030aac`
- `0x18004609c`
- `0x180047988`

## import_xrefs

- `WINHTTP!WinHttpCrackUrl` at `0x180047a04`
- `WINHTTP!WinHttpCrackUrl` at `0x180047a04`

## string_xrefs

- `0x180047c7b`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetProxyVectorFromList(_QWORD *a1, __int64 *a2, __int16 *a3)
{
  DWORD v6; // edx
  const char *v7; // r9
  __int16 *i; // r15
  __int16 v9; // ax
  void **v10; // r14
  char *v11; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v13; // rsi
  const wchar_t *v14; // rax
  INTERNET_SCHEME nScheme; // ecx
  unsigned __int64 v16; // r9
  unsigned __int64 v17; // rbx
  void **v18; // r14
  void **v19; // r8
  unsigned __int64 v20; // r10
  unsigned __int64 v21; // rax
  char *v22; // rbx
  __int64 v23; // rax
  void **v24; // r14
  char *v25; // rbx
  __int64 v26; // rax
  unsigned __int64 v27; // rdx
  void **v28; // rcx
  unsigned __int64 v29; // rbx
  __int64 v30; // rdx
  __int16 j; // ax
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+30h] [rbp-79h] BYREF
  void *v34[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v35; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  memset_0(&UrlComponents.dwStructSize + 1, 0, 0x64u);
  UrlComponents.dwStructSize = 104;
  v6 = *((_DWORD *)a2 + 4);
  if ( (unsigned __int64)a2[3] > 7 )
    a2 = (__int64 *)*a2;
  if ( !WinHttpCrackUrl((LPCWSTR)a2, v6, 0, &UrlComponents) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x25,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      v7);
  if ( a3 )
  {
    while ( 1 )
    {
      if ( !*a3 )
        return a1;
      for ( i = a3 + 1; ; ++i )
      {
        v9 = *i;
        if ( !*i || v9 == 59 || v9 == 32 )
          break;
      }
      *(_OWORD *)v34 = 0;
      v35 = 0u;
      std::wstring::_Construct<1,unsigned short const *>(v34, a3, i - a3);
      v10 = v34;
      if ( *((_QWORD *)&v35 + 1) > 7u )
        v10 = (void **)v34[0];
      if ( !(_QWORD)v35 )
        goto LABEL_41;
      v11 = (char *)v10 + 2 * v35;
      trivial_2 = _std_find_trivial_2(v10, v11, 61);
      if ( (char *)trivial_2 == v11 )
        goto LABEL_41;
      v13 = (trivial_2 - (__int64)v10) >> 1;
      if ( v13 == -1 )
        goto LABEL_41;
      v14 = L"https";
      nScheme = UrlComponents.nScheme;
      if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER )
        v14 = L"http";
      v16 = -1;
      do
        ++v16;
      while ( v14[v16] );
      v17 = v35;
      v18 = v34;
      v19 = (void **)v34[0];
      v20 = *((_QWORD *)&v35 + 1);
      if ( *((_QWORD *)&v35 + 1) > 7u )
        v18 = (void **)v34[0];
      if ( v16 <= (unsigned __int64)v35 )
      {
        if ( v16 )
        {
          v22 = (char *)v18 + 2 * v35;
          v23 = _std_search_2(v18, v22, v14);
          if ( (char *)v23 == v22 )
            goto LABEL_44;
          v21 = (v23 - (__int64)v18) >> 1;
          if ( v21 == -1 )
            goto LABEL_44;
          nScheme = UrlComponents.nScheme;
          v20 = *((_QWORD *)&v35 + 1);
          v17 = v35;
          v19 = (void **)v34[0];
        }
        else
        {
          v21 = 0;
        }
        if ( v13 <= v21 )
          goto LABEL_44;
        if ( nScheme != INTERNET_SCHEME_FTP )
          goto LABEL_36;
        v24 = v34;
        if ( v20 > 7 )
          v24 = v19;
        if ( v17 < 5 )
          goto LABEL_36;
        v25 = (char *)v24 + 2 * v17;
        v26 = _std_search_2(v24, v25, L"https");
        if ( (char *)v26 == v25 || (v26 - (__int64)v24) >> 1 == -1 )
        {
          v20 = *((_QWORD *)&v35 + 1);
          v17 = v35;
          v19 = (void **)v34[0];
LABEL_36:
          v27 = v17;
          if ( v17 >= v13 + 1 )
            v27 = v13 + 1;
          v28 = v34;
          if ( v20 > 7 )
            v28 = v19;
          v29 = v17 - v27;
          memmove_0(v28, (char *)v28 + 2 * v27, 2 * v29 + 2);
          *(_QWORD *)&v35 = v29;
LABEL_41:
          v30 = a1[1];
          if ( v30 == a1[2] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, v30, v34);
          }
          else
          {
            *(_OWORD *)v30 = 0;
            *(_QWORD *)(v30 + 16) = 0;
            *(_QWORD *)(v30 + 24) = 0;
            *(_OWORD *)v30 = *(_OWORD *)v34;
            *(_OWORD *)(v30 + 16) = v35;
            *(_QWORD *)&v35 = 0;
            *((_QWORD *)&v35 + 1) = 7;
            LOWORD(v34[0]) = 0;
            a1[1] += 32LL;
          }
        }
      }
LABEL_44:
      a3 = i;
      for ( j = *i; *a3; j = *a3 )
      {
        if ( j != 59 && j != 32 )
          break;
        ++a3;
      }
      std::wstring::_Tidy_deallocate((char **)v34);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180047988  push    rbp
0x18004798a  push    rbx
0x18004798b  push    rsi
0x18004798c  push    rdi
0x18004798d  push    r12
0x18004798f  push    r14
0x180047991  push    r15
0x180047993  lea     rbp, [rsp-27h]
0x180047998  sub     rsp, 0D0h
0x18004799f  mov     rax, cs:__security_cookie
0x1800479a6  xor     rax, rsp
0x1800479a9  mov     [rbp+57h+var_40], rax
0x1800479ad  mov     rbx, r8
0x1800479b0  mov     rsi, rdx
0x1800479b3  mov     rdi, rcx
0x1800479b6  mov     [rsp+100h+var_D8], rcx
0x1800479bb  xor     r12d, r12d
0x1800479be  mov     [rsp+100h+var_E0], r12d
0x1800479c3  mov     [rcx], r12
0x1800479c6  mov     [rcx+8], r12
0x1800479ca  mov     [rcx+10h], r12
0x1800479ce  mov     [rsp+100h+var_E0], 1
0x1800479d6  xor     edx, edx; Val
0x1800479d8  lea     r8d, [r12+64h]; Size
0x1800479dd  lea     rcx, [rbp+57h+UrlComponents+4]; void *
0x1800479e1  call    memset_0
0x1800479e6  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800479ed  mov     edx, [rsi+10h]; dwUrlLength
0x1800479f0  cmp     qword ptr [rsi+18h], 7
0x1800479f5  jbe     short loc_1800479FA
0x1800479f7  mov     rsi, [rsi]
0x1800479fa  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x1800479fe  xor     r8d, r8d; dwFlags
0x180047a01  mov     rcx, rsi; pwszUrl
0x180047a04  call    cs:__imp_WinHttpCrackUrl
0x180047a0a  mov     rcx, [rbp+5Fh]; this
0x180047a0e  test    eax, eax
0x180047a10  jz      loc_180047C7B
0x180047a16  test    rbx, rbx
0x180047a19  jz      loc_180047C5A
0x180047a1f  mov     esi, 20h ; ' '
0x180047a24  cmp     [rbx], r12w
0x180047a28  jz      loc_180047C5A
0x180047a2e  lea     r15, [rbx+2]
0x180047a32  jmp     short loc_180047A43
0x180047a34  cmp     ax, 3Bh ; ';'
0x180047a38  jz      short loc_180047A4C
0x180047a3a  cmp     ax, si
0x180047a3d  jz      short loc_180047A4C
0x180047a3f  add     r15, 2
0x180047a43  movzx   eax, word ptr [r15]
0x180047a47  test    ax, ax
0x180047a4a  jnz     short loc_180047A34
0x180047a4c  xorps   xmm0, xmm0
0x180047a4f  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180047a53  mov     qword ptr [rbp+57h+var_50], r12
0x180047a57  mov     qword ptr [rbp+57h+var_50+8], r12
0x180047a5b  mov     r8, r15
0x180047a5e  sub     r8, rbx
0x180047a61  sar     r8, 1
0x180047a64  mov     rdx, rbx
0x180047a67  lea     rcx, [rbp+57h+var_60]
0x180047a6b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180047a70  nop
0x180047a71  mov     rax, qword ptr [rbp+57h+var_50]
0x180047a75  lea     r14, [rbp+57h+var_60]
0x180047a79  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180047a7e  cmova   r14, [rbp+57h+var_60]
0x180047a83  test    rax, rax
0x180047a86  jz      loc_180047BDA
0x180047a8c  lea     rbx, [r14+rax*2]
0x180047a90  mov     r8d, 3Dh ; '='
0x180047a96  mov     rdx, rbx
0x180047a99  mov     rcx, r14
0x180047a9c  call    __std_find_trivial_2
0x180047aa1  mov     rsi, rax
0x180047aa4  cmp     rax, rbx
0x180047aa7  jz      loc_180047BD5
0x180047aad  sub     rsi, r14
0x180047ab0  sar     rsi, 1
0x180047ab3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180047ab7  jz      loc_180047BD5
0x180047abd  lea     rax, aHttps_1; "https"
0x180047ac4  lea     rdx, aHttp_0; "http"
0x180047acb  mov     ecx, [rbp+57h+UrlComponents.nScheme]
0x180047ace  cmp     ecx, 2
0x180047ad1  cmovnz  rax, rdx
0x180047ad5  or      r9, 0FFFFFFFFFFFFFFFFh
0x180047ad9  inc     r9
0x180047adc  cmp     [rax+r9*2], r12w
0x180047ae1  jnz     short loc_180047AD9
0x180047ae3  mov     rbx, qword ptr [rbp+57h+var_50]
0x180047ae7  lea     r14, [rbp+57h+var_60]
0x180047aeb  mov     r8, [rbp+57h+var_60]
0x180047aef  mov     r10, qword ptr [rbp+57h+var_50+8]
0x180047af3  cmp     r10, 7
0x180047af7  cmova   r14, r8
0x180047afb  cmp     r9, rbx
0x180047afe  ja      loc_180047C24
0x180047b04  test    r9, r9
0x180047b07  jnz     short loc_180047B0E
0x180047b09  mov     rax, r12
0x180047b0c  jmp     short loc_180047B48
0x180047b0e  lea     rbx, [r14+rbx*2]
0x180047b12  mov     r8, rax
0x180047b15  mov     rdx, rbx
0x180047b18  mov     rcx, r14
0x180047b1b  call    __std_search_2
0x180047b20  cmp     rax, rbx
0x180047b23  jz      loc_180047C24
0x180047b29  sub     rax, r14
0x180047b2c  sar     rax, 1
0x180047b2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047b33  jz      loc_180047C24
0x180047b39  mov     ecx, [rbp+57h+UrlComponents.nScheme]
0x180047b3c  mov     r10, qword ptr [rbp+57h+var_50+8]
0x180047b40  mov     rbx, qword ptr [rbp+57h+var_50]
0x180047b44  mov     r8, [rbp+57h+var_60]
0x180047b48  cmp     rsi, rax
0x180047b4b  jbe     loc_180047C24
0x180047b51  cmp     ecx, 1
0x180047b54  jnz     short loc_180047BA3
0x180047b56  lea     r14, [rbp+57h+var_60]
0x180047b5a  cmp     r10, 7
0x180047b5e  cmova   r14, r8
0x180047b62  cmp     rbx, 5
0x180047b66  jb      short loc_180047BA3
0x180047b68  lea     rbx, [r14+rbx*2]
0x180047b6c  lea     r9d, [rcx+4]
0x180047b70  lea     r8, aHttps_1; "https"
0x180047b77  mov     rdx, rbx
0x180047b7a  mov     rcx, r14
0x180047b7d  call    __std_search_2
0x180047b82  cmp     rax, rbx
0x180047b85  jz      short loc_180047B97
0x180047b87  sub     rax, r14
0x180047b8a  sar     rax, 1
0x180047b8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047b91  jnz     loc_180047C24
0x180047b97  mov     r10, qword ptr [rbp+57h+var_50+8]
0x180047b9b  mov     rbx, qword ptr [rbp+57h+var_50]
0x180047b9f  mov     r8, [rbp+57h+var_60]
0x180047ba3  lea     rax, [rsi+1]
0x180047ba7  mov     rdx, rbx
0x180047baa  cmp     rbx, rax
0x180047bad  cmovnb  rdx, rax
0x180047bb1  lea     rcx, [rbp+57h+var_60]
0x180047bb5  cmp     r10, 7
0x180047bb9  cmova   rcx, r8; void *
0x180047bbd  sub     rbx, rdx
0x180047bc0  lea     r8, ds:2[rbx*2]; Size
0x180047bc8  lea     rdx, [rcx+rdx*2]; Src
0x180047bcc  call    memmove_0
0x180047bd1  mov     qword ptr [rbp+57h+var_50], rbx
0x180047bd5  mov     esi, 20h ; ' '
0x180047bda  mov     rdx, [rdi+8]
0x180047bde  cmp     rdx, [rdi+10h]
0x180047be2  jz      short loc_180047C18
0x180047be4  xorps   xmm0, xmm0
0x180047be7  movups  xmmword ptr [rdx], xmm0
0x180047bea  mov     [rdx+10h], r12
0x180047bee  mov     [rdx+18h], r12
0x180047bf2  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x180047bf6  movups  xmmword ptr [rdx], xmm0
0x180047bf9  movups  xmm1, [rbp+57h+var_50]
0x180047bfd  movups  xmmword ptr [rdx+10h], xmm1
0x180047c01  mov     qword ptr [rbp+57h+var_50], r12
0x180047c05  mov     qword ptr [rbp+57h+var_50+8], 7
0x180047c0d  mov     word ptr [rbp+57h+var_60], r12w
0x180047c12  add     [rdi+8], rsi
0x180047c16  jmp     short loc_180047C24
0x180047c18  lea     r8, [rbp+57h+var_60]
0x180047c1c  mov     rcx, rdi
0x180047c1f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180047c24  mov     rbx, r15
0x180047c27  movzx   eax, word ptr [r15]
0x180047c2b  test    ax, ax
0x180047c2e  jz      short loc_180047C4C
0x180047c30  mov     ecx, 20h ; ' '
0x180047c35  cmp     ax, 3Bh ; ';'
0x180047c39  jz      short loc_180047C40
0x180047c3b  cmp     ax, cx
0x180047c3e  jnz     short loc_180047C4C
0x180047c40  add     rbx, 2
0x180047c44  movzx   eax, word ptr [rbx]
0x180047c47  test    ax, ax
0x180047c4a  jnz     short loc_180047C35
0x180047c4c  lea     rcx, [rbp+57h+var_60]
0x180047c50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047c55  jmp     loc_180047A1F
0x180047c5a  mov     rax, rdi
0x180047c5d  mov     rcx, [rbp+57h+var_40]
0x180047c61  xor     rcx, rsp; StackCookie
0x180047c64  call    __security_check_cookie
0x180047c69  add     rsp, 0D0h
0x180047c70  pop     r15
0x180047c72  pop     r14
0x180047c74  pop     r12
0x180047c76  pop     rdi
0x180047c77  pop     rsi
0x180047c78  pop     rbx
0x180047c79  pop     rbp
0x180047c7a  retn
0x180047c7b  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180047c82  mov     edx, 25h ; '%'; void *
0x180047c87  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

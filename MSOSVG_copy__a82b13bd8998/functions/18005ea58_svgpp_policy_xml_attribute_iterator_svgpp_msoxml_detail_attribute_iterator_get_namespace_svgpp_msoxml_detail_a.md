# svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_namespace(svgpp::msoxml_detail::attribute_iterator const &)

- ea: `0x18005ea58`
- end: `0x18005ec87`
- name: `?get_namespace@?$attribute_iterator@V0msoxml_detail@svgpp@@@xml@policy@svgpp@@SA?AW4namespace_id@detail@4@AEBVattribute_iterator@msoxml_detail@4@@Z`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `50`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180061a14`
- `0x18006b644`
- `0x18006b968`
- `0x18006bc8c`
- `0x18006bfb0`
- `0x18006c2d4`
- `0x18006c5f8`
- `0x18006c91c`
- `0x18006cca8`
- `0x18006cfcc`
- `0x18006d2f0`
- `0x18006d614`
- `0x18006d938`
- `0x18006dc5c`
- `0x18006df80`
- `0x18006e2a4`
- `0x18006e5c8`
- `0x18006e8ec`
- `0x18006ec10`
- `0x18006ef34`
- `0x18006f258`
- `0x18006f57c`
- `0x18006f8a0`
- `0x18006fbc4`
- `0x18006fee8`
- `0x1800b3a40`
- `0x1800b3d64`
- `0x1800b4090`
- `0x1800b43b4`
- `0x1800b46e0`
- `0x1800b4a04`
- `0x1800b4d30`
- `0x1800b5054`
- `0x1800b5380`
- `0x1800b56a4`
- `0x1800b59d0`
- `0x1800b5cf4`
- `0x1800b6020`
- `0x1800b6344`
- `0x1800b6670`
- `0x1800b6994`
- `0x1800b6cc0`
- `0x1800b70e4`
- `0x1800b7518`
- `0x1800b7840`
- `0x1800ede50`
- `0x1800ee278`
- `0x1800ee65c`
- `0x1800eea30`
- `0x1800eed54`

## callees

- `0x180009068`
- `0x180009618`
- `0x18005ea58`
- `0x18005ec88`
- `0x18013d700`
- `0x18013f6aa`
- `0x18013f810`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005ec0e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec47`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec56`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec0e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec47`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec56`
- `OLEAUT32!__imp_SysStringLen` at `0x18005eaeb`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ec24`
- `OLEAUT32!__imp_SysStringLen` at `0x18005eaeb`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ec24`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005ebe3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005ebe3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005ebd9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005ebd9`

## string_xrefs

- `0x18005eb45`: `http://www.w3.org/XML/1998/namespace`
- `0x18005eb7e`: `http://www.w3.org/1999/xlink`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_namespace(
        __int64 a1)
{
  OLECHAR *v2; // rdi
  unsigned int AttributeDefaultNamespace; // esi
  __int64 v4; // rax
  BSTR v5; // rbx
  void **v6; // rcx
  void **v7; // rbx
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  void **v10; // rdx
  void **v11; // rcx
  char *v12; // rcx
  void **v13; // rdx
  void **v14; // rcx
  OLECHAR *v15; // rbx
  UINT v16; // eax
  __m128i bstrString; // [rsp+30h] [rbp-50h] BYREF
  char v19[8]; // [rsp+40h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-38h]
  void *Buf2[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v22; // [rsp+60h] [rbp-20h]

  v2 = 0;
  bstrString.m128i_i64[0] = 0;
  AttributeDefaultNamespace = 1;
  v19[0] = 1;
  pbstr = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 48LL))(*(_QWORD *)(a1 + 8));
  if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 232LL))(v4, v19) || v19[0] || (v5 = pbstr) == 0 )
  {
    svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_local_name(&bstrString, a1);
    v15 = (OLECHAR *)bstrString.m128i_i64[0];
    if ( bstrString.m128i_i64[0] )
    {
      v16 = SysStringLen((BSTR)bstrString.m128i_i64[0]);
      bstrString.m128i_i64[0] = (__int64)v15;
      bstrString.m128i_i64[1] = v16;
      AttributeDefaultNamespace = svgpp::policy::xml::GetAttributeDefaultNamespace(&bstrString);
      SysFreeString(v15);
    }
    else
    {
      AttributeDefaultNamespace = 0;
    }
  }
  else
  {
    v2 = pbstr;
    bstrString.m128i_i64[0] = (__int64)pbstr;
    SysStringLen(pbstr);
    *(_OWORD *)Buf2 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t *>(Buf2, v5);
    v6 = Buf2;
    v7 = (void **)Buf2[0];
    v8 = *((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) > 7u )
      v6 = (void **)Buf2[0];
    v9 = 2 * v22;
    v10 = Buf2;
    if ( *((_QWORD *)&v22 + 1) > 7u )
      v10 = (void **)Buf2[0];
    if ( (void **)((char *)v6 + v9 - (_QWORD)v10) != (void **)72
      || memcmp_0(L"http://www.w3.org/XML/1998/namespace", v10, 0x48u) )
    {
      v11 = Buf2;
      if ( v8 > 7 )
        v11 = v7;
      v12 = (char *)v11 + v9;
      v13 = Buf2;
      if ( v8 > 7 )
        v13 = v7;
      if ( v12 - (char *)v13 != 56
        || (AttributeDefaultNamespace = 2, memcmp_0(L"http://www.w3.org/1999/xlink", v13, 0x38u)) )
      {
        AttributeDefaultNamespace = 3;
      }
    }
    if ( v8 > 7 )
    {
      v14 = v7;
      if ( 2 * v8 + 2 >= 0x1000 )
      {
        v7 = (void **)*(v7 - 1);
        if ( (unsigned __int64)((char *)v14 - (char *)v7 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v7);
    }
  }
  if ( v2 )
    SysFreeString(v2);
  return AttributeDefaultNamespace;
}

```

## disassembly

```asm
0x18005ea58  mov     [rsp-18h+arg_8], rbx
0x18005ea5d  mov     [rsp-18h+arg_10], rsi
0x18005ea62  mov     [rsp-18h+arg_18], rdi
0x18005ea67  push    rbp
0x18005ea68  push    r14
0x18005ea6a  push    r15
0x18005ea6c  mov     rbp, rsp
0x18005ea6f  sub     rsp, 80h
0x18005ea76  mov     rax, cs:__security_cookie
0x18005ea7d  xor     rax, rsp
0x18005ea80  mov     [rbp+var_10], rax
0x18005ea84  mov     r14, rcx
0x18005ea87  xor     edi, edi
0x18005ea89  mov     [rbp+bstrString], rdi
0x18005ea8d  lea     esi, [rdi+1]
0x18005ea90  mov     [rbp+var_40], sil
0x18005ea94  mov     [rbp+pbstr], rdi
0x18005ea98  mov     rcx, [rcx+8]
0x18005ea9c  mov     rax, [rcx]
0x18005ea9f  mov     rax, [rax+30h]
0x18005eaa3  call    cs:__guard_dispatch_icall_fptr
0x18005eaa9  mov     r8, rax
0x18005eaac  mov     rcx, [rax]
0x18005eaaf  mov     rax, [rcx+0E8h]
0x18005eab6  lea     rdx, [rbp+var_40]
0x18005eaba  mov     rcx, r8
0x18005eabd  call    cs:__guard_dispatch_icall_fptr
0x18005eac3  test    eax, eax
0x18005eac5  jnz     loc_18005EBEB
0x18005eacb  cmp     [rbp+var_40], al
0x18005eace  jnz     loc_18005EBEB
0x18005ead4  mov     rbx, [rbp+pbstr]
0x18005ead8  test    rbx, rbx
0x18005eadb  jz      loc_18005EBEB
0x18005eae1  mov     rdi, rbx
0x18005eae4  mov     [rbp+bstrString], rbx
0x18005eae8  mov     rcx, rbx; pbstr
0x18005eaeb  call    cs:__imp_SysStringLen
0x18005eaf1  mov     r8d, eax
0x18005eaf4  xorps   xmm0, xmm0
0x18005eaf7  movups  xmmword ptr [rbp+Buf2], xmm0
0x18005eafb  xorps   xmm1, xmm1
0x18005eafe  movdqu  [rbp+var_20], xmm1
0x18005eb03  mov     rdx, rbx
0x18005eb06  lea     rcx, [rbp+Buf2]
0x18005eb0a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18005eb0f  lea     rcx, [rbp+Buf2]
0x18005eb13  mov     rbx, [rbp+Buf2]
0x18005eb17  mov     r14, qword ptr [rbp+var_20+8]
0x18005eb1b  cmp     r14, 7
0x18005eb1f  cmova   rcx, rbx
0x18005eb23  mov     rax, qword ptr [rbp+var_20]
0x18005eb27  lea     r15, [rax+rax]
0x18005eb2b  lea     rdx, [rbp+Buf2]
0x18005eb2f  cmova   rdx, rbx; Buf2
0x18005eb33  mov     rax, r15
0x18005eb36  sub     rax, rdx
0x18005eb39  add     rax, rcx
0x18005eb3c  lea     r8d, [rsi+47h]; Size
0x18005eb40  cmp     rax, r8
0x18005eb43  jnz     short loc_18005EB55
0x18005eb45  lea     rcx, ?value@?1???$xml_namespace_uri@_W@detail@svgpp@@YA?AV?$iterator_range@PEB_W@boost@@XZ@4QB_WB; "http://www.w3.org/XML/1998/namespace"
0x18005eb4c  call    memcmp_0
0x18005eb51  test    eax, eax
0x18005eb53  jz      short loc_18005EB98
0x18005eb55  lea     rcx, [rbp+Buf2]
0x18005eb59  cmp     r14, 7
0x18005eb5d  cmova   rcx, rbx
0x18005eb61  add     rcx, r15
0x18005eb64  lea     rdx, [rbp+Buf2]
0x18005eb68  cmp     r14, 7
0x18005eb6c  cmova   rdx, rbx; Buf2
0x18005eb70  sub     rcx, rdx
0x18005eb73  mov     r8d, 38h ; '8'; Size
0x18005eb79  cmp     rcx, r8
0x18005eb7c  jnz     short loc_18005EB93
0x18005eb7e  lea     rcx, ?value@?1???$xlink_namespace_uri@_W@detail@svgpp@@YA?AV?$iterator_range@PEB_W@boost@@XZ@4QB_WB; "http://www.w3.org/1999/xlink"
0x18005eb85  call    memcmp_0
0x18005eb8a  test    eax, eax
0x18005eb8c  mov     esi, 2
0x18005eb91  jz      short loc_18005EB98
0x18005eb93  mov     esi, 3
0x18005eb98  cmp     r14, 7
0x18005eb9c  jbe     loc_18005EC4E
0x18005eba2  mov     rcx, rbx
0x18005eba5  lea     rax, ds:2[r14*2]
0x18005ebad  cmp     rax, 1000h
0x18005ebb3  jb      short loc_18005EBE0
0x18005ebb5  mov     rbx, [rbx-8]
0x18005ebb9  sub     rcx, rbx
0x18005ebbc  lea     rax, [rcx-8]
0x18005ebc0  cmp     rax, 1Fh
0x18005ebc4  jbe     short loc_18005EBE0
0x18005ebc6  mov     [rsp+80h+Reserved], 0; Reserved
0x18005ebcf  xor     r9d, r9d; LineNo
0x18005ebd2  xor     r8d, r8d; FileName
0x18005ebd5  xor     edx, edx; FunctionName
0x18005ebd7  xor     ecx, ecx; Expression
0x18005ebd9  call    cs:__imp__invoke_watson
0x18005ebe0  mov     rcx, rbx; Block
0x18005ebe3  call    cs:__imp_free
0x18005ebe9  jmp     short loc_18005EC4E
0x18005ebeb  mov     rdx, r14
0x18005ebee  lea     rcx, [rbp+bstrString]
0x18005ebf2  call    ?get_local_name@?$attribute_iterator@V0msoxml_detail@svgpp@@@xml@policy@svgpp@@SA?AVBStrHolder@Mso@@AEBVattribute_iterator@msoxml_detail@4@@Z; svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_local_name(svgpp::msoxml_detail::attribute_iterator const &)
0x18005ebf7  mov     rbx, [rbp+bstrString]
0x18005ebfb  test    rbx, rbx
0x18005ebfe  setz    r14b
0x18005ec02  test    rbx, rbx
0x18005ec05  jnz     short loc_18005EC18
0x18005ec07  test    r14b, r14b
0x18005ec0a  jnz     short loc_18005EC14
0x18005ec0c  xor     ecx, ecx; bstrString
0x18005ec0e  call    cs:__imp_SysFreeString
0x18005ec14  xor     esi, esi
0x18005ec16  jmp     short loc_18005EC4E
0x18005ec18  test    r14b, r14b
0x18005ec1b  jz      short loc_18005EC21
0x18005ec1d  xor     eax, eax
0x18005ec1f  jmp     short loc_18005EC2A
0x18005ec21  mov     rcx, rbx; pbstr
0x18005ec24  call    cs:__imp_SysStringLen
0x18005ec2a  mov     [rbp+bstrString], rbx
0x18005ec2e  mov     eax, eax
0x18005ec30  mov     [rbp+var_48], rax
0x18005ec34  lea     rcx, [rbp+bstrString]
0x18005ec38  call    ?GetAttributeDefaultNamespace@xml@policy@svgpp@@YA?AW4namespace_id@detail@3@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; svgpp::policy::xml::GetAttributeDefaultNamespace(std::wstring_view const &)
0x18005ec3d  mov     esi, eax
0x18005ec3f  test    r14b, r14b
0x18005ec42  jnz     short loc_18005EC4E
0x18005ec44  mov     rcx, rbx; bstrString
0x18005ec47  call    cs:__imp_SysFreeString
0x18005ec4d  nop
0x18005ec4e  test    rdi, rdi
0x18005ec51  jz      short loc_18005EC5C
0x18005ec53  mov     rcx, rdi; bstrString
0x18005ec56  call    cs:__imp_SysFreeString
0x18005ec5c  mov     eax, esi
0x18005ec5e  mov     rcx, [rbp+var_10]
0x18005ec62  xor     rcx, rsp; StackCookie
0x18005ec65  call    __security_check_cookie
0x18005ec6a  lea     r11, [rsp+80h+var_s0]
0x18005ec72  mov     rbx, [r11+28h]
0x18005ec76  mov     rsi, [r11+30h]
0x18005ec7a  mov     rdi, [r11+38h]
0x18005ec7e  mov     rsp, r11
0x18005ec81  pop     r15
0x18005ec83  pop     r14
0x18005ec85  pop     rbp
0x18005ec86  retn
```

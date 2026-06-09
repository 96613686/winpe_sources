# svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_namespace(svgpp::msoxml_detail::attribute_iterator const &)

- ea: `0x18005ea38`
- end: `0x18005ec67`
- name: `?get_namespace@?$attribute_iterator@V0msoxml_detail@svgpp@@@xml@policy@svgpp@@SA?AW4namespace_id@detail@4@AEBVattribute_iterator@msoxml_detail@4@@Z`
- size: `559`
- prototype: ``
- caller_count: `50`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800619f4`
- `0x18006b624`
- `0x18006b948`
- `0x18006bc6c`
- `0x18006bf90`
- `0x18006c2b4`
- `0x18006c5d8`
- `0x18006c8fc`
- `0x18006cc88`
- `0x18006cfac`
- `0x18006d2d0`
- `0x18006d5f4`
- `0x18006d918`
- `0x18006dc3c`
- `0x18006df60`
- `0x18006e284`
- `0x18006e5a8`
- `0x18006e8cc`
- `0x18006ebf0`
- `0x18006ef14`
- `0x18006f238`
- `0x18006f55c`
- `0x18006f880`
- `0x18006fba4`
- `0x18006fec8`
- `0x1800b3a20`
- `0x1800b3d44`
- `0x1800b4070`
- `0x1800b4394`
- `0x1800b46c0`
- `0x1800b49e4`
- `0x1800b4d10`
- `0x1800b5034`
- `0x1800b5360`
- `0x1800b5684`
- `0x1800b59b0`
- `0x1800b5cd4`
- `0x1800b6000`
- `0x1800b6324`
- `0x1800b6650`
- `0x1800b6974`
- `0x1800b6ca0`
- `0x1800b70c4`
- `0x1800b74f8`
- `0x1800b7820`
- `0x1800ede30`
- `0x1800ee258`
- `0x1800ee63c`
- `0x1800eea10`
- `0x1800eed34`

## callees

- `0x180009068`
- `0x180009618`
- `0x18005ea38`
- `0x18005ec68`
- `0x18013d650`
- `0x18013f5fa`
- `0x18013f760`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005ebee`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec27`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec36`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ebee`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec27`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ec36`
- `OLEAUT32!__imp_SysStringLen` at `0x18005eacb`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ec04`
- `OLEAUT32!__imp_SysStringLen` at `0x18005eacb`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ec04`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005ebc3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18005ebc3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005ebb9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18005ebb9`

## string_xrefs

- `0x18005eb25`: `http://www.w3.org/XML/1998/namespace`
- `0x18005eb5e`: `http://www.w3.org/1999/xlink`

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
  UINT v6; // eax
  void **v7; // rcx
  void **v8; // rbx
  unsigned __int64 v9; // r14
  __int64 v10; // r15
  void **v11; // rdx
  void **v12; // rcx
  char *v13; // rcx
  void **v14; // rdx
  void **v15; // rcx
  OLECHAR *v16; // rbx
  UINT v17; // eax
  __m128i bstrString; // [rsp+30h] [rbp-50h] BYREF
  char v20[8]; // [rsp+40h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-38h]
  void *Buf2[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v23; // [rsp+60h] [rbp-20h]

  v2 = 0;
  bstrString.m128i_i64[0] = 0;
  AttributeDefaultNamespace = 1;
  v20[0] = 1;
  pbstr = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 48LL))(*(_QWORD *)(a1 + 8));
  if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 232LL))(v4, v20) || v20[0] || (v5 = pbstr) == 0 )
  {
    svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_local_name(&bstrString, a1);
    v16 = (OLECHAR *)bstrString.m128i_i64[0];
    if ( bstrString.m128i_i64[0] )
    {
      v17 = SysStringLen((BSTR)bstrString.m128i_i64[0]);
      bstrString.m128i_i64[0] = (__int64)v16;
      bstrString.m128i_i64[1] = v17;
      AttributeDefaultNamespace = svgpp::policy::xml::GetAttributeDefaultNamespace(&bstrString);
      SysFreeString(v16);
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
    v6 = SysStringLen(pbstr);
    *(_OWORD *)Buf2 = 0;
    v23 = 0;
    std::wstring::_Construct<1,wchar_t *>(Buf2, v5, v6);
    v7 = Buf2;
    v8 = (void **)Buf2[0];
    v9 = *((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) > 7u )
      v7 = (void **)Buf2[0];
    v10 = 2 * v23;
    v11 = Buf2;
    if ( *((_QWORD *)&v23 + 1) > 7u )
      v11 = (void **)Buf2[0];
    if ( (void **)((char *)v7 + v10 - (_QWORD)v11) != (void **)72
      || memcmp_0(L"http://www.w3.org/XML/1998/namespace", v11, 0x48u) )
    {
      v12 = Buf2;
      if ( v9 > 7 )
        v12 = v8;
      v13 = (char *)v12 + v10;
      v14 = Buf2;
      if ( v9 > 7 )
        v14 = v8;
      if ( v13 - (char *)v14 != 56
        || (AttributeDefaultNamespace = 2, memcmp_0(L"http://www.w3.org/1999/xlink", v14, 0x38u)) )
      {
        AttributeDefaultNamespace = 3;
      }
    }
    if ( v9 > 7 )
    {
      v15 = v8;
      if ( 2 * v9 + 2 >= 0x1000 )
      {
        v8 = (void **)*(v8 - 1);
        if ( (unsigned __int64)((char *)v15 - (char *)v8 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v8);
    }
  }
  if ( v2 )
    SysFreeString(v2);
  return AttributeDefaultNamespace;
}

```

## disassembly

```asm
0x18005ea38  mov     [rsp-18h+arg_8], rbx
0x18005ea3d  mov     [rsp-18h+arg_10], rsi
0x18005ea42  mov     [rsp-18h+arg_18], rdi
0x18005ea47  push    rbp
0x18005ea48  push    r14
0x18005ea4a  push    r15
0x18005ea4c  mov     rbp, rsp
0x18005ea4f  sub     rsp, 80h
0x18005ea56  mov     rax, cs:__security_cookie
0x18005ea5d  xor     rax, rsp
0x18005ea60  mov     [rbp+var_10], rax
0x18005ea64  mov     r14, rcx
0x18005ea67  xor     edi, edi
0x18005ea69  mov     [rbp+bstrString], rdi
0x18005ea6d  lea     esi, [rdi+1]
0x18005ea70  mov     [rbp+var_40], sil
0x18005ea74  mov     [rbp+pbstr], rdi
0x18005ea78  mov     rcx, [rcx+8]
0x18005ea7c  mov     rax, [rcx]
0x18005ea7f  mov     rax, [rax+30h]
0x18005ea83  call    cs:__guard_dispatch_icall_fptr
0x18005ea89  mov     r8, rax
0x18005ea8c  mov     rcx, [rax]
0x18005ea8f  mov     rax, [rcx+0E8h]
0x18005ea96  lea     rdx, [rbp+var_40]
0x18005ea9a  mov     rcx, r8
0x18005ea9d  call    cs:__guard_dispatch_icall_fptr
0x18005eaa3  test    eax, eax
0x18005eaa5  jnz     loc_18005EBCB
0x18005eaab  cmp     [rbp+var_40], al
0x18005eaae  jnz     loc_18005EBCB
0x18005eab4  mov     rbx, [rbp+pbstr]
0x18005eab8  test    rbx, rbx
0x18005eabb  jz      loc_18005EBCB
0x18005eac1  mov     rdi, rbx
0x18005eac4  mov     [rbp+bstrString], rbx
0x18005eac8  mov     rcx, rbx; pbstr
0x18005eacb  call    cs:__imp_SysStringLen
0x18005ead1  mov     r8d, eax
0x18005ead4  xorps   xmm0, xmm0
0x18005ead7  movups  xmmword ptr [rbp+Buf2], xmm0
0x18005eadb  xorps   xmm1, xmm1
0x18005eade  movdqu  [rbp+var_20], xmm1
0x18005eae3  mov     rdx, rbx
0x18005eae6  lea     rcx, [rbp+Buf2]
0x18005eaea  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18005eaef  lea     rcx, [rbp+Buf2]
0x18005eaf3  mov     rbx, [rbp+Buf2]
0x18005eaf7  mov     r14, qword ptr [rbp+var_20+8]
0x18005eafb  cmp     r14, 7
0x18005eaff  cmova   rcx, rbx
0x18005eb03  mov     rax, qword ptr [rbp+var_20]
0x18005eb07  lea     r15, [rax+rax]
0x18005eb0b  lea     rdx, [rbp+Buf2]
0x18005eb0f  cmova   rdx, rbx; Buf2
0x18005eb13  mov     rax, r15
0x18005eb16  sub     rax, rdx
0x18005eb19  add     rax, rcx
0x18005eb1c  lea     r8d, [rsi+47h]; Size
0x18005eb20  cmp     rax, r8
0x18005eb23  jnz     short loc_18005EB35
0x18005eb25  lea     rcx, ?value@?1???$xml_namespace_uri@_W@detail@svgpp@@YA?AV?$iterator_range@PEB_W@boost@@XZ@4QB_WB; "http://www.w3.org/XML/1998/namespace"
0x18005eb2c  call    memcmp_0
0x18005eb31  test    eax, eax
0x18005eb33  jz      short loc_18005EB78
0x18005eb35  lea     rcx, [rbp+Buf2]
0x18005eb39  cmp     r14, 7
0x18005eb3d  cmova   rcx, rbx
0x18005eb41  add     rcx, r15
0x18005eb44  lea     rdx, [rbp+Buf2]
0x18005eb48  cmp     r14, 7
0x18005eb4c  cmova   rdx, rbx; Buf2
0x18005eb50  sub     rcx, rdx
0x18005eb53  mov     r8d, 38h ; '8'; Size
0x18005eb59  cmp     rcx, r8
0x18005eb5c  jnz     short loc_18005EB73
0x18005eb5e  lea     rcx, ?value@?1???$xlink_namespace_uri@_W@detail@svgpp@@YA?AV?$iterator_range@PEB_W@boost@@XZ@4QB_WB; "http://www.w3.org/1999/xlink"
0x18005eb65  call    memcmp_0
0x18005eb6a  test    eax, eax
0x18005eb6c  mov     esi, 2
0x18005eb71  jz      short loc_18005EB78
0x18005eb73  mov     esi, 3
0x18005eb78  cmp     r14, 7
0x18005eb7c  jbe     loc_18005EC2E
0x18005eb82  mov     rcx, rbx
0x18005eb85  lea     rax, ds:2[r14*2]
0x18005eb8d  cmp     rax, 1000h
0x18005eb93  jb      short loc_18005EBC0
0x18005eb95  mov     rbx, [rbx-8]
0x18005eb99  sub     rcx, rbx
0x18005eb9c  lea     rax, [rcx-8]
0x18005eba0  cmp     rax, 1Fh
0x18005eba4  jbe     short loc_18005EBC0
0x18005eba6  mov     [rsp+80h+Reserved], 0; Reserved
0x18005ebaf  xor     r9d, r9d; LineNo
0x18005ebb2  xor     r8d, r8d; FileName
0x18005ebb5  xor     edx, edx; FunctionName
0x18005ebb7  xor     ecx, ecx; Expression
0x18005ebb9  call    cs:__imp__invoke_watson
0x18005ebc0  mov     rcx, rbx; Block
0x18005ebc3  call    cs:__imp_free
0x18005ebc9  jmp     short loc_18005EC2E
0x18005ebcb  mov     rdx, r14
0x18005ebce  lea     rcx, [rbp+bstrString]
0x18005ebd2  call    ?get_local_name@?$attribute_iterator@V0msoxml_detail@svgpp@@@xml@policy@svgpp@@SA?AVBStrHolder@Mso@@AEBVattribute_iterator@msoxml_detail@4@@Z; svgpp::policy::xml::attribute_iterator<svgpp::msoxml_detail::attribute_iterator>::get_local_name(svgpp::msoxml_detail::attribute_iterator const &)
0x18005ebd7  mov     rbx, [rbp+bstrString]
0x18005ebdb  test    rbx, rbx
0x18005ebde  setz    r14b
0x18005ebe2  test    rbx, rbx
0x18005ebe5  jnz     short loc_18005EBF8
0x18005ebe7  test    r14b, r14b
0x18005ebea  jnz     short loc_18005EBF4
0x18005ebec  xor     ecx, ecx; bstrString
0x18005ebee  call    cs:__imp_SysFreeString
0x18005ebf4  xor     esi, esi
0x18005ebf6  jmp     short loc_18005EC2E
0x18005ebf8  test    r14b, r14b
0x18005ebfb  jz      short loc_18005EC01
0x18005ebfd  xor     eax, eax
0x18005ebff  jmp     short loc_18005EC0A
0x18005ec01  mov     rcx, rbx; pbstr
0x18005ec04  call    cs:__imp_SysStringLen
0x18005ec0a  mov     [rbp+bstrString], rbx
0x18005ec0e  mov     eax, eax
0x18005ec10  mov     [rbp+var_48], rax
0x18005ec14  lea     rcx, [rbp+bstrString]
0x18005ec18  call    ?GetAttributeDefaultNamespace@xml@policy@svgpp@@YA?AW4namespace_id@detail@3@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; svgpp::policy::xml::GetAttributeDefaultNamespace(std::wstring_view const &)
0x18005ec1d  mov     esi, eax
0x18005ec1f  test    r14b, r14b
0x18005ec22  jnz     short loc_18005EC2E
0x18005ec24  mov     rcx, rbx; bstrString
0x18005ec27  call    cs:__imp_SysFreeString
0x18005ec2d  nop
0x18005ec2e  test    rdi, rdi
0x18005ec31  jz      short loc_18005EC3C
0x18005ec33  mov     rcx, rdi; bstrString
0x18005ec36  call    cs:__imp_SysFreeString
0x18005ec3c  mov     eax, esi
0x18005ec3e  mov     rcx, [rbp+var_10]
0x18005ec42  xor     rcx, rsp; StackCookie
0x18005ec45  call    __security_check_cookie
0x18005ec4a  lea     r11, [rsp+80h+var_s0]
0x18005ec52  mov     rbx, [r11+28h]
0x18005ec56  mov     rsi, [r11+30h]
0x18005ec5a  mov     rdi, [r11+38h]
0x18005ec5e  mov     rsp, r11
0x18005ec61  pop     r15
0x18005ec63  pop     r14
0x18005ec65  pop     rbp
0x18005ec66  retn
```

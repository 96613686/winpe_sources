# Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003c020`
- end: `0x18003c297`
- name: `?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180023570`
- `0x180023730`
- `0x18002f2f0`
- `0x180034170`
- `0x18003ba50`
- `0x18003bf20`
- `0x18003c2a0`
- `0x18003c4a0`
- `0x18003c6b0`
- `0x18003c8dc`
- `0x18003cb5c`

## callees

- `0x180009380`
- `0x18002f1f0`
- `0x1800338a4`
- `0x180034a30`
- `0x180034a70`
- `0x18003a614`
- `0x18003c020`
- `0x18003d200`
- `0x18003d3c8`
- `0x18003ddcc`
- `0x180052c68`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003c22a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c22a`

## string_xrefs

- `0x18003c107`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003c285`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Registry::GetRedirectedRegistryKeyName(__int64 a1, __int64 a2, const char **a3, __int64 a4)
{
  const char *v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rdx
  const wchar_t *v10; // rdx
  unsigned __int64 v11; // rbx
  const wchar_t *v12; // rcx
  unsigned __int64 v13; // r15
  size_t v14; // r8
  int v15; // eax
  char v16; // al
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, const char *, _QWORD *, BSTR *); // r15
  __int64 v19; // r8
  _QWORD *v20; // rax
  int v21; // eax
  const wchar_t *v22; // rbx
  void *v23; // rax
  __int64 v24; // rax
  int v26; // [rsp+20h] [rbp-59h]
  int v27; // [rsp+20h] [rbp-59h]
  wchar_t *S1[2]; // [rsp+40h] [rbp-39h] BYREF
  __int128 v29; // [rsp+50h] [rbp-29h]
  _BYTE v30[24]; // [rsp+68h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+7h] BYREF
  __int64 v32; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v32 = a2;
  v6 = *a3;
  *(_OWORD *)S1 = 0;
  v29 = 0u;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&v6[2 * v8] );
  std::wstring::_Construct<1,wchar_t const *>(S1);
  v9 = *(_QWORD *)(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
                     &Windows::Registry::s_defaultRedirectionMap,
                     v30,
                     S1)
                 + 16);
  if ( *(_BYTE *)(v9 + 25) )
    goto LABEL_12;
  v10 = (const wchar_t *)(v9 + 32);
  v11 = *((_QWORD *)v10 + 2);
  if ( *((_QWORD *)v10 + 3) > 7u )
    v10 = *(const wchar_t **)v10;
  v12 = (const wchar_t *)S1;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    v12 = S1[0];
  v13 = v29;
  v14 = v29;
  if ( v11 < (unsigned __int64)v29 )
    v14 = v11;
  v15 = wmemcmp(v12, v10, v14);
  if ( !v15 )
  {
    if ( v13 < v11 )
      goto LABEL_12;
LABEL_28:
    v16 = 0;
    goto LABEL_13;
  }
  if ( v15 >= 0 )
    goto LABEL_28;
LABEL_12:
  v16 = 1;
LABEL_13:
  LOBYTE(v26) = v16;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xD0,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)0x80070057LL,
    v26,
    (bool)"Redirection Id %ws not found in default map.",
    v6);
  std::wstring::~wstring(S1);
  v32 = 0;
  Windows::DockedHelpers::GetDockedSystem(&v32);
  bstrString = 0;
  v17 = v32;
  v18 = *(__int64 (__fastcall **)(__int64, const char *, _QWORD *, BSTR *))(*(_QWORD *)v32 + 24LL);
  bstrString = 0;
  *(_OWORD *)S1 = 0;
  v29 = 0;
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)&v6[2 * v19] );
  std::wstring::_Construct<1,wchar_t const *>(S1);
  v20 = (_QWORD *)std::map<std::wstring,std::wstring>::operator[](&Windows::Registry::s_defaultRedirectionMap, S1);
  if ( v20[3] > 7u )
    v20 = (_QWORD *)*v20;
  v21 = v18(v17, v6, v20, &bstrString);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)(unsigned int)v21,
      v27);
  std::wstring::~wstring(S1);
  v22 = &S2;
  if ( *(_QWORD *)(a4 + 8) )
    v22 = *(const wchar_t **)a4;
  v23 = (void *)Windows::Strings::to_wstring(S1, &bstrString);
  do
    ++v7;
  while ( v22[v7] );
  v24 = std::wstring::append(v23);
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  *(_OWORD *)a2 = *(_OWORD *)v24;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)(v24 + 16);
  *(_WORD *)v24 = 0;
  *(_QWORD *)(v24 + 16) = 0;
  *(_QWORD *)(v24 + 24) = 7;
  std::wstring::~wstring(S1);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  return a2;
}

```

## disassembly

```asm
0x18003c020  mov     [rsp-8+arg_0], rbx
0x18003c025  push    rbp
0x18003c026  push    rsi
0x18003c027  push    rdi
0x18003c028  push    r12
0x18003c02a  push    r13
0x18003c02c  push    r14
0x18003c02e  push    r15
0x18003c030  lea     rbp, [rsp-27h]
0x18003c035  sub     rsp, 0A0h
0x18003c03c  mov     rax, cs:__security_cookie
0x18003c043  xor     rax, rsp
0x18003c046  mov     [rbp+57h+var_40], rax
0x18003c04a  mov     r12, r9
0x18003c04d  mov     r14, rdx
0x18003c050  mov     [rbp+57h+var_48], rdx
0x18003c054  xor     r13d, r13d
0x18003c057  mov     rsi, [r8]
0x18003c05a  xorps   xmm0, xmm0
0x18003c05d  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18003c061  mov     qword ptr [rbp+57h+var_80], r13
0x18003c065  mov     qword ptr [rbp+57h+var_80+8], r13
0x18003c069  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003c06d  mov     r8, rdi
0x18003c070  inc     r8
0x18003c073  cmp     [rsi+r8*2], r13w
0x18003c078  jnz     short loc_18003C070
0x18003c07a  mov     rdx, rsi
0x18003c07d  lea     rcx, [rbp+57h+S1]
0x18003c081  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003c086  nop
0x18003c087  lea     r8, [rbp+57h+S1]
0x18003c08b  lea     rdx, [rbp+57h+var_68]
0x18003c08f  lea     rcx, ?s_defaultRedirectionMap@Registry@Windows@@0V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> Windows::Registry::s_defaultRedirectionMap
0x18003c096  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18003c09b  mov     rdx, [rax+10h]
0x18003c09f  cmp     [rdx+19h], r13b
0x18003c0a3  jnz     short loc_18003C0E6
0x18003c0a5  add     rdx, 20h ; ' '
0x18003c0a9  mov     rbx, [rdx+10h]
0x18003c0ad  cmp     qword ptr [rdx+18h], 7
0x18003c0b2  jbe     short loc_18003C0B7
0x18003c0b4  mov     rdx, [rdx]; S2
0x18003c0b7  lea     rcx, [rbp+57h+S1]
0x18003c0bb  cmp     qword ptr [rbp+57h+var_80+8], 7
0x18003c0c0  cmova   rcx, [rbp+57h+S1]; S1
0x18003c0c5  mov     r15, qword ptr [rbp+57h+var_80]
0x18003c0c9  mov     r8, r15
0x18003c0cc  cmp     rbx, r15
0x18003c0cf  cmovb   r8, rbx; N
0x18003c0d3  call    wmemcmp
0x18003c0d8  test    eax, eax
0x18003c0da  jz      loc_18003C271
0x18003c0e0  jns     loc_18003C27A
0x18003c0e6  mov     al, 1
0x18003c0e8  mov     rcx, [rbp+5Fh]; this
0x18003c0ec  mov     [rsp+0D0h+var_A0], rsi; char *
0x18003c0f1  lea     rdx, aRedirectionIdW; "Redirection Id %ws not found in default"...
0x18003c0f8  mov     qword ptr [rsp+0D0h+var_A8], rdx; bool
0x18003c0fd  mov     byte ptr [rsp+0D0h+var_B0], al; int
0x18003c101  mov     r9d, 80070057h; char *
0x18003c107  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c10e  mov     edx, 0D0h; void *
0x18003c113  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003c118  nop
0x18003c119  lea     rcx, [rbp+57h+S1]; void *
0x18003c11d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c122  mov     [rbp+57h+var_48], r13
0x18003c126  lea     rcx, [rbp+57h+var_48]
0x18003c12a  call    ?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedSystem(void)
0x18003c12f  nop
0x18003c130  mov     [rbp+57h+bstrString], r13
0x18003c134  mov     rbx, [rbp+57h+var_48]
0x18003c138  mov     rax, [rbx]
0x18003c13b  mov     r15, [rax+18h]
0x18003c13f  mov     [rbp+57h+bstrString], r13
0x18003c143  xorps   xmm0, xmm0
0x18003c146  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18003c14a  xorps   xmm1, xmm1
0x18003c14d  movdqu  [rbp+57h+var_80], xmm1
0x18003c152  mov     r8, rdi
0x18003c155  inc     r8
0x18003c158  cmp     [rsi+r8*2], r13w
0x18003c15d  jnz     short loc_18003C155
0x18003c15f  mov     rdx, rsi
0x18003c162  lea     rcx, [rbp+57h+S1]
0x18003c166  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003c16b  nop
0x18003c16c  lea     rdx, [rbp+57h+S1]
0x18003c170  lea     rcx, ?s_defaultRedirectionMap@Registry@Windows@@0V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> Windows::Registry::s_defaultRedirectionMap
0x18003c177  call    ??A?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18003c17c  cmp     qword ptr [rax+18h], 7
0x18003c181  jbe     short loc_18003C186
0x18003c183  mov     rax, [rax]
0x18003c186  lea     r9, [rbp+57h+bstrString]
0x18003c18a  mov     r8, rax
0x18003c18d  mov     rdx, rsi
0x18003c190  mov     rcx, rbx
0x18003c193  mov     rax, r15
0x18003c196  call    _guard_dispatch_icall
0x18003c19b  mov     rcx, [rbp+5Fh]; this
0x18003c19f  test    eax, eax
0x18003c1a1  js      loc_18003C282
0x18003c1a7  lea     rcx, [rbp+57h+S1]; void *
0x18003c1ab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c1b0  cmp     [r12+8], r13
0x18003c1b5  lea     rbx, S2
0x18003c1bc  jz      short loc_18003C1C2
0x18003c1be  mov     rbx, [r12]
0x18003c1c2  lea     rdx, [rbp+57h+bstrString]
0x18003c1c6  lea     rcx, [rbp+57h+S1]
0x18003c1ca  call    ?to_wstring@Strings@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Strings::to_wstring(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &)
0x18003c1cf  nop
0x18003c1d0  inc     rdi
0x18003c1d3  cmp     [rbx+rdi*2], r13w
0x18003c1d8  jnz     short loc_18003C1D0
0x18003c1da  mov     r8, rdi
0x18003c1dd  mov     rdx, rbx
0x18003c1e0  mov     rcx, rax; Src
0x18003c1e3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x18003c1e8  xorps   xmm0, xmm0
0x18003c1eb  movups  xmmword ptr [r14], xmm0
0x18003c1ef  mov     [r14+10h], r13
0x18003c1f3  mov     [r14+18h], r13
0x18003c1f7  movups  xmm0, xmmword ptr [rax]
0x18003c1fa  movups  xmmword ptr [r14], xmm0
0x18003c1fe  movups  xmm1, xmmword ptr [rax+10h]
0x18003c202  movups  xmmword ptr [r14+10h], xmm1
0x18003c207  mov     [rax], r13w
0x18003c20b  mov     [rax+10h], r13
0x18003c20f  mov     qword ptr [rax+18h], 7
0x18003c217  lea     rcx, [rbp+57h+S1]; void *
0x18003c21b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c220  nop
0x18003c221  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18003c225  test    rcx, rcx
0x18003c228  jz      short loc_18003C231
0x18003c22a  call    cs:__imp_SysFreeString
0x18003c230  nop
0x18003c231  mov     rcx, [rbp+57h+var_48]
0x18003c235  test    rcx, rcx
0x18003c238  jz      short loc_18003C247
0x18003c23a  mov     rdx, [rcx]
0x18003c23d  mov     rax, [rdx+10h]
0x18003c241  call    _guard_dispatch_icall
0x18003c246  nop
0x18003c247  mov     rax, r14
0x18003c24a  mov     rcx, [rbp+57h+var_40]
0x18003c24e  xor     rcx, rsp; StackCookie
0x18003c251  call    __security_check_cookie
0x18003c256  mov     rbx, [rsp+0D0h+arg_0]
0x18003c25e  add     rsp, 0A0h
0x18003c265  pop     r15
0x18003c267  pop     r14
0x18003c269  pop     r13
0x18003c26b  pop     r12
0x18003c26d  pop     rdi
0x18003c26e  pop     rsi
0x18003c26f  pop     rbp
0x18003c270  retn
0x18003c271  cmp     r15, rbx
0x18003c274  jb      loc_18003C0E6
0x18003c27a  mov     al, r13b
0x18003c27d  jmp     loc_18003C0E8
0x18003c282  mov     r9d, eax; char *
0x18003c285  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c28c  mov     edx, 0D5h; void *
0x18003c291  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

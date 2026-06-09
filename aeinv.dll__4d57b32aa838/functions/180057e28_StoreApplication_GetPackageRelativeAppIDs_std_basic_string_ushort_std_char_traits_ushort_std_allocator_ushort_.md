# StoreApplication::GetPackageRelativeAppIDs(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x180057e28`
- end: `0x1800580f5`
- name: `?GetPackageRelativeAppIDs@StoreApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fc498`

## callees

- `0x18000a39c`
- `0x180018300`
- `0x180018a60`
- `0x1800404c4`
- `0x180051834`
- `0x1800518f0`
- `0x18005356c`
- `0x180057e28`
- `0x1800580fc`
- `0x180059920`
- `0x1800679f8`
- `0x1801003f4`
- `0x180130010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180057f72`
- `ole32!CoTaskMemFree` at `0x18005809d`
- `ole32!CoTaskMemFree` at `0x180057f72`
- `ole32!CoTaskMemFree` at `0x18005809d`

## string_xrefs

- `0x180057eb4`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180057ed4`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800580b5`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800580ce`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800580e3`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall StoreApplication::GetPackageRelativeAppIDs(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  const char *v7; // r9
  __int64 v8; // rcx
  void (__fastcall *i)(__int64, __int64 *); // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  void *v14; // rcx
  int v16; // eax
  void *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID v24; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v26[3]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v27[32]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v28[40]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v29[64]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+28h]

  v25[1] = -2;
  v25[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(v25);
  StoreApplication::GetStoreAppManifestReaderFromManifestPath(a1, v25);
  v22 = 0;
  v4 = v25[0];
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25[0] + 80LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v22);
  v6 = v5(v4, &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v6,
      v20);
  v8 = v22;
  if ( !v22 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x407,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      v7);
  LODWORD(v20) = 0;
  for ( i = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 32LL);
        ;
        i = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 40LL) )
  {
    i(v8, &v20);
    if ( !(_DWORD)v20 )
      break;
    v21 = 0;
    v10 = v22;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v21);
    v12 = v11(v10, &v21);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x40E,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v12,
        v20);
    pv = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v21 + 24LL))(v21, L"Id", &pv);
    v14 = pv;
    if ( v13 >= 0 )
    {
      if ( pv )
      {
        v24 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v21 + 24LL))(
                v21,
                L"Executable",
                &v24);
        v17 = v24;
        if ( v16 >= 0 )
        {
          if ( v24 )
          {
            std::wstring::wstring(v27, pv);
            std::wstring::wstring(v26, v24);
            v18 = Utility::ToLower((__int64)v28, v26);
            v19 = std::make_pair<std::wstring &,std::wstring>(v29, v27, v18);
            std::vector<std::pair<std::wstring,std::wstring>>::push_back(a2, v19);
            std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v29);
            std::wstring::~wstring(v28);
            std::wstring::~wstring(v26);
            std::wstring::~wstring(v27);
            v17 = v24;
          }
        }
        else if ( v16 != -2147024809 )
        {
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x422,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)(unsigned int)v16,
            v20);
        }
        CoTaskMemFree(v17);
        v14 = pv;
      }
    }
    else if ( v13 != -2147024809 )
    {
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x415,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v13,
        v20);
    }
    CoTaskMemFree(v14);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v21);
    v8 = v22;
  }
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v22);
  return Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(v25);
}

```

## disassembly

```asm
0x180057e28  mov     rax, rsp
0x180057e2b  push    rbp
0x180057e2c  push    rsi
0x180057e2d  push    rdi
0x180057e2e  lea     rbp, [rax-28h]
0x180057e32  sub     rsp, 110h
0x180057e39  mov     qword ptr [rsp+120h+var_D0], 0FFFFFFFFFFFFFFFEh
0x180057e42  mov     [rax+18h], rbx
0x180057e46  mov     rax, cs:__security_cookie
0x180057e4d  xor     rax, rsp
0x180057e50  mov     [rbp+20h+var_20], rax
0x180057e54  mov     rsi, rdx
0x180057e57  mov     rbx, rcx
0x180057e5a  mov     [rsp+120h+var_D8], 0
0x180057e63  lea     rcx, [rsp+120h+var_D8]
0x180057e68  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180057e6d  lea     rdx, [rsp+120h+var_D8]
0x180057e72  mov     rcx, rbx
0x180057e75  call    ?GetStoreAppManifestReaderFromManifestPath@StoreApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIAppxManifestReader@@@Z; StoreApplication::GetStoreAppManifestReaderFromManifestPath(std::wstring const &,IAppxManifestReader * *)
0x180057e7a  mov     [rsp+120h+var_F0], 0
0x180057e83  mov     rdi, [rsp+120h+var_D8]
0x180057e88  mov     rax, [rdi]
0x180057e8b  mov     rbx, [rax+50h]
0x180057e8f  lea     rcx, [rsp+120h+var_F0]
0x180057e94  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180057e99  lea     rdx, [rsp+120h+var_F0]
0x180057e9e  mov     rcx, rdi
0x180057ea1  mov     rax, rbx
0x180057ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ea9  mov     rcx, [rbp+28h]; this
0x180057ead  test    eax, eax
0x180057eaf  jns     short loc_180057EC6
0x180057eb1  mov     r9d, eax; char *
0x180057eb4  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180057ebb  mov     edx, 406h; void *
0x180057ec0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180057ec6  mov     rax, [rbp+28h]
0x180057eca  mov     rcx, [rsp+120h+var_F0]
0x180057ecf  test    rcx, rcx
0x180057ed2  jnz     short loc_180057EE9
0x180057ed4  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180057edb  mov     edx, 407h; void *
0x180057ee0  mov     rcx, rax; this
0x180057ee3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180057ee9  mov     dword ptr [rsp+120h+var_100], 0
0x180057ef1  mov     rax, [rcx]
0x180057ef4  mov     rax, [rax+20h]
0x180057ef8  jmp     loc_180057F8F
0x180057efd  mov     [rsp+120h+var_F8], 0
0x180057f06  mov     rdi, [rsp+120h+var_F0]
0x180057f0b  mov     rax, [rdi]
0x180057f0e  mov     rbx, [rax+18h]
0x180057f12  lea     rcx, [rsp+120h+var_F8]
0x180057f17  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180057f1c  lea     rdx, [rsp+120h+var_F8]
0x180057f21  mov     rcx, rdi
0x180057f24  mov     rax, rbx
0x180057f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f2c  mov     rcx, [rbp+28h]; this
0x180057f30  test    eax, eax
0x180057f32  js      loc_1800580E0
0x180057f38  mov     [rsp+120h+pv], 0
0x180057f41  mov     rcx, [rsp+120h+var_F8]
0x180057f46  mov     rax, [rcx]
0x180057f49  lea     r8, [rsp+120h+pv]
0x180057f4e  lea     rdx, aId; "Id"
0x180057f55  mov     rax, [rax+18h]
0x180057f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f5e  mov     rcx, [rsp+120h+pv]; pv
0x180057f63  test    eax, eax
0x180057f65  jns     short loc_180057FD8
0x180057f67  cmp     eax, 80070057h
0x180057f6c  jnz     loc_1800580AE
0x180057f72  call    cs:__imp_CoTaskMemFree
0x180057f78  nop
0x180057f79  lea     rcx, [rsp+120h+var_F8]
0x180057f7e  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180057f83  mov     rcx, [rsp+120h+var_F0]
0x180057f88  mov     rax, [rcx]
0x180057f8b  mov     rax, [rax+28h]
0x180057f8f  lea     rdx, [rsp+120h+var_100]
0x180057f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f99  cmp     dword ptr [rsp+120h+var_100], 0
0x180057f9e  jnz     loc_180057EFD
0x180057fa4  lea     rcx, [rsp+120h+var_F0]
0x180057fa9  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180057fae  nop
0x180057faf  lea     rcx, [rsp+120h+var_D8]
0x180057fb4  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180057fb9  mov     rcx, [rbp+20h+var_20]
0x180057fbd  xor     rcx, rsp; StackCookie
0x180057fc0  call    __security_check_cookie
0x180057fc5  mov     rbx, [rsp+120h+arg_10]
0x180057fcd  add     rsp, 110h
0x180057fd4  pop     rdi
0x180057fd5  pop     rsi
0x180057fd6  pop     rbp
0x180057fd7  retn
0x180057fd8  test    rcx, rcx
0x180057fdb  jz      short loc_180057F72
0x180057fdd  mov     [rsp+120h+var_E0], 0
0x180057fe6  mov     rcx, [rsp+120h+var_F8]
0x180057feb  mov     rax, [rcx]
0x180057fee  lea     r8, [rsp+120h+var_E0]
0x180057ff3  lea     rdx, aExecutable; "Executable"
0x180057ffa  mov     rax, [rax+18h]
0x180057ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058003  mov     rcx, [rsp+120h+var_E0]
0x180058008  test    eax, eax
0x18005800a  jns     short loc_18005801C
0x18005800c  cmp     eax, 80070057h
0x180058011  jnz     loc_1800580C7
0x180058017  jmp     loc_18005809D
0x18005801c  test    rcx, rcx
0x18005801f  jz      short loc_180058017
0x180058021  mov     rdx, [rsp+120h+pv]
0x180058026  lea     rcx, [rsp+78h]
0x18005802b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180058030  nop
0x180058031  mov     rdx, [rsp+120h+var_E0]
0x180058036  lea     rcx, [rsp+58h]
0x18005803b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180058040  nop
0x180058041  lea     rdx, [rsp+58h]
0x180058046  lea     rcx, [rbp+20h+var_88]
0x18005804a  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18005804f  nop
0x180058050  mov     r8, rax
0x180058053  lea     rdx, [rsp+78h]
0x180058058  lea     rcx, [rbp+20h+var_60]
0x18005805c  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV20@@Z; std::make_pair<std::wstring &,std::wstring>(std::wstring &,std::wstring &&)
0x180058061  nop
0x180058062  mov     rdx, rax
0x180058065  mov     rcx, rsi
0x180058068  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::vector<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x18005806d  nop
0x18005806e  lea     rcx, [rbp+20h+var_60]
0x180058072  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
0x180058077  nop
0x180058078  lea     rcx, [rbp+20h+var_88]
0x18005807c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058081  nop
0x180058082  lea     rcx, [rsp+58h]
0x180058087  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005808c  nop
0x18005808d  lea     rcx, [rsp+78h]
0x180058092  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058097  nop
0x180058098  mov     rcx, [rsp+120h+var_E0]; pv
0x18005809d  call    cs:__imp_CoTaskMemFree
0x1800580a3  nop
0x1800580a4  mov     rcx, [rsp+120h+pv]
0x1800580a9  jmp     loc_180057F72
0x1800580ae  mov     rcx, [rbp+28h]; this
0x1800580b2  mov     r9d, eax; char *
0x1800580b5  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800580bc  mov     edx, 415h; void *
0x1800580c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800580c7  mov     rcx, [rbp+28h]; this
0x1800580cb  mov     r9d, eax; char *
0x1800580ce  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800580d5  mov     edx, 422h; void *
0x1800580da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800580e0  mov     r9d, eax; char *
0x1800580e3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800580ea  mov     edx, 40Eh; void *
0x1800580ef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

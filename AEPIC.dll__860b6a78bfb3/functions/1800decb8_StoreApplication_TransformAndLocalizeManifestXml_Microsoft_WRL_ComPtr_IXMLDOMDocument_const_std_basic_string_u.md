# StoreApplication::TransformAndLocalizeManifestXml(Microsoft::WRL::ComPtr<IXMLDOMDocument> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800decb8`
- end: `0x1800df577`
- name: `?TransformAndLocalizeManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV23@_N@Z`
- size: `2239`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, char)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800dbc34`
- `0x1800dbff4`

## callees

- `0x180005890`
- `0x1800081e8`
- `0x1800088e0`
- `0x18000a2d4`
- `0x18000edf0`
- `0x18000faf0`
- `0x1800108a8`
- `0x18001c5f0`
- `0x1800c97f0`
- `0x1800ca3fc`
- `0x1800d94a8`
- `0x1800d96c4`
- `0x1800decb8`
- `0x1800dfbf8`
- `0x1800dfe24`
- `0x1800e0000`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ded27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dee12`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ded27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800dee12`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df3df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df473`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df3df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800df473`

## string_xrefs

- `0x1800ded38`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dedce`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dee23`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dee80`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800df4a3`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800ded4a`: `<?xml version='1.0' encoding='UTF-8'?>\n<xsl:stylesheet version='1.0' xmlns:xsl='http://www.w3.org/1999/XSL/Transform'>\n<xsl:output method='xml' version='1.0' encoding='UTF-8' indent='yes'/>\n<xsl:template match='*'>\n<xsl:element name='{local-name()}'>\n<xsl:for-each select='@*'>\n<xsl:attribute name='{local-name()}'>\n<xsl:value-of select='.'/>\n</xsl:attribute></xsl:for-each><xsl:apply-templates/></xsl:element></xsl:template></xsl:stylesheet>`
- `0x1800df05b`: `/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/DisplayName`
- `0x1800df129`: `/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/InfoTip`
- `0x1800df0c2`: `/Package/Applications/Application/Extensions/Extension/Protocol/DisplayName`
- `0x1800df2cd`: `/Package/Applications/Application/Extensions/Extension/AutoPlayContent/LaunchAction`
- `0x1800df422`: `<?xml version = "1.0"?>`
- `0x1800df4d8`: `<?xml version = "1.0"?>`
- `0x1800df338`: `/Package/Applications/Application/Extensions/Extension/AutoPlayDevice/LaunchAction`

## pseudocode

```c
__int64 __fastcall StoreApplication::TransformAndLocalizeManifestXml(__int64 a1, __int64 *a2, __int64 a3, char a4)
{
  HRESULT v8; // eax
  LPVOID v9; // rdi
  void (__fastcall *v10)(LPVOID, __int64, __int16 *); // r14
  const unsigned __int16 *v11; // rdx
  _bstr_t *v12; // rax
  __int64 v13; // rdx
  HRESULT v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  char IsEnabled; // al
  LPVOID v18; // rsi
  OLECHAR *v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, BSTR *); // r14
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  int ppv; // [rsp+20h] [rbp-B9h]
  int ppva; // [rsp+20h] [rbp-B9h]
  LPVOID v27; // [rsp+30h] [rbp-A9h] BYREF
  __int16 v28; // [rsp+38h] [rbp-A1h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-99h] BYREF
  LPVOID v30; // [rsp+48h] [rbp-91h] BYREF
  _BYTE v31[8]; // [rsp+50h] [rbp-89h] BYREF
  int v32; // [rsp+58h] [rbp-81h]
  __int64 v33; // [rsp+60h] [rbp-79h]
  int v34[4]; // [rsp+70h] [rbp-69h] BYREF
  __int64 v35; // [rsp+80h] [rbp-59h]
  _BYTE v36[16]; // [rsp+90h] [rbp-49h] BYREF
  unsigned __int64 v37; // [rsp+A0h] [rbp-39h]
  _BYTE v38[32]; // [rsp+B0h] [rbp-29h] BYREF
  unsigned __int16 *v39[4]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v33 = a1;
  v32 = 0;
  v30 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v8 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
         &v30);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6DB,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  std::wstring::wstring(
    v39,
    L"<?xml version='1.0' encoding='UTF-8'?>\n"
     "<xsl:stylesheet version='1.0' xmlns:xsl='http://www.w3.org/1999/XSL/Transform'>\n"
     "<xsl:output method='xml' version='1.0' encoding='UTF-8' indent='yes'/>\n"
     "<xsl:template match='*'>\n"
     "<xsl:element name='{local-name()}'>\n"
     "<xsl:for-each select='@*'>\n"
     "<xsl:attribute name='{local-name()}'>\n"
     "<xsl:value-of select='.'/>\n"
     "</xsl:attribute></xsl:for-each><xsl:apply-templates/></xsl:element></xsl:template></xsl:stylesheet>");
  v28 = 0;
  v9 = v30;
  v10 = *(void (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)v30 + 520LL);
  v11 = (const unsigned __int16 *)v39;
  if ( v39[3] > (unsigned __int16 *)7 )
    v11 = v39[0];
  v12 = _bstr_t::_bstr_t((_bstr_t *)v31, v11);
  if ( *(_QWORD *)v12 )
    v13 = **(_QWORD **)v12;
  else
    v13 = 0;
  v10(v9, v13, &v28);
  _bstr_t::_Free((_bstr_t *)v31);
  if ( v28 != -1 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F1,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)0xC00CE225LL,
      ppv);
  v27 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v14 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
          &v27);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F5,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v14,
      ppva);
  *(_QWORD *)v34 = 13;
  *(_QWORD *)&v34[2] = v27;
  v15 = *a2;
  v35 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, LPVOID, int *))(*(_QWORD *)v15 + 336LL))(v15, v30, v34);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6FB,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v16,
      ppva);
  if ( a4 )
  {
    std::wstring::wstring(v38, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(v34, L"/Package/Properties/DisplayName");
    StoreApplication::TranslateResourceIds(&v27, a3, v34, v36, v38);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(v38, L"/Package/Applications/Application/VisualElements");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(v38, L"/Package/Properties/PublisherDisplayName");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(v38, L"/Package/Properties/Description");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(
      v38,
      L"/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/DisplayName");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(v38, L"/Package/Applications/Application/Extensions/Extension/Protocol/DisplayName");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, &pszFormat);
    std::wstring::wstring(v38, L"/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/InfoTip");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, L"DisplayName");
    std::wstring::wstring(v38, L"/Package/Applications/Application/VisualElements");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, L"Description");
    std::wstring::wstring(v38, L"/Package/Applications/Application/VisualElements");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, L"ShortName");
    std::wstring::wstring(v38, L"/Package/Applications/Application/VisualElements/DefaultTile");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, L"ActionDisplayName");
    std::wstring::wstring(v38, L"/Package/Applications/Application/Extensions/Extension/AutoPlayContent/LaunchAction");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::wstring(v34, &pszFormat);
    std::wstring::wstring(v36, L"ActionDisplayName");
    std::wstring::wstring(v38, L"/Package/Applications/Application/Extensions/Extension/AutoPlayDevice/LaunchAction");
    StoreApplication::TranslateResourceIds(&v27, a3, v38, v36, v34);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v34);
  }
  bstrString = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v32 = 1;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_TransformAppxManifest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_TransformAppxManifest>::GetImpl'::`2'::impl);
  v18 = v27;
  v19 = bstrString;
  v20 = *(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v27 + 272LL);
  if ( IsEnabled )
  {
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v31);
      SysFreeString(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v31);
    }
    bstrString = 0;
    v22 = v20(v18, &bstrString);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x747,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v22,
        ppva);
    if ( bstrString )
    {
      v23 = -1;
      do
        ++v23;
      while ( bstrString[v23] );
      std::wstring::_Assign<unsigned short>(a1, bstrString);
    }
    std::wstring::wstring(v36, L"<?xml version = \"1.0\"?>");
    if ( *(_QWORD *)(a1 + 16) > v37 )
    {
      std::wstring::wstring(v38, a1, v37, -1);
      std::wstring::operator=(a1, v38);
      std::wstring::_Tidy_deallocate(v38);
    }
  }
  else
  {
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v31);
      SysFreeString(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v31);
    }
    bstrString = 0;
    v20(v18, &bstrString);
    v21 = -1;
    do
      ++v21;
    while ( bstrString[v21] );
    std::wstring::_Assign<unsigned short>(a1, bstrString);
    std::wstring::wstring(v36, L"<?xml version = \"1.0\"?>");
    std::wstring::wstring(v38, a1, v37, -1);
    std::wstring::operator=(a1, v38);
    std::wstring::_Tidy_deallocate(v38);
  }
  std::wstring::_Tidy_deallocate(v36);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  std::wstring::_Tidy_deallocate(v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return a1;
}

```

## disassembly

```asm
0x1800decb8  mov     [rsp-8+arg_18], rbx
0x1800decbd  push    rbp
0x1800decbe  push    rsi
0x1800decbf  push    rdi
0x1800decc0  push    r12
0x1800decc2  push    r13
0x1800decc4  push    r14
0x1800decc6  push    r15
0x1800decc8  lea     rbp, [rsp-27h]
0x1800deccd  sub     rsp, 100h
0x1800decd4  mov     rax, cs:__security_cookie
0x1800decdb  xor     rax, rsp
0x1800decde  mov     [rbp+57h+var_40], rax
0x1800dece2  mov     sil, r9b
0x1800dece5  mov     r12, r8
0x1800dece8  mov     r15, rdx
0x1800deceb  mov     rbx, rcx
0x1800decee  mov     [rbp+57h+var_D0], rcx
0x1800decf2  xor     r13d, r13d
0x1800decf5  mov     [rsp+130h+var_D8], r13d
0x1800decfa  mov     [rsp+130h+var_E8], r13
0x1800decff  lea     rcx, [rsp+130h+var_E8]
0x1800ded04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ded09  lea     rax, [rsp+130h+var_E8]
0x1800ded0e  mov     qword ptr [rsp+130h+ppv], rax; int
0x1800ded13  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800ded1a  xor     edx, edx; pUnkOuter
0x1800ded1c  lea     r8d, [r13+1]; dwClsContext
0x1800ded20  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800ded27  call    cs:__imp_CoCreateInstance
0x1800ded2d  mov     rcx, [rbp+5Fh]; this
0x1800ded31  test    eax, eax
0x1800ded33  jns     short loc_1800DED4A
0x1800ded35  mov     r9d, eax; char *
0x1800ded38  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800ded3f  mov     edx, 6DBh; void *
0x1800ded44  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ded4a  lea     rdx, aXmlVersion10En; "<?xml version='1.0' encoding='UTF-8'?>"...
0x1800ded51  lea     rcx, [rbp+57h+var_60]
0x1800ded55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ded5a  nop
0x1800ded5b  mov     [rsp+130h+var_F8], r13w
0x1800ded61  mov     rdi, [rsp+130h+var_E8]
0x1800ded66  mov     rax, [rdi]
0x1800ded69  mov     r14, [rax+208h]
0x1800ded70  lea     rdx, [rbp+57h+var_60]
0x1800ded74  cmp     [rbp+57h+var_48], 7
0x1800ded79  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800ded7e  lea     rcx, [rsp+130h+var_E0]; this
0x1800ded83  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800ded88  nop
0x1800ded89  mov     rdx, [rax]
0x1800ded8c  test    rdx, rdx
0x1800ded8f  jz      short loc_1800DED96
0x1800ded91  mov     rdx, [rdx]
0x1800ded94  jmp     short loc_1800DED99
0x1800ded96  mov     rdx, r13
0x1800ded99  lea     r8, [rsp+130h+var_F8]
0x1800ded9e  mov     rcx, rdi
0x1800deda1  mov     rax, r14
0x1800deda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deda9  nop
0x1800dedaa  lea     rcx, [rsp+130h+var_E0]; this
0x1800dedaf  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800dedb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dedb8  cmp     [rsp+130h+var_F8], ax
0x1800dedbd  setz    al
0x1800dedc0  mov     rcx, [rbp+5Fh]; this
0x1800dedc4  test    al, al
0x1800dedc6  jnz     short loc_1800DEDE0
0x1800dedc8  mov     r9d, 0C00CE225h; char *
0x1800dedce  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dedd5  mov     edx, 6F1h; void *
0x1800dedda  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dede0  mov     [rsp+130h+var_100], r13
0x1800dede5  lea     rcx, [rsp+130h+var_100]
0x1800dedea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dedef  lea     rax, [rsp+130h+var_100]
0x1800dedf4  mov     qword ptr [rsp+130h+ppv], rax; int
0x1800dedf9  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800dee00  mov     r14d, 1
0x1800dee06  mov     r8d, r14d; dwClsContext
0x1800dee09  xor     edx, edx; pUnkOuter
0x1800dee0b  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800dee12  call    cs:__imp_CoCreateInstance
0x1800dee18  mov     rcx, [rbp+5Fh]; this
0x1800dee1c  test    eax, eax
0x1800dee1e  jns     short loc_1800DEE35
0x1800dee20  mov     r9d, eax; char *
0x1800dee23  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dee2a  mov     edx, 6F5h; void *
0x1800dee2f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dee35  xorps   xmm0, xmm0
0x1800dee38  xor     edx, edx
0x1800dee3a  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800dee3e  lea     eax, [rdx+0Dh]
0x1800dee41  mov     word ptr [rbp+57h+var_C0], ax
0x1800dee45  mov     rax, [rsp+130h+var_100]
0x1800dee4a  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1800dee4e  mov     rcx, [r15]
0x1800dee51  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x1800dee55  movaps  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800dee59  mov     [rbp+57h+var_B0], rdx
0x1800dee5d  mov     rax, [rcx]
0x1800dee60  lea     r8, [rbp+57h+var_C0]
0x1800dee64  mov     rdx, [rsp+130h+var_E8]
0x1800dee69  mov     rax, [rax+150h]
0x1800dee70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee75  mov     rcx, [rbp+5Fh]; this
0x1800dee79  test    eax, eax
0x1800dee7b  jns     short loc_1800DEE92
0x1800dee7d  mov     r9d, eax; char *
0x1800dee80  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dee87  mov     edx, 6FBh; void *
0x1800dee8c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dee92  test    sil, sil
0x1800dee95  jz      loc_1800DF385
0x1800dee9b  lea     rsi, pszFormat
0x1800deea2  mov     rdx, rsi
0x1800deea5  lea     rcx, [rbp+57h+var_80]
0x1800deea9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800deeae  nop
0x1800deeaf  mov     rdx, rsi
0x1800deeb2  lea     rcx, [rbp+57h+var_A0]
0x1800deeb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800deebb  nop
0x1800deebc  lea     rdx, aPackagePropert_0; "/Package/Properties/DisplayName"
0x1800deec3  lea     rcx, [rbp+57h+var_C0]
0x1800deec7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800deecc  nop
0x1800deecd  lea     rax, [rbp+57h+var_80]
0x1800deed1  mov     qword ptr [rsp+130h+ppv], rax
0x1800deed6  lea     r9, [rbp+57h+var_A0]
0x1800deeda  lea     r8, [rbp+57h+var_C0]
0x1800deede  mov     rdx, r12
0x1800deee1  lea     rcx, [rsp+130h+var_100]
0x1800deee6  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800deeeb  nop
0x1800deeec  lea     rcx, [rbp+57h+var_C0]
0x1800deef0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800deef5  nop
0x1800deef6  lea     rcx, [rbp+57h+var_A0]
0x1800deefa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800deeff  nop
0x1800def00  lea     rcx, [rbp+57h+var_80]
0x1800def04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800def09  mov     rdx, rsi
0x1800def0c  lea     rcx, [rbp+57h+var_C0]
0x1800def10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800def15  nop
0x1800def16  mov     rdx, rsi
0x1800def19  lea     rcx, [rbp+57h+var_A0]
0x1800def1d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800def22  nop
0x1800def23  lea     rdi, aPackageApplica_5; "/Package/Applications/Application/Visua"...
0x1800def2a  mov     rdx, rdi
0x1800def2d  lea     rcx, [rbp+57h+var_80]
0x1800def31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800def36  nop
0x1800def37  lea     rax, [rbp+57h+var_C0]
0x1800def3b  mov     qword ptr [rsp+130h+ppv], rax
0x1800def40  lea     r9, [rbp+57h+var_A0]
0x1800def44  lea     r8, [rbp+57h+var_80]
0x1800def48  mov     rdx, r12
0x1800def4b  lea     rcx, [rsp+130h+var_100]
0x1800def50  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800def55  nop
0x1800def56  lea     rcx, [rbp+57h+var_80]
0x1800def5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800def5f  nop
0x1800def60  lea     rcx, [rbp+57h+var_A0]
0x1800def64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800def69  nop
0x1800def6a  lea     rcx, [rbp+57h+var_C0]
0x1800def6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800def73  mov     rdx, rsi
0x1800def76  lea     rcx, [rbp+57h+var_C0]
0x1800def7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800def7f  nop
0x1800def80  mov     rdx, rsi
0x1800def83  lea     rcx, [rbp+57h+var_A0]
0x1800def87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800def8c  nop
0x1800def8d  lea     rdx, aPackagePropert_1; "/Package/Properties/PublisherDisplayNam"...
0x1800def94  lea     rcx, [rbp+57h+var_80]
0x1800def98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800def9d  nop
0x1800def9e  lea     rax, [rbp+57h+var_C0]
0x1800defa2  mov     qword ptr [rsp+130h+ppv], rax
0x1800defa7  lea     r9, [rbp+57h+var_A0]
0x1800defab  lea     r8, [rbp+57h+var_80]
0x1800defaf  mov     rdx, r12
0x1800defb2  lea     rcx, [rsp+130h+var_100]
0x1800defb7  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800defbc  nop
0x1800defbd  lea     rcx, [rbp+57h+var_80]
0x1800defc1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800defc6  nop
0x1800defc7  lea     rcx, [rbp+57h+var_A0]
0x1800defcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800defd0  nop
0x1800defd1  lea     rcx, [rbp+57h+var_C0]
0x1800defd5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800defda  mov     rdx, rsi
0x1800defdd  lea     rcx, [rbp+57h+var_C0]
0x1800defe1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800defe6  nop
0x1800defe7  mov     rdx, rsi
0x1800defea  lea     rcx, [rbp+57h+var_A0]
0x1800defee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800deff3  nop
0x1800deff4  lea     rdx, aPackagePropert; "/Package/Properties/Description"
0x1800deffb  lea     rcx, [rbp+57h+var_80]
0x1800defff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df004  nop
0x1800df005  lea     rax, [rbp+57h+var_C0]
0x1800df009  mov     qword ptr [rsp+130h+ppv], rax
0x1800df00e  lea     r9, [rbp+57h+var_A0]
0x1800df012  lea     r8, [rbp+57h+var_80]
0x1800df016  mov     rdx, r12
0x1800df019  lea     rcx, [rsp+130h+var_100]
0x1800df01e  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800df023  nop
0x1800df024  lea     rcx, [rbp+57h+var_80]
0x1800df028  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df02d  nop
0x1800df02e  lea     rcx, [rbp+57h+var_A0]
0x1800df032  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df037  nop
0x1800df038  lea     rcx, [rbp+57h+var_C0]
0x1800df03c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df041  mov     rdx, rsi
0x1800df044  lea     rcx, [rbp+57h+var_C0]
0x1800df048  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df04d  nop
0x1800df04e  mov     rdx, rsi
0x1800df051  lea     rcx, [rbp+57h+var_A0]
0x1800df055  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df05a  nop
0x1800df05b  lea     rdx, aPackageApplica_0; "/Package/Applications/Application/Exten"...
0x1800df062  lea     rcx, [rbp+57h+var_80]
0x1800df066  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df06b  nop
0x1800df06c  lea     rax, [rbp+57h+var_C0]
0x1800df070  mov     qword ptr [rsp+130h+ppv], rax
0x1800df075  lea     r9, [rbp+57h+var_A0]
0x1800df079  lea     r8, [rbp+57h+var_80]
0x1800df07d  mov     rdx, r12
0x1800df080  lea     rcx, [rsp+130h+var_100]
0x1800df085  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800df08a  nop
0x1800df08b  lea     rcx, [rbp+57h+var_80]
0x1800df08f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df094  nop
0x1800df095  lea     rcx, [rbp+57h+var_A0]
0x1800df099  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df09e  nop
0x1800df09f  lea     rcx, [rbp+57h+var_C0]
0x1800df0a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df0a8  mov     rdx, rsi
0x1800df0ab  lea     rcx, [rbp+57h+var_C0]
0x1800df0af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df0b4  nop
0x1800df0b5  mov     rdx, rsi
0x1800df0b8  lea     rcx, [rbp+57h+var_A0]
0x1800df0bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df0c1  nop
0x1800df0c2  lea     rdx, aPackageApplica_1; "/Package/Applications/Application/Exten"...
0x1800df0c9  lea     rcx, [rbp+57h+var_80]
0x1800df0cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df0d2  nop
0x1800df0d3  lea     rax, [rbp+57h+var_C0]
0x1800df0d7  mov     qword ptr [rsp+130h+ppv], rax
0x1800df0dc  lea     r9, [rbp+57h+var_A0]
0x1800df0e0  lea     r8, [rbp+57h+var_80]
0x1800df0e4  mov     rdx, r12
0x1800df0e7  lea     rcx, [rsp+130h+var_100]
0x1800df0ec  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800df0f1  nop
0x1800df0f2  lea     rcx, [rbp+57h+var_80]
0x1800df0f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df0fb  nop
0x1800df0fc  lea     rcx, [rbp+57h+var_A0]
0x1800df100  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df105  nop
0x1800df106  lea     rcx, [rbp+57h+var_C0]
0x1800df10a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800df10f  mov     rdx, rsi
0x1800df112  lea     rcx, [rbp+57h+var_C0]
0x1800df116  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df11b  nop
0x1800df11c  mov     rdx, rsi
0x1800df11f  lea     rcx, [rbp+57h+var_A0]
0x1800df123  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df128  nop
0x1800df129  lea     rdx, aPackageApplica_4; "/Package/Applications/Application/Exten"...
0x1800df130  lea     rcx, [rbp+57h+var_80]
0x1800df134  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800df139  nop
0x1800df13a  lea     rax, [rbp+57h+var_C0]
  ... truncated ...
```

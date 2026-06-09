# StoreApplication::TransformAndLocalizeManifestXml(Microsoft::WRL::ComPtr<IXMLDOMDocument> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180025340`
- end: `0x180025c54`
- name: `?TransformAndLocalizeManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV23@_N@Z`
- size: `2324`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, char)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019810`
- `0x180054154`

## callees

- `0x18000a39c`
- `0x1800150ac`
- `0x18001632c`
- `0x180017250`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x180025340`
- `0x180025c5c`
- `0x1800404c4`
- `0x180040500`
- `0x180045480`
- `0x1800470e8`
- `0x18004826c`
- `0x1800487ac`
- `0x180059920`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180025a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b28`
- `OLEAUT32!__imp_SysFreeString` at `0x180025be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b28`
- `OLEAUT32!__imp_SysFreeString` at `0x180025be0`
- `ole32!CoCreateInstance` at `0x1800253b8`
- `ole32!CoCreateInstance` at `0x1800254bd`
- `ole32!CoCreateInstance` at `0x1800253b8`
- `ole32!CoCreateInstance` at `0x1800254bd`

## string_xrefs

- `0x1800253f0`: `<?xml version='1.0' encoding='UTF-8'?>\n<xsl:stylesheet version='1.0' xmlns:xsl='http://www.w3.org/1999/XSL/Transform'>\n<xsl:output method='xml' version='1.0' encoding='UTF-8' indent='yes'/>\n<xsl:template match='*'>\n<xsl:element name='{local-name()}'>\n<xsl:for-each select='@*'>\n<xsl:attribute name='{local-name()}'>\n<xsl:value-of select='.'/>\n</xsl:attribute></xsl:for-each><xsl:apply-templates/></xsl:element></xsl:template></xsl:stylesheet>`
- `0x180025ad4`: `<?xml version = "1.0"?>`
- `0x180025b8d`: `<?xml version = "1.0"?>`
- `0x1800253c9`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180025479`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800254ce`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18002552b`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180025b58`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18002576d`: `/Package/Applications/Application/Extensions/Extension/Protocol/DisplayName`
- `0x180025706`: `/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/DisplayName`
- `0x1800257d4`: `/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/InfoTip`
- `0x1800259e3`: `/Package/Applications/Application/Extensions/Extension/AutoPlayDevice/LaunchAction`
- `0x180025978`: `/Package/Applications/Application/Extensions/Extension/AutoPlayContent/LaunchAction`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall StoreApplication::TransformAndLocalizeManifestXml(__int64 a1, __int64 *a2, __int64 a3, char a4)
{
  HRESULT v8; // eax
  LPVOID v9; // rdi
  void (__fastcall *v10)(LPVOID, __int64, __int64 *); // r14
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
  __int64 v22; // rax
  int *v23; // rcx
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rax
  LPVOID v27; // rcx
  _QWORD *v28; // rcx
  int v30; // [rsp+28h] [rbp-B9h]
  int v31; // [rsp+28h] [rbp-B9h]
  LPVOID v32; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v33; // [rsp+40h] [rbp-A1h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-99h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-91h] BYREF
  _bstr_t::Data_t *v36; // [rsp+58h] [rbp-89h] BYREF
  int v37; // [rsp+60h] [rbp-81h]
  __int64 v38; // [rsp+68h] [rbp-79h]
  __int64 v39; // [rsp+70h] [rbp-71h]
  int v40[4]; // [rsp+78h] [rbp-69h] BYREF
  __int128 v41; // [rsp+88h] [rbp-59h]
  _BYTE v42[16]; // [rsp+98h] [rbp-49h] BYREF
  unsigned __int64 v43; // [rsp+A8h] [rbp-39h]
  _BYTE v44[32]; // [rsp+B8h] [rbp-29h] BYREF
  unsigned __int16 *v45[2]; // [rsp+D8h] [rbp-9h] BYREF
  __int128 v46; // [rsp+E8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]

  v38 = -2;
  v39 = a1;
  v37 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
  v8 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6DB,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v30);
  *(_OWORD *)v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v45);
  LOWORD(v33) = 0;
  v9 = ppv;
  v10 = *(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 520LL);
  v11 = (const unsigned __int16 *)v45;
  if ( *((_QWORD *)&v46 + 1) > 7u )
    v11 = v45[0];
  v12 = _bstr_t::_bstr_t((_bstr_t *)&v36, v11);
  if ( *(_QWORD *)v12 )
    v13 = **(_QWORD **)v12;
  else
    v13 = 0;
  v10(v9, v13, &v33);
  if ( v36 )
    _bstr_t::Data_t::Release(v36);
  if ( (_WORD)v33 != 0xFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F1,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)0xC00CE225LL,
      v30);
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v32);
  v14 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
          &v32);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6F5,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v14,
      v31);
  *(_QWORD *)v40 = 13;
  *(_QWORD *)&v40[2] = v32;
  v15 = *a2;
  *(_QWORD *)&v41 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, LPVOID, int *))(*(_QWORD *)v15 + 336LL))(v15, ppv, v40);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6FB,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v16,
      v31);
  if ( a4 )
  {
    std::wstring::wstring(v42, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(v40, L"/Package/Properties/DisplayName");
    StoreApplication::TranslateResourceIds(&v32, a3, v40, v44, v42);
    std::wstring::~wstring(v40);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v42);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(v42, L"/Package/Applications/Application/VisualElements");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(v42, L"/Package/Properties/PublisherDisplayName");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(v42, L"/Package/Properties/Description");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(
      v42,
      L"/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/DisplayName");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(v42, L"/Package/Applications/Application/Extensions/Extension/Protocol/DisplayName");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, &byte_1801389F0);
    std::wstring::wstring(v42, L"/Package/Applications/Application/Extensions/Extension/FileTypeAssociation/InfoTip");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, L"DisplayName");
    std::wstring::wstring(v42, L"/Package/Applications/Application/VisualElements");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, L"Description");
    std::wstring::wstring(v42, L"/Package/Applications/Application/VisualElements");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, L"ShortName");
    std::wstring::wstring(v42, L"/Package/Applications/Application/VisualElements/DefaultTile");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, L"ActionDisplayName");
    std::wstring::wstring(v42, L"/Package/Applications/Application/Extensions/Extension/AutoPlayContent/LaunchAction");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
    std::wstring::wstring(v40, &byte_1801389F0);
    std::wstring::wstring(v44, L"ActionDisplayName");
    std::wstring::wstring(v42, L"/Package/Applications/Application/Extensions/Extension/AutoPlayDevice/LaunchAction");
    StoreApplication::TranslateResourceIds(&v32, a3, v42, v44, v40);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v40);
  }
  bstrString = 0;
  std::wstring::wstring(a1);
  v37 = 1;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_TransformAppxManifest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_TransformAppxManifest>::GetImpl'::`2'::impl);
  v18 = v32;
  v19 = bstrString;
  v20 = *(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v32 + 272LL);
  if ( IsEnabled )
  {
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v36);
      SysFreeString(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v36);
    }
    bstrString = 0;
    v24 = v20(v18, &bstrString);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x747,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v24,
        v31);
    if ( bstrString )
    {
      v25 = -1;
      do
        ++v25;
      while ( bstrString[v25] );
      std::wstring::_Assign<unsigned short>(a1, bstrString);
    }
    std::wstring::wstring(v42, L"<?xml version = \"1.0\"?>");
    if ( *(_QWORD *)(a1 + 16) > v43 )
    {
      v26 = std::wstring::substr(a1, v44, v43, -1);
      std::wstring::operator=(a1, v26);
      std::wstring::~wstring(v44);
    }
    v23 = (int *)v42;
  }
  else
  {
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v36);
      SysFreeString(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v36);
    }
    bstrString = 0;
    v20(v18, &bstrString);
    v21 = -1;
    do
      ++v21;
    while ( bstrString[v21] );
    std::wstring::_Assign<unsigned short>(a1, bstrString);
    *(_OWORD *)v40 = 0;
    v41 = 0;
    std::wstring::_Construct<1,unsigned short const *>(v40);
    v22 = std::wstring::substr(a1, v42, v41, -1);
    std::wstring::operator=(a1, v22);
    std::wstring::~wstring(v42);
    v23 = v40;
  }
  std::wstring::~wstring(v23);
  if ( bstrString )
    SysFreeString(bstrString);
  v27 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  }
  std::wstring::~wstring(v45);
  v28 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
  }
  return a1;
}

```

## disassembly

```asm
0x180025340  mov     rax, rsp
0x180025343  push    rbp
0x180025344  push    rsi
0x180025345  push    rdi
0x180025346  push    r12
0x180025348  push    r13
0x18002534a  push    r14
0x18002534c  push    r15
0x18002534e  lea     rbp, [rax-5Fh]
0x180025352  sub     rsp, 100h
0x180025359  mov     [rbp+57h+var_D0], 0FFFFFFFFFFFFFFFEh
0x180025361  mov     [rax+20h], rbx
0x180025365  mov     rax, cs:__security_cookie
0x18002536c  xor     rax, rsp
0x18002536f  mov     [rbp+57h+var_40], rax
0x180025373  mov     sil, r9b
0x180025376  mov     r12, r8
0x180025379  mov     r15, rdx
0x18002537c  mov     rbx, rcx
0x18002537f  mov     [rbp+57h+var_C8], rcx
0x180025383  xor     r13d, r13d
0x180025386  mov     [rsp+130h+var_D8], r13d
0x18002538b  mov     [rsp+130h+ppv], r13
0x180025390  lea     rcx, [rsp+130h+ppv]
0x180025395  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18002539a  lea     rax, [rsp+130h+ppv]
0x18002539f  mov     [rsp+20h], rax; int
0x1800253a4  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800253ab  xor     edx, edx; pUnkOuter
0x1800253ad  lea     r8d, [r13+1]; dwClsContext
0x1800253b1  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800253b8  call    cs:__imp_CoCreateInstance
0x1800253be  mov     rcx, [rbp+5Fh]; this
0x1800253c2  test    eax, eax
0x1800253c4  jns     short loc_1800253DB
0x1800253c6  mov     r9d, eax; char *
0x1800253c9  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800253d0  mov     edx, 6DBh; void *
0x1800253d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800253db  xorps   xmm0, xmm0
0x1800253de  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800253e2  xorps   xmm1, xmm1
0x1800253e5  movdqu  [rbp+57h+var_50], xmm1
0x1800253ea  mov     r8d, 1BAh
0x1800253f0  lea     rdx, aXmlVersion10En; "<?xml version='1.0' encoding='UTF-8'?>"...
0x1800253f7  lea     rcx, [rbp+57h+var_60]
0x1800253fb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180025400  nop
0x180025401  mov     word ptr [rsp+130h+var_F8], r13w
0x180025407  mov     rdi, [rsp+130h+ppv]
0x18002540c  mov     rax, [rdi]
0x18002540f  mov     r14, [rax+208h]
0x180025416  lea     rdx, [rbp+57h+var_60]
0x18002541a  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18002541f  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180025424  lea     rcx, [rsp+130h+var_E0]; this
0x180025429  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002542e  nop
0x18002542f  mov     rdx, [rax]
0x180025432  test    rdx, rdx
0x180025435  jz      short loc_18002543C
0x180025437  mov     rdx, [rdx]
0x18002543a  jmp     short loc_18002543F
0x18002543c  mov     rdx, r13
0x18002543f  lea     r8, [rsp+130h+var_F8]
0x180025444  mov     rcx, rdi
0x180025447  mov     rax, r14
0x18002544a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002544f  nop
0x180025450  mov     rcx, [rsp+130h+var_E0]; this
0x180025455  test    rcx, rcx
0x180025458  jz      short loc_18002545F
0x18002545a  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18002545f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025463  cmp     word ptr [rsp+130h+var_F8], ax
0x180025468  setz    al
0x18002546b  mov     rcx, [rbp+5Fh]; this
0x18002546f  test    al, al
0x180025471  jnz     short loc_18002548B
0x180025473  mov     r9d, 0C00CE225h; char *
0x180025479  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180025480  mov     edx, 6F1h; void *
0x180025485  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002548b  mov     [rsp+130h+var_100], r13
0x180025490  lea     rcx, [rsp+130h+var_100]
0x180025495  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18002549a  lea     rax, [rsp+130h+var_100]
0x18002549f  mov     [rsp+20h], rax; int
0x1800254a4  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800254ab  mov     r14d, 1
0x1800254b1  mov     r8d, r14d; dwClsContext
0x1800254b4  xor     edx, edx; pUnkOuter
0x1800254b6  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800254bd  call    cs:__imp_CoCreateInstance
0x1800254c3  mov     rcx, [rbp+5Fh]; this
0x1800254c7  test    eax, eax
0x1800254c9  jns     short loc_1800254E0
0x1800254cb  mov     r9d, eax; char *
0x1800254ce  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800254d5  mov     edx, 6F5h; void *
0x1800254da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800254e0  xorps   xmm0, xmm0
0x1800254e3  xor     edx, edx
0x1800254e5  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800254e9  lea     eax, [rdx+0Dh]
0x1800254ec  mov     word ptr [rbp+57h+var_C0], ax
0x1800254f0  mov     rax, [rsp+130h+var_100]
0x1800254f5  mov     qword ptr [rbp+57h+var_C0+8], rax
0x1800254f9  mov     rcx, [r15]
0x1800254fc  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x180025500  movaps  xmmword ptr [rbp+57h+var_C0], xmm0
0x180025504  mov     qword ptr [rbp+57h+var_B0], rdx
0x180025508  mov     rax, [rcx]
0x18002550b  lea     r8, [rbp+57h+var_C0]
0x18002550f  mov     rdx, [rsp+130h+ppv]
0x180025514  mov     rax, [rax+150h]
0x18002551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025520  mov     rcx, [rbp+5Fh]; this
0x180025524  test    eax, eax
0x180025526  jns     short loc_18002553D
0x180025528  mov     r9d, eax; char *
0x18002552b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180025532  mov     edx, 6FBh; void *
0x180025537  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002553d  test    sil, sil
0x180025540  jz      loc_180025A30
0x180025546  lea     rsi, byte_1801389F0
0x18002554d  mov     rdx, rsi
0x180025550  lea     rcx, [rbp+57h+var_A0]
0x180025554  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025559  nop
0x18002555a  mov     rdx, rsi
0x18002555d  lea     rcx, [rbp+57h+var_80]
0x180025561  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025566  nop
0x180025567  lea     rdx, aPackagePropert_0; "/Package/Properties/DisplayName"
0x18002556e  lea     rcx, [rbp+57h+var_C0]
0x180025572  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025577  nop
0x180025578  lea     rax, [rbp+57h+var_A0]
0x18002557c  mov     [rsp+20h], rax
0x180025581  lea     r9, [rbp+57h+var_80]
0x180025585  lea     r8, [rbp+57h+var_C0]
0x180025589  mov     rdx, r12
0x18002558c  lea     rcx, [rsp+130h+var_100]
0x180025591  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180025596  nop
0x180025597  lea     rcx, [rbp+57h+var_C0]
0x18002559b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800255a0  nop
0x1800255a1  lea     rcx, [rbp+57h+var_80]
0x1800255a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800255aa  nop
0x1800255ab  lea     rcx, [rbp+57h+var_A0]
0x1800255af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800255b4  mov     rdx, rsi
0x1800255b7  lea     rcx, [rbp+57h+var_C0]
0x1800255bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800255c0  nop
0x1800255c1  mov     rdx, rsi
0x1800255c4  lea     rcx, [rbp+57h+var_80]
0x1800255c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800255cd  nop
0x1800255ce  lea     rdi, aPackageApplica_5; "/Package/Applications/Application/Visua"...
0x1800255d5  mov     rdx, rdi
0x1800255d8  lea     rcx, [rbp+57h+var_A0]
0x1800255dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800255e1  nop
0x1800255e2  lea     rax, [rbp+57h+var_C0]
0x1800255e6  mov     [rsp+20h], rax
0x1800255eb  lea     r9, [rbp+57h+var_80]
0x1800255ef  lea     r8, [rbp+57h+var_A0]
0x1800255f3  mov     rdx, r12
0x1800255f6  lea     rcx, [rsp+130h+var_100]
0x1800255fb  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180025600  nop
0x180025601  lea     rcx, [rbp+57h+var_A0]
0x180025605  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002560a  nop
0x18002560b  lea     rcx, [rbp+57h+var_80]
0x18002560f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025614  nop
0x180025615  lea     rcx, [rbp+57h+var_C0]
0x180025619  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002561e  mov     rdx, rsi
0x180025621  lea     rcx, [rbp+57h+var_C0]
0x180025625  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002562a  nop
0x18002562b  mov     rdx, rsi
0x18002562e  lea     rcx, [rbp+57h+var_80]
0x180025632  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025637  nop
0x180025638  lea     rdx, aPackagePropert_1; "/Package/Properties/PublisherDisplayNam"...
0x18002563f  lea     rcx, [rbp+57h+var_A0]
0x180025643  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025648  nop
0x180025649  lea     rax, [rbp+57h+var_C0]
0x18002564d  mov     [rsp+20h], rax
0x180025652  lea     r9, [rbp+57h+var_80]
0x180025656  lea     r8, [rbp+57h+var_A0]
0x18002565a  mov     rdx, r12
0x18002565d  lea     rcx, [rsp+130h+var_100]
0x180025662  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180025667  nop
0x180025668  lea     rcx, [rbp+57h+var_A0]
0x18002566c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025671  nop
0x180025672  lea     rcx, [rbp+57h+var_80]
0x180025676  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002567b  nop
0x18002567c  lea     rcx, [rbp+57h+var_C0]
0x180025680  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025685  mov     rdx, rsi
0x180025688  lea     rcx, [rbp+57h+var_C0]
0x18002568c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025691  nop
0x180025692  mov     rdx, rsi
0x180025695  lea     rcx, [rbp+57h+var_80]
0x180025699  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002569e  nop
0x18002569f  lea     rdx, aPackagePropert; "/Package/Properties/Description"
0x1800256a6  lea     rcx, [rbp+57h+var_A0]
0x1800256aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800256af  nop
0x1800256b0  lea     rax, [rbp+57h+var_C0]
0x1800256b4  mov     [rsp+20h], rax
0x1800256b9  lea     r9, [rbp+57h+var_80]
0x1800256bd  lea     r8, [rbp+57h+var_A0]
0x1800256c1  mov     rdx, r12
0x1800256c4  lea     rcx, [rsp+130h+var_100]
0x1800256c9  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x1800256ce  nop
0x1800256cf  lea     rcx, [rbp+57h+var_A0]
0x1800256d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800256d8  nop
0x1800256d9  lea     rcx, [rbp+57h+var_80]
0x1800256dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800256e2  nop
0x1800256e3  lea     rcx, [rbp+57h+var_C0]
0x1800256e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800256ec  mov     rdx, rsi
0x1800256ef  lea     rcx, [rbp+57h+var_C0]
0x1800256f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800256f8  nop
0x1800256f9  mov     rdx, rsi
0x1800256fc  lea     rcx, [rbp+57h+var_80]
0x180025700  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025705  nop
0x180025706  lea     rdx, aPackageApplica_0; "/Package/Applications/Application/Exten"...
0x18002570d  lea     rcx, [rbp+57h+var_A0]
0x180025711  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180025716  nop
0x180025717  lea     rax, [rbp+57h+var_C0]
0x18002571b  mov     [rsp+20h], rax
0x180025720  lea     r9, [rbp+57h+var_80]
0x180025724  lea     r8, [rbp+57h+var_A0]
0x180025728  mov     rdx, r12
0x18002572b  lea     rcx, [rsp+130h+var_100]
0x180025730  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180025735  nop
0x180025736  lea     rcx, [rbp+57h+var_A0]
0x18002573a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002573f  nop
0x180025740  lea     rcx, [rbp+57h+var_80]
0x180025744  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025749  nop
0x18002574a  lea     rcx, [rbp+57h+var_C0]
0x18002574e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025753  mov     rdx, rsi
0x180025756  lea     rcx, [rbp+57h+var_C0]
0x18002575a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002575f  nop
0x180025760  mov     rdx, rsi
0x180025763  lea     rcx, [rbp+57h+var_80]
0x180025767  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002576c  nop
0x18002576d  lea     rdx, aPackageApplica_1; "/Package/Applications/Application/Exten"...
0x180025774  lea     rcx, [rbp+57h+var_A0]
0x180025778  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002577d  nop
0x18002577e  lea     rax, [rbp+57h+var_C0]
0x180025782  mov     [rsp+20h], rax
0x180025787  lea     r9, [rbp+57h+var_80]
0x18002578b  lea     r8, [rbp+57h+var_A0]
0x18002578f  mov     rdx, r12
0x180025792  lea     rcx, [rsp+130h+var_100]
0x180025797  call    ?TranslateResourceIds@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; StoreApplication::TranslateResourceIds(Microsoft::WRL::ComPtr<IXMLDOMDocument> &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x18002579c  nop
0x18002579d  lea     rcx, [rbp+57h+var_A0]
0x1800257a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800257a6  nop
0x1800257a7  lea     rcx, [rbp+57h+var_80]
0x1800257ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800257b0  nop
0x1800257b1  lea     rcx, [rbp+57h+var_C0]
0x1800257b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800257ba  mov     rdx, rsi
0x1800257bd  lea     rcx, [rbp+57h+var_C0]
0x1800257c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800257c6  nop
  ... truncated ...
```

# OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass(Microsoft::WRL::ComPtr<IXMLDOMNode>,Windows::Internal::String const &,bool)

- ea: `0x180043ed0`
- end: `0x180044fe9`
- name: `?ParseAndSubmitIAMActivatableClass@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEBVString@2Windows@@_N@Z`
- size: `4377`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800436a8`

## callees

- `0x18000b3bc`
- `0x1800434a0`
- `0x180043ed0`
- `0x180044ff0`
- `0x180045a04`
- `0x18009aff4`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800fc211`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043f56`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044276`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043f56`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044276`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004405b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180044377`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004405b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180044377`
- `OLEAUT32!__imp_SysFreeString` at `0x180044010`
- `OLEAUT32!__imp_SysFreeString` at `0x18004417c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004432f`
- `OLEAUT32!__imp_SysFreeString` at `0x180044499`
- `OLEAUT32!__imp_SysFreeString` at `0x180044010`
- `OLEAUT32!__imp_SysFreeString` at `0x18004417c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004432f`
- `OLEAUT32!__imp_SysFreeString` at `0x180044499`
- `OLEAUT32!__imp_VariantClear` at `0x180044187`
- `OLEAUT32!__imp_VariantClear` at `0x1800444a4`
- `OLEAUT32!__imp_VariantClear` at `0x180044187`
- `OLEAUT32!__imp_VariantClear` at `0x1800444a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800441d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800444e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800441d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800444e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043fd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800442f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004456a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043fd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800442f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004456a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800441ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800444fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004492e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044bc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044bda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044ef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800441ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800444fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044867`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004492e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044a8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044bc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044bda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044ef0`

## string_xrefs

- `0x180044ab6`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044acf`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044c30`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044c51`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044c8b`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044cd5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044f18`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044f39`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044f7b`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044f9f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180044899`: `Common::Xml::GetAttributeValueStringFromElement( element.Get(), attributeName.GetRawBuffer(nullptr), buffer)`
- `0x18004494e`: `Common::Xml::GetAttributeValueStringFromElement( element.Get(), attributeName.GetRawBuffer(nullptr), buffer)`
- `0x180044a02`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180044a20`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180044bf4`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180044c12`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180044f57`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180044fc0`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18004481e`: `activatableClass->put_IsPackageRelativePath(isPackageRelativePath)`
- `0x1800449b9`: `InProcessActivatableClassRegistration::Create(acid, _sourcePackage->GetCollectors(), &activatableClass)`
- `0x180044e06`: `!activatableClass->put_DllPath(dllPath)`
- `0x180044e49`: `!activatableClass->put_ThreadingType(threadingModel)`
- `0x180044b9c`: `RetrieveAttribute(threadingModelQuery, root, threadingModelString)`
- `0x180044ec3`: `MapEnumString(ActivatableClassConstants::threadingMap, ARRAYSIZE(ActivatableClassConstants::threadingMap), threadingModelString, reinterpret_cast<DWORD*>(&threadingModel))`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned __int8 a4)
{
  __int64 *v4; // r12
  const WCHAR *v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rbx
  OLECHAR *v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  HRESULT v11; // r14d
  const OLECHAR *StringRawBuffer; // rdi
  __int64 v13; // r15
  __int64 v14; // rcx
  const OLECHAR *v15; // rax
  int v16; // eax
  BSTR bstrVal; // r12
  __int64 v18; // rcx
  BSTR v19; // rax
  unsigned int v20; // r15d
  unsigned int v21; // eax
  WCHAR *v22; // rdi
  unsigned __int64 v23; // rdx
  HSTRING v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  const WCHAR *v27; // rdi
  unsigned __int64 v28; // rbx
  HSTRING v29; // rdi
  __int64 v30; // rcx
  int v31; // eax
  HRESULT v32; // r15d
  const OLECHAR *v33; // r14
  __int64 v34; // r12
  OLECHAR *v35; // rbx
  __int64 v36; // rcx
  const OLECHAR *v37; // rax
  int v38; // eax
  BSTR v39; // r13
  __int64 v40; // rcx
  BSTR v41; // rax
  unsigned int v42; // r12d
  unsigned int v43; // eax
  WCHAR *v44; // r14
  unsigned __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rcx
  unsigned __int64 k; // rbx
  PCWSTR v49; // rax
  char *v50; // r8
  int v51; // ecx
  int v52; // edx
  unsigned int v53; // ecx
  bool v54; // zf
  __int64 v55; // rcx
  WCHAR *v56; // rax
  unsigned int i; // edx
  int v58; // eax
  unsigned int v59; // esi
  __int64 v60; // r14
  int v61; // eax
  unsigned int v62; // ebx
  int v63; // eax
  __int64 *v64; // rsi
  __int64 v65; // rcx
  int v66; // eax
  __int64 v67; // rdx
  unsigned int v68; // ebx
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v69; // rcx
  __int64 v70; // rcx
  unsigned int v72; // ecx
  __int64 v73; // rcx
  WCHAR *v74; // rax
  unsigned int j; // eax
  int v76; // eax
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v77; // rcx
  unsigned __int64 v78; // rdx
  __int64 v79; // rcx
  unsigned __int64 v80; // rdx
  __int64 v81; // rcx
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v82; // rcx
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  int v86; // eax
  int v87; // eax
  unsigned __int64 v88; // rdx
  unsigned __int64 v89; // rdx
  HSTRING v90; // rcx
  int v91; // [rsp+20h] [rbp-E0h]
  char *v92; // [rsp+28h] [rbp-D8h]
  char *v93; // [rsp+28h] [rbp-D8h]
  char *v94; // [rsp+28h] [rbp-D8h]
  char *v95; // [rsp+28h] [rbp-D8h]
  int v96[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v97; // [rsp+38h] [rbp-C8h] BYREF
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v98; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v99; // [rsp+48h] [rbp-B8h]
  HSTRING v100; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v101; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v102; // [rsp+60h] [rbp-A0h]
  PCNZWCH sourceString[2]; // [rsp+68h] [rbp-98h] BYREF
  int v104; // [rsp+78h] [rbp-88h]
  HSTRING v105; // [rsp+80h] [rbp-80h]
  VARIANTARG Src; // [rsp+88h] [rbp-78h] BYREF
  int *v107; // [rsp+A0h] [rbp-60h]
  __int64 v108; // [rsp+A8h] [rbp-58h]
  __int64 v109; // [rsp+B0h] [rbp-50h]
  __int64 *v110; // [rsp+B8h] [rbp-48h]
  HSTRING string; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v113; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v114; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+168h] [rbp+68h]

  v99 = a4;
  v109 = a3;
  v4 = a2;
  v102 = a2;
  v108 = a1;
  v110 = a2;
  v5 = off_1802E05E8;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( off_1802E05E8[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    LODWORD(v7) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v5, v7, &hstringHeader, &string);
  v8 = 0;
  v101 = 0;
  v9 = *v4;
  *(_QWORD *)v96 = v9;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v9 = *(_QWORD *)v96;
  }
  v105 = (HSTRING)v96;
  *(_OWORD *)sourceString = 0;
  v104 = 0;
  v97 = 0;
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
          v9,
          &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
          &v97);
  v11 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v92) = v10;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "node.As(&element)",
      v92,
      v96[0]);
    v84 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    }
    goto LABEL_157;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v13 = v97;
  memset(&Src, 0, sizeof(Src));
  Src.vt = 0;
  if ( v97 && StringRawBuffer )
  {
    SysFreeString(0);
    v8 = 0;
    v100 = 0;
    v14 = 0x7FFFFFFF;
    v15 = StringRawBuffer;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v14;
    }
    while ( v14 );
    v11 = -2147024809;
    if ( v14 )
    {
      if ( (unsigned int)(0x7FFFFFFF - v14) > 0x3FFFFFFF )
      {
        v11 = -2147024809;
      }
      else
      {
        v8 = SysAllocStringLen(StringRawBuffer, 0x7FFFFFFF - (int)v14);
        v100 = (HSTRING)v8;
        v11 = 0;
        if ( !v8 )
          v11 = -2147024882;
      }
    }
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v11,
        v91);
      v22 = (WCHAR *)sourceString[1];
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v13 + 352LL))(v13, v8, &Src);
      v11 = v16;
      if ( v16 >= 0 )
      {
        bstrVal = Src.bstrVal;
        if ( !Src.llVal )
        {
          v53 = _mm_cvtsi128_si32((__m128i)0LL);
          v54 = 2LL * v53 == 0;
          v55 = 2LL * v53;
          v22 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          v56 = v22;
          if ( !v54 )
          {
            do
            {
              *(_BYTE *)v56 = 0;
              v56 = (WCHAR *)((char *)v56 + 1);
              --v55;
            }
            while ( v55 );
          }
          goto LABEL_37;
        }
        v18 = 1073741822;
        v19 = Src.bstrVal;
        do
        {
          if ( !*v19 )
            break;
          ++v19;
          --v18;
        }
        while ( v18 );
        v11 = -2147024809;
        if ( v18 )
        {
          v20 = 1073741822 - v18;
          v11 = 0;
          if ( (unsigned int)(1073741822 - v18) > 0x7FFFFFFF )
            v11 = -2147024362;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x22F,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)(unsigned int)v11,
              v91);
            v22 = (WCHAR *)sourceString[1];
          }
          else
          {
            if ( !v20 )
              goto LABEL_28;
            if ( v20 > 0x20 )
            {
              i = 1073741822 - v18;
            }
            else
            {
              for ( i = 8; i < v20; i *= 2 )
                ;
            }
            v58 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)sourceString, i);
            v11 = v58;
            if ( v58 >= 0 )
            {
              if ( v104 )
              {
                v21 = v104 - 1;
LABEL_29:
                if ( v20 <= v21
                  || (v86 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)sourceString, v20),
                      v11 = v86,
                      v86 >= 0) )
                {
                  LODWORD(sourceString[0]) = v20;
                  v22 = (WCHAR *)sourceString[1];
                  if ( v20 )
                    sourceString[1][v20] = 0;
                  v11 = 0;
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x20C,
                    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                    (const char *)(unsigned int)v86,
                    v91);
                  v22 = (WCHAR *)sourceString[1];
                }
                if ( v11 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x235,
                    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                    (const char *)(unsigned int)v11,
                    v91);
                }
                else
                {
                  memcpy_0(v22, bstrVal, 2 * v20);
                  v11 = 0;
                }
                goto LABEL_35;
              }
LABEL_28:
              v21 = 0;
              goto LABEL_29;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x232,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)(unsigned int)v58,
              v91);
            v22 = (WCHAR *)sourceString[1];
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)0x80070057LL,
            v91);
          v22 = (WCHAR *)sourceString[1];
        }
LABEL_35:
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x13D,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v11,
            v91);
LABEL_37:
        v4 = v102;
        goto LABEL_38;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v16,
        v91);
      v22 = (WCHAR *)sourceString[1];
    }
  }
  else
  {
    v11 = -2147024809;
    v22 = (WCHAR *)sourceString[1];
  }
LABEL_38:
  SysFreeString(v8);
  VariantClear(&Src);
  if ( v11 < 0 )
  {
    LODWORD(v92) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "Common::Xml::GetAttributeValueStringFromElement( element.Get(), attributeName.GetRawBuffer(nullptr), buffer)",
      v92,
      v96[0]);
    v79 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    if ( v22 )
      operator delete(v22, v78);
    goto LABEL_157;
  }
  if ( !v22 )
  {
    v11 = -2147467261;
LABEL_201:
    LODWORD(v92) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "result.Initialize(buffer.GetChars())",
      v92,
      v96[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
    if ( v22 )
      operator delete(v22, v88);
LABEL_157:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v96);
    LODWORD(v93) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
      "RetrieveAttribute(acidQuery, root, acid)",
      v93,
      v96[0]);
    if ( v101 )
      WindowsDeleteString(v101);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v4);
    return (unsigned int)v11;
  }
  v100 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( v23 > 0xFFFFFFFF )
  {
    v11 = -2147024362;
  }
  else
  {
    v11 = WindowsCreateString(v22, v23, &v100);
    if ( v11 >= 0 )
    {
      v24 = v101;
      v101 = v100;
      WindowsDeleteString(v24);
    }
  }
  if ( v11 < 0 )
    goto LABEL_201;
  v25 = v97;
  if ( v97 )
  {
    v97 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  operator delete(v22, v23);
  v26 = *(_QWORD *)v96;
  if ( *(_QWORD *)v96 )
  {
    *(_QWORD *)v96 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = off_1802E05E0;
  v28 = -1;
  do
    ++v28;
  while ( off_1802E05E0[v28] );
  if ( v28 > 0xFFFFFFFF )
  {
    LODWORD(v28) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v27, v28, &v114, &v113);
  v29 = 0;
  v105 = 0;
  v30 = *v4;
  *(_QWORD *)v96 = v30;
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    v30 = *(_QWORD *)v96;
  }
  v107 = v96;
  *(_OWORD *)sourceString = 0;
  v104 = 0;
  v97 = 0;
  v31 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(
          v30,
          &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
          &v97);
  v32 = v31;
  if ( v31 < 0 )
  {
    LODWORD(v92) = v31;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "node.As(&element)",
      v92,
      v96[0]);
    v85 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v96);
    goto LABEL_185;
  }
  v33 = WindowsGetStringRawBuffer(v113, 0);
  v34 = v97;
  memset(&Src, 0, sizeof(Src));
  Src.vt = 0;
  v35 = 0;
  if ( !v97 || !v33 )
  {
    v32 = -2147024809;
    v44 = (WCHAR *)sourceString[1];
    goto LABEL_86;
  }
  SysFreeString(0);
  v100 = 0;
  v36 = 0x7FFFFFFF;
  v37 = v33;
  do
  {
    if ( !*v37 )
      break;
    ++v37;
    --v36;
  }
  while ( v36 );
  v32 = -2147024809;
  if ( v36 )
  {
    if ( (unsigned int)(0x7FFFFFFF - v36) > 0x3FFFFFFF )
    {
      v32 = -2147024809;
    }
    else
    {
      v35 = SysAllocStringLen(v33, 0x7FFFFFFF - (int)v36);
      v100 = (HSTRING)v35;
      v32 = 0;
      if ( !v35 )
        v32 = -2147024882;
    }
  }
  if ( v32 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v32,
      v91);
    v44 = (WCHAR *)sourceString[1];
    goto LABEL_86;
  }
  v38 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v34 + 352LL))(v34, v35, &Src);
  v32 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)(unsigned int)v38,
      v91);
    v44 = (WCHAR *)sourceString[1];
    goto LABEL_86;
  }
  v39 = Src.bstrVal;
  if ( Src.llVal )
  {
    v40 = 1073741822;
    v41 = Src.bstrVal;
    do
    {
      if ( !*v41 )
        break;
      ++v41;
      --v40;
    }
    while ( v40 );
    v32 = -2147024809;
    if ( v40 )
    {
      v42 = 1073741822 - v40;
      v32 = 0;
      if ( (unsigned int)(1073741822 - v40) > 0x7FFFFFFF )
        v32 = -2147024362;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v32,
          v91);
        v44 = (WCHAR *)sourceString[1];
      }
      else
      {
        if ( !v42 )
          goto LABEL_77;
        if ( v42 > 0x20 )
        {
          j = 1073741822 - v40;
        }
        else
        {
          for ( j = 8; j < v42; j *= 2 )
            ;
        }
        v76 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)sourceString, j);
        v32 = v76;
        if ( v76 >= 0 )
        {
          if ( v104 )
          {
            v43 = v104 - 1;
LABEL_78:
            if ( v42 <= v43
              || (v87 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)sourceString, v42), v32 = v87, v87 >= 0) )
            {
              LODWORD(sourceString[0]) = v42;
              v44 = (WCHAR *)sourceString[1];
              if ( v42 )
                sourceString[1][v42] = 0;
              v32 = 0;
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x20C,
                (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                (const char *)(unsigned int)v87,
                v91);
              v44 = (WCHAR *)sourceString[1];
            }
            if ( v32 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x235,
                (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                (const char *)(unsigned int)v32,
                v91);
            }
            else
            {
              memcpy_0(v44, v39, 2 * v42);
              v32 = 0;
            }
            goto LABEL_84;
          }
LABEL_77:
          v43 = 0;
          goto LABEL_78;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v76,
          v91);
        v44 = (WCHAR *)sourceString[1];
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        v91);
      v44 = (WCHAR *)sourceString[1];
    }
LABEL_84:
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)(unsigned int)v32,
        v91);
    goto LABEL_86;
  }
  v72 = _mm_cvtsi128_si32((__m128i)0LL);
  v54 = 2LL * v72 == 0;
  v73 = 2LL * v72;
  v44 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v74 = v44;
  if ( !v54 )
  {
    do
    {
      *(_BYTE *)v74 = 0;
      v74 = (WCHAR *)((char *)v74 + 1);
      --v73;
    }
    while ( v73 );
  }
LABEL_86:
  SysFreeString(v35);
  VariantClear(&Src);
  if ( v32 < 0 )
  {
    LODWORD(v92) = v32;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "Common::Xml::GetAttributeValueStringFromElement( element.Get(), attributeName.GetRawBuffer(nullptr), buffer)",
      v92,
      v96[0]);
    v81 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    if ( v44 )
      operator delete(v44, v80);
    goto LABEL_164;
  }
  if ( !v44 )
  {
    v32 = -2147467261;
LABEL_205:
    LODWORD(v92) = v32;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute",
      "result.Initialize(buffer.GetChars())",
      v92,
      v96[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
    if ( v44 )
      operator delete(v44, v89);
LABEL_164:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v96);
    v4 = v102;
LABEL_185:
    LODWORD(v94) = v32;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x27E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
      "RetrieveAttribute(threadingModelQuery, root, threadingModelString)",
      v94,
      v96[0]);
    if ( v29 )
      WindowsDeleteString(v29);
    if ( v101 )
      WindowsDeleteString(v101);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v4);
    return (unsigned int)v32;
  }
  v100 = 0;
  do
    ++v6;
  while ( v44[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    v32 = -2147024362;
  }
  else
  {
    v32 = WindowsCreateString(v44, v6, &v100);
    if ( v32 >= 0 )
    {
      v29 = v100;
      v105 = v100;
      WindowsDeleteString(0);
    }
  }
  if ( v32 < 0 )
    goto LABEL_205;
  v46 = v97;
  if ( v97 )
  {
    v97 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  operator delete(v44, v45);
  v47 = *(_QWORD *)v96;
  if ( *(_QWORD *)v96 )
  {
    *(_QWORD *)v96 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  for ( k = 0; ; ++k )
  {
    if ( k >= 3 )
    {
      LODWORD(v92) = -2147024809;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::MapEnumString",
        "E_INVALIDARG",
        v92,
        v96[0]);
      LODWORD(v95) = -2147024809;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x282,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
        "MapEnumString(ActivatableClassConstants::threadingMap, ARRAYSIZE(ActivatableClassConstants::threadingMap), threa"
        "dingModelString, reinterpret_cast<DWORD*>(&threadingModel))",
        v95,
        v96[0]);
      if ( v29 )
        WindowsDeleteString(v29);
      v90 = v101;
      if ( v101 )
        goto LABEL_208;
      goto LABEL_209;
    }
    v49 = WindowsGetStringRawBuffer(v29, 0);
    v50 = (char *)((char *)(&off_1802E05B0)[2 * k] - (char *)v49);
    do
    {
      v51 = *(unsigned __int16 *)&v50[(_QWORD)v49];
      v52 = *v49 - v51;
      if ( v52 )
        break;
      ++v49;
    }
    while ( v51 );
    if ( !v52 )
      break;
  }
  v59 = *((_DWORD *)&off_1802E05B0 + 4 * k + 2);
  v98 = 0;
  v60 = v108;
  v61 = OSIntegration::DEH::InProcessActivatableClassRegistration::Create(
          (const struct Windows::Internal::String *)&v101,
          *(struct OSIntegration::DEH::Collectors **)(*(_QWORD *)(v108 + 32) + 808LL),
          &v98);
  v62 = v61;
  if ( v61 < 0 )
  {
    LODWORD(v92) = v61;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
      "InProcessActivatableClassRegistration::Create(acid, _sourcePackage->GetCollectors(), &activatableClass)",
      v92,
      v96[0]);
    v82 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v82 + 16LL))(v82);
    }
  }
  else
  {
    if ( !(*(unsigned __int8 (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *, __int64))(*(_QWORD *)v98 + 152LL))(
            v98,
            v109) )
    {
      LODWORD(v92) = -2147024809;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x287,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
        "!activatableClass->put_DllPath(dllPath)",
        v92,
        v96[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
      if ( v29 )
        goto LABEL_210;
      goto LABEL_211;
    }
    v63 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *, _QWORD))(*(_QWORD *)v98 + 160LL))(
            v98,
            v99);
    v62 = v63;
    if ( v63 >= 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *, _QWORD))(*(_QWORD *)v98 + 168LL))(
             v98,
             v59) )
      {
        v100 = (HSTRING)v98;
        if ( v98 )
          (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v98 + 8LL))(v98);
        v64 = v102;
        v65 = *v102;
        *(_QWORD *)v96 = v65;
        if ( v65 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
        v66 = OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitCustomAttributes(v60, v96, &v100);
        v68 = v66;
        if ( v66 < 0 )
        {
          LODWORD(v92) = v66;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x28B,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
            "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
            "ParseAndSubmitCustomAttributes(root, activatableClass)",
            v92,
            v96[0]);
          v83 = v98;
          if ( v98 )
          {
            v98 = 0;
            (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v83 + 16LL))(v83);
          }
          if ( v29 )
            WindowsDeleteString(v29);
          if ( v101 )
            WindowsDeleteString(v101);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v64);
          return v68;
        }
        else
        {
          LOBYTE(v67) = 1;
          (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *, __int64))(*(_QWORD *)v98 + 128LL))(
            v98,
            v67);
          v69 = v98;
          if ( v98 )
          {
            v98 = 0;
            (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v69 + 16LL))(v69);
          }
          if ( v29 )
            WindowsDeleteString(v29);
          if ( v101 )
            WindowsDeleteString(v101);
          v70 = *v64;
          if ( *v64 )
          {
            *v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
          }
          return 0;
        }
      }
      LODWORD(v92) = -2147024809;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
        "!activatableClass->put_ThreadingType(threadingModel)",
        v92,
        v96[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
      if ( v29 )
LABEL_210:
        WindowsDeleteString(v29);
LABEL_211:
      v90 = v101;
      if ( v101 )
LABEL_208:
        WindowsDeleteString(v90);
LABEL_209:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v102);
      return 2147942487LL;
    }
    LODWORD(v92) = v63;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass",
      "activatableClass->put_IsPackageRelativePath(isPackageRelativePath)",
      v92,
      v96[0]);
    v77 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v77 + 16LL))(v77);
    }
  }
  if ( v29 )
    WindowsDeleteString(v29);
  if ( v101 )
    WindowsDeleteString(v101);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v102);
  return v62;
}

```

## disassembly

```asm
0x180043ed0  push    rbp
0x180043ed2  push    rbx
0x180043ed3  push    rsi
0x180043ed4  push    rdi
0x180043ed5  push    r12
0x180043ed7  push    r13
0x180043ed9  push    r14
0x180043edb  push    r15
0x180043edd  lea     rbp, [rsp-28h]
0x180043ee2  sub     rsp, 128h
0x180043ee9  movaps  [rsp+160h+var_50], xmm6
0x180043ef1  mov     rax, cs:__security_cookie
0x180043ef8  xor     rax, rsp
0x180043efb  mov     [rbp+60h+var_60], rax
0x180043eff  mov     [rsp+160h+var_118], r9b
0x180043f04  mov     [rbp+60h+var_B0], r8
0x180043f08  mov     r12, rdx
0x180043f0b  mov     [rsp+160h+var_100], rdx
0x180043f10  mov     [rbp+60h+var_B8], rcx
0x180043f14  mov     [rbp+60h+var_A8], rdx
0x180043f18  mov     rdi, cs:off_1802E05E8; "ActivatableClassId"
0x180043f1f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180043f26  mov     rbx, rsi
0x180043f29  nop     dword ptr [rax+00000000h]
0x180043f30  inc     rbx
0x180043f33  cmp     word ptr [rdi+rbx*2], 0
0x180043f38  jnz     short loc_180043F30
0x180043f3a  mov     eax, 0FFFFFFFFh
0x180043f3f  cmp     rbx, rax
0x180043f42  jbe     short loc_180043F5C
0x180043f44  mov     ebx, eax
0x180043f46  xor     r9d, r9d; lpArguments
0x180043f49  xor     r8d, r8d; nNumberOfArguments
0x180043f4c  mov     edx, 1; dwExceptionFlags
0x180043f51  mov     ecx, 0C000000Dh; dwExceptionCode
0x180043f56  call    cs:__imp_RaiseException
0x180043f5c  lea     r9, [rbp+60h+string]; string
0x180043f60  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180043f64  mov     edx, ebx; length
0x180043f66  mov     rcx, rdi; sourceString
0x180043f69  call    cs:__imp_WindowsCreateStringReference
0x180043f6f  xor     ebx, ebx
0x180043f71  mov     [rsp+160h+var_108], rbx
0x180043f76  mov     rcx, [r12]
0x180043f7a  mov     qword ptr [rsp+160h+var_130], rcx; int
0x180043f7f  test    rcx, rcx
0x180043f82  jz      short loc_180043F95
0x180043f84  mov     rax, [rcx]
0x180043f87  mov     rax, [rax+8]
0x180043f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f90  mov     rcx, qword ptr [rsp+160h+var_130]
0x180043f95  lea     rax, [rsp+160h+var_130]
0x180043f9a  mov     [rbp+60h+var_E0], rax
0x180043f9e  xorps   xmm6, xmm6
0x180043fa1  movups  xmmword ptr [rsp+160h+sourceString], xmm6
0x180043fa6  mov     [rsp+160h+var_E8], ebx
0x180043faa  mov     [rsp+160h+var_128], rbx
0x180043faf  mov     rax, [rcx]
0x180043fb2  lea     r8, [rsp+160h+var_128]
0x180043fb7  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180043fbe  mov     rax, [rax]
0x180043fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fc6  mov     r14d, eax
0x180043fc9  test    eax, eax
0x180043fcb  js      loc_180044AE8
0x180043fd1  xor     edx, edx; length
0x180043fd3  mov     rcx, [rbp+60h+string]; string
0x180043fd7  call    cs:__imp_WindowsGetStringRawBuffer
0x180043fdd  mov     rdi, rax
0x180043fe0  mov     r15, [rsp+160h+var_128]
0x180043fe5  xorps   xmm0, xmm0
0x180043fe8  xor     eax, eax
0x180043fea  movups  xmmword ptr [rbp+60h+Src], xmm0
0x180043fee  mov     [rbp+60h+var_C8], rax
0x180043ff2  mov     word ptr [rbp+60h+Src], bx
0x180043ff6  mov     r13d, 3FFFFFFEh
0x180043ffc  test    r15, r15
0x180043fff  jz      loc_180044CA6
0x180044005  test    rdi, rdi
0x180044008  jz      loc_180044CA6
0x18004400e  xor     ecx, ecx; bstrString
0x180044010  call    cs:__imp_SysFreeString
0x180044016  xor     ebx, ebx
0x180044018  mov     [rsp+160h+var_110], rbx
0x18004401d  mov     ecx, 7FFFFFFFh
0x180044022  mov     rax, rdi
0x180044025  cmp     [rax], bx
0x180044028  jz      short loc_180044034
0x18004402a  add     rax, 2
0x18004402e  sub     rcx, 1
0x180044032  jnz     short loc_180044025
0x180044034  xor     eax, eax
0x180044036  mov     r14d, 80070057h
0x18004403c  test    rcx, rcx
0x18004403f  cmovnz  r14d, eax
0x180044043  jz      short loc_180044078
0x180044045  mov     edx, 7FFFFFFFh
0x18004404a  sub     edx, ecx; ui
0x18004404c  cmp     edx, 3FFFFFFFh
0x180044052  ja      loc_180044F0A
0x180044058  mov     rcx, rdi; strIn
0x18004405b  call    cs:__imp_SysAllocStringLen
0x180044061  mov     rbx, rax
0x180044064  mov     [rsp+160h+var_110], rax
0x180044069  xor     r14d, r14d
0x18004406c  test    rax, rax
0x18004406f  mov     eax, 8007000Eh
0x180044074  cmovz   r14d, eax
0x180044078  mov     rcx, [rbp+68h]; this
0x18004407c  test    r14d, r14d
0x18004407f  js      loc_180044BF1
0x180044085  mov     rax, [r15]
0x180044088  lea     r8, [rbp+60h+Src]
0x18004408c  mov     rdx, rbx
0x18004408f  mov     rcx, r15
0x180044092  mov     rax, [rax+160h]
0x180044099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004409e  mov     r14d, eax
0x1800440a1  mov     rcx, [rbp+68h]; this
0x1800440a5  test    eax, eax
0x1800440a7  js      loc_1800449FF
0x1800440ad  mov     r12, [rbp+60h+Src+8]
0x1800440b1  test    r12, r12
0x1800440b4  jz      loc_1800445AC
0x1800440ba  mov     rcx, r13
0x1800440bd  mov     rax, r12
0x1800440c0  cmp     word ptr [rax], 0
0x1800440c4  jz      short loc_1800440D0
0x1800440c6  add     rax, 2
0x1800440ca  sub     rcx, 1
0x1800440ce  jnz     short loc_1800440C0
0x1800440d0  xor     eax, eax
0x1800440d2  mov     r14d, 80070057h
0x1800440d8  test    rcx, rcx
0x1800440db  cmovnz  r14d, eax
0x1800440df  mov     rax, r13
0x1800440e2  sub     rax, rcx
0x1800440e5  xor     r15d, r15d
0x1800440e8  test    rcx, rcx
0x1800440eb  cmovnz  r15, rax
0x1800440ef  mov     rax, [rbp+68h]
0x1800440f3  jz      loc_180044F15
0x1800440f9  xor     r14d, r14d
0x1800440fc  cmp     r15d, 7FFFFFFFh
0x180044103  mov     eax, 80070216h
0x180044108  cmova   r14d, eax
0x18004410c  mov     rcx, [rbp+68h]; this
0x180044110  test    r14d, r14d
0x180044113  js      loc_180044F36
0x180044119  test    r15d, r15d
0x18004411c  jnz     loc_1800445D8
0x180044122  xor     eax, eax
0x180044124  cmp     r15d, eax
0x180044127  ja      loc_180044C6C
0x18004412d  mov     dword ptr [rsp+160h+sourceString], r15d
0x180044132  mov     rdi, [rsp+160h+sourceString+8]
0x180044137  test    r15d, r15d
0x18004413a  jz      short loc_180044145
0x18004413c  mov     ecx, r15d
0x18004413f  xor     eax, eax
0x180044141  mov     [rdi+rcx*2], ax
0x180044145  xor     r14d, r14d
0x180044148  mov     rcx, [rbp+68h]; this
0x18004414c  test    r14d, r14d
0x18004414f  js      loc_180044AB3
0x180044155  lea     r8d, [r15+r15]; Size
0x180044159  mov     rdx, r12; Src
0x18004415c  mov     rcx, rdi; void *
0x18004415f  call    memcpy_0
0x180044164  xor     r14d, r14d
0x180044167  mov     rcx, [rbp+68h]; this
0x18004416b  test    r14d, r14d
0x18004416e  js      loc_180044F54
0x180044174  mov     r12, [rsp+160h+var_100]
0x180044179  mov     rcx, rbx; bstrString
0x18004417c  call    cs:__imp_SysFreeString
0x180044182  nop
0x180044183  lea     rcx, [rbp+60h+Src]; pvarg
0x180044187  call    cs:__imp_VariantClear
0x18004418d  test    r14d, r14d
0x180044190  js      loc_180044890
0x180044196  lea     rax, aResultInitiali; "result.Initialize(buffer.GetChars())"
0x18004419d  xor     r13d, r13d
0x1800441a0  test    rdi, rdi
0x1800441a3  jz      loc_180044D00
0x1800441a9  mov     [rsp+160h+var_110], r13
0x1800441ae  mov     rdx, rsi
0x1800441b1  inc     rdx; length
0x1800441b4  cmp     [rdi+rdx*2], r13w
0x1800441b9  jnz     short loc_1800441B1
0x1800441bb  mov     r15d, 0FFFFFFFFh
0x1800441c1  cmp     rdx, r15
0x1800441c4  ja      loc_1800445A1
0x1800441ca  lea     r8, [rsp+160h+var_110]; string
0x1800441cf  mov     rcx, rdi; sourceString
0x1800441d2  call    cs:__imp_WindowsCreateString
0x1800441d8  mov     r14d, eax
0x1800441db  test    eax, eax
0x1800441dd  js      short loc_1800441F4
0x1800441df  mov     rcx, [rsp+160h+var_108]; string
0x1800441e4  mov     rax, [rsp+160h+var_110]
0x1800441e9  mov     [rsp+160h+var_108], rax
0x1800441ee  call    cs:__imp_WindowsDeleteString
0x1800441f4  lea     rax, aResultInitiali; "result.Initialize(buffer.GetChars())"
0x1800441fb  test    r14d, r14d
0x1800441fe  js      loc_180044D0C
0x180044204  mov     rcx, [rsp+160h+var_128]
0x180044209  test    rcx, rcx
0x18004420c  jz      short loc_180044220
0x18004420e  mov     [rsp+160h+var_128], r13
0x180044213  mov     rax, [rcx]
0x180044216  mov     rax, [rax+10h]
0x18004421a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004421f  nop
0x180044220  test    rdi, rdi
0x180044223  jz      short loc_18004422E
0x180044225  mov     rcx, rdi; void *
0x180044228  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004422d  nop
0x18004422e  mov     rcx, qword ptr [rsp+160h+var_130]
0x180044233  test    rcx, rcx
0x180044236  jz      short loc_18004424A
0x180044238  mov     qword ptr [rsp+160h+var_130], r13
0x18004423d  mov     rax, [rcx]
0x180044240  mov     rax, [rax+10h]
0x180044244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044249  nop
0x18004424a  mov     rdi, cs:off_1802E05E0
0x180044251  mov     rbx, rsi
0x180044254  inc     rbx
0x180044257  cmp     word ptr [rdi+rbx*2], 0
0x18004425c  jnz     short loc_180044254
0x18004425e  cmp     rbx, r15
0x180044261  jbe     short loc_18004427C
0x180044263  mov     ebx, r15d
0x180044266  xor     r9d, r9d; lpArguments
0x180044269  xor     r8d, r8d; nNumberOfArguments
0x18004426c  mov     edx, 1; dwExceptionFlags
0x180044271  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044276  call    cs:__imp_RaiseException
0x18004427c  lea     r9, [rbp+60h+var_80]; string
0x180044280  lea     r8, [rbp+60h+var_78]; hstringHeader
0x180044284  mov     edx, ebx; length
0x180044286  mov     rcx, rdi; sourceString
0x180044289  call    cs:__imp_WindowsCreateStringReference
0x18004428f  mov     rdi, r13
0x180044292  mov     [rbp+60h+var_E0], r13
0x180044296  mov     rcx, [r12]
0x18004429a  mov     qword ptr [rsp+160h+var_130], rcx; int
0x18004429f  test    rcx, rcx
0x1800442a2  jz      short loc_1800442B5
0x1800442a4  mov     rax, [rcx]
0x1800442a7  mov     rax, [rax+8]
0x1800442ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442b0  mov     rcx, qword ptr [rsp+160h+var_130]
0x1800442b5  lea     rax, [rsp+160h+var_130]
0x1800442ba  mov     [rbp+60h+var_C0], rax
0x1800442be  xorps   xmm6, xmm6
0x1800442c1  movups  xmmword ptr [rsp+160h+sourceString], xmm6
0x1800442c6  mov     [rsp+160h+var_E8], r13d
0x1800442cb  mov     [rsp+160h+var_128], r13
0x1800442d0  mov     rax, [rcx]
0x1800442d3  lea     r8, [rsp+160h+var_128]
0x1800442d8  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800442df  mov     rax, [rax]
0x1800442e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442e7  mov     r15d, eax
0x1800442ea  test    eax, eax
0x1800442ec  js      loc_180044B40
0x1800442f2  xor     edx, edx; length
0x1800442f4  mov     rcx, [rbp+60h+var_80]; string
0x1800442f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800442fe  mov     r14, rax
0x180044301  mov     r12, [rsp+160h+var_128]
0x180044306  xorps   xmm0, xmm0
0x180044309  xor     eax, eax
0x18004430b  movups  xmmword ptr [rbp+60h+Src], xmm0
0x18004430f  mov     [rbp+60h+var_C8], rax
0x180044313  mov     word ptr [rbp+60h+Src], r13w
0x180044318  mov     rbx, r13
0x18004431b  test    r12, r12
0x18004431e  jz      loc_180044CF0
0x180044324  test    r14, r14
0x180044327  jz      loc_180044CF0
0x18004432d  xor     ecx, ecx; bstrString
0x18004432f  call    cs:__imp_SysFreeString
0x180044335  mov     [rsp+160h+var_110], rbx
0x18004433a  mov     ecx, 7FFFFFFFh
0x18004433f  mov     rax, r14
0x180044342  cmp     word ptr [rax], 0
0x180044346  jz      short loc_180044352
0x180044348  add     rax, 2
0x18004434c  sub     rcx, 1
0x180044350  jnz     short loc_180044342
0x180044352  mov     r15d, 80070057h
0x180044358  test    rcx, rcx
0x18004435b  cmovnz  r15d, r13d
0x18004435f  jz      short loc_180044394
0x180044361  mov     edx, 7FFFFFFFh
0x180044366  sub     edx, ecx; ui
  ... truncated ...
```

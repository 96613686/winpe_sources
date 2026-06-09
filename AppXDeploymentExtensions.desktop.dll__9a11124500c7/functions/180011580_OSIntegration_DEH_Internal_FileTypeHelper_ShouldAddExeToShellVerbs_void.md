# OSIntegration::DEH::Internal::FileTypeHelper::ShouldAddExeToShellVerbs(void)

- ea: `0x180011580`
- end: `0x180012709`
- name: `?ShouldAddExeToShellVerbs@FileTypeHelper@Internal@DEH@OSIntegration@@AEAAJXZ`
- size: `4489`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::FileTypeHelper *this, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e0950`

## callees

- `0x180006130`
- `0x180006970`
- `0x180011580`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800207a0`
- `0x1800353c0`
- `0x18003d8b8`
- `0x180040230`
- `0x18005649c`
- `0x180064994`
- `0x180066780`
- `0x1800807b4`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800ba45d`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011a60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800121c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180011a60`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800121c5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011816`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011d8f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011816`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180011d8f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800117b9`
- `OLEAUT32!__imp_SysFreeString` at `0x180011929`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e23`
- `OLEAUT32!__imp_SysFreeString` at `0x180012002`
- `OLEAUT32!__imp_SysFreeString` at `0x180012048`
- `OLEAUT32!__imp_SysFreeString` at `0x1800117b9`
- `OLEAUT32!__imp_SysFreeString` at `0x180011929`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e23`
- `OLEAUT32!__imp_SysFreeString` at `0x180012002`
- `OLEAUT32!__imp_SysFreeString` at `0x180012048`
- `OLEAUT32!__imp_VariantClear` at `0x180011a0d`
- `OLEAUT32!__imp_VariantClear` at `0x180011a0d`

## string_xrefs

- `0x180011912`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x1800119d7`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011ae3`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011afc`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011be7`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011c03`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011c1c`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011c38`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011fed`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180012033`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180011eb7`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011f4f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180011fcf`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18001230c`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18001237f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800125d3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012670`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012691`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800126b7`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::FileTypeHelper::ShouldAddExeToShellVerbs(
        OSIntegration::DEH::Internal::FileTypeHelper *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  OSIntegration::DEH::Internal::FileTypeHelper *v4; // r13
  __int64 v5; // rax
  _DWORD *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int i; // r12d
  int v14; // eax
  int v15; // ebx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rdi
  struct IXMLDOMNodeListVtbl *lpVtbl; // rcx
  int v19; // eax
  const struct std::nothrow_t *v20; // rdx
  struct IXMLDOMNodeListVtbl *v21; // rax
  struct IXMLDOMNodeListVtbl *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rcx
  unsigned int v24; // r15d
  struct IXMLDOMNodeListVtbl *v25; // r14
  OLECHAR *v26; // rdi
  __int64 v27; // rcx
  const OLECHAR *v28; // rax
  int v29; // esi
  __int64 (__fastcall *v30)(struct IXMLDOMNodeListVtbl *, OLECHAR *, int *); // rbx
  _QWORD *v31; // rcx
  int v32; // eax
  __int64 (__fastcall ***v33)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rsi
  struct IXMLDOMNodeListVtbl *v35; // rcx
  int v36; // eax
  struct IXMLDOMNodeListVtbl *v37; // rax
  struct IXMLDOMNodeListVtbl *v38; // rcx
  __int64 (__fastcall ***v39)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rcx
  int v40; // eax
  int v41; // ebx
  BSTR bstrVal; // r13
  WCHAR *v43; // rdi
  void *v44; // rcx
  const struct std::nothrow_t *v45; // rdx
  struct IXMLDOMNodeListVtbl *v46; // rcx
  struct IXMLDOMNodeListVtbl *v47; // rcx
  unsigned int v48; // ecx
  bool v49; // zf
  __int64 v50; // rcx
  WCHAR *v51; // rax
  __int64 v52; // rcx
  BSTR v53; // rax
  unsigned int v54; // ebx
  unsigned int v55; // eax
  __int64 result; // rax
  struct IXMLDOMNodeListVtbl *v57; // r14
  OLECHAR *v58; // rbx
  __int64 v59; // rcx
  const OLECHAR *v60; // rax
  __int64 v61; // rcx
  _QWORD *v62; // rcx
  unsigned int v63; // esi
  __int64 (__fastcall *v64)(struct IXMLDOMNodeListVtbl *, OLECHAR *, struct IXMLDOMNodeListVtbl **); // rsi
  struct IXMLDOMNodeListVtbl *v65; // rcx
  int v66; // eax
  struct IXMLDOMNodeListVtbl *v67; // rax
  struct IXMLDOMNodeListVtbl *v68; // rcx
  int v69; // eax
  unsigned int v70; // ebx
  unsigned int k; // esi
  __int64 (__fastcall ***v72)(_QWORD, GUID *, struct IXMLDOMNodeList *); // rcx
  unsigned int j; // esi
  __int64 v74; // r14
  WCHAR *v75; // xmm7_8
  unsigned __int64 v76; // rax
  WCHAR *v77; // rax
  WCHAR *v78; // r15
  const struct std::nothrow_t *v79; // rdx
  struct IXMLDOMNodeListVtbl *v80; // rcx
  struct IXMLDOMElement **v81; // r9
  int ElementFromNodeList; // eax
  int AttributeValueStringByLocalName; // eax
  const struct std::nothrow_t *v84; // rdx
  __int64 v85; // r8
  const unsigned __int16 *v86; // r8
  int v87; // r14d
  std::filesystem *v88; // rcx
  const unsigned __int16 *v89; // rbx
  BSTR v90; // rbx
  LONGLONG llVal; // r14
  WCHAR *v92; // rcx
  struct IXMLDOMNodeListVtbl *v93; // rcx
  const struct std::nothrow_t *v94; // rdx
  struct IXMLDOMNodeListVtbl *v95; // rcx
  __int64 v96; // rcx
  _QWORD *v97; // rcx
  int v98; // eax
  const struct std::nothrow_t *v99; // rdx
  const struct std::nothrow_t *v100; // rdx
  WCHAR *v101; // xmm7_8
  const struct std::nothrow_t *v102; // rdx
  errno_t v103; // r12d
  int *bIgnoreCase; // [rsp+20h] [rbp-138h]
  int bIgnoreCasea; // [rsp+20h] [rbp-138h]
  char *v106; // [rsp+28h] [rbp-130h]
  struct IXMLDOMNodeList v107; // [rsp+30h] [rbp-128h] BYREF
  int v108[2]; // [rsp+38h] [rbp-120h] BYREF
  struct IXMLDOMNodeListVtbl *v109; // [rsp+40h] [rbp-118h] BYREF
  __int64 v110; // [rsp+48h] [rbp-110h] BYREF
  _QWORD *v111; // [rsp+50h] [rbp-108h] BYREF
  struct IXMLDOMNodeListVtbl *v112; // [rsp+58h] [rbp-100h] BYREF
  unsigned int v113; // [rsp+60h] [rbp-F8h]
  int v114; // [rsp+64h] [rbp-F4h]
  LPCWCH lpString1[2]; // [rsp+68h] [rbp-F0h] BYREF
  unsigned int v116; // [rsp+78h] [rbp-E0h]
  int v117; // [rsp+80h] [rbp-D8h] BYREF
  int v118; // [rsp+84h] [rbp-D4h] BYREF
  OLECHAR *v119; // [rsp+88h] [rbp-D0h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-C8h] BYREF
  OSIntegration::DEH::Internal::FileTypeHelper *v121; // [rsp+A8h] [rbp-B0h]
  _QWORD v122[2]; // [rsp+B0h] [rbp-A8h] BYREF
  std::filesystem *v123[2]; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v124; // [rsp+D0h] [rbp-88h]
  unsigned __int64 v125; // [rsp+D8h] [rbp-80h]
  WCHAR String1[4]; // [rsp+E0h] [rbp-78h] BYREF
  unsigned __int64 v127; // [rsp+F8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  try
  {
    v4 = this;
    v121 = this;
    v114 = 0;
    v5 = *((_QWORD *)this + 20);
    if ( !v5 )
      return 0;
    v6 = (_DWORD *)(v5 + 144);
    if ( !v6 || !*v6 )
      return 0;
    v111 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(**((_QWORD **)this + 2) + 88LL))(*((_QWORD *)this + 2), &v111);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x272,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
        (const char *)(unsigned int)v7,
        (int)bIgnoreCase);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v111);
      return v8;
    }
    v110 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v111 + 96LL))(v111, &v110);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x275,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
        (const char *)(unsigned int)v9,
        (int)bIgnoreCase);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v110);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v111);
      return v10;
    }
    v117 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v110 + 64LL))(v110, &v117);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
        (const char *)(unsigned int)v11,
        (int)bIgnoreCase);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v110);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v111);
      return v12;
    }
    for ( i = 0; ; ++i )
    {
      v113 = i;
      if ( (int)i >= v117 )
      {
        v61 = v110;
        if ( v110 )
        {
          v110 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        }
        v62 = v111;
        if ( v111 )
        {
          v111 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
        }
        return 0;
      }
      v112 = 0;
      if ( !v110 )
      {
        v15 = -2147024809;
LABEL_94:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
          (const char *)(unsigned int)v15,
          (int)bIgnoreCase);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v110);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v111);
        return (unsigned int)v15;
      }
      *(_QWORD *)v108 = 0;
      v107.lpVtbl = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v110 + 56LL))(v110, i, v108);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v14,
          (int)bIgnoreCase);
      }
      else
      {
        v16 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
        v17 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
        lpVtbl = v107.lpVtbl;
        if ( v107.lpVtbl )
        {
          v107.lpVtbl = 0;
          (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *, HRESULT (__stdcall *)(IXMLDOMNodeList *, const IID *const, void **)))lpVtbl->QueryInterface
           + 2))(
            lpVtbl,
            lpVtbl->QueryInterface);
        }
        v19 = v17(v16, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v107);
        v15 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v19,
            (int)bIgnoreCase);
        }
        else
        {
          v21 = v107.lpVtbl;
          v107.lpVtbl = 0;
          v112 = v21;
        }
      }
      v22 = v107.lpVtbl;
      if ( v107.lpVtbl )
      {
        v107.lpVtbl = 0;
        (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v22->QueryInterface + 2))(v22);
      }
      v23 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
      if ( *(_QWORD *)v108 )
      {
        *(_QWORD *)v108 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IXMLDOMNodeList *)))(*v23)[2])(v23);
      }
      if ( v15 < 0 )
        goto LABEL_94;
      *(_OWORD *)lpString1 = 0;
      v24 = 0;
      v116 = 0;
      v25 = v112;
      v109 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      pvarg.vt = 0;
      *(_OWORD *)v123 = 0;
      LODWORD(v124) = 0;
      if ( !v112 )
      {
        v29 = -2147024809;
LABEL_49:
        v43 = (WCHAR *)lpString1[1];
LABEL_50:
        v41 = 0;
        goto LABEL_51;
      }
      *(_QWORD *)v108 = 0;
      v107.lpVtbl = 0;
      SysFreeString(0);
      v26 = 0;
      v119 = 0;
      v27 = 0x7FFFFFFF;
      v28 = L"@*[local-name()='Category']";
      do
      {
        if ( !*v28 )
          break;
        ++v28;
        --v27;
      }
      while ( v27 );
      v29 = -2147024809;
      if ( v27 )
      {
        if ( (unsigned int)(0x7FFFFFFF - v27) > 0x3FFFFFFF )
        {
          v29 = -2147024809;
        }
        else
        {
          v26 = SysAllocStringLen(L"@*[local-name()='Category']", 0x7FFFFFFF - (int)v27);
          v119 = v26;
          if ( v26 )
            v29 = 0;
          else
            v29 = -2147024882;
        }
      }
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
      }
      else
      {
        v30 = (__int64 (__fastcall *)(struct IXMLDOMNodeListVtbl *, OLECHAR *, int *))*((_QWORD *)v25->QueryInterface
                                                                                      + 37);
        v31 = *(_QWORD **)v108;
        if ( *(_QWORD *)v108 )
        {
          *(_QWORD *)v108 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v31 + 16LL))(v31, *v31);
        }
        v32 = v30(v25, v26, v108);
        v29 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4D,
            (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
            (const char *)(unsigned int)v32,
            (int)bIgnoreCase);
        }
        else
        {
          v33 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
          if ( *(_QWORD *)v108 )
          {
            v34 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
            v35 = v107.lpVtbl;
            if ( v107.lpVtbl )
            {
              v107.lpVtbl = 0;
              (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *, HRESULT (__stdcall *)(IXMLDOMNodeList *, const IID *const, void **)))v35->QueryInterface
               + 2))(
                v35,
                v35->QueryInterface);
            }
            v36 = v34(v33, &GUID_2933bf85_7b36_11d2_b20e_00c04f983e60, &v107);
            v29 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x53,
                (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                (const char *)(unsigned int)v36,
                (int)bIgnoreCase);
            }
            else
            {
              v37 = v107.lpVtbl;
              v107.lpVtbl = 0;
              v109 = v37;
            }
          }
          else
          {
            v109 = 0;
          }
        }
      }
      SysFreeString(v26);
      v38 = v107.lpVtbl;
      if ( v107.lpVtbl )
      {
        v107.lpVtbl = 0;
        (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v38->QueryInterface + 2))(v38);
      }
      v39 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
      if ( *(_QWORD *)v108 )
      {
        *(_QWORD *)v108 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IXMLDOMNodeList *)))(*v39)[2])(v39);
      }
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2A0,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        goto LABEL_49;
      }
      if ( !v109 )
      {
        v48 = _mm_cvtsi128_si32((__m128i)0LL);
        v49 = 2LL * v48 == 0;
        v50 = 2LL * v48;
        v43 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v51 = v43;
        if ( !v49 )
        {
          do
          {
            *(_BYTE *)v51 = 0;
            v51 = (WCHAR *)((char *)v51 + 1);
            --v50;
          }
          while ( v50 );
        }
        goto LABEL_50;
      }
      v40 = (*((__int64 (__fastcall **)(struct IXMLDOMNodeListVtbl *, VARIANTARG *))v109->QueryInterface + 44))(
              v109,
              &pvarg);
      v29 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2A4,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v40,
          (int)bIgnoreCase);
        goto LABEL_49;
      }
      v41 = 0;
      bstrVal = pvarg.bstrVal;
      if ( !pvarg.llVal )
      {
        v43 = (WCHAR *)lpString1[1];
        v4 = v121;
        goto LABEL_51;
      }
      v52 = 1073741822;
      v53 = pvarg.bstrVal;
      do
      {
        if ( !*v53 )
          break;
        ++v53;
        --v52;
      }
      while ( v52 );
      v29 = -2147024809;
      if ( v52 )
      {
        v29 = 0;
        v54 = 1073741822 - v52;
      }
      else
      {
        v54 = 0;
      }
      if ( !v52 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        v43 = (WCHAR *)lpString1[1];
        goto LABEL_87;
      }
      if ( v54 > 0x7FFFFFFF )
        v29 = -2147024362;
      else
        v29 = 0;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22F,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        v43 = (WCHAR *)lpString1[1];
        goto LABEL_87;
      }
      if ( !v54 )
      {
        v43 = (WCHAR *)lpString1[1];
LABEL_80:
        v55 = 0;
        goto LABEL_81;
      }
      if ( v54 > 0x20 )
      {
        j = v54;
      }
      else
      {
        for ( j = 8; j < v54; j *= 2 )
          ;
      }
      if ( j > 0x3FFFFFFF )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x80070503LL,
          (int)bIgnoreCase);
        v29 = -2147023613;
        v43 = (WCHAR *)lpString1[1];
        goto LABEL_177;
      }
      if ( !j )
        break;
      v74 = j + 1;
      v75 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v43 = v75;
      v76 = 2LL * (unsigned int)v74;
      if ( !is_mul_ok((unsigned int)v74, 2u) )
        v76 = -1;
      v77 = (WCHAR *)operator new[](v76, (const struct std::nothrow_t *)&std::nothrow);
      v78 = v77;
      if ( v77 )
      {
        v103 = memcpy_s(v77, 2 * v74, v75, 0);
        if ( !v103 )
        {
          operator delete(v75, v102);
          v43 = v78;
          i = v113;
          v24 = j + 1;
          v116 = j + 1;
          lpString1[1] = v43;
          if ( LODWORD(lpString1[0]) > j )
          {
            LODWORD(lpString1[0]) = j;
            v43[j] = 0;
          }
          else if ( LODWORD(lpString1[0]) < j && !LODWORD(lpString1[0]) )
          {
            *v43 = 0;
          }
LABEL_176:
          v29 = 0;
          goto LABEL_177;
        }
        operator delete(v78, v102);
        LODWORD(v106) = v103;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x198,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x80070057LL,
          (int)"0x%08lx",
          v106);
        v29 = -2147024809;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x8007000ELL,
          (int)bIgnoreCase);
        v29 = -2147024882;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v29,
        bIgnoreCasea);
      v24 = v116;
      i = v113;
LABEL_177:
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        goto LABEL_87;
      }
      if ( !v24 )
        goto LABEL_80;
      v55 = v24 - 1;
LABEL_81:
      if ( v54 <= v55 )
        goto LABEL_82;
      v98 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)lpString1, v54);
      v29 = v98;
      if ( v98 >= 0 )
      {
        v43 = (WCHAR *)lpString1[1];
LABEL_82:
        LODWORD(lpString1[0]) = v54;
        if ( v54 )
          v43[v54] = 0;
        v29 = 0;
        goto LABEL_85;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v98,
        (int)bIgnoreCase);
      v43 = (WCHAR *)lpString1[1];
LABEL_85:
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
      }
      else
      {
        memcpy_0(v43, bstrVal, 2 * v54);
        v29 = 0;
      }
LABEL_87:
      if ( v29 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2AB,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        v4 = v121;
        goto LABEL_50;
      }
      v41 = 1;
      v4 = v121;
LABEL_51:
      v44 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v44 )
        operator delete(v44, v20);
      VariantClear(&pvarg);
      v46 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v46->QueryInterface + 2))(v46);
      }
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x286,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
        if ( v43 )
          operator delete(v43, v94);
        v95 = v112;
        if ( v112 )
        {
          v112 = 0;
          (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v95->QueryInterface + 2))(v95);
        }
        v96 = v110;
        if ( v110 )
        {
          v110 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        }
        v97 = v111;
        if ( v111 )
        {
          v111 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v97 + 16LL))(v97, *v97);
        }
        return (unsigned int)v29;
      }
      if ( v41 && CompareStringOrdinal(v43, -1, L"windows.appExecutionAlias", -1, 1) == 2 )
      {
        *(_QWORD *)v108 = 0;
        v57 = v112;
        if ( v112 )
        {
          v109 = 0;
          *(_QWORD *)v108 = 0;
          SysFreeString(0);
          v58 = 0;
          v119 = 0;
          v59 = 0x7FFFFFFF;
          v60 = L"*[local-name()='AppExecutionAlias']/*[local-name()='ExecutionAlias']";
          do
          {
            if ( !*v60 )
              break;
            ++v60;
            --v59;
          }
          while ( v59 );
          v63 = -2147024809;
          if ( v59 )
          {
            if ( (unsigned int)(0x7FFFFFFF - v59) > 0x3FFFFFFF )
            {
              v63 = -2147024809;
            }
            else
            {
              v58 = SysAllocStringLen(
                      L"*[local-name()='AppExecutionAlias']/*[local-name()='ExecutionAlias']",
                      0x7FFFFFFF - (int)v59);
              v119 = v58;
              if ( v58 )
                v63 = 0;
              else
                v63 = -2147024882;
            }
          }
          if ( (v63 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xD3,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)v63,
              (int)bIgnoreCase);
            SysFreeString(v58);
            v80 = v109;
            if ( v109 )
            {
              v109 = 0;
              (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v80->QueryInterface + 2))(v80);
            }
          }
          else
          {
            v64 = (__int64 (__fastcall *)(struct IXMLDOMNodeListVtbl *, OLECHAR *, struct IXMLDOMNodeListVtbl **))*((_QWORD *)v57->QueryInterface + 36);
            v65 = v109;
            if ( v109 )
            {
              v109 = 0;
              (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *, HRESULT (__stdcall *)(IXMLDOMNodeList *, const IID *const, void **)))v65->QueryInterface
               + 2))(
                v65,
                v65->QueryInterface);
            }
            v66 = v64(v57, v58, &v109);
            v63 = v66;
            if ( v66 >= 0 )
            {
              v67 = v109;
              if ( v109 )
              {
                v109 = 0;
                *(_QWORD *)v108 = v67;
              }
              SysFreeString(v58);
              v68 = v109;
              if ( v109 )
              {
                v109 = 0;
                (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v68->QueryInterface + 2))(v68);
              }
              v118 = 0;
              v69 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v108 + 64LL))(*(_QWORD *)v108, &v118);
              v70 = v69;
              if ( v69 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x292,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
                  (const char *)(unsigned int)v69,
                  (int)bIgnoreCase);
                Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v108);
                if ( !v43 )
                {
LABEL_193:
                  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v112);
                  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v110);
                  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v111);
                  return v70;
                }
              }
              else
              {
                for ( k = 0; ; ++k )
                {
                  if ( (int)k >= v118 )
                    goto LABEL_120;
                  v107.lpVtbl = 0;
                  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v107);
                  ElementFromNodeList = Common::Xml::GetElementFromNodeList((Common::Xml *)k, v108[0], &v107, v81);
                  v70 = ElementFromNodeList;
                  if ( ElementFromNodeList < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x297,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
                      (const char *)(unsigned int)ElementFromNodeList,
                      (int)bIgnoreCase);
                    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v107);
                    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v108);
                    if ( !v43 )
                      goto LABEL_193;
                    goto LABEL_192;
                  }
                  LODWORD(v109) = 0;
                  memset(&pvarg, 0, 20);
                  AttributeValueStringByLocalName = Common::Xml::GetAttributeValueStringByLocalName(
                                                      (Common::Xml *)v107.lpVtbl,
                                                      (struct IXMLDOMElement *)&stru_1801C68A0,
                                                      &pvarg.vt,
                                                      (struct Common::StringBuffer *)&v109,
                                                      bIgnoreCase);
                  v70 = AttributeValueStringByLocalName;
                  if ( AttributeValueStringByLocalName < 0 )
                    break;
                  if ( (_DWORD)v109 )
                  {
                    v85 = -1;
                    do
                      ++v85;
                    while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v4 + 20) + 152LL) + 2 * v85) );
                    *(_OWORD *)v123 = 0;
                    v124 = 0;
                    v125 = 0;
                    std::wstring::_Construct<1,unsigned short const *>(v123);
                    v87 = v114 | 3;
                    v88 = (std::filesystem *)v123;
                    if ( v125 > 7 )
                      v88 = v123[0];
                    v89 = (const unsigned __int16 *)((char *)v88 + 2 * v124);
                    v122[0] = std::filesystem::_Find_filename(v88, v89, v86);
                    v122[1] = ((__int64)v89 - v122[0]) >> 1;
                    std::wstring::wstring(String1, v122);
                    v114 = v87 | 0x1C;
                    v90 = pvarg.bstrVal;
                    llVal = pvarg.llVal;
                    v92 = *(WCHAR **)String1;
                    if ( v127 <= 7 )
                      v92 = String1;
                    if ( CompareStringOrdinal(v92, -1, pvarg.bstrVal, -1, 1) == 2 )
                    {
                      std::wstring::_Tidy_deallocate(String1);
                      *((_BYTE *)v4 + 964) = 1;
                      std::wstring::_Tidy_deallocate(v123);
                      if ( llVal )
                        operator delete(v90, v45);
                      v93 = v107.lpVtbl;
                      if ( v107.lpVtbl )
                      {
                        v107.lpVtbl = 0;
                        (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v93->QueryInterface + 2))(v93);
                      }
LABEL_120:
                      v72 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMNodeList *))v108;
                      if ( *(_QWORD *)v108 )
                      {
                        *(_QWORD *)v108 = 0;
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IXMLDOMNodeList *)))(*v72)[2])(v72);
                      }
                      i = v113;
                      goto LABEL_58;
                    }
                    std::wstring::_Tidy_deallocate(String1);
                    std::wstring::_Tidy_deallocate(v123);
                  }
                  else
                  {
                    v90 = pvarg.bstrVal;
                  }
                  if ( v90 )
                    operator delete(v90, v84);
                  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v107);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x29C,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
                  (const char *)(unsigned int)AttributeValueStringByLocalName,
                  (int)bIgnoreCase);
                if ( pvarg.llVal )
                  operator delete(pvarg.bstrVal, v100);
                Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v107);
                Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v108);
                if ( !v43 )
                  goto LABEL_193;
              }
LABEL_192:
              operator delete(v43, v99);
              goto LABEL_193;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xD7,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)(unsigned int)v66,
              (int)bIgnoreCase);
            SysFreeString(v58);
            Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v109);
          }
        }
        else
        {
          v63 = -2147024809;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
          (const char *)v63,
          (int)bIgnoreCase);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v108);
        if ( v43 )
          operator delete(v43, v79);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v110);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v111);
        return v63;
      }
LABEL_58:
      if ( v43 )
        operator delete(v43, v45);
      v47 = v112;
      if ( v112 )
      {
        v112 = 0;
        (*((void (__fastcall **)(struct IXMLDOMNodeListVtbl *))v47->QueryInterface + 2))(v47);
      }
    }
    v101 = (WCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v43 = v101;
    if ( v101 )
    {
      operator delete(v101, v20);
      v43 = 0;
      lpString1[1] = 0;
      LODWORD(lpString1[0]) = 0;
    }
    v24 = 0;
    v116 = 0;
    goto LABEL_176;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2AD,
                           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180011580  mov     rax, rsp
0x180011583  mov     [rax+10h], rbx
0x180011587  mov     [rax+18h], rsi
0x18001158b  push    rdi
0x18001158c  push    r12
0x18001158e  push    r13
0x180011590  push    r14
0x180011592  push    r15
0x180011594  sub     rsp, 130h
0x18001159b  movaps  xmmword ptr [rax-38h], xmm6
0x18001159f  movaps  xmmword ptr [rax-48h], xmm7
0x1800115a3  mov     rax, cs:__security_cookie
0x1800115aa  xor     rax, rsp
0x1800115ad  mov     [rsp+158h+var_58], rax
0x1800115b5  mov     r13, rcx
0x1800115b8  mov     [rsp+158h+var_B0], rcx
0x1800115c0  xor     r14d, r14d
0x1800115c3  mov     [rsp+158h+var_F4], r14d
0x1800115c8  mov     rax, [rcx+0A0h]
0x1800115cf  test    rax, rax
0x1800115d2  jz      loc_1800122F7
0x1800115d8  add     rax, 90h
0x1800115de  jz      loc_1800122F7
0x1800115e4  cmp     [rax], r14d
0x1800115e7  jz      loc_1800122F7
0x1800115ed  mov     [rsp+158h+var_108], r14
0x1800115f2  mov     rcx, [rcx+10h]
0x1800115f6  mov     rax, [rcx]
0x1800115f9  lea     rdx, [rsp+158h+var_108]
0x1800115fe  mov     rax, [rax+58h]
0x180011602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011607  mov     ebx, eax
0x180011609  test    eax, eax
0x18001160b  js      loc_180012521
0x180011611  mov     [rsp+158h+var_110], r14
0x180011616  mov     rcx, [rsp+158h+var_108]
0x18001161b  mov     rax, [rcx]
0x18001161e  lea     rdx, [rsp+158h+var_110]
0x180011623  mov     rax, [rax+60h]
0x180011627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001162c  mov     ebx, eax
0x18001162e  test    eax, eax
0x180011630  js      loc_18001254F
0x180011636  mov     [rsp+158h+var_D8], r14d
0x18001163e  mov     rcx, [rsp+158h+var_110]
0x180011643  mov     rax, [rcx]
0x180011646  lea     rdx, [rsp+158h+var_D8]
0x18001164e  mov     rax, [rax+40h]
0x180011652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011657  mov     ebx, eax
0x180011659  test    eax, eax
0x18001165b  js      loc_180012588
0x180011661  mov     r12d, r14d
0x180011664  mov     [rsp+158h+var_F8], r12d
0x180011669  cmp     r12d, [rsp+158h+var_D8]
0x180011671  jge     loc_180011D28
0x180011677  mov     [rsp+158h+var_100], r14
0x18001167c  mov     rcx, [rsp+158h+var_110]
0x180011681  test    rcx, rcx
0x180011684  jz      loc_180011C56
0x18001168a  mov     qword ptr [rsp+158h+var_120], r14
0x18001168f  mov     [rsp+158h+var_128.lpVtbl], r14
0x180011694  mov     rax, [rcx]
0x180011697  lea     r8, [rsp+158h+var_120]
0x18001169c  mov     edx, r12d
0x18001169f  mov     rax, [rax+38h]
0x1800116a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a8  mov     ebx, eax
0x1800116aa  mov     rcx, [rsp+158h]; this
0x1800116b2  test    eax, eax
0x1800116b4  js      loc_180011AE0
0x1800116ba  mov     rbx, qword ptr [rsp+158h+var_120]
0x1800116bf  mov     rax, [rbx]
0x1800116c2  mov     rdi, [rax]
0x1800116c5  mov     rcx, [rsp+158h+var_128.lpVtbl]
0x1800116ca  test    rcx, rcx
0x1800116cd  jz      short loc_1800116E1
0x1800116cf  mov     [rsp+158h+var_128.lpVtbl], r14
0x1800116d4  mov     rdx, [rcx]
0x1800116d7  mov     rax, [rdx+10h]
0x1800116db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116e0  nop
0x1800116e1  lea     r8, [rsp+158h+var_128]
0x1800116e6  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800116ed  mov     rcx, rbx
0x1800116f0  mov     rax, rdi
0x1800116f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116f8  mov     ebx, eax
0x1800116fa  mov     rcx, [rsp+158h]; this
0x180011702  test    eax, eax
0x180011704  js      loc_180011AF9
0x18001170a  mov     rax, [rsp+158h+var_128.lpVtbl]
0x18001170f  mov     [rsp+158h+var_128.lpVtbl], r14
0x180011714  mov     [rsp+158h+var_100], rax
0x180011719  mov     rcx, [rsp+158h+var_128.lpVtbl]
0x18001171e  test    rcx, rcx
0x180011721  jz      short loc_180011735
0x180011723  mov     [rsp+158h+var_128.lpVtbl], r14
0x180011728  mov     rax, [rcx]
0x18001172b  mov     rax, [rax+10h]
0x18001172f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011734  nop
0x180011735  mov     rcx, qword ptr [rsp+158h+var_120]
0x18001173a  test    rcx, rcx
0x18001173d  jz      short loc_180011751
0x18001173f  mov     qword ptr [rsp+158h+var_120], r14
0x180011744  mov     rax, [rcx]
0x180011747  mov     rax, [rax+10h]
0x18001174b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011750  nop
0x180011751  test    ebx, ebx
0x180011753  js      loc_180011C5B
0x180011759  xorps   xmm7, xmm7
0x18001175c  movups  xmmword ptr [rsp+158h+lpString1], xmm7
0x180011761  mov     r15d, r14d
0x180011764  mov     [rsp+158h+var_E0], r14d
0x180011769  mov     r14, [rsp+158h+var_100]
0x18001176e  xor     ebx, ebx
0x180011770  mov     [rsp+158h+var_118], rbx
0x180011775  xorps   xmm0, xmm0
0x180011778  xor     eax, eax
0x18001177a  movups  xmmword ptr [rsp+158h+pvarg], xmm0
0x180011782  mov     qword ptr [rsp+158h+pvarg+10h], rax
0x18001178a  mov     word ptr [rsp+158h+pvarg], bx
0x180011792  xorps   xmm6, xmm6
0x180011795  movups  xmmword ptr [rsp+158h+var_98], xmm6
0x18001179d  mov     dword ptr [rsp+158h+var_88], ebx
0x1800117a4  test    r14, r14
0x1800117a7  jz      loc_1800126D2
0x1800117ad  mov     qword ptr [rsp+158h+var_120], rbx
0x1800117b2  mov     [rsp+158h+var_128.lpVtbl], rbx
0x1800117b7  xor     ecx, ecx; bstrString
0x1800117b9  call    cs:__imp_SysFreeString
0x1800117c0  nop     dword ptr [rax+rax+00h]
0x1800117c5  mov     edi, ebx
0x1800117c7  mov     [rsp+158h+var_D0], rbx
0x1800117cf  mov     ecx, 7FFFFFFFh
0x1800117d4  lea     rax, aLocalNameCateg; "@*[local-name()='Category']"
0x1800117db  nop     dword ptr [rax+rax+00h]
0x1800117e0  cmp     [rax], bx
0x1800117e3  jz      short loc_1800117EF
0x1800117e5  add     rax, 2
0x1800117e9  sub     rcx, 1
0x1800117ed  jnz     short loc_1800117E0
0x1800117ef  mov     esi, 80070057h
0x1800117f4  test    rcx, rcx
0x1800117f7  cmovnz  esi, ebx
0x1800117fa  jz      short loc_18001183B
0x1800117fc  mov     edx, 7FFFFFFFh
0x180011801  sub     edx, ecx; ui
0x180011803  cmp     edx, 3FFFFFFFh
0x180011809  ja      loc_180012232
0x18001180f  lea     rcx, aLocalNameCateg; "@*[local-name()='Category']"
0x180011816  call    cs:__imp_SysAllocStringLen
0x18001181d  nop     dword ptr [rax+rax+00h]
0x180011822  mov     rdi, rax
0x180011825  mov     [rsp+158h+var_D0], rax
0x18001182d  test    rax, rax
0x180011830  jnz     loc_1800125C1
0x180011836  mov     esi, 8007000Eh
0x18001183b  mov     rcx, [rsp+158h]; this
0x180011843  test    esi, esi
0x180011845  js      loc_18001190F
0x18001184b  mov     rax, [r14]
0x18001184e  mov     rbx, [rax+128h]
0x180011855  mov     rcx, qword ptr [rsp+158h+var_120]
0x18001185a  test    rcx, rcx
0x18001185d  jz      short loc_180011875
0x18001185f  mov     qword ptr [rsp+158h+var_120], 0
0x180011868  mov     rdx, [rcx]
0x18001186b  mov     rax, [rdx+10h]
0x18001186f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011874  nop
0x180011875  lea     r8, [rsp+158h+var_120]
0x18001187a  mov     rdx, rdi
0x18001187d  mov     rcx, r14
0x180011880  mov     rax, rbx
0x180011883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011888  mov     esi, eax
0x18001188a  mov     rcx, [rsp+158h]; this
0x180011892  test    eax, eax
0x180011894  js      loc_180011BE4
0x18001189a  mov     rbx, qword ptr [rsp+158h+var_120]
0x18001189f  test    rbx, rbx
0x1800118a2  jz      loc_180011AD3
0x1800118a8  mov     rax, [rbx]
0x1800118ab  mov     rsi, [rax]
0x1800118ae  mov     rcx, [rsp+158h+var_128.lpVtbl]
0x1800118b3  test    rcx, rcx
0x1800118b6  jz      short loc_1800118CE
0x1800118b8  mov     [rsp+158h+var_128.lpVtbl], 0
0x1800118c1  mov     rdx, [rcx]
0x1800118c4  mov     rax, [rdx+10h]
0x1800118c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118cd  nop
0x1800118ce  lea     r8, [rsp+158h+var_128]
0x1800118d3  lea     rdx, _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60
0x1800118da  mov     rcx, rbx
0x1800118dd  mov     rax, rsi
0x1800118e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e5  mov     esi, eax
0x1800118e7  mov     rcx, [rsp+158h]; this
0x1800118ef  test    eax, eax
0x1800118f1  js      loc_180011C19
0x1800118f7  mov     rax, [rsp+158h+var_128.lpVtbl]
0x1800118fc  mov     [rsp+158h+var_128.lpVtbl], 0
0x180011905  mov     [rsp+158h+var_118], rax
0x18001190a  xor     r14d, r14d
0x18001190d  jmp     short loc_180011926
0x18001190f  mov     r9d, esi; char *
0x180011912  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180011919  mov     edx, 49h ; 'I'; void *
0x18001191e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011923  xor     r14d, r14d
0x180011926  mov     rcx, rdi; bstrString
0x180011929  call    cs:__imp_SysFreeString
0x180011930  nop     dword ptr [rax+rax+00h]
0x180011935  nop
0x180011936  mov     rcx, [rsp+158h+var_128.lpVtbl]
0x18001193b  test    rcx, rcx
0x18001193e  jz      short loc_180011952
0x180011940  mov     [rsp+158h+var_128.lpVtbl], r14
0x180011945  mov     rax, [rcx]
0x180011948  mov     rax, [rax+10h]
0x18001194c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011951  nop
0x180011952  mov     rcx, qword ptr [rsp+158h+var_120]
0x180011957  test    rcx, rcx
0x18001195a  jz      short loc_18001196E
0x18001195c  mov     qword ptr [rsp+158h+var_120], r14
0x180011961  mov     rax, [rcx]
0x180011964  mov     rax, [rax+10h]
0x180011968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196d  nop
0x18001196e  mov     rcx, [rsp+158h]; this
0x180011976  test    esi, esi
0x180011978  js      short loc_1800119D4
0x18001197a  mov     rcx, [rsp+158h+var_118]
0x18001197f  test    rcx, rcx
0x180011982  jz      loc_180011AA7
0x180011988  mov     rax, [rcx]
0x18001198b  lea     rdx, [rsp+158h+pvarg]
0x180011993  mov     rax, [rax+160h]
0x18001199a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001199f  mov     esi, eax
0x1800119a1  mov     rcx, [rsp+158h]; this
0x1800119a9  test    eax, eax
0x1800119ab  js      loc_180011C00
0x1800119b1  mov     ebx, r14d
0x1800119b4  mov     r13, qword ptr [rsp+158h+pvarg+8]
0x1800119bc  test    r13, r13
0x1800119bf  jnz     loc_180011B12
0x1800119c5  mov     rdi, [rsp+158h+lpString1+8]
0x1800119ca  mov     r13, [rsp+158h+var_B0]
0x1800119d2  jmp     short loc_1800119F0
0x1800119d4  mov     r9d, esi; char *
0x1800119d7  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800119de  mov     edx, 2A0h; void *
0x1800119e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800119e8  mov     rdi, [rsp+158h+lpString1+8]
0x1800119ed  mov     ebx, r14d
0x1800119f0  psrldq  xmm6, 8
0x1800119f5  movq    rcx, xmm6; void *
0x1800119fa  test    rcx, rcx
0x1800119fd  jz      short loc_180011A05
0x1800119ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011a04  nop
0x180011a05  lea     rcx, [rsp+158h+pvarg]; pvarg
0x180011a0d  call    cs:__imp_VariantClear
0x180011a14  nop     dword ptr [rax+rax+00h]
0x180011a19  nop
0x180011a1a  mov     rcx, [rsp+158h+var_118]
0x180011a1f  test    rcx, rcx
0x180011a22  jz      short loc_180011A36
0x180011a24  mov     [rsp+158h+var_118], r14
0x180011a29  mov     rax, [rcx]
0x180011a2c  mov     rax, [rax+10h]
0x180011a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a35  nop
0x180011a36  test    esi, esi
0x180011a38  js      loc_180012271
0x180011a3e  test    ebx, ebx
0x180011a40  jz      short loc_180011A75
0x180011a42  mov     [rsp+158h+bIgnoreCase], 1; int
0x180011a4a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180011a51  mov     r9d, esi; cchCount2
0x180011a54  lea     r8, aWindowsAppexec; "windows.appExecutionAlias"
0x180011a5b  mov     edx, esi; cchCount1
0x180011a5d  mov     rcx, rdi; lpString1
0x180011a60  call    cs:__imp_CompareStringOrdinal
0x180011a67  nop     dword ptr [rax+rax+00h]
0x180011a6c  add     eax, 0FFFFFFFEh
0x180011a6f  jz      loc_180011CD2
0x180011a75  test    rdi, rdi
0x180011a78  jz      short loc_180011A83
0x180011a7a  mov     rcx, rdi; void *
0x180011a7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011a82  nop
0x180011a83  mov     rcx, [rsp+158h+var_100]
0x180011a88  test    rcx, rcx
  ... truncated ...
```

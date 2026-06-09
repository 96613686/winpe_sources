# OSIntegration::Tools::MoCOMHelper::ApplicationExtensionSupportsMultipleInstances(IXMLDOMElement *,IXMLDOMElement *,bool *)

- ea: `0x180006c98`
- end: `0x180007539`
- name: `?ApplicationExtensionSupportsMultipleInstances@MoCOMHelper@Tools@OSIntegration@@IEAAJPEAUIXMLDOMElement@@0PEA_N@Z`
- size: `2209`
- prototype: `__int64 __fastcall(OSIntegration::Tools::MoCOMHelper *__hidden this, struct IXMLDOMElement *, struct IXMLDOMElement *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dd2dc`

## callees

- `0x180006970`
- `0x180006c98`
- `0x180009dc0`
- `0x180011020`
- `0x180012da0`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800af1bc`
- `0x180180144`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006cda`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006cf9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800073a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007483`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006cda`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006cf9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800073a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007483`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006dc1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000719a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006dc1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000719a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d53`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e45`
- `OLEAUT32!__imp_SysFreeString` at `0x18000704c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007120`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d53`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e45`
- `OLEAUT32!__imp_SysFreeString` at `0x18000704c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007120`
- `OLEAUT32!__imp_VariantClear` at `0x180006eed`
- `OLEAUT32!__imp_VariantClear` at `0x180006eed`

## string_xrefs

- `0x180006ccf`: `Windows.BackgroundTasks`
- `0x180006cee`: `Windows.AppService`
- `0x18000713a`: `./*[local-name()='BackgroundTasks']`
- `0x180007193`: `./*[local-name()='BackgroundTasks']`
- `0x180006f95`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180006fae`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18000703c`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180007272`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x18000709c`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180007298`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180007303`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180007320`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800073f7`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18000742e`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800074e4`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800074b5`: `./*[local-name()='AppService']`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::ApplicationExtensionSupportsMultipleInstances(
        OSIntegration::Tools::MoCOMHelper *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        bool *a4)
{
  const struct std::nothrow_t *llVal; // rdx
  bool v9; // r15
  OLECHAR *v10; // rbx
  __int64 v11; // rdx
  const OLECHAR *v12; // rax
  signed int v13; // esi
  __int64 v14; // r8
  wil::details::in1diag3 *v15; // rcx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMElement *, BSTR, IXMLDOMNode **); // rsi
  struct IXMLDOMElementVtbl *lpVtbl; // rcx
  int v18; // eax
  struct IXMLDOMElementVtbl *v19; // rdi
  int *v20; // rcx
  struct IXMLDOMElementVtbl *v21; // rcx
  wil::details::in1diag3 *v22; // rcx
  int v23; // eax
  int v24; // edi
  Common::Xml *v25; // rbx
  void *v26; // rcx
  const unsigned __int16 *v27; // rdx
  int *v28; // rcx
  bool v29; // si
  unsigned int v31; // ecx
  bool v32; // zf
  __int64 v33; // rcx
  Common::Xml *v34; // rax
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  unsigned __int64 v37; // r9
  __int64 v38; // rdx
  __int64 (__fastcall *v39)(struct IXMLDOMElementVtbl *, GUID *, int **); // rsi
  int v40; // eax
  int *v41; // rax
  OLECHAR *v42; // rbx
  unsigned int v43; // r14d
  wil::details::in1diag3 *v44; // rcx
  __int64 v45; // r9
  __int64 v46; // rdx
  int *v47; // rcx
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rcx
  struct IXMLDOMElementVtbl *v49; // rcx
  int v50; // eax
  __int64 v51; // rdx
  const OLECHAR *v52; // rax
  __int64 v53; // r8
  HRESULT (__stdcall *v54)(IXMLDOMElement *, BSTR, IXMLDOMNode **); // rdi
  int v55; // eax
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v57)(_QWORD, GUID *, int **); // rsi
  int v58; // eax
  struct IXMLDOMElementVtbl *v59; // rax
  const struct std::nothrow_t *v60; // rdx
  struct IXMLDOMElementVtbl *v61; // rbx
  __int64 (__fastcall *v62)(struct IXMLDOMElementVtbl *, int **); // rdi
  int v63; // eax
  const struct std::nothrow_t *v64; // rdx
  int AttributeValueStringFromElement; // eax
  const struct std::nothrow_t *v66; // rdx
  Common::Xml *v67; // rbx
  bool v68; // cl
  const struct std::nothrow_t *v69; // rdx
  int v70; // eax
  const struct std::nothrow_t *v71; // rdx
  Common::Xml *v72; // rbx
  bool v73; // cl
  struct IXMLDOMElement **v74; // r9
  int XMLElementFromQuery; // eax
  __int64 v76; // r9
  __int64 v77; // rdx
  int *v78; // [rsp+28h] [rbp-59h] BYREF
  Common::Xml *v79[2]; // [rsp+30h] [rbp-51h] BYREF
  int v80; // [rsp+40h] [rbp-41h]
  __int64 (__fastcall ***v81)(_QWORD, GUID *, int **); // [rsp+48h] [rbp-39h] BYREF
  OLECHAR *v82; // [rsp+50h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-29h] BYREF
  __int128 v84; // [rsp+70h] [rbp-11h]
  int v85; // [rsp+80h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  int *v87; // [rsp+E8h] [rbp+67h] BYREF
  struct IXMLDOMElement v88; // [rsp+100h] [rbp+7Fh] BYREF

  *a4 = 0;
  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"Windows.BackgroundTasks") )
  {
    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"Windows.AppService") )
    {
      *(_OWORD *)v79 = 0;
      v80 = 0;
      v78 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      pvarg.vt = 0;
      v84 = 0;
      v85 = 0;
      v9 = 1;
      if ( !a3 )
      {
        v13 = -2147024809;
        goto LABEL_44;
      }
      v88.lpVtbl = 0;
      v87 = 0;
      SysFreeString(0);
      v10 = 0;
      v82 = 0;
      v11 = 0x7FFFFFFF;
      v12 = L"@*[local-name()='SupportsMultipleInstances']";
      do
      {
        if ( !*v12 )
          break;
        ++v12;
        --v11;
      }
      while ( v11 );
      v13 = v11 == 0 ? 0x80070057 : 0;
      v14 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
      if ( v11 )
      {
        if ( (unsigned int)v14 > 0x3FFFFFFF )
        {
          v13 = -2147024809;
        }
        else
        {
          v10 = SysAllocStringLen(L"@*[local-name()='SupportsMultipleInstances']", v14);
          v82 = v10;
          v13 = v10 == 0 ? 0x8007000E : 0;
        }
      }
      v15 = retaddr;
      if ( v13 < 0 )
      {
        v35 = (unsigned int)v13;
        v36 = 73;
      }
      else
      {
        selectSingleNode = a3->lpVtbl->selectSingleNode;
        lpVtbl = v88.lpVtbl;
        if ( v88.lpVtbl )
        {
          v88.lpVtbl = 0;
          (*((void (__fastcall **)(struct IXMLDOMElementVtbl *, HRESULT (__stdcall *)(IXMLDOMElement *, const IID *const, void **), __int64))lpVtbl->QueryInterface
           + 2))(
            lpVtbl,
            lpVtbl->QueryInterface,
            v14);
        }
        v18 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, struct IXMLDOMElement *))selectSingleNode)(
                a3,
                v10,
                &v88);
        v13 = v18;
        v15 = retaddr;
        if ( v18 < 0 )
        {
          v35 = (unsigned int)v18;
          v36 = 77;
        }
        else
        {
          v19 = v88.lpVtbl;
          if ( !v88.lpVtbl )
          {
            v78 = 0;
LABEL_16:
            SysFreeString(v10);
            v20 = v87;
            if ( v87 )
            {
              v87 = 0;
              (*(void (__fastcall **)(int *))(*(_QWORD *)v20 + 16LL))(v20);
            }
            v21 = v88.lpVtbl;
            if ( v88.lpVtbl )
            {
              v88.lpVtbl = 0;
              (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v21->QueryInterface + 2))(v21);
            }
            v22 = retaddr;
            if ( v13 < 0 )
            {
              v37 = (unsigned int)v13;
              v38 = 672;
            }
            else
            {
              if ( !v78 )
              {
                v31 = _mm_cvtsi128_si32((__m128i)0LL);
                v32 = 2LL * v31 == 0;
                v33 = 2LL * v31;
                v25 = (Common::Xml *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
                v34 = v25;
                if ( !v32 )
                {
                  do
                  {
                    *(_BYTE *)v34 = 0;
                    v34 = (Common::Xml *)((char *)v34 + 1);
                    --v33;
                  }
                  while ( v33 );
                }
                v24 = 0;
                goto LABEL_25;
              }
              v23 = (*(__int64 (__fastcall **)(int *, VARIANTARG *))(*(_QWORD *)v78 + 352LL))(v78, &pvarg);
              v13 = v23;
              v22 = retaddr;
              if ( v23 < 0 )
              {
                v37 = (unsigned int)v23;
                v38 = 676;
              }
              else
              {
                v24 = 0;
                llVal = (const struct std::nothrow_t *)pvarg.llVal;
                if ( !pvarg.llVal )
                {
LABEL_24:
                  v25 = v79[1];
LABEL_25:
                  v26 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
                  if ( v26 )
                    operator delete(v26, llVal);
                  VariantClear(&pvarg);
                  v28 = v78;
                  if ( v78 )
                  {
                    v78 = 0;
                    (*(void (__fastcall **)(int *))(*(_QWORD *)v28 + 16LL))(v28);
                  }
                  if ( v13 >= 0 )
                  {
                    v29 = 0;
                    if ( v24 )
                      v29 = Common::Xml::StringToBool(v25, v27);
                    if ( v25 )
                      operator delete(v25, (const struct std::nothrow_t *)v27);
                    if ( !v24 || !v29 )
                      v9 = 0;
                    *a4 = v9;
                    return 0;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x30F,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
                    (const char *)(unsigned int)v13,
                    (int)v78);
                  if ( v25 )
                    operator delete(v25, v60);
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x9EB,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
                    (const char *)(unsigned int)v13,
                    (int)v78);
                  return (unsigned int)v13;
                }
                v50 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v79, pvarg.bstrVal);
                v13 = v50;
                v22 = retaddr;
                if ( v50 >= 0 )
                {
                  v24 = 1;
                  goto LABEL_24;
                }
                v37 = (unsigned int)v50;
                v38 = 683;
              }
            }
            wil::details::in1diag3::_Log_Hr(
              v22,
              (void *)v38,
              (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
              (const char *)v37,
              (int)v78);
LABEL_44:
            v24 = 0;
            goto LABEL_24;
          }
          v39 = *(__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, GUID *, int **))v88.lpVtbl->QueryInterface;
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v87);
          v40 = v39(v19, &GUID_2933bf85_7b36_11d2_b20e_00c04f983e60, &v87);
          v13 = v40;
          v15 = retaddr;
          if ( v40 >= 0 )
          {
            v41 = v87;
            v87 = 0;
            v78 = v41;
            goto LABEL_16;
          }
          v35 = (unsigned int)v40;
          v36 = 83;
        }
      }
      wil::details::in1diag3::_Log_Hr(
        v15,
        (void *)v36,
        (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
        (const char *)v35,
        (int)v78);
      goto LABEL_16;
    }
    v88.lpVtbl = 0;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v88);
    XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                            (OLECHAR *)L"./*[local-name()='AppService']",
                            (const unsigned __int16 *)a2,
                            &v88,
                            v74);
    v43 = XMLElementFromQuery;
    if ( XMLElementFromQuery < 0 )
    {
      v76 = (unsigned int)XMLElementFromQuery;
      v77 = 2514;
LABEL_112:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v77,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)v76,
        (int)v78);
      goto LABEL_89;
    }
    if ( !v88.lpVtbl )
    {
      v43 = -2147024809;
      v76 = 2147942487LL;
      v77 = 2515;
      goto LABEL_112;
    }
    LODWORD(v87) = 0;
    *(_OWORD *)v79 = 0;
    v80 = 0;
    AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                        (Common::Xml *)v88.lpVtbl,
                                        (struct IXMLDOMElement *)&stru_1801DBA30,
                                        (const unsigned __int16 *)v79,
                                        (struct Common::StringBuffer *)&v87,
                                        v78);
    v43 = AttributeValueStringFromElement;
    if ( AttributeValueStringFromElement < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9DC,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)AttributeValueStringFromElement,
        (int)v78);
      if ( v79[1] )
        operator delete(v79[1], v64);
      goto LABEL_89;
    }
    v67 = v79[1];
    if ( (_DWORD)v87 )
      v68 = (unsigned int)_o__wcsicmp(v79[1], L"true") == 0;
    else
      v68 = 0;
    *a4 = v68;
    if ( v67 )
      operator delete(v67, v66);
LABEL_100:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v88);
    return 0;
  }
  v88.lpVtbl = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v88);
  v81 = 0;
  v87 = 0;
  v42 = 0;
  if ( !a2 )
  {
    v43 = -2147024809;
    v13 = -2147024809;
    v44 = retaddr;
    v45 = 2147942487LL;
    v46 = 124;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      v44,
      (void *)v46,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)v45,
      (int)v78);
    goto LABEL_50;
  }
  SysFreeString(0);
  v42 = 0;
  v82 = 0;
  v51 = 0x7FFFFFFF;
  v52 = L"./*[local-name()='BackgroundTasks']";
  do
  {
    if ( !*v52 )
      break;
    ++v52;
    --v51;
  }
  while ( v51 );
  v43 = -2147024809;
  v13 = v51 == 0 ? 0x80070057 : 0;
  v53 = (0x7FFFFFFF - v51) & -(__int64)(v51 != 0);
  if ( v51 )
  {
    if ( (unsigned int)v53 > 0x3FFFFFFF )
    {
      v13 = -2147024809;
    }
    else
    {
      v42 = SysAllocStringLen(L"./*[local-name()='BackgroundTasks']", v53);
      v82 = v42;
      v13 = v42 == 0 ? 0x8007000E : 0;
    }
  }
  v44 = retaddr;
  if ( v13 < 0 )
  {
    v45 = (unsigned int)v13;
    v46 = 127;
    goto LABEL_49;
  }
  v54 = a2->lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v81);
  v55 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, _QWORD))v54)(a2, v42, &v81);
  v13 = v55;
  v44 = retaddr;
  if ( v55 < 0 )
  {
    v45 = (unsigned int)v55;
    v46 = 131;
    goto LABEL_49;
  }
  v56 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
  if ( v81 )
  {
    v57 = **v81;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v87);
    v58 = v57(v56, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v87);
    v13 = v58;
    v44 = retaddr;
    if ( v58 < 0 )
    {
      v45 = (unsigned int)v58;
      v46 = 137;
      goto LABEL_49;
    }
    v59 = (struct IXMLDOMElementVtbl *)v87;
    v87 = 0;
    v88.lpVtbl = v59;
  }
  else
  {
    v88.lpVtbl = 0;
  }
LABEL_50:
  SysFreeString(v42);
  v47 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(int *))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
  if ( v81 )
  {
    v81 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v48)[2])(v48);
  }
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v13,
      (int)v78);
    v49 = v88.lpVtbl;
    if ( v88.lpVtbl )
    {
      v88.lpVtbl = 0;
      (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v49->QueryInterface + 2))(v49);
    }
    return (unsigned int)v13;
  }
  v61 = v88.lpVtbl;
  if ( v88.lpVtbl )
  {
    v78 = 0;
    v62 = (__int64 (__fastcall *)(struct IXMLDOMElementVtbl *, int **))*((_QWORD *)v88.lpVtbl->QueryInterface + 17);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v78);
    v63 = v62(v61, &v78);
    v43 = v63;
    if ( v63 >= 0 )
    {
      LODWORD(v87) = 0;
      *(_OWORD *)v79 = 0;
      v80 = 0;
      v70 = Common::Xml::GetAttributeValueStringFromElement(
              (Common::Xml *)v88.lpVtbl,
              (struct IXMLDOMElement *)&stru_1801DBA30,
              (const unsigned __int16 *)v79,
              (struct Common::StringBuffer *)&v87,
              v78);
      v43 = v70;
      if ( v70 >= 0 )
      {
        v72 = v79[1];
        if ( (_DWORD)v87 )
          v73 = (unsigned int)_o__wcsicmp(v79[1], L"true") == 0;
        else
          v73 = 0;
        *a4 = v73;
        if ( v72 )
          operator delete(v72, v71);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v78);
        goto LABEL_100;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C4,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v70,
        (int)v78);
      if ( v79[1] )
        operator delete(v79[1], v69);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9BB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v63,
        (int)v78);
    }
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v78);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)0x80070057LL,
      (int)v78);
  }
LABEL_89:
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v88);
  return v43;
}

```

## disassembly

```asm
0x180006c98  mov     rax, rsp
0x180006c9b  mov     [rax+10h], rbx
0x180006c9f  push    rbp
0x180006ca0  push    rsi
0x180006ca1  push    rdi
0x180006ca2  push    r12
0x180006ca4  push    r13
0x180006ca6  push    r14
0x180006ca8  push    r15
0x180006caa  lea     rbp, [rax-5Fh]
0x180006cae  sub     rsp, 0A0h
0x180006cb5  movaps  xmmword ptr [rax-48h], xmm6
0x180006cb9  movaps  xmmword ptr [rax-58h], xmm7
0x180006cbd  mov     r13, r9
0x180006cc0  mov     rdi, r8
0x180006cc3  mov     r12, rdx
0x180006cc6  mov     rbx, rcx
0x180006cc9  xor     r15d, r15d
0x180006ccc  mov     [r9], r15b
0x180006ccf  lea     rdx, aWindowsBackgro; "Windows.BackgroundTasks"
0x180006cd6  mov     rcx, [rcx+20h]
0x180006cda  call    cs:__imp__o__wcsicmp
0x180006ce1  nop     dword ptr [rax+rax+00h]
0x180006ce6  test    eax, eax
0x180006ce8  jz      loc_180007006
0x180006cee  lea     rdx, aWindowsAppserv; "Windows.AppService"
0x180006cf5  mov     rcx, [rbx+20h]
0x180006cf9  call    cs:__imp__o__wcsicmp
0x180006d00  nop     dword ptr [rax+rax+00h]
0x180006d05  test    eax, eax
0x180006d07  jz      loc_1800074A1
0x180006d0d  xorps   xmm6, xmm6
0x180006d10  movups  xmmword ptr [rbp+57h+var_A8], xmm6
0x180006d14  mov     [rbp+57h+var_98], r15d
0x180006d18  mov     [rbp+57h+var_B0], r15
0x180006d1c  xorps   xmm0, xmm0
0x180006d1f  xor     eax, eax
0x180006d21  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180006d25  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180006d29  mov     word ptr [rbp+57h+pvarg], r15w
0x180006d2e  xorps   xmm7, xmm7
0x180006d31  movups  [rbp+57h+var_68], xmm7
0x180006d35  mov     [rbp+57h+var_58], r15d
0x180006d39  lea     r15d, [rax+1]
0x180006d3d  xor     r12d, r12d
0x180006d40  test    rdi, rdi
0x180006d43  jz      loc_180007511
0x180006d49  mov     [rbp+57h+arg_18.lpVtbl], r12
0x180006d4d  mov     [rbp+57h+arg_0], r12
0x180006d51  xor     ecx, ecx; bstrString
0x180006d53  call    cs:__imp_SysFreeString
0x180006d5a  nop     dword ptr [rax+rax+00h]
0x180006d5f  mov     ebx, r12d
0x180006d62  mov     [rbp+57h+var_88], rbx
0x180006d66  mov     ecx, 7FFFFFFFh
0x180006d6b  mov     edx, ecx
0x180006d6d  lea     rax, strIn; "@*[local-name()='SupportsMultipleInstan"...
0x180006d74  cmp     [rax], r12w
0x180006d78  jz      short loc_180006D83
0x180006d7a  add     rax, 2
0x180006d7e  sub     rdx, r15
0x180006d81  jnz     short loc_180006D74
0x180006d83  mov     rax, rdx
0x180006d86  neg     rax
0x180006d89  sbb     esi, esi
0x180006d8b  not     esi
0x180006d8d  mov     r14d, 80070057h
0x180006d93  and     esi, r14d
0x180006d96  mov     rax, rdx
0x180006d99  sub     rcx, rdx
0x180006d9c  neg     rax
0x180006d9f  sbb     r8, r8
0x180006da2  and     r8, rcx
0x180006da5  test    rdx, rdx
0x180006da8  jz      short loc_180006DE1
0x180006daa  cmp     r8d, 3FFFFFFFh
0x180006db1  ja      loc_1800072AE
0x180006db7  mov     edx, r8d; ui
0x180006dba  lea     rcx, strIn; "@*[local-name()='SupportsMultipleInstan"...
0x180006dc1  call    cs:__imp_SysAllocStringLen
0x180006dc8  nop     dword ptr [rax+rax+00h]
0x180006dcd  mov     rbx, rax
0x180006dd0  mov     [rbp+57h+var_88], rax
0x180006dd4  neg     rax
0x180006dd7  sbb     esi, esi
0x180006dd9  not     esi
0x180006ddb  and     esi, 8007000Eh
0x180006de1  mov     rcx, [rbp+5Fh]; this
0x180006de5  test    esi, esi
0x180006de7  js      loc_180006F8D
0x180006ded  mov     rax, [rdi]
0x180006df0  mov     rsi, [rax+128h]
0x180006df7  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x180006dfb  test    rcx, rcx
0x180006dfe  jz      short loc_180006E11
0x180006e00  mov     [rbp+57h+arg_18.lpVtbl], r12
0x180006e04  mov     rdx, [rcx]
0x180006e07  mov     rax, [rdx+10h]
0x180006e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e10  nop
0x180006e11  lea     r8, [rbp+57h+arg_18]
0x180006e15  mov     rdx, rbx
0x180006e18  mov     rcx, rdi
0x180006e1b  mov     rax, rsi
0x180006e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e23  mov     esi, eax
0x180006e25  mov     rcx, [rbp+5Fh]
0x180006e29  test    eax, eax
0x180006e2b  js      loc_1800070EA
0x180006e31  mov     rdi, [rbp+57h+arg_18.lpVtbl]
0x180006e35  test    rdi, rdi
0x180006e38  jnz     loc_180006FC2
0x180006e3e  mov     [rbp+57h+var_B0], r12
0x180006e42  mov     rcx, rbx; bstrString
0x180006e45  call    cs:__imp_SysFreeString
0x180006e4c  nop     dword ptr [rax+rax+00h]
0x180006e51  nop
0x180006e52  mov     rcx, [rbp+57h+arg_0]
0x180006e56  test    rcx, rcx
0x180006e59  jz      short loc_180006E6C
0x180006e5b  mov     [rbp+57h+arg_0], r12
0x180006e5f  mov     rax, [rcx]
0x180006e62  mov     rax, [rax+10h]
0x180006e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6b  nop
0x180006e6c  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x180006e70  test    rcx, rcx
0x180006e73  jz      short loc_180006E86
0x180006e75  mov     [rbp+57h+arg_18.lpVtbl], r12
0x180006e79  mov     rax, [rcx]
0x180006e7c  mov     rax, [rax+10h]
0x180006e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e85  nop
0x180006e86  mov     rcx, [rbp+5Fh]; this
0x180006e8a  test    esi, esi
0x180006e8c  js      loc_180006FA6
0x180006e92  mov     rcx, [rbp+57h+var_B0]
0x180006e96  test    rcx, rcx
0x180006e99  jz      loc_180006F6B
0x180006e9f  mov     rax, [rcx]
0x180006ea2  lea     rdx, [rbp+57h+pvarg]
0x180006ea6  mov     rax, [rax+160h]
0x180006ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb2  mov     esi, eax
0x180006eb4  mov     rcx, [rbp+5Fh]
0x180006eb8  test    eax, eax
0x180006eba  js      loc_1800070F7
0x180006ec0  mov     edi, r12d
0x180006ec3  mov     rdx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x180006ec7  test    rdx, rdx
0x180006eca  jnz     loc_1800070CF
0x180006ed0  mov     rbx, [rbp+57h+var_A8+8]
0x180006ed4  psrldq  xmm7, 8
0x180006ed9  movq    rcx, xmm7; void *
0x180006ede  test    rcx, rcx
0x180006ee1  jz      short loc_180006EE9
0x180006ee3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006ee8  nop
0x180006ee9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180006eed  call    cs:__imp_VariantClear
0x180006ef4  nop     dword ptr [rax+rax+00h]
0x180006ef9  nop
0x180006efa  mov     rcx, [rbp+57h+var_B0]
0x180006efe  test    rcx, rcx
0x180006f01  jz      short loc_180006F14
0x180006f03  mov     [rbp+57h+var_B0], r12
0x180006f07  mov     rax, [rcx]
0x180006f0a  mov     rax, [rax+10h]
0x180006f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f13  nop
0x180006f14  test    esi, esi
0x180006f16  js      loc_18000726B
0x180006f1c  mov     sil, r12b
0x180006f1f  test    edi, edi
0x180006f21  jnz     loc_18000751B
0x180006f27  test    rbx, rbx
0x180006f2a  jz      short loc_180006F34
0x180006f2c  mov     rcx, rbx; void *
0x180006f2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006f34  test    edi, edi
0x180006f36  jnz     loc_18000752B
0x180006f3c  mov     r15b, r12b
0x180006f3f  mov     [r13+0], r15b
0x180006f43  xor     eax, eax
0x180006f45  lea     r11, [rsp+0D0h+var_30]
0x180006f4d  mov     rbx, [r11+48h]
0x180006f51  movaps  xmm6, xmmword ptr [r11-10h]
0x180006f56  movaps  xmm7, xmmword ptr [r11-20h]
0x180006f5b  mov     rsp, r11
0x180006f5e  pop     r15
0x180006f60  pop     r14
0x180006f62  pop     r13
0x180006f64  pop     r12
0x180006f66  pop     rdi
0x180006f67  pop     rsi
0x180006f68  pop     rbp
0x180006f69  retn
0x180006f6b  movd    ecx, xmm6
0x180006f6f  add     rcx, rcx
0x180006f72  psrldq  xmm6, 8
0x180006f77  movq    rbx, xmm6
0x180006f7c  mov     rax, rbx
0x180006f7f  jnz     loc_180007501
0x180006f85  mov     edi, r12d
0x180006f88  jmp     loc_180006ED4
0x180006f8d  mov     r9d, esi; char *
0x180006f90  mov     edx, 49h ; 'I'; void *
0x180006f95  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180006f9c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006fa1  jmp     loc_180006E42
0x180006fa6  mov     r9d, esi; char *
0x180006fa9  mov     edx, 2A0h; void *
0x180006fae  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180006fb5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006fba  mov     edi, r12d
0x180006fbd  jmp     loc_180006ED0
0x180006fc2  mov     rax, [rdi]
0x180006fc5  mov     rsi, [rax]
0x180006fc8  lea     rcx, [rbp+57h+arg_0]
0x180006fcc  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180006fd1  lea     r8, [rbp+57h+arg_0]
0x180006fd5  lea     rdx, _GUID_2933bf85_7b36_11d2_b20e_00c04f983e60
0x180006fdc  mov     rcx, rdi
0x180006fdf  mov     rax, rsi
0x180006fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe7  mov     esi, eax
0x180006fe9  mov     rcx, [rbp+5Fh]
0x180006fed  test    eax, eax
0x180006fef  js      loc_180007104
0x180006ff5  mov     rax, [rbp+57h+arg_0]
0x180006ff9  mov     [rbp+57h+arg_0], r12
0x180006ffd  mov     [rbp+57h+var_B0], rax
0x180007001  jmp     loc_180006E42
0x180007006  mov     [rbp+57h+arg_18.lpVtbl], r15
0x18000700a  lea     rcx, [rbp+57h+arg_18]
0x18000700e  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180007013  mov     [rbp+57h+var_90], r15
0x180007017  mov     [rbp+57h+arg_0], r15
0x18000701b  mov     rbx, r15
0x18000701e  test    r12, r12
0x180007021  jnz     loc_18000711E
0x180007027  mov     r14d, 80070057h
0x18000702d  mov     esi, r14d
0x180007030  mov     rcx, [rbp+5Fh]; this
0x180007034  mov     r9d, r14d; char *
0x180007037  lea     edx, [r12+7Ch]; void *
0x18000703c  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180007043  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007048  nop
0x180007049  mov     rcx, rbx; bstrString
0x18000704c  call    cs:__imp_SysFreeString
0x180007053  nop     dword ptr [rax+rax+00h]
0x180007058  nop
0x180007059  mov     rcx, [rbp+57h+arg_0]
0x18000705d  test    rcx, rcx
0x180007060  jz      short loc_180007073
0x180007062  mov     [rbp+57h+arg_0], r15
0x180007066  mov     rax, [rcx]
0x180007069  mov     rax, [rax+10h]
0x18000706d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007072  nop
0x180007073  mov     rcx, [rbp+57h+var_90]
0x180007077  test    rcx, rcx
0x18000707a  jz      short loc_18000708D
0x18000707c  mov     [rbp+57h+var_90], r15
0x180007080  mov     rax, [rcx]
0x180007083  mov     rax, [rax+10h]
0x180007087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000708c  nop
0x18000708d  test    esi, esi
0x18000708f  jns     loc_1800072BE
0x180007095  mov     rcx, [rbp+5Fh]; this
0x180007099  mov     r9d, esi; char *
0x18000709c  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800070a3  mov     edx, 9B7h; void *
0x1800070a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070ad  nop
0x1800070ae  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x1800070b2  test    rcx, rcx
0x1800070b5  jz      short loc_1800070C8
0x1800070b7  mov     [rbp+57h+arg_18.lpVtbl], r15
0x1800070bb  mov     rax, [rcx]
0x1800070be  mov     rax, [rax+10h]
0x1800070c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c7  nop
0x1800070c8  mov     eax, esi
0x1800070ca  jmp     loc_180006F45
0x1800070cf  lea     rcx, [rbp+57h+var_A8]; this
0x1800070d3  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800070d8  mov     esi, eax
0x1800070da  mov     rcx, [rbp+5Fh]
0x1800070de  test    eax, eax
0x1800070e0  js      short loc_180007111
0x1800070e2  mov     edi, r15d
0x1800070e5  jmp     loc_180006ED0
0x1800070ea  mov     r9d, eax
0x1800070ed  mov     edx, 4Dh ; 'M'
0x1800070f2  jmp     loc_180006F95
0x1800070f7  mov     r9d, eax
0x1800070fa  mov     edx, 2A4h
  ... truncated ...
```

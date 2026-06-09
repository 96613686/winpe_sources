# CSmsProcessor::Initialize(IXMLDOMNode *)

- ea: `0x180066410`
- end: `0x180067310`
- name: `?Initialize@CSmsProcessor@@UEAAJPEAUIXMLDOMNode@@@Z`
- size: `3840`
- prototype: `__int64 __fastcall(CSmsProcessor *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003a90`
- `0x180014d20`
- `0x18003cf74`
- `0x18003e02c`
- `0x180065be0`
- `0x180065d40`
- `0x180066020`
- `0x18006615c`
- `0x180066410`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800666f3`
- `OLEAUT32!__imp_SysAllocString` at `0x180066959`
- `OLEAUT32!__imp_SysAllocString` at `0x1800666f3`
- `OLEAUT32!__imp_SysAllocString` at `0x180066959`
- `OLEAUT32!__imp_SysFreeString` at `0x18006654d`
- `OLEAUT32!__imp_SysFreeString` at `0x180066618`
- `OLEAUT32!__imp_SysFreeString` at `0x1800666d0`
- `OLEAUT32!__imp_SysFreeString` at `0x180066720`
- `OLEAUT32!__imp_SysFreeString` at `0x1800667ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800667cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18006689f`
- `OLEAUT32!__imp_SysFreeString` at `0x180066986`
- `OLEAUT32!__imp_SysFreeString` at `0x180066999`
- `OLEAUT32!__imp_SysFreeString` at `0x180066aa1`
- `OLEAUT32!__imp_SysFreeString` at `0x180066acd`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180066cd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180066d91`
- `OLEAUT32!__imp_SysFreeString` at `0x180066e49`
- `OLEAUT32!__imp_SysFreeString` at `0x180066f01`
- `OLEAUT32!__imp_SysFreeString` at `0x180066fa3`
- `OLEAUT32!__imp_SysFreeString` at `0x180067045`
- `OLEAUT32!__imp_SysFreeString` at `0x1800670e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180067189`
- `OLEAUT32!__imp_SysFreeString` at `0x18006722b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800672c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18006654d`
- `OLEAUT32!__imp_SysFreeString` at `0x180066618`
- `OLEAUT32!__imp_SysFreeString` at `0x1800666d0`
- `OLEAUT32!__imp_SysFreeString` at `0x180066720`
- `OLEAUT32!__imp_SysFreeString` at `0x1800667ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800667cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18006689f`
- `OLEAUT32!__imp_SysFreeString` at `0x180066986`
- `OLEAUT32!__imp_SysFreeString` at `0x180066999`
- `OLEAUT32!__imp_SysFreeString` at `0x180066aa1`
- `OLEAUT32!__imp_SysFreeString` at `0x180066acd`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180066cd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180066d91`
- `OLEAUT32!__imp_SysFreeString` at `0x180066e49`
- `OLEAUT32!__imp_SysFreeString` at `0x180066f01`
- `OLEAUT32!__imp_SysFreeString` at `0x180066fa3`
- `OLEAUT32!__imp_SysFreeString` at `0x180067045`
- `OLEAUT32!__imp_SysFreeString` at `0x1800670e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180067189`
- `OLEAUT32!__imp_SysFreeString` at `0x18006722b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800672c3`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180066715`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18006697b`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180066715`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18006697b`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall CSmsProcessor::Initialize(CSmsProcessor *this, struct IXMLDOMNode *a2)
{
  __int64 *v3; // r15
  __int64 v4; // rbx
  __int64 v5; // rdi
  _DWORD *v6; // rsi
  int v7; // ebx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  struct IXMLDOMNode *v10; // rcx
  OLECHAR *v11; // rax
  OLECHAR *v12; // rbx
  HRESULT v13; // edi
  unsigned int v14; // r12d
  __int64 v15; // rcx
  OLECHAR *v16; // rax
  OLECHAR *v17; // rbx
  HRESULT v18; // edi
  unsigned int v19; // r14d
  _QWORD *v20; // rbx
  _QWORD *v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rcx
  BSTR bstrString; // [rsp+20h] [rbp-49h] BYREF
  struct IXMLDOMNode *v25; // [rsp+28h] [rbp-41h] BYREF
  __int64 v26; // [rsp+30h] [rbp-39h] BYREF
  __int64 v27; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  __int128 v31; // [rsp+58h] [rbp-11h] BYREF
  __int64 v32; // [rsp+68h] [rbp-1h]
  __int128 v33; // [rsp+70h] [rbp+7h] BYREF
  __int64 v34; // [rsp+80h] [rbp+17h]
  _DWORD *v35; // [rsp+88h] [rbp+1Fh]
  int v36; // [rsp+D0h] [rbp+67h] BYREF
  int v37; // [rsp+E0h] [rbp+77h] BYREF
  int v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v35 = 0;
  bstrString = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v31 = 0;
  v32 = 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  v3 = (__int64 *)((char *)this + 48);
  v4 = *((_QWORD *)this + 6);
  v5 = *((_QWORD *)this + 7);
  if ( v4 != v5 )
  {
    do
    {
      std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>(v4);
      v4 += 24;
    }
    while ( v4 != v5 );
    v3[1] = *v3;
  }
  v6 = operator new(0x10u);
  *(_QWORD *)v6 = &CSmsMessageFilterFactory::`vftable';
  v6[2] = 1;
  v35 = v6;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))a2->lpVtbl->get_nodeType)(a2, &v38);
  if ( v7 < 0 )
  {
    std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
    if ( v25 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    return (unsigned int)v7;
  }
  lpVtbl = a2->lpVtbl;
  if ( v38 == 9 )
  {
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, struct IXMLDOMNode **))lpVtbl->selectSingleNode)(
           a2,
           L"/SmsMessageFilter",
           &v25);
    if ( v7 < 0 )
    {
      std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
      if ( v25 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      SysFreeString(bstrString);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
      return (unsigned int)v7;
    }
    v10 = v25;
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_nodeName)(a2, &bstrString);
    if ( v7 < 0 )
    {
      std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
      if ( v25 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      goto LABEL_226;
    }
    v11 = SysAllocString(L"SmsMessageFilter");
    v12 = v11;
    if ( !v11 )
      ATL::AtlThrowImpl(-2147024882);
    v13 = VarBstrCmp(bstrString, v11, 0x400u, 0);
    SysFreeString(v12);
    if ( v13 != 1 )
    {
      std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
      if ( v25 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      goto LABEL_237;
    }
    SysFreeString(bstrString);
    bstrString = 0;
    v10 = v25;
    if ( v25 != a2 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
      if ( v25 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
      v10 = a2;
      v25 = a2;
    }
  }
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v10->lpVtbl->get_childNodes)(v10, &v29);
  if ( v7 < 0 )
  {
    std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
    if ( v25 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_226:
    SysFreeString(bstrString);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    return (unsigned int)v7;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 64LL))(v29, &v37);
  if ( v7 >= 0 && v37 )
  {
    v14 = 0;
    if ( v37 <= 0 )
    {
LABEL_107:
      if ( v3 != (__int64 *)&v31 )
        std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::_Assign_counted_range<std::vector<ATL::CComPtr<ISmsMessageFilter>> *>(
          v3,
          v31,
          0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v31 + 1) - v31) >> 3));
      std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
      if ( v25 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    else
    {
      while ( 1 )
      {
        v33 = 0;
        v34 = 0;
        v15 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 56LL))(v29, v14, &v27);
        if ( v7 < 0 )
        {
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_226;
        }
        v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 56LL))(v27, &bstrString);
        if ( v7 < 0 )
        {
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_226;
        }
        v16 = SysAllocString(L"FilterRule");
        v17 = v16;
        if ( !v16 )
          ATL::AtlThrowImpl(-2147024882);
        v18 = VarBstrCmp(bstrString, v16, 0x400u, 0);
        SysFreeString(v17);
        if ( v18 != 1 )
        {
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_237;
        }
        SysFreeString(bstrString);
        bstrString = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 96LL))(v27, &v28);
        if ( v7 < 0 )
        {
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_226;
        }
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 64LL))(v28, &v36);
        if ( v7 < 0 )
        {
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_237;
        }
        v19 = 0;
        if ( v36 > 0 )
          break;
LABEL_103:
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::_Emplace_reallocate<std::vector<ATL::CComPtr<ISmsMessageFilter>> const &>(
            (char **)&v31,
            *((char **)&v31 + 1),
            (__int64)&v33);
        }
        else
        {
          std::vector<ATL::CComPtr<ISmsMessageFilter>>::vector<ATL::CComPtr<ISmsMessageFilter>>(
            *((_QWORD **)&v31 + 1),
            (__int64 **)&v33);
          *((_QWORD *)&v31 + 1) += 24LL;
        }
        std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
        if ( (int)++v14 >= v37 )
          goto LABEL_107;
      }
      while ( 1 )
      {
        v30 = 0;
        v21 = (_QWORD *)*((_QWORD *)&v33 + 1);
        v20 = (_QWORD *)v33;
        if ( (_QWORD)v33 != *((_QWORD *)&v33 + 1) )
        {
          do
          {
            if ( *v20 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 16LL))(*v20);
            ++v20;
          }
          while ( v20 != v21 );
          *((_QWORD *)&v33 + 1) = v33;
        }
        v22 = v26;
        if ( v26 )
        {
          v26 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 56LL))(v28, v19, &v26);
        if ( v7 < 0 )
          break;
        v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 56LL))(v26, &bstrString);
        if ( v7 < 0 )
        {
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_226;
        }
        v7 = (*(__int64 (__fastcall **)(_DWORD *, BSTR, __int64 *))(*(_QWORD *)v6 + 24LL))(v6, bstrString, &v30);
        if ( v7 < 0 )
        {
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_226;
        }
        SysFreeString(bstrString);
        bstrString = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 24LL))(v30, v26);
        if ( v7 < 0 )
        {
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
          std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
          if ( v25 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          goto LABEL_226;
        }
        SysFreeString(bstrString);
        bstrString = 0;
        if ( *((_QWORD *)&v33 + 1) == v34 )
        {
          std::vector<ATL::CComPtr<ISmsMessageFilter>>::_Emplace_reallocate<ATL::CComPtr<ISmsMessageFilter> const &>(
            (char **)&v33,
            *((char **)&v33 + 1),
            &v30);
        }
        else
        {
          v23 = v30;
          **((_QWORD **)&v33 + 1) = v30;
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
          *((_QWORD *)&v33 + 1) += 8LL;
        }
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        if ( (int)++v19 >= v36 )
          goto LABEL_103;
      }
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>((__int64)&v33);
      std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
      if ( v25 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    goto LABEL_226;
  }
  std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>((__int64 *)&v31);
  if ( v25 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_237:
  SysFreeString(bstrString);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180066410  mov     [rsp-8+arg_8], rbx
0x180066415  push    rbp
0x180066416  push    rsi
0x180066417  push    rdi
0x180066418  push    r12
0x18006641a  push    r13
0x18006641c  push    r14
0x18006641e  push    r15
0x180066420  lea     rbp, [rsp-27h]
0x180066425  sub     rsp, 90h
0x18006642c  mov     r14, rdx
0x18006642f  xor     r13d, r13d
0x180066432  mov     [rbp+57h+var_38], r13
0x180066436  mov     [rbp+57h+bstrString], r13
0x18006643a  mov     [rbp+57h+var_78], r13
0x18006643e  mov     [rbp+57h+var_80], r13
0x180066442  mov     [rbp+57h+var_88], r13
0x180066446  mov     [rbp+57h+var_90], r13
0x18006644a  mov     [rbp+57h+var_98], r13
0x18006644e  xorps   xmm0, xmm0
0x180066451  movdqu  [rbp+57h+var_68], xmm0
0x180066456  mov     [rbp+57h+var_58], r13
0x18006645a  mov     [rbp+57h+arg_10], r13d
0x18006645e  mov     [rbp+57h+arg_0], r13d
0x180066462  mov     [rbp+57h+arg_18], r13d
0x180066466  lea     r15, [rcx+30h]
0x18006646a  mov     rbx, [r15]
0x18006646d  mov     rdi, [r15+8]
0x180066471  cmp     rbx, rdi
0x180066474  jz      short loc_18006648E
0x180066476  mov     rcx, rbx
0x180066479  call    ??1?$vector@V?$CComPtr@UISmsDevice@@@ATL@@V?$allocator@V?$CComPtr@UISmsDevice@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComPtr<ISmsDevice>>::~vector<ATL::CComPtr<ISmsDevice>>(void)
0x18006647e  add     rbx, 18h
0x180066482  cmp     rbx, rdi
0x180066485  jnz     short loc_180066476
0x180066487  mov     rax, [r15]
0x18006648a  mov     [r15+8], rax
0x18006648e  mov     ecx, 10h; Size
0x180066493  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066498  mov     rsi, rax
0x18006649b  mov     [rbp+57h+var_38], rax
0x18006649f  lea     rax, ??_7CSmsMessageFilterFactory@@6B@; const CSmsMessageFilterFactory::`vftable'
0x1800664a6  mov     [rsi], rax
0x1800664a9  mov     dword ptr [rsi+8], 1
0x1800664b0  mov     [rbp+57h+var_38], rsi
0x1800664b4  mov     rcx, [r14]
0x1800664b7  mov     rax, [rcx+50h]
0x1800664bb  lea     rdx, [rbp+57h+arg_18]
0x1800664bf  mov     rcx, r14
0x1800664c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664c7  mov     ebx, eax
0x1800664c9  test    eax, eax
0x1800664cb  jns     loc_18006656B
0x1800664d1  lea     rcx, [rbp+57h+var_68]
0x1800664d5  call    ??1?$vector@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@V?$allocator@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>(void)
0x1800664da  nop
0x1800664db  mov     rcx, [rbp+57h+var_98]
0x1800664df  test    rcx, rcx
0x1800664e2  jz      short loc_1800664F1
0x1800664e4  mov     rdx, [rcx]
0x1800664e7  mov     rax, [rdx+10h]
0x1800664eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664f0  nop
0x1800664f1  mov     rcx, [rbp+57h+var_90]
0x1800664f5  test    rcx, rcx
0x1800664f8  jz      short loc_180066507
0x1800664fa  mov     rax, [rcx]
0x1800664fd  mov     rax, [rax+10h]
0x180066501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066506  nop
0x180066507  mov     rcx, [rbp+57h+var_88]
0x18006650b  test    rcx, rcx
0x18006650e  jz      short loc_18006651D
0x180066510  mov     rax, [rcx]
0x180066513  mov     rax, [rax+10h]
0x180066517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006651c  nop
0x18006651d  mov     rcx, [rbp+57h+var_80]
0x180066521  test    rcx, rcx
0x180066524  jz      short loc_180066533
0x180066526  mov     rax, [rcx]
0x180066529  mov     rax, [rax+10h]
0x18006652d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066532  nop
0x180066533  mov     rcx, [rbp+57h+var_78]
0x180066537  test    rcx, rcx
0x18006653a  jz      short loc_180066549
0x18006653c  mov     rax, [rcx]
0x18006653f  mov     rax, [rax+10h]
0x180066543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066548  nop
0x180066549  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006654d  call    cs:__imp_SysFreeString
0x180066553  nop
0x180066554  mov     rax, [rsi]
0x180066557  mov     rcx, rsi
0x18006655a  mov     rax, [rax+10h]
0x18006655e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066563  nop
0x180066564  mov     eax, ebx
0x180066566  jmp     loc_1800672DF
0x18006656b  mov     rax, [r14]
0x18006656e  mov     rcx, r14
0x180066571  cmp     [rbp+57h+arg_18], 9
0x180066575  jnz     loc_18006663D
0x18006657b  lea     r8, [rbp+57h+var_98]
0x18006657f  lea     rdx, aSmsmessagefilt_2; "/SmsMessageFilter"
0x180066586  mov     rax, [rax+128h]
0x18006658d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066592  mov     ebx, eax
0x180066594  test    eax, eax
0x180066596  jns     loc_180066634
0x18006659c  lea     rcx, [rbp+57h+var_68]
0x1800665a0  call    ??1?$vector@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@V?$allocator@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>(void)
0x1800665a5  nop
0x1800665a6  mov     rcx, [rbp+57h+var_98]
0x1800665aa  test    rcx, rcx
0x1800665ad  jz      short loc_1800665BC
0x1800665af  mov     rdx, [rcx]
0x1800665b2  mov     rax, [rdx+10h]
0x1800665b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665bb  nop
0x1800665bc  mov     rcx, [rbp+57h+var_90]
0x1800665c0  test    rcx, rcx
0x1800665c3  jz      short loc_1800665D2
0x1800665c5  mov     rax, [rcx]
0x1800665c8  mov     rax, [rax+10h]
0x1800665cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665d1  nop
0x1800665d2  mov     rcx, [rbp+57h+var_88]
0x1800665d6  test    rcx, rcx
0x1800665d9  jz      short loc_1800665E8
0x1800665db  mov     rax, [rcx]
0x1800665de  mov     rax, [rax+10h]
0x1800665e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665e7  nop
0x1800665e8  mov     rcx, [rbp+57h+var_80]
0x1800665ec  test    rcx, rcx
0x1800665ef  jz      short loc_1800665FE
0x1800665f1  mov     rax, [rcx]
0x1800665f4  mov     rax, [rax+10h]
0x1800665f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665fd  nop
0x1800665fe  mov     rcx, [rbp+57h+var_78]
0x180066602  test    rcx, rcx
0x180066605  jz      short loc_180066614
0x180066607  mov     rax, [rcx]
0x18006660a  mov     rax, [rax+10h]
0x18006660e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066613  nop
0x180066614  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180066618  call    cs:__imp_SysFreeString
0x18006661e  nop
0x18006661f  mov     rax, [rsi]
0x180066622  mov     rcx, rsi
0x180066625  mov     rax, [rax+10h]
0x180066629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006662e  nop
0x18006662f  jmp     loc_180066564
0x180066634  mov     rcx, [rbp+57h+var_98]
0x180066638  jmp     loc_180066809
0x18006663d  lea     rdx, [rbp+57h+bstrString]
0x180066641  mov     rax, [rax+38h]
0x180066645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006664a  mov     ebx, eax
0x18006664c  test    eax, eax
0x18006664e  jns     loc_1800666EC
0x180066654  lea     rcx, [rbp+57h+var_68]
0x180066658  call    ??1?$vector@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@V?$allocator@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>(void)
0x18006665d  nop
0x18006665e  mov     rcx, [rbp+57h+var_98]
0x180066662  test    rcx, rcx
0x180066665  jz      short loc_180066674
0x180066667  mov     rdx, [rcx]
0x18006666a  mov     rax, [rdx+10h]
0x18006666e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066673  nop
0x180066674  mov     rcx, [rbp+57h+var_90]
0x180066678  test    rcx, rcx
0x18006667b  jz      short loc_18006668A
0x18006667d  mov     rax, [rcx]
0x180066680  mov     rax, [rax+10h]
0x180066684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066689  nop
0x18006668a  mov     rcx, [rbp+57h+var_88]
0x18006668e  test    rcx, rcx
0x180066691  jz      short loc_1800666A0
0x180066693  mov     rax, [rcx]
0x180066696  mov     rax, [rax+10h]
0x18006669a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006669f  nop
0x1800666a0  mov     rcx, [rbp+57h+var_80]
0x1800666a4  test    rcx, rcx
0x1800666a7  jz      short loc_1800666B6
0x1800666a9  mov     rax, [rcx]
0x1800666ac  mov     rax, [rax+10h]
0x1800666b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666b5  nop
0x1800666b6  mov     rcx, [rbp+57h+var_78]
0x1800666ba  test    rcx, rcx
0x1800666bd  jz      short loc_1800666CC
0x1800666bf  mov     rax, [rcx]
0x1800666c2  mov     rax, [rax+10h]
0x1800666c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666cb  nop
0x1800666cc  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800666d0  call    cs:__imp_SysFreeString
0x1800666d6  nop
0x1800666d7  mov     rax, [rsi]
0x1800666da  mov     rcx, rsi
0x1800666dd  mov     rax, [rax+10h]
0x1800666e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666e6  nop
0x1800666e7  jmp     loc_180066564
0x1800666ec  lea     rcx, aSmsmessagefilt; "SmsMessageFilter"
0x1800666f3  call    cs:__imp_SysAllocString
0x1800666f9  mov     rbx, rax
0x1800666fc  test    rax, rax
0x1800666ff  jz      loc_180067305
0x180066705  xor     r9d, r9d; dwFlags
0x180066708  mov     r8d, 400h; lcid
0x18006670e  mov     rdx, rax; bstrRight
0x180066711  mov     rcx, [rbp+57h+bstrString]; bstrLeft
0x180066715  call    cs:__imp_VarBstrCmp
0x18006671b  mov     edi, eax
0x18006671d  mov     rcx, rbx; bstrString
0x180066720  call    cs:__imp_SysFreeString
0x180066726  cmp     edi, 1
0x180066729  jz      loc_1800667C7
0x18006672f  lea     rcx, [rbp+57h+var_68]
0x180066733  call    ??1?$vector@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@V?$allocator@V?$vector@V?$CComPtr@UISmsMessageFilter@@@ATL@@V?$allocator@V?$CComPtr@UISmsMessageFilter@@@ATL@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>::~vector<std::vector<ATL::CComPtr<ISmsMessageFilter>>>(void)
0x180066738  nop
0x180066739  mov     rcx, [rbp+57h+var_98]
0x18006673d  test    rcx, rcx
0x180066740  jz      short loc_18006674F
0x180066742  mov     rax, [rcx]
0x180066745  mov     rax, [rax+10h]
0x180066749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006674e  nop
0x18006674f  mov     rcx, [rbp+57h+var_90]
0x180066753  test    rcx, rcx
0x180066756  jz      short loc_180066765
0x180066758  mov     rax, [rcx]
0x18006675b  mov     rax, [rax+10h]
0x18006675f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066764  nop
0x180066765  mov     rcx, [rbp+57h+var_88]
0x180066769  test    rcx, rcx
0x18006676c  jz      short loc_18006677B
0x18006676e  mov     rax, [rcx]
0x180066771  mov     rax, [rax+10h]
0x180066775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006677a  nop
0x18006677b  mov     rcx, [rbp+57h+var_80]
0x18006677f  test    rcx, rcx
0x180066782  jz      short loc_180066791
0x180066784  mov     rax, [rcx]
0x180066787  mov     rax, [rax+10h]
0x18006678b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066790  nop
0x180066791  mov     rcx, [rbp+57h+var_78]
0x180066795  test    rcx, rcx
0x180066798  jz      short loc_1800667A7
0x18006679a  mov     rax, [rcx]
0x18006679d  mov     rax, [rax+10h]
0x1800667a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667a6  nop
0x1800667a7  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800667ab  call    cs:__imp_SysFreeString
0x1800667b1  nop
0x1800667b2  mov     rax, [rsi]
0x1800667b5  mov     rcx, rsi
0x1800667b8  mov     rax, [rax+10h]
0x1800667bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667c1  nop
0x1800667c2  jmp     loc_1800672DA
0x1800667c7  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800667cb  call    cs:__imp_SysFreeString
0x1800667d1  mov     [rbp+57h+bstrString], r13
0x1800667d5  mov     rcx, [rbp+57h+var_98]
0x1800667d9  cmp     rcx, r14
0x1800667dc  jz      short loc_180066809
0x1800667de  mov     rax, [r14]
0x1800667e1  mov     rcx, r14
0x1800667e4  mov     rax, [rax+8]
0x1800667e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667ed  mov     rcx, [rbp+57h+var_98]
0x1800667f1  test    rcx, rcx
0x1800667f4  jz      short loc_180066802
0x1800667f6  mov     rax, [rcx]
0x1800667f9  mov     rax, [rax+10h]
0x1800667fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066802  mov     rcx, r14
0x180066805  mov     [rbp+57h+var_98], rcx
0x180066809  mov     rax, [rcx]
0x18006680c  lea     rdx, [rbp+57h+var_78]
0x180066810  mov     rax, [rax+60h]
0x180066814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066819  mov     ebx, eax
0x18006681b  test    eax, eax
  ... truncated ...
```

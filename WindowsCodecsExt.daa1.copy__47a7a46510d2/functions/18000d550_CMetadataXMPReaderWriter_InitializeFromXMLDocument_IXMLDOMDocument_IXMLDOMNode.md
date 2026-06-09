# CMetadataXMPReaderWriter::InitializeFromXMLDocument(IXMLDOMDocument *,IXMLDOMNode * *)

- ea: `0x18000d550`
- end: `0x18000e073`
- name: `?InitializeFromXMLDocument@CMetadataXMPReaderWriter@@MEAAJPEAUIXMLDOMDocument@@PEAPEAUIXMLDOMNode@@@Z`
- size: `2851`
- prototype: `int(CMetadataXMPReaderWriter *__hidden this, struct IXMLDOMDocument *, struct IXMLDOMNode **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d550`
- `0x18000e07c`
- `0x18000e21c`
- `0x1800144bc`
- `0x180015958`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000d7cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d966`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db55`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d7cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d966`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db55`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db6b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000daa1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000dc1e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000daa1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000dc1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dac5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dc3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dac5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dc3c`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::InitializeFromXMLDocument(
        CMetadataXMPReaderWriter *this,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode **a3)
{
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  int v4; // r13d
  struct IXMLDOMDocument *v5; // r14
  HRESULT (__stdcall *get_nodeType)(IXMLDOMDocument *, DOMNodeType *); // rax
  struct IXMLDOMNode *v7; // rdi
  struct IXMLDOMNode *v8; // rsi
  int v9; // r15d
  int v10; // eax
  signed int v11; // ebx
  bool v12; // zf
  int v14; // ecx
  __int64 v15; // rdx
  int v16; // r12d
  int matched; // eax
  struct IXMLDOMNode *v18; // r14
  int v19; // eax
  int v20; // eax
  int v21; // ecx
  struct IXMLDOMNode *v22; // rsi
  int v23; // eax
  OLECHAR *v24; // rcx
  CMetadataXMPReaderWriter *v25; // rcx
  int updated; // eax
  int v27; // ecx
  const OLECHAR *v28; // rax
  __int64 v29; // rsi
  UINT v30; // eax
  struct IXMLDOMNode *v31; // rsi
  int v32; // eax
  __int64 v33; // rdx
  int v34; // ecx
  __int64 v35; // rcx
  const WCHAR *v36; // rax
  __int64 v37; // r14
  UINT v38; // eax
  int v39; // eax
  int v40; // ecx
  int v41; // ecx
  struct IXMLDOMNode *v42; // rax
  bool v43; // zf
  bool v44; // zf
  bool v45; // zf
  struct IXMLDOMNode *v46; // [rsp+38h] [rbp-39h] BYREF
  struct IXMLDOMNode *v47; // [rsp+40h] [rbp-31h]
  struct IXMLDOMNode *v48; // [rsp+48h] [rbp-29h] BYREF
  __int64 v49; // [rsp+50h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-19h] BYREF
  int v51; // [rsp+60h] [rbp-11h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-9h] BYREF
  struct IXMLDOMNode *v53; // [rsp+70h] [rbp-1h] BYREF
  int v54; // [rsp+78h] [rbp+7h] BYREF
  __int64 v55[9]; // [rsp+80h] [rbp+Fh] BYREF
  struct IXMLDOMDocument *v57; // [rsp+E0h] [rbp+6Fh] BYREF
  struct IXMLDOMNode **v58; // [rsp+E8h] [rbp+77h]
  int v59; // [rsp+F0h] [rbp+7Fh] BYREF

  v58 = a3;
  v57 = a2;
  lpVtbl = a2->lpVtbl;
  v4 = 0;
  v5 = a2;
  v51 = 0;
  v49 = 0;
  v48 = 0;
  get_nodeType = lpVtbl->get_nodeType;
  v7 = 0;
  v46 = 0;
  v8 = 0;
  v47 = 0;
  v9 = 0;
  v55[0] = 0;
  v53 = 0;
  v59 = 0;
  v54 = 0;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, int *))get_nodeType)(a2, &v51);
  v11 = v10;
  if ( v10 < 0 )
    goto LABEL_2;
  if ( v10 )
    goto LABEL_160;
  if ( v51 != 9 )
  {
    v44 = g_doStackCaptures == 0;
    v11 = -2003292271;
    goto LABEL_168;
  }
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))v5->lpVtbl->get_childNodes)(v5, &v49);
  v11 = v10;
  if ( v10 < 0 )
  {
LABEL_2:
    v12 = g_doStackCaptures == 0;
LABEL_3:
    if ( v12 )
      goto LABEL_4;
    v14 = v10;
    goto LABEL_18;
  }
  if ( v10 )
  {
LABEL_160:
    v43 = g_doStackCaptures == 0;
LABEL_161:
    if ( !v43 )
      DoStackCapture(-2147467259);
    v11 = -2147467259;
    goto LABEL_91;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v59);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = g_doStackCaptures == 0;
    goto LABEL_3;
  }
  if ( v10 )
  {
    v43 = g_doStackCaptures == 0;
    goto LABEL_161;
  }
  if ( v59 < 0 )
  {
    v44 = g_doStackCaptures == 0;
    v11 = -2003292273;
LABEL_168:
    if ( v44 )
      goto LABEL_4;
    v14 = v11;
LABEL_18:
    DoStackCapture(v14);
    goto LABEL_4;
  }
  v16 = 1;
  while ( 1 )
  {
    if ( v4 >= v59 )
    {
      if ( v49 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 16LL))(v49, v15, 0);
        v49 = 0;
      }
      if ( v53 )
        goto LABEL_139;
      v8 = v47;
      if ( !v47 )
        goto LABEL_165;
      v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *, _QWORD))v47->lpVtbl->get_childNodes)(v47, &v49, 0);
      v11 = v20;
      if ( v20 < 0 )
        goto LABEL_65;
      if ( v20 )
        goto LABEL_160;
      v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v59);
      v11 = v20;
      if ( v20 < 0 )
        goto LABEL_65;
      if ( !v20 )
      {
        if ( v59 != 1 )
        {
          v11 = -2003292273;
          if ( !g_doStackCaptures )
            goto LABEL_91;
          v21 = -2003292273;
          goto LABEL_67;
        }
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v49 + 56LL))(v49, 0, &v48);
        v11 = v20;
        if ( v20 < 0 )
        {
LABEL_65:
          if ( !g_doStackCaptures )
            goto LABEL_91;
          v21 = v20;
          goto LABEL_67;
        }
        if ( !v20 )
        {
          v31 = v48;
          pbstr = 0;
          bstrString = 0;
          LODWORD(v57) = 0;
          v32 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument **))v48->lpVtbl->get_nodeType)(
                  v48,
                  &v57);
          v11 = v32;
          if ( v32 < 0 )
            goto LABEL_107;
          if ( v32 )
          {
            if ( g_doStackCaptures )
              DoStackCapture(-2147467259);
            v11 = -2147467259;
            goto LABEL_108;
          }
          if ( (_DWORD)v57 != 8 )
          {
            v35 = 0x7FFFFFFF;
            v36 = L"RDF";
            do
            {
              if ( !*v36 )
                break;
              ++v36;
              --v35;
            }
            while ( v35 );
            v33 = 0x7FFFFFFF - v35;
            v11 = v35 == 0 ? 0x80070057 : 0;
            v37 = (0x7FFFFFFF - v35) & -(__int64)(v35 != 0);
            if ( !v35 )
            {
              if ( !g_doStackCaptures )
                goto LABEL_108;
              v34 = v35 == 0 ? 0x80070057 : 0;
              goto LABEL_116;
            }
            v32 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *, _QWORD))v31->lpVtbl->get_baseName)(
                    v31,
                    &pbstr,
                    0);
            v11 = v32;
            if ( v32 < 0 )
            {
LABEL_107:
              if ( !g_doStackCaptures )
              {
LABEL_108:
                if ( pbstr )
                {
                  SysFreeString(pbstr);
                  pbstr = 0;
                }
                if ( bstrString )
                  SysFreeString(bstrString);
                if ( v11 < 0 )
                {
LABEL_113:
                  if ( !g_doStackCaptures )
                    goto LABEL_90;
                  goto LABEL_88;
                }
                if ( v9 )
                {
                  matched = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, struct IXMLDOMNode **))v48->lpVtbl->QueryInterface)(
                              v48,
                              &IID_IXMLDOMElement,
                              &v53);
                  v11 = matched;
                  if ( matched < 0 )
                  {
                    if ( !g_doStackCaptures )
                      goto LABEL_90;
                    goto LABEL_133;
                  }
                }
                if ( v49 )
                {
                  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 16LL))(v49, v33, 0);
                  v49 = 0;
                }
                if ( v48 )
                {
                  ((void (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v48->lpVtbl->Release)(v48, v33, 0);
                  v48 = 0;
                }
                if ( v53 )
                {
LABEL_139:
                  v39 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *, _QWORD))v53->lpVtbl->get_childNodes)(
                          v53,
                          &v49,
                          0);
                  v11 = v39;
                  if ( v39 < 0 )
                    goto LABEL_140;
                  if ( !v39 )
                  {
                    v39 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v59);
                    v11 = v39;
                    if ( v39 < 0 )
                    {
LABEL_140:
                      if ( !g_doStackCaptures )
                        goto LABEL_141;
                      goto LABEL_144;
                    }
                    if ( !v39 )
                    {
                      if ( v59 < 0 )
                      {
                        v11 = -2003292273;
                        if ( !g_doStackCaptures )
                          goto LABEL_141;
                        v41 = -2003292273;
LABEL_145:
                        DoStackCapture(v41);
                        goto LABEL_141;
                      }
                      v39 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, struct IXMLDOMNode *))(*(_QWORD *)this + 392LL))(
                              this,
                              v53);
                      v11 = v39;
                      if ( v39 >= 0 )
                      {
                        v42 = v53;
                        v53 = 0;
                        *v58 = v42;
                        goto LABEL_141;
                      }
                      if ( !g_doStackCaptures )
                      {
LABEL_141:
                        v8 = v47;
                        goto LABEL_91;
                      }
LABEL_144:
                      v41 = v39;
                      goto LABEL_145;
                    }
                  }
                  v45 = g_doStackCaptures == 0;
                  goto LABEL_180;
                }
                v8 = v47;
LABEL_165:
                v11 = -2003292317;
                if ( !g_doStackCaptures )
                  goto LABEL_91;
                v21 = -2003292317;
                goto LABEL_67;
              }
              v34 = v32;
LABEL_116:
              DoStackCapture(v34);
              goto LABEL_108;
            }
            v16 = 0;
            if ( !v32 )
            {
              v38 = SysStringLen(pbstr);
              if ( CompareStringW(0x400u, 0, pbstr, v38, L"RDF", v37) == 2 )
              {
                v32 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v31->lpVtbl->get_namespaceURI)(
                        v31,
                        &bstrString);
                v11 = v32;
                if ( v32 < 0 )
                  goto LABEL_107;
                if ( !v32 )
                  v16 = XMPSchemaURIsMatch(bstrString, (wchar_t *)L"http://www.w3.org/1999/02/22-rdf-syntax-ns#");
              }
            }
          }
          v9 = v16;
          v11 = 0;
          goto LABEL_108;
        }
      }
      goto LABEL_160;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v49 + 56LL))(
            v49,
            (unsigned int)v4,
            &v48);
    if ( v11 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_90;
      goto LABEL_88;
    }
    if ( v11 )
    {
      v45 = g_doStackCaptures == 0;
LABEL_180:
      if ( !v45 )
        DoStackCapture(-2147467259);
      v11 = -2147467259;
      goto LABEL_141;
    }
    matched = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v48->lpVtbl->get_nodeType)(v48, &v51);
    v11 = matched;
    if ( matched < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_90;
      goto LABEL_133;
    }
    if ( matched )
      goto LABEL_187;
    if ( (!v4 || v4 == v59 - 1) && v51 == 7 )
    {
      v18 = v48;
      bstrString = 0;
      LODWORD(pbstr) = 0;
      v19 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v48->lpVtbl->get_nodeType)(v48, &pbstr);
      v11 = v19;
      if ( v19 < 0 )
        goto LABEL_40;
      if ( !v19 )
      {
        if ( (_DWORD)pbstr == 8 )
        {
          v9 = 1;
          goto LABEL_101;
        }
        v15 = 0x7FFFFFFF;
        v28 = L"xpacket";
        do
        {
          if ( !*v28 )
            break;
          ++v28;
          --v15;
        }
        while ( v15 );
        v11 = v15 == 0 ? 0x80070057 : 0;
        v29 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
        if ( v15 )
        {
          v19 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *, _QWORD))v18->lpVtbl->get_baseName)(
                  v18,
                  &bstrString,
                  0);
          v11 = v19;
          if ( v19 >= 0 )
          {
            v9 = 0;
            if ( !v19 )
            {
              v30 = SysStringLen(bstrString);
              v9 = CompareStringW(0x400u, 0, bstrString, v30, L"xpacket", v29) == 2;
            }
LABEL_101:
            v54 = v9;
            v11 = 0;
LABEL_41:
            if ( bstrString )
              SysFreeString(bstrString);
            if ( v11 < 0 )
            {
              if ( !g_doStackCaptures )
                goto LABEL_90;
              goto LABEL_88;
            }
            if ( !v9 )
              goto LABEL_197;
            v5 = v57;
            if ( v4 == v59 - 1 )
            {
              matched = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct IXMLDOMNode *, __int64 *))v57->lpVtbl->removeChild)(
                          v57,
                          v48,
                          v55);
              v11 = matched;
              if ( matched < 0 )
              {
                if ( !g_doStackCaptures )
                  goto LABEL_90;
LABEL_133:
                v27 = matched;
                goto LABEL_89;
              }
              if ( matched )
              {
LABEL_187:
                if ( g_doStackCaptures )
                  DoStackCapture(-2147467259);
                v11 = -2147467259;
                goto LABEL_90;
              }
              if ( v55[0] )
              {
                (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v55[0] + 16LL))(v55[0], v15, 0);
                v55[0] = 0;
              }
            }
            goto LABEL_54;
          }
LABEL_40:
          if ( !g_doStackCaptures )
            goto LABEL_41;
          v40 = v19;
        }
        else
        {
          if ( !g_doStackCaptures )
            goto LABEL_41;
          v40 = v15 == 0 ? 0x80070057 : 0;
        }
        DoStackCapture(v40);
        goto LABEL_41;
      }
      if ( g_doStackCaptures )
        DoStackCapture(-2147467259);
      v11 = -2147467259;
      goto LABEL_41;
    }
    if ( v51 != 1 )
      goto LABEL_54;
    v22 = v48;
    bstrString = 0;
    LODWORD(pbstr) = 0;
    v23 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v48->lpVtbl->get_nodeType)(v48, &pbstr);
    v11 = v23;
    if ( v23 < 0 )
    {
LABEL_71:
      if ( g_doStackCaptures )
        DoStackCapture(v23);
      goto LABEL_73;
    }
    if ( v23 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(-2147467259);
      v11 = -2147467259;
      goto LABEL_73;
    }
    if ( (_DWORD)pbstr == 8 )
    {
      v9 = 1;
    }
    else
    {
      v23 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *, _QWORD))v22->lpVtbl->get_namespaceURI)(
              v22,
              &bstrString,
              0);
      v11 = v23;
      if ( v23 < 0 )
        goto LABEL_71;
      v9 = 0;
      if ( !v23 )
        v9 = XMPSchemaURIsMatch(bstrString, (wchar_t *)L"adobe:ns:meta/");
    }
    v54 = v9;
    v11 = 0;
LABEL_73:
    v24 = bstrString;
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v11 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_90;
LABEL_88:
      v27 = v11;
LABEL_89:
      DoStackCapture(v27);
      goto LABEL_90;
    }
    if ( v9 )
    {
      v8 = v47;
      if ( v47 )
        goto LABEL_165;
      if ( *((_DWORD *)this + 42) && CMetadataXMPReaderWriter::CheckXMPMetadataName(v24, v48) )
      {
        updated = CMetadataXMPReaderWriter::UpdateXMPMetadataNode(v25, v5, v48, &v46);
        v11 = updated;
        if ( updated < 0 )
        {
          if ( !g_doStackCaptures )
            goto LABEL_91;
          v21 = updated;
LABEL_67:
          DoStackCapture(v21);
          goto LABEL_91;
        }
        if ( v48 )
          ((void (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v48->lpVtbl->Release)(v48, v15, 0);
        v48 = v46;
        if ( v46 )
          ((void (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v46->lpVtbl->AddRef)(v46, v15, 0);
      }
      v47 = v48;
      goto LABEL_56;
    }
    matched = MatchNodeByUriAndName(v48, L"http://www.w3.org/1999/02/22-rdf-syntax-ns#", L"RDF", &v54);
    v11 = matched;
    if ( matched < 0 )
    {
      if ( g_doStackCaptures )
        goto LABEL_133;
      goto LABEL_90;
    }
    v9 = v54;
    if ( v54 )
    {
      if ( v53 )
      {
LABEL_197:
        v11 = -2003292317;
        goto LABEL_113;
      }
      matched = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, struct IXMLDOMNode **))v48->lpVtbl->QueryInterface)(
                  v48,
                  &IID_IXMLDOMElement,
                  &v53);
      v11 = matched;
      if ( matched < 0 )
        break;
    }
LABEL_54:
    if ( !v48 )
      goto LABEL_57;
    ((void (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v48->lpVtbl->Release)(v48, v15, 0);
LABEL_56:
    v48 = 0;
LABEL_57:
    ++v4;
  }
  if ( g_doStackCaptures )
    goto LABEL_133;
LABEL_90:
  v8 = v47;
LABEL_91:
  v7 = v46;
LABEL_4:
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v48 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v48->lpVtbl->Release)(v48);
    v48 = 0;
  }
  if ( v55[0] )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55[0] + 16LL))(v55[0]);
    v55[0] = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  if ( v53 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v53->lpVtbl->Release)(v53);
    v53 = 0;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d550  mov     rax, rsp
0x18000d553  mov     [rax+18h], r8
0x18000d557  mov     [rax+10h], rdx
0x18000d55b  mov     [rax+8], rcx
0x18000d55f  push    rbp
0x18000d560  push    rbx
0x18000d561  push    rsi
0x18000d562  push    rdi
0x18000d563  push    r12
0x18000d565  push    r13
0x18000d567  push    r14
0x18000d569  push    r15
0x18000d56b  lea     rbp, [rax-5Fh]
0x18000d56f  sub     rsp, 88h
0x18000d576  mov     rax, [rdx]
0x18000d579  xor     r13d, r13d
0x18000d57c  mov     r14, rdx
0x18000d57f  mov     [rbp+57h+var_68], r13d
0x18000d583  lea     rdx, [rbp+57h+var_68]
0x18000d587  mov     [rbp+57h+var_78], r13
0x18000d58b  mov     rcx, r14
0x18000d58e  mov     [rbp+57h+var_80], r13
0x18000d592  mov     rax, [rax+50h]
0x18000d596  mov     edi, r13d
0x18000d599  mov     [rbp+57h+var_90], r13
0x18000d59d  mov     esi, r13d
0x18000d5a0  mov     [rbp+57h+var_88], r13
0x18000d5a4  mov     r15d, r13d
0x18000d5a7  mov     [rbp+57h+var_48], r13
0x18000d5ab  mov     [rbp+57h+var_58], r13
0x18000d5af  mov     [rbp+57h+arg_18], r13d
0x18000d5b3  mov     [rbp+57h+var_50], r13d
0x18000d5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5bc  mov     ebx, eax
0x18000d5be  test    eax, eax
0x18000d5c0  jns     loc_18000D681
0x18000d5c6  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000d5cd  jnz     loc_18000D675
0x18000d5d3  mov     rcx, [rbp+57h+var_78]
0x18000d5d7  test    rcx, rcx
0x18000d5da  jz      short loc_18000D5EC
0x18000d5dc  mov     rax, [rcx]
0x18000d5df  mov     rax, [rax+10h]
0x18000d5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5e8  mov     [rbp+57h+var_78], r13
0x18000d5ec  mov     rcx, [rbp+57h+var_80]
0x18000d5f0  test    rcx, rcx
0x18000d5f3  jz      short loc_18000D605
0x18000d5f5  mov     rax, [rcx]
0x18000d5f8  mov     rax, [rax+10h]
0x18000d5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d601  mov     [rbp+57h+var_80], r13
0x18000d605  mov     rcx, [rbp+57h+var_48]
0x18000d609  test    rcx, rcx
0x18000d60c  jz      short loc_18000D61E
0x18000d60e  mov     rax, [rcx]
0x18000d611  mov     rax, [rax+10h]
0x18000d615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61a  mov     [rbp+57h+var_48], r13
0x18000d61e  test    rsi, rsi
0x18000d621  jz      short loc_18000D632
0x18000d623  mov     rax, [rsi]
0x18000d626  mov     rcx, rsi
0x18000d629  mov     rax, [rax+10h]
0x18000d62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d632  mov     rcx, [rbp+57h+var_58]
0x18000d636  test    rcx, rcx
0x18000d639  jz      short loc_18000D64B
0x18000d63b  mov     rax, [rcx]
0x18000d63e  mov     rax, [rax+10h]
0x18000d642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d647  mov     [rbp+57h+var_58], r13
0x18000d64b  test    rdi, rdi
0x18000d64e  jz      short loc_18000D65F
0x18000d650  mov     rcx, [rdi]
0x18000d653  mov     rax, [rcx+10h]
0x18000d657  mov     rcx, rdi
0x18000d65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d65f  mov     eax, ebx
0x18000d661  add     rsp, 88h
0x18000d668  pop     r15
0x18000d66a  pop     r14
0x18000d66c  pop     r13
0x18000d66e  pop     r12
0x18000d670  pop     rdi
0x18000d671  pop     rsi
0x18000d672  pop     rbx
0x18000d673  pop     rbp
0x18000d674  retn
0x18000d675  mov     ecx, eax; int
0x18000d677  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d67c  jmp     loc_18000D5D3
0x18000d681  jnz     loc_18000DE29
0x18000d687  cmp     [rbp+57h+var_68], 9
0x18000d68b  jnz     loc_18000E016
0x18000d691  mov     rax, [r14]
0x18000d694  lea     rdx, [rbp+57h+var_78]
0x18000d698  mov     rcx, r14
0x18000d69b  mov     rax, [rax+60h]
0x18000d69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a4  mov     ebx, eax
0x18000d6a6  test    eax, eax
0x18000d6a8  js      loc_18000D5C6
0x18000d6ae  jnz     loc_18000DE29
0x18000d6b4  mov     rcx, [rbp+57h+var_78]
0x18000d6b8  lea     rdx, [rbp+57h+arg_18]
0x18000d6bc  mov     rax, [rcx]
0x18000d6bf  mov     rax, [rax+40h]
0x18000d6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c8  xor     r8d, r8d
0x18000d6cb  mov     ebx, eax
0x18000d6cd  test    eax, eax
0x18000d6cf  jns     short loc_18000D6DD
0x18000d6d1  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d6d8  jmp     loc_18000D5CD
0x18000d6dd  jnz     loc_18000E027
0x18000d6e3  cmp     [rbp+57h+arg_18], r8d
0x18000d6e7  jl      loc_18000DE60
0x18000d6ed  mov     edi, 80004005h
0x18000d6f2  mov     r12d, 1
0x18000d6f8  mov     esi, 7FFFFFFFh
0x18000d6fd  mov     rcx, [rbp+57h+var_78]
0x18000d701  cmp     r13d, [rbp+57h+arg_18]
0x18000d705  jge     loc_18000D884
0x18000d70b  mov     rax, [rcx]
0x18000d70e  lea     r8, [rbp+57h+var_80]
0x18000d712  mov     edx, r13d
0x18000d715  mov     rax, [rax+38h]
0x18000d719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d71e  mov     ebx, eax
0x18000d720  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000d726  test    ebx, ebx
0x18000d728  jns     short loc_18000D73A
0x18000d72a  test    eax, eax
0x18000d72c  jnz     loc_18000DA0A
0x18000d732  test    ebx, ebx
0x18000d734  js      loc_18000DA11
0x18000d73a  jnz     loc_18000E069
0x18000d740  mov     rcx, [rbp+57h+var_80]
0x18000d744  lea     rdx, [rbp+57h+var_68]
0x18000d748  mov     rax, [rcx]
0x18000d74b  mov     rax, [rax+50h]
0x18000d74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d754  xor     r8d, r8d
0x18000d757  mov     ebx, eax
0x18000d759  test    eax, eax
0x18000d75b  jns     short loc_18000D772
0x18000d75d  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d764  jnz     loc_18000DCC2
0x18000d76a  test    eax, eax
0x18000d76c  js      loc_18000DA11
0x18000d772  jnz     loc_18000DF15
0x18000d778  test    r13d, r13d
0x18000d77b  jnz     loc_18000D90C
0x18000d781  cmp     [rbp+57h+var_68], 7
0x18000d785  jnz     loc_18000D91A
0x18000d78b  mov     r14, [rbp+57h+var_80]
0x18000d78f  lea     rdx, [rbp+57h+pbstr]
0x18000d793  mov     rcx, r14
0x18000d796  mov     [rbp+57h+bstrString], r8
0x18000d79a  mov     dword ptr [rbp+57h+pbstr], r8d
0x18000d79e  mov     rax, [r14]
0x18000d7a1  mov     rax, [rax+50h]
0x18000d7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7aa  xor     r8d, r8d
0x18000d7ad  mov     ebx, eax
0x18000d7af  test    eax, eax
0x18000d7b1  jns     loc_18000DA21
0x18000d7b7  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d7be  jnz     loc_18000DD3A
0x18000d7c4  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000d7c8  test    rcx, rcx
0x18000d7cb  jz      short loc_18000D7D6
0x18000d7cd  call    cs:__imp_SysFreeString
0x18000d7d3  xor     r8d, r8d
0x18000d7d6  test    ebx, ebx
0x18000d7d8  jns     short loc_18000D7EF
0x18000d7da  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d7e1  jnz     loc_18000DA0A
0x18000d7e7  test    ebx, ebx
0x18000d7e9  js      loc_18000DA11
0x18000d7ef  test    r15d, r15d
0x18000d7f2  jz      loc_18000DF99
0x18000d7f8  mov     eax, [rbp+57h+arg_18]
0x18000d7fb  mov     r14, [rbp+57h+arg_8]
0x18000d7ff  dec     eax
0x18000d801  cmp     r13d, eax
0x18000d804  jnz     short loc_18000D860
0x18000d806  mov     rax, [r14]
0x18000d809  lea     r8, [rbp+57h+var_48]
0x18000d80d  mov     rdx, [rbp+57h+var_80]
0x18000d811  mov     rcx, r14
0x18000d814  mov     rax, [rax+0A0h]
0x18000d81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d820  xor     r8d, r8d
0x18000d823  mov     ebx, eax
0x18000d825  test    eax, eax
0x18000d827  jns     short loc_18000D83E
0x18000d829  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d830  jnz     loc_18000DCC2
0x18000d836  test    eax, eax
0x18000d838  js      loc_18000DA11
0x18000d83e  jnz     loc_18000DF15
0x18000d844  mov     rcx, [rbp+57h+var_48]
0x18000d848  test    rcx, rcx
0x18000d84b  jz      short loc_18000D860
0x18000d84d  mov     rax, [rcx]
0x18000d850  mov     rax, [rax+10h]
0x18000d854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d859  xor     r8d, r8d
0x18000d85c  mov     [rbp+57h+var_48], r8
0x18000d860  mov     rcx, [rbp+57h+var_80]
0x18000d864  test    rcx, rcx
0x18000d867  jz      short loc_18000D87C
0x18000d869  mov     rax, [rcx]
0x18000d86c  mov     rax, [rax+10h]
0x18000d870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d875  xor     r8d, r8d
0x18000d878  mov     [rbp+57h+var_80], r8
0x18000d87c  add     r13d, r12d
0x18000d87f  jmp     loc_18000D6F8
0x18000d884  test    rcx, rcx
0x18000d887  jz      short loc_18000D89C
0x18000d889  mov     rax, [rcx]
0x18000d88c  mov     rax, [rax+10h]
0x18000d890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d895  xor     r8d, r8d
0x18000d898  mov     [rbp+57h+var_78], r8
0x18000d89c  cmp     [rbp+57h+var_58], r8
0x18000d8a0  jnz     loc_18000DD0B
0x18000d8a6  mov     rsi, [rbp+57h+var_88]
0x18000d8aa  test    rsi, rsi
0x18000d8ad  jz      loc_18000DE42
0x18000d8b3  mov     rax, [rsi]
0x18000d8b6  lea     rdx, [rbp+57h+var_78]
0x18000d8ba  mov     rcx, rsi
0x18000d8bd  mov     rax, [rax+60h]
0x18000d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c6  xor     r13d, r13d
0x18000d8c9  mov     ebx, eax
0x18000d8cb  test    eax, eax
0x18000d8cd  js      short loc_18000D8F3
0x18000d8cf  jnz     loc_18000DE2E
0x18000d8d5  mov     rcx, [rbp+57h+var_78]
0x18000d8d9  lea     rdx, [rbp+57h+arg_18]
0x18000d8dd  mov     rax, [rcx]
0x18000d8e0  mov     rax, [rax+40h]
0x18000d8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8e9  mov     ebx, eax
0x18000d8eb  test    eax, eax
0x18000d8ed  jns     loc_18000DAE1
0x18000d8f3  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18000d8fa  jz      loc_18000DA18
0x18000d900  mov     ecx, eax; int
0x18000d902  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d907  jmp     loc_18000DA18
0x18000d90c  mov     eax, [rbp+57h+arg_18]
0x18000d90f  dec     eax
0x18000d911  cmp     r13d, eax
0x18000d914  jz      loc_18000D781
0x18000d91a  cmp     [rbp+57h+var_68], r12d
0x18000d91e  jnz     loc_18000D860
0x18000d924  mov     rsi, [rbp+57h+var_80]
0x18000d928  lea     rdx, [rbp+57h+pbstr]
0x18000d92c  mov     rcx, rsi
0x18000d92f  mov     [rbp+57h+bstrString], r8
0x18000d933  mov     dword ptr [rbp+57h+pbstr], r8d
0x18000d937  mov     rax, [rsi]
0x18000d93a  mov     rax, [rax+50h]
0x18000d93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d943  xor     r8d, r8d
0x18000d946  mov     ebx, eax
0x18000d948  test    eax, eax
0x18000d94a  jns     loc_18000DDC0
0x18000d950  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d957  jnz     loc_18000DE1A
0x18000d95d  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000d961  test    rcx, rcx
0x18000d964  jz      short loc_18000D96F
0x18000d966  call    cs:__imp_SysFreeString
0x18000d96c  xor     r8d, r8d
0x18000d96f  test    ebx, ebx
0x18000d971  jns     short loc_18000D988
0x18000d973  cmp     cs:?g_doStackCaptures@@3HA, r8d; int g_doStackCaptures
0x18000d97a  jnz     loc_18000DA0A
0x18000d980  test    ebx, ebx
0x18000d982  js      loc_18000DA11
0x18000d988  test    r15d, r15d
0x18000d98b  jz      loc_18000DF4D
0x18000d991  mov     rsi, [rbp+57h+var_88]
0x18000d995  test    rsi, rsi
0x18000d998  jnz     loc_18000DE42
0x18000d99e  mov     rax, [rbp+57h+arg_0]
0x18000d9a2  cmp     [rax+0A8h], r8d
0x18000d9a9  jz      short loc_18000D9FD
0x18000d9ab  mov     rdx, [rbp+57h+var_80]; struct IXMLDOMNode *
0x18000d9af  call    ?CheckXMPMetadataName@CMetadataXMPReaderWriter@@IEAAHPEAUIXMLDOMNode@@@Z; CMetadataXMPReaderWriter::CheckXMPMetadataName(IXMLDOMNode *)
0x18000d9b4  xor     r8d, r8d
0x18000d9b7  test    eax, eax
0x18000d9b9  jz      short loc_18000D9FD
  ... truncated ...
```

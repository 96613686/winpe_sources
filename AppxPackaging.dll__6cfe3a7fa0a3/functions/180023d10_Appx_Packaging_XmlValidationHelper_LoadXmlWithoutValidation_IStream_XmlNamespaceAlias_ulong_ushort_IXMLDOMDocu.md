# Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(IStream *,XmlNamespaceAlias *,ulong,ushort * *,IXMLDOMDocument * *,IXMLDOMDocument * *)

- ea: `0x180023d10`
- end: `0x180024339`
- name: `?LoadXmlWithoutValidation@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUXmlNamespaceAlias@@KPEAPEAGPEAPEAUIXMLDOMDocument@@3@Z`
- size: `1577`
- prototype: `__int64 __usercall@<rax>(struct IStream *this@<rcx>, struct XmlNamespaceAlias *@<rdx>, unsigned int@<r8d>, unsigned __int16 **@<r9>, struct IXMLDOMDocument **, struct IXMLDOMDocument **)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022054`
- `0x180058b00`
- `0x18008e120`

## callees

- `0x180005eb8`
- `0x180009eb8`
- `0x18000b254`
- `0x1800133fc`
- `0x180023d10`
- `0x180024c74`
- `0x18006bf44`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002411d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002430d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002411d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002430d`

## string_xrefs

- `0x180023ee2`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180023f3a`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180023f65`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180023f86`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180024010`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x18002403c`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x18002410d`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x1800241cf`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x1800242fd`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(
        struct IStream *this,
        struct XmlNamespaceAlias *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        struct IXMLDOMDocument **a5,
        struct IXMLDOMDocument **a6)
{
  struct IXMLDOMDocument **v10; // r12
  int v11; // eax
  unsigned int v12; // ebx
  int XmlDocument; // eax
  unsigned int v14; // r8d
  struct IXMLDOMDocument2 *v15; // rdi
  struct IXMLDOMDocument **v16; // r14
  struct IXMLDOMDocument2 *v17; // rbx
  int v18; // eax
  int v19; // eax
  struct IXMLDOMDocument2Vtbl *v20; // rax
  int v21; // eax
  unsigned int v22; // r15d
  int v23; // eax
  unsigned int v24; // esi
  __int64 v26; // rdx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  HRESULT (__stdcall *v30)(IXMLDOMDocument2 *, IXMLDOMParseError **); // rbx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 *v34; // rcx
  int v35; // ecx
  HRESULT (__stdcall *get_parseError)(IXMLDOMDocument2 *, IXMLDOMParseError **); // rbx
  int v37; // eax
  __int64 v38; // rdx
  int v39; // ecx
  __int64 v40; // r9
  int v41; // [rsp+20h] [rbp-79h]
  __int64 v42; // [rsp+30h] [rbp-69h] BYREF
  __int64 v43; // [rsp+38h] [rbp-61h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-59h] BYREF
  BSTR v45; // [rsp+48h] [rbp-51h] BYREF
  struct IXMLDOMDocument2 *v46; // [rsp+50h] [rbp-49h] BYREF
  int v47; // [rsp+58h] [rbp-41h] BYREF
  int v48; // [rsp+5Ch] [rbp-3Dh] BYREF
  int v49; // [rsp+60h] [rbp-39h] BYREF
  int v50; // [rsp+64h] [rbp-35h] BYREF
  int v51; // [rsp+68h] [rbp-31h] BYREF
  int v52; // [rsp+6Ch] [rbp-2Dh] BYREF
  struct IXMLDOMDocument2 *v53[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v54; // [rsp+80h] [rbp-19h] BYREF
  struct IStream *v55; // [rsp+88h] [rbp-11h]
  __int64 v56; // [rsp+90h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]
  __int16 v58; // [rsp+F0h] [rbp+57h] BYREF

  if ( !this )
  {
    v29 = 493;
LABEL_43:
    v12 = -2147024809;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)v12,
      v41);
    return v12;
  }
  if ( !a2 )
  {
    v29 = 494;
    goto LABEL_43;
  }
  if ( !a3 )
  {
    v29 = 495;
    goto LABEL_43;
  }
  v10 = a5;
  if ( !a5 )
  {
    v29 = 496;
    goto LABEL_43;
  }
  v11 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 40LL))(this, 0, 0, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\lib\\Core\\src\\StreamHelper.hpp",
      (const char *)(unsigned int)v11,
      v41);
    v29 = 498;
    goto LABEL_44;
  }
  v53[0] = 0;
  v46 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v53);
  XmlDocument = Appx::Packaging::XmlValidationHelper::CreateXmlDocument((LPVOID *)v53);
  v12 = XmlDocument;
  if ( XmlDocument < 0 )
  {
    v28 = 502;
    goto LABEL_40;
  }
  v14 = a3;
  v15 = v53[0];
  v12 = Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(v53[0], a2, v14);
  if ( (v12 & 0x80000000) != 0 )
  {
    v26 = 503;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)v12,
      v41);
    if ( !v15 )
      return v12;
    goto LABEL_29;
  }
  v58 = 0;
  if ( !a4 )
  {
    v56 = 0;
    lpVtbl = v15->lpVtbl;
    v54 = 13;
    v55 = this;
    XmlDocument = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *, __int16 *))lpVtbl->load)(
                    v15,
                    &v54,
                    &v58);
    v12 = XmlDocument;
    if ( XmlDocument >= 0 )
      goto LABEL_10;
    v28 = 519;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)XmlDocument,
      v41);
LABEL_83:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v53);
    return v12;
  }
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, __int16 *))v15->lpVtbl->loadXML)(v15, *a4, &v58);
  if ( (v12 & 0x80000000) != 0 )
  {
    v26 = 511;
    goto LABEL_31;
  }
LABEL_10:
  if ( v12 == 1 || !v58 )
  {
    v43 = 0;
    v52 = 0;
    v51 = 0;
    v50 = 0;
    v45 = 0;
    get_parseError = v15->lpVtbl->get_parseError;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
    v37 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))get_parseError)(v15, &v43);
    v12 = v37;
    if ( v37 >= 0 )
    {
      v37 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 56LL))(v43, &v52);
      v12 = v37;
      if ( v37 >= 0 )
      {
        v37 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 88LL))(v43, &v51);
        v12 = v37;
        if ( v37 >= 0 )
        {
          v37 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 96LL))(v43, &v50);
          v12 = v37;
          if ( v37 >= 0 )
          {
            v37 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v43 + 72LL))(v43, &v45);
            v12 = v37;
            if ( v37 >= 0 )
            {
              if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
                McTemplateU0dqqz_EventWriteTransfer(
                  v39,
                  (unsigned int)&EVENT_MANIFEST_XML_PARSING_ERROR,
                  v52,
                  v51,
                  v50,
                  (__int64)v45);
              v12 = -2146958844;
              v38 = 537;
              v40 = 2148008452LL;
              goto LABEL_81;
            }
            v38 = 535;
          }
          else
          {
            v38 = 534;
          }
        }
        else
        {
          v38 = 533;
        }
      }
      else
      {
        v38 = 532;
      }
    }
    else
    {
      v38 = 531;
    }
    v40 = (unsigned int)v37;
LABEL_81:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)v40,
      v41);
    SysFreeString(v45);
    v34 = &v43;
    goto LABEL_82;
  }
  v16 = a6;
  v17 = 0;
  if ( !a6 )
  {
LABEL_18:
    v23 = Appx::Packaging::SetStreamPosition(this, 0);
    v24 = v23;
    if ( v23 >= 0 )
    {
      *v10 = (struct IXMLDOMDocument *)v15;
      if ( v16 )
      {
        *v16 = (struct IXMLDOMDocument *)v17;
      }
      else if ( v17 )
      {
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v17->lpVtbl->Release)(v17);
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v23,
      v41);
    v12 = v24;
    goto LABEL_83;
  }
  v18 = Appx::Packaging::SetStreamPosition(this, 0);
  v12 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v18,
      v41);
    if ( !v15 )
      return v12;
LABEL_29:
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v15->lpVtbl->Release)(v15);
    return v12;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
  v19 = Appx::Packaging::XmlValidationHelper::CreateXmlDocument((LPVOID *)&v46);
  v12 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v19,
      v41);
    if ( v46 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v46->lpVtbl->Release)(v46);
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v15->lpVtbl->Release)(v15);
    return v12;
  }
  v17 = v46;
  v56 = 0;
  v54 = 0;
  v55 = this;
  v20 = v46->lpVtbl;
  LOWORD(v54) = 13;
  v21 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *, __int16 *))v20->load)(v46, &v54, &v58);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( v21 != 1 && v58 )
      goto LABEL_18;
    v42 = 0;
    v49 = 0;
    v48 = 0;
    v47 = 0;
    bstrString = 0;
    v30 = v15->lpVtbl->get_parseError;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
    v31 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))v30)(v15, &v42);
    v12 = v31;
    if ( v31 >= 0 )
    {
      v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 56LL))(v42, &v49);
      v12 = v31;
      if ( v31 >= 0 )
      {
        v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 88LL))(v42, &v48);
        v12 = v31;
        if ( v31 >= 0 )
        {
          v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 96LL))(v42, &v47);
          v12 = v31;
          if ( v31 >= 0 )
          {
            v31 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v42 + 72LL))(v42, &bstrString);
            v12 = v31;
            if ( v31 >= 0 )
            {
              if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
                McTemplateU0dqqz_EventWriteTransfer(
                  v35,
                  (unsigned int)&EVENT_MANIFEST_XML_PARSING_ERROR,
                  v49,
                  v48,
                  v47,
                  (__int64)bstrString);
              v12 = -2146958844;
              v32 = 565;
              v33 = 2148008452LL;
              goto LABEL_55;
            }
            v32 = 563;
          }
          else
          {
            v32 = 562;
          }
        }
        else
        {
          v32 = 561;
        }
      }
      else
      {
        v32 = 560;
      }
    }
    else
    {
      v32 = 559;
    }
    v33 = (unsigned int)v31;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)v33,
      v41);
    SysFreeString(bstrString);
    v34 = &v42;
LABEL_82:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v34);
    goto LABEL_83;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x224,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
    (const char *)(unsigned int)v21,
    v41);
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v17->lpVtbl->Release)(v17);
  if ( v15 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v15->lpVtbl->Release)(v15);
  return v22;
}

```

## disassembly

```asm
0x180023d10  push    rbp
0x180023d12  push    rbx
0x180023d13  push    rsi
0x180023d14  push    rdi
0x180023d15  push    r12
0x180023d17  push    r13
0x180023d19  push    r14
0x180023d1b  push    r15
0x180023d1d  lea     rbp, [rsp-0Fh]
0x180023d22  sub     rsp, 0A8h
0x180023d29  xor     r13d, r13d
0x180023d2c  mov     r15, r9
0x180023d2f  mov     edi, r8d
0x180023d32  mov     r14, rdx
0x180023d35  mov     rsi, rcx
0x180023d38  test    rcx, rcx
0x180023d3b  jz      loc_18002402E
0x180023d41  test    rdx, rdx
0x180023d44  jz      loc_180024050
0x180023d4a  test    r8d, r8d
0x180023d4d  jz      loc_180024057
0x180023d53  mov     r12, [rbp+47h+arg_20]
0x180023d57  test    r12, r12
0x180023d5a  jz      loc_18002405E
0x180023d60  mov     rax, [rcx]
0x180023d63  mov     edx, r13d
0x180023d66  xor     r9d, r9d
0x180023d69  xor     r8d, r8d
0x180023d6c  mov     rax, [rax+28h]
0x180023d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d75  mov     ebx, eax
0x180023d77  test    eax, eax
0x180023d79  js      loc_180024065
0x180023d7f  lea     rcx, [rbp+47h+var_70]
0x180023d83  mov     [rbp+47h+var_70], r13
0x180023d87  mov     [rbp+47h+var_90], r13
0x180023d8b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180023d90  lea     rcx, [rbp+47h+var_70]; struct IXMLDOMDocument2 **
0x180023d94  call    ?CreateXmlDocument@XmlValidationHelper@Packaging@Appx@@SAJPEAPEAUIXMLDOMDocument2@@@Z; Appx::Packaging::XmlValidationHelper::CreateXmlDocument(IXMLDOMDocument2 * *)
0x180023d99  mov     ebx, eax
0x180023d9b  test    eax, eax
0x180023d9d  js      loc_180024084
0x180023da3  mov     r8d, edi; unsigned int
0x180023da6  mov     rdx, r14; struct XmlNamespaceAlias *
0x180023da9  mov     rdi, [rbp+47h+var_70]
0x180023dad  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180023db0  call    ?SetSelectionNamespaces@XmlValidationHelper@Packaging@Appx@@SAJPEAUIXMLDOMDocument2@@PEAUXmlNamespaceAlias@@K@Z; Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(IXMLDOMDocument2 *,XmlNamespaceAlias *,ulong)
0x180023db5  mov     ebx, eax
0x180023db7  test    eax, eax
0x180023db9  js      loc_180024024
0x180023dbf  mov     [rbp+47h+arg_0], r13w
0x180023dc4  lea     ecx, [r13+0Dh]
0x180023dc8  lea     r8, [rbp+47h+arg_0]
0x180023dcc  test    r15, r15
0x180023dcf  jz      loc_180023FCA
0x180023dd5  mov     rax, [rdi]
0x180023dd8  mov     rcx, rdi
0x180023ddb  mov     rdx, [r15]
0x180023dde  mov     rax, [rax+208h]
0x180023de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dea  mov     ebx, eax
0x180023dec  test    eax, eax
0x180023dee  js      loc_180023F5C
0x180023df4  cmp     ebx, 1
0x180023df7  jz      loc_1800241F2
0x180023dfd  cmp     [rbp+47h+arg_0], r13w
0x180023e02  jz      loc_1800241F2
0x180023e08  mov     r14, [rbp+47h+arg_28]
0x180023e0c  mov     rbx, r13
0x180023e0f  test    r14, r14
0x180023e12  jz      loc_180023EA5
0x180023e18  xor     edx, edx; struct IStream *
0x180023e1a  mov     rcx, rsi; this
0x180023e1d  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x180023e22  mov     ebx, eax
0x180023e24  test    eax, eax
0x180023e26  js      loc_180023F36
0x180023e2c  lea     rcx, [rbp+47h+var_90]
0x180023e30  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180023e35  lea     rcx, [rbp+47h+var_90]; struct IXMLDOMDocument2 **
0x180023e39  call    ?CreateXmlDocument@XmlValidationHelper@Packaging@Appx@@SAJPEAPEAUIXMLDOMDocument2@@@Z; Appx::Packaging::XmlValidationHelper::CreateXmlDocument(IXMLDOMDocument2 * *)
0x180023e3e  mov     ebx, eax
0x180023e40  test    eax, eax
0x180023e42  js      loc_180023EDE
0x180023e48  mov     rbx, [rbp+47h+var_90]
0x180023e4c  lea     r8, [rbp+47h+arg_0]
0x180023e50  xor     eax, eax
0x180023e52  lea     rdx, [rbp+47h+var_60]
0x180023e56  xorps   xmm0, xmm0
0x180023e59  mov     [rbp+47h+var_50], rax
0x180023e5d  movups  [rbp+47h+var_60], xmm0
0x180023e61  mov     qword ptr [rbp+47h+var_60+8], rsi
0x180023e65  lea     ecx, [rax+0Dh]
0x180023e68  mov     rax, [rbx]
0x180023e6b  mov     word ptr [rbp+47h+var_60], cx
0x180023e6f  mov     rcx, rbx
0x180023e72  movups  xmm0, [rbp+47h+var_60]
0x180023e76  mov     rax, [rax+1D0h]
0x180023e7d  movaps  [rbp+47h+var_60], xmm0
0x180023e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e86  mov     r15d, eax
0x180023e89  test    eax, eax
0x180023e8b  js      loc_180023F82
0x180023e91  cmp     eax, 1
0x180023e94  jz      loc_18002408B
0x180023e9a  cmp     [rbp+47h+arg_0], r13w
0x180023e9f  jz      loc_18002408B
0x180023ea5  xor     edx, edx; struct IStream *
0x180023ea7  mov     rcx, rsi; this
0x180023eaa  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x180023eaf  mov     esi, eax
0x180023eb1  test    eax, eax
0x180023eb3  js      loc_1800241CB
0x180023eb9  mov     [r12], rdi
0x180023ebd  test    r14, r14
0x180023ec0  jnz     loc_1800241EA
0x180023ec6  test    rbx, rbx
0x180023ec9  jz      short loc_180023EDA
0x180023ecb  mov     rax, [rbx]
0x180023ece  mov     rcx, rbx
0x180023ed1  mov     rax, [rax+10h]
0x180023ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eda  xor     eax, eax
0x180023edc  jmp     short loc_180023F21
0x180023ede  mov     rcx, [rbp+4Fh]; this
0x180023ee2  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180023ee9  mov     r9d, ebx; char *
0x180023eec  mov     edx, 21Fh; void *
0x180023ef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ef6  mov     rcx, [rbp+47h+var_90]
0x180023efa  test    rcx, rcx
0x180023efd  jz      short loc_180023F0B
0x180023eff  mov     rdx, [rcx]
0x180023f02  mov     rax, [rdx+10h]
0x180023f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f0b  test    rdi, rdi
0x180023f0e  jz      short loc_180023F1F
0x180023f10  mov     rax, [rdi]
0x180023f13  mov     rax, [rax+10h]
0x180023f17  mov     rcx, rdi
0x180023f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f1f  mov     eax, ebx
0x180023f21  add     rsp, 0A8h
0x180023f28  pop     r15
0x180023f2a  pop     r14
0x180023f2c  pop     r13
0x180023f2e  pop     r12
0x180023f30  pop     rdi
0x180023f31  pop     rsi
0x180023f32  pop     rbx
0x180023f33  pop     rbp
0x180023f34  retn
0x180023f36  mov     rcx, [rbp+4Fh]; this
0x180023f3a  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180023f41  mov     r9d, ebx; char *
0x180023f44  mov     edx, 21Eh; void *
0x180023f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f4e  test    rdi, rdi
0x180023f51  jz      short loc_180023F1F
0x180023f53  mov     rdx, [rdi]
0x180023f56  mov     rax, [rdx+10h]
0x180023f5a  jmp     short loc_180023F17
0x180023f5c  mov     edx, 1FFh; void *
0x180023f61  mov     rcx, [rbp+4Fh]; this
0x180023f65  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180023f6c  mov     r9d, ebx; char *
0x180023f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f74  test    rdi, rdi
0x180023f77  jz      short loc_180023F1F
0x180023f79  mov     rcx, [rdi]
0x180023f7c  mov     rax, [rcx+10h]
0x180023f80  jmp     short loc_180023F17
0x180023f82  mov     rcx, [rbp+4Fh]; this
0x180023f86  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180023f8d  mov     r9d, r15d; char *
0x180023f90  mov     edx, 224h; void *
0x180023f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f9a  test    rbx, rbx
0x180023f9d  jz      short loc_180023FAE
0x180023f9f  mov     rcx, [rbx]
0x180023fa2  mov     rax, [rcx+10h]
0x180023fa6  mov     rcx, rbx
0x180023fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fae  test    rdi, rdi
0x180023fb1  jz      short loc_180023FC2
0x180023fb3  mov     rax, [rdi]
0x180023fb6  mov     rcx, rdi
0x180023fb9  mov     rax, [rax+10h]
0x180023fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fc2  mov     eax, r15d
0x180023fc5  jmp     loc_180023F21
0x180023fca  xor     eax, eax
0x180023fcc  lea     rdx, [rbp+47h+var_60]
0x180023fd0  xorps   xmm0, xmm0
0x180023fd3  mov     [rbp+47h+var_50], rax
0x180023fd7  mov     rax, [rdi]
0x180023fda  movups  [rbp+47h+var_60], xmm0
0x180023fde  mov     word ptr [rbp+47h+var_60], cx
0x180023fe2  mov     rcx, rdi
0x180023fe5  mov     qword ptr [rbp+47h+var_60+8], rsi
0x180023fe9  movups  xmm0, [rbp+47h+var_60]
0x180023fed  mov     rax, [rax+1D0h]
0x180023ff4  movaps  [rbp+47h+var_60], xmm0
0x180023ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ffd  mov     ebx, eax
0x180023fff  test    eax, eax
0x180024001  jns     loc_180023DF4
0x180024007  mov     edx, 207h; void *
0x18002400c  mov     rcx, [rbp+4Fh]; this
0x180024010  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180024017  mov     r9d, eax; char *
0x18002401a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002401f  jmp     loc_180024322
0x180024024  mov     edx, 1F7h
0x180024029  jmp     loc_180023F61
0x18002402e  mov     edx, 1EDh; void *
0x180024033  mov     ebx, 80070057h
0x180024038  mov     rcx, [rbp+4Fh]; this
0x18002403c  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180024043  mov     r9d, ebx; char *
0x180024046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002404b  jmp     loc_180023F1F
0x180024050  mov     edx, 1EEh
0x180024055  jmp     short loc_180024033
0x180024057  mov     edx, 1EFh
0x18002405c  jmp     short loc_180024033
0x18002405e  mov     edx, 1F0h
0x180024063  jmp     short loc_180024033
0x180024065  mov     rcx, [rbp+4Fh]; this
0x180024069  lea     r8, aOnecorePrintsc_19; "onecore\\printscan\\AppxPackaging\\lib"...
0x180024070  mov     r9d, ebx; char *
0x180024073  mov     edx, 2Dh ; '-'; void *
0x180024078  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002407d  mov     edx, 1F2h
0x180024082  jmp     short loc_180024038
0x180024084  mov     edx, 1F6h
0x180024089  jmp     short loc_18002400C
0x18002408b  mov     [rbp+47h+var_B0], r13
0x18002408f  lea     rcx, [rbp+47h+var_B0]
0x180024093  mov     [rbp+47h+var_80], r13d
0x180024097  mov     [rbp+47h+var_84], r13d
0x18002409b  mov     [rbp+47h+var_88], r13d
0x18002409f  mov     [rbp+47h+bstrString], r13
0x1800240a3  mov     rax, [rdi]
0x1800240a6  mov     rbx, [rax+1E0h]
0x1800240ad  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800240b2  lea     rdx, [rbp+47h+var_B0]
0x1800240b6  mov     rcx, rdi
0x1800240b9  mov     rax, rbx
0x1800240bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240c1  mov     ebx, eax
0x1800240c3  test    eax, eax
0x1800240c5  jns     short loc_180024132
0x1800240c7  mov     edx, 22Fh
0x1800240cc  jmp     short loc_1800240D3
0x1800240ce  mov     edx, 233h
0x1800240d3  mov     r9d, eax
0x1800240d6  jmp     short loc_180024109
0x1800240d8  mov     rax, [rbp+47h+bstrString]
0x1800240dc  lea     rdx, EVENT_MANIFEST_XML_PARSING_ERROR
0x1800240e3  mov     r9d, [rbp+47h+var_84]
0x1800240e7  mov     r8d, [rbp+47h+var_80]
0x1800240eb  mov     [rsp+0E0h+var_B8], rax
0x1800240f0  mov     eax, [rbp+47h+var_88]
0x1800240f3  mov     [rsp+0E0h+var_C0], eax; int
0x1800240f7  call    McTemplateU0dqqz_EventWriteTransfer
0x1800240fc  mov     ebx, 80080204h
0x180024101  mov     edx, 235h; void *
0x180024106  mov     r9d, ebx; char *
0x180024109  mov     rcx, [rbp+4Fh]; this
0x18002410d  lea     r8, aOnecorePrintsc_32; "onecore\\printscan\\appxpackaging\\lib"...
0x180024114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024119  mov     rcx, [rbp+47h+bstrString]; bstrString
0x18002411d  call    cs:__imp_SysFreeString
0x180024124  nop     dword ptr [rax+rax+00h]
0x180024129  lea     rcx, [rbp+47h+var_B0]
0x18002412d  jmp     loc_18002431D
0x180024132  mov     rcx, [rbp+47h+var_B0]
0x180024136  lea     rdx, [rbp+47h+var_80]
0x18002413a  mov     rax, [rcx]
0x18002413d  mov     rax, [rax+38h]
0x180024141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024146  mov     ebx, eax
0x180024148  test    eax, eax
0x18002414a  jns     short loc_180024153
0x18002414c  mov     edx, 230h
0x180024151  jmp     short loc_1800240D3
0x180024153  mov     rcx, [rbp+47h+var_B0]
0x180024157  lea     rdx, [rbp+47h+var_84]
0x18002415b  mov     rax, [rcx]
0x18002415e  mov     rax, [rax+58h]
0x180024162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024167  mov     ebx, eax
0x180024169  test    eax, eax
0x18002416b  jns     short loc_180024177
0x18002416d  mov     edx, 231h
0x180024172  jmp     loc_1800240D3
0x180024177  mov     rcx, [rbp+47h+var_B0]
0x18002417b  lea     rdx, [rbp+47h+var_88]
0x18002417f  mov     rax, [rcx]
  ... truncated ...
```

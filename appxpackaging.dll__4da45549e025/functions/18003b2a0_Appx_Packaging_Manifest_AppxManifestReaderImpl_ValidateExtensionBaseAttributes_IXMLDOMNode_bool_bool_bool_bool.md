# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateExtensionBaseAttributes(IXMLDOMNode *,bool,bool *,bool *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x18003b2a0`
- end: `0x18003c7c1`
- name: `?ValidateExtensionBaseAttributes@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@_NPEA_N222222@Z`
- size: `5409`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestReaderImpl *__hidden this, struct IXMLDOMNode *, bool, bool *, bool *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c8a8`
- `0x1800d757c`
- `0x1800df30c`
- `0x1800e074c`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x18000f260`
- `0x1800133fc`
- `0x18003a344`
- `0x18003afbc`
- `0x18003b2a0`
- `0x18003c7c8`
- `0x18003d3d0`
- `0x1800446d0`
- `0x1800490c0`
- `0x180071f50`
- `0x1800965d0`
- `0x1800e0c4c`
- `0x1800e0cc4`
- `0x1800e0f0c`
- `0x1800e1044`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003b933`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b943`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b953`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b963`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b973`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b983`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b993`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bb8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bf14`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c552`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c562`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b933`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b943`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b953`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b963`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b973`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b983`
- `OLEAUT32!__imp_SysFreeString` at `0x18003b993`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bb8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bf14`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c552`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c562`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b374`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b432`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b4f0`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b5ae`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b66c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b72a`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b7e8`
- `OLEAUT32!__imp_SysStringLen` at `0x18003bb39`
- `OLEAUT32!__imp_SysStringLen` at `0x18003c573`
- `OLEAUT32!__imp_SysStringLen` at `0x18003c59d`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b374`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b432`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b4f0`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b5ae`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b66c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b72a`
- `OLEAUT32!__imp_SysStringLen` at `0x18003b7e8`
- `OLEAUT32!__imp_SysStringLen` at `0x18003bb39`
- `OLEAUT32!__imp_SysStringLen` at `0x18003c573`
- `OLEAUT32!__imp_SysStringLen` at `0x18003c59d`

## string_xrefs

- `0x18003be48`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18003bf01`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18003c298`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18003c2b2`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18003bebb`: `Extension`
- `0x18003bf61`: `Extension`
- `0x18003c02e`: `Extension`
- `0x18003c17f`: `Extension`
- `0x18003c312`: `Extension`
- `0x18003c3e0`: `Extension`
- `0x18003c4d1`: `Extension`
- `0x18003c634`: `Extension`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateExtensionBaseAttributes(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this,
        struct IXMLDOMNode *a2,
        char a3,
        bool *a4,
        bool *a5,
        bool *a6,
        bool *a7,
        bool *a8,
        bool *a9,
        bool *a10)
{
  __int64 v10; // rdi
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v16; // eax
  int NodeValue; // ebx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdi
  struct IXMLDOMNodeVtbl *v21; // rax
  HRESULT (__stdcall *v22)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rdi
  struct IXMLDOMNodeVtbl *v27; // rax
  HRESULT (__stdcall *v28)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rdi
  struct IXMLDOMNodeVtbl *v33; // rax
  HRESULT (__stdcall *v34)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v35; // eax
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rdi
  struct IXMLDOMNodeVtbl *v39; // rax
  HRESULT (__stdcall *v40)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rdi
  struct IXMLDOMNodeVtbl *v45; // rax
  HRESULT (__stdcall *v46)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v47; // eax
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rdi
  struct IXMLDOMNodeVtbl *v51; // rax
  HRESULT (__stdcall *v52)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v53; // eax
  int v54; // eax
  __int64 v55; // rcx
  BSTR v56; // rax
  bool v57; // r10
  bool v58; // r13
  BSTR v59; // rcx
  int v60; // edx
  int v61; // r8d
  bool v62; // bl
  bool v63; // di
  bool v64; // cl
  bool v65; // cl
  BSTR v67; // rcx
  int v68; // edx
  int v69; // r8d
  bool v70; // cl
  bool v71; // r15
  BSTR v72; // rcx
  int v73; // r8d
  int v74; // edx
  char *v75; // rdi
  int v76; // edx
  int v77; // ecx
  int v78; // ecx
  int v79; // r8d
  struct IXMLDOMNodeVtbl *v80; // rax
  __int64 v81; // rdi
  struct IXMLDOMNodeVtbl *v82; // rax
  HRESULT (__stdcall *v83)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rbx
  int v84; // eax
  int v85; // eax
  BSTR v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rcx
  BSTR v94; // rcx
  __int64 v95; // rdx
  int v96; // ecx
  int v97; // r8d
  __int64 v98; // rdx
  OLECHAR *v99; // rcx
  int v100; // ecx
  int v101; // ecx
  int v102; // r8d
  int v103; // ecx
  int v104; // ecx
  int v105; // r8d
  __int64 v106; // rbx
  __int64 v107; // rdx
  __int64 v108; // rdx
  int v109; // ecx
  int v110; // r8d
  __int64 v111; // rbx
  BSTR v112; // rax
  int v113; // edx
  int v114; // r8d
  int v115; // ecx
  int v116; // r8d
  BSTR v117; // rax
  int v118; // r8d
  int v119; // edx
  int v120; // ecx
  int v121; // r8d
  UINT v122; // eax
  UINT v123; // eax
  int v124; // eax
  bool v125; // zf
  int v126; // ecx
  int v127; // r8d
  int v128; // ecx
  int v129; // r8d
  int v130; // [rsp+20h] [rbp-99h]
  int v131; // [rsp+20h] [rbp-99h]
  int v132; // [rsp+20h] [rbp-99h]
  unsigned __int16 *v133; // [rsp+30h] [rbp-89h]
  unsigned int v134; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v135; // [rsp+54h] [rbp-65h] BYREF
  bool v136; // [rsp+58h] [rbp-61h]
  BSTR v137; // [rsp+60h] [rbp-59h] BYREF
  bool v138; // [rsp+68h] [rbp-51h]
  bool v139; // [rsp+69h] [rbp-50h]
  bool v140; // [rsp+6Ah] [rbp-4Fh]
  BSTR v141; // [rsp+70h] [rbp-49h] BYREF
  BSTR v142; // [rsp+78h] [rbp-41h] BYREF
  BSTR v143; // [rsp+80h] [rbp-39h] BYREF
  BSTR v144; // [rsp+88h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-29h] BYREF
  BSTR v146; // [rsp+98h] [rbp-21h] BYREF
  BSTR v147; // [rsp+A0h] [rbp-19h] BYREF
  BSTR v148; // [rsp+A8h] [rbp-11h] BYREF
  BSTR pbstr[8]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]
  __int64 v151; // [rsp+100h] [rbp+47h] BYREF
  bool v152; // [rsp+108h] [rbp+4Fh]
  bool *v153; // [rsp+118h] [rbp+5Fh]

  v153 = a4;
  v10 = *((_QWORD *)this + 19);
  v135 = 0;
  v134 = 0;
  pbstr[0] = 0;
  v148 = 0;
  v142 = 0;
  v147 = 0;
  v143 = 0;
  v146 = 0;
  bstrString = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  lpVtbl = a2->lpVtbl;
  v151 = 0;
  pbstr[0] = 0;
  selectSingleNode = lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v16 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))selectSingleNode)(a2, v10, &v151);
  NodeValue = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v16,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_9:
      NodeValue = 0;
      goto LABEL_10;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, pbstr);
    NodeValue = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v18,
        v130);
    }
    else if ( !SysStringLen(pbstr[0]) )
    {
      v19 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      goto LABEL_9;
    }
    v87 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
    }
  }
LABEL_10:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2561;
    goto LABEL_132;
  }
  v20 = *((_QWORD *)this + 26);
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  v21 = a2->lpVtbl;
  v151 = 0;
  v148 = 0;
  v22 = v21->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v23 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v22)(a2, v20, &v151);
  NodeValue = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v23,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_17:
      NodeValue = 0;
      goto LABEL_18;
    }
    v24 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, &v148);
    NodeValue = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v24,
        v130);
    }
    else if ( !SysStringLen(v148) )
    {
      v25 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      goto LABEL_17;
    }
    v88 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
  }
LABEL_18:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2562;
    goto LABEL_132;
  }
  v26 = *((_QWORD *)this + 21);
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  v27 = a2->lpVtbl;
  v151 = 0;
  v142 = 0;
  v28 = v27->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v29 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v28)(a2, v26, &v151);
  NodeValue = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v29,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_25:
      NodeValue = 0;
      goto LABEL_26;
    }
    v30 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, &v142);
    NodeValue = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v30,
        v130);
    }
    else if ( !SysStringLen(v142) )
    {
      v31 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      goto LABEL_25;
    }
    v89 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    }
  }
LABEL_26:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2563;
    goto LABEL_132;
  }
  v32 = *((_QWORD *)this + 20);
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  v33 = a2->lpVtbl;
  v151 = 0;
  v147 = 0;
  v34 = v33->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v35 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v34)(a2, v32, &v151);
  NodeValue = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v35,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_33:
      NodeValue = 0;
      goto LABEL_34;
    }
    v36 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, &v147);
    NodeValue = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v36,
        v130);
    }
    else if ( !SysStringLen(v147) )
    {
      v37 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      goto LABEL_33;
    }
    v90 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
  }
LABEL_34:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2564;
    goto LABEL_132;
  }
  v38 = *((_QWORD *)this + 25);
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  v39 = a2->lpVtbl;
  v151 = 0;
  v143 = 0;
  v40 = v39->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v41 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v40)(a2, v38, &v151);
  NodeValue = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v41,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_41:
      NodeValue = 0;
      goto LABEL_42;
    }
    v42 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, &v143);
    NodeValue = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v42,
        v130);
    }
    else if ( !SysStringLen(v143) )
    {
      v43 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      goto LABEL_41;
    }
    v91 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    }
  }
LABEL_42:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2565;
    goto LABEL_132;
  }
  v44 = *((_QWORD *)this + 24);
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  v45 = a2->lpVtbl;
  v151 = 0;
  v146 = 0;
  v46 = v45->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v47 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v46)(a2, v44, &v151);
  NodeValue = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v47,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_49:
      NodeValue = 0;
      goto LABEL_50;
    }
    v48 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, &v146);
    NodeValue = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v48,
        v130);
    }
    else if ( !SysStringLen(v146) )
    {
      v49 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      goto LABEL_49;
    }
    v92 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    }
  }
LABEL_50:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2566;
    goto LABEL_132;
  }
  v50 = *((_QWORD *)this + 27);
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->AddRef)(a2);
  v51 = a2->lpVtbl;
  v151 = 0;
  bstrString = 0;
  v52 = v51->selectSingleNode;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  v53 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v52)(a2, v50, &v151);
  NodeValue = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v53,
      v130);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v151);
  }
  else
  {
    if ( !v151 )
    {
LABEL_57:
      NodeValue = 0;
      goto LABEL_58;
    }
    v54 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v151 + 208LL))(v151, &bstrString);
    NodeValue = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v54,
        v130);
    }
    else if ( !SysStringLen(bstrString) )
    {
      v55 = v151;
      if ( v151 )
      {
        v151 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      goto LABEL_57;
    }
    v93 = v151;
    if ( v151 )
    {
      v151 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    }
  }
LABEL_58:
  ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
  if ( NodeValue < 0 )
  {
    v95 = 2567;
    goto LABEL_132;
  }
  v56 = v142;
  v139 = v148 != 0;
  LOBYTE(v151) = v143 != 0;
  v152 = v146 != 0;
  v57 = v147 != 0;
  v136 = v147 != 0;
  v58 = v142 != 0;
  v138 = pbstr[0] != 0;
  v140 = bstrString != 0;
  if ( v148 )
  {
    if ( !pbstr[0] && !v142 && !v147 && !v143 && !v146 )
    {
      v62 = v143 != 0;
      v63 = 0;
      goto LABEL_68;
    }
    Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
      *((Appx::Packaging::XmlLineInformation **)this + 13),
      (struct IStream *)a2,
      (struct IXMLDOMNode *)&Appx::Packaging::Manifest::ManganeseUapNamespace,
      L"HostId",
      (const unsigned __int16 *)&v135,
      &v134,
      (unsigned int *)v133);
    NodeValue = -2146958844;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dqqzz_EventWriteTransfer(
        v100,
        (unsigned int)&EVENT_MANIFEST_INCORRECT_HOSTID_APPLICATION_EXTENSION_EXTRA_ATTRIBUTES,
        -2146958844,
        v135,
        v134,
        (__int64)L"Extension",
        (__int64)L"Category");
    AppxPackagingLog(
      &EVENT_MANIFEST_INCORRECT_HOSTID_APPLICATION_EXTENSION_EXTRA_ATTRIBUTES,
      0xB0000110,
      -2146958844,
      v135,
      v134,
      L"Extension",
      L"Category");
    v95 = 2754;
    goto LABEL_132;
  }
  if ( pbstr[0] )
  {
    if ( v142 )
    {
      Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
        *((Appx::Packaging::XmlLineInformation **)this + 13),
        (struct IStream *)a2,
        0,
        L"EntryPoint",
        (const unsigned __int16 *)&v135,
        &v134,
        (unsigned int *)v133);
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0dqqzzz_EventWriteTransfer(
          v101,
          (unsigned int)&EVENT_MANIFEST_CONFLICTING_ATTRIBUTES,
          v102,
          v135,
          v134,
          (__int64)L"EntryPoint",
          (__int64)L"StartPage",
          (__int64)L"Extension");
      AppxPackagingLog(
        &EVENT_MANIFEST_CONFLICTING_ATTRIBUTES,
        0xB0000086,
        v102,
        v135,
        v134,
        L"EntryPoint",
        L"StartPage",
        L"Extension");
      v95 = 2588;
      NodeValue = -2146958844;
      goto LABEL_132;
    }
    if ( v147 )
    {
      if ( !*((_BYTE *)this + 416) || !a3 )
      {
        Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
          *((Appx::Packaging::XmlLineInformation **)this + 13),
          (struct IStream *)a2,
          0,
          L"Executable",
          (const unsigned __int16 *)&v135,
          &v134,
          (unsigned int *)v133);
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0dqqzzz_EventWriteTransfer(
            v104,
            (unsigned int)&EVENT_MANIFEST_CONFLICTING_ATTRIBUTES,
            v105,
            v135,
            v134,
            (__int64)L"Executable",
            (__int64)L"StartPage",
            (__int64)L"Extension");
        AppxPackagingLog(
          &EVENT_MANIFEST_CONFLICTING_ATTRIBUTES,
          0xB0000086,
          v105,
          v135,
          v134,
          L"Executable",
          L"StartPage",
          L"Extension");
        v95 = 2599;
        NodeValue = -2146958844;
        goto LABEL_132;
      }
      if ( !Common::String::CaseInsensitiveEquals(v147, L"wwahost.exe") )
      {
        Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
          *((Appx::Packaging::XmlLineInformation **)this + 13),
          (struct IStream *)a2,
          0,
          L"Executable",
          (const unsigned __int16 *)&v135,
          &v134,
          (unsigned int *)v133);
        NodeValue = -2146958844;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0dqq_EventWriteTransfer(
            v103,
            (unsigned int)&EVENT_MANIFEST_INVALID_EXECUTABLE_FOR_BACKGROUND_TASK,
            -2146958844,
            v135,
            v134);
        AppxPackagingLog(&EVENT_MANIFEST_INVALID_EXECUTABLE_FOR_BACKGROUND_TASK, 0xB00000B7, -2146958844, v135, v134);
        v95 = 2605;
        goto LABEL_132;
      }
    }
    v106 = *((_QWORD *)this + 22);
    v137 = 0;
    v141 = (BSTR)a2;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v141);
    v131 = 0;
    NodeValue = Appx::Packaging::GetNodeValue(&v141, v106, 0, &v137);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v141);
    if ( NodeValue < 0 )
    {
      v107 = 2610;
LABEL_167:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v107,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)NodeValue,
        v131);
LABEL_170:
      v99 = v137;
      goto LABEL_138;
    }
    if ( v137 )
    {
      Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
        *((Appx::Packaging::XmlLineInformation **)this + 13),
        (struct IStream *)a2,
        0,
        L"RuntimeType",
        (const unsigned __int16 *)&v135,
        &v134,
        (unsigned int *)v133);
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0dqqzzz_EventWriteTransfer(
          v109,
          (unsigned int)&EVENT_MANIFEST_CONFLICTING_ATTRIBUTES,
          v110,
          v135,
          v134,
          (__int64)L"RuntimeType",
          (__int64)L"StartPage",
          (__int64)L"Extension");
      AppxPackagingLog(
        &EVENT_MANIFEST_CONFLICTING_ATTRIBUTES,
        0xB0000086,
        v110,
        v135,
        v134,
        L"RuntimeType",
        L"StartPage",
        L"Extension");
      v107 = 2617;
      NodeValue = -2146958844;
      goto LABEL_167;
    }
    v111 = *((_QWORD *)this + 24);
    v144 = 0;
    v141 = (BSTR)a2;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v141);
    v132 = 0;
    NodeValue = Appx::Packaging::GetNodeValue(&v141, v111, 0, &v144);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v141);
    if ( NodeValue >= 0 )
    {
      if ( v144 )
      {
        v112 = v144;
        do
        {
          v113 = *(BSTR)((char *)v112 + (char *)L"appContainer" - (char *)v144);
          v114 = *v112 - v113;
          if ( v114 )
            break;
          ++v112;
        }
        while ( v113 );
        if ( v114 )
        {
          Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
            *((Appx::Packaging::XmlLineInformation **)this + 13),
            (struct IStream *)a2,
            (struct IXMLDOMNode *)&Appx::Packaging::Manifest::VibraniumUapNamespace,
            L"TrustLevel",
            (const unsigned __int16 *)&v135,
            &v134,
            (unsigned int *)v133);
          if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
            McTemplateU0dqqzzzz_EventWriteTransfer(
              v115,
              (unsigned int)&EVENT_MANIFEST_CONFLICTING_ATTRIBUTES_WITH_INCORRECT_VALUE,
              v116,
              v135,
              v134,
              (__int64)L"TrustLevel",
              (__int64)L"appContainer",
              (__int64)L"StartPage",
              (__int64)L"Extension");
          AppxPackagingLog(
            &EVENT_MANIFEST_CONFLICTING_ATTRIBUTES_WITH_INCORRECT_VALUE,
            0xB000010A,
            v116,
            v135,
            v134,
            L"TrustLevel",
            L"appContainer",
            L"StartPage",
            L"Extension");
          v108 = 2639;
          NodeValue = -2146958844;
          goto LABEL_169;
        }
        v63 = 1;
      }
      else
      {
        v63 = v152;
      }
      if ( v143 )
      {
        v117 = v144;
        do
        {
          v118 = *(BSTR)((char *)v117 + (char *)L"windowsApp" - (char *)v144);
          v119 = *v117 - v118;
          if ( v119 )
            break;
          ++v117;
        }
        while ( v118 );
        if ( v119 )
        {
          Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
            *((Appx::Packaging::XmlLineInformation **)this + 13),
            (struct IStream *)a2,
            (struct IXMLDOMNode *)&Appx::Packaging::Manifest::VibraniumUapNamespace,
            L"RuntimeBehavior",
            (const unsigned __int16 *)&v135,
            &v134,
            (unsigned int *)v133);
          if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
            McTemplateU0dqqzzzz_EventWriteTransfer(
              v120,
              (unsigned int)&EVENT_MANIFEST_CONFLICTING_ATTRIBUTES_WITH_INCORRECT_VALUE,
              v121,
              v135,
              v134,
              (__int64)L"RuntimeBehavior",
              (__int64)L"windowsApp",
              (__int64)L"StartPage",
              (__int64)L"Extension");
          AppxPackagingLog(
            &EVENT_MANIFEST_CONFLICTING_ATTRIBUTES_WITH_INCORRECT_VALUE,
            0xB000010A,
            v121,
            v135,
            v134,
            L"RuntimeBehavior",
            L"windowsApp",
            L"StartPage",
            L"Extension");
          v108 = 2661;
          NodeValue = -2146958844;
          goto LABEL_169;
        }
        v62 = 1;
      }
      else
      {
        v62 = v151;
      }
      SysFreeString(v144);
      SysFreeString(v137);
      goto LABEL_68;
    }
    v108 = 2622;
LABEL_169:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v108,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)NodeValue,
      v132);
    SysFreeString(v144);
    goto LABEL_170;
  }
  if ( v143 )
  {
    v122 = SysStringLen(v143);
    v71 = Common::String::Equals(v143, v122, L"windowsApp", 0xAu) != 0;
    v123 = SysStringLen(v143);
    v124 = Common::String::Equals(v143, v123, L"win32App", 8u);
    v57 = v136;
    v125 = v124 == 0;
    v56 = v142;
    v70 = !v125;
  }
  else
  {
    if ( v142 )
    {
      v59 = v142;
      do
      {
        v60 = *(BSTR)((char *)v59 + (char *)L"Windows.FullTrustApplication" - (char *)v142);
        v61 = *v59 - v60;
        if ( v61 )
          break;
        ++v59;
      }
      while ( v60 );
      if ( !v61 )
        goto LABEL_67;
      v67 = v142;
      do
      {
        v68 = *(BSTR)((char *)v67 + (char *)L"Windows.PartialTrustApplication" - (char *)v142);
        v69 = *v67 - v68;
        if ( v69 )
          break;
        ++v67;
      }
      while ( v68 );
      if ( !v69 )
        goto LABEL_67;
    }
    v70 = 0;
    v71 = 1;
  }
  if ( !v58 )
  {
    if ( !v71 && (*((_QWORD *)this + 33) & 0xFFFFFFFFFFFF0000uLL) >= 0xA000049CE0000LL )
      goto LABEL_67;
    if ( !v57 )
    {
      v80 = a2->lpVtbl;
      v81 = *((_QWORD *)this + 22);
      v141 = 0;
      ((void (__fastcall *)(struct IXMLDOMNode *))v80->AddRef)(a2);
      v82 = a2->lpVtbl;
      v137 = 0;
      v141 = 0;
      v83 = v82->selectSingleNode;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v137);
      v84 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, BSTR *))v83)(a2, v81, &v137);
      NodeValue = v84;
      if ( v84 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v84,
          v130);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v137);
        goto LABEL_97;
      }
      if ( v137 )
      {
        v85 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v137 + 208LL))(v137, &v141);
        NodeValue = v85;
        if ( v85 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x51,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
            (const char *)(unsigned int)v85,
            v130);
        }
        else if ( !SysStringLen(v141) )
        {
          v86 = v137;
          if ( v137 )
          {
            v137 = 0;
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v86 + 16LL))(v86);
          }
          goto LABEL_96;
        }
        v94 = v137;
        if ( v137 )
        {
          v137 = 0;
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v94 + 16LL))(v94);
        }
        goto LABEL_97;
      }
LABEL_96:
      NodeValue = 0;
LABEL_97:
      ((void (__fastcall *)(struct IXMLDOMNode *))a2->lpVtbl->Release)(a2);
      if ( NodeValue < 0 )
      {
        v98 = 2701;
      }
      else
      {
        if ( !v141 )
        {
          SysFreeString(0);
          goto LABEL_67;
        }
        Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
          *((Appx::Packaging::XmlLineInformation **)this + 13),
          (struct IStream *)a2,
          0,
          L"RuntimeType",
          (const unsigned __int16 *)&v135,
          &v134,
          (unsigned int *)v133);
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0dqqzzz_EventWriteTransfer(
            v96,
            (unsigned int)&EVENT_MANIFEST_ADDITIONAL_ATTRIBUTE_REQUIRED,
            v97,
            v135,
            v134,
            (__int64)L"EntryPoint",
            (__int64)L"RuntimeType",
            (__int64)L"Extension");
        AppxPackagingLog(
          &EVENT_MANIFEST_ADDITIONAL_ATTRIBUTE_REQUIRED,
          0xB0000085,
          v97,
          v135,
          v134,
          L"EntryPoint",
          L"RuntimeType",
          L"Extension");
        v98 = 2707;
        NodeValue = -2146958844;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v98,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
        (const char *)(unsigned int)NodeValue,
        v130);
      v99 = v141;
LABEL_138:
      SysFreeString(v99);
      goto LABEL_69;
    }
    Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
      *((Appx::Packaging::XmlLineInformation **)this + 13),
      (struct IStream *)a2,
      0,
      L"Executable",
      (const unsigned __int16 *)&v135,
      &v134,
      (unsigned int *)v133);
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dqqzzz_EventWriteTransfer(
        v126,
        (unsigned int)&EVENT_MANIFEST_ADDITIONAL_ATTRIBUTE_REQUIRED,
        v127,
        v135,
        v134,
        (__int64)L"EntryPoint",
        (__int64)L"Executable",
        (__int64)L"Extension");
    AppxPackagingLog(
      &EVENT_MANIFEST_ADDITIONAL_ATTRIBUTE_REQUIRED,
      0xB0000085,
      v127,
      v135,
      v134,
      L"EntryPoint",
      L"Executable",
      L"Extension");
    v95 = 2697;
    NodeValue = -2146958844;
LABEL_132:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v95,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)NodeValue,
      v130);
    goto LABEL_69;
  }
  if ( !v70 )
  {
LABEL_67:
    v62 = v151;
    v63 = v152;
LABEL_68:
    *v153 = v138;
    v64 = v136;
    *a6 = v58;
    *a5 = v64;
    v65 = v139;
    *a7 = v63;
    *a8 = v62;
    NodeValue = 0;
    *a9 = v65;
    *a10 = v140;
    goto LABEL_69;
  }
  v72 = v56;
  do
  {
    v73 = *(BSTR)((char *)v72 + (char *)L"Windows.FullTrustApplication" - (char *)v56);
    v74 = *v72 - v73;
    if ( v74 )
      break;
    ++v72;
  }
  while ( v73 );
  if ( !v74 )
    goto LABEL_202;
  v75 = (char *)((char *)L"Windows.PartialTrustApplication" - (char *)v56);
  do
  {
    v76 = *(unsigned __int16 *)&v75[(_QWORD)v56];
    v77 = *v56 - v76;
    if ( v77 )
      break;
    ++v56;
  }
  while ( v76 );
  if ( v77 )
  {
    Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
      *((Appx::Packaging::XmlLineInformation **)this + 13),
      (struct IStream *)a2,
      0,
      0,
      (const unsigned __int16 *)&v135,
      &v134,
      (unsigned int *)v133);
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dqqzzz_EventWriteTransfer(
        v78,
        (unsigned int)&EVENT_MANIFEST_ENTRYPOINT_CONFLICT_TRUSTLEVE_OR_RUNTIMEBEHAVIOR,
        v79,
        v135,
        v134,
        (__int64)v142,
        (__int64)L"RuntimeBehavior",
        (__int64)L"windowsApp");
    AppxPackagingLog(
      &EVENT_MANIFEST_ENTRYPOINT_CONFLICT_TRUSTLEVE_OR_RUNTIMEBEHAVIOR,
      0xB000010C,
      v79,
      v135,
      v134,
      v142,
      L"RuntimeBehavior",
      L"windowsApp");
  }
  else
  {
LABEL_202:
    Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
      *((Appx::Packaging::XmlLineInformation **)this + 13),
      (struct IStream *)a2,
      0,
      0,
      (const unsigned __int16 *)&v135,
      &v134,
      (unsigned int *)v133);
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dqqzzz_EventWriteTransfer(
        v128,
        (unsigned int)&EVENT_MANIFEST_ENTRYPOINT_CONFLICT_TRUSTLEVE_OR_RUNTIMEBEHAVIOR,
        v129,
        v135,
        v134,
        (__int64)v142,
        (__int64)L"RuntimeBehavior",
        (__int64)L"packagedClassicApp");
    AppxPackagingLog(
      &EVENT_MANIFEST_ENTRYPOINT_CONFLICT_TRUSTLEVE_OR_RUNTIMEBEHAVIOR,
      0xB000010C,
      v129,
      v135,
      v134,
      v142,
      L"RuntimeBehavior",
      L"packagedClassicApp");
  }
  NodeValue = -2146958844;
LABEL_69:
  SysFreeString(bstrString);
  SysFreeString(v146);
  SysFreeString(v143);
  SysFreeString(v147);
  SysFreeString(v142);
  SysFreeString(v148);
  SysFreeString(pbstr[0]);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18003b2a0  mov     [rsp-8+arg_10], rbx
0x18003b2a5  mov     [rsp-8+arg_18], r9
0x18003b2aa  push    rbp
0x18003b2ab  push    rsi
0x18003b2ac  push    rdi
0x18003b2ad  push    r12
0x18003b2af  push    r13
0x18003b2b1  push    r14
0x18003b2b3  push    r15
0x18003b2b5  lea     rbp, [rsp-7]
0x18003b2ba  sub     rsp, 0C0h
0x18003b2c1  mov     rdi, [rcx+98h]
0x18003b2c8  xor     r13d, r13d
0x18003b2cb  mov     [rbp+37h+var_9C], r13d
0x18003b2cf  mov     r12b, r8b
0x18003b2d2  mov     [rbp+37h+var_A0], r13d
0x18003b2d6  mov     rsi, rdx
0x18003b2d9  mov     [rbp+37h+pbstr], r13
0x18003b2dd  mov     r14, rcx
0x18003b2e0  mov     [rbp+37h+var_48], r13
0x18003b2e4  mov     [rbp+37h+var_78], r13
0x18003b2e8  mov     [rbp+37h+var_50], r13
0x18003b2ec  mov     [rbp+37h+var_70], r13
0x18003b2f0  mov     [rbp+37h+var_58], r13
0x18003b2f4  mov     [rbp+37h+bstrString], r13
0x18003b2f8  test    rdx, rdx
0x18003b2fb  jz      short loc_18003B30C
0x18003b2fd  mov     rax, [rdx]
0x18003b300  mov     rcx, rdx
0x18003b303  mov     rax, [rax+8]
0x18003b307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b30c  mov     rax, [rsi]
0x18003b30f  lea     rcx, [rbp+37h+arg_0]
0x18003b313  mov     [rbp+37h+arg_0], r13
0x18003b317  mov     [rbp+37h+pbstr], r13
0x18003b31b  mov     rbx, [rax+128h]
0x18003b322  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003b327  lea     r8, [rbp+37h+arg_0]
0x18003b32b  mov     rdx, rdi
0x18003b32e  mov     rcx, rsi
0x18003b331  mov     rax, rbx
0x18003b334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b339  lea     r15, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18003b340  mov     ebx, eax
0x18003b342  test    eax, eax
0x18003b344  js      loc_18003BD17
0x18003b34a  mov     rcx, [rbp+37h+arg_0]
0x18003b34e  test    rcx, rcx
0x18003b351  jz      short loc_18003B3A1
0x18003b353  mov     rax, [rcx]
0x18003b356  lea     rdx, [rbp+37h+pbstr]
0x18003b35a  mov     rax, [rax+0D0h]
0x18003b361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b366  mov     ebx, eax
0x18003b368  test    eax, eax
0x18003b36a  js      loc_18003BB9D
0x18003b370  mov     rcx, [rbp+37h+pbstr]; pbstr
0x18003b374  call    cs:__imp_SysStringLen
0x18003b37b  nop     dword ptr [rax+rax+00h]
0x18003b380  test    eax, eax
0x18003b382  jnz     loc_18003BBB1
0x18003b388  mov     rcx, [rbp+37h+arg_0]
0x18003b38c  test    rcx, rcx
0x18003b38f  jz      short loc_18003B3A1
0x18003b391  mov     [rbp+37h+arg_0], r13
0x18003b395  mov     rax, [rcx]
0x18003b398  mov     rax, [rax+10h]
0x18003b39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3a1  mov     ebx, r13d
0x18003b3a4  mov     rax, [rsi]
0x18003b3a7  mov     rcx, rsi
0x18003b3aa  mov     rax, [rax+10h]
0x18003b3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3b3  test    ebx, ebx
0x18003b3b5  js      loc_18003BE3F
0x18003b3bb  mov     rax, [rsi]
0x18003b3be  mov     rcx, rsi
0x18003b3c1  mov     rdi, [r14+0D0h]
0x18003b3c8  mov     rax, [rax+8]
0x18003b3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3d1  mov     rax, [rsi]
0x18003b3d4  lea     rcx, [rbp+37h+arg_0]
0x18003b3d8  mov     [rbp+37h+arg_0], r13
0x18003b3dc  mov     [rbp+37h+var_48], r13
0x18003b3e0  mov     rbx, [rax+128h]
0x18003b3e7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003b3ec  lea     r8, [rbp+37h+arg_0]
0x18003b3f0  mov     rdx, rdi
0x18003b3f3  mov     rcx, rsi
0x18003b3f6  mov     rax, rbx
0x18003b3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3fe  mov     ebx, eax
0x18003b400  test    eax, eax
0x18003b402  js      loc_18003BD39
0x18003b408  mov     rcx, [rbp+37h+arg_0]
0x18003b40c  test    rcx, rcx
0x18003b40f  jz      short loc_18003B45F
0x18003b411  mov     rax, [rcx]
0x18003b414  lea     rdx, [rbp+37h+var_48]
0x18003b418  mov     rax, [rax+0D0h]
0x18003b41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b424  mov     ebx, eax
0x18003b426  test    eax, eax
0x18003b428  js      loc_18003BBD3
0x18003b42e  mov     rcx, [rbp+37h+var_48]; pbstr
0x18003b432  call    cs:__imp_SysStringLen
0x18003b439  nop     dword ptr [rax+rax+00h]
0x18003b43e  test    eax, eax
0x18003b440  jnz     loc_18003BBE7
0x18003b446  mov     rcx, [rbp+37h+arg_0]
0x18003b44a  test    rcx, rcx
0x18003b44d  jz      short loc_18003B45F
0x18003b44f  mov     [rbp+37h+arg_0], r13
0x18003b453  mov     rax, [rcx]
0x18003b456  mov     rax, [rax+10h]
0x18003b45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b45f  mov     ebx, r13d
0x18003b462  mov     rax, [rsi]
0x18003b465  mov     rcx, rsi
0x18003b468  mov     rax, [rax+10h]
0x18003b46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b471  test    ebx, ebx
0x18003b473  js      loc_18003BFCB
0x18003b479  mov     rax, [rsi]
0x18003b47c  mov     rcx, rsi
0x18003b47f  mov     rdi, [r14+0A8h]
0x18003b486  mov     rax, [rax+8]
0x18003b48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b48f  mov     rax, [rsi]
0x18003b492  lea     rcx, [rbp+37h+arg_0]
0x18003b496  mov     [rbp+37h+arg_0], r13
0x18003b49a  mov     [rbp+37h+var_78], r13
0x18003b49e  mov     rbx, [rax+128h]
0x18003b4a5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003b4aa  lea     r8, [rbp+37h+arg_0]
0x18003b4ae  mov     rdx, rdi
0x18003b4b1  mov     rcx, rsi
0x18003b4b4  mov     rax, rbx
0x18003b4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4bc  mov     ebx, eax
0x18003b4be  test    eax, eax
0x18003b4c0  js      loc_18003BD5B
0x18003b4c6  mov     rcx, [rbp+37h+arg_0]
0x18003b4ca  test    rcx, rcx
0x18003b4cd  jz      short loc_18003B51D
0x18003b4cf  mov     rax, [rcx]
0x18003b4d2  lea     rdx, [rbp+37h+var_78]
0x18003b4d6  mov     rax, [rax+0D0h]
0x18003b4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4e2  mov     ebx, eax
0x18003b4e4  test    eax, eax
0x18003b4e6  js      loc_18003BC09
0x18003b4ec  mov     rcx, [rbp+37h+var_78]; pbstr
0x18003b4f0  call    cs:__imp_SysStringLen
0x18003b4f7  nop     dword ptr [rax+rax+00h]
0x18003b4fc  test    eax, eax
0x18003b4fe  jnz     loc_18003BC1D
0x18003b504  mov     rcx, [rbp+37h+arg_0]
0x18003b508  test    rcx, rcx
0x18003b50b  jz      short loc_18003B51D
0x18003b50d  mov     [rbp+37h+arg_0], r13
0x18003b511  mov     rax, [rcx]
0x18003b514  mov     rax, [rax+10h]
0x18003b518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b51d  mov     ebx, r13d
0x18003b520  mov     rax, [rsi]
0x18003b523  mov     rcx, rsi
0x18003b526  mov     rax, [rax+10h]
0x18003b52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b52f  test    ebx, ebx
0x18003b531  js      loc_18003BFB7
0x18003b537  mov     rax, [rsi]
0x18003b53a  mov     rcx, rsi
0x18003b53d  mov     rdi, [r14+0A0h]
0x18003b544  mov     rax, [rax+8]
0x18003b548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b54d  mov     rax, [rsi]
0x18003b550  lea     rcx, [rbp+37h+arg_0]
0x18003b554  mov     [rbp+37h+arg_0], r13
0x18003b558  mov     [rbp+37h+var_50], r13
0x18003b55c  mov     rbx, [rax+128h]
0x18003b563  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003b568  lea     r8, [rbp+37h+arg_0]
0x18003b56c  mov     rdx, rdi
0x18003b56f  mov     rcx, rsi
0x18003b572  mov     rax, rbx
0x18003b575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b57a  mov     ebx, eax
0x18003b57c  test    eax, eax
0x18003b57e  js      loc_18003BD7D
0x18003b584  mov     rcx, [rbp+37h+arg_0]
0x18003b588  test    rcx, rcx
0x18003b58b  jz      short loc_18003B5DB
0x18003b58d  mov     rax, [rcx]
0x18003b590  lea     rdx, [rbp+37h+var_50]
0x18003b594  mov     rax, [rax+0D0h]
0x18003b59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5a0  mov     ebx, eax
0x18003b5a2  test    eax, eax
0x18003b5a4  js      loc_18003BC3F
0x18003b5aa  mov     rcx, [rbp+37h+var_50]; pbstr
0x18003b5ae  call    cs:__imp_SysStringLen
0x18003b5b5  nop     dword ptr [rax+rax+00h]
0x18003b5ba  test    eax, eax
0x18003b5bc  jnz     loc_18003BC53
0x18003b5c2  mov     rcx, [rbp+37h+arg_0]
0x18003b5c6  test    rcx, rcx
0x18003b5c9  jz      short loc_18003B5DB
0x18003b5cb  mov     [rbp+37h+arg_0], r13
0x18003b5cf  mov     rax, [rcx]
0x18003b5d2  mov     rax, [rax+10h]
0x18003b5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5db  mov     ebx, r13d
0x18003b5de  mov     rax, [rsi]
0x18003b5e1  mov     rcx, rsi
0x18003b5e4  mov     rax, [rax+10h]
0x18003b5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5ed  test    ebx, ebx
0x18003b5ef  js      loc_18003BFC1
0x18003b5f5  mov     rax, [rsi]
0x18003b5f8  mov     rcx, rsi
0x18003b5fb  mov     rdi, [r14+0C8h]
0x18003b602  mov     rax, [rax+8]
0x18003b606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b60b  mov     rax, [rsi]
0x18003b60e  lea     rcx, [rbp+37h+arg_0]
0x18003b612  mov     [rbp+37h+arg_0], r13
0x18003b616  mov     [rbp+37h+var_70], r13
0x18003b61a  mov     rbx, [rax+128h]
0x18003b621  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003b626  lea     r8, [rbp+37h+arg_0]
0x18003b62a  mov     rdx, rdi
0x18003b62d  mov     rcx, rsi
0x18003b630  mov     rax, rbx
0x18003b633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b638  mov     ebx, eax
0x18003b63a  test    eax, eax
0x18003b63c  js      loc_18003BD9F
0x18003b642  mov     rcx, [rbp+37h+arg_0]
0x18003b646  test    rcx, rcx
0x18003b649  jz      short loc_18003B699
0x18003b64b  mov     rax, [rcx]
0x18003b64e  lea     rdx, [rbp+37h+var_70]
0x18003b652  mov     rax, [rax+0D0h]
0x18003b659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b65e  mov     ebx, eax
0x18003b660  test    eax, eax
0x18003b662  js      loc_18003BC75
0x18003b668  mov     rcx, [rbp+37h+var_70]; pbstr
0x18003b66c  call    cs:__imp_SysStringLen
0x18003b673  nop     dword ptr [rax+rax+00h]
0x18003b678  test    eax, eax
0x18003b67a  jnz     loc_18003BC89
0x18003b680  mov     rcx, [rbp+37h+arg_0]
0x18003b684  test    rcx, rcx
0x18003b687  jz      short loc_18003B699
0x18003b689  mov     [rbp+37h+arg_0], r13
0x18003b68d  mov     rax, [rcx]
0x18003b690  mov     rax, [rax+10h]
0x18003b694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b699  mov     ebx, r13d
0x18003b69c  mov     rax, [rsi]
0x18003b69f  mov     rcx, rsi
0x18003b6a2  mov     rax, [rax+10h]
0x18003b6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6ab  test    ebx, ebx
0x18003b6ad  js      loc_18003BFD5
0x18003b6b3  mov     rax, [rsi]
0x18003b6b6  mov     rcx, rsi
0x18003b6b9  mov     rdi, [r14+0C0h]
0x18003b6c0  mov     rax, [rax+8]
0x18003b6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6c9  mov     rax, [rsi]
0x18003b6cc  lea     rcx, [rbp+37h+arg_0]
0x18003b6d0  mov     [rbp+37h+arg_0], r13
0x18003b6d4  mov     [rbp+37h+var_58], r13
0x18003b6d8  mov     rbx, [rax+128h]
0x18003b6df  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003b6e4  lea     r8, [rbp+37h+arg_0]
0x18003b6e8  mov     rdx, rdi
0x18003b6eb  mov     rcx, rsi
0x18003b6ee  mov     rax, rbx
0x18003b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6f6  mov     ebx, eax
0x18003b6f8  test    eax, eax
0x18003b6fa  js      loc_18003BDC1
0x18003b700  mov     rcx, [rbp+37h+arg_0]
0x18003b704  test    rcx, rcx
0x18003b707  jz      short loc_18003B757
0x18003b709  mov     rax, [rcx]
0x18003b70c  lea     rdx, [rbp+37h+var_58]
0x18003b710  mov     rax, [rax+0D0h]
0x18003b717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b71c  mov     ebx, eax
0x18003b71e  test    eax, eax
0x18003b720  js      loc_18003BCAB
0x18003b726  mov     rcx, [rbp+37h+var_58]; pbstr
0x18003b72a  call    cs:__imp_SysStringLen
0x18003b731  nop     dword ptr [rax+rax+00h]
0x18003b736  test    eax, eax
  ... truncated ...
```

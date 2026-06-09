# Appx::Packaging::Manifest::ManifestReaderBase::ValidateUniqueStrings(IXMLDOMNode *,Appx::Packaging::Manifest::XPathTable const *,uint)

- ea: `0x180033250`
- end: `0x180033b5c`
- name: `?ValidateUniqueStrings@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEAUIXMLDOMNode@@PEBUXPathTable@234@I@Z`
- size: `2316`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::ManifestReaderBase *__hidden this, struct IXMLDOMNode *, const struct Appx::Packaging::Manifest::XPathTable *, unsigned int)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d010`
- `0x180022400`
- `0x180063f38`
- `0x1800d757c`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x180009eb8`
- `0x180010f40`
- `0x1800133fc`
- `0x180033250`
- `0x180033b64`
- `0x18003c7c8`
- `0x180071f50`
- `0x1800961b8`
- `0x1800992d0`
- `0x1800cab20`
- `0x1800e1be0`
- `0x180106010`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800335fe`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800335fe`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800336a3`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800336a3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800332cd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800332cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003339d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033452`
- `OLEAUT32!__imp_SysFreeString` at `0x180033472`
- `OLEAUT32!__imp_SysFreeString` at `0x180033541`
- `OLEAUT32!__imp_SysFreeString` at `0x1800336cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180033955`
- `OLEAUT32!__imp_SysFreeString` at `0x180033975`
- `OLEAUT32!__imp_SysFreeString` at `0x1800339e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180033abd`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b02`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b22`
- `OLEAUT32!__imp_SysFreeString` at `0x18003339d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033452`
- `OLEAUT32!__imp_SysFreeString` at `0x180033472`
- `OLEAUT32!__imp_SysFreeString` at `0x180033541`
- `OLEAUT32!__imp_SysFreeString` at `0x1800336cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180033955`
- `OLEAUT32!__imp_SysFreeString` at `0x180033975`
- `OLEAUT32!__imp_SysFreeString` at `0x1800339e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180033abd`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b02`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b22`
- `OLEAUT32!__imp_SysStringLen` at `0x180033761`
- `OLEAUT32!__imp_SysStringLen` at `0x180033761`

## string_xrefs

- `0x18003350d`: `onecore\printscan\appxpackaging\lib\core\src\xpathhelper.cpp`
- `0x1800333f3`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18003343f`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18003352a`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18003379d`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180033931`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180033998`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180033ae1`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180033b43`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::ManifestReaderBase::ValidateUniqueStrings(
        Appx::Packaging **this,
        struct IXMLDOMNode *a2,
        const struct Appx::Packaging::Manifest::XPathTable *a3,
        unsigned int a4)
{
  int v4; // r15d
  unsigned int v5; // eax
  int v6; // esi
  unsigned int v7; // r12d
  struct IXMLDOMNode *v8; // rdi
  const OLECHAR *v9; // rbx
  struct IStream *v10; // r14
  struct IStream *v11; // r13
  OLECHAR *v12; // rbx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v14; // eax
  struct IStream *v16; // rcx
  struct Common::AutoBStr *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  struct IStream *v20; // rcx
  __int64 v21; // rdx
  OLECHAR *v22; // rdi
  __int64 v23; // rcx
  int v24; // eax
  struct _RTL_AVL_TABLE *v25; // rbx
  struct _RTL_AVL_TABLE *v26; // r14
  RTL_AVL_COMPARE_ROUTINE *v27; // rdx
  int v28; // eax
  unsigned __int64 v29; // r8
  struct IStream *v30; // rcx
  struct IStream *v31; // r14
  __int64 (__fastcall *v32)(struct IStream *, OLECHAR *, unsigned __int16 *); // rsi
  int v33; // eax
  int v34; // eax
  UINT v35; // eax
  __int64 v36; // rcx
  struct IStream *v37; // rcx
  struct IStream *v38; // r15
  __int64 Element; // rax
  struct IStream *v40; // rsi
  Appx::Packaging *v41; // rcx
  unsigned __int64 v42; // r8
  int v43; // eax
  unsigned int v44; // r14d
  unsigned int v45; // edx
  const struct _EVENT_DESCRIPTOR *v46; // rcx
  int v47; // r8d
  struct IStream *v48; // rcx
  __int64 v49; // rcx
  int TableContext; // [rsp+20h] [rbp-99h]
  int TableContexta; // [rsp+20h] [rbp-99h]
  int TableContextb; // [rsp+20h] [rbp-99h]
  unsigned __int16 *v53; // [rsp+30h] [rbp-89h]
  unsigned __int16 *v54; // [rsp+30h] [rbp-89h]
  struct IStream *v55; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 v57[4]; // [rsp+60h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-51h] BYREF
  int v59; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int16 v60[2]; // [rsp+74h] [rbp-45h] BYREF
  unsigned int v61; // [rsp+78h] [rbp-41h] BYREF
  struct IStream *v62; // [rsp+80h] [rbp-39h] BYREF
  struct IStream *v63; // [rsp+88h] [rbp-31h] BYREF
  _QWORD Buffer[2]; // [rsp+90h] [rbp-29h] BYREF
  int v65; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-11h]
  int v67; // [rsp+B0h] [rbp-9h]
  const wchar_t *v68; // [rsp+B8h] [rbp-1h]
  int v69; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  const struct Appx::Packaging::Manifest::XPathTable *v73; // [rsp+130h] [rbp+77h]
  unsigned int v74; // [rsp+138h] [rbp+7Fh] BYREF

  v74 = a4;
  v73 = a3;
  v4 = 0;
  v5 = a4;
  v6 = 0;
  v7 = 0;
  v8 = a2;
  while ( 1 )
  {
    if ( v7 >= v5 )
    {
      if ( v6 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
          (const char *)(unsigned int)v6,
          TableContext);
      return (unsigned int)v6;
    }
    v59 = 0;
    v9 = (const OLECHAR *)*((_QWORD *)a3 + 3 * v7);
    v10 = (const struct Appx::Packaging::Manifest::XPathTable *)((char *)a3 + 24 * v7);
    v63 = v10;
    if ( v8 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->AddRef)(v8);
    v62 = 0;
    v11 = 0;
    v59 = 0;
    v12 = SysAllocString(v9);
    if ( v12 )
    {
      lpVtbl = v8->lpVtbl;
      v55 = 0;
      v59 = 0;
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, struct IStream **))lpVtbl->selectNodes)(
              v8,
              v12,
              &v55);
      v6 = v14;
      if ( v14 < 0 )
      {
        v19 = 139;
      }
      else
      {
        if ( !v55 )
        {
          v6 = 0;
LABEL_17:
          SysFreeString(v12);
          goto LABEL_18;
        }
        v14 = (*(__int64 (__fastcall **)(struct IStream *, int *))(*(_QWORD *)v55 + 64LL))(v55, &v59);
        v6 = v14;
        if ( v14 >= 0 )
        {
          if ( v59 <= 0 )
          {
            v16 = v55;
            if ( v55 )
            {
              v55 = 0;
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v6 = 0;
          }
          else
          {
            v11 = v55;
            v62 = v55;
          }
          goto LABEL_17;
        }
        v19 = 143;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v14,
        TableContext);
      v20 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v20 + 16LL))(v20);
      }
      goto LABEL_17;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)0x8007000ELL,
      TableContext);
    SysFreeString(0);
    v6 = -2147024882;
LABEL_18:
    if ( v8 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)(unsigned int)v6,
        TableContext);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      return (unsigned int)v6;
    }
    if ( v59 > 1 )
      break;
    if ( v11 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_24:
    v5 = v74;
    ++v7;
    a3 = v73;
  }
  v21 = *((_QWORD *)v10 + 1);
  v22 = 0;
  v55 = 0;
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v21 + 2 * v23) );
    if ( (unsigned __int64)(v23 - 1) > 0xFFFFFFFD )
    {
      v6 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xpathhelper.cpp",
        (const char *)0x8000FFFFLL,
        TableContext);
LABEL_38:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F6,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)(unsigned int)v6,
        TableContext);
LABEL_39:
      SysFreeString(v22);
      if ( v11 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)v6;
    }
    v66 = v21;
    v67 = v23;
    v68 = L"']";
    v65 = 5;
    v69 = 0;
    v24 = Appx::Packaging::BuildXPath(
            (Appx::Packaging *)&v65,
            (const struct Appx::Packaging::XPathComponent *)1,
            (BSTR *)&v55,
            v17);
    v22 = (OLECHAR *)v55;
    v6 = v24;
    if ( v24 < 0 )
      goto LABEL_38;
  }
  v25 = 0;
  if ( *((_BYTE *)v10 + 16) )
  {
    v26 = (struct _RTL_AVL_TABLE *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v26 )
      goto LABEL_46;
    v27 = Common::GenericMapCaseInsensitiveCompare;
    goto LABEL_45;
  }
  v26 = (struct _RTL_AVL_TABLE *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v26 )
  {
    v27 = Common::GenericMap<unsigned short const *,Appx::Packaging::Bitmap *>::GenericMapCompare;
LABEL_45:
    v26[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::AutoBStrDeallocate;
    v26[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateCom<IAppxFile *>;
    RtlInitializeGenericTableAvl(
      v26,
      v27,
      Common::GenericMap<unsigned short *,void *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,Appx::Packaging::Bitmap *>::GenericMapFree,
      0);
    Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(0);
    v25 = v26;
  }
LABEL_46:
  while ( 2 )
  {
    if ( v4 >= v59 )
    {
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v25);
      SysFreeString(v22);
      if ( v11 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v11 + 16LL))(v11);
      v8 = a2;
      v4 = 0;
      goto LABEL_24;
    }
    v55 = 0;
    v28 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, struct IStream **))(*(_QWORD *)v11 + 56LL))(
            v11,
            (unsigned int)v4,
            &v55);
    v6 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)(unsigned int)v28,
        TableContext);
      v48 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v48 + 16LL))(v48);
      }
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v25);
      goto LABEL_39;
    }
    bstrString = 0;
    if ( !*((_QWORD *)v63 + 1) )
    {
      v6 = (*(__int64 (__fastcall **)(struct IStream *, BSTR *))(*(_QWORD *)v55 + 208LL))(v55, &bstrString);
      if ( v6 < 0 )
      {
        v18 = 526;
        goto LABEL_28;
      }
      goto LABEL_50;
    }
    *(_QWORD *)v57 = 0;
    v31 = v55;
    v32 = *(__int64 (__fastcall **)(struct IStream *, OLECHAR *, unsigned __int16 *))(*(_QWORD *)v55 + 296LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v57);
    v33 = v32(v31, v22, v57);
    v6 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v33,
        TableContext);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v57);
      goto LABEL_27;
    }
    if ( !*(_QWORD *)v57 )
    {
      v6 = 0;
LABEL_50:
      if ( bstrString )
      {
        Buffer[0] = bstrString;
        Buffer[1] = v55;
        NewElement[0] = 0;
        if ( !RtlInsertElementGenericTableAvl(v25, Buffer, 0x10u, NewElement) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x242,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
            (const char *)0x8007000ELL,
            TableContext);
          SysFreeString(bstrString);
          v37 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v37 + 16LL))(v37);
          }
          Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v25);
          SysFreeString(v22);
          if ( v11 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v11 + 16LL))(v11);
          return 2147942414LL;
        }
        if ( !NewElement[0] )
        {
          *(_DWORD *)v57 = 0;
          v61 = 0;
          v6 = Appx::Packaging::SetStreamPosition(*this, 0, v29);
          if ( v6 < 0 )
          {
            v18 = 549;
            goto LABEL_28;
          }
          v38 = v63;
          Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
            *this,
            v55,
            0,
            *((const unsigned __int16 **)v63 + 1),
            v57,
            &v61,
            (unsigned int *)v53);
          Element = Common::GenericMap<unsigned short *,IXMLDOMNode *>::FindElement(v25, bstrString);
          v40 = 0;
          if ( Element )
            v40 = *(struct IStream **)(Element + 8);
          v63 = v40;
          Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v63);
          v41 = *this;
          *(_DWORD *)v60 = 0;
          v74 = 0;
          v43 = Appx::Packaging::SetStreamPosition(v41, 0, v42);
          v44 = v43;
          if ( v43 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x233,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
              (const char *)(unsigned int)v43,
              TableContexta);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
            SysFreeString(bstrString);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
            Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v25);
            SysFreeString(v22);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
            return v44;
          }
          else
          {
            Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
              *this,
              v40,
              0,
              *((const unsigned __int16 **)v38 + 1),
              v60,
              &v74,
              (unsigned int *)v54);
            if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
              McTemplateU0dqqzzqq_EventWriteTransfer(
                (_DWORD)v46,
                v45,
                v47,
                *(_DWORD *)v57,
                v61,
                *(_QWORD *)v38,
                (__int64)bstrString,
                v60[0],
                v74);
            AppxPackagingLog(
              v46,
              v45,
              v47,
              *(unsigned int *)v57,
              v61,
              *(const unsigned __int16 **)v38,
              bstrString,
              *(unsigned int *)v60,
              v74);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23E,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
              (const char *)0x80080204LL,
              TableContextb);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
            SysFreeString(bstrString);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
            Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v25);
            SysFreeString(v22);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
            return 2148008452LL;
          }
        }
        v6 = 0;
        v55 = 0;
        bstrString = 0;
      }
      SysFreeString(0);
      v30 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v30 + 16LL))(v30);
      }
      ++v4;
      continue;
    }
    break;
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)v57 + 208LL))(*(_QWORD *)v57, &bstrString);
  v6 = v34;
  if ( v34 >= 0 )
  {
    v35 = SysStringLen(bstrString);
    v36 = *(_QWORD *)v57;
    if ( v35 )
    {
      if ( *(_QWORD *)v57 )
      {
        *(_QWORD *)v57 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
    }
    else
    {
      if ( *(_QWORD *)v57 )
      {
        *(_QWORD *)v57 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v6 = 0;
    }
    goto LABEL_50;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x51,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
    (const char *)(unsigned int)v34,
    TableContext);
  v49 = *(_QWORD *)v57;
  if ( *(_QWORD *)v57 )
  {
    *(_QWORD *)v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
LABEL_27:
  v18 = 530;
LABEL_28:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
    (const char *)(unsigned int)v6,
    TableContext);
  SysFreeString(bstrString);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,IXMLDOMNode *>>(v25);
  SysFreeString(v22);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180033250  mov     [rsp-8+arg_18], r9d
0x180033255  mov     [rsp-8+arg_10], r8
0x18003325a  mov     [rsp-8+arg_8], rdx
0x18003325f  mov     [rsp-8+arg_0], rcx
0x180033264  push    rbp
0x180033265  push    rbx
0x180033266  push    rsi
0x180033267  push    rdi
0x180033268  push    r12
0x18003326a  push    r13
0x18003326c  push    r14
0x18003326e  push    r15
0x180033270  lea     rbp, [rsp-1Fh]
0x180033275  sub     rsp, 0D8h
0x18003327c  xor     r15d, r15d
0x18003327f  mov     eax, r9d
0x180033282  mov     esi, r15d
0x180033285  mov     r12d, r15d
0x180033288  mov     rdi, rdx
0x18003328b  cmp     r12d, eax
0x18003328e  jnb     loc_18003335F
0x180033294  mov     eax, r12d
0x180033297  mov     [rbp+57h+var_A0], r15d
0x18003329b  lea     rcx, [rax+rax*2]
0x18003329f  mov     rbx, [r8+rcx*8]
0x1800332a3  lea     r14, [r8+rcx*8]
0x1800332a7  mov     [rbp+57h+var_88], r14
0x1800332ab  test    rdi, rdi
0x1800332ae  jz      short loc_1800332BF
0x1800332b0  mov     rax, [rdi]
0x1800332b3  mov     rcx, rdi
0x1800332b6  mov     rax, [rax+8]
0x1800332ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332bf  mov     rcx, rbx; psz
0x1800332c2  mov     [rbp+57h+var_90], r15
0x1800332c6  mov     r13, r15
0x1800332c9  mov     [rbp+57h+var_A0], r15d
0x1800332cd  call    cs:__imp_SysAllocString
0x1800332d4  nop     dword ptr [rax+rax+00h]
0x1800332d9  mov     rbx, rax
0x1800332dc  test    rax, rax
0x1800332df  jz      loc_180033AA0
0x1800332e5  mov     rax, [rdi]
0x1800332e8  lea     r8, [rbp+57h+var_C0]
0x1800332ec  mov     rdx, rbx
0x1800332ef  mov     [rbp+57h+var_C0], r15
0x1800332f3  mov     rcx, rdi
0x1800332f6  mov     [rbp+57h+var_A0], r15d
0x1800332fa  mov     rax, [rax+120h]
0x180033301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033306  mov     esi, eax
0x180033308  test    eax, eax
0x18003330a  js      loc_18003348C
0x180033310  mov     rcx, [rbp+57h+var_C0]
0x180033314  test    rcx, rcx
0x180033317  jz      loc_180033A98
0x18003331d  mov     rax, [rcx]
0x180033320  lea     rdx, [rbp+57h+var_A0]
0x180033324  mov     rax, [rax+40h]
0x180033328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003332d  mov     esi, eax
0x18003332f  test    eax, eax
0x180033331  js      loc_1800334C6
0x180033337  cmp     [rbp+57h+var_A0], 0
0x18003333b  jle     short loc_18003337E
0x18003333d  mov     r13, [rbp+57h+var_C0]
0x180033341  mov     rcx, r15
0x180033344  mov     [rbp+57h+var_90], r13
0x180033348  test    r15, r15
0x18003334b  jz      short loc_18003339A
0x18003334d  mov     [rbp+57h+var_C0], r15
0x180033351  mov     rax, [r15]
0x180033354  mov     rax, [rax+10h]
0x180033358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003335d  jmp     short loc_18003339A
0x18003335f  test    esi, esi
0x180033361  js      loc_180033B3F
0x180033367  mov     eax, esi
0x180033369  add     rsp, 0D8h
0x180033370  pop     r15
0x180033372  pop     r14
0x180033374  pop     r13
0x180033376  pop     r12
0x180033378  pop     rdi
0x180033379  pop     rsi
0x18003337a  pop     rbx
0x18003337b  pop     rbp
0x18003337c  retn
0x18003337e  mov     rcx, [rbp+57h+var_C0]
0x180033382  test    rcx, rcx
0x180033385  jz      short loc_180033397
0x180033387  mov     [rbp+57h+var_C0], r15
0x18003338b  mov     rax, [rcx]
0x18003338e  mov     rax, [rax+10h]
0x180033392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033397  mov     esi, r15d
0x18003339a  mov     rcx, rbx; bstrString
0x18003339d  call    cs:__imp_SysFreeString
0x1800333a4  nop     dword ptr [rax+rax+00h]
0x1800333a9  test    rdi, rdi
0x1800333ac  jz      short loc_1800333BD
0x1800333ae  mov     rax, [rdi]
0x1800333b1  mov     rcx, rdi
0x1800333b4  mov     rax, [rax+10h]
0x1800333b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333bd  test    esi, esi
0x1800333bf  js      short loc_1800333EF
0x1800333c1  cmp     [rbp+57h+var_A0], 1
0x1800333c5  jg      loc_1800334CD
0x1800333cb  test    r13, r13
0x1800333ce  jz      short loc_1800333E0
0x1800333d0  mov     rax, [r13+0]
0x1800333d4  mov     rcx, r13
0x1800333d7  mov     rax, [rax+10h]
0x1800333db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333e0  mov     eax, [rbp+57h+arg_18]
0x1800333e3  inc     r12d
0x1800333e6  mov     r8, [rbp+57h+arg_10]
0x1800333ea  jmp     loc_18003328B
0x1800333ef  mov     rcx, [rbp+5Fh]; this
0x1800333f3  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x1800333fa  mov     r9d, esi; char *
0x1800333fd  mov     edx, 1EBh; void *
0x180033402  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033407  lea     rcx, [rbp+57h+var_90]
0x18003340b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180033410  jmp     loc_180033367
0x180033415  mov     rcx, [rbp+5Fh]; this
0x180033419  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180033420  mov     r9d, eax; char *
0x180033423  mov     edx, 4Dh ; 'M'; void *
0x180033428  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003342d  lea     rcx, [rbp+57h+var_B0]
0x180033431  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180033436  mov     edx, 212h; void *
0x18003343b  mov     rcx, [rbp+5Fh]; this
0x18003343f  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x180033446  mov     r9d, esi; char *
0x180033449  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003344e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180033452  call    cs:__imp_SysFreeString
0x180033459  nop     dword ptr [rax+rax+00h]
0x18003345e  lea     rcx, [rbp+57h+var_C0]
0x180033462  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180033467  mov     rcx, rbx; void *
0x18003346a  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUIXMLDOMNode@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUIXMLDOMNode@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,IXMLDOMNode *>>(Common::GenericMap<ushort *,IXMLDOMNode *> *)
0x18003346f  mov     rcx, rdi; bstrString
0x180033472  call    cs:__imp_SysFreeString
0x180033479  nop     dword ptr [rax+rax+00h]
0x18003347e  lea     rcx, [rbp+57h+var_90]
0x180033482  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180033487  jmp     loc_180033367
0x18003348c  mov     edx, 8Bh; void *
0x180033491  mov     rcx, [rbp+5Fh]; this
0x180033495  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18003349c  mov     r9d, eax; char *
0x18003349f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800334a4  mov     rcx, [rbp+57h+var_C0]
0x1800334a8  test    rcx, rcx
0x1800334ab  jz      loc_18003339A
0x1800334b1  mov     [rbp+57h+var_C0], r15
0x1800334b5  mov     rax, [rcx]
0x1800334b8  mov     rax, [rax+10h]
0x1800334bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334c1  jmp     loc_18003339A
0x1800334c6  mov     edx, 8Fh
0x1800334cb  jmp     short loc_180033491
0x1800334cd  mov     rdx, [r14+8]
0x1800334d1  mov     rdi, r15
0x1800334d4  mov     [rbp+57h+var_C0], r15
0x1800334d8  test    rdx, rdx
0x1800334db  jz      loc_1800335A4
0x1800334e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800334e8  nop     dword ptr [rax+rax+00000000h]
0x1800334f0  inc     rcx
0x1800334f3  cmp     word ptr [rdx+rcx*2], 0
0x1800334f8  jnz     short loc_1800334F0
0x1800334fa  lea     rax, [rcx-1]
0x1800334fe  mov     r8d, 0FFFFFFFDh
0x180033504  cmp     rax, r8
0x180033507  jbe     short loc_18003356B
0x180033509  mov     rcx, [rbp+5Fh]; this
0x18003350d  lea     r8, aOnecorePrintsc_117; "onecore\\printscan\\appxpackaging\\lib"...
0x180033514  mov     esi, 8000FFFFh
0x180033519  mov     edx, 6Ah ; 'j'; void *
0x18003351e  mov     r9d, esi; char *
0x180033521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033526  mov     rcx, [rbp+5Fh]; this
0x18003352a  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x180033531  mov     r9d, esi; char *
0x180033534  mov     edx, 1F6h; void *
0x180033539  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003353e  mov     rcx, rdi; bstrString
0x180033541  call    cs:__imp_SysFreeString
0x180033548  nop     dword ptr [rax+rax+00h]
0x18003354d  test    r13, r13
0x180033550  jz      loc_180033367
0x180033556  mov     rax, [r13+0]
0x18003355a  mov     rcx, r13
0x18003355d  mov     rax, [rax+10h]
0x180033561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033566  jmp     loc_180033367
0x18003356b  mov     [rbp+57h+var_68], rdx
0x18003356f  lea     rax, asc_1801177B4; "']"
0x180033576  mov     [rbp+57h+var_60], ecx
0x180033579  lea     r8, [rbp+57h+var_C0]; unsigned int
0x18003357d  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180033582  mov     [rbp+57h+var_58], rax
0x180033586  lea     rcx, [rbp+57h+var_70]; this
0x18003358a  mov     [rbp+57h+var_70], 5
0x180033591  mov     [rbp+57h+var_50], r15d
0x180033595  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18003359a  mov     rdi, [rbp+57h+var_C0]
0x18003359e  mov     esi, eax
0x1800335a0  test    eax, eax
0x1800335a2  js      short loc_180033526
0x1800335a4  cmp     byte ptr [r14+10h], 0
0x1800335a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800335b0  mov     rbx, r15
0x1800335b3  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800335b8  jz      loc_180033A7B
0x1800335be  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800335c3  mov     r14, rax
0x1800335c6  test    rax, rax
0x1800335c9  jz      short loc_180033614
0x1800335cb  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800335d2  lea     rax, ?AutoBStrDeallocate@Common@@YAXPEAG@Z; Common::AutoBStrDeallocate(ushort *)
0x1800335d9  mov     [rsp+110h+TableContext], r15; int
0x1800335de  mov     [r14+68h], rax
0x1800335e2  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800335e9  lea     rax, ??$DeallocateCom@PEAUIAppxFile@@@Common@@YAXPEAUIAppxFile@@@Z; Common::DeallocateCom<IAppxFile *>(IAppxFile *)
0x1800335f0  mov     rcx, r14; Table
0x1800335f3  lea     r8, ?GenericMapAllocate@?$GenericMap@PEAGPEAX@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800335fa  mov     [r14+70h], rax
0x1800335fe  call    cs:__imp_RtlInitializeGenericTableAvl
0x180033605  nop     dword ptr [rax+rax+00h]
0x18003360a  xor     ecx, ecx; void *
0x18003360c  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUIXMLDOMNode@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUIXMLDOMNode@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,IXMLDOMNode *>>(Common::GenericMap<ushort *,IXMLDOMNode *> *)
0x180033611  mov     rbx, r14
0x180033614  cmp     r15d, [rbp+57h+var_A0]
0x180033618  jge     loc_1800339DD
0x18003361e  xor     r14d, r14d
0x180033621  lea     r8, [rbp+57h+var_C0]
0x180033625  mov     [rbp+57h+var_C0], r14
0x180033629  mov     edx, r15d
0x18003362c  mov     rax, [r13+0]
0x180033630  mov     rcx, r13
0x180033633  mov     rax, [rax+38h]
0x180033637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003363c  mov     esi, eax
0x18003363e  test    eax, eax
0x180033640  js      loc_180033994
0x180033646  mov     rax, [rbp+57h+var_88]
0x18003364a  mov     [rbp+57h+bstrString], r14
0x18003364e  cmp     [rax+8], r14
0x180033652  jnz     loc_1800336FC
0x180033658  mov     rcx, [rbp+57h+var_C0]
0x18003365c  lea     rdx, [rbp+57h+bstrString]
0x180033660  mov     rax, [rcx]
0x180033663  mov     rax, [rax+0D0h]
0x18003366a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003366f  mov     esi, eax
0x180033671  test    eax, eax
0x180033673  js      loc_180033A33
0x180033679  mov     rax, [rbp+57h+bstrString]
0x18003367d  test    rax, rax
0x180033680  jz      short loc_1800336CD
0x180033682  mov     [rbp+57h+Buffer], rax
0x180033686  lea     r9, [rbp+57h+NewElement]; NewElement
0x18003368a  mov     rax, [rbp+57h+var_C0]
0x18003368e  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180033692  mov     r8d, 10h; BufferSize
0x180033698  mov     [rbp+57h+var_78], rax
0x18003369c  mov     rcx, rbx; Table
0x18003369f  mov     [rbp+57h+NewElement], 0
0x1800336a3  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800336aa  nop     dword ptr [rax+rax+00h]
0x1800336af  test    rax, rax
0x1800336b2  jz      loc_180033799
0x1800336b8  cmp     [rbp+57h+NewElement], 0
0x1800336bc  jz      loc_180033813
0x1800336c2  mov     esi, r14d
0x1800336c5  mov     [rbp+57h+var_C0], r14
0x1800336c9  mov     [rbp+57h+bstrString], r14
0x1800336cd  xor     ecx, ecx; bstrString
0x1800336cf  call    cs:__imp_SysFreeString
0x1800336d6  nop     dword ptr [rax+rax+00h]
0x1800336db  mov     rcx, [rbp+57h+var_C0]
0x1800336df  test    rcx, rcx
0x1800336e2  jz      short loc_1800336F4
0x1800336e4  mov     [rbp+57h+var_C0], r14
0x1800336e8  mov     rax, [rcx]
0x1800336eb  mov     rax, [rax+10h]
0x1800336ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336f4  inc     r15d
0x1800336f7  jmp     loc_180033614
0x1800336fc  mov     qword ptr [rbp+57h+var_B0], r14
0x180033700  lea     rcx, [rbp+57h+var_B0]
0x180033704  mov     r14, [rbp+57h+var_C0]
0x180033708  mov     rax, [r14]
  ... truncated ...
```

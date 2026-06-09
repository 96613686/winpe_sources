# UniDrvUI::CPrintTicketProvider::ValidatePrintTicket(IXMLDOMDocument2 *)

- ea: `0x180101de0`
- end: `0x18010264e`
- name: `?ValidatePrintTicket@CPrintTicketProvider@UniDrvUI@@UEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `2158`
- prototype: `__int64 __fastcall(UniDrvUI::CPrintTicketProvider *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18001878c`
- `0x1800e80f8`
- `0x1800ea034`
- `0x1800ec048`
- `0x1800ec5d4`
- `0x1800ef400`
- `0x1800ef528`
- `0x1800f5af4`
- `0x1800f6778`
- `0x1800f8fac`
- `0x1800f9058`
- `0x1800fa9ac`
- `0x1800faa10`
- `0x1800fb18c`
- `0x1800fbe84`
- `0x1800fbf4c`
- `0x1801005b8`
- `0x180101de0`
- `0x180106b84`
- `0x18010d0b0`
- `0x180118408`
- `0x1801185f4`
- `0x18011a2e8`
- `0x180147f9c`
- `0x1801483a4`
- `0x1801483ec`
- `0x180149e58`
- `0x1801adb04`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1801024d7`
- `KERNEL32!FreeLibrary` at `0x1801024d7`
- `KERNEL32!LocalFree` at `0x180102576`
- `KERNEL32!LocalFree` at `0x180102576`
- `KERNEL32!LoadLibraryExW` at `0x1801024c2`
- `KERNEL32!LoadLibraryExW` at `0x1801024c2`
- `OLEAUT32!__imp_SysAllocString` at `0x180102191`
- `OLEAUT32!__imp_SysAllocString` at `0x180102191`
- `OLEAUT32!__imp_SysFreeString` at `0x18010222f`
- `OLEAUT32!__imp_SysFreeString` at `0x180102245`
- `OLEAUT32!__imp_SysFreeString` at `0x18010222f`
- `OLEAUT32!__imp_SysFreeString` at `0x180102245`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x180102511`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x180102511`

## string_xrefs

- `0x1801024ff`: `Windows.PrintSupportExtension`
- `0x1801024b5`: `Print.PrintSupport.Source.dll`
- `0x18010215c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180102197`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1801022c9`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18010230e`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall UniDrvUI::CPrintTicketProvider::ValidatePrintTicket(
        UniDrvUI::CPrintTicketProvider *this,
        struct IXMLDOMDocument2 *a2,
        int a3)
{
  OLECHAR *v3; // r13
  struct IXMLDOMDocument2 *v4; // r12
  int v7; // edi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned int v11; // ecx
  __int64 v12; // rcx
  unsigned int v13; // ebx
  struct _devicemodeW *v14; // r14
  int v15; // r8d
  int ValidatedDevmode; // eax
  struct _devicemodeW *v17; // r9
  int v18; // eax
  struct IXMLDOMElement *v19; // rdx
  int v20; // ebx
  int v21; // r15d
  int v22; // eax
  int v23; // r15d
  int v24; // eax
  int v25; // eax
  unsigned int v26; // r8d
  unsigned int v27; // r15d
  __int64 v28; // rdi
  struct _UIINFO *v29; // r15
  struct PSUI::_COMMONINFO *v30; // r12
  const CHAR *v31; // rcx
  const unsigned __int16 *v32; // rdi
  __int64 v33; // rdx
  OLECHAR *BSTRFromANSI; // rax
  struct IXMLDOMElement *v35; // rdx
  int PrintSchema; // eax
  UniDrvUI *v37; // rcx
  const char *v38; // rax
  PSUI *v39; // r11
  const unsigned __int16 *v40; // r14
  struct IXMLDOMElement *v41; // rdx
  int v42; // edi
  int v43; // eax
  int v44; // edi
  int v45; // eax
  __int64 v46; // rdx
  int v47; // eax
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r8
  int v51; // eax
  struct _OPTSELECT *v52; // r9
  struct NPrintTicketUtil::CPrintTicketWrapper *v53; // r9
  HMODULE Library; // rax
  __int64 v55; // rax
  int v56; // eax
  int v57; // eax
  bool v58; // zf
  int IsJScriptCapableDriver; // eax
  unsigned int i; // edi
  __int64 v61; // rdx
  __int64 v62; // rax
  unsigned int v63; // ecx
  __int64 v64; // rcx
  struct _devicemodeW *v65; // [rsp+20h] [rbp-E0h]
  struct _devicemodeW *v66; // [rsp+20h] [rbp-E0h]
  unsigned int v67; // [rsp+28h] [rbp-D8h]
  struct _devicemodeW *v68; // [rsp+30h] [rbp-D0h] BYREF
  struct _devicemodeW *v69; // [rsp+38h] [rbp-C8h] BYREF
  int v70; // [rsp+40h] [rbp-C0h]
  unsigned int v71; // [rsp+44h] [rbp-BCh]
  BSTR v72; // [rsp+48h] [rbp-B8h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMDocument2 *v74; // [rsp+58h] [rbp-A8h]
  void **v75; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v76; // [rsp+68h] [rbp-98h]
  __int64 v77; // [rsp+78h] [rbp-88h]
  __int16 v78; // [rsp+80h] [rbp-80h]
  int v79; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 v80[4]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v81[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v82; // [rsp+98h] [rbp-68h]
  __int64 v83; // [rsp+A8h] [rbp-58h]
  __int16 v84; // [rsp+B0h] [rbp-50h]
  int v85; // [rsp+B4h] [rbp-4Ch]
  struct _devicemodeW v86; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v3 = 0;
  v74 = a2;
  v4 = a2;
  if ( !a2 )
    return 2147942487LL;
  HIDWORD(v68) = 262145;
  *(_QWORD *)v81 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v82 = 0;
  v7 = 0;
  v83 = 0;
  v84 = 0;
  v8 = 0;
  v85 = 0;
  do
  {
    v9 = *((_QWORD *)this + 4);
    v10 = *(_QWORD *)(v9 + 136);
    if ( v10 )
      v11 = *(_DWORD *)(*(_QWORD *)(v10 + 80) + 8LL);
    else
      v11 = 0;
    if ( v8 >= v11 )
      break;
    v12 = *(_QWORD *)(v9 + 8LL * (int)v8 + 72);
    if ( v12 )
      v7 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *))(*(_QWORD *)v12 + 80LL))(v12, v4);
    ++v8;
  }
  while ( v7 >= 0 );
  if ( v7 >= 0 )
    v7 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)v81, v4, a3);
  v13 = 0;
  v69 = 0;
  v71 = 0;
  LOBYTE(v86.dmDeviceName[0]) = 0;
  v14 = 0;
  memset_0((char *)v86.dmDeviceName + 1, 0, 0x3FFu);
  if ( v7 >= 0 )
  {
    ValidatedDevmode = UniDrvUI::CPrintTicketProvider::GetValidatedDevmode(this, 0, 0, &v69);
    v14 = v69;
    v7 = ValidatedDevmode;
    if ( ValidatedDevmode >= 0 )
    {
      v13 = v69->dmSize + v69->dmDriverExtra;
      v71 = v13;
    }
  }
  v75 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v76 = 0;
  if ( v7 >= 0 )
  {
    v7 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v75, v4, v15);
    if ( v7 >= 0 )
    {
      if ( (*((_BYTE *)this + 56) & 1) != 0
        || (v7 = publicdm::DevmodeSnapshotFromJT(
                   (publicdm *)&v75,
                   *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 6),
                   v14->dmDeviceName,
                   v17),
            v7 >= 0) )
      {
        v18 = UniDrvUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(
                this,
                (struct NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                v13,
                v14);
        v7 = v18;
        if ( v18 == 262146 || (HIDWORD(v68) = 262145, v18 >= 0) )
        {
          HIDWORD(v68) = 262146 - (v18 != 262146);
          LODWORD(v65) = UniDrvUI::CPrintTicketProvider::GetPublicDMShimFlags(this);
          v7 = publicdm::JobTicketToPublicDevmode(
                 **((publicdm ***)this + 4),
                 &v75,
                 *(struct NPrintTicketUtil::CPrintTicketWrapper **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                 *((const unsigned __int16 **)this + 6),
                 v65->dmDeviceName,
                 (unsigned int)v14,
                 v68);
          v3 = 0;
        }
      }
    }
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v75);
  v20 = 0;
  v21 = 0;
  if ( v7 < 0 )
    v20 = v7;
  if ( v20 >= 0 )
  {
    while ( off_1801D1670[2 * v21] )
    {
      do
      {
        v22 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                (NPrintTicketUtil::CPrintTicketWrapper *)v81,
                v19,
                off_1801D1678[2 * v21],
                off_1801D1670[2 * v21]);
        v20 = v22;
      }
      while ( !v22 );
      v14 = v69;
      ++v21;
      if ( v22 < 0 )
        goto LABEL_95;
    }
    v23 = 0;
    while ( off_1801D1790[2 * v23].lpVtbl )
    {
      do
      {
        v24 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                (NPrintTicketUtil::CPrintTicketWrapper *)v81,
                off_1801D1798[2 * v23],
                (const unsigned __int16 *)off_1801D1790[2 * v23].lpVtbl);
        v20 = v24;
      }
      while ( !v24 );
      v14 = v69;
      ++v23;
      if ( v24 < 0 )
        goto LABEL_95;
    }
    do
    {
      v25 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
              (NPrintTicketUtil::CPrintTicketWrapper *)v81,
              *((const unsigned __int16 **)this + 6),
              (const unsigned __int16 *)&stru_1801FDBD8);
      v20 = v25;
    }
    while ( !v25 );
    if ( v25 >= 0 )
    {
      v27 = 0;
      v70 = 0;
      while ( 1 )
      {
        v28 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 72LL);
        if ( v27 >= *(_DWORD *)(v28 + 24) + *(_DWORD *)(v28 + 28)
          || (v29 = (struct _UIINFO *)(*(_QWORD *)(v28 + 328) + *(unsigned int *)(v28 + 32) + 84LL * v27)) == 0 )
        {
LABEL_72:
          v4 = v74;
          if ( v20 >= 0 )
          {
            v77 = 0;
            v75 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
            v78 = 0;
            v79 = 0;
            v76 = 0;
            v20 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                    (NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                    v74,
                    v26);
            v42 = 0;
            if ( v20 >= 0 )
            {
              do
              {
                if ( !(&UniDrvUI::gpUnidrvSupportedFeatureNames)[v42] )
                  break;
                do
                {
                  v43 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                          v41,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (const unsigned __int16 *)(&UniDrvUI::gpUnidrvSupportedFeatureNames)[v42]);
                  v20 = v43;
                }
                while ( !v43 );
                ++v42;
              }
              while ( v43 >= 0 );
              v14 = v69;
            }
            v44 = 0;
            if ( v20 >= 0 )
            {
              do
              {
                if ( !(&UniDrvUI::gpUnidrvSupportedParameterNames)[v44] )
                  break;
                do
                {
                  v45 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (const unsigned __int16 *)(&UniDrvUI::gpUnidrvSupportedParameterNames)[v44]);
                  v20 = v45;
                }
                while ( !v45 );
                ++v44;
              }
              while ( v45 >= 0 );
              v4 = v74;
            }
            NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v75);
            if ( v20 >= 0 )
            {
              v47 = PGetDevmodeOptionsArray(v14, v46, *(_QWORD *)(*((_QWORD *)this + 4) + 136LL));
              if ( !(unsigned int)CombineOptionArray(
                                    *(_QWORD *)(*(_QWORD *)(v48 + 48) + 40LL),
                                    (unsigned int)&v86,
                                    512,
                                    v47,
                                    *(_QWORD *)(v48 + 104) + 48LL) )
                goto LABEL_90;
              if ( (unsigned int)ResolveUIConflicts(
                                   *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                                   &v86,
                                   512,
                                   2) )
              {
                if ( HIDWORD(v68) != 262146 )
                  HIDWORD(v68) = 262145;
              }
              else
              {
                HIDWORD(v68) = 262146;
              }
              v51 = PGetDevmodeOptionsArray(v14, v49, v50);
              SeparateOptionArray(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                (unsigned int)&v86,
                v51,
                256,
                0);
              UniDrvUI::VOptionsToDevmodeFields(
                *(UniDrvUI **)(*((_QWORD *)this + 4) + 136LL),
                (struct UniDrvUI::_COMMONINFO *)v14,
                &v86,
                0,
                1,
                v67);
              if ( UniDrvUI::bDocOptionArrayToJTKeywords(
                     *(UniDrvUI **)(*((_QWORD *)this + 4) + 136LL),
                     (struct UniDrvUI::_COMMONINFO *)v14,
                     &v86,
                     v52) )
              {
                if ( (*((_BYTE *)this + 56) & 1) != 0
                  || (v20 = publicdm::DevmodeSnapshotToJT(
                              (publicdm *)v14,
                              *((struct _devicemodeW **)this + 6),
                              v81,
                              v53),
                      v20 >= 0) )
                {
                  LODWORD(v65) = UniDrvUI::CPrintTicketProvider::GetPublicDMShimFlags(this);
                  v20 = publicdm::PublicDevmodeToJobTicket(
                          **((publicdm ***)this + 4),
                          *(void **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                          *((const unsigned __int16 **)this + 6),
                          v14->dmDeviceName,
                          v65,
                          (unsigned int)v81,
                          (struct NPrintTicketUtil::CPrintTicketWrapper *)v68);
                  if ( v20 >= 0 )
                    v20 = UniDrvUI::CPrintTicketProvider::ConvertDevModeToPrintTicketInternal(this, v71, v14, v4);
                }
              }
              else
              {
LABEL_90:
                v20 = -2147467259;
              }
            }
          }
          goto LABEL_95;
        }
        if ( *((_DWORD *)v29 + 11) <= 1u )
        {
          v72 = 0;
          *(_QWORD *)v80 = 0;
          if ( *(_DWORD *)v29 )
            v30 = (struct PSUI::_COMMONINFO *)(*(_QWORD *)(v28 + 320) + *(unsigned int *)v29);
          else
            v30 = 0;
          if ( *((_DWORD *)v29 + 1) )
            v31 = (const CHAR *)(*(_QWORD *)(v28 + 320) + *((unsigned int *)v29 + 1));
          else
            v31 = 0;
          if ( !v30 )
          {
            v20 = -2147418113;
            goto LABEL_72;
          }
          if ( *((_DWORD *)v29 + 7) == 0xFFFF || v31 )
            break;
        }
LABEL_69:
        v27 = ++v70;
        if ( v20 < 0 )
          goto LABEL_72;
      }
      bstrString = 0;
      if ( v31 )
      {
        v32 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
        v33 = -1;
        do
          ++v33;
        while ( v31[v33] );
        BSTRFromANSI = UniDrvUI::CreateBSTRFromANSI(v31, (const char *)v33, v26);
      }
      else
      {
        if ( strcmp_0((const char *)v30, "Stapling") )
        {
          PrintSchema = PSUI::GetPrintSchemaNamespace<_FEATURE>(v28, v29, *((_QWORD *)this + 6), &bstrString);
          v3 = bstrString;
          v20 = PrintSchema;
          if ( PrintSchema < 0 )
          {
LABEL_65:
            if ( v3 )
              SysFreeString(v3);
            v3 = 0;
            if ( v72 )
              SysFreeString(v72);
            goto LABEL_69;
          }
          v32 = bstrString;
          v38 = (const char *)UniDrvUI::_SelectPrefixForFeature(
                                v37,
                                *(struct _RAWBINARYDATA **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 64LL),
                                *(struct _INFOHEADER **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 72LL),
                                v29,
                                (struct _FEATURE *)v65);
          v20 = PSUI::ConvertParserName(v39, v30, v38, v80, (struct NCoreLibrary::TAutoPtrBSTR *)v66);
          BSTRFromANSI = *(OLECHAR **)v80;
          goto LABEL_60;
        }
        BSTRFromANSI = SysAllocString(L"JobStapleAllDocuments");
        v32 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
      }
      if ( !BSTRFromANSI )
      {
        v20 = -2147024882;
        goto LABEL_61;
      }
LABEL_60:
      v72 = BSTRFromANSI;
LABEL_61:
      if ( v20 >= 0 )
      {
        v40 = v72;
        do
          v20 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                  (NPrintTicketUtil::CPrintTicketWrapper *)v81,
                  v35,
                  v32,
                  v40);
        while ( !v20 );
        v14 = v69;
      }
      goto LABEL_65;
    }
  }
LABEL_95:
  if ( !`PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isLoadLibraryCheckDone )
  {
    Library = LoadLibraryExW(L"Print.PrintSupport.Source.dll", 0, 0x800u);
    if ( Library )
    {
      `PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isPrintSupportAvailable = 1;
      FreeLibrary(Library);
    }
    `PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isLoadLibraryCheckDone = 1;
  }
  if ( `PrintSupportUtil::IsPrintSupportAvailable'::`2'::s_isPrintSupportAvailable )
  {
    v55 = *((_QWORD *)this + 4);
    LOBYTE(v68) = 0;
    v56 = IsPsaEnabledForContract(*(_QWORD *)(*(_QWORD *)(v55 + 136) + 24LL), L"Windows.PrintSupportExtension", &v68);
    if ( v56 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDD1,
        (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
        (const char *)(unsigned int)v56,
        (int)v65);
    if ( (_BYTE)v68 )
    {
      v57 = UniDrvUI::CPrintTicketProvider::PerformPsaValidatePrintTicket(this, v4);
      if ( v20 >= 0 )
        goto LABEL_104;
      goto LABEL_109;
    }
  }
  if ( v20 >= 0 )
  {
    IsJScriptCapableDriver = UniDrvUI::CPrintTicketProvider::IsJScriptCapableDriver(this);
    v20 = IsJScriptCapableDriver;
    if ( !IsJScriptCapableDriver )
    {
      v57 = UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(this, v4);
LABEL_104:
      v20 = v57;
LABEL_105:
      if ( v20 >= 0 )
      {
        if ( HIDWORD(v68) == 262146 || (v58 = v20 == 262146, v20 = 262145, v58) )
          v20 = 262146;
      }
      goto LABEL_109;
    }
    if ( IsJScriptCapableDriver >= 0 )
    {
      v20 = 262145;
      for ( i = 0; ; ++i )
      {
        while ( 1 )
        {
          v61 = *((_QWORD *)this + 4);
          v62 = *(_QWORD *)(v61 + 136);
          if ( v62 )
            v63 = *(_DWORD *)(*(_QWORD *)(v62 + 80) + 8LL);
          else
            v63 = 0;
          if ( i >= v63 )
            goto LABEL_105;
          v64 = *(_QWORD *)(v61 + 8LL * (int)i + 72);
          if ( v64 )
            break;
LABEL_126:
          ++i;
        }
        v57 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *))(*(_QWORD *)v64 + 88LL))(v64, v4);
        if ( v57 < 0 )
          goto LABEL_104;
        if ( v57 != 262146 )
        {
          if ( v57 != 262145 )
          {
            v20 = -2147467259;
            goto LABEL_105;
          }
          goto LABEL_126;
        }
        v20 = 262146;
      }
    }
  }
LABEL_109:
  if ( v14 )
    LocalFree(v14);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v81);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180101de0  mov     [rsp-8+arg_10], rbx
0x180101de5  push    rbp
0x180101de6  push    rsi
0x180101de7  push    rdi
0x180101de8  push    r12
0x180101dea  push    r13
0x180101dec  push    r14
0x180101dee  push    r15
0x180101df0  lea     rbp, [rsp-3D0h]
0x180101df8  sub     rsp, 4D0h
0x180101dff  mov     rax, cs:__security_cookie
0x180101e06  xor     rax, rsp
0x180101e09  mov     [rbp+400h+var_40], rax
0x180101e10  xor     r13d, r13d
0x180101e13  mov     [rsp+500h+var_4A8], rdx
0x180101e18  mov     r12, rdx
0x180101e1b  mov     rsi, rcx
0x180101e1e  test    rdx, rdx
0x180101e21  jnz     short loc_180101E2D
0x180101e23  mov     eax, 80070057h
0x180101e28  jmp     loc_180102587
0x180101e2d  lea     r15, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180101e34  mov     [rsp+500h+var_4CC], 40001h
0x180101e3c  xorps   xmm0, xmm0
0x180101e3f  mov     qword ptr [rbp+400h+var_470], r15
0x180101e43  movdqu  [rbp+400h+var_468], xmm0
0x180101e48  mov     edi, r13d
0x180101e4b  mov     [rbp+400h+var_458], r13
0x180101e4f  mov     [rbp+400h+var_450], r13w
0x180101e54  mov     ebx, r13d
0x180101e57  mov     [rbp+400h+var_44C], r13d
0x180101e5b  mov     rdx, [rsi+20h]
0x180101e5f  mov     rax, [rdx+88h]
0x180101e66  test    rax, rax
0x180101e69  jz      short loc_180101E74
0x180101e6b  mov     rax, [rax+50h]
0x180101e6f  mov     ecx, [rax+8]
0x180101e72  jmp     short loc_180101E77
0x180101e74  mov     ecx, r13d
0x180101e77  cmp     ebx, ecx
0x180101e79  jnb     short loc_180101E9F
0x180101e7b  movsxd  rax, ebx
0x180101e7e  mov     rcx, [rdx+rax*8+48h]
0x180101e83  test    rcx, rcx
0x180101e86  jz      short loc_180101E99
0x180101e88  mov     rax, [rcx]
0x180101e8b  mov     rdx, r12
0x180101e8e  mov     rax, [rax+50h]
0x180101e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e97  mov     edi, eax
0x180101e99  inc     ebx
0x180101e9b  test    edi, edi
0x180101e9d  jns     short loc_180101E5B
0x180101e9f  test    edi, edi
0x180101ea1  js      short loc_180101EB1
0x180101ea3  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180101ea6  lea     rcx, [rbp+400h+var_470]; this
0x180101eaa  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180101eaf  mov     edi, eax
0x180101eb1  mov     ebx, r13d
0x180101eb4  mov     [rsp+500h+var_4C8], r13
0x180101eb9  xor     edx, edx; Val
0x180101ebb  mov     [rsp+500h+var_4BC], ebx
0x180101ebf  mov     r8d, 3FFh; Size
0x180101ec5  mov     byte ptr [rbp+400h+var_440.dmDeviceName], r13b
0x180101ec9  lea     rcx, [rbp+400h+var_440.dmDeviceName+1]; void *
0x180101ecd  mov     r14, r13
0x180101ed0  call    memset_0
0x180101ed5  test    edi, edi
0x180101ed7  js      short loc_180101F06
0x180101ed9  lea     r9, [rsp+500h+var_4C8]; struct _devicemodeW **
0x180101ede  xor     r8d, r8d; struct _devicemodeW *
0x180101ee1  xor     edx, edx; unsigned int
0x180101ee3  mov     rcx, rsi; this
0x180101ee6  call    ?GetValidatedDevmode@CPrintTicketProvider@UniDrvUI@@IEAAJKPEAU_devicemodeW@@PEAPEAU3@@Z; UniDrvUI::CPrintTicketProvider::GetValidatedDevmode(ulong,_devicemodeW *,_devicemodeW * *)
0x180101eeb  mov     r14, [rsp+500h+var_4C8]
0x180101ef0  mov     edi, eax
0x180101ef2  test    eax, eax
0x180101ef4  js      short loc_180101F06
0x180101ef6  movzx   ebx, word ptr [r14+46h]
0x180101efb  movzx   eax, word ptr [r14+44h]
0x180101f00  add     ebx, eax
0x180101f02  mov     [rsp+500h+var_4BC], ebx
0x180101f06  mov     [rsp+500h+var_4A0], r15
0x180101f0b  xorps   xmm0, xmm0
0x180101f0e  mov     [rsp+500h+var_488], r13
0x180101f13  mov     r15d, 40002h
0x180101f19  mov     [rbp+400h+var_480], r13w
0x180101f1e  mov     [rbp+400h+var_47C], r13d
0x180101f22  movdqu  [rsp+500h+var_498], xmm0
0x180101f28  test    edi, edi
0x180101f2a  js      loc_180101FD2
0x180101f30  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180101f33  lea     rcx, [rsp+500h+var_4A0]; this
0x180101f38  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180101f3d  mov     edi, eax
0x180101f3f  test    eax, eax
0x180101f41  js      loc_180101FD2
0x180101f47  test    byte ptr [rsi+38h], 1
0x180101f4b  jnz     short loc_180101F64
0x180101f4d  mov     rdx, [rsi+30h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180101f51  lea     rcx, [rsp+500h+var_4A0]; this
0x180101f56  mov     r8, r14; unsigned __int16 *
0x180101f59  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x180101f5e  mov     edi, eax
0x180101f60  test    eax, eax
0x180101f62  js      short loc_180101FD2
0x180101f64  mov     r9, r14; struct _devicemodeW *
0x180101f67  lea     rdx, [rsp+500h+var_4A0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180101f6c  mov     r8d, ebx; unsigned int
0x180101f6f  mov     rcx, rsi; this
0x180101f72  call    ?ConvertPrintTicketToDevModeInternal@CPrintTicketProvider@UniDrvUI@@IEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@KPEAU_devicemodeW@@@Z; UniDrvUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(NPrintTicketUtil::CPrintTicketWrapper *,ulong,_devicemodeW *)
0x180101f77  mov     edi, eax
0x180101f79  cmp     eax, r15d
0x180101f7c  jz      short loc_180101F8A
0x180101f7e  mov     [rsp+500h+var_4CC], 40001h
0x180101f86  test    eax, eax
0x180101f88  js      short loc_180101FD2
0x180101f8a  mov     eax, r15d
0x180101f8d  mov     rcx, rsi; this
0x180101f90  sub     eax, edi
0x180101f92  neg     eax
0x180101f94  sbb     r13d, r13d
0x180101f97  add     r13d, r15d
0x180101f9a  mov     [rsp+500h+var_4CC], r13d
0x180101f9f  call    ?GetPublicDMShimFlags@CPrintTicketProvider@UniDrvUI@@QEAAKXZ; UniDrvUI::CPrintTicketProvider::GetPublicDMShimFlags(void)
0x180101fa4  mov     rcx, [rsi+20h]
0x180101fa8  lea     rdx, [rsp+500h+var_4A0]; void *
0x180101fad  mov     r9, [rsi+30h]; unsigned __int16 *
0x180101fb1  mov     qword ptr [rsp+500h+var_4D8], r14; unsigned int
0x180101fb6  mov     dword ptr [rsp+500h+var_4E0], eax; struct NCoreLibrary::TAutoPtrBSTR *
0x180101fba  mov     r8, [rcx+88h]
0x180101fc1  mov     rcx, [rcx]; this
0x180101fc4  mov     r8, [r8+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180101fc8  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x180101fcd  mov     edi, eax
0x180101fcf  xor     r13d, r13d
0x180101fd2  lea     rcx, [rsp+500h+var_4A0]; this
0x180101fd7  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180101fdc  test    edi, edi
0x180101fde  mov     ebx, r13d
0x180101fe1  mov     r15d, r13d
0x180101fe4  cmovs   ebx, edi
0x180101fe7  test    ebx, ebx
0x180101fe9  js      loc_1801024AA
0x180101fef  lea     rax, __ImageBase
0x180101ff6  movsxd  rdi, r15d
0x180101ff9  add     rdi, rdi
0x180101ffc  cmp     ds:rva off_1801D1670[rax+rdi*8], r13; "DocumentCollate" ...
0x180102004  jz      short loc_180102044
0x180102006  lea     r14, __ImageBase
0x18010200d  mov     r9, ds:rva off_1801D1670[r14+rdi*8]; unsigned __int16 *
0x180102015  lea     rcx, [rbp+400h+var_470]; this
0x180102019  mov     r8, ds:rva off_1801D1678[r14+rdi*8]; unsigned __int16 *
0x180102021  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x180102026  mov     ebx, eax
0x180102028  test    eax, eax
0x18010202a  jz      short loc_18010200D
0x18010202c  mov     r14, [rsp+500h+var_4C8]
0x180102031  inc     r15d
0x180102034  test    eax, eax
0x180102036  lea     rax, __ImageBase
0x18010203d  jns     short loc_180101FF6
0x18010203f  jmp     loc_1801024AA
0x180102044  mov     r15d, r13d
0x180102047  movsxd  rdi, r15d
0x18010204a  add     rdi, rdi
0x18010204d  cmp     ds:rva off_1801D1790[rax+rdi*8], r13
0x180102055  jz      short loc_180102095
0x180102057  lea     r14, __ImageBase
0x18010205e  mov     r8, ds:rva off_1801D1790[r14+rdi*8]; unsigned __int16 *
0x180102066  lea     rcx, [rbp+400h+var_470]; this
0x18010206a  mov     rdx, ds:rva off_1801D1798[r14+rdi*8]; unsigned __int16 *
0x180102072  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x180102077  mov     ebx, eax
0x180102079  test    eax, eax
0x18010207b  jz      short loc_18010205E
0x18010207d  mov     r14, [rsp+500h+var_4C8]
0x180102082  inc     r15d
0x180102085  test    eax, eax
0x180102087  lea     rax, __ImageBase
0x18010208e  jns     short loc_180102047
0x180102090  jmp     loc_1801024AA
0x180102095  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180102099  lea     r8, stru_1801FDBD8; unsigned __int16 *
0x1801020a0  lea     rcx, [rbp+400h+var_470]; this
0x1801020a4  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x1801020a9  mov     ebx, eax
0x1801020ab  test    eax, eax
0x1801020ad  jz      short loc_180102095
0x1801020af  js      loc_1801024AA
0x1801020b5  mov     r15d, r13d
0x1801020b8  mov     [rsp+500h+var_4C0], r13d
0x1801020bd  mov     rax, [rsi+20h]
0x1801020c1  mov     rcx, [rax+88h]
0x1801020c8  mov     rdi, [rcx+48h]
0x1801020cc  mov     eax, [rdi+1Ch]
0x1801020cf  add     eax, [rdi+18h]
0x1801020d2  cmp     r15d, eax
0x1801020d5  jnb     loc_180102267
0x1801020db  mov     edx, [rdi+20h]
0x1801020de  mov     eax, r15d
0x1801020e1  imul    r15, rax, 54h ; 'T'
0x1801020e5  add     r15, rdx
0x1801020e8  add     r15, [rdi+148h]
0x1801020ef  jz      loc_180102267
0x1801020f5  cmp     dword ptr [r15+2Ch], 1
0x1801020fa  ja      loc_18010224B
0x180102100  mov     rax, r13
0x180102103  mov     [rsp+500h+var_4B8], rax
0x180102108  mov     qword ptr [rbp+400h+var_478], rax
0x18010210c  cmp     [r15], r13d
0x18010210f  jz      short loc_18010211D
0x180102111  mov     r12d, [r15]
0x180102114  add     r12, [rdi+140h]
0x18010211b  jmp     short loc_180102120
0x18010211d  mov     r12, r13
0x180102120  cmp     [r15+4], r13d
0x180102124  jz      short loc_180102133
0x180102126  mov     ecx, [r15+4]
0x18010212a  add     rcx, [rdi+140h]
0x180102131  jmp     short loc_180102136
0x180102133  mov     rcx, r13; lpMultiByteStr
0x180102136  test    r12, r12
0x180102139  jz      loc_180102262
0x18010213f  cmp     dword ptr [r15+1Ch], 0FFFFh
0x180102147  jz      short loc_180102152
0x180102149  test    rcx, rcx
0x18010214c  jz      loc_18010224B
0x180102152  mov     [rsp+500h+bstrString], r13
0x180102157  test    rcx, rcx
0x18010215a  jz      short loc_180102177
0x18010215c  lea     rdi, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x180102163  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180102167  inc     rdx; cchWideChar
0x18010216a  cmp     byte ptr [rcx+rdx], 0
0x18010216e  jnz     short loc_180102167
0x180102170  call    ?CreateBSTRFromANSI@UniDrvUI@@YAPEAGPEBDK@Z; UniDrvUI::CreateBSTRFromANSI(char const *,ulong)
0x180102175  jmp     short loc_18010219E
0x180102177  lea     rdx, aStapling; "Stapling"
0x18010217e  mov     rcx, r12; Str1
0x180102181  call    strcmp_0
0x180102186  test    eax, eax
0x180102188  jnz     short loc_1801021AA
0x18010218a  lea     rcx, aJobstaplealldo_0; "JobStapleAllDocuments"
0x180102191  call    cs:__imp_SysAllocString
0x180102197  lea     rdi, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x18010219e  test    rax, rax
0x1801021a1  jnz     short loc_1801021FF
0x1801021a3  mov     ebx, 8007000Eh
0x1801021a8  jmp     short loc_180102204
0x1801021aa  mov     r8, [rsi+30h]
0x1801021ae  lea     r9, [rsp+500h+bstrString]
0x1801021b3  mov     rdx, r15
0x1801021b6  mov     rcx, rdi
0x1801021b9  call    ??$GetPrintSchemaNamespace@U_FEATURE@@@PSUI@@YAJPEAU_UIINFO@@PEAU_FEATURE@@PEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::GetPrintSchemaNamespace<_FEATURE>(_UIINFO *,_FEATURE *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x1801021be  mov     r13, [rsp+500h+bstrString]
0x1801021c3  mov     ebx, eax
0x1801021c5  test    eax, eax
0x1801021c7  js      short loc_180102227
0x1801021c9  mov     rax, [rsi+20h]
0x1801021cd  mov     r9, r15; struct _UIINFO *
0x1801021d0  mov     rdi, r13
0x1801021d3  mov     r11, [rax+88h]
0x1801021da  mov     r8, [r11+48h]; struct _INFOHEADER *
0x1801021de  mov     rdx, [r11+40h]; struct _RAWBINARYDATA *
0x1801021e2  call    ?_SelectPrefixForFeature@UniDrvUI@@YAPEBGPEAU_RAWBINARYDATA@@PEAU_INFOHEADER@@PEAU_UIINFO@@PEAU_FEATURE@@@Z; UniDrvUI::_SelectPrefixForFeature(_RAWBINARYDATA *,_INFOHEADER *,_UIINFO *,_FEATURE *)
0x1801021e7  mov     r8, rax; char *
0x1801021ea  lea     r9, [rbp+400h+var_478]; unsigned __int16 *
0x1801021ee  mov     rcx, r11; this
0x1801021f1  mov     rdx, r12; struct PSUI::_COMMONINFO *
0x1801021f4  call    ?ConvertParserName@PSUI@@YAJPEAU_COMMONINFO@1@PEBDPEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::ConvertParserName(PSUI::_COMMONINFO *,char const *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x1801021f9  mov     ebx, eax
0x1801021fb  mov     rax, qword ptr [rbp+400h+var_478]
0x1801021ff  mov     [rsp+500h+var_4B8], rax
0x180102204  test    ebx, ebx
0x180102206  js      short loc_180102227
0x180102208  mov     r14, [rsp+500h+var_4B8]
0x18010220d  mov     r9, r14; unsigned __int16 *
0x180102210  lea     rcx, [rbp+400h+var_470]; this
0x180102214  mov     r8, rdi; unsigned __int16 *
0x180102217  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x18010221c  mov     ebx, eax
0x18010221e  test    eax, eax
0x180102220  jz      short loc_18010220D
0x180102222  mov     r14, [rsp+500h+var_4C8]
0x180102227  test    r13, r13
0x18010222a  jz      short loc_180102235
0x18010222c  mov     rcx, r13; bstrString
0x18010222f  call    cs:__imp_SysFreeString
0x180102235  mov     rax, [rsp+500h+var_4B8]
0x18010223a  xor     r13d, r13d
0x18010223d  test    rax, rax
0x180102240  jz      short loc_18010224B
0x180102242  mov     rcx, rax; bstrString
0x180102245  call    cs:__imp_SysFreeString
0x18010224b  mov     r15d, [rsp+500h+var_4C0]
0x180102250  inc     r15d
0x180102253  mov     [rsp+500h+var_4C0], r15d
0x180102258  test    ebx, ebx
  ... truncated ...
```

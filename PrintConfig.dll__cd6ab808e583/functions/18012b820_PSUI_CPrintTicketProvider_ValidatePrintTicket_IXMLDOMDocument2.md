# PSUI::CPrintTicketProvider::ValidatePrintTicket(IXMLDOMDocument2 *)

- ea: `0x18012b820`
- end: `0x18012c08e`
- name: `?ValidatePrintTicket@CPrintTicketProvider@PSUI@@UEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `2158`
- prototype: `__int64 __fastcall(PSUI::CPrintTicketProvider *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18001878c`
- `0x1800e80f8`
- `0x1800ea034`
- `0x1800ef400`
- `0x1800ef528`
- `0x1800f8fac`
- `0x1800f9058`
- `0x1800fa9ac`
- `0x1800faa10`
- `0x1800fb18c`
- `0x1800fbe84`
- `0x1800fbf4c`
- `0x1801005b8`
- `0x180118408`
- `0x1801185f4`
- `0x180126338`
- `0x1801268c4`
- `0x18012b174`
- `0x18012b410`
- `0x18012b820`
- `0x18012e72c`
- `0x18013404c`
- `0x1801403a4`
- `0x180147f9c`
- `0x1801483a4`
- `0x1801483ec`
- `0x180149e58`
- `0x1801adb04`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18012bf17`
- `KERNEL32!FreeLibrary` at `0x18012bf17`
- `KERNEL32!LocalFree` at `0x18012bfb6`
- `KERNEL32!LocalFree` at `0x18012bfb6`
- `KERNEL32!LoadLibraryExW` at `0x18012bf02`
- `KERNEL32!LoadLibraryExW` at `0x18012bf02`
- `OLEAUT32!__imp_SysAllocString` at `0x18012bbd1`
- `OLEAUT32!__imp_SysAllocString` at `0x18012bbd1`
- `OLEAUT32!__imp_SysFreeString` at `0x18012bc77`
- `OLEAUT32!__imp_SysFreeString` at `0x18012bc8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18012bc77`
- `OLEAUT32!__imp_SysFreeString` at `0x18012bc8d`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x18012bf51`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x18012bf51`

## string_xrefs

- `0x18012bf3f`: `Windows.PrintSupportExtension`
- `0x18012bef5`: `Print.PrintSupport.Source.dll`
- `0x18012bb9c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18012bbd7`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18012bd11`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18012bd56`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall PSUI::CPrintTicketProvider::ValidatePrintTicket(
        PSUI::CPrintTicketProvider *this,
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
  __int64 v37; // rbx
  const char *v38; // rax
  const unsigned __int16 *v39; // r14
  struct IXMLDOMElement *v40; // rdx
  int v41; // edi
  int v42; // eax
  int v43; // edi
  int v44; // eax
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  int v50; // eax
  struct _OPTSELECT *v51; // r9
  struct NPrintTicketUtil::CPrintTicketWrapper *v52; // r9
  HMODULE Library; // rax
  __int64 v54; // rax
  int v55; // eax
  int v56; // eax
  bool v57; // zf
  int IsJScriptCapableDriver; // eax
  unsigned int i; // edi
  __int64 v60; // rdx
  __int64 v61; // rax
  unsigned int v62; // ecx
  __int64 v63; // rcx
  struct _devicemodeW *v64; // [rsp+20h] [rbp-E0h]
  struct _devicemodeW *v65; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+20h] [rbp-E0h]
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
    ValidatedDevmode = PSUI::CPrintTicketProvider::GetValidatedDevmode(this, 0, 0, &v69);
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
        v18 = PSUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(
                this,
                (struct NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                v13,
                v14);
        v7 = v18;
        if ( v18 == 262146 || (HIDWORD(v68) = 262145, v18 >= 0) )
        {
          HIDWORD(v68) = 262146 - (v18 != 262146);
          LODWORD(v64) = PSUI::CPrintTicketProvider::GetPublicDMShimFlags(this);
          v7 = publicdm::JobTicketToPublicDevmode(
                 **((publicdm ***)this + 4),
                 &v75,
                 *(struct NPrintTicketUtil::CPrintTicketWrapper **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                 *((const unsigned __int16 **)this + 6),
                 v64->dmDeviceName,
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
    while ( off_1801D1BC0[2 * v21] )
    {
      do
      {
        v22 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                (NPrintTicketUtil::CPrintTicketWrapper *)v81,
                v19,
                off_1801D1BC8[2 * v21],
                off_1801D1BC0[2 * v21]);
        v20 = v22;
      }
      while ( !v22 );
      v14 = v69;
      ++v21;
      if ( v22 < 0 )
        goto LABEL_95;
    }
    v23 = 0;
    while ( off_1801D1CE0[2 * v23] )
    {
      do
      {
        v24 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                (NPrintTicketUtil::CPrintTicketWrapper *)v81,
                off_1801D1CE8[2 * v23],
                off_1801D1CE0[2 * v23]);
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
              L"PageDevmodeSnapshot");
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
            v41 = 0;
            if ( v20 >= 0 )
            {
              do
              {
                if ( !(&PSUI::gpPScriptSupportedFeatureNames)[v41] )
                  break;
                do
                {
                  v42 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                          v40,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (const unsigned __int16 *)(&PSUI::gpPScriptSupportedFeatureNames)[v41]);
                  v20 = v42;
                }
                while ( !v42 );
                ++v41;
              }
              while ( v42 >= 0 );
              v14 = v69;
            }
            v43 = 0;
            if ( v20 >= 0 )
            {
              do
              {
                if ( !(&UniDrvUI::gpUnidrvSupportedParameterNames)[v43] )
                  break;
                do
                {
                  v44 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v75,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (const unsigned __int16 *)(&UniDrvUI::gpUnidrvSupportedParameterNames)[v43]);
                  v20 = v44;
                }
                while ( !v44 );
                ++v43;
              }
              while ( v44 >= 0 );
              v4 = v74;
            }
            NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v75);
            if ( v20 >= 0 )
            {
              v46 = PGetDevmodeOptionsArray(v14, v45, *(_QWORD *)(*((_QWORD *)this + 4) + 136LL));
              if ( !(unsigned int)CombineOptionArray(
                                    *(_QWORD *)(*(_QWORD *)(v47 + 48) + 40LL),
                                    (unsigned int)&v86,
                                    512,
                                    v46,
                                    *(_QWORD *)(v47 + 104) + 48LL) )
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
              v50 = PGetDevmodeOptionsArray(v14, v48, v49);
              SeparateOptionArray(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                (unsigned int)&v86,
                v50,
                256,
                0);
              PSUI::VOptionsToDevmodeFields(
                *(PSUI **)(*((_QWORD *)this + 4) + 136LL),
                (struct PSUI::_COMMONINFO *)v14,
                &v86,
                0,
                v66,
                v67);
              if ( PSUI::bDocOptionArrayToJTKeywords(
                     *(PSUI **)(*((_QWORD *)this + 4) + 136LL),
                     (struct PSUI::_COMMONINFO *)v14,
                     &v86,
                     v51) )
              {
                if ( (*((_BYTE *)this + 56) & 1) != 0
                  || (v20 = publicdm::DevmodeSnapshotToJT(
                              (publicdm *)v14,
                              *((struct _devicemodeW **)this + 6),
                              v81,
                              v52),
                      v20 >= 0) )
                {
                  LODWORD(v64) = PSUI::CPrintTicketProvider::GetPublicDMShimFlags(this);
                  v20 = publicdm::PublicDevmodeToJobTicket(
                          **((publicdm ***)this + 4),
                          *(void **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                          *((const unsigned __int16 **)this + 6),
                          v14->dmDeviceName,
                          v64,
                          (unsigned int)v81,
                          (struct NPrintTicketUtil::CPrintTicketWrapper *)v68);
                  if ( v20 >= 0 )
                    v20 = PSUI::CPrintTicketProvider::ConvertDevModeToPrintTicketInternal(this, v71, v14, v4);
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
          v37 = *(_QWORD *)(*((_QWORD *)this + 4) + 136LL);
          v38 = (const char *)PSUI::_SelectPrefixForFeature(
                                *(PSUI **)(*(_QWORD *)(v37 + 48) + 40LL),
                                *(struct _RAWBINARYDATA **)(v37 + 64),
                                *(struct _INFOHEADER **)(v37 + 72),
                                v29,
                                (struct _FEATURE *)v64);
          v20 = PSUI::ConvertParserName((PSUI *)v37, v30, v38, v80, (struct NCoreLibrary::TAutoPtrBSTR *)v65);
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
        v39 = v72;
        do
          v20 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                  (NPrintTicketUtil::CPrintTicketWrapper *)v81,
                  v35,
                  v32,
                  v39);
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
    v54 = *((_QWORD *)this + 4);
    LOBYTE(v68) = 0;
    v55 = IsPsaEnabledForContract(*(_QWORD *)(*(_QWORD *)(v54 + 136) + 24LL), L"Windows.PrintSupportExtension", &v68);
    if ( v55 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDD1,
        (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
        (const char *)(unsigned int)v55,
        (int)v64);
    if ( (_BYTE)v68 )
    {
      v56 = UniDrvUI::CPrintTicketProvider::PerformPsaValidatePrintTicket(this, v4);
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
      v56 = UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(this, v4);
LABEL_104:
      v20 = v56;
LABEL_105:
      if ( v20 >= 0 )
      {
        if ( HIDWORD(v68) == 262146 || (v57 = v20 == 262146, v20 = 262145, v57) )
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
          v60 = *((_QWORD *)this + 4);
          v61 = *(_QWORD *)(v60 + 136);
          if ( v61 )
            v62 = *(_DWORD *)(*(_QWORD *)(v61 + 80) + 8LL);
          else
            v62 = 0;
          if ( i >= v62 )
            goto LABEL_105;
          v63 = *(_QWORD *)(v60 + 8LL * (int)i + 72);
          if ( v63 )
            break;
LABEL_126:
          ++i;
        }
        v56 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *))(*(_QWORD *)v63 + 88LL))(v63, v4);
        if ( v56 < 0 )
          goto LABEL_104;
        if ( v56 != 262146 )
        {
          if ( v56 != 262145 )
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
0x18012b820  mov     [rsp-8+arg_10], rbx
0x18012b825  push    rbp
0x18012b826  push    rsi
0x18012b827  push    rdi
0x18012b828  push    r12
0x18012b82a  push    r13
0x18012b82c  push    r14
0x18012b82e  push    r15
0x18012b830  lea     rbp, [rsp-3D0h]
0x18012b838  sub     rsp, 4D0h
0x18012b83f  mov     rax, cs:__security_cookie
0x18012b846  xor     rax, rsp
0x18012b849  mov     [rbp+400h+var_40], rax
0x18012b850  xor     r13d, r13d
0x18012b853  mov     [rsp+500h+var_4A8], rdx
0x18012b858  mov     r12, rdx
0x18012b85b  mov     rsi, rcx
0x18012b85e  test    rdx, rdx
0x18012b861  jnz     short loc_18012B86D
0x18012b863  mov     eax, 80070057h
0x18012b868  jmp     loc_18012BFC7
0x18012b86d  lea     r15, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x18012b874  mov     [rsp+500h+var_4CC], 40001h
0x18012b87c  xorps   xmm0, xmm0
0x18012b87f  mov     qword ptr [rbp+400h+var_470], r15
0x18012b883  movdqu  [rbp+400h+var_468], xmm0
0x18012b888  mov     edi, r13d
0x18012b88b  mov     [rbp+400h+var_458], r13
0x18012b88f  mov     [rbp+400h+var_450], r13w
0x18012b894  mov     ebx, r13d
0x18012b897  mov     [rbp+400h+var_44C], r13d
0x18012b89b  mov     rdx, [rsi+20h]
0x18012b89f  mov     rax, [rdx+88h]
0x18012b8a6  test    rax, rax
0x18012b8a9  jz      short loc_18012B8B4
0x18012b8ab  mov     rax, [rax+50h]
0x18012b8af  mov     ecx, [rax+8]
0x18012b8b2  jmp     short loc_18012B8B7
0x18012b8b4  mov     ecx, r13d
0x18012b8b7  cmp     ebx, ecx
0x18012b8b9  jnb     short loc_18012B8DF
0x18012b8bb  movsxd  rax, ebx
0x18012b8be  mov     rcx, [rdx+rax*8+48h]
0x18012b8c3  test    rcx, rcx
0x18012b8c6  jz      short loc_18012B8D9
0x18012b8c8  mov     rax, [rcx]
0x18012b8cb  mov     rdx, r12
0x18012b8ce  mov     rax, [rax+50h]
0x18012b8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b8d7  mov     edi, eax
0x18012b8d9  inc     ebx
0x18012b8db  test    edi, edi
0x18012b8dd  jns     short loc_18012B89B
0x18012b8df  test    edi, edi
0x18012b8e1  js      short loc_18012B8F1
0x18012b8e3  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18012b8e6  lea     rcx, [rbp+400h+var_470]; this
0x18012b8ea  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18012b8ef  mov     edi, eax
0x18012b8f1  mov     ebx, r13d
0x18012b8f4  mov     [rsp+500h+var_4C8], r13
0x18012b8f9  xor     edx, edx; Val
0x18012b8fb  mov     [rsp+500h+var_4BC], ebx
0x18012b8ff  mov     r8d, 3FFh; Size
0x18012b905  mov     byte ptr [rbp+400h+var_440.dmDeviceName], r13b
0x18012b909  lea     rcx, [rbp+400h+var_440.dmDeviceName+1]; void *
0x18012b90d  mov     r14, r13
0x18012b910  call    memset_0
0x18012b915  test    edi, edi
0x18012b917  js      short loc_18012B946
0x18012b919  lea     r9, [rsp+500h+var_4C8]; struct _devicemodeW **
0x18012b91e  xor     r8d, r8d; struct _devicemodeW *
0x18012b921  xor     edx, edx; unsigned int
0x18012b923  mov     rcx, rsi; this
0x18012b926  call    ?GetValidatedDevmode@CPrintTicketProvider@PSUI@@IEAAJKPEAU_devicemodeW@@PEAPEAU3@@Z; PSUI::CPrintTicketProvider::GetValidatedDevmode(ulong,_devicemodeW *,_devicemodeW * *)
0x18012b92b  mov     r14, [rsp+500h+var_4C8]
0x18012b930  mov     edi, eax
0x18012b932  test    eax, eax
0x18012b934  js      short loc_18012B946
0x18012b936  movzx   ebx, word ptr [r14+46h]
0x18012b93b  movzx   eax, word ptr [r14+44h]
0x18012b940  add     ebx, eax
0x18012b942  mov     [rsp+500h+var_4BC], ebx
0x18012b946  mov     [rsp+500h+var_4A0], r15
0x18012b94b  xorps   xmm0, xmm0
0x18012b94e  mov     [rsp+500h+var_488], r13
0x18012b953  mov     r15d, 40002h
0x18012b959  mov     [rbp+400h+var_480], r13w
0x18012b95e  mov     [rbp+400h+var_47C], r13d
0x18012b962  movdqu  [rsp+500h+var_498], xmm0
0x18012b968  test    edi, edi
0x18012b96a  js      loc_18012BA12
0x18012b970  mov     rdx, r12; struct IXMLDOMDocument2 *
0x18012b973  lea     rcx, [rsp+500h+var_4A0]; this
0x18012b978  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18012b97d  mov     edi, eax
0x18012b97f  test    eax, eax
0x18012b981  js      loc_18012BA12
0x18012b987  test    byte ptr [rsi+38h], 1
0x18012b98b  jnz     short loc_18012B9A4
0x18012b98d  mov     rdx, [rsi+30h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18012b991  lea     rcx, [rsp+500h+var_4A0]; this
0x18012b996  mov     r8, r14; unsigned __int16 *
0x18012b999  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x18012b99e  mov     edi, eax
0x18012b9a0  test    eax, eax
0x18012b9a2  js      short loc_18012BA12
0x18012b9a4  mov     r9, r14; struct _devicemodeW *
0x18012b9a7  lea     rdx, [rsp+500h+var_4A0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18012b9ac  mov     r8d, ebx; unsigned int
0x18012b9af  mov     rcx, rsi; this
0x18012b9b2  call    ?ConvertPrintTicketToDevModeInternal@CPrintTicketProvider@PSUI@@IEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@KPEAU_devicemodeW@@@Z; PSUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(NPrintTicketUtil::CPrintTicketWrapper *,ulong,_devicemodeW *)
0x18012b9b7  mov     edi, eax
0x18012b9b9  cmp     eax, r15d
0x18012b9bc  jz      short loc_18012B9CA
0x18012b9be  mov     [rsp+500h+var_4CC], 40001h
0x18012b9c6  test    eax, eax
0x18012b9c8  js      short loc_18012BA12
0x18012b9ca  mov     eax, r15d
0x18012b9cd  mov     rcx, rsi; this
0x18012b9d0  sub     eax, edi
0x18012b9d2  neg     eax
0x18012b9d4  sbb     r13d, r13d
0x18012b9d7  add     r13d, r15d
0x18012b9da  mov     [rsp+500h+var_4CC], r13d
0x18012b9df  call    ?GetPublicDMShimFlags@CPrintTicketProvider@PSUI@@QEAAKXZ; PSUI::CPrintTicketProvider::GetPublicDMShimFlags(void)
0x18012b9e4  mov     rcx, [rsi+20h]
0x18012b9e8  lea     rdx, [rsp+500h+var_4A0]; void *
0x18012b9ed  mov     r9, [rsi+30h]; unsigned __int16 *
0x18012b9f1  mov     qword ptr [rsp+500h+var_4D8], r14; unsigned int
0x18012b9f6  mov     dword ptr [rsp+500h+var_4E0], eax; struct NCoreLibrary::TAutoPtrBSTR *
0x18012b9fa  mov     r8, [rcx+88h]
0x18012ba01  mov     rcx, [rcx]; this
0x18012ba04  mov     r8, [r8+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18012ba08  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x18012ba0d  mov     edi, eax
0x18012ba0f  xor     r13d, r13d
0x18012ba12  lea     rcx, [rsp+500h+var_4A0]; this
0x18012ba17  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18012ba1c  test    edi, edi
0x18012ba1e  mov     ebx, r13d
0x18012ba21  mov     r15d, r13d
0x18012ba24  cmovs   ebx, edi
0x18012ba27  test    ebx, ebx
0x18012ba29  js      loc_18012BEEA
0x18012ba2f  lea     rax, __ImageBase
0x18012ba36  movsxd  rdi, r15d
0x18012ba39  add     rdi, rdi
0x18012ba3c  cmp     ds:rva off_1801D1BC0[rax+rdi*8], r13; "DocumentCollate" ...
0x18012ba44  jz      short loc_18012BA84
0x18012ba46  lea     r14, __ImageBase
0x18012ba4d  mov     r9, ds:rva off_1801D1BC0[r14+rdi*8]; unsigned __int16 *
0x18012ba55  lea     rcx, [rbp+400h+var_470]; this
0x18012ba59  mov     r8, ds:rva off_1801D1BC8[r14+rdi*8]; unsigned __int16 *
0x18012ba61  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x18012ba66  mov     ebx, eax
0x18012ba68  test    eax, eax
0x18012ba6a  jz      short loc_18012BA4D
0x18012ba6c  mov     r14, [rsp+500h+var_4C8]
0x18012ba71  inc     r15d
0x18012ba74  test    eax, eax
0x18012ba76  lea     rax, __ImageBase
0x18012ba7d  jns     short loc_18012BA36
0x18012ba7f  jmp     loc_18012BEEA
0x18012ba84  mov     r15d, r13d
0x18012ba87  movsxd  rdi, r15d
0x18012ba8a  add     rdi, rdi
0x18012ba8d  cmp     ds:rva off_1801D1CE0[rax+rdi*8], r13; "JobCopiesAllDocuments" ...
0x18012ba95  jz      short loc_18012BAD5
0x18012ba97  lea     r14, __ImageBase
0x18012ba9e  mov     r8, ds:rva off_1801D1CE0[r14+rdi*8]; unsigned __int16 *
0x18012baa6  lea     rcx, [rbp+400h+var_470]; this
0x18012baaa  mov     rdx, ds:rva off_1801D1CE8[r14+rdi*8]; unsigned __int16 *
0x18012bab2  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x18012bab7  mov     ebx, eax
0x18012bab9  test    eax, eax
0x18012babb  jz      short loc_18012BA9E
0x18012babd  mov     r14, [rsp+500h+var_4C8]
0x18012bac2  inc     r15d
0x18012bac5  test    eax, eax
0x18012bac7  lea     rax, __ImageBase
0x18012bace  jns     short loc_18012BA87
0x18012bad0  jmp     loc_18012BEEA
0x18012bad5  mov     rdx, [rsi+30h]; unsigned __int16 *
0x18012bad9  lea     r8, aPagedevmodesna_1; "PageDevmodeSnapshot"
0x18012bae0  lea     rcx, [rbp+400h+var_470]; this
0x18012bae4  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x18012bae9  mov     ebx, eax
0x18012baeb  test    eax, eax
0x18012baed  jz      short loc_18012BAD5
0x18012baef  js      loc_18012BEEA
0x18012baf5  mov     r15d, r13d
0x18012baf8  mov     [rsp+500h+var_4C0], r13d
0x18012bafd  mov     rax, [rsi+20h]
0x18012bb01  mov     rcx, [rax+88h]
0x18012bb08  mov     rdi, [rcx+48h]
0x18012bb0c  mov     eax, [rdi+1Ch]
0x18012bb0f  add     eax, [rdi+18h]
0x18012bb12  cmp     r15d, eax
0x18012bb15  jnb     loc_18012BCAF
0x18012bb1b  mov     edx, [rdi+20h]
0x18012bb1e  mov     eax, r15d
0x18012bb21  imul    r15, rax, 54h ; 'T'
0x18012bb25  add     r15, rdx
0x18012bb28  add     r15, [rdi+148h]
0x18012bb2f  jz      loc_18012BCAF
0x18012bb35  cmp     dword ptr [r15+2Ch], 1
0x18012bb3a  ja      loc_18012BC93
0x18012bb40  mov     rax, r13
0x18012bb43  mov     [rsp+500h+var_4B8], rax
0x18012bb48  mov     qword ptr [rbp+400h+var_478], rax
0x18012bb4c  cmp     [r15], r13d
0x18012bb4f  jz      short loc_18012BB5D
0x18012bb51  mov     r12d, [r15]
0x18012bb54  add     r12, [rdi+140h]
0x18012bb5b  jmp     short loc_18012BB60
0x18012bb5d  mov     r12, r13
0x18012bb60  cmp     [r15+4], r13d
0x18012bb64  jz      short loc_18012BB73
0x18012bb66  mov     ecx, [r15+4]
0x18012bb6a  add     rcx, [rdi+140h]
0x18012bb71  jmp     short loc_18012BB76
0x18012bb73  mov     rcx, r13; lpMultiByteStr
0x18012bb76  test    r12, r12
0x18012bb79  jz      loc_18012BCAA
0x18012bb7f  cmp     dword ptr [r15+1Ch], 0FFFFh
0x18012bb87  jz      short loc_18012BB92
0x18012bb89  test    rcx, rcx
0x18012bb8c  jz      loc_18012BC93
0x18012bb92  mov     [rsp+500h+bstrString], r13
0x18012bb97  test    rcx, rcx
0x18012bb9a  jz      short loc_18012BBB7
0x18012bb9c  lea     rdi, aHttpSchemasMic_18; "http://schemas.microsoft.com/windows/20"...
0x18012bba3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18012bba7  inc     rdx; cchWideChar
0x18012bbaa  cmp     byte ptr [rcx+rdx], 0
0x18012bbae  jnz     short loc_18012BBA7
0x18012bbb0  call    ?CreateBSTRFromANSI@UniDrvUI@@YAPEAGPEBDK@Z; UniDrvUI::CreateBSTRFromANSI(char const *,ulong)
0x18012bbb5  jmp     short loc_18012BBDE
0x18012bbb7  lea     rdx, aStapling; "Stapling"
0x18012bbbe  mov     rcx, r12; Str1
0x18012bbc1  call    strcmp_0
0x18012bbc6  test    eax, eax
0x18012bbc8  jnz     short loc_18012BBEA
0x18012bbca  lea     rcx, aJobstaplealldo_2; "JobStapleAllDocuments"
0x18012bbd1  call    cs:__imp_SysAllocString
0x18012bbd7  lea     rdi, aHttpSchemasMic_18; "http://schemas.microsoft.com/windows/20"...
0x18012bbde  test    rax, rax
0x18012bbe1  jnz     short loc_18012BC47
0x18012bbe3  mov     ebx, 8007000Eh
0x18012bbe8  jmp     short loc_18012BC4C
0x18012bbea  mov     r8, [rsi+30h]
0x18012bbee  lea     r9, [rsp+500h+bstrString]
0x18012bbf3  mov     rdx, r15
0x18012bbf6  mov     rcx, rdi
0x18012bbf9  call    ??$GetPrintSchemaNamespace@U_FEATURE@@@PSUI@@YAJPEAU_UIINFO@@PEAU_FEATURE@@PEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::GetPrintSchemaNamespace<_FEATURE>(_UIINFO *,_FEATURE *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x18012bbfe  mov     r13, [rsp+500h+bstrString]
0x18012bc03  mov     ebx, eax
0x18012bc05  test    eax, eax
0x18012bc07  js      short loc_18012BC6F
0x18012bc09  mov     rax, [rsi+20h]
0x18012bc0d  mov     r9, r15; struct _UIINFO *
0x18012bc10  mov     rdi, r13
0x18012bc13  mov     rbx, [rax+88h]
0x18012bc1a  mov     rcx, [rbx+30h]
0x18012bc1e  mov     r8, [rbx+48h]; struct _INFOHEADER *
0x18012bc22  mov     rdx, [rbx+40h]; struct _RAWBINARYDATA *
0x18012bc26  mov     rcx, [rcx+28h]; this
0x18012bc2a  call    ?_SelectPrefixForFeature@PSUI@@YAPEBGPEAU_RAWBINARYDATA@@PEAU_INFOHEADER@@PEAU_UIINFO@@PEAU_FEATURE@@@Z; PSUI::_SelectPrefixForFeature(_RAWBINARYDATA *,_INFOHEADER *,_UIINFO *,_FEATURE *)
0x18012bc2f  lea     r9, [rbp+400h+var_478]; unsigned __int16 *
0x18012bc33  mov     r8, rax; char *
0x18012bc36  mov     rdx, r12; struct PSUI::_COMMONINFO *
0x18012bc39  mov     rcx, rbx; this
0x18012bc3c  call    ?ConvertParserName@PSUI@@YAJPEAU_COMMONINFO@1@PEBDPEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::ConvertParserName(PSUI::_COMMONINFO *,char const *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x18012bc41  mov     ebx, eax
0x18012bc43  mov     rax, qword ptr [rbp+400h+var_478]
0x18012bc47  mov     [rsp+500h+var_4B8], rax
0x18012bc4c  test    ebx, ebx
0x18012bc4e  js      short loc_18012BC6F
0x18012bc50  mov     r14, [rsp+500h+var_4B8]
0x18012bc55  mov     r9, r14; unsigned __int16 *
0x18012bc58  lea     rcx, [rbp+400h+var_470]; this
0x18012bc5c  mov     r8, rdi; unsigned __int16 *
0x18012bc5f  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x18012bc64  mov     ebx, eax
0x18012bc66  test    eax, eax
0x18012bc68  jz      short loc_18012BC55
0x18012bc6a  mov     r14, [rsp+500h+var_4C8]
0x18012bc6f  test    r13, r13
0x18012bc72  jz      short loc_18012BC7D
0x18012bc74  mov     rcx, r13; bstrString
0x18012bc77  call    cs:__imp_SysFreeString
0x18012bc7d  mov     rax, [rsp+500h+var_4B8]
0x18012bc82  xor     r13d, r13d
0x18012bc85  test    rax, rax
0x18012bc88  jz      short loc_18012BC93
0x18012bc8a  mov     rcx, rax; bstrString
0x18012bc8d  call    cs:__imp_SysFreeString
0x18012bc93  mov     r15d, [rsp+500h+var_4C0]
0x18012bc98  inc     r15d
  ... truncated ...
```

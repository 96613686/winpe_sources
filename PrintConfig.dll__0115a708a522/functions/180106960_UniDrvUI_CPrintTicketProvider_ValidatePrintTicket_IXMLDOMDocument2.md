# UniDrvUI::CPrintTicketProvider::ValidatePrintTicket(IXMLDOMDocument2 *)

- ea: `0x180106960`
- end: `0x1801071f9`
- name: `?ValidatePrintTicket@CPrintTicketProvider@UniDrvUI@@UEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `2201`
- prototype: `__int64 __fastcall(UniDrvUI::CPrintTicketProvider *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003400`
- `0x180004558`
- `0x1800192fc`
- `0x1800ec968`
- `0x1800ee8cc`
- `0x1800f0950`
- `0x1800f0ef0`
- `0x1800f3dc0`
- `0x1800f3ef4`
- `0x1800fa6f8`
- `0x1800fb378`
- `0x1800fdaf0`
- `0x1800fdba0`
- `0x1800ff438`
- `0x1800ff4a0`
- `0x1800ffc98`
- `0x1801009e0`
- `0x180100aac`
- `0x1801050d0`
- `0x180106960`
- `0x18010b86c`
- `0x180111d40`
- `0x18011d56c`
- `0x18011d770`
- `0x18011f550`
- `0x18014ebd0`
- `0x18014eff8`
- `0x18014f040`
- `0x180150be8`
- `0x1801b5674`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18010706f`
- `KERNEL32!FreeLibrary` at `0x18010706f`
- `KERNEL32!LocalFree` at `0x18010711a`
- `KERNEL32!LocalFree` at `0x18010711a`
- `KERNEL32!LoadLibraryExW` at `0x180107054`
- `KERNEL32!LoadLibraryExW` at `0x180107054`
- `OLEAUT32!__imp_SysAllocString` at `0x180106d11`
- `OLEAUT32!__imp_SysAllocString` at `0x180106d11`
- `OLEAUT32!__imp_SysFreeString` at `0x180106db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180106dd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180106db5`
- `OLEAUT32!__imp_SysFreeString` at `0x180106dd1`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x1801070af`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x1801070af`

## string_xrefs

- `0x18010709d`: `Windows.PrintSupportExtension`
- `0x180107047`: `Print.PrintSupport.Source.dll`
- `0x180106cdc`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180106d1d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180106e5b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180106ea0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall UniDrvUI::CPrintTicketProvider::ValidatePrintTicket(
        UniDrvUI::CPrintTicketProvider *this,
        struct IXMLDOMDocument2 *a2)
{
  OLECHAR *v2; // r13
  struct IXMLDOMDocument2 *v3; // r12
  int v6; // edi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // ecx
  __int64 v11; // rcx
  unsigned int v12; // ebx
  struct _devicemodeW *v13; // r14
  int ValidatedDevmode; // eax
  struct _devicemodeW *v15; // r9
  int v16; // eax
  struct IXMLDOMElement *v17; // rdx
  int v18; // ebx
  int v19; // r15d
  int v20; // eax
  int v21; // r15d
  int v22; // eax
  int v23; // eax
  unsigned int v24; // r15d
  __int64 v25; // rdi
  struct _UIINFO *v26; // r15
  struct PSUI::_COMMONINFO *v27; // r12
  const CHAR *v28; // rcx
  const unsigned __int16 *v29; // rdi
  __int64 v30; // rdx
  unsigned __int16 *BSTRFromANSI; // rax
  struct IXMLDOMElement *v32; // rdx
  int PrintSchema; // eax
  UniDrvUI *v34; // rcx
  const unsigned __int16 *v35; // rax
  PSUI *v36; // r11
  unsigned __int16 *v37; // r14
  struct IXMLDOMElement *v38; // rdx
  int v39; // edi
  int v40; // eax
  int v41; // edi
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // r8
  __int64 v45; // rax
  struct _OPTSELECT *v46; // r9
  unsigned __int16 **v47; // r9
  HMODULE Library; // rax
  __int64 v49; // rax
  int v50; // eax
  int v51; // eax
  bool v52; // zf
  int IsJScriptCapableDriver; // eax
  unsigned int i; // edi
  __int64 v55; // rdx
  __int64 v56; // rax
  unsigned int v57; // ecx
  __int64 v58; // rcx
  struct _devicemodeW *v59; // [rsp+20h] [rbp-E0h]
  struct _devicemodeW *v60; // [rsp+20h] [rbp-E0h]
  char v61[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v62; // [rsp+34h] [rbp-CCh]
  struct _devicemodeW *v63; // [rsp+38h] [rbp-C8h] BYREF
  int v64; // [rsp+40h] [rbp-C0h]
  unsigned int v65; // [rsp+44h] [rbp-BCh]
  BSTR v66; // [rsp+48h] [rbp-B8h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMDocument2 *v68; // [rsp+58h] [rbp-A8h]
  struct IXMLDOMElement *v69; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v70; // [rsp+68h] [rbp-98h]
  __int64 v71; // [rsp+78h] [rbp-88h]
  __int16 v72; // [rsp+80h] [rbp-80h]
  int v73; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 v74[4]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v75[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v76; // [rsp+98h] [rbp-68h]
  __int64 v77; // [rsp+A8h] [rbp-58h]
  __int16 v78; // [rsp+B0h] [rbp-50h]
  int v79; // [rsp+B4h] [rbp-4Ch]
  struct _devicemodeW v80; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v2 = 0;
  v68 = a2;
  v3 = a2;
  if ( !a2 )
    return 2147942487LL;
  v62 = 262145;
  *(_QWORD *)v75 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v76 = 0;
  v6 = 0;
  v77 = 0;
  v78 = 0;
  v7 = 0;
  v79 = 0;
  do
  {
    v8 = *((_QWORD *)this + 4);
    v9 = *(_QWORD *)(v8 + 136);
    if ( v9 )
      v10 = *(_DWORD *)(*(_QWORD *)(v9 + 80) + 8LL);
    else
      v10 = 0;
    if ( v7 >= v10 )
      break;
    v11 = *(_QWORD *)(v8 + 8LL * (int)v7 + 72);
    if ( v11 )
      v6 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *))(*(_QWORD *)v11 + 80LL))(v11, v3);
    ++v7;
  }
  while ( v6 >= 0 );
  if ( v6 >= 0 )
    v6 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)v75, v3);
  v12 = 0;
  v63 = 0;
  v65 = 0;
  LOBYTE(v80.dmDeviceName[0]) = 0;
  v13 = 0;
  memset_0((char *)v80.dmDeviceName + 1, 0, 0x3FFu);
  if ( v6 >= 0 )
  {
    ValidatedDevmode = UniDrvUI::CPrintTicketProvider::GetValidatedDevmode(this, 0, 0, (HLOCAL *)&v63);
    v13 = v63;
    v6 = ValidatedDevmode;
    if ( ValidatedDevmode >= 0 )
    {
      v12 = v63->dmSize + v63->dmDriverExtra;
      v65 = v12;
    }
  }
  v69 = (struct IXMLDOMElement *)&NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v70 = 0;
  if ( v6 >= 0 )
  {
    v6 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v69, v3);
    if ( v6 >= 0 )
    {
      if ( (*((_BYTE *)this + 56) & 1) != 0
        || (v6 = publicdm::DevmodeSnapshotFromJT(
                   (publicdm *)&v69,
                   *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 6),
                   v13->dmDeviceName,
                   v15),
            v6 >= 0) )
      {
        v16 = UniDrvUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(
                (PrintCore ***)this,
                (struct NPrintTicketUtil::CPrintTicketWrapper *)&v69,
                v12,
                v13);
        v6 = v16;
        if ( v16 == 262146 || (v62 = 262145, v16 >= 0) )
        {
          v62 = 262146 - (v16 != 262146);
          LODWORD(v59) = UniDrvUI::CPrintTicketProvider::GetPublicDMShimFlags(this);
          v6 = publicdm::JobTicketToPublicDevmode(
                 **((publicdm ***)this + 4),
                 &v69,
                 *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                 *((const unsigned __int16 **)this + 6),
                 v59->dmDeviceName,
                 v13);
          v2 = 0;
        }
      }
    }
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v69);
  v18 = 0;
  v19 = 0;
  if ( v6 < 0 )
    v18 = v6;
  if ( v18 >= 0 )
  {
    while ( off_1801D9440[2 * v19] )
    {
      do
      {
        v20 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                (struct IXMLDOMElement **)v75,
                v17,
                off_1801D9448[2 * v19],
                off_1801D9440[2 * v19]);
        v18 = v20;
      }
      while ( !v20 );
      v13 = v63;
      ++v19;
      if ( v20 < 0 )
        goto LABEL_95;
    }
    v21 = 0;
    while ( off_1801D9560[2 * v21].lpVtbl )
    {
      do
      {
        v22 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                (NPrintTicketUtil::CPrintTicketWrapper *)v75,
                off_1801D9568[2 * v21],
                (char *)off_1801D9560[2 * v21].lpVtbl);
        v18 = v22;
      }
      while ( !v22 );
      v13 = v63;
      ++v21;
      if ( v22 < 0 )
        goto LABEL_95;
    }
    do
    {
      v23 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
              (NPrintTicketUtil::CPrintTicketWrapper *)v75,
              *((const unsigned __int16 **)this + 6),
              (char *)&stru_180205968);
      v18 = v23;
    }
    while ( !v23 );
    if ( v23 >= 0 )
    {
      v24 = 0;
      v64 = 0;
      while ( 1 )
      {
        v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 72LL);
        if ( v24 >= *(_DWORD *)(v25 + 24) + *(_DWORD *)(v25 + 28)
          || (v26 = (struct _UIINFO *)(*(_QWORD *)(v25 + 328) + *(unsigned int *)(v25 + 32) + 84LL * v24)) == 0 )
        {
LABEL_72:
          v3 = v68;
          if ( v18 >= 0 )
          {
            v71 = 0;
            v69 = (struct IXMLDOMElement *)&NPrintTicketUtil::CPrintTicketWrapper::`vftable';
            v72 = 0;
            v73 = 0;
            v70 = 0;
            v18 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v69, v68);
            v39 = 0;
            if ( v18 >= 0 )
            {
              do
              {
                if ( !(&UniDrvUI::gpUnidrvSupportedFeatureNames)[v39] )
                  break;
                do
                {
                  v40 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                          &v69,
                          v38,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (unsigned __int16 *)(&UniDrvUI::gpUnidrvSupportedFeatureNames)[v39]);
                  v18 = v40;
                }
                while ( !v40 );
                ++v39;
              }
              while ( v40 >= 0 );
              v13 = v63;
            }
            v41 = 0;
            if ( v18 >= 0 )
            {
              do
              {
                if ( !(&UniDrvUI::gpUnidrvSupportedParameterNames)[v41] )
                  break;
                do
                {
                  v42 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v69,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (char *)(&UniDrvUI::gpUnidrvSupportedParameterNames)[v41]);
                  v18 = v42;
                }
                while ( !v42 );
                ++v41;
              }
              while ( v42 >= 0 );
              v3 = v68;
            }
            NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v69);
            if ( v18 >= 0 )
            {
              v43 = PGetDevmodeOptionsArray((__int64)v13);
              if ( !(unsigned int)CombineOptionArray(
                                    *(_QWORD *)(*(_QWORD *)(v44 + 48) + 40LL),
                                    (__int64)&v80,
                                    512,
                                    v43,
                                    *(_QWORD *)(v44 + 104) + 48LL) )
                goto LABEL_90;
              if ( (unsigned int)ResolveUIConflicts(
                                   *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                                   (__int64)&v80,
                                   512) )
              {
                if ( v62 != 262146 )
                  v62 = 262145;
              }
              else
              {
                v62 = 262146;
              }
              v45 = PGetDevmodeOptionsArray((__int64)v13);
              SeparateOptionArray(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                (int)&v80,
                v45,
                0x100u,
                0);
              UniDrvUI::VOptionsToDevmodeFields(
                *(UniDrvUI **)(*((_QWORD *)this + 4) + 136LL),
                (struct UniDrvUI::_COMMONINFO *)v13,
                &v80,
                0,
                1);
              if ( (unsigned int)UniDrvUI::bDocOptionArrayToJTKeywords(
                                   *(UniDrvUI **)(*((_QWORD *)this + 4) + 136LL),
                                   (struct UniDrvUI::_COMMONINFO *)v13,
                                   &v80,
                                   v46) )
              {
                if ( (*((_BYTE *)this + 56) & 1) != 0
                  || (v18 = publicdm::DevmodeSnapshotToJT(
                              (publicdm *)v13,
                              *((struct _devicemodeW **)this + 6),
                              (struct IXMLDOMElement **)v75,
                              v47),
                      v18 >= 0) )
                {
                  LODWORD(v60) = UniDrvUI::CPrintTicketProvider::GetPublicDMShimFlags(this);
                  v18 = publicdm::PublicDevmodeToJobTicket(
                          **((publicdm ***)this + 4),
                          *(void **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                          *((const unsigned __int16 **)this + 6),
                          v13->dmDeviceName,
                          v60,
                          (__int64)v75);
                  if ( v18 >= 0 )
                    v18 = UniDrvUI::CPrintTicketProvider::ConvertDevModeToPrintTicketInternal(this, v65, v13, v3);
                }
              }
              else
              {
LABEL_90:
                v18 = -2147467259;
              }
            }
          }
          goto LABEL_95;
        }
        if ( *((_DWORD *)v26 + 11) <= 1u )
        {
          v66 = 0;
          *(_QWORD *)v74 = 0;
          if ( *(_DWORD *)v26 )
            v27 = (struct PSUI::_COMMONINFO *)(*(_QWORD *)(v25 + 320) + *(unsigned int *)v26);
          else
            v27 = 0;
          if ( *((_DWORD *)v26 + 1) )
            v28 = (const CHAR *)(*(_QWORD *)(v25 + 320) + *((unsigned int *)v26 + 1));
          else
            v28 = 0;
          if ( !v27 )
          {
            v18 = -2147418113;
            goto LABEL_72;
          }
          if ( *((_DWORD *)v26 + 7) == 0xFFFF || v28 )
            break;
        }
LABEL_69:
        v24 = ++v64;
        if ( v18 < 0 )
          goto LABEL_72;
      }
      bstrString = 0;
      if ( v28 )
      {
        v29 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
        v30 = -1;
        do
          ++v30;
        while ( v28[v30] );
        BSTRFromANSI = UniDrvUI::CreateBSTRFromANSI(v28, (const char *)v30);
      }
      else
      {
        if ( strcmp_0((const char *)v27, "Stapling") )
        {
          PrintSchema = PSUI::GetPrintSchemaNamespace<_FEATURE>(
                          v25,
                          (__int64)v26,
                          *((const OLECHAR **)this + 6),
                          &bstrString);
          v2 = bstrString;
          v18 = PrintSchema;
          if ( PrintSchema < 0 )
          {
LABEL_65:
            if ( v2 )
              SysFreeString(v2);
            v2 = 0;
            if ( v66 )
              SysFreeString(v66);
            goto LABEL_69;
          }
          v29 = bstrString;
          v35 = UniDrvUI::_SelectPrefixForFeature(
                  v34,
                  *(struct _RAWBINARYDATA **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 64LL),
                  *(struct _INFOHEADER **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 72LL),
                  v26);
          v18 = PSUI::ConvertParserName(v36, v27, v35, (BSTR *)v74);
          BSTRFromANSI = *(unsigned __int16 **)v74;
          goto LABEL_60;
        }
        BSTRFromANSI = SysAllocString(L"JobStapleAllDocuments");
        v29 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
      }
      if ( !BSTRFromANSI )
      {
        v18 = -2147024882;
        goto LABEL_61;
      }
LABEL_60:
      v66 = BSTRFromANSI;
LABEL_61:
      if ( v18 >= 0 )
      {
        v37 = v66;
        do
          v18 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature((struct IXMLDOMElement **)v75, v32, v29, v37);
        while ( !v18 );
        v13 = v63;
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
    v49 = *((_QWORD *)this + 4);
    v61[0] = 0;
    v50 = IsPsaEnabledForContract(*(_QWORD *)(*(_QWORD *)(v49 + 136) + 24LL), L"Windows.PrintSupportExtension", v61);
    if ( v50 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE0B,
        (__int64)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
        (const char *)(unsigned int)v50);
    if ( v61[0] )
    {
      v51 = UniDrvUI::CPrintTicketProvider::PerformPsaValidatePrintTicket(this, v3);
      if ( v18 >= 0 )
        goto LABEL_104;
      goto LABEL_109;
    }
  }
  if ( v18 >= 0 )
  {
    IsJScriptCapableDriver = UniDrvUI::CPrintTicketProvider::IsJScriptCapableDriver(this);
    v18 = IsJScriptCapableDriver;
    if ( !IsJScriptCapableDriver )
    {
      v51 = UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(this, v3);
LABEL_104:
      v18 = v51;
LABEL_105:
      if ( v18 >= 0 )
      {
        if ( v62 == 262146 || (v52 = v18 == 262146, v18 = 262145, v52) )
          v18 = 262146;
      }
      goto LABEL_109;
    }
    if ( IsJScriptCapableDriver >= 0 )
    {
      v18 = 262145;
      for ( i = 0; ; ++i )
      {
        while ( 1 )
        {
          v55 = *((_QWORD *)this + 4);
          v56 = *(_QWORD *)(v55 + 136);
          if ( v56 )
            v57 = *(_DWORD *)(*(_QWORD *)(v56 + 80) + 8LL);
          else
            v57 = 0;
          if ( i >= v57 )
            goto LABEL_105;
          v58 = *(_QWORD *)(v55 + 8LL * (int)i + 72);
          if ( v58 )
            break;
LABEL_126:
          ++i;
        }
        v51 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *))(*(_QWORD *)v58 + 88LL))(v58, v3);
        if ( v51 < 0 )
          goto LABEL_104;
        if ( v51 != 262146 )
        {
          if ( v51 != 262145 )
          {
            v18 = -2147467259;
            goto LABEL_105;
          }
          goto LABEL_126;
        }
        v18 = 262146;
      }
    }
  }
LABEL_109:
  if ( v13 )
    LocalFree(v13);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v75);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180106960  mov     [rsp-8+arg_10], rbx
0x180106965  push    rbp
0x180106966  push    rsi
0x180106967  push    rdi
0x180106968  push    r12
0x18010696a  push    r13
0x18010696c  push    r14
0x18010696e  push    r15
0x180106970  lea     rbp, [rsp-3D0h]
0x180106978  sub     rsp, 4D0h
0x18010697f  mov     rax, cs:__security_cookie
0x180106986  xor     rax, rsp
0x180106989  mov     [rbp+400h+var_40], rax
0x180106990  xor     r13d, r13d
0x180106993  mov     [rsp+500h+var_4A8], rdx
0x180106998  mov     r12, rdx
0x18010699b  mov     rsi, rcx
0x18010699e  test    rdx, rdx
0x1801069a1  jnz     short loc_1801069AD
0x1801069a3  mov     eax, 80070057h
0x1801069a8  jmp     loc_180107131
0x1801069ad  lea     r15, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x1801069b4  mov     [rsp+500h+var_4CC], 40001h
0x1801069bc  xorps   xmm0, xmm0
0x1801069bf  mov     qword ptr [rbp+400h+var_470], r15
0x1801069c3  movdqu  [rbp+400h+var_468], xmm0
0x1801069c8  mov     edi, r13d
0x1801069cb  mov     [rbp+400h+var_458], r13
0x1801069cf  mov     [rbp+400h+var_450], r13w
0x1801069d4  mov     ebx, r13d
0x1801069d7  mov     [rbp+400h+var_44C], r13d
0x1801069db  mov     rdx, [rsi+20h]
0x1801069df  mov     rax, [rdx+88h]
0x1801069e6  test    rax, rax
0x1801069e9  jz      short loc_1801069F4
0x1801069eb  mov     rax, [rax+50h]
0x1801069ef  mov     ecx, [rax+8]
0x1801069f2  jmp     short loc_1801069F7
0x1801069f4  mov     ecx, r13d
0x1801069f7  cmp     ebx, ecx
0x1801069f9  jnb     short loc_180106A1F
0x1801069fb  movsxd  rax, ebx
0x1801069fe  mov     rcx, [rdx+rax*8+48h]
0x180106a03  test    rcx, rcx
0x180106a06  jz      short loc_180106A19
0x180106a08  mov     rax, [rcx]
0x180106a0b  mov     rdx, r12
0x180106a0e  mov     rax, [rax+50h]
0x180106a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106a17  mov     edi, eax
0x180106a19  inc     ebx
0x180106a1b  test    edi, edi
0x180106a1d  jns     short loc_1801069DB
0x180106a1f  test    edi, edi
0x180106a21  js      short loc_180106A31
0x180106a23  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180106a26  lea     rcx, [rbp+400h+var_470]; this
0x180106a2a  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180106a2f  mov     edi, eax
0x180106a31  mov     ebx, r13d
0x180106a34  mov     [rsp+500h+var_4C8], r13
0x180106a39  xor     edx, edx; Val
0x180106a3b  mov     [rsp+500h+var_4BC], ebx
0x180106a3f  mov     r8d, 3FFh; Size
0x180106a45  mov     byte ptr [rbp+400h+var_440.dmDeviceName], r13b
0x180106a49  lea     rcx, [rbp+400h+var_440.dmDeviceName+1]; void *
0x180106a4d  mov     r14, r13
0x180106a50  call    memset_0
0x180106a55  test    edi, edi
0x180106a57  js      short loc_180106A86
0x180106a59  lea     r9, [rsp+500h+var_4C8]; struct _devicemodeW **
0x180106a5e  xor     r8d, r8d; struct _devicemodeW *
0x180106a61  xor     edx, edx; unsigned int
0x180106a63  mov     rcx, rsi; this
0x180106a66  call    ?GetValidatedDevmode@CPrintTicketProvider@UniDrvUI@@IEAAJKPEAU_devicemodeW@@PEAPEAU3@@Z; UniDrvUI::CPrintTicketProvider::GetValidatedDevmode(ulong,_devicemodeW *,_devicemodeW * *)
0x180106a6b  mov     r14, [rsp+500h+var_4C8]
0x180106a70  mov     edi, eax
0x180106a72  test    eax, eax
0x180106a74  js      short loc_180106A86
0x180106a76  movzx   ebx, word ptr [r14+46h]
0x180106a7b  movzx   eax, word ptr [r14+44h]
0x180106a80  add     ebx, eax
0x180106a82  mov     [rsp+500h+var_4BC], ebx
0x180106a86  mov     [rsp+500h+var_4A0], r15
0x180106a8b  xorps   xmm0, xmm0
0x180106a8e  mov     [rsp+500h+var_488], r13
0x180106a93  mov     r15d, 40002h
0x180106a99  mov     [rbp+400h+var_480], r13w
0x180106a9e  mov     [rbp+400h+var_47C], r13d
0x180106aa2  movdqu  [rsp+500h+var_498], xmm0
0x180106aa8  test    edi, edi
0x180106aaa  js      loc_180106B52
0x180106ab0  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180106ab3  lea     rcx, [rsp+500h+var_4A0]; this
0x180106ab8  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180106abd  mov     edi, eax
0x180106abf  test    eax, eax
0x180106ac1  js      loc_180106B52
0x180106ac7  test    byte ptr [rsi+38h], 1
0x180106acb  jnz     short loc_180106AE4
0x180106acd  mov     rdx, [rsi+30h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180106ad1  lea     rcx, [rsp+500h+var_4A0]; this
0x180106ad6  mov     r8, r14; unsigned __int16 *
0x180106ad9  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x180106ade  mov     edi, eax
0x180106ae0  test    eax, eax
0x180106ae2  js      short loc_180106B52
0x180106ae4  mov     r9, r14; struct _devicemodeW *
0x180106ae7  lea     rdx, [rsp+500h+var_4A0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180106aec  mov     r8d, ebx; unsigned int
0x180106aef  mov     rcx, rsi; this
0x180106af2  call    ?ConvertPrintTicketToDevModeInternal@CPrintTicketProvider@UniDrvUI@@IEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@KPEAU_devicemodeW@@@Z; UniDrvUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(NPrintTicketUtil::CPrintTicketWrapper *,ulong,_devicemodeW *)
0x180106af7  mov     edi, eax
0x180106af9  cmp     eax, r15d
0x180106afc  jz      short loc_180106B0A
0x180106afe  mov     [rsp+500h+var_4CC], 40001h
0x180106b06  test    eax, eax
0x180106b08  js      short loc_180106B52
0x180106b0a  mov     eax, r15d
0x180106b0d  mov     rcx, rsi; this
0x180106b10  sub     eax, edi
0x180106b12  neg     eax
0x180106b14  sbb     r13d, r13d
0x180106b17  add     r13d, r15d
0x180106b1a  mov     [rsp+500h+var_4CC], r13d
0x180106b1f  call    ?GetPublicDMShimFlags@CPrintTicketProvider@UniDrvUI@@QEAAKXZ; UniDrvUI::CPrintTicketProvider::GetPublicDMShimFlags(void)
0x180106b24  mov     rcx, [rsi+20h]
0x180106b28  lea     rdx, [rsp+500h+var_4A0]; void *
0x180106b2d  mov     r9, [rsi+30h]; unsigned __int16 *
0x180106b31  mov     qword ptr [rsp+500h+var_4D8], r14; unsigned int
0x180106b36  mov     dword ptr [rsp+500h+var_4E0], eax; struct NCoreLibrary::TAutoPtrBSTR *
0x180106b3a  mov     r8, [rcx+88h]
0x180106b41  mov     rcx, [rcx]; this
0x180106b44  mov     r8, [r8+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180106b48  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x180106b4d  mov     edi, eax
0x180106b4f  xor     r13d, r13d
0x180106b52  lea     rcx, [rsp+500h+var_4A0]; this
0x180106b57  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x180106b5c  test    edi, edi
0x180106b5e  mov     ebx, r13d
0x180106b61  mov     r15d, r13d
0x180106b64  cmovs   ebx, edi
0x180106b67  test    ebx, ebx
0x180106b69  js      loc_18010703C
0x180106b6f  lea     rax, __ImageBase
0x180106b76  movsxd  rdi, r15d
0x180106b79  add     rdi, rdi
0x180106b7c  cmp     ds:rva off_1801D9440[rax+rdi*8], r13; "DocumentCollate" ...
0x180106b84  jz      short loc_180106BC4
0x180106b86  lea     r14, __ImageBase
0x180106b8d  mov     r9, ds:rva off_1801D9440[r14+rdi*8]; unsigned __int16 *
0x180106b95  lea     rcx, [rbp+400h+var_470]; this
0x180106b99  mov     r8, ds:rva off_1801D9448[r14+rdi*8]; unsigned __int16 *
0x180106ba1  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x180106ba6  mov     ebx, eax
0x180106ba8  test    eax, eax
0x180106baa  jz      short loc_180106B8D
0x180106bac  mov     r14, [rsp+500h+var_4C8]
0x180106bb1  inc     r15d
0x180106bb4  test    eax, eax
0x180106bb6  lea     rax, __ImageBase
0x180106bbd  jns     short loc_180106B76
0x180106bbf  jmp     loc_18010703C
0x180106bc4  mov     r15d, r13d
0x180106bc7  movsxd  rdi, r15d
0x180106bca  add     rdi, rdi
0x180106bcd  cmp     ds:rva off_1801D9560[rax+rdi*8], r13
0x180106bd5  jz      short loc_180106C15
0x180106bd7  lea     r14, __ImageBase
0x180106bde  mov     r8, ds:rva off_1801D9560[r14+rdi*8]; unsigned __int16 *
0x180106be6  lea     rcx, [rbp+400h+var_470]; this
0x180106bea  mov     rdx, ds:rva off_1801D9568[r14+rdi*8]; unsigned __int16 *
0x180106bf2  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x180106bf7  mov     ebx, eax
0x180106bf9  test    eax, eax
0x180106bfb  jz      short loc_180106BDE
0x180106bfd  mov     r14, [rsp+500h+var_4C8]
0x180106c02  inc     r15d
0x180106c05  test    eax, eax
0x180106c07  lea     rax, __ImageBase
0x180106c0e  jns     short loc_180106BC7
0x180106c10  jmp     loc_18010703C
0x180106c15  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180106c19  lea     r8, stru_180205968; unsigned __int16 *
0x180106c20  lea     rcx, [rbp+400h+var_470]; this
0x180106c24  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x180106c29  mov     ebx, eax
0x180106c2b  test    eax, eax
0x180106c2d  jz      short loc_180106C15
0x180106c2f  js      loc_18010703C
0x180106c35  mov     r15d, r13d
0x180106c38  mov     [rsp+500h+var_4C0], r13d
0x180106c3d  mov     rax, [rsi+20h]
0x180106c41  mov     rcx, [rax+88h]
0x180106c48  mov     rdi, [rcx+48h]
0x180106c4c  mov     eax, [rdi+1Ch]
0x180106c4f  add     eax, [rdi+18h]
0x180106c52  cmp     r15d, eax
0x180106c55  jnb     loc_180106DF9
0x180106c5b  mov     edx, [rdi+20h]
0x180106c5e  mov     eax, r15d
0x180106c61  imul    r15, rax, 54h ; 'T'
0x180106c65  add     r15, rdx
0x180106c68  add     r15, [rdi+148h]
0x180106c6f  jz      loc_180106DF9
0x180106c75  cmp     dword ptr [r15+2Ch], 1
0x180106c7a  ja      loc_180106DDD
0x180106c80  mov     rax, r13
0x180106c83  mov     [rsp+500h+var_4B8], rax
0x180106c88  mov     qword ptr [rbp+400h+var_478], rax
0x180106c8c  cmp     [r15], r13d
0x180106c8f  jz      short loc_180106C9D
0x180106c91  mov     r12d, [r15]
0x180106c94  add     r12, [rdi+140h]
0x180106c9b  jmp     short loc_180106CA0
0x180106c9d  mov     r12, r13
0x180106ca0  cmp     [r15+4], r13d
0x180106ca4  jz      short loc_180106CB3
0x180106ca6  mov     ecx, [r15+4]
0x180106caa  add     rcx, [rdi+140h]
0x180106cb1  jmp     short loc_180106CB6
0x180106cb3  mov     rcx, r13; lpMultiByteStr
0x180106cb6  test    r12, r12
0x180106cb9  jz      loc_180106DF4
0x180106cbf  cmp     dword ptr [r15+1Ch], 0FFFFh
0x180106cc7  jz      short loc_180106CD2
0x180106cc9  test    rcx, rcx
0x180106ccc  jz      loc_180106DDD
0x180106cd2  mov     [rsp+500h+bstrString], r13
0x180106cd7  test    rcx, rcx
0x180106cda  jz      short loc_180106CF7
0x180106cdc  lea     rdi, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x180106ce3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180106ce7  inc     rdx; cchWideChar
0x180106cea  cmp     byte ptr [rcx+rdx], 0
0x180106cee  jnz     short loc_180106CE7
0x180106cf0  call    ?CreateBSTRFromANSI@UniDrvUI@@YAPEAGPEBDK@Z; UniDrvUI::CreateBSTRFromANSI(char const *,ulong)
0x180106cf5  jmp     short loc_180106D24
0x180106cf7  lea     rdx, aStapling; "Stapling"
0x180106cfe  mov     rcx, r12; Str1
0x180106d01  call    strcmp_0
0x180106d06  test    eax, eax
0x180106d08  jnz     short loc_180106D30
0x180106d0a  lea     rcx, aJobstaplealldo_0; "JobStapleAllDocuments"
0x180106d11  call    cs:__imp_SysAllocString
0x180106d18  nop     dword ptr [rax+rax+00h]
0x180106d1d  lea     rdi, aHttpSchemasMic_8; "http://schemas.microsoft.com/windows/20"...
0x180106d24  test    rax, rax
0x180106d27  jnz     short loc_180106D85
0x180106d29  mov     ebx, 8007000Eh
0x180106d2e  jmp     short loc_180106D8A
0x180106d30  mov     r8, [rsi+30h]
0x180106d34  lea     r9, [rsp+500h+bstrString]
0x180106d39  mov     rdx, r15
0x180106d3c  mov     rcx, rdi
0x180106d3f  call    ??$GetPrintSchemaNamespace@U_FEATURE@@@PSUI@@YAJPEAU_UIINFO@@PEAU_FEATURE@@PEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::GetPrintSchemaNamespace<_FEATURE>(_UIINFO *,_FEATURE *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x180106d44  mov     r13, [rsp+500h+bstrString]
0x180106d49  mov     ebx, eax
0x180106d4b  test    eax, eax
0x180106d4d  js      short loc_180106DAD
0x180106d4f  mov     rax, [rsi+20h]
0x180106d53  mov     r9, r15; struct _UIINFO *
0x180106d56  mov     rdi, r13
0x180106d59  mov     r11, [rax+88h]
0x180106d60  mov     r8, [r11+48h]; struct _INFOHEADER *
0x180106d64  mov     rdx, [r11+40h]; struct _RAWBINARYDATA *
0x180106d68  call    ?_SelectPrefixForFeature@UniDrvUI@@YAPEBGPEAU_RAWBINARYDATA@@PEAU_INFOHEADER@@PEAU_UIINFO@@PEAU_FEATURE@@@Z; UniDrvUI::_SelectPrefixForFeature(_RAWBINARYDATA *,_INFOHEADER *,_UIINFO *,_FEATURE *)
0x180106d6d  mov     r8, rax; char *
0x180106d70  lea     r9, [rbp+400h+var_478]; unsigned __int16 *
0x180106d74  mov     rcx, r11; this
0x180106d77  mov     rdx, r12; struct PSUI::_COMMONINFO *
0x180106d7a  call    ?ConvertParserName@PSUI@@YAJPEAU_COMMONINFO@1@PEBDPEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::ConvertParserName(PSUI::_COMMONINFO *,char const *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x180106d7f  mov     ebx, eax
0x180106d81  mov     rax, qword ptr [rbp+400h+var_478]
0x180106d85  mov     [rsp+500h+var_4B8], rax
0x180106d8a  test    ebx, ebx
0x180106d8c  js      short loc_180106DAD
0x180106d8e  mov     r14, [rsp+500h+var_4B8]
0x180106d93  mov     r9, r14; unsigned __int16 *
0x180106d96  lea     rcx, [rbp+400h+var_470]; this
0x180106d9a  mov     r8, rdi; unsigned __int16 *
0x180106d9d  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x180106da2  mov     ebx, eax
0x180106da4  test    eax, eax
0x180106da6  jz      short loc_180106D93
0x180106da8  mov     r14, [rsp+500h+var_4C8]
0x180106dad  test    r13, r13
0x180106db0  jz      short loc_180106DC1
0x180106db2  mov     rcx, r13; bstrString
0x180106db5  call    cs:__imp_SysFreeString
0x180106dbc  nop     dword ptr [rax+rax+00h]
0x180106dc1  mov     rax, [rsp+500h+var_4B8]
0x180106dc6  xor     r13d, r13d
0x180106dc9  test    rax, rax
0x180106dcc  jz      short loc_180106DDD
0x180106dce  mov     rcx, rax; bstrString
0x180106dd1  call    cs:__imp_SysFreeString
0x180106dd8  nop     dword ptr [rax+rax+00h]
0x180106ddd  mov     r15d, [rsp+500h+var_4C0]
  ... truncated ...
```

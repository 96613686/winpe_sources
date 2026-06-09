# PSUI::CPrintTicketProvider::ValidatePrintTicket(IXMLDOMDocument2 *)

- ea: `0x180131690`
- end: `0x180131f29`
- name: `?ValidatePrintTicket@CPrintTicketProvider@PSUI@@UEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `2201`
- prototype: `__int64 __fastcall(PSUI::CPrintTicketProvider *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003400`
- `0x180004558`
- `0x1800192fc`
- `0x1800ec968`
- `0x1800ee8cc`
- `0x1800f3dc0`
- `0x1800f3ef4`
- `0x1800fdaf0`
- `0x1800fdba0`
- `0x1800ff438`
- `0x1800ff4a0`
- `0x1800ffc98`
- `0x1801009e0`
- `0x180100aac`
- `0x1801050d0`
- `0x18011d56c`
- `0x18011d770`
- `0x18012c000`
- `0x18012c5a0`
- `0x180130f98`
- `0x18013123c`
- `0x180131690`
- `0x180134660`
- `0x18013a0ac`
- `0x1801468fc`
- `0x18014ebd0`
- `0x18014eff8`
- `0x18014f040`
- `0x180150be8`
- `0x1801b5674`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180131d9f`
- `KERNEL32!FreeLibrary` at `0x180131d9f`
- `KERNEL32!LocalFree` at `0x180131e4a`
- `KERNEL32!LocalFree` at `0x180131e4a`
- `KERNEL32!LoadLibraryExW` at `0x180131d84`
- `KERNEL32!LoadLibraryExW` at `0x180131d84`
- `OLEAUT32!__imp_SysAllocString` at `0x180131a41`
- `OLEAUT32!__imp_SysAllocString` at `0x180131a41`
- `OLEAUT32!__imp_SysFreeString` at `0x180131aed`
- `OLEAUT32!__imp_SysFreeString` at `0x180131b09`
- `OLEAUT32!__imp_SysFreeString` at `0x180131aed`
- `OLEAUT32!__imp_SysFreeString` at `0x180131b09`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x180131ddf`
- `Print.PrintSupport.Source!IsPsaEnabledForContract` at `0x180131ddf`

## string_xrefs

- `0x180131dcd`: `Windows.PrintSupportExtension`
- `0x180131d77`: `Print.PrintSupport.Source.dll`
- `0x180131a0c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180131a4d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180131b93`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180131bd8`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall PSUI::CPrintTicketProvider::ValidatePrintTicket(
        PSUI::CPrintTicketProvider *this,
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
  __int64 v17; // rdx
  const char *v18; // r8
  struct IXMLDOMElement *v19; // rdx
  int v20; // ebx
  int v21; // r15d
  int v22; // eax
  int v23; // r15d
  int v24; // eax
  int v25; // eax
  unsigned int v26; // r15d
  __int64 v27; // rdi
  struct _UIINFO *v28; // r15
  struct PSUI::_COMMONINFO *v29; // r12
  const CHAR *v30; // rcx
  const unsigned __int16 *v31; // rdi
  __int64 v32; // rdx
  unsigned __int16 *BSTRFromANSI; // rax
  struct IXMLDOMElement *v34; // rdx
  int PrintSchema; // eax
  __int64 v36; // rbx
  const unsigned __int16 *v37; // rax
  unsigned __int16 *v38; // r14
  struct IXMLDOMElement *v39; // rdx
  int v40; // edi
  int v41; // eax
  int v42; // edi
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // r8
  __int64 v46; // rax
  struct _OPTSELECT *v47; // r9
  __int64 v48; // rdx
  const char *v49; // r8
  unsigned __int16 **v50; // r9
  HMODULE Library; // rax
  __int64 v52; // rax
  int v53; // eax
  int v54; // eax
  bool v55; // zf
  int IsJScriptCapableDriver; // eax
  unsigned int i; // edi
  __int64 v58; // rdx
  __int64 v59; // rax
  unsigned int v60; // ecx
  __int64 v61; // rcx
  struct _devicemodeW *v62; // [rsp+20h] [rbp-E0h]
  struct _devicemodeW *v63; // [rsp+20h] [rbp-E0h]
  _BYTE v64[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v65; // [rsp+34h] [rbp-CCh]
  struct _devicemodeW *v66; // [rsp+38h] [rbp-C8h] BYREF
  int v67; // [rsp+40h] [rbp-C0h]
  unsigned int v68; // [rsp+44h] [rbp-BCh]
  BSTR v69; // [rsp+48h] [rbp-B8h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMDocument2 *v71; // [rsp+58h] [rbp-A8h]
  struct IXMLDOMElement *v72; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v73; // [rsp+68h] [rbp-98h]
  __int64 v74; // [rsp+78h] [rbp-88h]
  __int16 v75; // [rsp+80h] [rbp-80h]
  int v76; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 v77[4]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v78[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v79; // [rsp+98h] [rbp-68h]
  __int64 v80; // [rsp+A8h] [rbp-58h]
  __int16 v81; // [rsp+B0h] [rbp-50h]
  int v82; // [rsp+B4h] [rbp-4Ch]
  struct _devicemodeW v83; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v2 = 0;
  v71 = a2;
  v3 = a2;
  if ( !a2 )
    return 2147942487LL;
  v65 = 262145;
  *(_QWORD *)v78 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v79 = 0;
  v6 = 0;
  v80 = 0;
  v81 = 0;
  v7 = 0;
  v82 = 0;
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
    v6 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)v78, v3);
  v12 = 0;
  v66 = 0;
  v68 = 0;
  LOBYTE(v83.dmDeviceName[0]) = 0;
  v13 = 0;
  memset_0((char *)v83.dmDeviceName + 1, 0, 0x3FFu);
  if ( v6 >= 0 )
  {
    ValidatedDevmode = PSUI::CPrintTicketProvider::GetValidatedDevmode(this, 0, 0, (HLOCAL *)&v66);
    v13 = v66;
    v6 = ValidatedDevmode;
    if ( ValidatedDevmode >= 0 )
    {
      v12 = v66->dmSize + v66->dmDriverExtra;
      v68 = v12;
    }
  }
  v72 = (struct IXMLDOMElement *)&NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v73 = 0;
  if ( v6 >= 0 )
  {
    v6 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v72, v3);
    if ( v6 >= 0 )
    {
      if ( (*((_BYTE *)this + 56) & 1) != 0
        || (v6 = publicdm::DevmodeSnapshotFromJT(
                   (publicdm *)&v72,
                   *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 6),
                   v13->dmDeviceName,
                   v15),
            v6 >= 0) )
      {
        v16 = PSUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(
                (PrintCore ***)this,
                (struct NPrintTicketUtil::CPrintTicketWrapper *)&v72,
                v12,
                v13);
        v6 = v16;
        if ( v16 == 262146 || (v65 = 262145, v16 >= 0) )
        {
          v65 = 262146 - (v16 != 262146);
          LODWORD(v62) = PSUI::CPrintTicketProvider::GetPublicDMShimFlags(this, v17, v18);
          v6 = publicdm::JobTicketToPublicDevmode(
                 **((publicdm ***)this + 4),
                 &v72,
                 *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                 *((const unsigned __int16 **)this + 6),
                 v62->dmDeviceName,
                 v13);
          v2 = 0;
        }
      }
    }
  }
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v72);
  v20 = 0;
  v21 = 0;
  if ( v6 < 0 )
    v20 = v6;
  if ( v20 >= 0 )
  {
    while ( off_1801D9990[2 * v21] )
    {
      do
      {
        v22 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                (struct IXMLDOMElement **)v78,
                v19,
                off_1801D9998[2 * v21],
                off_1801D9990[2 * v21]);
        v20 = v22;
      }
      while ( !v22 );
      v13 = v66;
      ++v21;
      if ( v22 < 0 )
        goto LABEL_95;
    }
    v23 = 0;
    while ( off_1801D9AB0[2 * v23] )
    {
      do
      {
        v24 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                (NPrintTicketUtil::CPrintTicketWrapper *)v78,
                off_1801D9AB8[2 * v23],
                (char *)off_1801D9AB0[2 * v23]);
        v20 = v24;
      }
      while ( !v24 );
      v13 = v66;
      ++v23;
      if ( v24 < 0 )
        goto LABEL_95;
    }
    do
    {
      v25 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
              (NPrintTicketUtil::CPrintTicketWrapper *)v78,
              *((const unsigned __int16 **)this + 6),
              (char *)L"PageDevmodeSnapshot");
      v20 = v25;
    }
    while ( !v25 );
    if ( v25 >= 0 )
    {
      v26 = 0;
      v67 = 0;
      while ( 1 )
      {
        v27 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 72LL);
        if ( v26 >= *(_DWORD *)(v27 + 24) + *(_DWORD *)(v27 + 28)
          || (v28 = (struct _UIINFO *)(*(_QWORD *)(v27 + 328) + *(unsigned int *)(v27 + 32) + 84LL * v26)) == 0 )
        {
LABEL_72:
          v3 = v71;
          if ( v20 >= 0 )
          {
            v74 = 0;
            v72 = (struct IXMLDOMElement *)&NPrintTicketUtil::CPrintTicketWrapper::`vftable';
            v75 = 0;
            v76 = 0;
            v73 = 0;
            v20 = NPrintTicketUtil::CPrintTicketWrapper::SetDocument((NPrintTicketUtil::CPrintTicketWrapper *)&v72, v71);
            v40 = 0;
            if ( v20 >= 0 )
            {
              do
              {
                if ( !(&PSUI::gpPScriptSupportedFeatureNames)[v40] )
                  break;
                do
                {
                  v41 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(
                          &v72,
                          v39,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (unsigned __int16 *)(&PSUI::gpPScriptSupportedFeatureNames)[v40]);
                  v20 = v41;
                }
                while ( !v41 );
                ++v40;
              }
              while ( v41 >= 0 );
              v13 = v66;
            }
            v42 = 0;
            if ( v20 >= 0 )
            {
              do
              {
                if ( !(&PSUI::gpPScriptSupportedParameterNames)[v42] )
                  break;
                do
                {
                  v43 = NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v72,
                          L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                          (char *)(&PSUI::gpPScriptSupportedParameterNames)[v42]);
                  v20 = v43;
                }
                while ( !v43 );
                ++v42;
              }
              while ( v43 >= 0 );
              v3 = v71;
            }
            NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)&v72);
            if ( v20 >= 0 )
            {
              v44 = PGetDevmodeOptionsArray((__int64)v13);
              if ( !(unsigned int)CombineOptionArray(
                                    *(_QWORD *)(*(_QWORD *)(v45 + 48) + 40LL),
                                    (__int64)&v83,
                                    512,
                                    v44,
                                    *(_QWORD *)(v45 + 104) + 48LL) )
                goto LABEL_90;
              if ( (unsigned int)ResolveUIConflicts(
                                   *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                                   (__int64)&v83,
                                   512) )
              {
                if ( v65 != 262146 )
                  v65 = 262145;
              }
              else
              {
                v65 = 262146;
              }
              v46 = PGetDevmodeOptionsArray((__int64)v13);
              SeparateOptionArray(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 48LL) + 40LL),
                (int)&v83,
                v46,
                0x100u,
                0);
              PSUI::VOptionsToDevmodeFields(
                *(PSUI **)(*((_QWORD *)this + 4) + 136LL),
                (struct PSUI::_COMMONINFO *)v13,
                &v83,
                0);
              if ( (unsigned int)PSUI::bDocOptionArrayToJTKeywords(
                                   *(PSUI **)(*((_QWORD *)this + 4) + 136LL),
                                   (struct PSUI::_COMMONINFO *)v13,
                                   &v83,
                                   v47) )
              {
                if ( (*((_BYTE *)this + 56) & 1) != 0
                  || (v20 = publicdm::DevmodeSnapshotToJT(
                              (publicdm *)v13,
                              *((struct _devicemodeW **)this + 6),
                              (struct IXMLDOMElement **)v78,
                              v50),
                      v20 >= 0) )
                {
                  LODWORD(v63) = PSUI::CPrintTicketProvider::GetPublicDMShimFlags(this, v48, v49);
                  v20 = publicdm::PublicDevmodeToJobTicket(
                          **((publicdm ***)this + 4),
                          *(void **)(*(_QWORD *)(*((_QWORD *)this + 4) + 136LL) + 24LL),
                          *((const unsigned __int16 **)this + 6),
                          v13->dmDeviceName,
                          v63,
                          (__int64)v78);
                  if ( v20 >= 0 )
                    v20 = PSUI::CPrintTicketProvider::ConvertDevModeToPrintTicketInternal(this, v68, v13, v3);
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
        if ( *((_DWORD *)v28 + 11) <= 1u )
        {
          v69 = 0;
          *(_QWORD *)v77 = 0;
          if ( *(_DWORD *)v28 )
            v29 = (struct PSUI::_COMMONINFO *)(*(_QWORD *)(v27 + 320) + *(unsigned int *)v28);
          else
            v29 = 0;
          if ( *((_DWORD *)v28 + 1) )
            v30 = (const CHAR *)(*(_QWORD *)(v27 + 320) + *((unsigned int *)v28 + 1));
          else
            v30 = 0;
          if ( !v29 )
          {
            v20 = -2147418113;
            goto LABEL_72;
          }
          if ( *((_DWORD *)v28 + 7) == 0xFFFF || v30 )
            break;
        }
LABEL_69:
        v26 = ++v67;
        if ( v20 < 0 )
          goto LABEL_72;
      }
      bstrString = 0;
      if ( v30 )
      {
        v31 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
        v32 = -1;
        do
          ++v32;
        while ( v30[v32] );
        BSTRFromANSI = UniDrvUI::CreateBSTRFromANSI(v30, (const char *)v32);
      }
      else
      {
        if ( strcmp_0((const char *)v29, "Stapling") )
        {
          PrintSchema = PSUI::GetPrintSchemaNamespace<_FEATURE>(
                          v27,
                          (__int64)v28,
                          *((const OLECHAR **)this + 6),
                          &bstrString);
          v2 = bstrString;
          v20 = PrintSchema;
          if ( PrintSchema < 0 )
          {
LABEL_65:
            if ( v2 )
              SysFreeString(v2);
            v2 = 0;
            if ( v69 )
              SysFreeString(v69);
            goto LABEL_69;
          }
          v31 = bstrString;
          v36 = *(_QWORD *)(*((_QWORD *)this + 4) + 136LL);
          v37 = PSUI::_SelectPrefixForFeature(
                  *(PSUI **)(*(_QWORD *)(v36 + 48) + 40LL),
                  *(struct _RAWBINARYDATA **)(v36 + 64),
                  *(struct _INFOHEADER **)(v36 + 72),
                  v28);
          v20 = PSUI::ConvertParserName((PSUI *)v36, v29, v37, (BSTR *)v77);
          BSTRFromANSI = *(unsigned __int16 **)v77;
          goto LABEL_60;
        }
        BSTRFromANSI = SysAllocString(L"JobStapleAllDocuments");
        v31 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
      }
      if ( !BSTRFromANSI )
      {
        v20 = -2147024882;
        goto LABEL_61;
      }
LABEL_60:
      v69 = BSTRFromANSI;
LABEL_61:
      if ( v20 >= 0 )
      {
        v38 = v69;
        do
          v20 = NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature((struct IXMLDOMElement **)v78, v34, v31, v38);
        while ( !v20 );
        v13 = v66;
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
    v52 = *((_QWORD *)this + 4);
    v64[0] = 0;
    v53 = IsPsaEnabledForContract(*(_QWORD *)(*(_QWORD *)(v52 + 136) + 24LL), L"Windows.PrintSupportExtension", v64);
    if ( v53 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE0B,
        (__int64)"printscan\\print\\drivers\\usermode\\driverui\\ptprovider.cxx",
        (const char *)(unsigned int)v53);
    if ( v64[0] )
    {
      v54 = UniDrvUI::CPrintTicketProvider::PerformPsaValidatePrintTicket(this, v3);
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
      v54 = UniDrvUI::CPrintTicketProvider::PerformJScriptValidatePrintTicket(this, v3);
LABEL_104:
      v20 = v54;
LABEL_105:
      if ( v20 >= 0 )
      {
        if ( v65 == 262146 || (v55 = v20 == 262146, v20 = 262145, v55) )
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
          v58 = *((_QWORD *)this + 4);
          v59 = *(_QWORD *)(v58 + 136);
          if ( v59 )
            v60 = *(_DWORD *)(*(_QWORD *)(v59 + 80) + 8LL);
          else
            v60 = 0;
          if ( i >= v60 )
            goto LABEL_105;
          v61 = *(_QWORD *)(v58 + 8LL * (int)i + 72);
          if ( v61 )
            break;
LABEL_126:
          ++i;
        }
        v54 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMDocument2 *))(*(_QWORD *)v61 + 88LL))(v61, v3);
        if ( v54 < 0 )
          goto LABEL_104;
        if ( v54 != 262146 )
        {
          if ( v54 != 262145 )
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
  if ( v13 )
    LocalFree(v13);
  NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper((NPrintTicketUtil::CPrintTicketWrapper *)v78);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180131690  mov     [rsp-8+arg_10], rbx
0x180131695  push    rbp
0x180131696  push    rsi
0x180131697  push    rdi
0x180131698  push    r12
0x18013169a  push    r13
0x18013169c  push    r14
0x18013169e  push    r15
0x1801316a0  lea     rbp, [rsp-3D0h]
0x1801316a8  sub     rsp, 4D0h
0x1801316af  mov     rax, cs:__security_cookie
0x1801316b6  xor     rax, rsp
0x1801316b9  mov     [rbp+400h+var_40], rax
0x1801316c0  xor     r13d, r13d
0x1801316c3  mov     [rsp+500h+var_4A8], rdx
0x1801316c8  mov     r12, rdx
0x1801316cb  mov     rsi, rcx
0x1801316ce  test    rdx, rdx
0x1801316d1  jnz     short loc_1801316DD
0x1801316d3  mov     eax, 80070057h
0x1801316d8  jmp     loc_180131E61
0x1801316dd  lea     r15, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x1801316e4  mov     [rsp+500h+var_4CC], 40001h
0x1801316ec  xorps   xmm0, xmm0
0x1801316ef  mov     qword ptr [rbp+400h+var_470], r15
0x1801316f3  movdqu  [rbp+400h+var_468], xmm0
0x1801316f8  mov     edi, r13d
0x1801316fb  mov     [rbp+400h+var_458], r13
0x1801316ff  mov     [rbp+400h+var_450], r13w
0x180131704  mov     ebx, r13d
0x180131707  mov     [rbp+400h+var_44C], r13d
0x18013170b  mov     rdx, [rsi+20h]
0x18013170f  mov     rax, [rdx+88h]
0x180131716  test    rax, rax
0x180131719  jz      short loc_180131724
0x18013171b  mov     rax, [rax+50h]
0x18013171f  mov     ecx, [rax+8]
0x180131722  jmp     short loc_180131727
0x180131724  mov     ecx, r13d
0x180131727  cmp     ebx, ecx
0x180131729  jnb     short loc_18013174F
0x18013172b  movsxd  rax, ebx
0x18013172e  mov     rcx, [rdx+rax*8+48h]
0x180131733  test    rcx, rcx
0x180131736  jz      short loc_180131749
0x180131738  mov     rax, [rcx]
0x18013173b  mov     rdx, r12
0x18013173e  mov     rax, [rax+50h]
0x180131742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131747  mov     edi, eax
0x180131749  inc     ebx
0x18013174b  test    edi, edi
0x18013174d  jns     short loc_18013170B
0x18013174f  test    edi, edi
0x180131751  js      short loc_180131761
0x180131753  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180131756  lea     rcx, [rbp+400h+var_470]; this
0x18013175a  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x18013175f  mov     edi, eax
0x180131761  mov     ebx, r13d
0x180131764  mov     [rsp+500h+var_4C8], r13
0x180131769  xor     edx, edx; Val
0x18013176b  mov     [rsp+500h+var_4BC], ebx
0x18013176f  mov     r8d, 3FFh; Size
0x180131775  mov     byte ptr [rbp+400h+var_440.dmDeviceName], r13b
0x180131779  lea     rcx, [rbp+400h+var_440.dmDeviceName+1]; void *
0x18013177d  mov     r14, r13
0x180131780  call    memset_0
0x180131785  test    edi, edi
0x180131787  js      short loc_1801317B6
0x180131789  lea     r9, [rsp+500h+var_4C8]; struct _devicemodeW **
0x18013178e  xor     r8d, r8d; struct _devicemodeW *
0x180131791  xor     edx, edx; unsigned int
0x180131793  mov     rcx, rsi; this
0x180131796  call    ?GetValidatedDevmode@CPrintTicketProvider@PSUI@@IEAAJKPEAU_devicemodeW@@PEAPEAU3@@Z; PSUI::CPrintTicketProvider::GetValidatedDevmode(ulong,_devicemodeW *,_devicemodeW * *)
0x18013179b  mov     r14, [rsp+500h+var_4C8]
0x1801317a0  mov     edi, eax
0x1801317a2  test    eax, eax
0x1801317a4  js      short loc_1801317B6
0x1801317a6  movzx   ebx, word ptr [r14+46h]
0x1801317ab  movzx   eax, word ptr [r14+44h]
0x1801317b0  add     ebx, eax
0x1801317b2  mov     [rsp+500h+var_4BC], ebx
0x1801317b6  mov     [rsp+500h+var_4A0], r15
0x1801317bb  xorps   xmm0, xmm0
0x1801317be  mov     [rsp+500h+var_488], r13
0x1801317c3  mov     r15d, 40002h
0x1801317c9  mov     [rbp+400h+var_480], r13w
0x1801317ce  mov     [rbp+400h+var_47C], r13d
0x1801317d2  movdqu  [rsp+500h+var_498], xmm0
0x1801317d8  test    edi, edi
0x1801317da  js      loc_180131882
0x1801317e0  mov     rdx, r12; struct IXMLDOMDocument2 *
0x1801317e3  lea     rcx, [rsp+500h+var_4A0]; this
0x1801317e8  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x1801317ed  mov     edi, eax
0x1801317ef  test    eax, eax
0x1801317f1  js      loc_180131882
0x1801317f7  test    byte ptr [rsi+38h], 1
0x1801317fb  jnz     short loc_180131814
0x1801317fd  mov     rdx, [rsi+30h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180131801  lea     rcx, [rsp+500h+var_4A0]; this
0x180131806  mov     r8, r14; unsigned __int16 *
0x180131809  call    ?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z; publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)
0x18013180e  mov     edi, eax
0x180131810  test    eax, eax
0x180131812  js      short loc_180131882
0x180131814  mov     r9, r14; struct _devicemodeW *
0x180131817  lea     rdx, [rsp+500h+var_4A0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18013181c  mov     r8d, ebx; unsigned int
0x18013181f  mov     rcx, rsi; this
0x180131822  call    ?ConvertPrintTicketToDevModeInternal@CPrintTicketProvider@PSUI@@IEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@KPEAU_devicemodeW@@@Z; PSUI::CPrintTicketProvider::ConvertPrintTicketToDevModeInternal(NPrintTicketUtil::CPrintTicketWrapper *,ulong,_devicemodeW *)
0x180131827  mov     edi, eax
0x180131829  cmp     eax, r15d
0x18013182c  jz      short loc_18013183A
0x18013182e  mov     [rsp+500h+var_4CC], 40001h
0x180131836  test    eax, eax
0x180131838  js      short loc_180131882
0x18013183a  mov     eax, r15d
0x18013183d  mov     rcx, rsi; this
0x180131840  sub     eax, edi
0x180131842  neg     eax
0x180131844  sbb     r13d, r13d
0x180131847  add     r13d, r15d
0x18013184a  mov     [rsp+500h+var_4CC], r13d
0x18013184f  call    ?GetPublicDMShimFlags@CPrintTicketProvider@PSUI@@QEAAKXZ; PSUI::CPrintTicketProvider::GetPublicDMShimFlags(void)
0x180131854  mov     rcx, [rsi+20h]
0x180131858  lea     rdx, [rsp+500h+var_4A0]; void *
0x18013185d  mov     r9, [rsi+30h]; unsigned __int16 *
0x180131861  mov     qword ptr [rsp+500h+var_4D8], r14; unsigned int
0x180131866  mov     dword ptr [rsp+500h+var_4E0], eax; struct NCoreLibrary::TAutoPtrBSTR *
0x18013186a  mov     r8, [rcx+88h]
0x180131871  mov     rcx, [rcx]; this
0x180131874  mov     r8, [r8+18h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180131878  call    ?JobTicketToPublicDevmode@publicdm@@YAJPEAXPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG2KPEAU_devicemodeW@@@Z; publicdm::JobTicketToPublicDevmode(void *,NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,ulong,_devicemodeW *)
0x18013187d  mov     edi, eax
0x18013187f  xor     r13d, r13d
0x180131882  lea     rcx, [rsp+500h+var_4A0]; this
0x180131887  call    ??1CPrintTicketWrapper@NPrintTicketUtil@@UEAA@XZ; NPrintTicketUtil::CPrintTicketWrapper::~CPrintTicketWrapper(void)
0x18013188c  test    edi, edi
0x18013188e  mov     ebx, r13d
0x180131891  mov     r15d, r13d
0x180131894  cmovs   ebx, edi
0x180131897  test    ebx, ebx
0x180131899  js      loc_180131D6C
0x18013189f  lea     rax, __ImageBase
0x1801318a6  movsxd  rdi, r15d
0x1801318a9  add     rdi, rdi
0x1801318ac  cmp     ds:rva off_1801D9990[rax+rdi*8], r13; "DocumentCollate" ...
0x1801318b4  jz      short loc_1801318F4
0x1801318b6  lea     r14, __ImageBase
0x1801318bd  mov     r9, ds:rva off_1801D9990[r14+rdi*8]; unsigned __int16 *
0x1801318c5  lea     rcx, [rbp+400h+var_470]; this
0x1801318c9  mov     r8, ds:rva off_1801D9998[r14+rdi*8]; unsigned __int16 *
0x1801318d1  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x1801318d6  mov     ebx, eax
0x1801318d8  test    eax, eax
0x1801318da  jz      short loc_1801318BD
0x1801318dc  mov     r14, [rsp+500h+var_4C8]
0x1801318e1  inc     r15d
0x1801318e4  test    eax, eax
0x1801318e6  lea     rax, __ImageBase
0x1801318ed  jns     short loc_1801318A6
0x1801318ef  jmp     loc_180131D6C
0x1801318f4  mov     r15d, r13d
0x1801318f7  movsxd  rdi, r15d
0x1801318fa  add     rdi, rdi
0x1801318fd  cmp     ds:rva off_1801D9AB0[rax+rdi*8], r13; "JobCopiesAllDocuments" ...
0x180131905  jz      short loc_180131945
0x180131907  lea     r14, __ImageBase
0x18013190e  mov     r8, ds:rva off_1801D9AB0[r14+rdi*8]; unsigned __int16 *
0x180131916  lea     rcx, [rbp+400h+var_470]; this
0x18013191a  mov     rdx, ds:rva off_1801D9AB8[r14+rdi*8]; unsigned __int16 *
0x180131922  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x180131927  mov     ebx, eax
0x180131929  test    eax, eax
0x18013192b  jz      short loc_18013190E
0x18013192d  mov     r14, [rsp+500h+var_4C8]
0x180131932  inc     r15d
0x180131935  test    eax, eax
0x180131937  lea     rax, __ImageBase
0x18013193e  jns     short loc_1801318F7
0x180131940  jmp     loc_180131D6C
0x180131945  mov     rdx, [rsi+30h]; unsigned __int16 *
0x180131949  lea     r8, aPagedevmodesna_1; "PageDevmodeSnapshot"
0x180131950  lea     rcx, [rbp+400h+var_470]; this
0x180131954  call    ?RemoveParameter@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveParameter(ushort const *,ushort const *)
0x180131959  mov     ebx, eax
0x18013195b  test    eax, eax
0x18013195d  jz      short loc_180131945
0x18013195f  js      loc_180131D6C
0x180131965  mov     r15d, r13d
0x180131968  mov     [rsp+500h+var_4C0], r13d
0x18013196d  mov     rax, [rsi+20h]
0x180131971  mov     rcx, [rax+88h]
0x180131978  mov     rdi, [rcx+48h]
0x18013197c  mov     eax, [rdi+1Ch]
0x18013197f  add     eax, [rdi+18h]
0x180131982  cmp     r15d, eax
0x180131985  jnb     loc_180131B31
0x18013198b  mov     edx, [rdi+20h]
0x18013198e  mov     eax, r15d
0x180131991  imul    r15, rax, 54h ; 'T'
0x180131995  add     r15, rdx
0x180131998  add     r15, [rdi+148h]
0x18013199f  jz      loc_180131B31
0x1801319a5  cmp     dword ptr [r15+2Ch], 1
0x1801319aa  ja      loc_180131B15
0x1801319b0  mov     rax, r13
0x1801319b3  mov     [rsp+500h+var_4B8], rax
0x1801319b8  mov     qword ptr [rbp+400h+var_478], rax
0x1801319bc  cmp     [r15], r13d
0x1801319bf  jz      short loc_1801319CD
0x1801319c1  mov     r12d, [r15]
0x1801319c4  add     r12, [rdi+140h]
0x1801319cb  jmp     short loc_1801319D0
0x1801319cd  mov     r12, r13
0x1801319d0  cmp     [r15+4], r13d
0x1801319d4  jz      short loc_1801319E3
0x1801319d6  mov     ecx, [r15+4]
0x1801319da  add     rcx, [rdi+140h]
0x1801319e1  jmp     short loc_1801319E6
0x1801319e3  mov     rcx, r13; lpMultiByteStr
0x1801319e6  test    r12, r12
0x1801319e9  jz      loc_180131B2C
0x1801319ef  cmp     dword ptr [r15+1Ch], 0FFFFh
0x1801319f7  jz      short loc_180131A02
0x1801319f9  test    rcx, rcx
0x1801319fc  jz      loc_180131B15
0x180131a02  mov     [rsp+500h+bstrString], r13
0x180131a07  test    rcx, rcx
0x180131a0a  jz      short loc_180131A27
0x180131a0c  lea     rdi, aHttpSchemasMic_18; "http://schemas.microsoft.com/windows/20"...
0x180131a13  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180131a17  inc     rdx; cchWideChar
0x180131a1a  cmp     byte ptr [rcx+rdx], 0
0x180131a1e  jnz     short loc_180131A17
0x180131a20  call    ?CreateBSTRFromANSI@UniDrvUI@@YAPEAGPEBDK@Z; UniDrvUI::CreateBSTRFromANSI(char const *,ulong)
0x180131a25  jmp     short loc_180131A54
0x180131a27  lea     rdx, aStapling; "Stapling"
0x180131a2e  mov     rcx, r12; Str1
0x180131a31  call    strcmp_0
0x180131a36  test    eax, eax
0x180131a38  jnz     short loc_180131A60
0x180131a3a  lea     rcx, aJobstaplealldo_2; "JobStapleAllDocuments"
0x180131a41  call    cs:__imp_SysAllocString
0x180131a48  nop     dword ptr [rax+rax+00h]
0x180131a4d  lea     rdi, aHttpSchemasMic_18; "http://schemas.microsoft.com/windows/20"...
0x180131a54  test    rax, rax
0x180131a57  jnz     short loc_180131ABD
0x180131a59  mov     ebx, 8007000Eh
0x180131a5e  jmp     short loc_180131AC2
0x180131a60  mov     r8, [rsi+30h]
0x180131a64  lea     r9, [rsp+500h+bstrString]
0x180131a69  mov     rdx, r15
0x180131a6c  mov     rcx, rdi
0x180131a6f  call    ??$GetPrintSchemaNamespace@U_FEATURE@@@PSUI@@YAJPEAU_UIINFO@@PEAU_FEATURE@@PEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::GetPrintSchemaNamespace<_FEATURE>(_UIINFO *,_FEATURE *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x180131a74  mov     r13, [rsp+500h+bstrString]
0x180131a79  mov     ebx, eax
0x180131a7b  test    eax, eax
0x180131a7d  js      short loc_180131AE5
0x180131a7f  mov     rax, [rsi+20h]
0x180131a83  mov     r9, r15; struct _UIINFO *
0x180131a86  mov     rdi, r13
0x180131a89  mov     rbx, [rax+88h]
0x180131a90  mov     rcx, [rbx+30h]
0x180131a94  mov     r8, [rbx+48h]; struct _INFOHEADER *
0x180131a98  mov     rdx, [rbx+40h]; struct _RAWBINARYDATA *
0x180131a9c  mov     rcx, [rcx+28h]; this
0x180131aa0  call    ?_SelectPrefixForFeature@PSUI@@YAPEBGPEAU_RAWBINARYDATA@@PEAU_INFOHEADER@@PEAU_UIINFO@@PEAU_FEATURE@@@Z; PSUI::_SelectPrefixForFeature(_RAWBINARYDATA *,_INFOHEADER *,_UIINFO *,_FEATURE *)
0x180131aa5  lea     r9, [rbp+400h+var_478]; unsigned __int16 *
0x180131aa9  mov     r8, rax; char *
0x180131aac  mov     rdx, r12; struct PSUI::_COMMONINFO *
0x180131aaf  mov     rcx, rbx; this
0x180131ab2  call    ?ConvertParserName@PSUI@@YAJPEAU_COMMONINFO@1@PEBDPEBGAEAVTAutoPtrBSTR@NCoreLibrary@@@Z; PSUI::ConvertParserName(PSUI::_COMMONINFO *,char const *,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x180131ab7  mov     ebx, eax
0x180131ab9  mov     rax, qword ptr [rbp+400h+var_478]
0x180131abd  mov     [rsp+500h+var_4B8], rax
0x180131ac2  test    ebx, ebx
0x180131ac4  js      short loc_180131AE5
0x180131ac6  mov     r14, [rsp+500h+var_4B8]
0x180131acb  mov     r9, r14; unsigned __int16 *
0x180131ace  lea     rcx, [rbp+400h+var_470]; this
0x180131ad2  mov     r8, rdi; unsigned __int16 *
0x180131ad5  call    ?RemoveFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::RemoveFeature(IXMLDOMElement *,ushort const *,ushort const *)
0x180131ada  mov     ebx, eax
0x180131adc  test    eax, eax
0x180131ade  jz      short loc_180131ACB
0x180131ae0  mov     r14, [rsp+500h+var_4C8]
0x180131ae5  test    r13, r13
0x180131ae8  jz      short loc_180131AF9
0x180131aea  mov     rcx, r13; bstrString
0x180131aed  call    cs:__imp_SysFreeString
0x180131af4  nop     dword ptr [rax+rax+00h]
0x180131af9  mov     rax, [rsp+500h+var_4B8]
0x180131afe  xor     r13d, r13d
0x180131b01  test    rax, rax
0x180131b04  jz      short loc_180131B15
0x180131b06  mov     rcx, rax; bstrString
0x180131b09  call    cs:__imp_SysFreeString
  ... truncated ...
```

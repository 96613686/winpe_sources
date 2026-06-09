# CWMIBroker::VerifyBaseClasses(IWbemServices *)

- ea: `0x1400037f0`
- end: `0x14000461a`
- name: `?VerifyBaseClasses@CWMIBroker@@EEAAJPEAUIWbemServices@@@Z`
- size: `3626`
- prototype: `__int64 __fastcall(CWMIBroker *this, struct IWbemServices *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001a6f`
- `0x140002b5c`
- `0x140002de4`
- `0x140002e14`
- `0x140002e44`
- `0x140002ee4`
- `0x140002f04`
- `0x140002f30`
- `0x140002f54`
- `0x1400030f8`
- `0x1400034cc`
- `0x140003698`
- `0x1400037f0`
- `0x140004620`
- `0x140004bc0`
- `0x140004c04`
- `0x140014ad0`
- `0x140017010`

## import_xrefs

- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x140003d33`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x1400040a0`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x14000447f`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x140003d33`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x1400040a0`
- `wbemcomn!??0CInsertionString@@QEAA@VCHex@@@Z` at `0x14000447f`
- `wbemcomn!GetMemLogObject` at `0x140003971`
- `wbemcomn!GetMemLogObject` at `0x140003dad`
- `wbemcomn!GetMemLogObject` at `0x14000411a`
- `wbemcomn!GetMemLogObject` at `0x1400044f9`
- `wbemcomn!GetMemLogObject` at `0x140003971`
- `wbemcomn!GetMemLogObject` at `0x140003dad`
- `wbemcomn!GetMemLogObject` at `0x14000411a`
- `wbemcomn!GetMemLogObject` at `0x1400044f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000397d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140003db9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140004126`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140004505`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000397d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140003db9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140004126`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140004505`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x14000426c`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x14000426c`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140004290`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140004290`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003a4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003b71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003eea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003a4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003b71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003eea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003a64`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003b8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003f06`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003a64`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003b8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003f06`
- `OLEAUT32!__imp_SysAllocString` at `0x140003869`
- `OLEAUT32!__imp_SysAllocString` at `0x140003869`
- `OLEAUT32!__imp_VariantInit` at `0x14000385b`
- `OLEAUT32!__imp_VariantInit` at `0x140003aec`
- `OLEAUT32!__imp_VariantInit` at `0x14000385b`
- `OLEAUT32!__imp_VariantInit` at `0x140003aec`

## pseudocode

```c
__int64 __fastcall CWMIBroker::VerifyBaseClasses(CWMIBroker *this, struct IWbemServices *a2)
{
  CWMIBroker *v3; // r15
  BOOL v4; // r14d
  OLECHAR *v5; // rax
  int v7; // ebx
  struct IWbemServices *v8; // rsi
  CInsertionString *v9; // r15
  CMemoryLog *MemLogObject; // rax
  int v11; // r8d
  int v12; // ebx
  HMODULE ModuleHandleW; // rax
  CWMIBroker *v14; // rcx
  CWMIBroker *v15; // rcx
  int v16; // ebx
  HMODULE v17; // rax
  CWMIBroker *v18; // rcx
  struct CInsertionString *v19; // r13
  struct CInsertionString *v20; // r12
  struct CInsertionString *v21; // r15
  struct CInsertionString *v22; // r14
  struct CInsertionString *v23; // rsi
  struct CInsertionString *v24; // rdi
  const struct CInsertionString *v25; // rbx
  const struct CInsertionString *v26; // rax
  CMemoryLog *v27; // rax
  __int64 v28; // r8
  unsigned int v29; // ebx
  int v30; // ebx
  HMODULE v31; // rax
  CWMIBroker *v32; // rcx
  struct CInsertionString *v33; // r13
  struct CInsertionString *v34; // r12
  struct CInsertionString *v35; // r15
  struct CInsertionString *v36; // r14
  struct CInsertionString *v37; // rsi
  struct CInsertionString *v38; // rdi
  const struct CInsertionString *v39; // rbx
  const struct CInsertionString *v40; // rax
  CMemoryLog *v41; // rax
  __int64 v42; // r8
  int v43; // edi
  struct IWbemServices *v44; // rbx
  struct CInsertionString *v45; // r13
  struct CInsertionString *v46; // r12
  struct CInsertionString *v47; // r15
  struct CInsertionString *v48; // r14
  struct CInsertionString *v49; // rsi
  struct CInsertionString *v50; // rdi
  const struct CInsertionString *v51; // rbx
  const struct CInsertionString *v52; // rax
  CMemoryLog *v53; // rax
  __int64 v54; // r8
  int v55; // [rsp+60h] [rbp-2F8h]
  unsigned int v56; // [rsp+60h] [rbp-2F8h]
  unsigned int v57; // [rsp+60h] [rbp-2F8h]
  unsigned int v58; // [rsp+60h] [rbp-2F8h]
  struct IWbemClassObject *v59; // [rsp+68h] [rbp-2F0h] BYREF
  CInsertionString *v60; // [rsp+70h] [rbp-2E8h] BYREF
  struct IWbemClassObject *v61; // [rsp+78h] [rbp-2E0h] BYREF
  CWMIBroker *v62; // [rsp+80h] [rbp-2D8h] BYREF
  int v63[2]; // [rsp+88h] [rbp-2D0h] BYREF
  struct IWbemClassObject *v64; // [rsp+90h] [rbp-2C8h] BYREF
  struct IWbemServices *v65; // [rsp+98h] [rbp-2C0h] BYREF
  struct CInsertionString *v66; // [rsp+A0h] [rbp-2B8h]
  struct IWbemServices *v67; // [rsp+A8h] [rbp-2B0h] BYREF
  struct IWbemServices *v68; // [rsp+B0h] [rbp-2A8h]
  OLECHAR *v69; // [rsp+B8h] [rbp-2A0h] BYREF
  struct CInsertionString *v70; // [rsp+C0h] [rbp-298h]
  unsigned __int16 *v71[2]; // [rsp+C8h] [rbp-290h] BYREF
  _BYTE *v72; // [rsp+D8h] [rbp-280h]
  _BYTE *v73; // [rsp+E0h] [rbp-278h]
  _BYTE *v74; // [rsp+E8h] [rbp-270h]
  _BYTE *v75; // [rsp+F0h] [rbp-268h]
  _BYTE *v76; // [rsp+F8h] [rbp-260h]
  _BYTE *v77; // [rsp+100h] [rbp-258h]
  _BYTE *v78; // [rsp+108h] [rbp-250h]
  _BYTE *v79; // [rsp+110h] [rbp-248h]
  _BYTE v80[16]; // [rsp+118h] [rbp-240h] BYREF
  _BYTE v81[16]; // [rsp+128h] [rbp-230h] BYREF
  _BYTE v82[16]; // [rsp+138h] [rbp-220h] BYREF
  _BYTE v83[16]; // [rsp+148h] [rbp-210h] BYREF
  _BYTE v84[16]; // [rsp+158h] [rbp-200h] BYREF
  _BYTE v85[16]; // [rsp+168h] [rbp-1F0h] BYREF
  _BYTE v86[16]; // [rsp+178h] [rbp-1E0h] BYREF
  _BYTE v87[16]; // [rsp+188h] [rbp-1D0h] BYREF
  _BYTE v88[16]; // [rsp+198h] [rbp-1C0h] BYREF
  _BYTE v89[16]; // [rsp+1A8h] [rbp-1B0h] BYREF
  VARIANTARG pvarg; // [rsp+1B8h] [rbp-1A0h] BYREF
  VARIANTARG v91; // [rsp+1D0h] [rbp-188h] BYREF
  struct IWbemClassObject **v92; // [rsp+1E8h] [rbp-170h]
  WCHAR Buffer[152]; // [rsp+1F0h] [rbp-168h] BYREF

  v3 = this;
  v62 = this;
  v4 = 1;
  v63[0] = 0;
  memset_0(Buffer, 0, 0x12Cu);
  VariantInit(&pvarg);
  v5 = SysAllocString(L"CIM_StatisticalInformation");
  if ( !v5 )
  {
    _variant_t::~_variant_t(&pvarg);
    return 2147749894LL;
  }
  v69 = v5;
  v67 = 0;
  v7 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, _QWORD, _QWORD, struct IWbemServices **, _QWORD))a2->lpVtbl->GetObjectA)(
         a2,
         v5,
         0,
         0,
         &v67,
         0);
  v55 = v7;
  v8 = v67;
  v65 = v67;
  v68 = v67;
  if ( v7 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v11, *((_QWORD *)v3 + 1), v7);
    }
  }
  else
  {
    v60 = 0;
    v7 = ((__int64 (__fastcall *)(struct IWbemServices *, CInsertionString **))v67->lpVtbl->OpenNamespace)(v67, &v60);
    v55 = v7;
    v9 = v60;
    v61 = (struct IWbemClassObject *)v60;
    if ( v7 >= 0 )
      v4 = (*(int (__fastcall **)(CInsertionString *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v60 + 24LL))(
             v60,
             L"abstract",
             0,
             &pvarg,
             0) >= 0;
    if ( v9 )
      (*(void (__fastcall **)(CInsertionString *))(*(_QWORD *)v9 + 16LL))(v9);
    v61 = 0;
    v3 = v62;
  }
  if ( v7 < 0 )
  {
    v43 = v55;
LABEL_77:
    if ( v8 )
      ((void (__fastcall *)(struct IWbemServices *))v8->lpVtbl->Release)(v8);
    goto LABEL_79;
  }
  v59 = 0;
  v12 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, struct IWbemClassObject **))v67->lpVtbl->PutInstance)(
          v67,
          0,
          &v59);
  v56 = v12;
  v92 = &v59;
  if ( v12 < 0 )
    goto LABEL_66;
  _variant_t::operator=(&pvarg, L"Win32_Perf");
  v12 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, int))v59->lpVtbl->Put)(
          v59,
          L"__CLASS",
          0,
          &pvarg,
          8);
  v56 = v12;
  if ( v12 < 0 )
    goto LABEL_66;
  ModuleHandleW = GetModuleHandleW(0);
  LoadStringW(ModuleHandleW, 1u, Buffer, 150);
  v12 = CWMIBroker::SetBaseClassQualifiers(v14, v59, v4, Buffer);
  v56 = v12;
  if ( v12 < 0 )
    goto LABEL_66;
  if ( v4 )
  {
    v12 = CWMIBroker::SetProperties(v15, v59);
    v56 = v12;
  }
  if ( v12 < 0 || (v12 = CWMIBroker::VerifyByTemplate(v3, a2, &v59, L"Win32_Perf", v63), v56 = v12, v12 < 0) )
  {
LABEL_66:
    v71[0] = (unsigned __int16 *)v89;
    v60 = CInsertionString::CInsertionString((CInsertionString *)v89);
    v79 = v88;
    v70 = CInsertionString::CInsertionString((CInsertionString *)v88);
    v78 = v87;
    v45 = CInsertionString::CInsertionString((CInsertionString *)v87);
    v77 = v86;
    v46 = CInsertionString::CInsertionString((CInsertionString *)v86);
    v76 = v85;
    v47 = CInsertionString::CInsertionString((CInsertionString *)v85);
    v75 = v84;
    v48 = CInsertionString::CInsertionString((CInsertionString *)v84);
    v74 = v83;
    v49 = CInsertionString::CInsertionString((CInsertionString *)v83);
    v73 = v82;
    v50 = CInsertionString::CInsertionString((CInsertionString *)v82);
    v72 = v81;
    LODWORD(v66) = v12;
    v51 = (const struct CInsertionString *)CInsertionString::CInsertionString(v81, (unsigned int)v12);
    *(_QWORD *)v63 = v80;
    v52 = CInsertionString::CInsertionString((CInsertionString *)v80, *((const unsigned __int16 **)v62 + 1));
    CAdapUtility::NTLogEvent(
      (__int64)v70,
      (__int64)WBEM_MC_ADAP_UNABLE_TO_ADD_WIN32PERF,
      v52,
      v51,
      v50,
      v49,
      v48,
      v47,
      v46,
      v45,
      v70,
      v60);
    v53 = GetMemLogObject();
    CMemoryLog::Write(v53, -1);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v29 = v56;
    }
    else
    {
      v29 = v56;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v54, v56);
    }
    if ( v59 )
      ((void (__fastcall *)(struct IWbemClassObject *))v59->lpVtbl->Release)(v59);
    v59 = 0;
    if ( v65 )
      ((void (__fastcall *)(struct IWbemServices *))v65->lpVtbl->Release)(v65);
    goto LABEL_36;
  }
  v64 = 0;
  VariantInit(&v91);
  v16 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v59->lpVtbl->SpawnDerivedClass)(
          v59,
          0,
          &v64);
  v57 = v16;
  v60 = (CInsertionString *)&v64;
  if ( v16 >= 0 )
  {
    _variant_t::operator=(&v91, L"Win32_PerfRawData");
    ((void (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, int))v64->lpVtbl->Put)(
      v64,
      L"__CLASS",
      0,
      &v91,
      8);
    v17 = GetModuleHandleW(0);
    LoadStringW(v17, 2u, Buffer, 150);
    v16 = CWMIBroker::SetBaseClassQualifiers(v18, v64, v4, Buffer);
    v57 = v16;
    if ( v16 >= 0 )
    {
      v16 = CWMIBroker::VerifyByTemplate(v3, a2, &v64, L"Win32_PerfRawData", v63);
      v57 = v16;
    }
  }
  if ( v64 )
    ((void (__fastcall *)(struct IWbemClassObject *))v64->lpVtbl->Release)(v64);
  v64 = 0;
  if ( v16 < 0 )
  {
    v70 = (struct CInsertionString *)v80;
    v60 = CInsertionString::CInsertionString((CInsertionString *)v80);
    *(_QWORD *)v63 = v81;
    v66 = CInsertionString::CInsertionString((CInsertionString *)v81);
    v73 = v82;
    v19 = CInsertionString::CInsertionString((CInsertionString *)v82);
    v74 = v83;
    v20 = CInsertionString::CInsertionString((CInsertionString *)v83);
    v75 = v84;
    v21 = CInsertionString::CInsertionString((CInsertionString *)v84);
    v76 = v85;
    v22 = CInsertionString::CInsertionString((CInsertionString *)v85);
    v77 = v86;
    v23 = CInsertionString::CInsertionString((CInsertionString *)v86);
    v78 = v87;
    v24 = CInsertionString::CInsertionString((CInsertionString *)v87);
    v79 = v88;
    LODWORD(v72) = v16;
    v25 = (const struct CInsertionString *)CInsertionString::CInsertionString(v88, (unsigned int)v16);
    v71[0] = (unsigned __int16 *)v89;
    v26 = CInsertionString::CInsertionString((CInsertionString *)v89, *((const unsigned __int16 **)v62 + 1));
    CAdapUtility::NTLogEvent((__int64)v66, (__int64)";", v26, v25, v24, v23, v22, v21, v20, v19, v66, v60);
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -1);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v29 = v57;
    }
    else
    {
      v29 = v57;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v28, v57);
    }
    _variant_t::~_variant_t(&v91);
    if ( v59 )
      ((void (__fastcall *)(struct IWbemClassObject *))v59->lpVtbl->Release)(v59);
    v59 = 0;
    if ( v65 )
      ((void (__fastcall *)(struct IWbemServices *))v65->lpVtbl->Release)(v65);
LABEL_36:
    v68 = 0;
    CSysFreeMe::~CSysFreeMe(&v69);
    _variant_t::~_variant_t(&pvarg);
    return v29;
  }
  v61 = 0;
  v30 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v59->lpVtbl->SpawnDerivedClass)(
          v59,
          0,
          &v61);
  v58 = v30;
  v71[0] = (unsigned __int16 *)&v61;
  if ( v30 >= 0 )
  {
    _variant_t::operator=(&v91, L"Win32_PerfFormattedData");
    ((void (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, int))v61->lpVtbl->Put)(
      v61,
      L"__CLASS",
      0,
      &v91,
      8);
    v31 = GetModuleHandleW(0);
    LoadStringW(v31, 3u, Buffer, 150);
    v30 = CWMIBroker::SetBaseClassQualifiers(v32, v61, v4, Buffer);
    v58 = v30;
    if ( v30 >= 0 )
    {
      v30 = CWMIBroker::VerifyByTemplate(v3, a2, &v61, L"Win32_PerfFormattedData", v63);
      v58 = v30;
    }
  }
  if ( v61 )
    ((void (__fastcall *)(struct IWbemClassObject *))v61->lpVtbl->Release)(v61);
  v61 = 0;
  if ( v30 >= 0 )
  {
    if ( v63[0] )
    {
      v62 = 0;
      if ( ((int (__fastcall *)(struct IWbemServices *, const wchar_t *, _QWORD, _QWORD, CWMIBroker **, _QWORD))a2->lpVtbl->GetObjectA)(
             a2,
             L"\\\\.\\ROOT\\cimv2:__ClassProviderRegistration.provider=\"\\\\\\\\.\\\\root\\\\cimv2:__Win32Provider.Name=\\"
              "\"WmiPerfClass\\\"\"",
             0,
             0,
             &v62,
             0) >= 0
        && v4 )
      {
        v43 = ((__int64 (__fastcall *)(struct IWbemServices *, CWMIBroker *, __int64, _QWORD, _QWORD))a2->lpVtbl->PutInstance)(
                a2,
                v62,
                1,
                0,
                0);
        v63[0] = 0;
      }
      else
      {
        WString::WString((WString *)&v60, L"\\\\.\\root\\cimv2");
        CWMIBroker::CWMIBroker((CWMIBroker *)v71, (const struct WString *)&v60);
        WString::DeleteString((WString *)&v60, (unsigned __int16 *)v60);
        v65 = 0;
        v43 = CWMIBroker::ConnectToNamespace((const OLECHAR **)v71, (struct IUnknown **)&v65);
        if ( v43 >= 0 )
        {
          v44 = v65;
          v43 = ((__int64 (__fastcall *)(struct IWbemServices *, CWMIBroker *, __int64, _QWORD, _QWORD))v65->lpVtbl->PutInstance)(
                  v65,
                  v62,
                  1,
                  0,
                  0);
          ((void (__fastcall *)(struct IWbemServices *))v44->lpVtbl->Release)(v44);
        }
        CWMIBroker::~CWMIBroker(v71);
      }
      if ( v62 )
        (*(void (__fastcall **)(CWMIBroker *))(*(_QWORD *)v62 + 16LL))(v62);
    }
    else
    {
      v43 = v58;
    }
    _variant_t::~_variant_t(&v91);
    if ( v59 )
      ((void (__fastcall *)(struct IWbemClassObject *))v59->lpVtbl->Release)(v59);
    v59 = 0;
    goto LABEL_77;
  }
  v71[0] = (unsigned __int16 *)v89;
  v60 = CInsertionString::CInsertionString((CInsertionString *)v89);
  v79 = v88;
  v66 = CInsertionString::CInsertionString((CInsertionString *)v88);
  v78 = v87;
  v33 = CInsertionString::CInsertionString((CInsertionString *)v87);
  v77 = v86;
  v34 = CInsertionString::CInsertionString((CInsertionString *)v86);
  v76 = v85;
  v35 = CInsertionString::CInsertionString((CInsertionString *)v85);
  v75 = v84;
  v36 = CInsertionString::CInsertionString((CInsertionString *)v84);
  v74 = v83;
  v37 = CInsertionString::CInsertionString((CInsertionString *)v83);
  v73 = v82;
  v38 = CInsertionString::CInsertionString((CInsertionString *)v82);
  v72 = v81;
  LODWORD(v70) = v30;
  v39 = (const struct CInsertionString *)CInsertionString::CInsertionString(v81, (unsigned int)v30);
  *(_QWORD *)v63 = v80;
  v40 = CInsertionString::CInsertionString((CInsertionString *)v80, *((const unsigned __int16 **)v62 + 1));
  CAdapUtility::NTLogEvent((__int64)v66, (__int64)";", v40, v39, v38, v37, v36, v35, v34, v33, v66, v60);
  v41 = GetMemLogObject();
  CMemoryLog::Write(v41, -1);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v43 = v58;
  }
  else
  {
    v43 = v58;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v42, v58);
  }
  _variant_t::~_variant_t(&v91);
  if ( v59 )
    ((void (__fastcall *)(struct IWbemClassObject *))v59->lpVtbl->Release)(v59);
  v59 = 0;
  if ( v65 )
    ((void (__fastcall *)(struct IWbemServices *))v65->lpVtbl->Release)(v65);
LABEL_79:
  v68 = 0;
  CSysFreeMe::~CSysFreeMe(&v69);
  _variant_t::~_variant_t(&pvarg);
  return (unsigned int)v43;
}

```

## disassembly

```asm
0x1400037f0  mov     r11, rsp
0x1400037f3  mov     [r11+18h], rbx
0x1400037f7  mov     [r11+20h], rsi
0x1400037fb  push    rdi
0x1400037fc  push    r12
0x1400037fe  push    r13
0x140003800  push    r14
0x140003802  push    r15
0x140003804  sub     rsp, 330h
0x14000380b  mov     rax, cs:__security_cookie
0x140003812  xor     rax, rsp
0x140003815  mov     [rsp+358h+var_38], rax
0x14000381d  mov     rdi, rdx
0x140003820  mov     r15, rcx
0x140003823  mov     [rsp+358h+var_2D8], rcx
0x14000382b  mov     r13d, 1
0x140003831  mov     r14d, r13d
0x140003834  xor     r12d, r12d
0x140003837  mov     [r11-2D0h], r12d
0x14000383e  xor     edx, edx; Val
0x140003840  mov     r8d, 12Ch; Size
0x140003846  lea     rcx, [r11-168h]; void *
0x14000384d  call    memset_0
0x140003852  nop
0x140003853  lea     rcx, [rsp+358h+pvarg]; pvarg
0x14000385b  call    cs:__imp_VariantInit
0x140003861  nop
0x140003862  lea     rcx, psz; "CIM_StatisticalInformation"
0x140003869  call    cs:__imp_SysAllocString
0x14000386f  mov     rdx, rax
0x140003872  test    rax, rax
0x140003875  jnz     short loc_14000388E
0x140003877  lea     rcx, [rsp+358h+pvarg]; this
0x14000387f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003884  mov     eax, 80041006h
0x140003889  jmp     loc_1400045EC
0x14000388e  mov     [rsp+358h+var_2A0], rdx
0x140003896  mov     [rsp+358h+var_2B0], r12
0x14000389e  mov     rax, [rdi]
0x1400038a1  mov     [rsp+358h+var_330], r12
0x1400038a6  lea     rcx, [rsp+358h+var_2B0]
0x1400038ae  mov     [rsp+358h+var_338], rcx
0x1400038b3  xor     r9d, r9d
0x1400038b6  xor     r8d, r8d
0x1400038b9  mov     rcx, rdi
0x1400038bc  mov     rax, [rax+30h]
0x1400038c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038c5  mov     ebx, eax
0x1400038c7  mov     [rsp+358h+var_2F8], eax
0x1400038cb  mov     rsi, [rsp+358h+var_2B0]
0x1400038d3  mov     [rsp+358h+var_2C0], rsi
0x1400038db  mov     [rsp+358h+var_2A8], rsi
0x1400038e3  test    eax, eax
0x1400038e5  js      loc_140003971
0x1400038eb  mov     [rsp+358h+var_2E8], r12
0x1400038f0  mov     rcx, [rsp+358h+var_2B0]
0x1400038f8  mov     rax, [rcx]
0x1400038fb  lea     rdx, [rsp+358h+var_2E8]
0x140003900  mov     rax, [rax+18h]
0x140003904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003909  mov     ebx, eax
0x14000390b  mov     [rsp+358h+var_2F8], eax
0x14000390f  mov     r15, [rsp+358h+var_2E8]
0x140003914  mov     [rsp+358h+var_2E0], r15
0x140003919  test    eax, eax
0x14000391b  js      short loc_14000394E
0x14000391d  mov     rcx, [rsp+358h+var_2E8]
0x140003922  mov     rax, [rcx]
0x140003925  mov     [rsp+358h+var_338], r12
0x14000392a  lea     r9, [rsp+358h+pvarg]
0x140003932  xor     r8d, r8d
0x140003935  lea     rdx, aAbstract_0; "abstract"
0x14000393c  mov     rax, [rax+18h]
0x140003940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003945  mov     r14d, r12d
0x140003948  test    eax, eax
0x14000394a  setns   r14b
0x14000394e  test    r15, r15
0x140003951  jz      short loc_140003962
0x140003953  mov     rax, [r15]
0x140003956  mov     rcx, r15
0x140003959  mov     rax, [rax+10h]
0x14000395d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003962  mov     [rsp+358h+var_2E0], r12
0x140003967  mov     r15, [rsp+358h+var_2D8]
0x14000396f  jmp     short loc_1400039B8
0x140003971  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140003977  or      edx, 0FFFFFFFFh
0x14000397a  mov     rcx, rax
0x14000397d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140003983  lea     rax, WPP_GLOBAL_Control
0x14000398a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003991  cmp     rcx, rax
0x140003994  jz      short loc_1400039B8
0x140003996  test    [rcx+1Ch], r13b
0x14000399a  jz      short loc_1400039B8
0x14000399c  cmp     byte ptr [rcx+19h], 2
0x1400039a0  jb      short loc_1400039B8
0x1400039a2  mov     edx, 0Dh
0x1400039a7  mov     dword ptr [rsp+358h+var_338], ebx
0x1400039ab  mov     r9, [r15+8]
0x1400039af  mov     rcx, [rcx+10h]
0x1400039b3  call    WPP_SF_SD
0x1400039b8  test    ebx, ebx
0x1400039ba  js      loc_1400045A8
0x1400039c0  mov     [rsp+358h+var_2F0], r12
0x1400039c5  mov     rcx, [rsp+358h+var_2B0]
0x1400039cd  mov     rax, [rcx]
0x1400039d0  lea     r8, [rsp+358h+var_2F0]
0x1400039d5  xor     edx, edx
0x1400039d7  mov     rax, [rax+70h]
0x1400039db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039e0  mov     ebx, eax
0x1400039e2  mov     [rsp+358h+var_2F8], eax
0x1400039e6  lea     rax, [rsp+358h+var_2F0]
0x1400039eb  mov     [rsp+358h+var_170], rax
0x1400039f3  test    ebx, ebx
0x1400039f5  js      loc_140004357
0x1400039fb  lea     rdx, aWin32Perf; "Win32_Perf"
0x140003a02  lea     rcx, [rsp+358h+pvarg]
0x140003a0a  call    ??4_variant_t@@QEAAAEAV0@PEBG@Z; _variant_t::operator=(ushort const *)
0x140003a0f  mov     rcx, [rsp+358h+var_2F0]
0x140003a14  mov     rax, [rcx]
0x140003a17  mov     dword ptr [rsp+358h+var_338], 8
0x140003a1f  lea     r9, [rsp+358h+pvarg]
0x140003a27  xor     r8d, r8d
0x140003a2a  lea     rdx, aClass; "__CLASS"
0x140003a31  mov     rax, [rax+28h]
0x140003a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a3a  mov     ebx, eax
0x140003a3c  mov     [rsp+358h+var_2F8], eax
0x140003a40  test    eax, eax
0x140003a42  js      loc_140004357
0x140003a48  xor     ecx, ecx; lpModuleName
0x140003a4a  call    cs:__imp_GetModuleHandleW
0x140003a50  mov     rcx, rax; hInstance
0x140003a53  mov     r9d, 96h; cchBufferMax
0x140003a59  lea     r8, [rsp+358h+Buffer]; lpBuffer
0x140003a61  mov     edx, r13d; uID
0x140003a64  call    cs:__imp_LoadStringW
0x140003a6a  lea     r9, [rsp+358h+Buffer]; unsigned __int16 *
0x140003a72  mov     r8d, r14d; int
0x140003a75  mov     rdx, [rsp+358h+var_2F0]; struct IWbemClassObject *
0x140003a7a  call    ?SetBaseClassQualifiers@CWMIBroker@@AEAAJPEAUIWbemClassObject@@HPEBG@Z; CWMIBroker::SetBaseClassQualifiers(IWbemClassObject *,int,ushort const *)
0x140003a7f  mov     ebx, eax
0x140003a81  mov     [rsp+358h+var_2F8], eax
0x140003a85  test    eax, eax
0x140003a87  js      loc_140004357
0x140003a8d  test    r14d, r14d
0x140003a90  jz      short loc_140003AA2
0x140003a92  mov     rdx, [rsp+358h+var_2F0]; struct IWbemClassObject *
0x140003a97  call    ?SetProperties@CWMIBroker@@AEAAJPEAUIWbemClassObject@@@Z; CWMIBroker::SetProperties(IWbemClassObject *)
0x140003a9c  mov     ebx, eax
0x140003a9e  mov     [rsp+358h+var_2F8], eax
0x140003aa2  test    ebx, ebx
0x140003aa4  js      loc_140004357
0x140003aaa  lea     rax, [rsp+358h+var_2D0]
0x140003ab2  mov     [rsp+358h+var_338], rax; int *
0x140003ab7  lea     r9, aWin32Perf; "Win32_Perf"
0x140003abe  lea     r8, [rsp+358h+var_2F0]; struct IWbemClassObject **
0x140003ac3  mov     rdx, rdi; struct IWbemServices *
0x140003ac6  mov     rcx, r15; this
0x140003ac9  call    ?VerifyByTemplate@CWMIBroker@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@PEAGAEAH@Z; CWMIBroker::VerifyByTemplate(IWbemServices *,IWbemClassObject * *,ushort *,int &)
0x140003ace  mov     ebx, eax
0x140003ad0  mov     [rsp+358h+var_2F8], eax
0x140003ad4  test    eax, eax
0x140003ad6  js      loc_140004357
0x140003adc  mov     [rsp+358h+var_2C8], r12
0x140003ae4  lea     rcx, [rsp+358h+var_188]; pvarg
0x140003aec  call    cs:__imp_VariantInit
0x140003af2  nop
0x140003af3  mov     rcx, [rsp+358h+var_2F0]
0x140003af8  mov     rax, [rcx]
0x140003afb  lea     r8, [rsp+358h+var_2C8]
0x140003b03  xor     edx, edx
0x140003b05  mov     rax, [rax+70h]
0x140003b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b0e  mov     ebx, eax
0x140003b10  mov     [rsp+358h+var_2F8], eax
0x140003b14  lea     rax, [rsp+358h+var_2C8]
0x140003b1c  mov     [rsp+358h+var_2E8], rax
0x140003b21  test    ebx, ebx
0x140003b23  js      loc_140003BE2
0x140003b29  lea     rdx, aWin32Perfrawda; "Win32_PerfRawData"
0x140003b30  lea     rcx, [rsp+358h+var_188]
0x140003b38  call    ??4_variant_t@@QEAAAEAV0@PEBG@Z; _variant_t::operator=(ushort const *)
0x140003b3d  mov     rcx, [rsp+358h+var_2C8]
0x140003b45  mov     rax, [rcx]
0x140003b48  mov     dword ptr [rsp+358h+var_338], 8
0x140003b50  lea     r9, [rsp+358h+var_188]
0x140003b58  xor     r8d, r8d
0x140003b5b  lea     rdx, aClass; "__CLASS"
0x140003b62  mov     rax, [rax+28h]
0x140003b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b6b  mov     [rsp+358h+var_2F8], eax
0x140003b6f  xor     ecx, ecx; lpModuleName
0x140003b71  call    cs:__imp_GetModuleHandleW
0x140003b77  mov     rcx, rax; hInstance
0x140003b7a  mov     r9d, 96h; cchBufferMax
0x140003b80  lea     r8, [rsp+358h+Buffer]; lpBuffer
0x140003b88  mov     edx, 2; uID
0x140003b8d  call    cs:__imp_LoadStringW
0x140003b93  lea     r9, [rsp+358h+Buffer]; unsigned __int16 *
0x140003b9b  mov     r8d, r14d; int
0x140003b9e  mov     rdx, [rsp+358h+var_2C8]; struct IWbemClassObject *
0x140003ba6  call    ?SetBaseClassQualifiers@CWMIBroker@@AEAAJPEAUIWbemClassObject@@HPEBG@Z; CWMIBroker::SetBaseClassQualifiers(IWbemClassObject *,int,ushort const *)
0x140003bab  mov     ebx, eax
0x140003bad  mov     [rsp+358h+var_2F8], eax
0x140003bb1  test    eax, eax
0x140003bb3  js      short loc_140003BE2
0x140003bb5  lea     rax, [rsp+358h+var_2D0]
0x140003bbd  mov     [rsp+358h+var_338], rax; int *
0x140003bc2  lea     r9, aWin32Perfrawda; "Win32_PerfRawData"
0x140003bc9  lea     r8, [rsp+358h+var_2C8]; struct IWbemClassObject **
0x140003bd1  mov     rdx, rdi; struct IWbemServices *
0x140003bd4  mov     rcx, r15; this
0x140003bd7  call    ?VerifyByTemplate@CWMIBroker@@AEAAJPEAUIWbemServices@@PEAPEAUIWbemClassObject@@PEAGAEAH@Z; CWMIBroker::VerifyByTemplate(IWbemServices *,IWbemClassObject * *,ushort *,int &)
0x140003bdc  mov     ebx, eax
0x140003bde  mov     [rsp+358h+var_2F8], eax
0x140003be2  mov     rcx, [rsp+358h+var_2C8]
0x140003bea  test    rcx, rcx
0x140003bed  jz      short loc_140003BFB
0x140003bef  mov     rax, [rcx]
0x140003bf2  mov     rax, [rax+10h]
0x140003bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bfb  mov     [rsp+358h+var_2C8], r12
0x140003c03  test    ebx, ebx
0x140003c05  jns     loc_140003E6D
0x140003c0b  lea     rax, [rsp+358h+var_240]
0x140003c13  mov     [rsp+358h+var_298], rax
0x140003c1b  lea     rcx, [rsp+358h+var_240]; this
0x140003c23  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003c28  mov     [rsp+358h+var_2E8], rax
0x140003c2d  lea     rax, [rsp+358h+var_230]
0x140003c35  mov     qword ptr [rsp+358h+var_2D0], rax
0x140003c3d  lea     rcx, [rsp+358h+var_230]; this
0x140003c45  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003c4a  mov     [rsp+358h+var_2B8], rax
0x140003c52  lea     rax, [rsp+358h+var_220]
0x140003c5a  mov     [rsp+358h+var_278], rax
0x140003c62  lea     rcx, [rsp+358h+var_220]; this
0x140003c6a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003c6f  mov     r13, rax
0x140003c72  lea     rax, [rsp+358h+var_210]
0x140003c7a  mov     [rsp+358h+var_270], rax
0x140003c82  lea     rcx, [rsp+358h+var_210]; this
0x140003c8a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003c8f  mov     r12, rax
0x140003c92  lea     rax, [rsp+358h+var_200]
0x140003c9a  mov     [rsp+358h+var_268], rax
0x140003ca2  lea     rcx, [rsp+358h+var_200]; this
0x140003caa  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003caf  mov     r15, rax
0x140003cb2  lea     rax, [rsp+358h+var_1F0]
0x140003cba  mov     [rsp+358h+var_260], rax
0x140003cc2  lea     rcx, [rsp+358h+var_1F0]; this
0x140003cca  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003ccf  mov     r14, rax
0x140003cd2  lea     rax, [rsp+358h+var_1E0]
0x140003cda  mov     [rsp+358h+var_258], rax
0x140003ce2  lea     rcx, [rsp+358h+var_1E0]; this
0x140003cea  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003cef  mov     rsi, rax
0x140003cf2  lea     rax, [rsp+358h+var_1D0]
0x140003cfa  mov     [rsp+358h+var_250], rax
0x140003d02  lea     rcx, [rsp+358h+var_1D0]; this
0x140003d0a  call    ??0CInsertionString@@QEAA@XZ; CInsertionString::CInsertionString(void)
0x140003d0f  mov     rdi, rax
0x140003d12  lea     rax, [rsp+358h+var_1C0]
0x140003d1a  mov     [rsp+358h+var_248], rax
0x140003d22  mov     dword ptr [rsp+358h+var_280], ebx
0x140003d29  mov     edx, ebx
0x140003d2b  lea     rcx, [rsp+358h+var_1C0]
0x140003d33  call    cs:__imp_??0CInsertionString@@QEAA@VCHex@@@Z; CInsertionString::CInsertionString(CHex)
0x140003d39  mov     rbx, rax
0x140003d3c  lea     rax, [rsp+358h+var_1B0]
0x140003d44  mov     [rsp+358h+var_290], rax
0x140003d4c  mov     rdx, [rsp+358h+var_2D8]
0x140003d54  mov     rdx, [rdx+8]; unsigned __int16 *
0x140003d58  lea     rcx, [rsp+358h+var_1B0]; this
0x140003d60  call    ??0CInsertionString@@QEAA@PEBG@Z; CInsertionString::CInsertionString(ushort const *)
0x140003d65  nop
0x140003d66  mov     rcx, [rsp+358h+var_2E8]
0x140003d6b  mov     [rsp+358h+var_300], rcx
0x140003d70  mov     rcx, [rsp+358h+var_2B8]
0x140003d78  mov     [rsp+358h+var_308], rcx
0x140003d7d  mov     [rsp+358h+var_310], r13
0x140003d82  mov     [rsp+358h+var_318], r12
0x140003d87  mov     [rsp+358h+var_320], r15
0x140003d8c  mov     [rsp+358h+var_328], r14
0x140003d91  mov     [rsp+358h+var_330], rsi
0x140003d96  mov     [rsp+358h+var_338], rdi
0x140003d9b  mov     r9, rbx
0x140003d9e  mov     r8, rax
0x140003da1  lea     rdx, WBEM_MC_ADAP_UNABLE_TO_ADD_WIN32PERFRAWDATA; ";"
0x140003da8  call    ?NTLogEvent@CAdapUtility@@SAJKAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z; CAdapUtility::NTLogEvent(ulong,_EVENT_DESCRIPTOR const &,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString,CInsertionString)
0x140003dad  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140003db3  or      edx, 0FFFFFFFFh
0x140003db6  mov     rcx, rax
0x140003db9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
  ... truncated ...
```

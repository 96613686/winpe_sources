# OSIntegration::DEH::FirewallHandler::GetXboxCapabilities(OSIntegration::Package const *,_SID_AND_ATTRIBUTES * *,ulong *)

- ea: `0x1800c72f8`
- end: `0x1800c7e72`
- name: `?GetXboxCapabilities@FirewallHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@PEAPEAU_SID_AND_ATTRIBUTES@@PEAK@Z`
- size: `2938`
- prototype: `int(OSIntegration::DEH::FirewallHandler *__hidden this, const struct OSIntegration::Package *, struct _SID_AND_ATTRIBUTES **, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005fc34`

## callees

- `0x18000b3bc`
- `0x18000bd80`
- `0x18000e6e0`
- `0x180016d1c`
- `0x18003f7e0`
- `0x180051b80`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a5970`
- `0x1800c72f8`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x1800f10e4`
- `0x18014d9e4`
- `0x1801727cc`
- `0x1801734fc`
- `0x1801ffc5c`
- `0x180211010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c7515`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c7515`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c75d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c7607`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c75d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c7607`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7e2d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7e2d`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c77cf`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7908`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7a04`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7c74`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7db5`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c77cf`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7908`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7a04`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7c74`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c7db5`
- `ntdll!RtlInitUnicodeString` at `0x1800c77bd`
- `ntdll!RtlInitUnicodeString` at `0x1800c78f6`
- `ntdll!RtlInitUnicodeString` at `0x1800c79f2`
- `ntdll!RtlInitUnicodeString` at `0x1800c7c61`
- `ntdll!RtlInitUnicodeString` at `0x1800c7da3`
- `ntdll!RtlInitUnicodeString` at `0x1800c77bd`
- `ntdll!RtlInitUnicodeString` at `0x1800c78f6`
- `ntdll!RtlInitUnicodeString` at `0x1800c79f2`
- `ntdll!RtlInitUnicodeString` at `0x1800c7c61`
- `ntdll!RtlInitUnicodeString` at `0x1800c7da3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7819`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7866`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c78dc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c794e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c79d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7a4a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7ac3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7b22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7b99`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7bf8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7cce`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7d18`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7d86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7dfb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7819`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7866`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c78dc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c794e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c79d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7a4a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7ac3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7b22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7b99`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7bf8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7cce`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7d18`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7d86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c7dfb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c7adf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c7bb5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c7adf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c7bb5`

## string_xrefs

- `0x1800c73fe`: `/m:Package/m:Applications/m:Application/m:Extensions/mx:Extension/mx:XboxSystemResources`
- `0x1800c7339`: `constrainedImpersonation`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::FirewallHandler::GetXboxCapabilities(
        OSIntegration::DEH::FirewallHandler *this,
        const struct OSIntegration::Package *a2,
        struct _SID_AND_ATTRIBUTES **a3,
        unsigned int *a4)
{
  __int64 v5; // rax
  int v6; // r13d
  unsigned int v7; // esi
  struct IXMLDOMDocument2 **v8; // r8
  int XMLDOMFromPackage; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int HasGameOSPackageDependency; // eax
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, BSTR, _QWORD); // rbx
  int AttributeValueStringFromElement; // eax
  __int64 v17; // rdx
  int v18; // r12d
  int v19; // r15d
  int i; // edi
  wchar_t *v21; // rbx
  int v22; // ecx
  int v23; // ecx
  int v24; // r12d
  int v25; // ecx
  unsigned int v26; // r14d
  struct _SID_AND_ATTRIBUTES *v27; // rbx
  void **v28; // rdx
  OSIntegration::Tools::Capabilities *v29; // rdi
  int v30; // eax
  int v31; // r15d
  int v32; // eax
  unsigned __int64 v33; // rdx
  int LastError; // r14d
  unsigned int j; // edi
  PSID Sid; // rcx
  unsigned __int64 v37; // rdx
  unsigned int k; // edi
  PSID v39; // rcx
  OSIntegration::Tools::Capabilities *v40; // rdi
  int v41; // eax
  unsigned int m; // edi
  PSID v43; // rcx
  int v44; // eax
  unsigned int n; // edi
  PSID v46; // rcx
  OSIntegration::Tools::Capabilities *v47; // rdi
  int v48; // eax
  unsigned int ii; // edi
  PSID v50; // rcx
  int v51; // eax
  unsigned int jj; // edi
  PSID v53; // rcx
  OSIntegration::Tools::Capabilities *v54; // rdi
  int v55; // eax
  unsigned int kk; // edi
  PSID v57; // rcx
  const char *v58; // r9
  unsigned int mm; // edi
  PSID v60; // rcx
  OSIntegration::Tools::Capabilities *v61; // rdi
  int v62; // eax
  unsigned int nn; // edi
  PSID v64; // rcx
  const char *v65; // r9
  unsigned int i1; // edi
  PSID v67; // rcx
  int v68; // eax
  signed int i2; // edi
  OSIntegration::Tools::Capabilities *v70; // r12
  int v71; // eax
  int v72; // eax
  unsigned int i4; // edi
  PSID v74; // rcx
  unsigned int i3; // edi
  PSID v76; // rcx
  OSIntegration::Tools::Capabilities *v77; // rdi
  int v78; // eax
  unsigned int i5; // edi
  PSID v80; // rcx
  int v81; // eax
  unsigned int i6; // edi
  PSID v83; // rcx
  int *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  bool v86; // [rsp+30h] [rbp-D0h] BYREF
  int v87; // [rsp+34h] [rbp-CCh] BYREF
  int v88; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v89; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v90; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v91; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v92; // [rsp+58h] [rbp-A8h] BYREF
  int v93; // [rsp+60h] [rbp-A0h]
  int v94; // [rsp+64h] [rbp-9Ch]
  Common::Xml *v95; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v96)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  struct _SID_AND_ATTRIBUTES **v99; // [rsp+90h] [rbp-70h]
  unsigned int *v100; // [rsp+98h] [rbp-68h]
  unsigned __int16 v101[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v102; // [rsp+B0h] [rbp-50h]
  OSIntegration::Package *v103; // [rsp+C0h] [rbp-40h]
  PCWSTR SourceString[3]; // [rsp+C8h] [rbp-38h]
  _BYTE v105[48]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v100 = a4;
  v99 = a3;
  v103 = a2;
  v93 = 0;
  SourceString[0] = L"constrainedImpersonation";
  SourceString[1] = L"activateAsUser";
  SourceString[2] = L"muma";
  DestinationString = 0;
  v5 = *((_QWORD *)a2 + 54);
  if ( v5 == 12 )
  {
    v93 = 1;
    v7 = 4;
  }
  else
  {
    v6 = 0;
    v7 = 0;
    if ( v5 != 11 )
      goto LABEL_6;
    v7 = 3;
  }
  v6 = 1;
LABEL_6:
  v89 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  XMLDOMFromPackage = OSIntegration::Tools::GetXMLDOMFromPackage(a2, (const struct OSIntegration::Package *)&v89, v8);
  v10 = XMLDOMFromPackage;
  if ( XMLDOMFromPackage >= 0 )
  {
    v96 = 0;
    bstrString = 0;
    HasGameOSPackageDependency = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
                                   &bstrString,
                                   L"/m:Package/m:Applications/m:Application/m:Extensions/mx:Extension/mx:XboxSystemResources");
    v10 = HasGameOSPackageDependency;
    if ( HasGameOSPackageDependency < 0 )
    {
      v13 = 881;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
        (const char *)(unsigned int)HasGameOSPackageDependency,
        (int)bIgnoreCase);
LABEL_172:
      SysFreeString(bstrString);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
      return v10;
    }
    v14 = v89;
    v15 = *(__int64 (__fastcall **)(__int64, BSTR, _QWORD))(*(_QWORD *)v89 + 296LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
    HasGameOSPackageDependency = v15(v14, bstrString, &v96);
    v10 = HasGameOSPackageDependency;
    if ( HasGameOSPackageDependency < 0 )
    {
      v13 = 882;
      goto LABEL_14;
    }
    v94 = 0;
    if ( v96 )
    {
      v95 = 0;
      *(_OWORD *)v101 = 0;
      v102 = 0;
      v88 = 0;
      AttributeValueStringFromElement = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v96, (__int64 *)&v95);
      v10 = AttributeValueStringFromElement;
      if ( AttributeValueStringFromElement < 0 )
      {
        v17 = 890;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
          (const char *)(unsigned int)AttributeValueStringFromElement,
          (int)bIgnoreCase);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v101);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
        goto LABEL_172;
      }
      AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                          v95,
                                          (struct IXMLDOMElement *)&stru_180259100,
                                          v101,
                                          (struct Common::StringBuffer *)&v88,
                                          bIgnoreCase);
      v10 = AttributeValueStringFromElement;
      if ( AttributeValueStringFromElement < 0 )
      {
        v17 = 891;
        goto LABEL_18;
      }
      if ( v88 && *(_QWORD *)&v101[4] && !(unsigned int)_o__wcsicmp(*(_QWORD *)&v101[4], L"extendedVideoPlayback") )
      {
        v94 = 1;
        ++v7;
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v101);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    }
    v18 = 0;
    v19 = 0;
    v88 = 0;
    for ( i = 0; (unsigned __int64)i < 7; ++i )
    {
      v87 = 0;
      v21 = off_18022A7C0[i];
      v91 = v89;
      Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalAddRef(&v91);
      HasGameOSPackageDependency = OSIntegration::DEH::FirewallHandler::CapabilityExists(
                                     v22,
                                     (unsigned int)&v91,
                                     (unsigned int)L"/*[local-name()='Package']/*[local-name()='Capabilities']/*[local-nam"
                                                    "e()='Capability' and @Name='%s']",
                                     (_DWORD)v21,
                                     (__int64)&v87);
      v10 = HasGameOSPackageDependency;
      if ( HasGameOSPackageDependency < 0 )
      {
        v13 = 903;
        goto LABEL_14;
      }
      if ( v87 )
      {
        v88 |= 1 << i;
        ++v7;
        if ( CompareStringOrdinal(off_18022A7C0[i], -1, L"kinectAudio", -1, 1) == 2 )
        {
          v18 = 1;
        }
        else if ( CompareStringOrdinal(off_18022A7C0[i], -1, L"kinectVision", -1, 1) == 2 )
        {
          v19 = 1;
        }
      }
    }
    LODWORD(v91) = 0;
    if ( v18 )
    {
      v87 = 0;
      v90 = v89;
      Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalAddRef(&v90);
      HasGameOSPackageDependency = OSIntegration::DEH::FirewallHandler::CapabilityExists(
                                     v23,
                                     (unsigned int)&v90,
                                     (unsigned int)L"/*[local-name()='Package']/*[local-name()='Capabilities']/*[local-nam"
                                                    "e()='DeviceCapability' and @Name='%s']",
                                     (unsigned int)L"microphone",
                                     (__int64)&v87);
      v10 = HasGameOSPackageDependency;
      if ( HasGameOSPackageDependency < 0 )
      {
        v13 = 926;
        goto LABEL_14;
      }
      if ( !v87 )
      {
        LODWORD(v91) = 1;
        ++v7;
      }
    }
    v24 = 0;
    LODWORD(v90) = 0;
    if ( v19 )
    {
      v87 = 0;
      v92 = v89;
      Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalAddRef(&v92);
      HasGameOSPackageDependency = OSIntegration::DEH::FirewallHandler::CapabilityExists(
                                     v25,
                                     (unsigned int)&v92,
                                     (unsigned int)L"/*[local-name()='Package']/*[local-name()='Capabilities']/*[local-nam"
                                                    "e()='DeviceCapability' and @Name='%s']",
                                     (unsigned int)L"webcam",
                                     (__int64)&v87);
      v10 = HasGameOSPackageDependency;
      if ( HasGameOSPackageDependency < 0 )
      {
        v13 = 937;
        goto LABEL_14;
      }
      if ( !v87 )
      {
        v24 = 1;
        LODWORD(v90) = 1;
        ++v7;
      }
    }
    v87 = 0;
    if ( Common::Deployment::Platform::g_platform == 5 )
    {
      v86 = 0;
      HasGameOSPackageDependency = OSIntegration::Package::GetHasGameOSPackageDependency(v103, &v86);
      v10 = HasGameOSPackageDependency;
      if ( HasGameOSPackageDependency < 0 )
      {
        v13 = 950;
        goto LABEL_14;
      }
      if ( v86 )
      {
        v87 = 1;
        ++v7;
      }
    }
    *v99 = 0;
    *v100 = 0;
    if ( !v7 )
    {
      v10 = 0;
      goto LABEL_172;
    }
    v26 = 0;
    v27 = (struct _SID_AND_ATTRIBUTES *)operator new[](saturated_mul(v7, 0x10u));
    memset_0(v27, 0, 16LL * v7);
    if ( v6 )
    {
      while ( 1 )
      {
        if ( v26 >= 3 )
        {
          v24 = v90;
          goto LABEL_71;
        }
        v29 = (OSIntegration::Tools::Capabilities *)&v27[v26];
        v30 = OSIntegration::Tools::Capabilities::AllocSid(v29, v28);
        v31 = v30;
        if ( v30 < 0 )
          break;
        RtlInitUnicodeString(&DestinationString, SourceString[v26]);
        v32 = RtlDeriveCapabilitySidsFromName(&DestinationString, v105, *(_QWORD *)v29);
        if ( v32 < 0 )
        {
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x3E1,
                        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                        (const char *)(unsigned int)v32,
                        (int)bIgnoreCase);
          if ( v27 )
          {
            for ( j = 0; j < v7; ++j )
            {
              Sid = v27[j].Sid;
              if ( Sid )
                FreeSid(Sid);
            }
          }
          goto LABEL_63;
        }
        *((_DWORD *)v29 + 2) = 4;
        ++v26;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
        (const char *)(unsigned int)v30,
        (int)bIgnoreCase);
      if ( v27 )
      {
        for ( k = 0; k < v7; ++k )
        {
          v39 = v27[k].Sid;
          if ( v39 )
            FreeSid(v39);
        }
      }
      goto LABEL_69;
    }
LABEL_71:
    if ( v93 )
    {
      v40 = (OSIntegration::Tools::Capabilities *)&v27[v26];
      v41 = OSIntegration::Tools::Capabilities::AllocSid(v40, v28);
      v31 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EB,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
          (const char *)(unsigned int)v41,
          (int)bIgnoreCase);
        if ( v27 )
        {
          for ( m = 0; m < v7; ++m )
          {
            v43 = v27[m].Sid;
            if ( v43 )
              FreeSid(v43);
          }
        }
LABEL_69:
        operator delete(v27, v37);
        v10 = v31;
        goto LABEL_172;
      }
      RtlInitUnicodeString(&DestinationString, L"eraApplication");
      v44 = RtlDeriveCapabilitySidsFromName(&DestinationString, v105, *(_QWORD *)v40);
      if ( v44 < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x3EE,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                      (const char *)(unsigned int)v44,
                      (int)bIgnoreCase);
        if ( v27 )
        {
          for ( n = 0; n < v7; ++n )
          {
            v46 = v27[n].Sid;
            if ( v46 )
              FreeSid(v46);
          }
        }
LABEL_63:
        operator delete(v27, v33);
        v10 = LastError;
        goto LABEL_172;
      }
      *((_DWORD *)v40 + 2) = 4;
      ++v26;
    }
    if ( v94 )
    {
      v47 = (OSIntegration::Tools::Capabilities *)&v27[v26];
      v48 = OSIntegration::Tools::Capabilities::AllocSid(v47, v28);
      v31 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F7,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
          (const char *)(unsigned int)v48,
          (int)bIgnoreCase);
        if ( v27 )
        {
          for ( ii = 0; ii < v7; ++ii )
          {
            v50 = v27[ii].Sid;
            if ( v50 )
              FreeSid(v50);
          }
        }
        goto LABEL_69;
      }
      RtlInitUnicodeString(&DestinationString, L"multiPlaneOverlay");
      v51 = RtlDeriveCapabilitySidsFromName(&DestinationString, v105, *(_QWORD *)v47);
      if ( v51 < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x3FA,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                      (const char *)(unsigned int)v51,
                      (int)bIgnoreCase);
        if ( v27 )
        {
          for ( jj = 0; jj < v7; ++jj )
          {
            v53 = v27[jj].Sid;
            if ( v53 )
              FreeSid(v53);
          }
        }
        goto LABEL_63;
      }
      *((_DWORD *)v47 + 2) = 4;
      ++v26;
    }
    if ( (_DWORD)v91 )
    {
      v54 = (OSIntegration::Tools::Capabilities *)&v27[v26];
      v55 = OSIntegration::Tools::Capabilities::AllocSid(v54, v28);
      v31 = v55;
      if ( v55 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x403,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
          (const char *)(unsigned int)v55,
          (int)bIgnoreCase);
        if ( v27 )
        {
          for ( kk = 0; kk < v7; ++kk )
          {
            v57 = v27[kk].Sid;
            if ( v57 )
              FreeSid(v57);
          }
        }
        goto LABEL_69;
      }
      if ( !ConvertStringSidToSidW(L"S-1-15-3-787448254-1207972858-3558633622-1059886964", (PSID *)v54) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x405,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                      v58);
        if ( v27 )
        {
          for ( mm = 0; mm < v7; ++mm )
          {
            v60 = v27[mm].Sid;
            if ( v60 )
              FreeSid(v60);
          }
        }
        goto LABEL_63;
      }
      *((_DWORD *)v54 + 2) = 4;
      ++v26;
    }
    if ( v24 )
    {
      v61 = (OSIntegration::Tools::Capabilities *)&v27[v26];
      v62 = OSIntegration::Tools::Capabilities::AllocSid(v61, v28);
      v31 = v62;
      if ( v62 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
          (const char *)(unsigned int)v62,
          (int)bIgnoreCase);
        if ( v27 )
        {
          for ( nn = 0; nn < v7; ++nn )
          {
            v64 = v27[nn].Sid;
            if ( v64 )
              FreeSid(v64);
          }
        }
        goto LABEL_69;
      }
      if ( !ConvertStringSidToSidW(L"S-1-15-3-3845273463-1331427702-1186551195-1148109977", (PSID *)v61) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x410,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                      v65);
        if ( v27 )
        {
          for ( i1 = 0; i1 < v7; ++i1 )
          {
            v67 = v27[i1].Sid;
            if ( v67 )
              FreeSid(v67);
          }
        }
        goto LABEL_63;
      }
      *((_DWORD *)v61 + 2) = 4;
      ++v26;
    }
    v68 = v88;
    if ( v88 )
    {
      for ( i2 = 0; (unsigned __int64)i2 < 7; ++i2 )
      {
        if ( _bittest(&v68, i2) )
        {
          v70 = (OSIntegration::Tools::Capabilities *)&v27[v26];
          v71 = OSIntegration::Tools::Capabilities::AllocSid(v70, v28);
          v31 = v71;
          if ( v71 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x41D,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
              (const char *)(unsigned int)v71,
              (int)bIgnoreCase);
            if ( v27 )
            {
              for ( i3 = 0; i3 < v7; ++i3 )
              {
                v76 = v27[i3].Sid;
                if ( v76 )
                  FreeSid(v76);
              }
            }
            goto LABEL_69;
          }
          RtlInitUnicodeString(&DestinationString, off_18022A7C0[i2]);
          v72 = RtlDeriveCapabilitySidsFromName(&DestinationString, v105, *(_QWORD *)v70);
          if ( v72 < 0 )
          {
            LastError = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x420,
                          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                          (const char *)(unsigned int)v72,
                          (int)bIgnoreCase);
            if ( v27 )
            {
              for ( i4 = 0; i4 < v7; ++i4 )
              {
                v74 = v27[i4].Sid;
                if ( v74 )
                  FreeSid(v74);
              }
            }
            goto LABEL_63;
          }
          *((_DWORD *)v70 + 2) = 4;
          ++v26;
          v68 = v88;
        }
      }
    }
    if ( v87 )
    {
      v77 = (OSIntegration::Tools::Capabilities *)&v27[v26];
      v78 = OSIntegration::Tools::Capabilities::AllocSid(v77, v28);
      LastError = v78;
      if ( v78 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42B,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
          (const char *)(unsigned int)v78,
          (int)bIgnoreCase);
        if ( v27 )
        {
          for ( i5 = 0; i5 < v7; ++i5 )
          {
            v80 = v27[i5].Sid;
            if ( v80 )
              FreeSid(v80);
          }
        }
        goto LABEL_63;
      }
      RtlInitUnicodeString(&DestinationString, L"gamingContainerResources");
      v81 = RtlDeriveCapabilitySidsFromName(&DestinationString, v105, *(_QWORD *)v77);
      if ( v81 < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x42E,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
                      (const char *)(unsigned int)v81,
                      (int)bIgnoreCase);
        if ( v27 )
        {
          for ( i6 = 0; i6 < v7; ++i6 )
          {
            v83 = v27[i6].Sid;
            if ( v83 )
              FreeSid(v83);
          }
        }
        goto LABEL_63;
      }
      *((_DWORD *)v77 + 2) = 4;
    }
    *v99 = v27;
    *v100 = v7;
    operator delete(0, (unsigned __int64)v28);
    v10 = 0;
    goto LABEL_172;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x366,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewall\\firewallhandler.cpp",
    (const char *)(unsigned int)XMLDOMFromPackage,
    (int)bIgnoreCase);
  v11 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v10;
}

```

## disassembly

```asm
0x1800c72f8  mov     [rsp-8+arg_0], rbx
0x1800c72fd  push    rbp
0x1800c72fe  push    rsi
0x1800c72ff  push    rdi
0x1800c7300  push    r12
0x1800c7302  push    r13
0x1800c7304  push    r14
0x1800c7306  push    r15
0x1800c7308  lea     rbp, [rsp-20h]
0x1800c730d  sub     rsp, 120h
0x1800c7314  mov     rax, cs:__security_cookie
0x1800c731b  xor     rax, rsp
0x1800c731e  mov     [rbp+50h+var_40], rax
0x1800c7322  mov     [rbp+50h+var_B8], r9
0x1800c7326  mov     [rbp+50h+var_C0], r8
0x1800c732a  mov     rbx, rdx
0x1800c732d  mov     [rbp+50h+var_90], rdx
0x1800c7331  xor     r14d, r14d
0x1800c7334  mov     [rsp+150h+var_F0], r14d
0x1800c7339  lea     rax, aConstrainedimp; "constrainedImpersonation"
0x1800c7340  mov     [rbp+50h+SourceString], rax
0x1800c7344  lea     rax, aActivateasuser; "activateAsUser"
0x1800c734b  mov     [rbp+50h+var_80], rax
0x1800c734f  lea     rax, aMuma; "muma"
0x1800c7356  mov     [rbp+50h+var_78], rax
0x1800c735a  xorps   xmm0, xmm0
0x1800c735d  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1800c7362  mov     rax, [rdx+1B0h]
0x1800c7369  lea     r15d, [r14+1]
0x1800c736d  cmp     rax, 0Ch
0x1800c7371  jz      short loc_1800C7385
0x1800c7373  mov     r13d, r14d
0x1800c7376  mov     esi, r14d
0x1800c7379  cmp     rax, 0Bh
0x1800c737d  jnz     short loc_1800C7399
0x1800c737f  cmp     rax, 0Ch
0x1800c7383  jnz     short loc_1800C7391
0x1800c7385  mov     [rsp+150h+var_F0], r15d
0x1800c738a  mov     esi, 4
0x1800c738f  jmp     short loc_1800C7396
0x1800c7391  mov     esi, 3
0x1800c7396  mov     r13d, r15d
0x1800c7399  mov     [rsp+150h+var_110], r14
0x1800c739e  lea     rcx, [rsp+150h+var_110]
0x1800c73a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c73a8  lea     rdx, [rsp+150h+var_110]; struct OSIntegration::Package *
0x1800c73ad  mov     rcx, rbx; this
0x1800c73b0  call    ?GetXMLDOMFromPackage@Tools@OSIntegration@@YAJPEBVPackage@2@PEAPEAUIXMLDOMDocument2@@@Z; OSIntegration::Tools::GetXMLDOMFromPackage(OSIntegration::Package const *,IXMLDOMDocument2 * *)
0x1800c73b5  mov     ebx, eax
0x1800c73b7  test    eax, eax
0x1800c73b9  jns     short loc_1800C73F5
0x1800c73bb  mov     rcx, [rbp+58h]; this
0x1800c73bf  mov     r9d, eax; char *
0x1800c73c2  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800c73c9  mov     edx, 366h; void *
0x1800c73ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c73d3  nop
0x1800c73d4  mov     rcx, [rsp+150h+var_110]
0x1800c73d9  test    rcx, rcx
0x1800c73dc  jz      short loc_1800C73F0
0x1800c73de  mov     [rsp+150h+var_110], r14
0x1800c73e3  mov     rax, [rcx]
0x1800c73e6  mov     rax, [rax+10h]
0x1800c73ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c73ef  nop
0x1800c73f0  jmp     loc_1800C7E49
0x1800c73f5  mov     [rsp+150h+var_E0], r14
0x1800c73fa  mov     [rbp+50h+bstrString], r14
0x1800c73fe  lea     rdx, aMPackageMAppli; "/m:Package/m:Applications/m:Application"...
0x1800c7405  lea     rcx, [rbp+50h+bstrString]
0x1800c7409  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)
0x1800c740e  mov     ebx, eax
0x1800c7410  test    eax, eax
0x1800c7412  jns     short loc_1800C741B
0x1800c7414  mov     edx, 371h
0x1800c7419  jmp     short loc_1800C7453
0x1800c741b  mov     rdi, [rsp+150h+var_110]
0x1800c7420  mov     rax, [rdi]
0x1800c7423  mov     rbx, [rax+128h]
0x1800c742a  lea     rcx, [rsp+150h+var_E0]
0x1800c742f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7434  lea     r8, [rsp+150h+var_E0]
0x1800c7439  mov     rdx, [rbp+50h+bstrString]
0x1800c743d  mov     rcx, rdi
0x1800c7440  mov     rax, rbx
0x1800c7443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7448  mov     ebx, eax
0x1800c744a  test    eax, eax
0x1800c744c  jns     short loc_1800C746B
0x1800c744e  mov     edx, 372h; void *
0x1800c7453  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800c745a  mov     r9d, eax; char *
0x1800c745d  mov     rcx, [rbp+58h]; this
0x1800c7461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7466  jmp     loc_1800C7E29
0x1800c746b  mov     [rsp+150h+var_EC], r14d
0x1800c7470  cmp     [rsp+150h+var_E0], r14
0x1800c7475  jz      loc_1800C753B
0x1800c747b  mov     [rsp+150h+var_E8], r14
0x1800c7480  xorps   xmm0, xmm0
0x1800c7483  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x1800c7487  mov     [rbp+50h+var_A0], r14d
0x1800c748b  mov     [rsp+150h+var_118], r14d
0x1800c7490  lea     rdx, [rsp+150h+var_E8]
0x1800c7495  lea     rcx, [rsp+150h+var_E0]
0x1800c749a  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x1800c749f  mov     ebx, eax
0x1800c74a1  test    eax, eax
0x1800c74a3  jns     short loc_1800C74D7
0x1800c74a5  mov     edx, 37Ah; void *
0x1800c74aa  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800c74b1  mov     r9d, eax; char *
0x1800c74b4  mov     rcx, [rbp+58h]; this
0x1800c74b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c74bd  nop
0x1800c74be  lea     rcx, [rbp+50h+var_B0]; this
0x1800c74c2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800c74c7  nop
0x1800c74c8  lea     rcx, [rsp+150h+var_E8]
0x1800c74cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c74d2  jmp     loc_1800C7E29
0x1800c74d7  lea     r9, [rsp+150h+var_118]; struct Common::StringBuffer *
0x1800c74dc  lea     r8, [rbp+50h+var_B0]; unsigned __int16 *
0x1800c74e0  lea     rdx, stru_180259100; struct IXMLDOMElement *
0x1800c74e7  mov     rcx, [rsp+150h+var_E8]; this
0x1800c74ec  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800c74f1  mov     ebx, eax
0x1800c74f3  test    eax, eax
0x1800c74f5  jns     short loc_1800C74FE
0x1800c74f7  mov     edx, 37Bh
0x1800c74fc  jmp     short loc_1800C74AA
0x1800c74fe  cmp     [rsp+150h+var_118], r14d
0x1800c7503  jz      short loc_1800C7527
0x1800c7505  mov     rcx, qword ptr [rbp+50h+var_B0+8]
0x1800c7509  test    rcx, rcx
0x1800c750c  jz      short loc_1800C7527
0x1800c750e  lea     rdx, aExtendedvideop; "extendedVideoPlayback"
0x1800c7515  call    cs:__imp__o__wcsicmp
0x1800c751b  test    eax, eax
0x1800c751d  jnz     short loc_1800C7527
0x1800c751f  mov     [rsp+150h+var_EC], r15d
0x1800c7524  add     esi, r15d
0x1800c7527  lea     rcx, [rbp+50h+var_B0]; this
0x1800c752b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800c7530  nop
0x1800c7531  lea     rcx, [rsp+150h+var_E8]
0x1800c7536  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c753b  mov     r12d, r14d
0x1800c753e  mov     r15d, r14d
0x1800c7541  mov     [rsp+150h+var_118], r14d
0x1800c7546  mov     edi, r14d
0x1800c7549  lea     rax, off_18022A7C0; "kinectGamechat"
0x1800c7550  movsxd  r14, edi
0x1800c7553  cmp     r14, 7
0x1800c7557  jnb     loc_1800C7625
0x1800c755d  mov     [rsp+150h+var_11C], 0
0x1800c7565  mov     rbx, [rax+r14*8]
0x1800c7569  mov     rax, [rsp+150h+var_110]
0x1800c756e  mov     [rsp+150h+var_100], rax
0x1800c7573  lea     rcx, [rsp+150h+var_100]
0x1800c7578  call    ?InternalAddRef@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalAddRef(void)
0x1800c757d  lea     rax, [rsp+150h+var_11C]
0x1800c7582  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x1800c7587  mov     r9, rbx
0x1800c758a  lea     r8, aLocalNamePacka_10; "/*[local-name()='Package']/*[local-name"...
0x1800c7591  lea     rdx, [rsp+150h+var_100]
0x1800c7596  call    ?CapabilityExists@FirewallHandler@DEH@OSIntegration@@AEAAJV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@PEBG1PEAH@Z; OSIntegration::DEH::FirewallHandler::CapabilityExists(Microsoft::WRL::ComPtr<IXMLDOMDocument2>,ushort const *,ushort const *,int *)
0x1800c759b  mov     ebx, eax
0x1800c759d  test    eax, eax
0x1800c759f  js      short loc_1800C761B
0x1800c75a1  mov     ebx, 1
0x1800c75a6  cmp     [rsp+150h+var_11C], 0
0x1800c75ab  jz      short loc_1800C7614
0x1800c75ad  mov     ecx, edi
0x1800c75af  mov     eax, ebx
0x1800c75b1  shl     eax, cl
0x1800c75b3  or      [rsp+150h+var_118], eax
0x1800c75b7  add     esi, ebx
0x1800c75b9  mov     [rsp+150h+bIgnoreCase], ebx; bIgnoreCase
0x1800c75bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c75c1  mov     r9d, eax; cchCount2
0x1800c75c4  lea     r8, aKinectaudio; "kinectAudio"
0x1800c75cb  mov     edx, eax; cchCount1
0x1800c75cd  lea     rcx, off_18022A7C0; "kinectGamechat"
0x1800c75d4  mov     rcx, [rcx+r14*8]; lpString1
0x1800c75d8  call    cs:__imp_CompareStringOrdinal
0x1800c75de  cmp     eax, 2
0x1800c75e1  jnz     short loc_1800C75E8
0x1800c75e3  mov     r12d, ebx
0x1800c75e6  jmp     short loc_1800C7614
0x1800c75e8  mov     [rsp+150h+bIgnoreCase], ebx; bIgnoreCase
0x1800c75ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c75f0  mov     r9d, eax; cchCount2
0x1800c75f3  lea     r8, aKinectvision; "kinectVision"
0x1800c75fa  mov     edx, eax; cchCount1
0x1800c75fc  lea     rax, off_18022A7C0; "kinectGamechat"
0x1800c7603  mov     rcx, [rax+r14*8]; lpString1
0x1800c7607  call    cs:__imp_CompareStringOrdinal
0x1800c760d  cmp     eax, 2
0x1800c7610  cmovz   r15d, ebx
0x1800c7614  add     edi, ebx
0x1800c7616  jmp     loc_1800C7549
0x1800c761b  mov     edx, 387h
0x1800c7620  jmp     loc_1800C7453
0x1800c7625  xor     edi, edi
0x1800c7627  mov     dword ptr [rsp+150h+var_100], edi
0x1800c762b  test    r12d, r12d
0x1800c762e  jz      short loc_1800C768A
0x1800c7630  mov     [rsp+150h+var_11C], edi
0x1800c7634  mov     rax, [rsp+150h+var_110]
0x1800c7639  mov     [rsp+150h+var_108], rax
0x1800c763e  lea     rcx, [rsp+150h+var_108]
0x1800c7643  call    ?InternalAddRef@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalAddRef(void)
0x1800c7648  lea     rax, [rsp+150h+var_11C]
0x1800c764d  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x1800c7652  lea     r9, aMicrophone; "microphone"
0x1800c7659  lea     r8, aLocalNamePacka_18; "/*[local-name()='Package']/*[local-name"...
0x1800c7660  lea     rdx, [rsp+150h+var_108]
0x1800c7665  call    ?CapabilityExists@FirewallHandler@DEH@OSIntegration@@AEAAJV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@PEBG1PEAH@Z; OSIntegration::DEH::FirewallHandler::CapabilityExists(Microsoft::WRL::ComPtr<IXMLDOMDocument2>,ushort const *,ushort const *,int *)
0x1800c766a  mov     ebx, eax
0x1800c766c  test    eax, eax
0x1800c766e  jns     short loc_1800C767A
0x1800c7670  mov     edx, 39Eh
0x1800c7675  jmp     loc_1800C7453
0x1800c767a  cmp     [rsp+150h+var_11C], edi
0x1800c767e  jnz     short loc_1800C768A
0x1800c7680  mov     dword ptr [rsp+150h+var_100], 1
0x1800c7688  inc     esi
0x1800c768a  mov     r12d, edi
0x1800c768d  mov     dword ptr [rsp+150h+var_108], edi
0x1800c7691  test    r15d, r15d
0x1800c7694  jz      short loc_1800C76F3
0x1800c7696  mov     [rsp+150h+var_11C], edi
0x1800c769a  mov     rax, [rsp+150h+var_110]
0x1800c769f  mov     [rsp+150h+var_F8], rax
0x1800c76a4  lea     rcx, [rsp+150h+var_F8]
0x1800c76a9  call    ?InternalAddRef@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalAddRef(void)
0x1800c76ae  lea     rax, [rsp+150h+var_11C]
0x1800c76b3  mov     qword ptr [rsp+150h+bIgnoreCase], rax; int
0x1800c76b8  lea     r9, aWebcam; "webcam"
0x1800c76bf  lea     r8, aLocalNamePacka_18; "/*[local-name()='Package']/*[local-name"...
0x1800c76c6  lea     rdx, [rsp+150h+var_F8]
0x1800c76cb  call    ?CapabilityExists@FirewallHandler@DEH@OSIntegration@@AEAAJV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@PEBG1PEAH@Z; OSIntegration::DEH::FirewallHandler::CapabilityExists(Microsoft::WRL::ComPtr<IXMLDOMDocument2>,ushort const *,ushort const *,int *)
0x1800c76d0  mov     ebx, eax
0x1800c76d2  test    eax, eax
0x1800c76d4  jns     short loc_1800C76E0
0x1800c76d6  mov     edx, 3A9h
0x1800c76db  jmp     loc_1800C7453
0x1800c76e0  cmp     [rsp+150h+var_11C], edi
0x1800c76e4  jnz     short loc_1800C76F3
0x1800c76e6  mov     r12d, 1
0x1800c76ec  mov     dword ptr [rsp+150h+var_108], r12d
0x1800c76f1  inc     esi
0x1800c76f3  mov     [rsp+150h+var_11C], edi
0x1800c76f7  cmp     cs:?g_platform@Platform@Deployment@Common@@3KA, 5; ulong Common::Deployment::Platform::g_platform
0x1800c76fe  jnz     short loc_1800C7734
0x1800c7700  mov     [rsp+150h+var_120], dil
0x1800c7705  lea     rdx, [rsp+150h+var_120]; bool *
0x1800c770a  mov     rcx, [rbp+50h+var_90]; this
0x1800c770e  call    ?GetHasGameOSPackageDependency@Package@OSIntegration@@QEBAJPEA_N@Z; OSIntegration::Package::GetHasGameOSPackageDependency(bool *)
0x1800c7713  mov     ebx, eax
0x1800c7715  test    eax, eax
0x1800c7717  jns     short loc_1800C7723
0x1800c7719  mov     edx, 3B6h
0x1800c771e  jmp     loc_1800C7453
0x1800c7723  cmp     [rsp+150h+var_120], dil
0x1800c7728  jz      short loc_1800C7734
0x1800c772a  mov     [rsp+150h+var_11C], 1
0x1800c7732  inc     esi
0x1800c7734  mov     rax, [rbp+50h+var_C0]
0x1800c7738  mov     [rax], rdi
0x1800c773b  mov     rax, [rbp+50h+var_B8]
0x1800c773f  mov     [rax], edi
0x1800c7741  test    esi, esi
0x1800c7743  jnz     short loc_1800C774C
0x1800c7745  mov     ebx, edi
0x1800c7747  jmp     loc_1800C7E29
0x1800c774c  mov     r14d, edi
0x1800c774f  mov     edi, esi
0x1800c7751  mov     eax, 10h
0x1800c7756  mul     rdi
0x1800c7759  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c7760  cmovb   rax, rcx
0x1800c7764  mov     rcx, rax; unsigned __int64
0x1800c7767  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c776c  mov     rbx, rax
0x1800c776f  shl     rdi, 4
0x1800c7773  mov     r8, rdi; Size
0x1800c7776  xor     edx, edx; Val
0x1800c7778  mov     rcx, rax; void *
0x1800c777b  call    memset_0
0x1800c7780  test    r13d, r13d
0x1800c7783  jz      loc_1800C7887
0x1800c7789  cmp     r14d, 3
0x1800c778d  jnb     loc_1800C7882
0x1800c7793  mov     r12d, r14d
0x1800c7796  mov     edi, r14d
0x1800c7799  shl     rdi, 4
0x1800c779d  add     rdi, rbx
0x1800c77a0  mov     rcx, rdi; this
  ... truncated ...
```

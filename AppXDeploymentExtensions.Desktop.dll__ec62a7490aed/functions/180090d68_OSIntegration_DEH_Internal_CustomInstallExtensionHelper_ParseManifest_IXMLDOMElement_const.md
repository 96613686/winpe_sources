# OSIntegration::DEH::Internal::CustomInstallExtensionHelper::ParseManifest(IXMLDOMElement const *)

- ea: `0x180090d68`
- end: `0x1800911a2`
- name: `?ParseManifest@CustomInstallExtensionHelper@Internal@DEH@OSIntegration@@QEAAXPEBUIXMLDOMElement@@@Z`
- size: `1082`
- prototype: `void(OSIntegration::DEH::Internal::CustomInstallExtensionHelper *__hidden this, const struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800eeeb0`

## callees

- `0x180006970`
- `0x180011020`
- `0x180012da0`
- `0x180017ba0`
- `0x18002f55c`
- `0x1800353c0`
- `0x18004a240`
- `0x18004dfe4`
- `0x180059424`
- `0x180064a88`
- `0x18008d8dc`
- `0x180090d68`
- `0x1800914c0`
- `0x180091b3c`
- `0x1800a8ac0`
- `0x1800af1bc`
- `0x1800af220`
- `0x1800af918`
- `0x1800da9f0`
- `0x1800ee9f4`
- `0x1800eed04`
- `0x1800ef060`
- `0x1800ef56c`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090edb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090edb`

## string_xrefs

- `0x180090fd3`: `*/*[local-name()='RepairActions']/*[local-name()='RepairAction']`
- `0x180090faf`: `*/*[local-name()='InstallActions']/*[local-name()='InstallAction']`
- `0x180090fc1`: `*/*[local-name()='UninstallActions']/*[local-name()='UninstallAction']`
- `0x180090ddf`: `Microsoft.classicAppInstaller_8wekyb3d8bbwe`
- `0x180090e50`: `*[local-name()='CustomInstall']`
- `0x180090dc9`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090dff`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090e21`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090e67`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090eab`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090eff`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090f54`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180090f99`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180091166`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009117b`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180091190`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall OSIntegration::DEH::Internal::CustomInstallExtensionHelper::ParseManifest(
        OSIntegration::DEH::Internal::CustomInstallExtensionHelper *this,
        const struct IXMLDOMElement *a2)
{
  OSIntegration::Package *v4; // rbx
  int v5; // r12d
  int ManifestReader; // eax
  int HasCapabilityInManifest; // eax
  struct IXMLDOMElement **v8; // r9
  int XMLElementFromQuery; // eax
  int AttributeValueStringFromElement; // eax
  bool v11; // zf
  char v12; // al
  int v13; // eax
  const struct Common::COMMON_STRING *v14; // rdx
  int UserIDByUserSid; // eax
  unsigned int i; // r15d
  struct IXMLDOMNodeList **v17; // r9
  int XMLElementsFromQuery; // eax
  int v19; // eax
  struct IXMLDOMElement **v20; // r9
  int ElementFromNodeList; // eax
  _DWORD *v22; // rbx
  __int64 v23; // r8
  __int64 InstallActionArrayByType; // rax
  const struct std::nothrow_t *v25; // rdx
  bool *bIgnoreCase; // [rsp+20h] [rbp-79h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-79h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-79h]
  struct IXMLDOMElement v29; // [rsp+30h] [rbp-69h] BYREF
  struct IXMLDOMNodeList v30; // [rsp+38h] [rbp-61h] BYREF
  LPCWCH lpString2[2]; // [rsp+40h] [rbp-59h] BYREF
  int v32; // [rsp+50h] [rbp-49h]
  void *v33[2]; // [rsp+58h] [rbp-41h] BYREF
  int v34; // [rsp+68h] [rbp-31h]
  _QWORD v35[3]; // [rsp+70h] [rbp-29h] BYREF
  char v36; // [rsp+88h] [rbp-11h]
  _DWORD v37[2]; // [rsp+90h] [rbp-9h]
  OLECHAR *strIn; // [rsp+98h] [rbp-1h]
  int v39; // [rsp+A0h] [rbp+7h]
  const wchar_t *v40; // [rsp+A8h] [rbp+Fh]
  int v41; // [rsp+B0h] [rbp+17h]
  const wchar_t *v42; // [rsp+B8h] [rbp+1Fh]
  _DWORD *v43; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  int v45; // [rsp+110h] [rbp+77h] BYREF
  struct IXMLDOMElement v46; // [rsp+118h] [rbp+7Fh] BYREF

  v4 = (OSIntegration::Package *)*((_QWORD *)this + 2);
  v5 = 0;
  if ( !*((_BYTE *)v4 + 413) )
  {
    v46.lpVtbl = 0;
    LOBYTE(v45) = 0;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
    ManifestReader = OSIntegration::Package::GetManifestReader(v4, (struct IAppxManifestReader **)&v46);
    if ( ManifestReader < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)ManifestReader,
        (int)bIgnoreCase);
    HasCapabilityInManifest = Common::Deployment::HasCapabilityInManifest(
                                (Common::Deployment *)v46.lpVtbl,
                                (struct IAppxManifestReader *)7,
                                (enum APPX_CAPABILITY_CLASS_TYPE)L"Microsoft.classicAppInstaller_8wekyb3d8bbwe",
                                (const unsigned __int16 *)&v45,
                                bIgnoreCase);
    if ( HasCapabilityInManifest < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)HasCapabilityInManifest,
        (int)bIgnoreCase);
    if ( !(_BYTE)v45 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)0x80080204LL,
        (int)bIgnoreCase);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
  }
  v29.lpVtbl = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v29);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                          (OLECHAR *)L"*[local-name()='CustomInstall']",
                          (const unsigned __int16 *)a2,
                          &v29,
                          v8);
  if ( XMLElementFromQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
      (const char *)(unsigned int)XMLElementFromQuery,
      (int)bIgnoreCase);
  v45 = 0;
  *(_OWORD *)lpString2 = 0;
  v32 = 0;
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      (Common::Xml *)v29.lpVtbl,
                                      (struct IXMLDOMElement *)&stru_1801D0688,
                                      (const unsigned __int16 *)lpString2,
                                      (struct Common::StringBuffer *)&v45,
                                      (int *)bIgnoreCase);
  if ( AttributeValueStringFromElement < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromElement,
      (int)bIgnoreCasea);
  if ( !v45 || (v11 = CompareStringOrdinal(&Value, -1, lpString2[1], -1, 0) == 2, v12 = 0, v11) )
    v12 = 1;
  if ( v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
      (const char *)0x80080204LL,
      (int)bIgnoreCasea);
  Common::StringBuffer::SetValue(
    (OSIntegration::DEH::Internal::CustomInstallExtensionHelper *)((char *)this + 24),
    lpString2[1],
    (unsigned int)lpString2[0]);
  v45 = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v13 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)v29.lpVtbl,
          (struct IXMLDOMElement *)&stru_1801D0660,
          (const unsigned __int16 *)v33,
          (struct Common::StringBuffer *)&v45,
          bIgnoreCasea);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCaseb);
  if ( v45 )
  {
    if ( OSIntegration::Tools::IsBooleanValueTrue((OSIntegration::Tools *)v33, v14) )
    {
      *((_BYTE *)this + 56) = 1;
      UserIDByUserSid = StateRepository::Entity::User::Get_UserIDByUserSid(
                          *((struct StateRepository::Database **)this + 1),
                          *((void **)this + 6),
                          (__int64 *)this + 8);
      if ( UserIDByUserSid < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
          (const char *)(unsigned int)UserIDByUserSid,
          bIgnoreCaseb);
    }
  }
  v37[0] = 0;
  strIn = L"*/*[local-name()='InstallActions']/*[local-name()='InstallAction']";
  v39 = 1;
  v40 = L"*/*[local-name()='UninstallActions']/*[local-name()='UninstallAction']";
  v41 = 2;
  v42 = L"*/*[local-name()='RepairActions']/*[local-name()='RepairAction']";
  for ( i = 0; i < 3; ++i )
  {
    v46.lpVtbl = 0;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
    XMLElementsFromQuery = Common::Xml::GetXMLElementsFromQuery(
                             (&strIn)[2 * (int)i],
                             (const unsigned __int16 *)a2,
                             &v46,
                             v17);
    if ( XMLElementsFromQuery < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)XMLElementsFromQuery,
        bIgnoreCaseb);
    v45 = 0;
    v19 = (*((__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, int *))v46.lpVtbl->QueryInterface + 8))(
            v46.lpVtbl,
            &v45);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v19,
        bIgnoreCaseb);
    memset(v35, 0, sizeof(v35));
    v36 = 1;
    if ( v45 > 0 )
    {
      do
      {
        v30.lpVtbl = 0;
        ElementFromNodeList = Common::Xml::GetElementFromNodeList(
                                (Common::Xml *)(unsigned int)v5,
                                (int)v46.lpVtbl,
                                &v30,
                                v20);
        if ( ElementFromNodeList < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA4,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
            (const char *)(unsigned int)ElementFromNodeList,
            bIgnoreCaseb);
        v22 = operator new(0x60u);
        memset_0(v22, 0, 0x60u);
        v22[18] = -1;
        v43 = v22;
        OSIntegration::DEH::Internal::CustomInstallActionHelper::ParseManifestEntry(
          (__int64)v22,
          v37[4 * i],
          v23,
          (Common::Xml *)v30.lpVtbl);
        OSIntegration::DEH::Internal::CustomInstallAction::SetIndex(
          (OSIntegration::DEH::Internal::CustomInstallAction *)v22,
          v5);
        Common::Array<OSIntegration::DEH::Internal::Print3DWorkflowHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::Print3DWorkflowHelper,OSIntegration::DEH::Internal::Print3DWorkflowHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::Print3DWorkflowHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::Print3DWorkflowHelper,Common::NoKey>>::Add(
          v35,
          v22);
        Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionHelper>(0);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v30);
        ++v5;
      }
      while ( v5 < v45 );
      v5 = 0;
    }
    InstallActionArrayByType = OSIntegration::DEH::Internal::CustomInstallExtensionHelper::GetInstallActionArrayByType(
                                 this,
                                 (unsigned int)v37[4 * i]);
    Common::Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,unsigned short const *,Common::ContainerOperations<unsigned short const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,unsigned short const *>>::operator=(
      InstallActionArrayByType,
      v35);
    Common::Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,unsigned short const *,Common::ContainerOperations<unsigned short const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,unsigned short const *>>::~Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,unsigned short const *,Common::ContainerOperations<unsigned short const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,unsigned short const *>>(v35);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
  }
  if ( v33[1] )
    operator delete(v33[1], v25);
  if ( lpString2[1] )
    operator delete((void *)lpString2[1], v25);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v29);
}

```

## disassembly

```asm
0x180090d68  mov     [rsp-8+arg_0], rbx
0x180090d6d  mov     [rsp-8+arg_8], rdi
0x180090d72  push    rbp
0x180090d73  push    r12
0x180090d75  push    r13
0x180090d77  push    r14
0x180090d79  push    r15
0x180090d7b  lea     rbp, [rsp-37h]
0x180090d80  sub     rsp, 0D0h
0x180090d87  mov     r13, rdx
0x180090d8a  mov     rdi, rcx
0x180090d8d  mov     rbx, [rcx+10h]
0x180090d91  xor     r12d, r12d
0x180090d94  cmp     [rbx+19Dh], r12b
0x180090d9b  jnz     loc_180090E3C
0x180090da1  mov     [rbp+57h+arg_18.lpVtbl], r12
0x180090da5  mov     byte ptr [rbp+57h+arg_10], r12b
0x180090da9  lea     rcx, [rbp+57h+arg_18]
0x180090dad  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090db2  lea     rdx, [rbp+57h+arg_18]; struct IAppxManifestReader **
0x180090db6  mov     rcx, rbx; this
0x180090db9  call    ?GetManifestReader@Package@OSIntegration@@QEBAJPEAPEAUIAppxManifestReader@@@Z; OSIntegration::Package::GetManifestReader(IAppxManifestReader * *)
0x180090dbe  mov     rcx, [rbp+5Fh]; this
0x180090dc2  test    eax, eax
0x180090dc4  jns     short loc_180090DDB
0x180090dc6  mov     r9d, eax; char *
0x180090dc9  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090dd0  lea     edx, [r12+65h]; void *
0x180090dd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090ddb  lea     r9, [rbp+57h+arg_10]; unsigned __int16 *
0x180090ddf  lea     r8, aMicrosoftClass; "Microsoft.classicAppInstaller_8wekyb3d8"...
0x180090de6  mov     edx, 7; struct IAppxManifestReader *
0x180090deb  mov     rcx, [rbp+57h+arg_18.lpVtbl]; this
0x180090def  call    ?HasCapabilityInManifest@Deployment@Common@@YAJPEAUIAppxManifestReader@@W4APPX_CAPABILITY_CLASS_TYPE@@PEBGPEA_N@Z; Common::Deployment::HasCapabilityInManifest(IAppxManifestReader *,APPX_CAPABILITY_CLASS_TYPE,ushort const *,bool *)
0x180090df4  mov     rcx, [rbp+5Fh]; this
0x180090df8  test    eax, eax
0x180090dfa  jns     short loc_180090E11
0x180090dfc  mov     r9d, eax; char *
0x180090dff  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090e06  mov     edx, 67h ; 'g'; void *
0x180090e0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090e11  cmp     byte ptr [rbp+57h+arg_10], r12b
0x180090e15  jnz     short loc_180090E33
0x180090e17  mov     rcx, [rbp+5Fh]; this
0x180090e1b  mov     r9d, 80080204h; char *
0x180090e21  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090e28  mov     edx, 6Bh ; 'k'; void *
0x180090e2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090e33  lea     rcx, [rbp+57h+arg_18]
0x180090e37  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090e3c  mov     [rbp+57h+var_C0.lpVtbl], r12
0x180090e40  lea     rcx, [rbp+57h+var_C0]
0x180090e44  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090e49  lea     r8, [rbp+57h+var_C0]; struct IXMLDOMElement *
0x180090e4d  mov     rdx, r13; unsigned __int16 *
0x180090e50  lea     rcx, aLocalNameCusto; "*[local-name()='CustomInstall']"
0x180090e57  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x180090e5c  mov     rcx, [rbp+5Fh]; this
0x180090e60  test    eax, eax
0x180090e62  jns     short loc_180090E79
0x180090e64  mov     r9d, eax; char *
0x180090e67  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090e6e  mov     edx, 72h ; 'r'; void *
0x180090e73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090e79  mov     [rbp+57h+arg_10], r12d
0x180090e7d  xorps   xmm0, xmm0
0x180090e80  movups  xmmword ptr [rbp+57h+lpString2], xmm0
0x180090e84  mov     [rbp+57h+var_A0], r12d
0x180090e88  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x180090e8c  lea     r8, [rbp+57h+lpString2]; unsigned __int16 *
0x180090e90  lea     rdx, stru_1801D0688; struct IXMLDOMElement *
0x180090e97  mov     rcx, [rbp+57h+var_C0.lpVtbl]; this
0x180090e9b  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180090ea0  mov     rcx, [rbp+5Fh]; this
0x180090ea4  test    eax, eax
0x180090ea6  jns     short loc_180090EBD
0x180090ea8  mov     r9d, eax; char *
0x180090eab  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090eb2  mov     edx, 77h ; 'w'; void *
0x180090eb7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090ebd  or      eax, 0FFFFFFFFh
0x180090ec0  cmp     [rbp+57h+arg_10], r12d
0x180090ec4  jz      short loc_180090EEF
0x180090ec6  mov     [rsp+0F0h+bIgnoreCase], r12d; int
0x180090ecb  mov     r9d, eax; cchCount2
0x180090ece  mov     r8, [rbp+57h+lpString2+8]; lpString2
0x180090ed2  mov     edx, eax; cchCount1
0x180090ed4  lea     rcx, Value; lpString1
0x180090edb  call    cs:__imp_CompareStringOrdinal
0x180090ee2  nop     dword ptr [rax+rax+00h]
0x180090ee7  add     eax, 0FFFFFFFEh
0x180090eea  mov     al, r12b
0x180090eed  jnz     short loc_180090EF1
0x180090eef  mov     al, 1
0x180090ef1  mov     rcx, [rbp+5Fh]; this
0x180090ef5  test    al, al
0x180090ef7  jz      short loc_180090F11
0x180090ef9  mov     r9d, 80080204h; char *
0x180090eff  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090f06  mov     edx, 7Ah ; 'z'; void *
0x180090f0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090f11  lea     rcx, [rdi+18h]; this
0x180090f15  mov     r8d, dword ptr [rbp+57h+lpString2]; unsigned int
0x180090f19  mov     rdx, [rbp+57h+lpString2+8]; unsigned __int16 *
0x180090f1d  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180090f22  mov     [rbp+57h+arg_10], r12d
0x180090f26  xorps   xmm0, xmm0
0x180090f29  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180090f2d  mov     [rbp+57h+var_88], r12d
0x180090f31  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x180090f35  lea     r8, [rbp+57h+var_98]; unsigned __int16 *
0x180090f39  lea     rdx, stru_1801D0660; struct IXMLDOMElement *
0x180090f40  mov     rcx, [rbp+57h+var_C0.lpVtbl]; this
0x180090f44  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180090f49  mov     rcx, [rbp+5Fh]; this
0x180090f4d  test    eax, eax
0x180090f4f  jns     short loc_180090F66
0x180090f51  mov     r9d, eax; char *
0x180090f54  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090f5b  mov     edx, 80h; void *
0x180090f60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090f66  cmp     [rbp+57h+arg_10], r12d
0x180090f6a  jz      short loc_180090FAB
0x180090f6c  lea     rcx, [rbp+57h+var_98]; this
0x180090f70  call    ?IsBooleanValueTrue@Tools@OSIntegration@@YA_NPEBUCOMMON_STRING@Common@@@Z; OSIntegration::Tools::IsBooleanValueTrue(Common::COMMON_STRING const *)
0x180090f75  test    al, al
0x180090f77  jz      short loc_180090FAB
0x180090f79  mov     byte ptr [rdi+38h], 1
0x180090f7d  lea     r8, [rdi+40h]; __int64 *
0x180090f81  mov     rdx, [rdi+30h]; void *
0x180090f85  mov     rcx, [rdi+8]; struct StateRepository::Database *
0x180090f89  call    ?Get_UserIDByUserSid@User@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEA_J@Z; StateRepository::Entity::User::Get_UserIDByUserSid(StateRepository::Database &,void *,__int64 *)
0x180090f8e  mov     rcx, [rbp+5Fh]; this
0x180090f92  test    eax, eax
0x180090f94  jns     short loc_180090FAB
0x180090f96  mov     r9d, eax; char *
0x180090f99  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180090fa0  mov     edx, 85h; void *
0x180090fa5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090fab  mov     [rbp+57h+var_60], r12d
0x180090faf  lea     rax, aLocalNameInsta; "*/*[local-name()='InstallActions']/*[lo"...
0x180090fb6  mov     [rbp+57h+strIn], rax
0x180090fba  mov     [rbp+57h+var_50], 1
0x180090fc1  lea     rax, aLocalNameUnins; "*/*[local-name()='UninstallActions']/*["...
0x180090fc8  mov     [rbp+57h+var_48], rax
0x180090fcc  mov     [rbp+57h+var_40], 2
0x180090fd3  lea     rax, aLocalNameRepai; "*/*[local-name()='RepairActions']/*[loc"...
0x180090fda  mov     [rbp+57h+var_38], rax
0x180090fde  mov     r15d, r12d
0x180090fe1  mov     [rbp+57h+arg_18.lpVtbl], r12
0x180090fe5  lea     rcx, [rbp+57h+arg_18]
0x180090fe9  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090fee  movsxd  r14, r15d
0x180090ff1  add     r14, r14
0x180090ff4  lea     r8, [rbp+57h+arg_18]; struct IXMLDOMElement *
0x180090ff8  mov     rdx, r13; unsigned __int16 *
0x180090ffb  mov     rcx, [rbp+r14*8+57h+strIn]; strIn
0x180091000  call    ?GetXMLElementsFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAUIXMLDOMNodeList@@@Z; Common::Xml::GetXMLElementsFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMNodeList * *)
0x180091005  mov     rcx, [rbp+5Fh]; this
0x180091009  test    eax, eax
0x18009100b  js      loc_18009118D
0x180091011  mov     [rbp+57h+arg_10], r12d
0x180091015  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x180091019  mov     rax, [rcx]
0x18009101c  lea     rdx, [rbp+57h+arg_10]
0x180091020  mov     rax, [rax+40h]
0x180091024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091029  mov     rcx, [rbp+5Fh]; this
0x18009102d  test    eax, eax
0x18009102f  js      loc_180091178
0x180091035  mov     [rbp+57h+var_80], r12
0x180091039  mov     [rbp+57h+var_78], r12
0x18009103d  mov     [rbp+57h+var_70], r12
0x180091041  mov     [rbp+57h+var_68], 1
0x180091045  cmp     [rbp+57h+arg_10], r12d
0x180091049  jle     loc_1800910E3
0x18009104f  mov     [rbp+57h+var_B8.lpVtbl], 0
0x180091057  lea     r8, [rbp+57h+var_B8]; struct IXMLDOMNodeList *
0x18009105b  mov     rdx, [rbp+57h+arg_18.lpVtbl]; int
0x18009105f  mov     ecx, r12d; this
0x180091062  call    ?GetElementFromNodeList@Xml@Common@@YAJJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMElement@@@Z; Common::Xml::GetElementFromNodeList(long,IXMLDOMNodeList *,IXMLDOMElement * *)
0x180091067  mov     rcx, [rbp+5Fh]; this
0x18009106b  test    eax, eax
0x18009106d  js      loc_180091163
0x180091073  mov     ecx, 60h ; '`'; Size
0x180091078  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009107d  mov     rbx, rax
0x180091080  xor     edx, edx; Val
0x180091082  lea     r8d, [rdx+60h]; Size
0x180091086  mov     rcx, rax; void *
0x180091089  call    memset_0
0x18009108e  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180091095  mov     [rbp+57h+var_30], rbx
0x180091099  mov     r9, [rbp+57h+var_B8.lpVtbl]
0x18009109d  mov     edx, [rbp+r14*8+57h+var_60]
0x1800910a2  mov     rcx, rbx
0x1800910a5  call    ?ParseManifestEntry@CustomInstallActionHelper@Internal@DEH@OSIntegration@@QEAAXW4Type@CustomInstallAction@234@PEBGPEAUIXMLDOMElement@@@Z; OSIntegration::DEH::Internal::CustomInstallActionHelper::ParseManifestEntry(OSIntegration::DEH::Internal::CustomInstallAction::Type,ushort const *,IXMLDOMElement *)
0x1800910aa  mov     edx, r12d; int
0x1800910ad  mov     rcx, rbx; this
0x1800910b0  call    ?SetIndex@CustomInstallAction@Internal@DEH@OSIntegration@@QEAAXH@Z; OSIntegration::DEH::Internal::CustomInstallAction::SetIndex(int)
0x1800910b5  mov     rdx, rbx
0x1800910b8  lea     rcx, [rbp+57h+var_80]
0x1800910bc  call    ?Add@?$Array@VPrint3DWorkflowHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VPrint3DWorkflowHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VPrint3DWorkflowHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VPrint3DWorkflowHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@QEAAJPEAVPrint3DWorkflowHelper@Internal@DEH@OSIntegration@@@Z; Common::Array<OSIntegration::DEH::Internal::Print3DWorkflowHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::Print3DWorkflowHelper,OSIntegration::DEH::Internal::Print3DWorkflowHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::Print3DWorkflowHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::Print3DWorkflowHelper,Common::NoKey>>::Add(OSIntegration::DEH::Internal::Print3DWorkflowHelper *)
0x1800910c1  nop
0x1800910c2  xor     ecx, ecx
0x1800910c4  call    ??$AutoPtrDeallocate@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@@Common@@YAXPEAVCustomInstallActionHelper@Internal@DEH@OSIntegration@@@Z; Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionHelper>(OSIntegration::DEH::Internal::CustomInstallActionHelper *)
0x1800910c9  nop
0x1800910ca  lea     rcx, [rbp+57h+var_B8]
0x1800910ce  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800910d3  inc     r12d
0x1800910d6  cmp     r12d, [rbp+57h+arg_10]
0x1800910da  jl      loc_18009104F
0x1800910e0  xor     r12d, r12d
0x1800910e3  mov     edx, [rbp+r14*8+57h+var_60]
0x1800910e8  mov     rcx, rdi
0x1800910eb  call    ?GetInstallActionArrayByType@CustomInstallExtensionHelper@Internal@DEH@OSIntegration@@QEAAAEAV?$Array@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@V1234@@Common@@PEBGV?$ContainerOperations@PEBGVCustomInstallActionHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@PEBG@6@@Common@@W4Type@CustomInstallAction@234@@Z; OSIntegration::DEH::Internal::CustomInstallExtensionHelper::GetInstallActionArrayByType(OSIntegration::DEH::Internal::CustomInstallAction::Type)
0x1800910f0  lea     rdx, [rbp+57h+var_80]
0x1800910f4  mov     rcx, rax
0x1800910f7  call    ??4?$Array@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@V1234@@Common@@PEBGV?$ContainerOperations@PEBGVCustomInstallActionHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@PEBG@6@@Common@@QEAAAEAV01@$$QEAV01@@Z; Common::Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,ushort const *,Common::ContainerOperations<ushort const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,ushort const *>>::operator=(Common::Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,ushort const *,Common::ContainerOperations<ushort const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,ushort const *>> &&)
0x1800910fc  nop
0x1800910fd  lea     rcx, [rbp+57h+var_80]
0x180091101  call    ??1?$Array@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@V1234@@Common@@PEBGV?$ContainerOperations@PEBGVCustomInstallActionHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionHelper@Internal@DEH@OSIntegration@@PEBG@6@@Common@@QEAA@XZ; Common::Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,ushort const *,Common::ContainerOperations<ushort const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,ushort const *>>::~Array<OSIntegration::DEH::Internal::CustomInstallActionHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,OSIntegration::DEH::Internal::CustomInstallActionHelper>,ushort const *,Common::ContainerOperations<ushort const *,OSIntegration::DEH::Internal::CustomInstallActionHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionHelper,ushort const *>>(void)
0x180091106  nop
0x180091107  lea     rcx, [rbp+57h+arg_18]
0x18009110b  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180091110  inc     r15d
0x180091113  cmp     r15d, 3
0x180091117  jb      loc_180090FE1
0x18009111d  mov     rcx, [rbp+57h+var_98+8]; void *
0x180091121  test    rcx, rcx
0x180091124  jz      short loc_18009112C
0x180091126  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009112b  nop
0x18009112c  cmp     [rbp+57h+lpString2+8], r12
0x180091130  jz      short loc_18009113C
0x180091132  mov     rcx, [rbp+57h+lpString2+8]; void *
0x180091136  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009113b  nop
0x18009113c  lea     rcx, [rbp+57h+var_C0]
0x180091140  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180091145  lea     r11, [rsp+0F0h+var_20]
0x18009114d  mov     rbx, [r11+30h]
0x180091151  mov     rdi, [r11+38h]
0x180091155  mov     rsp, r11
0x180091158  pop     r15
0x18009115a  pop     r14
0x18009115c  pop     r13
0x18009115e  pop     r12
0x180091160  pop     rbp
0x180091161  retn
0x180091163  mov     r9d, eax; char *
0x180091166  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009116d  mov     edx, 0A4h; void *
0x180091172  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180091178  mov     r9d, eax; char *
0x18009117b  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180091182  mov     edx, 9Ch; void *
0x180091187  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009118d  mov     r9d, eax; char *
0x180091190  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180091197  mov     edx, 98h; void *
0x18009119c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
